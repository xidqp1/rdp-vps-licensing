# RDP VPS: Is Windows Licensed, How Many People Can Log In, and Which Plan Actually Runs Your Apps? (Full Plan Table)

An RDP VPS is a Windows desktop that lives in a datacenter instead of on your desk. It runs around the clock, has its own IP address, and you open it with Remote Desktop — `mstsc` on Windows, Microsoft's Windows App on macOS, iOS or Android, Remmina or FreeRDP on Linux — and everything you left open is still there when you reconnect from a different device. Before you pay for one, five things decide whether the plan is usable or a refund request waiting to happen: which Windows edition you get and who owns the licence, how many people can be signed in at the same time, where the machine sits and whether the IPv4 is yours alone, how long the refund window is, and whether the RAM can carry a desktop at all.

> **If you're in a hurry**
> Single user, remote office, scripts that need to keep running: the 2-core / 2 GB tier is the smallest one that behaves like a real Windows desktop. Trading terminals, browser automation or several apps open at once: go to 4 cores / 4 GB. If your traffic is continuous rather than bursty, the unmetered tiers matter more than the core count. Whatever you pick, confirm with sales that Windows installation is supported on that plan and what it means for licensing before you pay.
> 👉 [Check the 2-core plan that can actually carry a Windows desktop](https://lisahost.com/cart.php?a=add&pid=71&aff=1587)

## RDP VPS vs a plain VPS vs a dedicated server

The confusion is worth clearing up, because the three products are sold with similar specs and wildly different purposes.

A **VPS** is usually a Linux box you reach over SSH to run websites, containers or databases. You configure it; you rarely look at it. An **RDP VPS** is the opposite: a graphical Windows session where you install software by double-clicking an installer, and where the machine keeps running your programs after you close the window. Same virtualization underneath, completely different working model.

Windows Server and the Pro/Enterprise editions of Windows are built to act as full RDP servers out of the box. Linux can serve RDP too, but only through third-party software such as xrdp, and you get a Linux desktop at the other end, not Windows. That distinction matters if the software you need is Windows-only.

A **dedicated server** is for the case where an entire physical machine has to belong to you — heavy sustained CPU, compliance requirements, or a workload that outgrows shared virtualization. Pricing starts an order of magnitude higher, and you inherit the hardware.

LisaHost's catalogue sits in the VPS half of that spectrum: KVM virtual machines on native-IP and residential-IP lines, with Windows installation listed as a supported option rather than a preconfigured Windows Server image with a licence baked in. That single sentence is the most important thing to understand before reading the plan table below.

## The five checks that decide whether a cheap plan is usable

### 1. Windows edition, and who owns the licence

This is where most first-time buyers lose money, and it has nothing to do with CPU.

Some providers sell RDP plans with a paid Windows Server licence inside the monthly price — VPS Shell, for example, states plainly that every plan carries a licence so the desktop "never runs on a trial and never asks you for a key" — and prices accordingly, from $14.40 a month. Others sell you a cheap virtual machine and leave you to bring your own key. HOSTKEY's instant Windows VPS tiers start at $1.43 a month, but that table doesn't state whether a Windows Server licence is included, and at that price you should assume it isn't.

Neither model is dishonest. The trap is comparing the two numbers as if they were the same product.

Then there's the edition question. Windows 10 is past Microsoft's end-of-support date (the cutoff was 14 October), which means no further security patches. Providers still sell Windows 10 images because a lot of business software was validated on it — accounting tools, internal applications, older utilities that were never tested on Windows 11 — but a brand-new desktop built on an unpatched OS is a decision, not a default. Windows Server images are the safer base for anything multi-user or internet-facing.

LisaHost's product pages list "Windows installation supported" as a feature on its KVM plans. They do not advertise a bundled Windows licence. On a ¥68 machine with 1 GB of RAM, there's no room in the price for one either. Assume you install your own image with your own key unless support tells you otherwise in writing.

### 2. How many people can be signed in at once

Windows client editions allow one interactive session. Windows Server allows two administrative sessions by default. Anything beyond that needs Remote Desktop Services licences and usually a bigger machine or a dedicated server — that's not a limitation invented by hosting companies, it's how Microsoft licenses the product.

So when a plan page says "full admin access", it tells you what you can do inside the session, not how many sessions you get. If two people need to work on the same box at the same time, ask explicitly, and expect the answer to involve either Windows Server or extra licensing.

### 3. Location, latency and whether the IP is yours

Location is decided by what the desktop talks to, not by where you sit. A trading terminal should live near the broker's servers. A desktop used for browsing and account work should live in the country whose IP you need the world to see.

A dedicated IPv4 per plan is the norm at this tier — VPS Shell includes one local IPv4 per city, Infrawire ships dedicated IPv4 and IPv6 on every tier, and LisaHost's plans each include one IPv4. Shared IPs on an RDP box are a red flag: you inherit whatever reputation the previous tenant left behind.

LisaHost's Singapore line is a BGP network with Singapore native IPs, and the vendor notes it is not optimized for direct routes from mainland China, suggesting Hong Kong or Japan transit instead. If your work is Southeast Asian e-commerce, streaming or regional accounts, that's fine. If you specifically need low latency from mainland China, this particular line isn't the one.

### 4. Refund window and payment rails

Compare, don't assume. Infrawire offers 7 days. VPS Shell and AnymHost both offer 30. LisaHost's plans carry a 48-hour unconditional refund if you're not satisfied — short, but enough to test whether Windows installs, whether RDP answers, and whether your software runs.

Payment is the other practical filter. VPS Shell takes Bitcoin, USDT and Litecoin only. Infrawire accepts cards, PayPal, Alipay and crypto. LisaHost's checkout is built around Chinese payment rails, so plan on Alipay or WeChat Pay rather than a foreign card form, and budget for the currency conversion since prices are quoted in CNY.

### 5. RAM, not CPU, is what breaks first

A Windows desktop idles at roughly 1 to 1.5 GB before you open anything. Add a browser and you're at 2.5 GB. Add a trading terminal with a few charts and you're past 3 GB.

That makes 1 GB plans technically Windows-capable and practically useless for daily work: the machine will swap, and RDP will feel like dial-up. 2 GB is the entry point for one person doing light work. 4 GB is where a desktop stops being fragile. CPU cores matter for compilers, backtests and video, not for keeping a session responsive.

## LisaHost's current plans, side by side

These are the plans published on LisaHost's Singapore native-IP line. All are KVM, all include one IPv4, all provision automatically after payment, and all carry the 48-hour refund.

| Plan | vCPU / RAM / NVMe | Bandwidth / Traffic | Windows | Price | Order |
| --- | --- | --- | --- | --- | --- |
| 基础版 (Basic) | 1 / 1 GB / 10 GB | 300 Mbps / 6,000 GB per month | Installation supported | ¥68 / month | [Order the 1 GB basic plan monthly](https://lisahost.com/cart.php?a=add&pid=70&aff=1587) |
| 进阶版 (Advanced) | 2 / 2 GB / 20 GB | 500 Mbps / 10,000 GB per month | Installation supported | ¥88 / month | [Order the 2-core advanced plan monthly](https://lisahost.com/cart.php?a=add&pid=71&aff=1587) |
| 豪华版 (Deluxe) | 4 / 4 GB / 40 GB | 1 Gbps / 20,000 GB per month | Installation supported | ¥388 / month | [Order the 4-core deluxe plan monthly](https://lisahost.com/cart.php?a=add&pid=72&aff=1587) |
| 不限流量 Lite | 2 / 2 GB / 40 GB | 200 Mbps / unmetered | Installation supported | ¥398 / month | [Order the unmetered Lite plan](https://lisahost.com/cart.php?a=add&pid=73&aff=1587) |
| 不限流量 Pro | 4 / 4 GB / 80 GB | 500 Mbps / unmetered | Installation supported | ¥898 / month | [Order the unmetered Pro plan](https://lisahost.com/cart.php?a=add&pid=74&aff=1587) |
| 特价年付版 (Annual) | 1 / 1 GB / 10 GB | 300 Mbps / 2,000 GB per month | Installation supported | ¥466 / year (about ¥39 / month) | [Take the annual plan at roughly ¥39 a month](https://lisahost.com/cart.php?a=add&pid=172&aff=1587) |

Two notes the table can't hold. First, the Lite and Pro unmetered plans trade compute for traffic: Lite costs more than the Deluxe plan while giving you half the cores and half the RAM, because "unmetered" is what you're buying. Second, the annual plan cuts the monthly rate by roughly 43% but also cuts the traffic allowance from 6,000 GB to 2,000 GB a month — fine for a desktop, wrong for anything that moves data continuously.

LisaHost also runs US lines on 9929 and 4837 routing with dual-ISP residential IPs, plus Hong Kong, Japan, Taiwan, Korea and UK lines. Specs and pricing differ by line, and the residential-IP lines are aimed at people who need a household-grade IP for account work rather than maximum CPU per yuan. 👉 [Browse LisaHost's regional native-IP and residential-IP lines](https://lisahost.com/aff.php?aff=1587)

## Which plan fits which job

**One person, one desktop, files that follow you.** A second computer in the cloud, reachable from a laptop, a tablet and a phone, with the same files and the same apps in the same places. The 2-core / 2 GB 进阶版 is the honest minimum; the 1 GB tier will boot Windows and then struggle the moment you open a browser with more than three tabs.

**A trading terminal or automation that must not stop.** MetaTrader, cTrader, NinjaTrader, browser bots, scheduled scripts — the whole point is that the machine stays up when your laptop sleeps. Go to the 4-core / 4 GB 豪华版 and keep the terminal plus one browser open; below 4 GB, chart-heavy platforms start paging during news windows. 👉 [Pick the 4-core deluxe plan for always-on terminals](https://lisahost.com/cart.php?a=add&pid=72&aff=1587)

**Legacy business software that only runs on Windows.** This is the one case where Windows 10 still makes sense, because the application was validated on it and never tested on anything newer. Understand what you're accepting: an OS past its support date, on a machine with a public IP. Keep it behind a firewall, don't browse on it, and treat it as an appliance.

**A small team sharing one machine.** Two administrative sessions on Windows Server is the ceiling before licensing gets involved, and two simultaneous users on 2 GB is unpleasant. If three or more people need in, you're shopping for a bigger plan and a conversation about RDS licences, not a cheaper one.

**You need a specific country's IP more than you need horsepower.** That's the residential-IP product line, not the Singapore BGP line. The trade-off is real: household-grade IPs cost more per core, and the CPU is modest. 👉 [Compare the residential-IP options by country](https://lisahost.com/aff.php?aff=1587)

## Where the extra money goes

Plan ladders are usually priced by feel rather than by arithmetic, so it's worth doing the arithmetic.

On LisaHost's Singapore line, moving from 基础版 to 进阶版 costs **¥20 more per month, about 29%**. For that you get double the cores, double the RAM, double the NVMe, bandwidth from 300 Mbps to 500 Mbps and traffic from 6,000 GB to 10,000 GB. There is no other step in the table that buys that much for that little. If you're unsure which plan you need, this is the one where guessing wrong costs least.

Moving from 进阶版 to 豪华版 costs **¥300 more per month** — a 4.4× jump — for double the cores, RAM, disk, bandwidth and traffic. Per unit of resource it's a worse deal than the first step, and it only makes sense once you've established that 2 GB is actually the bottleneck. Don't buy it preemptively.

The unmetered plans invert the logic. Lite gives you 2 cores, 2 GB and 40 GB of disk for ¥398, which is ¥10 more than the 4-core Deluxe plan. You are paying for the absence of a traffic cap and accepting less machine. If your monthly transfer sits comfortably under 10 TB, Deluxe is better value; if you're pushing continuous outbound traffic, Lite is the only one of the two that won't meter you.

The annual plan is the cheapest way onto the platform at roughly ¥39 a month against ¥68 monthly — a saving of about ¥350 over a year. The catch is 1 GB of RAM and a 2,000 GB monthly cap, so it's a good fit for a light single-purpose desktop and a bad fit for anything with a browser habit.

One caution that applies across the market, not just here: introductory discounts reset at renewal. Infrawire's five Windows tiers are discounted 20–50% off list, with the entry plan dropping from €16.60 to €8.30 — and renewing at the higher figure. AnymHost publishes original and discounted prices side by side on all six of its plans. Before you commit to a year, check what the second year costs.

## What these plans are not good for

**You want a licensed Windows Server desktop with no setup work.** LisaHost lists Windows installation as supported; it does not advertise a pre-licensed, preconfigured Windows Server image. If you want to pay and immediately RDP into a licensed desktop with patching handled for you, VPS Shell's $14.40 tier is built for exactly that, and the price difference is the licence.

**You need more than two people in at once.** That's a licensing problem, and no plan in this table solves it.

**You're hosting websites.** An RDP VPS is a desktop, not a web host. Take a Linux VPS for that and spend a third as much.

**You need a mainland-China-optimized route.** The Singapore line says outright that it isn't one; the vendor recommends Hong Kong or Japan transit. LisaHost's other lines address this, but check the specific line rather than the brand.

**You want a long safety net.** 48 hours is enough to install Windows, connect, and discover whether the machine is fast enough for your software. It is not enough to发现 a problem that appears in week three. Test hard in the first two days: install everything you need, run your heaviest workload, and check latency to whatever the desktop has to talk to.

**You can only pay by card.** Expect Alipay or WeChat Pay at checkout, prices in CNY, and a Chinese-language storefront.

## Ordering and connecting, step by step

1. **Pick the plan and the line.** Singapore native IP for regional presence and clean IPs; US residential lines for account-sensitive work; other regions if you need the IP to be somewhere specific.
2. **Confirm the Windows question before paying.** Ask support whether Windows installation is supported on the plan you chose, which images are available, and whether you supply the licence. Get it in writing — it's the one detail that changes the total cost.
3. **Pay and wait for provisioning.** LisaHost's cart provisions automatically, so the machine appears quickly; installing Windows from an ISO afterwards is your time, not theirs.
4. **Collect the IP and credentials** from the client area once the OS is up.
5. **Connect.** On Windows, run `mstsc`, paste the IP, enter the username and password. On macOS, iOS or Android, use Microsoft's Windows App. On Linux, Remmina or FreeRDP. Save the connection file so reconnecting is one double-click.
6. **Test before the refund window closes.** Reboot from the panel, confirm the desktop comes back, run your actual software, and measure latency to the services it depends on.

## FAQ

**Can I install any software?** On a machine where you hold the administrator account, yes — anything compatible with the Windows edition you installed. That's the difference between an admin RDP box and a shared RDP account, where you can't install anything.

**How long until it's ready?** Provisioning is automatic and immediate. The Windows installation itself is the variable; a clean install plus drivers and updates is a half-hour job, not a two-minute one.

**Can I upgrade later without reinstalling?** Ask before you buy. Some providers migrate a live desktop to a larger plan with files intact; others require a rebuild. The plan ladder existing doesn't guarantee in-place upgrades.

**What happens if RDP stops answering?** You need an out-of-band way in — a VNC or HTML5 console in the control panel, or a reinstall option. Confirm the panel has one before you rely on the box for anything important, because a firewall rule you wrote yourself can lock you out of RDP permanently.

**Is a 1 GB plan enough for Windows?** It will install and it will connect. It will not be pleasant. Buy it as a lightweight appliance, or for the annual saving, not as your daily desktop.

**How does this compare with a dedicated RDP provider?** You trade a bundled licence and hand-holding for a lower price and full control of the OS. If you already own Windows licences and know your way around an installer, that trade is worth making. If you don't, pay the $14-or-so premium elsewhere and save yourself the afternoon.

## The short version

Buy the 进阶版 if you want one usable Windows desktop for one person — ¥88 a month, 2 cores, 2 GB, and the cheapest sensible step in the whole table. Buy the 豪华版 only after you've proved 2 GB isn't enough. Buy the annual plan if the workload is light and predictable. And whatever you choose, settle the licensing question with sales first, because that's the line item that turns a cheap plan into an expensive surprise. 👉 [Start with the ¥88 two-core plan and test it inside the 48-hour refund window](https://lisahost.com/cart.php?a=add&pid=71&aff=1587)
