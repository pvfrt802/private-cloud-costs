# private cloud: What It Really Costs, Who Actually Needs One, and How to Get One Without Hyperscaler-Style Billing Surprises

A private cloud is a cloud environment reserved for a single organization — your compute, storage, and networking are isolated from everyone else's, whether they sit in your own server room or in a provider's data center. That's the definition every major source agrees on. What most search results don't tell you is the part that actually matters when you're budgeting: what a private cloud costs in practice, what hidden fees lurk in "cloud pricing," and when a simpler plan will do the job.

Sharktech is an interesting case study here. The company (founded 2003, Las Vegas-based, 1,000+ business customers) sells three related things: a fully custom **Private Cloud** built on dedicated hardware in SOC 2 data centers (priced by quote), a **Dedicated Cloud** with fixed monthly resource allocations, and a standard **Public Cloud** on OpenStack with plans from **$39 to $499 per month** — all with 60 Gbps DDoS protection baked in. For most people searching "private cloud," one of these three fits, and the cheapest one is probably more capable than you'd expect.

> **Quick pick:** If your goal is dedicated resources, full control, and no surprise bills, Sharktech's Public Cloud Small plan ($39/month, 4 vCPU / 8 GB RAM / 300 GB SSD / 20 TB outbound traffic) covers most small business workloads. If you need hardware that's physically exclusive to your organization — compliance, HIPAA-style requirements, or ML training clusters — that's the custom Private Cloud route, quoted as a flat monthly fee. 👉 Check Sharktech's cloud plans and current pricing

## What is a private cloud, in plain terms?

A private cloud is cloud infrastructure dedicated to one organization, with resources provisioned on demand through a self-service portal — just like public cloud, but isolated. IBM, AWS, Google Cloud, and Cloudflare all converge on this definition. The isolation part is what's called "isolated access": underlying resources like CPU and storage are yours alone.

Two things trip people up:

**First, a private cloud doesn't have to be on-premises.** It traditionally ran in your own data center, but it can just as easily run on rented infrastructure from a provider — AWS describes building one inside a VPC, where virtualized servers and networks are dedicated to a single organization. Sharktech's version is the second kind: exclusive hardware in their enterprise SOC 2 data centers, without you racking any servers yourself.

**Second, "private cloud" and "dedicated cloud" are different products at Sharktech.** The company itself draws this line on its own site: Dedicated Cloud is a billing model (fixed resource allocation, fixed price, no hourly overages), while Private Cloud means exclusive physical infrastructure built for a single organization. Confusing the two leads to quotes for the wrong thing.

## Sharktech's cloud plans: the full picture

Here are the plans currently shown on Sharktech's official cloud pricing calculator, plus the custom Private Cloud. All prices are USD, monthly.

| Plan | Core resources | Price | Billing | Order |
| --- | --- | --- | --- | --- |
| Public Cloud Small | 4 vCPU / 8 GB RAM / 300 GB SSD / 20 TB outbound | **$39.00/mo** | Base + metered overage | [ Deploy Small](https://portal.sharktech.net/cart.php?a=add&pid=602&carttpl=public_cloud_cart&configoption%5B1677%5D=11563&language=english&aff=1626) |
| Public Cloud Medium | 8 vCPU / 16 GB RAM / 800 GB SSD / 20 TB outbound | **$79.00/mo** | Base + metered overage | [ Deploy Medium](https://portal.sharktech.net/cart.php?a=add&pid=603&carttpl=public_cloud_cart&configoption%5B1677%5D=11563&language=english&aff=1626) |
| Public Cloud Large | 32 vCPU / 64 GB RAM / 1,500 GB SSD / 20 TB outbound | **$249.00/mo** | Base + metered overage | [ Deploy Large](https://portal.sharktech.net/cart.php?a=add&pid=604&carttpl=public_cloud_cart&configoption%5B1677%5D=11563&language=english&aff=1626) |
| Public Cloud Enterprise | 64 vCPU / 128 GB RAM / 5,000 GB SSD / 20 TB outbound | **$499.00/mo** | Base + metered overage, no preset resource ceiling | [ Deploy Enterprise](https://portal.sharktech.net/cart.php?a=add&pid=605&carttpl=public_cloud_cart&configoption%5B1677%5D=11563&language=english&aff=1626) |
| Private Cloud | Fully custom: exclusive compute, storage, network in a SOC 2 data center | Flat monthly quote | Custom quote after design | [ Request a private cloud design](https://bit.ly/SharKtech) |

The final column links to each plan's official cart page. One caveat that applies to every plan in the table: Sharktech itself states that "VM details are an estimate and must be configured after ordering," so treat the resource splits as accurate ballpark and confirm the exact allocation in the portal at checkout.

A detail worth pausing on, because it only shows up in the fine print: Small, Medium, and Large plans have **resource ceilings** — upper limits on how much you can burst above your included allocation. Enterprise has none. And Sharktech is explicit that "resource ceilings are not monetary spending caps." In other words, the ceiling stops your VMs, not your invoice.

## The middle ground most articles skip: Fixed-Price Public Cloud

If neither "metered with a base fee" nor "fully custom build" sounds right, Sharktech runs a third billing option on the same OpenStack platform and the same data centers: **Fixed-Price Public Cloud**, where you prepay for a specific allocation with no bursting at all. Listed tiers start around **$86.23/month** for 8 vCPU / 16 GB / 500 GB SSD, with an S tier at **$140.95/month** (16 vCPU / 32 GB) scaling up to an XL at **$907.03/month** (128 vCPU / 256 GB).

This is the option for a specific personality: you know exactly what your workload consumes, you'd rather eat the over-provisioning than ever see a variable line item, and you don't need exclusive physical hardware. If your usage swings month to month, the standard Public Cloud plans will be cheaper, since unused fixed allocation is money spent for nothing.

## What Sharktech's custom Private Cloud actually includes

The custom Private Cloud is a design-and-build service, and the scope is broader than most people expect from a hosting company. Sharktech builds the environment from the ground up in an enterprise SOC 2 data center: compute, storage, and network architecture specified for your workloads, security requirements, and growth plans.

The pieces you can define:

- **Hardware**: exclusive compute, storage (HDD, SSD, or NVMe), and network capacity, with redundancy strategies of your choosing
- **Orchestration**: Sharktech's Virtuozzo OpenStack platform for managing VMs, storage, networks, security groups, and load balancers — or bring your own compatible platform, with responsibilities sorted out during the design phase
- **Compliance planning**: the environment can be planned around HIPAA requirements, including security controls, access policies, and operational requirements, with the compliance scope and responsibility split agreed with Sharktech's team upfront. Note the careful wording — this is planning *around* HIPAA requirements, not a claim of certification
- **Machine learning infrastructure**: Sharktech sources power capacity and builds out GPU/CPU platforms, memory, local NVMe storage, and high-speed interconnects for training, fine-tuning, and inference, including rack density and cooling planning

Protection is layered four ways: facility (SOC 2 building, physical access controls, redundant power and cooling), network (DDoS mitigation, network segmentation, firewall policies), infrastructure (dedicated compute and storage with redundancy and recovery plans), and operations (access controls, monitoring, support responsibilities, compliance requirements). That last layer matters for regulated industries — it's the part auditors ask about.

The process runs in four steps: Discover (you provide workload profiles, compliance needs, availability targets, growth forecasts), Design (compute, storage tiers, redundancy, network capacity, security controls get specified), Build (deployment and platform configuration), then Operate & grow.

Pricing is the simplest part to describe and the hardest to pin down: **a flat monthly price based on the agreed hardware, platform, and service scope**. No public price list, because no two builds are the same. If you want a number before talking to sales, the closest reference points are Sharktech's own bare-metal servers: an entry dual-core Xeon machine with 16 GB RAM runs **$99/month** on promotion (regularly $159), mid-range dual-Xeon 72-core builds with 10 Gbps unmetered bandwidth run around $209/month, and 128-core EPYC configurations around $399/month. A private cloud starts in that neighborhood and scales with what you spec — and it includes things bare metal doesn't, like the design work, the orchestration platform, and the operational layer.

## The real cost math: where private cloud pricing actually bites

The sticker price is the smallest part of cloud costs. The part that wrecks budgets is egress — charging you for data leaving the cloud.

Hyperscalers typically charge somewhere between $0.05 and $0.12 per GB of outbound traffic. Run a workload pushing 10 TB per month and you're looking at roughly **$900/month in egress fees alone** at $0.09/GB — before paying for the actual servers. Sharktech's cloud plans flip this: **20 TB of outbound traffic is included** in every plan, inbound is unmetered, and overage runs $0.002/GB. That same 10 TB workload costs $0 within the included pool, or about $20 if you somehow exceeded it. The company claims 50–80% savings versus hyperscalers overall, with a floor guarantee of at least 40%.

The other cost traps to know about before ordering:

- **Storage bills even when VMs are stopped.** Sharktech's calculator estimates storage over a 730-hour month regardless of whether the VM is running. Deleted data stops billing; paused VMs with attached disks don't.
- **Overage rates are granular and published**: CPU $0.0025/hr per core, RAM $0.0035/hr per GB, NVMe $0.00009/hr per GB, SSD $0.00006/hr per GB, HDD $0.00002/hr per GB, extra public IPv4 $1.50/month each (the first one is free with every plan). Enterprise tiers run slightly lower rates on several of these.
- **Resources pool across VMs.** You're billed for the plan's aggregate allocation, not per named VM — so one month you can run a single big VM and the next month split the same pool across six small ones, at no extra cost.

If elastic-but-capped costs are the goal, start small and burst when you need to: 👉 Deploy the Small cloud plan at $39/month and scale only when usage demands it

## Public Cloud vs Dedicated Cloud vs Private Cloud: which billing model fits?

Sharktech runs all three on the same OpenStack infrastructure across five data center locations (Los Angeles, Las Vegas, Denver, Chicago, Amsterdam). The differences are about billing and exclusivity:

- **Public Cloud** — monthly base fee covering an included resource allocation, plus metered rates above it. Best for workloads with changing resource demand.
- **Dedicated Cloud** — you prepay for a fixed allocation at a fixed price. No hourly bursting, no automatic overages; upgrades go through the billing platform. Best for steady workloads and predictable budgets.
- **Private Cloud** — exclusive physical infrastructure, custom-designed, flat monthly quote. Best for compliance-driven or high-density workloads where shared hardware of any kind is off the table.

Everything runs on OpenStack, which matters more than it sounds: you can upload your own qcow2 or ISO images, and download your disk images at any time for offsite backups or migration. There's no proprietary API holding your data hostage — a real difference from the lock-in complaints that follow the big three clouds. The platform also covers the features most teams actually need day to day: private networks, routers, floating IPs, security groups, firewalls, and load balancers, all manageable through a simplified portal or the standard OpenStack REST API (API access is restricted to approved source IPs by default).

One practical tip before committing to a location: Sharktech operates a Looking Glass for all five sites, so you can check latency and routing from your own network before ordering. For reference, their Los Angeles site sits around 140–180ms from China Telecom over direct China Telecom/China Mobile peering — solid, though not a premium optimized route.

## Who should not buy a private cloud

Honest answer time, because this is where most content stops short.

If you're running a blog, a small site, or a dev environment, a private cloud is overkill by definition. AWS's own comparison material notes that private cloud deployments "require complex technologies and significant IT expertise" — you're taking on architecture decisions that a managed public plan handles for you. For that kind of workload, Sharktech's Public Cloud plans (or competitors like Vultr and DigitalOcean, which price lower but offer far weaker DDoS protection) are the sensible tier.

There's one policy to know before you order anything from Sharktech: **third-party reviews state that the company does not offer refunds**, in any scenario. The standard advice from those reviews is to start with the cheapest plan, validate that the network and support work for you, and only then scale up. Trustpilot sits at 4.0/5 — the positive side highlights effective protection, network stability, and responsive support; the criticisms center on pricing that isn't cheap, the no-refund policy, and an aging user interface.

## The DDoS protection question (and why it's included, not upsold)

Every Sharktech cloud product includes 60 Gbps of DDoS mitigation per IP — per IP, not shared across the fleet — with upgrades available up to 100 Gbps, 500 Gbps, and 1 Tbps. The filtering is always-on, covering network, transport, and application layers, and the company says its network was designed around DDoS protection from the start rather than bolting it on afterward.

This is the single biggest differentiator against cheaper clouds. Budget VPS providers will happily null-route your IP during an attack and call it protection; Sharktech's model is built for workloads that attract attacks — game servers, VoIP, fintech, high-traffic sites. Gaming clients cited in third-party reviews report facing 3–8 Gbps attacks regularly with zero downtime on Sharktech.

For context on quality beyond the security story: HostAdvice's review measured 6,000+ random IOPS and sub-millisecond network latency, concluding that "Sharktech delivers genuine power." And if you're migrating from AWS or Azure, one IT manager's public review of Sharktech's Dedicated Cloud praised the pricing as "shockingly reasonable" and the support team's speed as the standout difference. On migration itself, Sharktech acknowledges there's a cost/speed tradeoff: some clients accept an overnight maintenance window, while others pay a premium for live migration with zero downtime — worth raising during your first support conversation rather than discovering it mid-move.

## Common questions

**Can I leave if I don't like it?** Yes — that's the point of the OpenStack base. Upload custom images, download your disks anytime, migrate out. What you can't do is get a refund after paying, so size your first order conservatively.

**How do I pay?** Alipay, PayPal, credit cards, and cryptocurrency. The Alipay support is unusual for a US-based infrastructure provider and handy if you're billing from China.

**What's the uptime guarantee?** Sharktech advertises 99.999% uptime on its cloud platform, with infrastructure engineers on 24/7/365 support including phone. You can also test latency and routes to all five locations through the Looking Glass before ordering.

**Is the API locked down?** API access is IP-restricted by default (compute, network, block/object storage, identity via standard OpenStack REST APIs) — a security measure, though you'll need to whitelist your source IPs before automating anything.

**Do I have to use Sharktech's control panel?** No. A simplified portal handles most tasks without touching OpenStack's native complexity, but full OpenStack API access is there if your team wants infrastructure-as-code from day one.

## The bottom line, by situation

Running steady production workloads and want a bill you can predict to the dollar? Dedicated Cloud's fixed allocations remove bursting surprises entirely — and if your allocation needs fall between the standard tiers, the Fixed-Price line fills the gaps from roughly $86 to $907/month. Need elastic resources with the exit door always open? Public Cloud at $39–$499/month with 20 TB included traffic is the value play — the egress math alone justifies it if you move real data. Handling compliance requirements, sensitive data, or GPU-heavy ML builds? That's the custom Private Cloud conversation, and it starts with a workload profile rather than a credit card.

Two things to verify before you click buy: confirm your final resource allocation in the portal (the listed splits are estimates until configured), and remember there's no refund window — so it's worth starting small. 👉 Compare Sharktech's cloud plans and lock in your starting configuration
