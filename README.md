# Cheap Bare Metal Hosting: Is €4.99/Month Enough, Why Do $99.99 Renewals Show Up, and What Else Lands on the Bill? (Verified Specs, 10Gbps Transfer Terms and Add-On Costs)

Cheap bare metal hosting spans two very different price bands. At the bottom, Scaleway's Dedibox line starts at €4.99/month for an entry dedicated server, and its cloud-integrated Elastic Metal line starts at €27.99/month or €0.077/hour. At the commercial end, the cheapest renewal price on InMotion Hosting's live-inventory page is $99.99/month. The gap buys cores, RAM generation, NVMe instead of SATA, port speed, bundled transfer, IP addresses and how fast the machine appears after you pay.

This article breaks down those variables, lists the configurations SpinServers publishes for Dallas and San Jose, and covers the charges that sit outside the sticker price: metered outbound bandwidth, extra IPv4 addresses, Windows licensing, and backup or DDoS add-ons.

> **Quick pick.** If you want a US machine with a 10Gbps port and 30TB of monthly transfer that provisions without a sales call, start with SpinServers' Dallas or San Jose listings. If your budget is under €30/month and France or the Netherlands works for your users, Scaleway is cheaper. If the purchase has to satisfy HIPAA, PCI DSS or SOC 2, price Atlantic.Net first.
> 👉 [See the current SpinServers Dallas and San Jose configurations](https://bit.ly/Spinservers)

## What SpinServers actually lists

There are no named tiers to compare. SpinServers lists individual machines, each with its own CPU, memory, storage, port speed and monthly transfer, and the mix changes as stock rotates. That is normal for a host that trades in its own hardware, and it changes how you shop: you compare boxes, not plans.

| CPU | Cores / threads | RAM | Storage | Network | Order |
| --- | --- | --- | --- | --- | --- |
| Intel Xeon E3-1280 v5 (Dallas) | 4C / 8T, 3.7GHz turbo | 32GB DDR4 ECC | 1TB M.2 NVMe | 30TB on 10Gbps | [ Check price](https://bit.ly/Spinservers) |
| Dual Intel Xeon E5-2630L v3 (Dallas) | 16C / 32T, 2.9GHz | 128GB DDR4 ECC | 1TB NVMe | 30TB on 10Gbps | [ Check price](https://bit.ly/Spinservers) |
| Xeon-class, 3.7–4.0GHz (San Jose) | 4C / 8T | 32GB DDR4 ECC | 1TB M.2 NVMe | 30TB on 2×10Gbps | [ Check price](https://bit.ly/Spinservers) |
| 2.6–3.1GHz (San Jose) | 12C / 24T | 64GB DDR3 ECC | 240GB SSD | 30TB on 2×10Gbps | [ Check price](https://bit.ly/Spinservers) |
| 1.8–2.9GHz (San Jose) | 16C / 32T | 64GB DDR4 ECC | 1.6TB SSD | 30TB on 2×10Gbps | [ Check price](https://bit.ly/Spinservers) |
| 1.8–2.9GHz (San Jose) | 16C / 32T | 256GB DDR4 ECC | 2×1.6TB SSD, hardware RAID | 30TB on 2×10Gbps | [ Check price](https://bit.ly/Spinservers) |
| 2.1–3.0GHz (San Jose) | 32C / 64T | 512GB DDR4 ECC | 2×3.84TB SSD, RAID with battery-backed cache | 30TB on 2×10Gbps | [ Check price](https://bit.ly/Spinservers) |

Two details in that list matter more than the core counts. The 12-core San Jose machine uses DDR3 ECC memory while every other box on the page is DDR4, which is part of why a 12-core server can price under a 16-core one. And storage is split across SATA SSDs, M.2 NVMe and hardware RAID arrays with battery-backed cache, so "SSD" on a quote can mean three different things once you put a database on it. The San Jose machines advertise two 10Gbps ports rather than one, which is what you want if you plan to separate public traffic from replication or a private link between servers.

Pricing is where I have to stop and hand you the order page. These listings carry specs and deployment terms, not a published per-plan price I could verify, and inventory-driven hosts re-quote as stock moves. Where the listing states an IP count, it is a single IPv4 per server. Every Dallas and San Jose machine shown above is marked as auto-provisioning, so the "ready to go" stock deploys without a human, while custom memory or storage builds take longer.

A third-party review of SpinServers lists SOC 2, HIPAA and PCI compliance along with a 99.999% uptime SLA. Both are claims, not terms printed on the order page, so get them in writing if you are putting a regulated workload on the hardware.

## The bill after the bill

A cheap bare metal quote covers hardware. Three other buckets decide your actual monthly number, and one budget host's own documentation says it outright: firewall and backup are paid add-ons, and operating system or bundled commercial software can carry licence fees on top of the server rent. Hardware, software licensing and backup/security are three separate line items, and only the first one appears in the headline price.

**Outbound transfer.** SpinServers bundles 30TB per month. HorizonIQ bundles 10TB outbound with all inbound traffic free, and bills anything above the contracted amount by actual usage, with extra bandwidth purchasable. Those numbers are easy to misread next to a 10Gbps port. A 10Gbps link running flat for a month moves roughly 3.2PB. Ten terabytes spread evenly across a month averages around 31Mbps. So the port is a burst ceiling, and the transfer quota is your real throughput budget. If your workload is video, a CDN origin, off-site backups or bulk data movement, 10TB is a few days of work, and the per-GB overage rate decides whether the server is cheap or expensive. Ask for that rate before you sign.

**IPv4 addresses.** HorizonIQ includes one public IPv4 with each server and sells more, with IPv6 available in only some locations. InMotion Hosting bundles 16 to 64 dedicated IPs depending on the configuration. If you host mail, terminate SSL for dozens of domains or run VPN endpoints, IP count is a real cost line and not a rounding error.

**Windows licensing.** HorizonIQ offers Windows Server 2022 Standard and Datacenter on standard orders. At budget hosts, OS and preinstalled commercial software such as databases, CMS platforms or ERP suites may be billed separately, and one provider points to Windows Server Evaluation Edition as a free option for up to 180 days. Linux distributions avoid this entirely, which is one reason the cheap end of the market is overwhelmingly Linux.

**Backup and DDoS.** One low-cost provider states its automated backups for VPS run once every 2 or 4 weeks. Assume nothing about daily snapshots at this price tier, and price backup as a separate service. Atlantic.Net sells DDoS protection as an optional paid service. If someone else's attack can take your box offline, that line item belongs in the budget.

**Renewal and term.** InMotion's bare metal page shows only "Renews at" prices, running from $99.99 to $1,919.99 per month across its listed configurations, with 1-month, 1-year and 2-year billing toggles. The intro invoice and the third-year invoice are frequently different numbers, so compare renewal prices, not first invoices. Atlantic.Net takes the other approach and discounts 1, 2 and 3-year contracts, which means monthly billing is the most expensive way to rent the same hardware.

## Which price band matches your workload

| Budget band | Verified example | Fits | The catch |
| --- | --- | --- | --- |
| Under €10/month | Scaleway Dedibox, from €4.99/month, almost 100 configurations across Start, Pro, Core, Store & GPU lines, data centers in France and the Netherlands | A single site, VPN, small database, lab machine | Entry dedicated tier, not the cloud-integrated product line |
| Around €28/month or hourly | Scaleway Elastic Metal, from €27.99/month or €0.077/hour, five product lines | Workloads that need to sit beside cloud primitives such as load balancers, private networks and object storage | You pay for the ecosystem as well as the box |
| Around $100/month renewing | InMotion Hosting, renewal prices from $99.99/month, live inventory, 1–10Gbps uplinks, 16–64 IPs, US and EU data centers | Teams that want to pick an exact CPU, core count, RAM and disk, then run their own stack | Unmanaged: the OS, patches and applications are yours |
| Bandwidth-heavy | SpinServers 30TB on 10Gbps per listing; HorizonIQ 10TB outbound included, inbound free, 10Gbps, 19 ready-to-deploy configurations plus 50 CPU options to order | Streaming, game servers, CDN origins, bulk transfer | Overage is metered; confirm the per-GB rate and the IP count |
| Regulated workloads | Atlantic.Net, SOC 2 Type II, HIPAA and PCI DSS, US data centers in New York, San Francisco, Dallas, Ashburn and Orlando | HIPAA or PCI scope, ERP and CRM platforms, large databases | DDoS protection is a paid option, and the contract discounts require 1–3 year terms |

Scaleway's Dedibox is the honest floor of the market: a real single-tenant machine at a price that undercuts most VPS plans with comparable RAM, in two French and Dutch availability zones. What you give up is proximity to US users and the cloud tooling. Elastic Metal fixes the second problem by putting the same physical hardware inside a public cloud account, which is why it costs roughly five times the entry Dedibox price while still being cheaper than most managed dedicated offers.

HorizonIQ publishes no prices at all, which makes it hard to rank against the others. What it does publish is useful for comparison: three tiers from 4-core Xeon E3 machines with 32GB of RAM up to dual-socket Xeon Gold and AMD EPYC configurations with 36 cores and 192GB, 10Gbps public bandwidth on the top two tiers, a 100% uptime SLA in the company's own wording, and compliance coverage for HIPAA, SOC 2, ISO 27001 and PCI DSS. Its standard 2×480GB SSD mirror is smaller than what SpinServers lists, and NVMe up to 12TB per drive is a custom order rather than a stock configuration.

## When bare metal is the wrong purchase

Three situations where a dedicated box is the expensive answer.

**Your load has real peaks and troughs.** Scaleway names inconsistent workloads, seasonal peaks and drops as the case for its flexible products rather than a fixed monthly server. A machine that sits at 15% utilisation for eight months a year is not cheap at any price. Hourly billing on something like Elastic Metal, or ordinary cloud instances, absorbs seasonality better.

**You need a custom build today.** Instant provisioning depends on stock and configuration. Atlantic.Net notes that instant deployment is not universal and that a dedicated cloud server can be the faster route when you need capacity immediately. On SpinServers, the auto-provisioning labels cover listed configurations. A custom memory, storage or GPU build is a different timeline, so ask before you promise a launch date.

**Nobody on your team wants root.** Bare metal hosts manage the data center, the network and the hardware. InMotion states plainly that its managed offering stops there, and that the operating system and applications stay under customer control. Paid consulting and IT support exist, but the default is that you own patching, hardening, monitoring and backups. A team without a sysadmin should price a managed service into the comparison before choosing raw hardware.

## FAQ

**Does cheap bare metal include NVMe?**
Often, but not always. Atlantic.Net notes that NVMe is usually standard on bare metal and still depends on the provider. SpinServers lists M.2 NVMe on several Dallas and San Jose machines alongside SATA SSD and RAID arrays. HorizonIQ ships 2×480GB SSD as standard and offers NVMe up to 12TB per drive on custom configurations. Check the storage type per machine, not per brand.

**Can I get the server within the hour?**
On in-stock configurations, yes. SpinServers marks its Dallas and San Jose listings as auto-provisioning, and HorizonIQ keeps 19 ready-to-deploy configurations in its online store. Custom builds and anything requiring different RAM, drives or GPUs go to a queue.

**Do I need to buy a Windows licence separately?**
Usually yes. HorizonIQ sells Windows Server 2022 Standard and Datacenter as an OS option, and budget providers note that operating system and preinstalled commercial software may carry licence fees. One provider offers Windows Server Evaluation Edition free for up to 180 days. If your stack runs on Linux, this line disappears.

**Are backups and DDoS protection in the price?**
Rarely. One low-cost host lists firewall and backup as optional paid add-ons and runs VPS backups as infrequently as once every two to four weeks. Atlantic.Net sells DDoS protection as a paid service. Budget for both as separate items.

**Is the advertised price the renewal price?**
Not always. InMotion's page displays only renewal prices, from $99.99 to $1,919.99 per month, which tells you what the machine costs after any promotional period but not what the first invoice looks like. Atlantic.Net's 1, 2 and 3-year contract discounts mean the monthly rate depends heavily on the term you commit to.

**How much transfer do I actually get?**
SpinServers bundles 30TB per month on 10Gbps ports across the listings above. HorizonIQ bundles 10TB outbound with inbound free. Above those limits you pay per GB at a rate that is usually quoted on request, so it belongs in your cost model before you choose.

## Picking one

Under €10/month with one machine to run: Scaleway's Dedibox line, in France or the Netherlands. You want the hardware inside a cloud account and billed by the hour: Elastic Metal. You want to choose an exact US or EU machine from live inventory and manage the stack yourself: InMotion Hosting's renewal prices start at $99.99/month. Your workload is transfer-heavy and a 10Gbps port with 30TB bundled is the requirement: the SpinServers Dallas and San Jose machines. HIPAA or PCI scope is on the purchase order: Atlantic.Net.

Before you pay anywhere, get four numbers in writing: the renewal price and minimum term, the included outbound allowance plus the per-GB overage rate, the IPv4 count and the cost of extras, and whether backup, firewall and DDoS protection are included or add-ons. On a $50–$100 server, the second and fourth items regularly move the real monthly cost by more than the difference between two competing quotes.

If a US box with a 10Gbps port and 30TB of transfer is what you're after, the current machine list is the place to start.
👉 [Compare the Dallas and San Jose bare metal machines](https://bit.ly/Spinservers)
