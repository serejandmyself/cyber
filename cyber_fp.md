# cyber: Pag-compute ng kaalaman ng Great Web

<p align="center">
  <img src="images/graph.png" />
</p>

## Abstract

Ang consensus ng computer ay pinapayagang mag-compute ng mga may kaugnayan na mga sagot nang walang mga kuro-kuro na mga tagapamagitan ng blackbox, tulad ng Google, Amazon o Facebook. Ang mga walang saysay, content-addressable peer-to-peer communication networks, tulad ng IPFS, at mga stateful consensus computer tulad ng Ethereum, ay maaaring magbigay ng bahagi lamang ng solusyon na kinakailangan upang makakuha ng mga parehong sagot. Gayunpaman, mayroong hindi bababa sa 3 mga problema na nauugnay sa nabanggit na mga pagpapatupad. (A) ang subjective na katangian ng kaugnayan. (B) kahirapan sa scaling consensus computer para sa over-sized knowledge graphs. (C) ang kakulangan ng kalidad sa mga tulad ng mga knowledge graphs. Sila ay madaling kapitan ng iba't ibang mga surface attacks, tulad ng sybil attacks, at ang makasariling pag-uugali ng mga nakikipag-ugnay na ahente. Sa dokumentong ito, tinukoy namin ang isang protocol para sa mapagkakatiwalaan na pagsasama ng computing na may kaugnayan, sa pagitan ng mga IPFS objects, na batay sa Tendermint na pinagkasunduan ng cyber~Rank, na kinakalkula gamit ang mga GPU sa pag sang-ayon. Bilang patunay na pagsang-ayon ng patakaran ay hindi makakatulong sa paunang pamamahagi, binabalangkas namin ang disenyo para sa mga laro ng ekolohiya at mahusay na pamamahagi. Naniniwala kami na ang isang minimalistic na arkitektura ng protocol ay kritikal para sa pagbuo ng isang network ng domain-specific knowledge consensus computers. Bilang isang resulta ng aming trabaho, ang ilang mga aplikasyon na hindi pa naganap nuon, ay lalabas na. Pinalawak namin ang dokumentong ito sa aming pangitain ng mga posibleng tampok at potensyal na aplikasyon.

## Ang Dakilang Web

Ang mga orihinal na protocol ng Internet, tulad ng: TCP / IP, DNS, URL at HTTP/S ay nagdala ng web sa isang stale point, kung saan ito matatagpuan hanggang ngayon. Isinasaalang-alang ang lahat ng mga benepisyo na ginawa ng mga protocol na ito para sa paunang pag-unlad ng web, kasama ang mga ito, nagdala sila ng mga makabuluhang obstacles sa talahanayan. Globality, ang pagiging isang vital property ng web ay nasa ilalim ng isang tunay na banta mula nang ito ay umpisahan. Ang bilis ng koneksyon ay nagpapanatili ng panghinaaalsa habang ang network mismo ay patuloy na lumalaki dahil sa maraming mga interbensyon ng gobyerno. Ang huli ay nagdudulot ng mga alalahanin sa privacy bilang isang umiiral na banta sa mga karapatang pantao.

Ang isang pag-aari na hindi maliwanag sa simula ay nagiging mahalaga sa pang-araw-araw na paggamit ng Internet: ang kakayahang makipagpalitan ng permanenteng mga link, sa gayon, [hindi sila masisira matapos ang oras na lumipas](https://ipfs.io/ipfs/QmNhaUrhM7KcWzFYdBeyskoNyihrpHvUEBQnaddwPZigcN). Ang pag-asa sa arkitektura nang paisa-isa ay pinapayagan ng ISP ang mga pamahalaan na epektibong magsumite ng mga packet. Ito ang huling pagbagsak sa tradisyonal na web-stack para sa bawat engineer na nababahala tungkol sa hinaharap.

Ang iba pang mga pag-aari, kahit na hindi gaanong kritikal, ay talagang kanais-nais: offline at real-time connection. Ang average Internet user, habang offline, ay dapat pa ring magkaroon ng kakayahang magpatuloy sa pagtatrabaho sa estado na hawak na nila. Matapos makuha ang isang koneksyon dapat silang mag-sync sa global state at magpatuloy upang mapatunayan ang pagiging totoo ng kanilang sariling estado real-time. Sa kasalukuyan, ang mga pag-aari na ito ay inaalok sa antas ng aplikasyon. Naniniwala kami na ang mga pag-aari na ito ay dapat isama sa mga mas mababang antas ng mga protocol.

Ang paglitaw ng [isang brand-new web-stack](https://ipfs.io/ipfs/Qmf2rKkDPSsvdudwSmdDPbZuYae8XRV26c1wAFCCvg8Dhw) ay lumilikha ng isang pagkakataon para sa isang mahusay na Internet. Tinatawag ito ng web3 ng mga pamayanan. Tinatawag namin itong the Great Web. Naniniwala kami na ang iba't ibang uri ng mga komunikasyon sa mababang antas ay dapat na hindi mabago at hindi dapat baguhin sa loob ng mga dekada, hal. hindi mababago ang mga link sa nilalaman. Tila nangangako sila sa pag-alis ng mga problemang conventional protocol stack. Nagdaragdag sila ng higit na bilis at nagbibigay ng mas madaling ma-access na koneksyon sa bagong web. Gayunpaman, tulad ng nangyari sa anumang konsepto na nag-aalok ng something unique- lumitaw ang mga bagong problema. Ang isa sa gayong pagkabahala ay ang general-purpose search. Ang existing na general-purpose search engines ay mahigpit at sentralisadong database na ang lahat ay napipilitang magtiwala. Ang mga search engine ay partikular na idinisenyo para sa mga arkitektura ng client-server, batay sa TCP / IP, DNS, URL at HTTP/S. Ang Great Web ay lumilikha ng isang hamon at isang pagkakataon para sa isang search engine na batay sa mga umuusbong na teknolohiya at partikular na idinisenyo para sa mga layuning ito. Ito'y kahanga-hanga, ang walang pahintulot na arkitektura ng blockchain ay nagbibigay-daan sa pagbuo ng general-purpose search engine sa isang paraan na hindi naa-access sa mga nakaraang arkitektura.


## Sa mga Halimbawa ng mga problema ng kalaban

[Ang kasalukuyang arkitektura ng mga search engine](https://ipfs.io/ipfs/QmeS4LjoL1iMNRGuyYSx78RAtubTT2bioSGnsvoaupcHR6) ay isang sistema kung saan ang ilang mga entity ay nagpoproseso ng maling pamamaraan. Ang pamamaraang ito ay naghihirap mula sa isang mapaghamon at isang natatanging problema, na hindi pa malulutas, maging ng mga napakatalino na siyentipiko ng Google: ang mga halimbawa ng panlusob na problema. [the adversarial examples problem](https://ipfs.io/ipfs/QmNrAFz34SLqkzhSg4wAYYJeokfJU5hBEpkT4hPRi226y9). Ang problema na kinikilala ng Google, ay sa halip mahirap na algorithmically dahilan kung o isang partikular na sample ay magkasalungat. Ito ay hindi naaayon sa kung gaano kamangha-mangha ang teknolohiya sa pagtuturo sa sarili nito. Ang isang diskarte sa crypto-economical ay maaaring magbago ng mga benepisyaryo sa laro. Dahil dito, ang pamamaraang ito ay epektibong mag-alis ng mga posibleng mga vektor ng pag-atake ng sybil. Inaalis nito ang pangangailangan sa modelo ng hard-code na pag-crawl at nangangahulugang pagkuha ng isang nilalang. Sa halip, binibigyan nito ang kapangyarihang ito sa buong mundo. Ang isang pag-aaral na lumalaban sa sybil, agent-generated model, ay maaaring humantong sa mga order ng magnitude na higit na mahuhula na mga resulta.


## Cyber protocol

Sa core nito ang protocol ay napaka minimalistic at maaaring maipahayag gamit ang mga sumusunod na hakbang:

1.Sumite ang genesis ng cyber protocol batay sa tinukoy na pamamahagi.
2.Tukuyin ang estado ng [knowledge graph](#knowledge-graph)
3. Magtipon ng mga transaksyon gamit ang [consensus computer] (#the-notion-of-a-consensus-computer)
4.Suriin ang bisa ng mga lagda
5.Suriin ang [limitasyon ng bandwidth](#relevance-machine)
6.Suriin ang bisa ng mga CIDs
7.Kung ang mga lagda, ang limitasyon ng bandwidth at CIDs ay lahat ng may-bisa, mag-apply ng mga [cyberlink](#cyberlinks) at transaksyon
8.Kalkulahin ang mga mapagmataas ng [cyber/~Rank](#cyberrank) para sa bawat pag-ikot para sa mga CIDs sa [knowledge graph](#knowledge-graph)

Ang natitirang bahagi ng dokumentong ito ay tinatalakay ang makatwiran at ang mga teknikal na detalye ng iminungkahing protocol.

## Knowledge graph

Kinakatawan namin ang isang knowledge graph bilang isang weighted graph ng mga direktang link sa pagitan ng mga content addresses. Aka, mga pagkakakilanlan ng nilalaman, CID, IPFS hashes, o simpleng - mga link sa IPFS. Sa dokumentong ito, gagamitin namin ang mga term sa itaas bilang mga kasingkahulugan

<p align="center">
  <img src="images/knowledge-graph.png" />
</p>

Ang mga content addresses ay mahalagang web3 link. Sa halip na gamitin ang hindi maliwanag at pabago-bago:

`https://github.com/cosmos/cosmos/blob/master/WHITEPAPER.md`

Ginagamit namin ang bagay mismo:

`Qme4z71Zea9xaXScUi6pbsuTKCCNFp5TAv8W5tjdfH7yuH`

Sa pamamagitan ng paggamit ng mga content addresses upang mabuo ang knowledge graph nakakakuha kami ng [labis na kinakailangang](https://steemit.com/web3/@hipster/an-idea-of-decentralized-search-for-web3-ce860d61defe5est) [IPFS](https://ipfs.io/ipfs/QmV9tSDx9UiPeWExXEeH6aoDvmihvx6jD5eLb4jbTaKGps) - [tulad](https://ipfs.io/ipfs/QmXHGmfo4sjdHVW2MAxczAfs44RCpSeva2an4QvkzqYgfR) ng mga superpower ng p2p protocol na nais para sa isang search engine:

- mesh-network future-proof
- pag-access sa interplanetary
- paglaban sa censorship
- teknolohiyang pagsasarili

Ang aming knowledge graph ay nabuo ng mga kamangha-manghang masters. Idinagdag ng mga masters ang kanilang sarili sa knowledge graph sa tulong ng isang solong transaksyon, isang cyberlink. Sa gayon, napatunayan nila ang pagkakaroon ng kanilang private keys para sa mga content addresses ng kanilang ipinahayag na mga Public keys. Sa pamamagitan ng paggamit ng mga mechanics na ito, ang [consensus computer](#the-notion-of-a-consensus-computer) ay maaaring makamit ang napatunayan na pagkakaiba sa pagitan ng mga paksa at mga bagay sa knowledge graph. 

Ang aming pagpapatupad ng [go-cyber](https://github.com/cybercongress/go-cyber) ay batay sa mga pagkakakilanlan ng [cosmos-SDK](https://github.com/cosmos/cosmos-sdk) at mga address ng nilalaman ng [CIDv0/CIDv1](https://github.com/multiformats/cid#cidv0 

Bumubuo ang mga masters graph ng kaalaman sa pamamagitan ng paglalapat ng mga [cyberlinks](#cyberlinks).


## Cyberlinks

Upang maunawaan kung paano gumagana ang mga cyberlink kailangan nating maunawaan ang pagkakaiba sa pagitan ng isang link sa URL (aka, isang hyperlink) at sa pagitan ng isang link sa IPFS. Ang isang link sa URL ay tumutukoy sa lokasyon ng nilalaman, maging isang link ng IPFS ang nilalaman mismo. Ang pagkakaiba sa pagitan ng web architectures batay sa mga location links at content links ay radikal at nangangailangan ng isang natatanging diskarte.

Ang Cyberlink ay isang diskarte upang maiugnay ang dalawang content addresses, o mga link sa IPFS, semantically:

````bash
.md syntax: [QmdvsvrVqdkzx8HnowpXGLi88tXZDsoNrGhGvPvHBQB6sH](Qme4z71Zea9xaXScUi6pbsuTKCCNFp5TAv8W5tjdfH7yuH)    
.dura syntax: QmdvsvrVqdkzx8HnowpXGLi88tXZDsoNrGhGvPvHBQB6sH.Qme4z71Zea9xaXScUi6pbsuTKCCNFp5TAv8W5tjdfH7yuH
````

Ang nabanggit sa cyberlink ay nangangahulugan na ang pagtatanghal ng [go-cyber](https://github.com/cybercongress/go-cyber)sa panahon ng [cyberc0n](https://etherscan.io/token/0x61B81103e716B611Fff8aF5A5Dc8f37C628efb1E) ay tumutukoy sa Cosmos white paper. Ang konsepto ng mga cyberlink ay isang kombensyon sa paligid ng mga simpleng semantika ng isang format na pangkomunikasyon sa anumang p2p network:

<p align="center">
  <img src="images/cyberlink.png" />
</p>

Nakita namin na ang isang cyberlink ay kumakatawan sa isang link sa pagitan ng dalawang link. Napakadali!

Ang Cyberlink ay simple, ngunit napaka-powerful semantic construction para sa pagtatayo ng predictive model ng universe. Nangangahulugan ito na ang paggamit ng mga cyberlink sa halip ng mga hyperlink ay nagbibigay sa amin ng mga superpower na hindi naa-access sa mga nakaraang arkitektura ng mga search engine ng pangkalahatang-layunin.

Ang mga Cyberlink ay maaaring mapalawig, maaari silang bumuo ng mga linkchain kung mayroong dalawa o higit pang mga cyberlink subsist mula sa isang master, kung saan ang pangalawang link sa unang cyberlink ay katumbas ng unang link sa ikalawang cyberlink:

<p align="center">
  <img src="images/linkchain.png" />
</p>

Kung pinalawak ng mga ahente ang mga native IPFS links na may isang semantically mas mayamang, halimbawa, na may [dura](https://github.com/cybercongress/cyb/blob/dev/docs/dura.md) links, kung gayon ang pagsang-ayon sa mga execution rules sa pamamagitan ng isang tiyak na programa ay maabot sa isang mas natural na pamamaraan.

Ang [go-cyber](https://github.com/cybercongress/go-cyber) implementation ng mga cyberlink ay available sa [.cyber](https://github.com/cybercongress/dot-cyber) app ng aming eksperimentong web3 browser cyb, at sa [cyber.page](http://cyber.page).

Ang mga cyberlink na isinumite ng mga masters ay naka-imbak sa isang merkle tree ayon sa [RFC-6962 standard](https://ipfs.io/ipfs/QmZpJLmc3T2L1FLUxzvU3P8MBCPe15fEmUyVS7Bz8ZKMhG). Pinapayagan nito ang pagpapatunay para sa [proof-of-relevance](#proof-of-relevance).

<p align="center">
  <img src="images/graph-tree.png" />
</p>

Gamit ang mga cyberlink, maaari nating kalkulahin ang kaugnayan ng mga paksa at mga bagay sa [knowledge graph](#knowledge-graph). Ngunit kailangan namin ng isang  [consensus computer](#the-notion-of-a-consensus-computer).

## Ang paniwala ng isang computer na pinagkasunduan

Ang isang consensus computer ay isang abstract na computing machine na lumitaw mula sa pakikipag-ugnayan sa pagitan ng mga ahente. Ang isang consensus computer ay may kakayahan sa mga tuntunin ng mga fundamental computing resources: memorya at pagkalkula. Upang makipag-ugnay sa mga ahente ang isang computer ay nangangailangan ng bandwidth. Ang isang perpektong consensus computer ay isang computer kung saan:

`the sum of all the computations and memory available to individuals`     
`is equal to`    
`the sum of all the verified computations and memory of the consensus computer`    


Alam natin na:

`verifications of computations < (computations + verifications of computations)`    

Samakatuwid, hindi namin makamit ang isang perpektong consensus computer. Ang CAP theorem at ang scalability trilemma ay nagdaragdag ng higit na katibayan sa pahayag na ito.

<p align="center">
  <img src="images/consensus-computer.png" />
</p>

Ngunit ang teoryang ito ay maaaring gumana bilang isang tagapagpahiwatig ng pagganap para sa isang consensus computer. Matapos ang 6 na taon ng pamumuhunan sa consensus computer, natanto namin na ang pinagkasunduan ng  [Tendermint](https://ipfs.io/ipfs/QmaMtD7xDgghqgjN62zWZ5TBGFiEjGQtuZBjJ9sMh816KJ) ay may sapat na balanse sa pagitan na kinakailangan para sa aming gawain at kahandaan para sa paggawa nito. Samakatuwid, nagpasya kaming ipatupad ang [cyber](#cyber-protocol) gamit ang Tendermint consensus, na kung saan ay may napakalapit na mga setting sa Cosmos Hub. Ang pagpapatupad ng [go-cyber](https://github.com/cybercongress/go-cyber) ay isang 64-bit Tendermint consensus computer ng kaugnayan para sa 64-byte string-space. Hindi ito perpekto, hindi bababa sa 1/146, dahil mayroon kaming 146 na validator na nagpapatunay sa parehong mga pagkalkula na gumagawa ng [knowledge-graph](#knowledge-graph).

Dapat nating tiyakin ang pagkalkula, pag-iimbak at ang supply ng bandwidth ng consensus computer sa isang na-maximize na demand para sa mga query. Ang pagkalkula at pag-iimbak, kung sakaling ang isang basic [relevance machine](#relevance-machine) ay madaling mahulaan batay sa bandwidth. Ngunit ang bandwidth ay nangangailangan ng isang limiting mechanism.

## Relevance machine

Tinukoy namin ang relevance machine bilang isang makina na naglilipat ng estado ng isang [knowledge-graph](#knowledge-graph) batay sa kalooban ng mga ahente na nais magturo at pag-aralan ang [knowledge-graph](#knowledge-graph) na ito. Ang kalooban ay inaasahan ng bawat [cyberlinks](#cyberlinks) na ginagawa ng isang master. Kung mas maraming pang mga ahente ang nagtatanong sa [knowledge-graph](#knowledge-graph), mas nagiging higit ang kanilang kaalaman. Batay sa mga proyektong ito, ang pagkakaugnay sa pagitan ng content address ay maaaring makalkula. Ang relevance machine ay nagbibigay-daan sa isang simpleng konstruksyon para sa search mechanism sa pamamagitan ng pag-query at paghahatid ng mga sagot.

Ang isang pag-aari ng relevance machine ay mahalaga. Dapat itong magkaroon ng mga induktibong katangian ng pangangatuwiran o sundin ang prinsipyo ng blackbox:

`The machine should be able to interfere with predictions without any knowledge about the objects,`   
`except for who, when and what was cyberlinked`   

Kung ia-assume natin na ang [consensus computer](#the-notion-of-a-consensus-computer) ay dapat magkaroon ng ilang impormasyon tungkol sa mga linked objects, kung gayon ang pagiging kumplikado ng naturang modelo ay lalago nang hindi nahuhulaan. Samakatuwid ang mataas na mga kinakailangan ng computer sa pagproseso para sa memorya at pagkalkula. Salamat sa nilalaman ng pagtugon sa isang relevance machine na sumusunod sa prinsipyo ng blackbox, ay hindi kailangang mag-imbak ng data. Ngunit, maaari pa ring epektibong gumana sa tuktok nito. Ang pagbawas ng kahulugan sa loob ng [consensus computer](#the-notion-of-a-consensus-computer ay mahal. Samakatuwid, ang gayong disenyo ay maaaring depende sa assumption blindness. Sa halip na ibawas ang kahulugan sa loob ng [consensus computer](#the-notion-of-a-consensus-computer), nag-disenyo kami ng isang sistema kung saan ang kahulugan ng pagkuha ay hindi na-insentibo. Nakamit ito dahil sa mga masters na nangangailangan ng mga token ng [CYB](#cyb) upang ipahayag ang kanilang kalooban, batay sa kung saan, maaaring makalkula ang ranggo ng kaugnayan. 

Sa gitna ng sistema ng proteksyon ng spam ay isang palagay na ang mga operasyon ng pagsulat ay maaaring isakatuparan lamang ng mga mayroong isang vested na interes sa ebolusyon ng tagumpay ng relevance machine. Bawat 1% ng epektibong stake sa loob ng [consensus computer](#the-notion-of-a-consensus-computer) ay nagbibigay ng kakayahang magamit ang 1% ng mga bandwidth ng mga posibleng network at ang computing capabilities nito. Ang isang simpleng patakaran ay pumipigil sa pang-aabuso sa mga ahente: isang pares ng mga pagkakakilanlan ng nilalaman ay maaaring mai-cyberlink ng isang beses sa isang address.

<p align="center">
  <img src="images/algo1.png" />
</p>

Mayroong dalawang mga paraan lamang upang mabago ang epektibong stake (active stake + bonded stake) ng isang account: direct token transfers at bonding operations.

Gumagamit ang [Cyber](#cyber-protocol) ng isang napaka-simpleng modelo ng bandwidth. Ang pangunahing layunin ng modelong ito ay upang mabawasan ang pang-araw-araw na paglaki ng network sa naibigay palagi. Ginagawa ito upang mapaunlakan ang mga bayani (validators) na may kakayahang mag-forecast ng anumang pamumuhunan sa hinaharap sa imprastraktura. Kaya, narito ipinakilala namin ang 'watts' o 'W'. Ang bawat uri ng mensahe ay may itinalagang W cost. Ang palagiang 'DesirableBandwidth', ay tumutukoy sa kanais-nais na 'RecoveryWindow' na ginugol ng halaga ng W. Tinukoy ng recovery period kung gaano kabilis ang mababawi ng isang master ang kanilang bandwidth mula 0 pabalik sa max bandwidth. Ang isang master ay may pinakamataas na proporsyonal na W sa kanyang mabisang stake, na tinutukoy ng sumusunod na pormula:

`AgentMaxW = EffectiveStake * DesirableBandwidth`

Ang panahong 'AdjustPricePeriod' ay nagbubuo ng kung magkano ang ginugol sa W sa panahon ng 'RecoveryPeriod' sa pinakabagong block. Ang 'SpentBandwidth' / 'DesirableBandwidths' ratio ay tinatawag na fractional reserve ratio. Kapag ang network usage ay mababa, ang fractional reserve ratio ay nag-aayos ng gastos sa mensahe upang payagan ang mga masters na may mas mababang stake upang gumawa ng mas maraming mga transaksyon. Kapag ang demand para sa mga mapagkukunan ay nagdaragdag, ang fractional reserve ratio ay napupunta> 1, dahil dito, ang pagtaas ng gastos ng mensahe at paglilimita ng huling tx count para sa isang pangmatagalang panahon (ang pagbawi ng W ay <pagkatapos W paggastos). Dahil walang gumagamit ng lahat ng kanilang pagmamay-ari ng bandwidth, ito'y ligtas at maaaring gumamit ng hanggang sa 100x na fractional na reserba sa loob ng panahon ng target na recalculation target. Ang ganitong mga mechanics ay nagbibigay ng discount para sa paglikha ng [cyberlinking](#cyberlinks), sa gayon, epektibong na-maximize ang demand para dito. Maaari mong makita na ang iminungkahing disenyo ay nangangailangan ng demand para sa buong bandwidth para sa kaugnayan upang maging mahalaga.

Ang katalinuhan ng tao ay isinaayos sa isang paraan na walang nauugnay at walang-mahalagang mga alaala na nakalimutan sa paglipas ng panahon. Parehong maaaring mailapat sa relevance machine. Ang relevance machine ay maaaring magpatupad ng mga [aggressive pruning strategies](https://ipfs.io/ipfs/QmP81EcuNDZHQutvdcDjbQEqiTYUzU315aYaTyrVj6gtJb) tulad ng, ang pruning ng kasaysayan ng pagbuo ng [knowledge-graph](#knowledge-graph), o pagkalimot ng mga link na hindi gaanong nauugnay.

Bilang resulta, ang ipinatupad na cybernomics ng mga token ng [CYB](#cyb) ay nagsisilbi hindi lamang bilang mga mekanismo ng proteksyon ng pagpapahayag at proteksyon ng spam, kundi pati na rin, gumana bilang isang tool sa regulasyon sa ekonomiya na maaaring ihanay ang kapasidad sa pagproseso ng mga bayani at ang demand sa merkado para sa pagproseso. Ang go-cyber na pagpapatupad ng relevance machine ay batay sa isang straightforward mechanism, na tinatawag na: cyber~ Rank.


## cyber\~Rank

Ranking using a [consensus computer](#the-notion-of-a-consensus-computer) can be challenging, as consensus computers have serious resource constraints. First, we must ask ourselves: why do we need to compute and to store the rank on-chain and not follow the same way as [Colony](https://ipfs.io/ipfs/QmZo7eY5UdJYotf3Z9GNVBGLjkCnE1j2fMdW2PgGCmvGPj) or [Truebit](https://ipfs.io/ipfs/QmTrxXp2xhB2zWGxhNoLgsztevqKLwpy5HwKjLjzFa7rnD)?

When rank was computed inside a [consensus computer](#the-notion-of-a-consensus-computer) one has easy access to the content distribution of that rank and an easy way to [build provable applications](#apps) on top of that rank. Hence, we have decided to follow a more cosmic architecture. In the next section we describe the [proof of relevance](#proof-of-relevance) mechanism, which allows the network to scale with the help of domain-specific [relevance machines](#relevance-machine). Those work concurrently, thanks to the IBC protocol.

Eventually, the [relevance machine](#relevance-machine) needs to obtain (1) a deterministic algorithm, that will allow for the computation of the rank on a continuously appending network, which itself, can scale to the orders of magnitude of the likes of [Google](https://google.com). Additionally, a perfect algorithm (2) must have linear memory and computational complexity. Most importantly, it must have (3) the highest provable prediction capabilities for the existence of relevant [cyberlinks](#cyberlinks).

After [thorough research](https://ipfs.io/ipfs/QmTJPJ55ePgR2MS1HoAtyqS1mteVLXUjAS4H8W97EEopxC), we have found that it is impossible to obtain the silver bullet. Therefore, we have decided to find a more basic, bulletproof way, that can bootstrap the network: [the rank](http://ipfs.io/ipfs/QmbuE2Pfcsiji1g9kzmmsCnptqPEn3BuN3BhnZHrPVsiVw) which Larry and Sergey used to bootstrap their previous network. The key problem with the original PageRank is that it wasn't resistant to sybil attacks. However, a token-weighted PageRank which is limited by a token-weighted bandwidth model does not inherit the key problem of the naive PageRank, because - it is resistant to sybil attacks. For the time being, we will call it cyber\~Rank, until something more suitable will emerge. The following algorithm is applied to its implementation at Genesis:

<p align="center">
  <img src="images/algo2.png" />
</p>

We understand that the ranking mechanism will always remain a red herring. This is why we expect to rely on the on-chain governance tools that can define the most suited mechanism at a given time. We suppose that the network can switch from one algorithm to another, not simply based on subjective opinion, but rather on economical a/b testing through 'hard spooning' of domain-specific [relevance machines](#relevance-machine).

cyber\~Rank shields two design decisions which are of paramount importance: (1) it accounts for the current intention of the agents, and (2) it encourages rank inflation of [cyberlinks](#cyberlinks). The first property ensures that cyber\~Rank can not be gamed with. If an agent decides to transfer their [CYB](#cyb) tokens out of their account, the [relevance machine](#relevance-machine) will adjust all the [cyberlinks](#cyberlinks) relevant for this account per the current intentions of the agent. And vice versa, if an agent transfers [CYB](#cyb) tokens into their account, all of the [cyberlinks](#cyberlinks) submitted from this account will immediately gain more relevance. The second property is essential in order not to get cemented in the past. As new [cyberlinks](#cyberlinks) are continuously added, they will dilute the rank of the already existing links proportionally. This property prevents a situation where new and better content has a lower rank simply because it was recently submitted. We expect these decisions to enable an inference quality for recently added content to the long tail of the [knowledge graph](#knowledge-graph).

We would love to discuss the problem of vote-buying. Vote-buying as an occurrence isn't that bad. The dilemmas with vote-buying appear within systems where voting affects the allocation of that systems inflation. For example, [Steem](http://ipfs.io/ipfs/QmepU77tqMAHHuiSASUvUnu8f8ENuPF2Kfs97WjLn8vAS3) or any fiat-state based system. Vote-buying can become easily profitable for an adversary that employs a zero-sum game without the necessity to add value. Our original idea of a decentralized search was based on this approach. But, we have rejected that idea, removing the incentive of the formation of the [knowledge graph](#knowledge-graph) to the consensus level. In the environment where every participant must bring some value to the system to affect the predictive model, vote-buying becomes NP-hard problem. Therefore, becomes beneficial to the system.

The current implementation of the [relevance machine](#relevance-machine) utilizes GPUs to compute rank. The machine can answer and deliver relevant results for any given search request in a 64-byte CID space. However, it is not enough to build a network of domain-specific [relevance machines](#relevance-machine). [Consensus computers](#the-notion-of-a-consensus-computer) must have the ability to prove relevance to one another.

## Proof of relevance

We have designed the network under the assumption that with regards to search, such a thing as malicious behaviour, does not exist. This can be assumed as no malicious behaviour can be found in the intention of finding the answers. This approach significantly reduces any surface attacks.

````bash
Ranks are computed based on the fact that something was searched, thus linked, and as a result - affected the predictive model
````

A good analogy is observed in quantum mechanics, where the observation itself affects behaviour. This is why we have no requirement for such a thing as negative voting. By doing this, we remove subjectivity out of the protocol and we can define proof of relevance.

<p align="center">
  <img src="images/graph-tree.png" />
</p>

Each new CID receives a sequence number. Numbering starts with zero. Then incremented by one for each new CID. Therefore, we can store rank in a one-dimensional array, where indices are the CID sequence numbers. Merkle tree calculations are based on the [RFC-6962 standard](https://ipfs.io/ipfs/QmZpJLmc3T2L1FLUxzvU3P8MBCPe15fEmUyVS7Bz8ZKMhG). Using Merkle trees, we can effectively proof the rank for any given content address. While relevance is still subjective by nature, we have a collective proof that something was relevant to a certain community at some point in time.

Using this type of proof any two [IBC compatible](https://ipfs.io/ipfs/QmSGbrGAPZtR6Q1jHHe8mmS3bLBehKmfp9ZYvrg5ycaZuk) [consensus computers](#the-notion-of-a-consensus-computer) can prove relevance one to another. This means that domain-specific [relevance machines](#relevance-machine) can flourish.

In the relevance for a common [go-cyber](https://github.com/cybercongress/go-cyber) implementation, the Merkle tree is computed every round and its root hash committed to ABCI.

## Speed

We require instant confirmation time to provide users with the feeling of a conventional web-application. This is a powerful architectural requirement that shapes the economical topology and the scalability of the [cyber](#cyber-protocol) protocol. The proposed blockchain design is based on the [Tendermint consensus](https://ipfs.io/ipfs/QmaMtD7xDgghqgjN62zWZ5TBGFiEjGQtuZBjJ9sMh816KJ) algorithm with 146 validators and has a quick, 5 second tx finality time. The average confirmation time is closer to 1 second and could make complex blockchain interactions almost invisible to agents.

We denote one particular [go-cyber](https://github.com/cybercongress/go-cyber) property in the context of speed - rank computation. Being a part of the consensus, it occurs in parallel to transaction validation within the rounds. A round is a consensus variable defined by the stakeholders. At the inception, one round is set to 20 blocks. Practically, this indicates that every 100 seconds the network must agree on the current root hash of the [knowledge graph](#knowledge-graph). This means that every [cyberlink](#cyberlinks) submitted becomes a part of the [knowledge graph](#knowledge-graph) almost instantly and acquires a rank within an average period of 50 seconds. In the early days of [Google](https://google.com) rank was recomputed roughly every week. We believe that masters of the Great Web will be pleased to observe that ranking changes in real-time, but, have decided to launch the network with an assumption that this window is enough. It is expected that with the development of the [cyber](#cyber-protocol) protocol the velocity of each round will decrease. This is due to competition between heroes. We are aware of certain mechanisms to make this function order of magnitudes faster:

- optimization of the consensus parameters
- better parallelization of rank computation
- a [better clock](https://ipfs.io/ipfs/QmbsKzizZVVVzPbZvg1qSsNMkwmA3MFufgXb3MFqbSnmPs) ahead of consensus

## Scalability

We require an architecture which will allow us to scale the idea to the significance of the likes of [Google](https://google.com). Let us assume, that node implementation, which is based on [Cosmos-SDK](https://github.com/cosmos/cosmos-sdk) can process 10k transactions per second. This would mean, that every day, at least 8.64 million masters will be able to submit 100 [cyberlinks](#cyberlinks) each, and impact the search results simultaneously. This is enough to verify all the assumptions out in the wild, but, not enough to say that it will work at the current scale of the Internet. Given the current state of the art research done by our team, we can safely state that there is no consensus technology in existence, that will allow scaling a particular blockchain to the size that we require. Hence, we introduce the concept of domain-specific [knowledge graphs](#knowledge-graph).

<p align="center">
  <img src="images/network.png" />
</p>

One can either launch an own domain-specific search engine by forking [go-cyber](https://github.com/cybercongress/go-cyber), which is focused on \textit{common public knowledge}. Or, simply plug [go-cyber](https://github.com/cybercongress/go-cyber) as a module into an existing chain, e.i. Cosmos Hub. The inter-blockchain communication protocol introduces concurrent mechanisms of syncing state between [relevance machines](#relevance-machine). Therefore, in proposed search architecture, domain-specific [relevance machine](#relevance-machine) will be able to learn from common knowledge. Just as common knowledge can learn from domain-specific [relevance machines](#relevance-machine).

## Browzers

We were aspired to imagine how proposed network would operate with a web3 browser. To our disappointment we [were not able](https://github.com/cybercongress/cyb/blob/master/docs/comparison.md) to find a web3 browser that can showcase the coolness of the proposed approach in action. This is why we have decided to develop a web3 browser from scratch. [Cyb](https://cyb.ai) is your friendly robot which has a sample [.cyber](https://cyber.page) application for interacting with the [cyber](#cyber-protocol) protocol.

<p align="center">
  <img src="images/cyb.jpg" />
</p>

As a good example of delivery, we have created [cyber.page](https://cyber.page/). It allows heroes, masters and evangelists to interact with the protocol via a web2 gateway. Create cyberlinks, pin content directly to IPFS, search the Great Web, participate in the governance of cyber and so on. It can also act as an in-depth explorer, a wallet and can pocket hardware wallets, such as Ledger devices.

The current search snippets are ugly. But, we presume that they can be easily extended using [IPLD](https://github.com/ipld/specs) for different types of content. Eventually, they can become even more attractive than those of [Google](https://google.com).

<p align="center">
  <img src="images/architecture.png" />
</p>

During the implementation of the proposed architecture, we have realized at least 3 key benefits that [Google](https://google.com) would probably not be able to deliver with its conventional approach:

- the search results can be easily delivered from any p2p network: e.g. .cyber can play videos
- payment buttons can be embedded right into search snippets. This means that agents can interact with the search results, e.g. agents can buy an item right in .cyber. This means that e-commerce can flourish fairly thanks to a provable conversion attribution
- search snippets do not have to be static but can be interactive. e.g. .cyber can deliver your current wallet balance

## Deployment

Due to technical limitations, we have to bootstrap the ecosystem using 2 tokens: [THC](#thc) and [CYB](#cyb)

- [CYB](#cyb) is the native token of the sovereign [cyber](#cyber-protocol) protocol powered by the Tendermint consensus algorithm. It has 3 primary uses: (1) staking for consensus, (2) bandwidth limiting for submitting [cyberlinks](#cyberlinks), and (3) expression of the will of the masters for the computation of cyber\~Rank.

- [THC](#thc) (pronounce as tech) is a creative cyber proto substance. [THC](#thc) being an Ethereum ERC-20 compatible token that has utility value in the form of control over cyber\~Foundation (the community governing DAO) and the ETH from the distribution game. [THC](#thc) is emitted during the creation of cyber\~Foundation as an Aragon organization. The creative powers of [THC](#thc) come from the ability to receive 1 [CYB](#cyb) token per each 1 [THC](#thc) token when vested before the end of cyber\~Auction.

Both tokens remain functional and will track value independently of one another due to their very different utility by nature.

Overall, the deployment process has the following structure:

1. cyber\~Congress deploys Game of Links
2. The community participates in the Game of Links
3. The community verifies and proposes a Genesis block with results from the Game of Links
4. cyber\~Congress deploys contracts for cyber\~Foundation and cyber\~Auction
5. The community participate in cyber\~Auction after Genesis. Donors stake [THC](#thc) tokens to get [CYB](#cyb) tokens
6. cyber\~Congress distributes [CYB](#cyb) tokens continuously during cyber\~Auction
7. cyber\~Congress burns the remaining [CYB](#cyb) and [THC](#thc) tokens and reports on the end of the initial distribution process

cyber~Congress lives in Ethereum as an [Aragon DAO](https://mainnet.aragon.org/#/cybercongress/0x4feb2bcc5907e7779130c093eef8fb44502c1330). It also operates a [2-of-3 multisig in Cyber network](https://cyber.page/network/cyber/contract/cyber1latzme6xf6s8tsrymuu6laf2ks2humqvdq39v8). cyber\~Congress developed the [cyber](#cyber-protocol) protocol. Within the context of cyber, the Congress has 2 roles:

1. To deploy and to execute the initial distribution program, which is impossible to automate. Because there is no trustless infrastructure for message swapping between ETH and ATOM, cyber\~Congress introduces a single point of failure in the initial distribution process. We have decided to send [CYB](#cyb) tokens to [THC](#thc) stakers manually because we feel that now is the right time to launch the network we have created. We also believe that an ongoing auction is vital for the initial distribution process. If cyber\~Congress fails to deliver its obligations in terms of distribution due to any possible reasons, we hope that the community will be able to fork out the network and to distribute [CYB](#cyb) tokens as was promised. Hopefully, every operation is designed provably and transparently. All operations will be executed using a [special purpose 2-of-3 multisig account in Cyber network](https://cyber.page/network/cyber/contract/cyber147drnke9676972jr3anklkj7pzgwjw47cp2u7j).

2. Support the growth of [cyber](#cyber-protocol) protocol until the community takes over the development in the form of cyber\~Foundation. Donations in ATOMs during Game of Links will be distributed to the [cyber\~Congress Cosmos 2-of-3 multisig](https://www.mintscan.io/account/cosmos1latzme6xf6s8tsrymuu6laf2ks2humqv2tkd9a). All ATOM donations that are routed to the cyber\~Congress multisig will become its property. The role of ATOM donation is the following: thanks to ATOM we want to secure a commitment for cyber\~Congress in the development of both Cosmos and Cyber ecosystems. ATOM donations will allow cyber\~Congress to use staking rewards and reach a sustainable flow, for the continuous funding of the [cyber](#cyber-protocol) protocol without the necessity to dump neither [CYB](#cyb) nor ATOM tokens.

## CYB

Proof-of-stake systems do not help with the initial distribution. We believe that if the initial distribution is designed purposefully, energy-efficiently, provably and transparently, hence accessible, the early [knowledge graph](#knowledge-graph) will gain in quality and size.

The genesis block of the cyber protocol contains 1 000 000 000 000 000 CYB (one petacyb or 1 PCYB) tokens broken down as follows:

- 750 000 000 000 000 CYB tokens for those who stake [THC](#thc) tokens until the end of cyber\~Auction (participants of cyber\~Congress, Game of Thrones in ETH and cyber\~Auction)
- 150 000 000 000 000 CYB tokens for the participants of Game of Links
- 100 000 000 000 000 CYB tokens as a gift for Ethereum, Cosmos and Urbit communities

<p align="center">
  <img src="images/CYB.svg" />
</p>

After the Genesis, CYB tokens can only be created by heroes based on staking and slashing parameters. The basic consensus is that newly created CYB tokens are at the disposal of stakeholders.

There is currently no such thing as a maximum amount of CYB tokens. This is due to the continuous inflation paid to the heroes of the network. CYB token is implemented using uint64, so the creation of additional CYB tokens makes it significantly more expensive to compute state changes and rank. We expect for a lifelong monetary strategy to be established by the governance system after the complete initial distribution of CYB tokens and the activation of the functionality of smart contracts. The starting parameters of the inflation will be defined via governance during the Game of Links.

## THC

The goal of creating an alternative to a [Google-like](https://google.com) structure requires extraordinary effort from various groups. Hence, we have decided to set up cyber\~Foundation as a fund, managed via a decentralized engine such as an Aragon DAO. It is charged with ETH and managed by the agents who have participated in the initial distribution. This approach will allow safeguarding from excessive market dumping of the native platform token - [CYB](#cyb) within the first years of its work, thereby, ensuring stable development. Additionally, this allows to diversify the underlying platform and extend the protocol to other consensus computing architectures, should such a need arise.

While choosing the token for donations, we followed three main criteria: the token must be (1) one of the most liquid, (2) most promising, so a community can secure a solid investment bag to be competitive even in comparison to such giants like [Google](https://google.com), and (3) have the technical ability to execute an auction and a resulting organization, without relying on any third party. The only system that matches these criteria is Ethereum, hence, the primary token of donations will be ETH.

Prior to Genesis cyber\~Foundation has minted 750 000 000 000 000 THC (seven hundred fifty terathc) broken down as follows:

- 600 000 000 000 000 THC tokens are allocated to the cyber\~Auction contract
- 150 000 000 000 000 THC tokens are allocated to the cyber\~Congress contract

<p align="center">
  <img src="images/THC.svg" />
</p>

All decisions by cyber\~Foundation will be executed based on the results of THC votes. The following parameters will be applied:

- Support: 51\%
- Quorum: 51\%
- Vote duration: 500 hours

## Gift

We want to give the ability to evaluate the proposed approach to as many agents as we can. But, without adding such complexity as KYC and/or captcha. That is why we chose to gift 8% of [CYB](#cyb) tokens in Genesis to Ethereum, 1% to Cosmos, and 1% to Urbit communities. The following rules are applied to reproduce the Genesis:

- Every account within the Ethereum foundation network, with at least 1 outgoing transaction which is not a contract, and holds > 0.001 ETH at block 8080808
- Every non-zero account within Cosmos hub-3 at block 2000000
- Every account which holds galaxies (30%), stars (30%), or planets (40%) at block 10677601 according to the number of objects

The key purpose of this gift is for every account in Genesis to be able to make at least 1 [cyberlink](#cyberlinks) in the space of 24 hours as the network is unloaded. This is why we have decided to make the distribution curve a bit more even, and radically change it to a quadratic curve. Hence, we distribute [CYB](#cyb) tokens proportionally to the square root of each account balance during the snapshots. Because a quadratic design is too easy to game with, we have calculated the amount of the distributed [CYB](#cyb) tokens for the proposed blocks before this fact became known to the public. We do not apply the quadratic rule to Urbit aliens.

## Game of Links

A game for Cosmos hodlers in ATOM. Participants donate ATOM in exchange for CYB. The more ATOM is donated, the higher the price of CYB. The game starts from 1 ATOM per 1 GCYB. The game is over when either 146 days have passed since the beginning of the Takeoff donations, or if the price has increased 5x from the starting price. The price of [CYB](#cyb) during the Takeoff is defined by the following function:

f(c) = 40 * c + 1000 

where f(c) is TCYB price in ATOM, the c is amount of TCYB tokens won during Takeoff.

The key idea is: the better the Takeoff donation round performs, the more payouts the participants in the disciplines will receive. 100 [TCYB](#cyb) is allocated to the participants of the Takeoff donations and 50 [TCYB](#cyb) is allocated for participants of the Game of Links disciplines. All [CYB](#cyb) tokens that remain from the Takeoff, are allocated to the community pool at the end of the game. All [CYB](#cyb) tokens that remain from the disciplines are allocated to cyber\~Congress. In addition to CYB tokens, Game of Links allocates test EUL tokens to all Takeoff donors for the final. A [detailed document](https://cybercongress.ai/game-of-links/) has been published with rules and provisions for the game.

## Cyber\~Auction

A game for Ethereum hodlers in ETH. Participants donate ETH in exchange for THC. The more ETH is donated, the higher the price of THC. The game starts from the price which is 5x closing price of the Takeoff in ETH. The game is over when either 888 days have passed since its inception or if the price has increased 5x from the starting price. During this phase [CYB](#cyb) tokens are continuously distributed by cyber\~Congress, based on the vested [THC](#thc) tokens until the end of the auction. Vested [THC](#thc) tokens provide the ability to receive [CYB](#cyb) tokens accordingly, and voting powers within cyber\~Foundation. The price of [THC](#thc) during Cyber\~Auction is defined by the following function:

g(t)= 1/30 * t * p + 5 * p

where g(t) is TTHC price in ETH, t is amount of TTHC tokens won during cyber\~Auction, p is the resulting price of Takeoff for one CYB converted to ETH at closing moment.

The starting price is designed to give the Takeoff participants 5x premium for their risk of investing in hardware and software infrastructure prior to Genesis. cyber\~Auction gives significant incentives for early participators. After the end of the distribution, participants will be able to unlock their [THC](#thc) tokens and use them as they wish, e.i. transfer, exchange, etc. As a result of the auction, the community will have access to all the donated ETH within the Aragon organization. After the end of cyber\~Auction, all the remaining [THC](#thc) on the cyber\~Auction contract must be provably burned. The following rules apply to [CYB](#cyb) tokens under the [multisig for distribution](https://cyber.page/network/cyber/contract/cyber147drnke9676972jr3anklkj7pzgwjw47cp2u7j):

- cyber\~Congress will not delegate its stake, and as a result, it will remain a passive stake until it will become distributed
- after the end of cyber\~Auction, all the remaining [CYB](#cyb) tokens must be provably burned

## Apps

We assume that the proposed algorithm does not guarantee high-quality knowledge by default. Just like a newborn, it needs to acquire knowledge to develop further. The protocol itself provides just one simple tool: the ability to create a [cyberlinks](#cyberlinks) with an agents stake between two content addresses.

Analysis of the semantic core, behavioural factors, anonymous data about the interests of agents and other tools that determine the quality of search, can be achieved via smart contracts and off-chain applications, such as: [web3 browsers](#browzers), decentralized social networks and content platforms. We believe, that it is in the interest of the community and the masters to build the initial [knowledge graph](#knowledge-graph) and to maintain it. Hence, for the graph, to provide the most relevant search results.

Generally, we distinguish three types of applications for [knowledge graphs](#knowledge-graph):

- Consensus apps. Can be run at the discretion of the [consensus computer](#the-notion-of-a-consensus-computer) by adding intelligent abilities
- On-chain apps. Can be run by the [consensus computer](#the-notion-of-a-consensus-computer) in exchange for gas
- Off-chain apps. Can be implemented by using the [knowledge graph](#knowledge-graph) as an input within an execution environment

The following, imaginable, list of apps consolidates the above-mentioned categories:

Web3 browsers. In reality, browser and search are inseparable. It is hard to imagine the emergence of a full-blown web3 browser which is based on web2 search. Currently, there are several efforts for developing browsers around blockchains and distributed tech. Amongst them are Beaker, Mist, Brave, and Metamask. All of them suffer from trying to embed web2 into web3. Our approach is a bit different. We consider web2 as an unsafe subset for web3. So we have developed an experimental web3 browser, Cyb, showcasing the [cyber](#cyber-protocol) approach to answering queries better and delivering content faster.

Social networks. Social networks are not that mysterious. In any social network content is the king. Hence, provable ranking is the basic building block of any social network. All types of social networks can be easily built on top of a [knowledge graph](#knowledge-graph). Cyber can also create social networks based on relevance between users, which no current network is able to achieve.

Programmable semantics. Currently, the most popular keywords in the gigantic semantic core of [Google](https://google.com) are keywords of apps such as: [Youtube](https://youtube.com), [Facebook](https://facebook.com), [GitHub](https://github.com), etc. However, the developers of those successful apps have very limited ability to explain to [Google](https://google.com) how to structure search results in a better manner. The [cyber](#cyber-protocol) approach gives this power back to developers. Developers are now able to target specific semantics cores and index their apps as they wish.

Search actions. The proposed design enables native support for blockchain (and tangle-alike) assets related activity. It is trivial to design applications which are (1) owned by the creators, (2) appear correctly in the search results and (3) allow a transactable action, with (4) provable attribution of a conversion for a search query. e-Commerce has never been this easy for everyone.

Off-line search. IPFS makes it possible to easily retrieve a document from an environment without a global internet connection. [go-cyber](https://github.com/cybercongress/go-cyber) itself can be distributed by using IPFS. This creates the possibility for ubiquitous, off-line search!

Command tools. Command-line tools can rely on relevant and structured answers from a search engine. Practically speaking, the following CLI tool is possible to implement:

````bash
>  go-cyber earn using 100 GB

Enjoy the following predictions:
- apt install go-filecoin:     0.001   BTC p/ month p/ GB
- apt install siad:            0.0007  BTC p/ month p/ GB
- apt install storjd:          0.0005 BTC p/ month p/ GB

According to the most desirable prediction, I decided to try `mine go-filecoin -limit 107374182400`

Git clone ...
Building go-filecoin
Starting go-filecoin
Creating a wallet using @xhipster seed
Your address is ...
Placing bids ...
Waiting for incoming storage requests ...
````

Search tools, from within CLI will inevitably create a highly competitive market of a dedicated semantic core for robots.

Autonomous robots. Blockchain technology enables the creation of devices that can manage digital assets on their own.

`If a robot can store, earn, spend and invest - they can do everything you can do`

What is needed is a simple, yet a powerful state reality tool with the ability to find particular things. [go-cyber](https://github.com/cybercongress/go-cyber) offers a minimalistic, but a continuously self-improving data source, which provides the necessary tools for programming economically rational robots. According to [top-10,000 English words](https://github.com/first20hours/google-10000-english) the most popular word in the English language is the defining article 'the', which means a pointer to a particular item. This fact can be explained as the following: particular items are of most importance to us. Therefore, the nature of us is to find unique things. Hence, the understanding of unique things is essential for robots too.

Language convergence. A programmer should not care about the language that an agent will be using. We don't need to know in which language the agent is performing their search in. The entire UTF-8 spectrum is at work. The semantic core is open, so competition for answering queries can become distributed across different domain-specific areas. Including the semantic cores for various languages. This unified approach creates an opportunity for cyber\~Bahasa. Since the dawn of the Internet, we observe a process of rapid language convergence. We use truly global words across the entire planet, independently of nationality, language, race, name or Internet connection. The dream of a truly global language is hard to deploy because it is hard to agree on what means what. However, we have the tools to make this dream come true. It is not hard to predict that the shorter a word, the more powerful its cyber\~Rank will be. Global, publicly available list of symbols, words, and phrases sorted accordingly by cyber\~Rank with a corresponding link provided by [go-cyber](https://github.com/cybercongress/go-cyber) can become the foundation for the emergence of a genuinely global language everybody can accept. Recent [scientific advances](https://ipfs.io/ipfs/QmQUWBhDMfPKgFt3NfbxM1VU22oU8CRepUzGPBDtopwap1) in machine translation are breathtaking but meaningless to those who wish to apply them without a Google-scale trained model. The proposed cyber\~Rank offers precisely this.

Self prediction. A [consensus computer](#the-notion-of-a-consensus-computer) can continuously build a [knowledge graph](#knowledge-graph) on its own predicting the existence of [cyberlinks](#cyberlinks) and applying these predictions to its state. Hence, a [consensus computer](#the-notion-of-a-consensus-computer) can participate in the economic consensus of the [cyber](#cyber-protocol) protocol.

Universal oracle. A [consensus computer](#the-notion-of-a-consensus-computer) can store the most relevant data in a key-value storage. Where the key is a CID and the values are the bytes of the actual content. This can be achieved by making a decision every round, in regards to which CID value the agentss want to prune and which value they wish to apply. Based on the utility measure of content addresses within the [knowledge graph](#knowledge-graph). To compute utility measure, heroes check the availability and the size of the content for the top-ranked content addresses within the [knowledge graph](#knowledge-graph), then, weight on the size of the CIDs and its rank. The emergent key-value storage will be available to write for [consensus computer](#the-notion-of-a-consensus-computer) only and not for agents. But, values could be used in programs.

Location-aware search. It is possible to construct [cyberlinks](#cyberlinks) with [Proof-of-Location](https://ipfs.io/ipfs/QmZYKGuLHf2h1mZrhiP2FzYsjj3tWt2LYduMCRbpgi5pKG) based on remarkable existing protocols such as [Foam](https://ipfs.io/ipfs/QmZYKGuLHf2h1mZrhiP2FzYsjj3tWt2LYduMCRbpgi5pKG). Consequently, a location-based search also becomes provable, if web3-agents will mine triangulations and attach [proof-of-location](https://ipfs.io/ipfs/QmZYKGuLHf2h1mZrhiP2FzYsjj3tWt2LYduMCRbpgi5pKG) for every linked chain.

Prediction markets on link relevance. We can implement this idea using the ranking of the [knowledge graph](#knowledge-graph) based on a prediction market on link relevance. An app that allows betting on link relevance, can become a unique source of truth for the direction of terms, as well as, motivate agents to submit more links.

Private cyberlinks. Privacy is fundamental. While we are committed to privacy, achieving implementation of private [cyberlinks](#cyberlinks) is unfeasible for our team up to Genesis. Therefore, it is up to the community to work on WASM programs, that can be executed on top of the protocol. The problem is to compute cyber\~Rank, based on the [cyberlinks](#cyberlinks) submitted by a web3-masters without revealing neither: their previous request nor the public keys. Zero-knowledge proofs, in general, are very expensive. We believe that the privacy of search should be a feature by design, but we are unsure that we know how to implement it at this stage. [Coda](https://ipfs.io/ipfs/Qmdje3AmtsfjX9edWAxo3LFhV9CTAXoUvwGR7wHJXnc2Gk) like recursive Snarks and [MimbleWimble](https://ipfs.io/ipfs/Qmd99xmraYip9cVv8gRMy6Y97Bkij8qUYArGDME7CzFasg) constructions, in theory, can solve part of the privacy concern. But, they are new, untested and anyway, will be more expensive with regards to computations than their transparent alternative.

This is surely not the excessive list of all the possible applications, but a very exciting one indeed.

## Conclusion

We defined and implemented a protocol for provable communication, between consensus computers on relevance. The protocol is based on the simple idea of knowledge graphs, which are generated by agents via the use of cyberlinks. Cyberlinks are processed by a consensus computer using the concept of the relevance machine. The cyber consensus computer is based on CIDv0/CIDv1 and uses go-IPFS and Cosmos-SDK as a foundation. IPFS provides significant benefits with regards to resource consumption. CID as primary objects are robust in their simplicity. For every CID, cyber\~Rank is computed by a consensus computer without a single point of failure. Cyber\~Rank is a CYB token weighted PageRank, with economic protection from sybil attacks and selfish voting. Every round the Merkle root of the rank and graph trees are published. Consequently, every computer can prove to any other computer the relevance of value for a given CID. Sybil resistance is based on bandwidth limiting. The embedded ability to execute programs offers inspiring applications. The starting primary goal is the indexing of peer-to-peer content addresses systems, either stateless, such as: IPFS, Swarm, Sia, Git, BitTorrent, or stateful, such as: Bitcoin, Ethereum and other blockchains and tangles. The proposed semantics of cyberlinking offers a robust mechanism for predicting meaningful relations between objects by the consensus computer itself. The source code of the relevance machine is open-source. Every bit of data accumulated by the consensus computer is available for anyone if one has the resources to process it. The performance of the proposed software implementation is sufficient for seamless interaction. The scalability of the proposed implementation is sufficient to index all self-authenticated data that exist today and can serve it to millions of agents of the Great Web. The blockchain is managed by a Superintelligence, which functions under the Tendermint consensus algorithm with a standard governance module. Though the system provides the necessary utility to offer an alternative for a conventional search engine, it is not limited just to this use case. The system is extendable for numerous applications and makes it possible to design economically rational, self-owned robots, that can autonomously understand objects around them.

## References

1. [Scholarly context adrift](https://ipfs.io/ipfs/QmNhaUrhM7KcWzFYdBeyskoNyihrpHvUEBQnaddwPZigcN)
2. [Brand-new stack](https://ipfs.io/ipfs/Qmf2rKkDPSsvdudwSmdDPbZuYae8XRV26c1wAFCCvg8Dhw)
3. [Search engines information retrieval in practice](https://ipfs.io/ipfs/QmeS4LjoL1iMNRGuyYSx78RAtubTT2bioSGnsvoaupcHR6)
4. [Motivating game for adversarial example research](https://ipfs.io/ipfs/QmNrAFz34SLqkzhSg4wAYYJeokfJU5hBEpkT4hPRi226y9)
5. [An idea of a decentralized search](https://ipfs.io/ipfs/QmXNoGTWLQrcFRb66oS4HafpP1vcLKbVkJrQm4DVvihuoq)
6. [IPFS](https://ipfs.io/ipfs/QmV9tSDx9UiPeWExXEeH6aoDvmihvx6jD5eLb4jbTaKGps)
7. [DAT](https://ipfs.io/ipfs/QmXHGmfo4sjdHVW2MAxczAfs44RCpSeva2an4QvkzqYgfR)
8. [go-cyber](https://github.com/cybercongress/go-cyber)
9. [cosmos-sdk](https://github.com/cosmos/cosmos-sdk)
10. [CIDv1](https://github.com/multiformats/cid#cidv1)
11. [cyber.page](http://cyber.page)
12. [DURA](https://github.com/cybercongress/cyb/blob/dev/docs/dura.md)
13. [Colony](https://ipfs.io/ipfs/QmZo7eY5UdJYotf3Z9GNVBGLjkCnE1j2fMdW2PgGCmvGPj)
14. [Truebit](https://ipfs.io/ipfs/QmTrxXp2xhB2zWGxhNoLgsztevqKLwpy5HwKjLjzFa7rnD)
15. [Thermodynamics of predictions](https://ipfs.io/ipfs/QmP81EcuNDZHQutvdcDjbQEqiTYUzU315aYaTyrVj6gtJb)
16. [PageRank](http://ipfs.io/ipfs/QmbuE2Pfcsiji1g9kzmmsCnptqPEn3BuN3BhnZHrPVsiVw)
17. [RFC-6962](https://ipfs.io/ipfs/QmZpJLmc3T2L1FLUxzvU3P8MBCPe15fEmUyVS7Bz8ZKMhG)
18. [IBC protocol](https://ipfs.io/ipfs/QmSGbrGAPZtR6Q1jHHe8mmS3bLBehKmfp9ZYvrg5ycaZuk)
19. [Tendermint](https://ipfs.io/ipfs/QmaMtD7xDgghqgjN62zWZ5TBGFiEjGQtuZBjJ9sMh816KJ)
20. [Comparison of web3 browsers](https://github.com/cybercongress/cyb/blob/master/docs/comparison.md)
21. [Cyb](https://cyb.ai)
22. [SpringRank](https://ipfs.io/ipfs/QmTJPJ55ePgR2MS1HoAtyqS1mteVLXUjAS4H8W97EEopxC)
23. [Run validator in cyber protocol](https://cybercongress.ai/docs/go-cyber/run_validator/)
24. [Top 10000 english words](https://github.com/first20hours/google-10000-english)
25. [Multilingual neural machine translation](https://ipfs.io/ipfs/QmQUWBhDMfPKgFt3NfbxM1VU22oU8CRepUzGPBDtopwap1)
26. [Foam](https://ipfs.io/ipfs/QmZYKGuLHf2h1mZrhiP2FzYsjj3tWt2LYduMCRbpgi5pKG)
27. [Coda](https://ipfs.io/ipfs/Qmdje3AmtsfjX9edWAxo3LFhV9CTAXoUvwGR7wHJXnc2Gk)
28. [Mimblewimble](https://ipfs.io/ipfs/Qmd99xmraYip9cVv8gRMy6Y97Bkij8qUYArGDME7CzFasg)
29. [Tezos](https://ipfs.io/ipfs/QmdSQ1AGTizWjSRaVLJ8Bw9j1xi6CGLptNUcUodBwCkKNS)
30. [Software 2.0](https://medium.com/@karpathy/software-2-0-a64152b37c35)
31. [Proof-of-history](https://ipfs.io/ipfs/QmbsKzizZVVVzPbZvg1qSsNMkwmA3MFufgXb3MFqbSnmPs)
32. [IPLD](https://github.com/ipld)
33. [cyber\~Congress organization](https://mainnet.aragon.org/#/cybercongress/0x4feb2bcc5907e7779130c093eef8fb44502c1330/)
34. [cyber~Congress in Cyber](https://cyber.page/network/cyber/contract/cyber1latzme6xf6s8tsrymuu6laf2ks2humqvdq39v8)
35. [cyber~Congress in Cosmos](https://www.mintscan.io/account/cosmos1latzme6xf6s8tsrymuu6laf2ks2humqv2tkd9a)
36. [multisig for CYB distribution](https://cyber.page/network/cyber/contract/cyber147drnke9676972jr3anklkj7pzgwjw47cp2u7j)
37. [.cyber](https://github.com/cybercongress/dot-cyber)

## Acknowledgements

1. @hleb-albau
2. @arturalbov
3. @jaekwon
4. @ebuchman
5. @npopeka
6. @belya
7. @serejandmyself


