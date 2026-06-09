# VidPartitionManager::Initialize(IVirtualMachine *,INumaManager *,IVpOperations *,IMemoryApertureCallback *,IGuestCallback *,void *,void *,Config::VmWorkerProcess::ProcessorSettings const &,Config::VmWorkerProcess::MemorySettings const &,_HV_PARTITION_CREATION_PROPERTIES_V2 const &,_HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES const &,_VMM_PARTITION_PROPERTIES const &)

- ea: `0x1402766ec`
- end: `0x14027928b`
- name: `?Initialize@VidPartitionManager@@AEAAJPEAUIVirtualMachine@@PEAUINumaManager@@PEAUIVpOperations@@PEAVIMemoryApertureCallback@@PEAUIGuestCallback@@PEAX5AEBUProcessorSettings@VmWorkerProcess@Config@@AEBUMemorySettings@89@AEBU_HV_PARTITION_CREATION_PROPERTIES_V2@@AEBT_HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES@@AEBU_VMM_PARTITION_PROPERTIES@@@Z`
- size: `11167`
- prototype: `__int64 __fastcall(VidPartitionManager *__hidden this, struct IVirtualMachine *, struct INumaManager *, struct IVpOperations *, struct IMemoryApertureCallback *, struct IGuestCallback *, void *, void *, const struct Config::VmWorkerProcess::ProcessorSettings *, const struct Config::VmWorkerProcess::MemorySettings *, const struct _HV_PARTITION_CREATION_PROPERTIES_V2 *, const union _HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES *, const struct _VMM_PARTITION_PROPERTIES *)`
- caller_count: `1`
- callee_count: `69`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140275d70`

## callees

- `0x14000d5a0`
- `0x14000d638`
- `0x14000d6e0`
- `0x14000d778`
- `0x14001e628`
- `0x140021d00`
- `0x140021fb8`
- `0x14002a1b0`
- `0x140031c88`
- `0x140042240`
- `0x14004c11c`
- `0x140051ad8`
- `0x14005348c`
- `0x140054508`
- `0x140054630`
- `0x140054af0`
- `0x14005606c`
- `0x14005611c`
- `0x1400586c4`
- `0x14005b628`
- `0x14005e7e4`
- `0x14005eca0`
- `0x140061dbc`
- `0x140066760`
- `0x140067f4c`
- `0x14006af38`
- `0x14006fec8`
- `0x140070bac`
- `0x140081778`
- `0x1400828dc`
- `0x1400996b8`
- `0x14009d7ac`
- `0x1400b2bd0`
- `0x1400c5a1c`
- `0x1400c5d24`
- `0x1400d4954`
- `0x1400dd7f4`
- `0x1400df740`
- `0x1400e7f4c`
- `0x1400e8cf4`
- `0x1400e8d20`
- `0x1400fe1bc`
- `0x14012f68c`
- `0x140132940`
- `0x140132cec`
- `0x1401335fc`
- `0x140135935`
- `0x140145294`
- `0x14014c5e8`
- `0x1401ded68`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140278eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027919b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140278eae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14027919b`
- `vid!VidOpenStatisticsHandle` at `0x1402767a7`
- `vid!VidOpenStatisticsHandle` at `0x1402767a7`
- `vid!VidGetSystemInformation` at `0x1402776f2`
- `vid!VidGetSystemInformation` at `0x1402776f2`
- `vid!VidGetSystemTopology` at `0x14027766c`
- `vid!VidGetSystemTopology` at `0x14027766c`
- `vid!VidQueryPartitionInformation` at `0x140278782`
- `vid!VidQueryPartitionInformation` at `0x140278782`
- `vid!VidSetPartitionProperty` at `0x1402784f7`
- `vid!VidSetPartitionProperty` at `0x1402784f7`
- `vid!VidGetPartitionPropertyEx` at `0x14027752a`
- `vid!VidGetPartitionPropertyEx` at `0x14027843d`
- `vid!VidGetPartitionPropertyEx` at `0x14027752a`
- `vid!VidGetPartitionPropertyEx` at `0x14027843d`
- `vid!VidCreatePartition` at `0x140278397`
- `vid!VidCreatePartition` at `0x140278397`
- `vid!VidSetPartitionFriendlyName` at `0x1402784c3`
- `vid!VidSetPartitionFriendlyName` at `0x1402784c3`
- `vid!VidAttachPartition` at `0x1402783b7`
- `vid!VidAttachPartition` at `0x1402783b7`

## string_xrefs

- `0x1402768bd`: `/configuration/global_settings/debug/channel_id`
- `0x140278f19`: `Failed to create partition. GetLastError=%d .\n`
- `0x140278e66`: `Failed to copy specified hosting process name suffix into the IOCTL buffer`
- `0x140278b5f`: `Physically backed VMs don't support deferred commit.`
- `0x140278b2d`: `Physically backed VMs don't support private compression stores.`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall VidPartitionManager::Initialize(
        VidPartitionManager *this,
        struct IVirtualMachine *a2,
        struct INumaManager *a3,
        struct IVpOperations *a4,
        struct IMemoryApertureCallback *a5,
        struct IGuestCallback *a6,
        void *a7,
        void *a8,
        const struct Config::VmWorkerProcess::ProcessorSettings *a9,
        const struct Config::VmWorkerProcess::MemorySettings *a10,
        const struct _HV_PARTITION_CREATION_PROPERTIES_V2 *a11,
        const union _HV_PARTITION_SYNTHETIC_PROCESSOR_FEATURES *a12,
        const struct _VMM_PARTITION_PROPERTIES *a13)
{
  HKEY v16; // r13
  __int64 v17; // rcx
  __int64 v18; // rax
  const char *v19; // r9
  __int64 v20; // rax
  int v21; // eax
  unsigned __int8 v22; // al
  __int64 v23; // r12
  int v24; // eax
  char v26; // al
  __int64 v27; // rdx
  __int64 v28; // r8
  const void *v29; // rdx
  unsigned int *v30; // r15
  gsl::details *v31; // rcx
  __int64 v32; // rdi
  __m128i v33; // xmm6
  gsl::details *v34; // rcx
  char *v35; // xmm6_8
  unsigned __int64 v36; // rax
  __m128i v37; // xmm6
  unsigned __int64 v38; // xmm6_8
  __int64 v39; // rax
  __int64 v40; // rdx
  gsl::details *v41; // rcx
  __int64 v42; // rbx
  __int64 v43; // rdi
  __int64 v44; // rsi
  __int64 v45; // rbx
  __int64 v46; // rax
  __int64 v47; // rbx
  unsigned int v48; // eax
  __int64 v49; // rdi
  int v50; // eax
  int v51; // eax
  int v52; // eax
  int v53; // eax
  __int64 v54; // r12
  __int64 v55; // rbx
  __int64 v56; // rax
  __int64 v57; // rax
  int v58; // edi
  __int64 v59; // rax
  __int64 v60; // rsi
  unsigned int v61; // edi
  __int64 v62; // rax
  __int64 v63; // rax
  unsigned int v64; // eax
  __int128 v65; // xmm6
  const struct Config::VmWorkerProcess::MemorySettings *v66; // rsi
  __int64 v67; // r12
  unsigned int v68; // edx
  int v69; // edx
  unsigned int v70; // eax
  __int64 *v71; // rbx
  __int64 v72; // rdx
  void (__fastcall *v73)(__int64 *, struct VmRepository **, _QWORD); // rdi
  unsigned int v74; // eax
  void *v75; // rbx
  const unsigned __int16 *v76; // r8
  VmPrefixRepository *v77; // rax
  struct VmRepository *v78; // rbx
  struct VmRepository *v79; // rdi
  __int64 v80; // rax
  __int64 v81; // r12
  __int64 v82; // rcx
  __int64 v83; // rax
  __int64 v84; // rcx
  __int64 v85; // rbx
  __int64 v86; // rax
  __int64 v87; // rcx
  __int64 v88; // rdi
  char v89; // bl
  unsigned __int64 v90; // rdi
  int SystemTopology; // esi
  __int64 v92; // rax
  const char *v93; // r9
  unsigned int v94; // eax
  struct IVpOperations *v95; // r12
  unsigned int v96; // ecx
  unsigned int v97; // esi
  __int64 v98; // rbx
  unsigned int v99; // ecx
  unsigned int v100; // esi
  __int64 v101; // rbx
  unsigned int v102; // ecx
  unsigned int v103; // esi
  __int64 v104; // rbx
  unsigned int v105; // ecx
  unsigned int v106; // esi
  __int64 v107; // rbx
  __int64 v108; // rbx
  __int64 v109; // rdi
  __int64 v110; // rbx
  __int64 v111; // rsi
  __int64 v112; // rdi
  __int64 v113; // rax
  unsigned int v114; // ecx
  unsigned int v115; // ebx
  const struct Config::VmWorkerProcess::MemorySettings *v116; // r12
  int v117; // ecx
  int v118; // ecx
  unsigned int v119; // ebx
  wchar_t *v120; // rax
  __int64 v121; // rcx
  char v122; // al
  __int64 v123; // rcx
  __int64 v124; // rsi
  __int64 v125; // rax
  unsigned __int64 v126; // rdx
  __int64 v127; // rcx
  unsigned int v128; // eax
  __int64 v129; // rcx
  __int64 v130; // rax
  __int64 v131; // r9
  const unsigned __int16 *v132; // r8
  int v133; // eax
  __int64 v134; // rbx
  struct IVirtualMachine *v135; // rbx
  char v136; // di
  char v137; // al
  char v138; // bl
  unsigned int v139; // ecx
  unsigned int v140; // r12d
  __int64 v141; // rbx
  char v142; // cl
  unsigned int v143; // ecx
  unsigned int v144; // edi
  __int64 v145; // rbx
  struct IVpOperations *v146; // rbx
  unsigned int v147; // ecx
  unsigned int v148; // edi
  __int64 v149; // rbx
  struct IVirtualMachine *v150; // rbx
  unsigned __int64 v151; // rdi
  unsigned int v152; // ecx
  unsigned int v153; // ebx
  __int64 v154; // rax
  unsigned int v155; // eax
  __int64 v156; // rbx
  __int64 v157; // rax
  int v158; // eax
  unsigned int v159; // ecx
  unsigned int v160; // edi
  VidPartitionManager *v161; // rdi
  __int64 v162; // rbx
  __int64 v163; // rax
  __int64 Partition; // rax
  void **v165; // rsi
  const char *v166; // r9
  const char *v167; // rdi
  unsigned __int8 *v168; // rcx
  unsigned __int64 v169; // r15
  unsigned __int64 i; // rbx
  const struct _VMM_PARTITION_PROPERTIES *v171; // r12
  __int64 v172; // rdi
  __int64 v173; // rax
  int v174; // eax
  const char *v175; // r9
  wil *v176; // rcx
  char *v177; // rbx
  unsigned int v178; // eax
  wil *v179; // rcx
  __int64 v180; // r15
  int Instance; // eax
  struct INumaManager *v182; // r15
  int v183; // eax
  const char *v184; // r9
  unsigned __int8 v185; // dl
  unsigned __int8 v186; // r8
  __int64 v187; // r9
  __int64 v188; // rcx
  unsigned __int8 j; // dl
  unsigned int v190; // r12d
  int v191; // r12d
  const struct _tlgProvider_t *v192; // rax
  int v193; // ebx
  void *v194; // rbx
  WorkerStatsPanel *v195; // rbx
  unsigned int v196; // edi
  const unsigned __int16 *v197; // r8
  const struct _GUID *v198; // r9
  int v199; // eax
  const char *v200; // r9
  __int64 result; // rax
  unsigned int v202; // eax
  unsigned int v203; // eax
  unsigned int v204; // eax
  unsigned int v205; // eax
  unsigned int v206; // eax
  unsigned int v207; // eax
  unsigned int v208; // eax
  unsigned int v209; // eax
  unsigned int v210; // eax
  unsigned int v211; // eax
  unsigned int v212; // eax
  unsigned int v213; // eax
  int v214; // edx
  unsigned int v215; // eax
  int v216; // edx
  unsigned int v217; // eax
  int v218; // edx
  const wchar_t *v219; // r8
  unsigned int v220; // eax
  unsigned int v221; // eax
  signed int LastError; // eax
  const struct _GUID *v223; // r8
  const unsigned __int16 *v224; // r9
  unsigned int v225; // esi
  unsigned int v226; // edi
  unsigned int v227; // eax
  const struct _tlgProvider_t *v228; // rax
  int v229; // ebx
  __int64 v230; // rax
  int v231; // r8d
  int v232; // r9d
  unsigned int v233; // eax
  const struct _tlgProvider_t *v234; // rax
  int v235; // esi
  __int64 v236; // rax
  int v237; // r8d
  int v238; // r9d
  unsigned int v239; // eax
  signed int v240; // eax
  unsigned int v241; // ebx
  const struct _tlgProvider_t *v242; // rax
  int v243; // edi
  __int64 v244; // rax
  int v245; // r8d
  int v246; // r9d
  unsigned int v247; // eax
  wil *v248; // rcx
  __int64 v249; // rax
  unsigned int v250; // eax
  unsigned int v251; // eax
  unsigned int v252; // ebx
  __int64 v253; // r9
  VidPartitionManager *v254; // rbx
  unsigned int v255; // ebx
  __int64 v256; // r9
  VidPartitionManager *v257; // rbx
  __int64 v258; // rax
  __int64 v259; // rax
  int v260; // [rsp+20h] [rbp-1898h]
  int v261; // [rsp+20h] [rbp-1898h]
  unsigned int v262; // [rsp+20h] [rbp-1898h]
  struct IVpOperations *v263; // [rsp+20h] [rbp-1898h]
  struct IVpOperations *v264; // [rsp+20h] [rbp-1898h]
  int v265; // [rsp+20h] [rbp-1898h]
  int v266; // [rsp+20h] [rbp-1898h]
  int v267; // [rsp+20h] [rbp-1898h]
  struct IMemoryApertureCallback *v268; // [rsp+28h] [rbp-1890h]
  struct IMemoryApertureCallback *v269; // [rsp+28h] [rbp-1890h]
  struct IGuestCallback *v270; // [rsp+30h] [rbp-1888h]
  unsigned __int8 v271; // [rsp+40h] [rbp-1878h] BYREF
  unsigned __int8 v272; // [rsp+41h] [rbp-1877h]
  __int64 v273; // [rsp+48h] [rbp-1870h] BYREF
  int v274; // [rsp+50h] [rbp-1868h]
  unsigned int v275; // [rsp+54h] [rbp-1864h] BYREF
  const struct _VMM_PARTITION_PROPERTIES *v276; // [rsp+58h] [rbp-1860h] BYREF
  struct INumaManager *v277; // [rsp+60h] [rbp-1858h]
  struct INumaManager *v278; // [rsp+68h] [rbp-1850h] BYREF
  VidPartitionManager *v279; // [rsp+70h] [rbp-1848h]
  struct IVpOperations *v280; // [rsp+78h] [rbp-1840h]
  unsigned int *v281; // [rsp+80h] [rbp-1838h]
  __int64 v282[2]; // [rsp+88h] [rbp-1830h] BYREF
  __int64 v283; // [rsp+98h] [rbp-1820h] BYREF
  __int64 v284; // [rsp+A0h] [rbp-1818h]
  VidPartitionManager *v285; // [rsp+A8h] [rbp-1810h]
  struct IVirtualMachine *v286; // [rsp+B0h] [rbp-1808h]
  struct IGuestCallback *v287; // [rsp+B8h] [rbp-1800h]
  const std::exception *v288; // [rsp+C0h] [rbp-17F8h] BYREF
  unsigned int HvCompatibilityVersion; // [rsp+C8h] [rbp-17F0h] BYREF
  unsigned int v290; // [rsp+CCh] [rbp-17ECh] BYREF
  unsigned __int8 v291; // [rsp+D0h] [rbp-17E8h] BYREF
  unsigned int v292; // [rsp+D4h] [rbp-17E4h] BYREF
  unsigned int v293; // [rsp+D8h] [rbp-17E0h] BYREF
  unsigned int v294; // [rsp+DCh] [rbp-17DCh] BYREF
  int v295; // [rsp+E0h] [rbp-17D8h] BYREF
  struct VmRepository *v296; // [rsp+E8h] [rbp-17D0h] BYREF
  __m128i v297; // [rsp+F0h] [rbp-17C8h] BYREF
  void *v298[2]; // [rsp+100h] [rbp-17B8h] BYREF
  __int128 v299; // [rsp+110h] [rbp-17A8h]
  __int128 v300; // [rsp+120h] [rbp-1798h]
  __int64 v301; // [rsp+130h] [rbp-1788h] BYREF
  const struct Config::VmWorkerProcess::MemorySettings *v302; // [rsp+138h] [rbp-1780h] BYREF
  HKEY phkResult; // [rsp+140h] [rbp-1778h] BYREF
  unsigned int v304; // [rsp+148h] [rbp-1770h] BYREF
  char *v305; // [rsp+150h] [rbp-1768h] BYREF
  __int128 v306; // [rsp+158h] [rbp-1760h] BYREF
  __int64 v307; // [rsp+168h] [rbp-1750h]
  __int128 v308; // [rsp+170h] [rbp-1748h] BYREF
  __int64 v309; // [rsp+180h] [rbp-1738h]
  __int128 v310; // [rsp+188h] [rbp-1730h] BYREF
  __int64 v311; // [rsp+198h] [rbp-1720h]
  _BYTE v312[24]; // [rsp+1A0h] [rbp-1718h] BYREF
  __int64 v313; // [rsp+1B8h] [rbp-1700h]
  __m128i v314; // [rsp+1C0h] [rbp-16F8h]
  __int128 v315; // [rsp+1D0h] [rbp-16E8h]
  __int64 v316; // [rsp+1E0h] [rbp-16D8h]
  __int64 v317; // [rsp+1E8h] [rbp-16D0h]
  int v318; // [rsp+1F0h] [rbp-16C8h]
  void *v319[2]; // [rsp+200h] [rbp-16B8h] BYREF
  void *v320[2]; // [rsp+210h] [rbp-16A8h] BYREF
  __int128 v321; // [rsp+220h] [rbp-1698h] BYREF
  __int64 v322; // [rsp+230h] [rbp-1688h]
  void *Src[2]; // [rsp+238h] [rbp-1680h] BYREF
  _DWORD v324[2]; // [rsp+250h] [rbp-1668h] BYREF
  _QWORD v325[509]; // [rsp+258h] [rbp-1660h]
  _BYTE v326[1536]; // [rsp+1240h] [rbp-678h] BYREF
  char *v327[2]; // [rsp+1840h] [rbp-78h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+18B8h] [rbp+0h]

  v280 = a4;
  v277 = a3;
  v286 = a2;
  v279 = this;
  v285 = this;
  v278 = a3;
  v273 = (__int64)a4;
  v287 = a6;
  v302 = a10;
  v276 = a13;
  v16 = (HKEY)((char *)this + 104);
  Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset((char *)this + 104);
  try
  {
    *((_BYTE *)this + 114) = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)a4 + 184LL))(a4) != 0;
    v18 = VidOpenStatisticsHandle(v17);
    *((_QWORD *)this + 10) = v18;
    if ( (unsigned __int64)(v18 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      v20 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
      v21 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v20 + 152LL))(v20);
      v281 = (unsigned int *)((char *)this + 88);
      *((_DWORD *)this + 22) = v21;
      v22 = lambda_997682190daf7855ab97ce0562d05e09_::operator()();
      v23 = v22;
      v271 = v22;
      v305 = 0;
      v294 = 0;
      v292 = 0;
      v301 = 0;
      (*(void (__fastcall **)(_QWORD, __int64 *))(**(_QWORD **)v16 + 56LL))(*(_QWORD *)v16, &v301);
      *(_OWORD *)v327 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v327, v301, 0);
      if ( SLODWORD(v327[1]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x161,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)LODWORD(v327[1]),
          v261);
      v24 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v301 + 288LL))(v301, &v294);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x166,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)(unsigned int)v24,
          v261);
      (*(void (__fastcall **)(__int64, const unsigned __int16 *, char **))(*(_QWORD *)v301 + 112LL))(
        v301,
        L"/configuration/global_settings/debug/channel_id",
        &v305);
      (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v301 + 320LL))(v301, &v292);
      memset(v312, 0, sizeof(v312));
      v313 = 0;
      v314 = 0u;
      v315 = 0;
      v316 = 0;
      v317 = 0;
      v318 = 0;
      if ( !*(_BYTE *)Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings,>(
                        v298,
                        &v301,
                        v312) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x170,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v261);
      std::vector<std::pair<std::wstring,enum Marshal::UnmarshalError>>::_Tidy(&v298[1]);
      v274 = v316;
      v275 = v316;
      if ( (unsigned int)v316 > 3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x175,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v261);
      if ( (_DWORD)v316 && (v294 < 0x903 || v292 != 1) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x17A,
          (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
          (const char *)0x80070057LL,
          v261);
      if ( !(_BYTE)v23 )
      {
        if ( (_DWORD)v316 != 3 || (v26 = 1, v294 >= 0xB00) )
          v26 = 0;
        if ( v26 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)0x80070057LL,
            v261);
      }
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v327);
      v284 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)a3 + 8LL))(a3);
      v283 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v284 + 88LL))(v284);
      v272 = *(_BYTE *)(v283 + 272);
      *((_BYTE *)this + 92) = v272;
      v310 = 0;
      v311 = 0;
      v306 = 0;
      v307 = 0;
      LOBYTE(v27) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
        v27);
      if ( *((_BYTE *)this + 114) )
      {
        if ( *((_WORD *)a13 + 8) )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(
            (__int64 *)&v306,
            (_OWORD *)a13 + 1);
        if ( *(_WORD *)a13 )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(
            (__int64 *)&v310,
            a13);
      }
      v308 = 0;
      v309 = 0;
      v28 = *((_QWORD *)a13 + 4);
      if ( v28 )
      {
        v29 = (const void *)*((_QWORD *)a13 + 8);
        if ( v29 )
          HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX>::InitializeFromBuffer(
            (__int64 *)&v308,
            v29,
            8 * v28 + 8);
      }
      v321 = 0;
      v322 = 0;
      std::vector<enum gsl::byte>::vector<enum gsl::byte>(
        (void **)&v321,
        *((_QWORD *)&v306 + 1) + *((_QWORD *)&v308 + 1) - v308 - v306 - v310 + *((_QWORD *)&v310 + 1) + 68704LL);
      *(_OWORD *)v298 = 0;
      gsl::span<unsigned char,-1>::span<unsigned char,-1>(v298, &v321);
      v30 = (unsigned int *)v298[1];
      v327[0] = (char *)v298[0];
      v327[1] = (char *)v298[1];
      if ( (unsigned __int64)gsl::span<unsigned char,-1>::size_bytes(v327) >= 0x10B40 )
      {
        gsl::span<unsigned char,-1>::size_bytes(v327);
        memset_0(v30, 0, 0x10B40u);
        v32 = (unsigned int)gsl::narrow<unsigned int,unsigned __int64,0>(68704);
        v327[0] = 0;
        v33 = *(__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(v298, v282, 68416, 288);
        v297 = v33;
        if ( (gsl::span<unsigned char,-1>::size_bytes(&v297) & 0xF) != 0
          || (v297 = v33,
              v35 = (char *)_mm_srli_si128(v33, 8).m128i_u64[0],
              v36 = gsl::span<unsigned char,-1>::size_bytes(&v297),
              gsl::details::extent_type<-1>::extent_type<-1>(v327, v36 >> 4),
              v327[1] = v35,
              v327[0] == (char *)-1LL)
          || !v35 && v327[0] )
        {
          gsl::details::terminate(v34);
          __debugbreak();
        }
        v297.m128i_i64[0] = 0;
        v37 = *(__m128i *)gsl::span<enum gsl::byte const,-1>::subspan(v298, v282, v32, -1);
        *(__m128i *)v298 = v37;
        gsl::span<unsigned char,-1>::size_bytes(v298);
        *(__m128i *)v298 = v37;
        v38 = _mm_srli_si128(v37, 8).m128i_u64[0];
        v39 = gsl::span<unsigned char,-1>::size_bytes(v298);
        gsl::details::extent_type<-1>::extent_type<-1>(&v297, v39);
        v297.m128i_i64[1] = v38;
        if ( v297.m128i_i64[0] == -1 || !v38 && v297.m128i_i64[0] )
        {
          gsl::details::terminate(v41);
          __debugbreak();
        }
        *(_QWORD *)v312 = v30;
        *(_OWORD *)&v312[8] = *(_OWORD *)v327;
        LODWORD(v313) = v32;
        v314 = v297;
        LOBYTE(v40) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl'::`2'::impl,
          v40);
        if ( *((_BYTE *)this + 114) )
        {
          if ( *((_QWORD *)&v306 + 1) != (_QWORD)v306 )
          {
            gsl::span<unsigned char,-1>::span<unsigned char,-1>(v298, &v306);
            PartitionConfigHelper::AddProperty((__int64)v312, 589831, (unsigned int *)v298);
          }
          if ( *((_QWORD *)&v310 + 1) != (_QWORD)v310 )
          {
            gsl::span<unsigned char,-1>::span<unsigned char,-1>(v298, &v310);
            PartitionConfigHelper::AddProperty((__int64)v312, 589833, (unsigned int *)v298);
          }
        }
        if ( *((_QWORD *)&v308 + 1) != (_QWORD)v308 )
        {
          gsl::span<unsigned char,-1>::span<unsigned char,-1>(v298, &v308);
          PartitionConfigHelper::AddProperty((__int64)v312, 589838, (unsigned int *)v298);
        }
        v42 = (v23 << 32) | 2;
        if ( (*(unsigned int (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 24LL))(v277) )
          v42 = v23 << 32;
        v43 = v42 | 0x40000000;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 216LL))(*(_QWORD *)v16) )
          v43 = v42;
        v44 = v43 | 0x4000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 224LL))(*(_QWORD *)v16) )
          v44 = v43;
        v45 = v44 | 0x2000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 336LL))(*(_QWORD *)v16) )
          v45 = v44;
        if ( (*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 344LL))(*(_QWORD *)v16) )
        {
          if ( v294 < 0xC04 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x22A,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)0x80070057LL,
              v261);
          v45 |= 0x40000000000000uLL;
        }
        v46 = v45 | 0x400;
        if ( !*((_BYTE *)a9 + 121) )
          v46 = v45;
        v47 = v46 | 0x100000;
        if ( !*((_BYTE *)a9 + 248) )
          v47 = v46;
        if ( *((_BYTE *)a9 + 256) )
          v48 = *((_DWORD *)a9 + 63);
        else
          v48 = 0;
        v30[11] = v48;
        v49 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
        v290 = 0;
        v50 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 88LL))(v49, &v290);
        if ( v50 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x243,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v50,
            v261);
        v30[16956] &= 0xFFFFFFF0;
        v30[16956] |= v290 & 0xF;
        v293 = 0;
        v51 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 96LL))(v49, &v293);
        if ( v51 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x247,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v51,
            v261);
        if ( v293 )
          v47 |= 8uLL;
        v295 = 0;
        v52 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 112LL))(v49, &v295);
        if ( v52 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x24E,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v52,
            v261);
        if ( v295 )
          v47 |= 0x10uLL;
        HvCompatibilityVersion = 0;
        v53 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v49 + 136LL))(
                v49,
                &HvCompatibilityVersion);
        if ( v53 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x255,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v53,
            v261);
        if ( HvCompatibilityVersion )
          v47 |= 0x80uLL;
        v54 = v47 | 0x80000000000000LL;
        if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 352LL))(*(_QWORD *)v16) )
          v54 = v47;
        if ( (v30[16956] & 0xF) - 2 > 2 )
          goto LABEL_82;
        *((_QWORD *)v30 + 8479) = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 264LL))(*(_QWORD *)v16);
        v55 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 272LL))(*(_QWORD *)v16);
        HvCompatibilityVersion = 0;
        v56 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
        (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v56 + 88LL))(v56, &HvCompatibilityVersion);
        if ( HvCompatibilityVersion == 3 )
        {
          v295 = 0;
          *(_OWORD *)v298 = 0;
          v299 = 0;
          v300 = 0;
          VidPartitionManager::CalculateMaxmimumTdxMigrationStreamCount(v279);
          *(_OWORD *)v298 = 0;
          v299 = 0;
          v300 = 0;
          v57 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
          (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v57 + 144LL))(v57, &v295);
          v58 = v295;
          v59 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
          if ( (*(unsigned int (__fastcall **)(__int64, void **))(*(_QWORD *)v59 + 432LL))(v59, v298) )
          {
            if ( !v58 )
            {
              v60 = v30[17098];
              v30[17098] = v60 + 1;
              v61 = *((_DWORD *)v279 + 78);
              v62 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
              if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v62 + 464LL))(v62) )
              {
                v63 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
                v64 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v63 + 472LL))(v63);
                if ( v61 < v64 )
                  v61 = v64;
              }
              v55 |= 4uLL;
              *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v60) = 327727;
              *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v60) + 8) = v61 + 1;
              goto LABEL_81;
            }
            if ( v58 != 1 )
            {
              v202 = wil::verify_hresult<long>(2147942487LL);
              LODWORD(v268) = v58;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x2B2,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v202,
                (int)"Unknown TDX migratable policy %u",
                (const char *)v268);
            }
          }
          v55 &= ~4uLL;
        }
LABEL_81:
        *((_QWORD *)v30 + 8480) = v55;
LABEL_82:
        v295 = v313;
        v65 = 0;
        v66 = v302;
        if ( (unsigned __int64)(*((_QWORD *)v302 + 5) - 2LL) <= 1 )
        {
          if ( *((_BYTE *)v302 + 160) )
          {
            v68 = v30[12] ^ (v30[12] ^ (*((_DWORD *)v302 + 38) << 11)) & 0x7800;
          }
          else
          {
            v69 = 18432;
            if ( *((_QWORD *)v302 + 23) != 512 )
              v69 = 0x2000;
            v68 = v30[12] & 0xFFFF87FF | v69;
          }
          v30[12] = v68;
          if ( *((_BYTE *)v66 + 176) )
            v70 = v68 ^ (v68 ^ (*((_DWORD *)v66 + 42) << 15)) & 0x78000;
          else
            v70 = v68 & 0xFFF87FFF | 0x20000;
          v30[12] = v70;
          v296 = 0;
          v71 = *(__int64 **)v16;
          v72 = **(_QWORD **)v16;
          v73 = *(void (__fastcall **)(__int64 *, struct VmRepository **, _QWORD))(v72 + 160);
          v74 = (*(__int64 (__fastcall **)(_QWORD))(v72 + 64))(*(_QWORD *)v16);
          v73(v71, &v296, v74);
          if ( v296 )
          {
            v75 = operator new(0x80u);
            v298[0] = v75;
            memset_0(v75, 0, 0x80u);
            v77 = VmPrefixRepository::VmPrefixRepository((VmPrefixRepository *)v75, v296, v76);
            v78 = v77;
            v79 = v296;
            if ( v77 )
              Vml::VmSharableObject::IncrementUserCount((VmPrefixRepository *)((char *)v77 + 8));
            v296 = v78;
            if ( v79 )
            {
              Vml::VmSharableObject::DecrementUserCount((struct VmRepository *)((char *)v79 + 8));
              v78 = v296;
            }
            if ( v78 )
            {
              v80 = MemoryManager::RestoreCloneTemplateId(&MemoryManager::m_Instance, v298, v78);
              if ( *(_BYTE *)(v80 + 16) )
                v65 = *(_OWORD *)v80;
            }
          }
          v81 = v54 | 0x8000000000100LL;
          v82 = v81 | 0x1000;
          if ( !*((_BYTE *)v66 + 313) )
            v82 = v81;
          v83 = v82 | 0x2000;
          if ( !*((_BYTE *)v66 + 314) )
            v83 = v82;
          v84 = v83 | 0x4000;
          if ( !*((_BYTE *)v66 + 315) )
            v84 = v83;
          v85 = v84 | 0x20000;
          if ( !*((_BYTE *)v66 + 316) )
            v85 = v84;
          if ( *((_BYTE *)v66 + 317) )
          {
            memset_0(v324, 0, 0xFE8u);
            if ( (unsigned int)VidGetPartitionPropertyEx(-1, 589831, 0, v324, 4072) && (v325[0] & 0x100) == 0 )
              wil::details::in1diag3::Throw_Win32(
                retaddr,
                (void *)0x314,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)0x32,
                v262);
            v85 |= 0x20000000010000uLL;
          }
          v86 = v85 | 0x8000;
          if ( !*((_BYTE *)v66 + 144) )
            v86 = v85;
          v87 = v86 | 0x40000;
          if ( !*((_BYTE *)v66 + 145) )
            v87 = v86;
          v88 = v87 | 0x400000;
          if ( !*((_BYTE *)v66 + 208) )
            v88 = v87;
          v89 = *((_BYTE *)v66 + 209);
          Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v296);
          v67 = v88 | 0x200000;
          if ( !v89 )
            v67 = v88;
        }
        else
        {
          if ( *((_BYTE *)v302 + 160) || *((_BYTE *)v302 + 176) )
          {
            v210 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x344,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v210,
              (int)"Physically backed VMs don't support fault clustering.",
              (const char *)v268);
          }
          if ( *((_BYTE *)v302 + 313) || *((_BYTE *)v302 + 314) || *((_BYTE *)v302 + 315) )
          {
            v209 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x34D,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v209,
              (int)"Physically backed VMs don't support memory heat hints.",
              (const char *)v268);
          }
          if ( *((_BYTE *)v302 + 316) )
          {
            v203 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x354,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v203,
              (int)"Physically backed VMs don't support EPF.",
              (const char *)v268);
          }
          if ( *((_BYTE *)v302 + 317) )
          {
            v204 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x35B,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v204,
              (int)"Physically backed VMs don't support GPA pinning.",
              (const char *)v268);
          }
          if ( *((_BYTE *)v302 + 144) )
          {
            v205 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x362,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v205,
              (int)"Physically backed VMs don't support private compression stores.",
              (const char *)v268);
          }
          if ( *((_BYTE *)v302 + 145) )
          {
            v206 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x369,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v206,
              (int)"Physically backed VMs don't support deferred commit.",
              (const char *)v268);
          }
          if ( *((_BYTE *)v302 + 208) )
          {
            v207 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x370,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v207,
              (int)"Physically backed VMs don't support pinning.",
              (const char *)v268);
          }
          v67 = v54 | 0x10000;
          if ( *((_BYTE *)v302 + 209) )
          {
            v208 = wil::verify_hresult<long>(3224829998LL);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x377,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v208,
              (int)"Physically backed VMs don't support direct mapped images.",
              (const char *)v268);
          }
        }
        v90 = v67 & 0xFFDFFFFFFFFEFFFFuLL;
        if ( (v30[16956] & 0xF) != 1 )
          v90 = v67;
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 64LL))(*(_QWORD *)v16) )
        {
          v90 |= 0x800u;
          if ( *(_BYTE *)((*(__int64 (__fastcall **)(_QWORD, void **))(**(_QWORD **)v16 + 408LL))(*(_QWORD *)v16, v298)
                        + 9) )
            v90 |= 0x20000000000uLL;
        }
        if ( v305 )
          v90 |= 1u;
        v291 = 64;
        v304 = 0;
        v270 = (struct IGuestCallback *)&v291;
        v269 = (struct IMemoryApertureCallback *)v326;
        v263 = 0;
        SystemTopology = VidGetSystemTopology(*((_QWORD *)v279 + 10), 0, &v304, 0);
        LODWORD(v296) = SystemTopology;
        v92 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 8LL))(v277);
        if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v92 + 312LL))(v92) <= 1 )
        {
          if ( !*((_BYTE *)v279 + 114) )
          {
            HvCompatibilityVersion = 0;
            v270 = 0;
            LODWORD(v269) = 4;
            v263 = (struct IVpOperations *)&HvCompatibilityVersion;
            if ( !(unsigned int)VidGetSystemInformation(*((_QWORD *)v279 + 10), 1, 0) )
              wil::details::in1diag3::Throw_GetLastError(
                retaddr,
                (void *)0x3BC,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                v93);
            if ( HvCompatibilityVersion == 3 )
            {
              phkResult = 0;
              v290 = 0;
              v293 = 0;
              Vml::VmRegistryKey::Open(
                &phkResult,
                HKEY_LOCAL_MACHINE,
                L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
                0x20019u);
              if ( !Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"NoAutomaticSmtEnablement", &v290) )
                v290 = v271 != 0;
              if ( Vml::VmRegistryKey::QueryValue((Vml::VmRegistryKey *)&phkResult, L"ForceSmtEnablement", &v293) )
              {
                v94 = v293;
              }
              else
              {
                v94 = 0;
                v293 = 0;
              }
              if ( v94 || SystemTopology && !v290 && *v281 > v304 )
              {
                v90 |= 0x800000000uLL;
                v282[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 8LL))(*(_QWORD *)v16 + 16LL);
                v297.m128i_i64[0] = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
                VmEventWrite<unsigned short const *,unsigned short const *>(
                  &MSVML_WP_WARN_SMT_AUTO_ENABLED,
                  1u,
                  (__int64)v282);
              }
              Vml::VmRegistryKey::Close((Vml::VmRegistryKey *)&phkResult);
            }
          }
        }
        else
        {
          v90 |= 0x20u;
        }
        v95 = v280;
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v280 + 160LL))(v280) )
        {
          if ( v292 >= 2 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Only generation 1 and generation 2 VMs support nested virtualization");
            v211 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v269) = v292;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x3F8,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v211,
              (int)"virtualSystemSubType = %u",
              (const char *)v269,
              v270);
          }
          v90 |= 0x40u;
        }
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v280 + 184LL))(v280) )
        {
          if ( v292 != 1 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Only generation 2 VMs support hierarchical virtualization");
            v212 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v269) = v292;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x40B,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v212,
              (int)"virtualSystemSubType = %u",
              (const char *)v269,
              v270);
          }
          v96 = v30[17098];
          v30[17098] = v96 + 1;
          v97 = v96;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v96) = 524545;
          v98 = (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 384LL))(*(_QWORD *)v16);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v97) + 8) = v98;
          v99 = v30[17098];
          v30[17098] = v99 + 1;
          v100 = v99;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v99) = 524546;
          v101 = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 192LL))(v95);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v100) + 8) = v101;
          if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 392LL))(*(_QWORD *)v16) )
          {
            v102 = v30[17098];
            v30[17098] = v102 + 1;
            v103 = v102;
            *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v102) = 131077;
            v104 = (*(int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 392LL))(*(_QWORD *)v16);
            *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v103) + 8) = v104;
          }
          v90 |= 0x10000000000000uLL;
          v105 = v30[17098];
          v30[17098] = v105 + 1;
          v106 = v105;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v105) = 327718;
          (*(void (__fastcall **)(_QWORD, __m128i *))(**(_QWORD **)v16 + 400LL))(*(_QWORD *)v16, &v297);
          v107 = v297.m128i_i64[0];
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v106) + 8) = v107;
        }
        v108 = v90 | 0x1000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 200LL))(v95) )
          v108 = v90;
        v109 = v108 | 0x1000000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 208LL))(v95) )
          v109 = v108;
        v110 = v109 | 0x2000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 216LL))(v95) )
          v110 = v109;
        v111 = v110 | 0x4000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 224LL))(v95) )
          v111 = v110;
        v112 = v111 | 0x8000000000LL;
        if ( !(*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 232LL))(v95) )
          v112 = v111;
        if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 72LL))(v277) )
        {
          if ( *v281 > 0xF0 )
          {
            v213 = wil::verify_hresult<long>(2147942450LL);
            LODWORD(v269) = v214;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x473,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v213,
              (int)"Maximum processor count limit exceeded for legacy apic mode(%d).",
              (const char *)v269,
              v270);
          }
          v112 |= 0x40000000000uLL;
        }
        else if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 80LL))(v277) )
        {
          v112 |= 0x80000000000uLL;
          v113 = (*(__int64 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 8LL))(v277);
          if ( (unsigned __int64)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v113 + 352LL))(v113) >= 0xF0 )
            v112 |= 0x400000000000uLL;
        }
        if ( (*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 88LL))(v277) )
        {
          v114 = v30[17098];
          v30[17098] = v114 + 1;
          v115 = v114;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v114) = 327716;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v115) + 8) = 1;
        }
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v95 + 240LL))(v95) )
          v112 |= 0x100000000000uLL;
        if ( v294 >= 0x800 && v292 != 1 )
          v112 |= 0x80uLL;
        if ( v292 )
          v112 |= 0x100000000000000uLL;
        v116 = v302;
        if ( *((_BYTE *)v302 + 256) )
        {
          if ( v294 < (v271 ^ 1u) + 2048 || v292 != 1 )
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
            {
              v219 = L"RS1";
              if ( !v271 )
                v219 = L"RS2";
              VmlDebugTrace(16416, L"Only generation 2 %s VMs support SGX", v219);
            }
            v220 = wil::verify_hresult<long>(2147778582LL);
            LODWORD(v270) = v292;
            LODWORD(v269) = v294;
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x4C0,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v220,
              (int)"VM version %x (subtype %u) does not support SGX.",
              (const char *)v269,
              v270);
          }
          v112 |= 0x200uLL;
          v117 = *((_DWORD *)v302 + 68);
          if ( v117 )
          {
            v118 = v117 - 1;
            if ( v118 )
            {
              if ( v118 != 1 )
              {
                v215 = wil::verify_hresult<long>(2147942487LL);
                LODWORD(v269) = v216;
                wil::details::in1diag3::Throw_HrMsg(
                  retaddr,
                  (void *)0x4D6,
                  (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                  (const char *)v215,
                  (int)"LaunchControlMode = %u",
                  (const char *)v269,
                  v270);
              }
              v112 |= 0x18000000uLL;
            }
            else
            {
              v112 |= 0x8000000uLL;
            }
          }
          if ( *((_QWORD *)v302 + 37) )
          {
            if ( *((_QWORD *)v302 + 37) != 64 )
            {
              NumaManager::GetRequestedNumaNodeMask((const struct Config::VmWorkerProcess::MemorySettings *)((char *)v302 + 280));
              v217 = wil::verify_hresult<long>(2147942487LL);
              LODWORD(v269) = v218;
              wil::details::in1diag3::Throw_HrMsg(
                retaddr,
                (void *)0x4E9,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v217,
                (int)"defaultString.size() = %u",
                (const char *)v269,
                v270);
            }
            v119 = 0;
            while ( 1 )
            {
              HvCompatibilityVersion = v119;
              if ( v119 >= 4 )
                break;
              try
              {
                v120 = (wchar_t *)std::wstring::substr((char *)v116 + 280, v298, 16 * v119, 16, v263);
                *(_QWORD *)&v30[2 * v119 + 16948] = _byteswap_uint64(std::stoull(v120));
                std::wstring::_Tidy_deallocate(v298);
                ++v119;
              }
              catch ( const std::exception *v288 )
              {
                if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
                {
                  v249 = (*(__int64 (__fastcall **)(const std::exception *))(*(_QWORD *)v288 + 8LL))(v288);
                  VmlDebugTrace(
                    16416,
                    L"Invalid SGX launch control default string (MSR %u): %S",
                    HvCompatibilityVersion,
                    v249);
                }
                v250 = wil::ResultFromCaughtException(v248);
                v251 = wil::verify_hresult<long>(v250);
                wil::details::in1diag3::Throw_Hr(
                  retaddr,
                  (void *)0x4FC,
                  (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                  (const char *)v251,
                  v260);
              }
            }
            v112 |= 0x20000000uLL;
          }
        }
        phkResult = v16;
        v121 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 424LL))(*(_QWORD *)v16);
        v122 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v121 + 800LL))(v121);
        v123 = v112 | 0x800000000000LL;
        if ( !v122 )
          v123 = v112;
        v124 = v123 | 0x80000;
        if ( !*((_BYTE *)v116 + 192) )
          v124 = v123;
        v125 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 424LL))(*(_QWORD *)v16);
        if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v125 + 480LL))(v125) )
        {
          v30[12] |= 0x180u;
          v128 = v30[12] | 0x600;
        }
        else
        {
          v30[12] ^= (v30[12]
                    ^ ((unsigned int)lambda_0242864c6572879e96253374616fb0b4_::operator()(v127, *((_QWORD *)v116 + 23)) << 7))
                   & 0x180;
          v128 = v30[12]
               ^ (v30[12]
                ^ ((unsigned int)lambda_0242864c6572879e96253374616fb0b4_::operator()(v129, *((_QWORD *)v116 + 25)) << 9))
               & 0x600;
        }
        v30[12] = v128;
        if ( (v128 & 0x600) == 0 && *((_QWORD *)v116 + 5) == 1 )
        {
          v130 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 48LL))(*(_QWORD *)v16);
          if ( (*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v130 + 392LL))(v130) )
            v30[12] |= 0x600u;
        }
        v131 = *((_QWORD *)v116 + 29);
        if ( v131 )
        {
          v132 = (const unsigned __int16 *)((char *)v116 + 216);
          if ( *((_QWORD *)v116 + 30) > 7u )
            v132 = *(const unsigned __int16 **)v132;
          v133 = StringCbCopyNW((unsigned __int16 *)v30 + 33924, v126, v132, 2 * v131);
          if ( v133 < 0 )
          {
            v221 = wil::verify_hresult<long>((unsigned int)v133);
            wil::details::in1diag3::Throw_HrMsg(
              retaddr,
              (void *)0x56E,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v221,
              (int)"Failed to copy specified hosting process name suffix into the IOCTL buffer",
              (const char *)v269,
              v270);
          }
        }
        v134 = v284;
        v282[0] = v284;
        HvCompatibilityVersion = VidPartitionManager::GetHvCompatibilityVersion(v127, v294);
        *(_OWORD *)Src = 0;
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v134 + 104LL))(v134, Src);
        *(_OWORD *)v319 = 0;
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v134 + 112LL))(v134, v319);
        *(_OWORD *)v320 = 0;
        (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v134 + 120LL))(v134, v320);
        if ( (v30[16956] & 0xF) == 2 )
        {
          v135 = v286;
          v136 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v286 + 248LL))(v286);
          v137 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v135 + 256LL))(v135);
          v138 = v137;
          if ( v136 || v137 )
          {
            if ( !(*(unsigned __int8 (__fastcall **)(struct INumaManager *))(*(_QWORD *)v277 + 80LL))(v277) )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x589,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)0x80070057LL,
                (int)v263);
            v124 |= 0x400000000000uLL;
            if ( v138 )
            {
              v30[16956] |= 0xC0u;
            }
            else if ( v136 )
            {
              v30[16956] &= ~0x80u;
              v30[16956] |= 0x40u;
            }
          }
        }
        v298[0] = v281;
        v139 = *v281;
        v30[10] = *v281;
        v140 = v272;
        v290 = v272;
        v293 = v272;
        v30[12] ^= (v30[12] ^ v272) & 0x7F;
        *((_QWORD *)v30 + 4) = v124;
        *v30 = HvCompatibilityVersion;
        *(_OWORD *)(v30 + 2) = *(_OWORD *)a11;
        *((_QWORD *)v30 + 3) = *((_QWORD *)a11 + 2);
        v141 = v283;
        memcpy_0(v30 + 46, (const void *)(v283 + 344), v139);
        memcpy_0(v30 + 558, Src[1], 8LL * v30[10]);
        if ( v319[0] )
          memcpy_0(v30 + 4654, v319[1], 16LL * v30[10]);
        if ( v320[0] )
        {
          memcpy_0(v30 + 12847, v320[1], 8LL * v30[10]);
          v142 = 1;
        }
        else
        {
          v142 = 0;
        }
        *((_BYTE *)v30 + 51384) = v142;
        memcpy_0(v30 + 13, (const void *)(v141 + 280), v30[12] & 0x7F);
        memcpy_0(v30 + 29, (const void *)(v141 + 2392), v30[12] & 0x7F);
        *((_OWORD *)v30 + 4236) = v65;
        v30[17099] = 68416;
        v143 = v30[17098];
        v30[17098] = v143 + 1;
        v144 = v143;
        *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v143) = 65537;
        v145 = *(_QWORD *)a12;
        *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v144) + 8) = v145;
        v146 = v280;
        if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v280 + 168LL))(v280) )
        {
          v147 = v30[17098];
          v30[17098] = v147 + 1;
          v148 = v147;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v147) = 524289;
          v149 = (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v146 + 176LL))(v146);
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v148) + 8) = v149;
          if ( (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v280 + 184LL))(v280)
            && (*(unsigned int (__fastcall **)(struct IVpOperations *))(*(_QWORD *)v280 + 176LL))(v280) )
          {
            v30[16956] |= 0x20u;
          }
          else
          {
            v30[16956] |= 0x10u;
          }
        }
        v150 = v286;
        if ( (*(unsigned __int8 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v286 + 216LL))(v286)
          && (v30[16956] & 0xF) - 2 > 2 )
        {
          v302 = 0;
          (*(void (__fastcall **)(_QWORD, _QWORD, const struct Config::VmWorkerProcess::MemorySettings **))(**(_QWORD **)v16 + 288LL))(
            *(_QWORD *)v16,
            0,
            &v302);
          v151 = (((unsigned __int64)v302 + 511) >> 9) + 512;
          v152 = v30[17098];
          v30[17098] = v152 + 1;
          v153 = v152;
          *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v152) = 327713;
          *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v153) + 8) = v151;
          v150 = v286;
        }
        v154 = (*(__int64 (__fastcall **)(struct IVirtualMachine *))(*(_QWORD *)v150 + 48LL))(v150);
        v155 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v154 + 240LL))(v154);
        v156 = v155;
        if ( v155 )
        {
          HvCompatibilityVersion = 0;
          v157 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 448LL))(*(_QWORD *)v16);
          v158 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v157 + 88LL))(
                   v157,
                   &HvCompatibilityVersion);
          if ( v158 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x618,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)(unsigned int)v158,
              (int)v263);
          if ( HvCompatibilityVersion != 3 )
          {
            v159 = v30[17098];
            v30[17098] = v159 + 1;
            v160 = v159;
            *(_DWORD *)gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v159) = 393222;
            *(_QWORD *)(gsl::span<_HV_PARTITION_PROPERTY_ASSOC,-1>::operator[](v327, v160) + 8) = v156;
          }
        }
        if ( a7 != (void *)-1LL )
          *((_QWORD *)v30 + 8547) = a7;
        *((_QWORD *)v30 + 8548) = a8;
        v161 = v279;
        *((_QWORD *)v279 + 12) = v124;
        v30[17100] = v295 - 68416;
        v162 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
        v163 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 8LL))(*(_QWORD *)v16 + 16LL);
        Partition = VidCreatePartition(v163, v162, v30);
        v165 = (void **)((char *)v161 + 56);
        *((_QWORD *)v161 + 7) = Partition;
        if ( Partition == -1 )
        {
          LastError = GetLastError();
          v225 = LastError;
          if ( (LastError & 0x1FFF0000) != 0 )
          {
            v226 = LastError;
            if ( LastError > 0 )
              v226 = LastError & 0xFFFFFFF | 0x80000000;
          }
          else if ( LastError > 0 )
          {
            v226 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v226 = LastError;
          }
          if ( LastError == -1070264320 )
          {
            VmEventWriteAndReport(&MSVML_WP_INIT_HYPERVISOR_NOT_RUNNING_ERROR, 5u, v223, v224);
          }
          else
          {
            if ( (unsigned int)VmlIsDebugTraceEnabled(16416) )
              VmlDebugTrace(16416, L"Failed to create partition. GetLastError=%d .\n", v225);
            _snwprintf_s<16>(v298, 16, L"%%%%%u", v226 & 0xEFFFFFFF, v263, v269, v270);
            _snwprintf_s<16>(v327, 16, L"0x%08X", v226 & 0xEFFFFFFF);
            VmEventWriteAndReport<unsigned short (&)[16],unsigned short (&)[16]>(
              (struct _EVENT_DESCRIPTOR *)&MSVML_WP_INIT_CREATE_PARTITION_ERROR,
              (__int64)v298,
              (unsigned __int16 *)v327);
          }
          v227 = wil::verify_hresult<long>(v226);
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x652,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)v227,
            (int)v263);
        }
        if ( !(unsigned int)VidAttachPartition(Partition) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x655,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            v166);
        v302 = (VidPartitionManager *)((char *)v161 + 56);
        if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v16 + 64LL))(*(_QWORD *)v16) )
        {
          if ( *((_QWORD *)v276 + 4) > 2u )
          {
            if ( *((_QWORD *)v276 + 8) )
            {
              memset_0(v324, 0, 0xFE8u);
              if ( (unsigned int)VidGetPartitionPropertyEx(*v165, 589840, 0, v324, 4072) )
              {
                v167 = (const char *)LOBYTE(v324[0]);
                v168 = (unsigned __int8 *)*((_QWORD *)v276 + 8);
                v169 = *v168;
                if ( LOBYTE(v324[0]) != v169 )
                {
                  v228 = VmWorkerTrace::Provider();
                  v229 = (int)v228;
                  if ( *(_DWORD *)v228 > 2u && (unsigned __int8)tlgKeywordOn(v228, 0) )
                  {
                    v276 = (const struct _VMM_PARTITION_PROPERTIES *)v169;
                    v297.m128i_i64[0] = (__int64)v167;
                    v230 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v16);
                    v282[0] = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v230 + 16) + 16LL))(v230 + 16);
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                      v229,
                      (unsigned int)&word_140360A2E,
                      v231,
                      v232,
                      (__int64)v282,
                      (__int64)&v297,
                      (__int64)&v276);
                  }
                  v233 = wil::verify_hresult<long>(2147549183LL);
                  wil::details::in1diag3::Throw_HrMsg(
                    retaddr,
                    (void *)0x67C,
                    (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                    (const char *)v233,
                    (int)"Processor features bank count mismatch Hypervisor visible bank count=%zu, Worker visible bank count=%zu",
                    v167,
                    v169);
                }
                for ( i = 2; i < v169; ++i )
                {
                  v171 = (const struct _VMM_PARTITION_PROPERTIES *)v325[i];
                  v172 = ~*(_QWORD *)&v168[8 * i + 8];
                  if ( ((unsigned __int64)v171 & v172) != v172 )
                  {
                    v234 = VmWorkerTrace::Provider();
                    v235 = (int)v234;
                    if ( *(_DWORD *)v234 > 2u )
                    {
                      if ( (unsigned __int8)tlgKeywordOn(v234, 0) )
                      {
                        v276 = v171;
                        v297.m128i_i64[0] = v172;
                        v282[0] = i;
                        v236 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v16);
                        v283 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v236 + 16) + 16LL))(v236 + 16);
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
                          v235,
                          (unsigned int)&unk_140360830,
                          v237,
                          v238,
                          (__int64)&v283,
                          (__int64)v282,
                          (__int64)&v297,
                          (__int64)&v276);
                      }
                    }
                    v239 = wil::verify_hresult<long>(2147549183LL);
                    wil::details::in1diag3::Throw_HrMsg(
                      retaddr,
                      (void *)0x69F,
                      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                      (const char *)v239,
                      (int)"Processor features bank %zu: expected enabled features are not a subset of actual enabled fea"
                           "tures. expected enabled=0x%llx, actual enabled=0x%llx",
                      (const char *)i,
                      v172,
                      v171);
                  }
                }
                v140 = v290;
                v161 = v279;
              }
            }
          }
        }
        VidPartitionManager::FreezeTime(v161);
        try
        {
          v173 = (**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
          v174 = VidSetPartitionFriendlyName(*v165, v173);
          v176 = retaddr;
          if ( !v174 )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x6AF,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              v175);
        }
        catch ( ... )
        {
          v255 = wil::ResultFromCaughtException(v176);
          v256 = v255;
          LODWORD(v256) = v255 & 0xEFFFFFFF;
          _snwprintf_s<16>(v327, 16, L"%%%%%u", v256);
          _snwprintf_s<16>(v312, 16, L"0x%08X", v255 & 0xEFFFFFFF);
          v257 = v285;
          v258 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->((char *)v285 + 104);
          v273 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v258 + 16) + 8LL))(v258 + 16);
          v259 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->((char *)v257 + 104);
          v278 = (struct INumaManager *)(**(__int64 (__fastcall ***)(__int64))(v259 + 16))(v259 + 16);
          VmEventWriteAndReport<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
            (struct _EVENT_DESCRIPTOR *)&MSVML_WP_SET_PARTITION_PROP_ERROR,
            5u,
            (__int64)&v278,
            (__int64)&v273,
            (__int64)v327,
            (__int64)v312);
          throw;
        }
        v177 = v305;
        if ( v305 )
        {
          v178 = VidSetPartitionProperty(*v165, 262147, v305);
          try
          {
            wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
              retaddr,
              (void *)0x6D1,
              (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
              (const char *)v178,
              (int)"channelId = %I64u",
              v177);
          }
          catch ( ... )
          {
            v252 = wil::ResultFromCaughtException(v179);
            v253 = v252;
            LODWORD(v253) = v252 & 0xEFFFFFFF;
            _snwprintf_s<16>(v312, 16, L"%%%%%u", v253);
            _snwprintf_s<16>(v327, 16, L"0x%08X", v252 & 0xEFFFFFFF);
            v254 = v285;
            v276 = (const struct _VMM_PARTITION_PROPERTIES *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v285 + 13) + 16LL)
                                                                                                + 8LL))(*((_QWORD *)v285 + 13) + 16LL);
            v297.m128i_i64[0] = (**(__int64 (__fastcall ***)(__int64))(*((_QWORD *)v254 + 13) + 16LL))(*((_QWORD *)v254 + 13) + 16LL);
            VmEventWrite<unsigned short const *,unsigned short const *,unsigned short (&)[16],unsigned short (&)[16]>(
              &MSVML_WP_SET_DEBUG_CHANNEL_ERROR,
              5u,
              (__int64)&v276,
              (__int64)v312,
              (__int64)v327);
            v274 = v275;
            v284 = v282[0];
            v16 = phkResult;
            v165 = (void **)v302;
            v281 = (unsigned int *)v298[0];
            v161 = v285;
            v277 = v278;
            v180 = v273;
            v140 = v293;
            goto LABEL_260;
          }
        }
        v180 = (__int64)v280;
LABEL_260:
        Instance = VidNotificationDispatcher::CreateInstance((struct VidNotificationDispatcher **)v161 + 8);
        if ( Instance < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6E4,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)Instance,
            (int)v263);
        v264 = (struct IVpOperations *)v180;
        v182 = v277;
        v183 = VidNotificationDispatcher::Initialize(
                 *((VidNotificationDispatcher **)v161 + 8),
                 v161,
                 v277,
                 *(struct IVirtualMachine **)v16,
                 v264,
                 a5,
                 v287);
        if ( v183 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x6EB,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v183,
            v265);
        if ( !(unsigned int)Vml::VmCompletionHandlerIo::AssociateHandle(
                              (VidPartitionManager *)((char *)v161 + 120),
                              *v165) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x6ED,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            v184);
        memset_0(v324, 0, 0x100u);
        if ( (_DWORD)v296 )
        {
          v185 = 0;
          v186 = v272;
          if ( v272 )
          {
            v187 = v283;
            do
            {
              v188 = *(unsigned __int8 *)(v187 + v185 + 280);
              v324[v188] += *(_DWORD *)(v187 + 4LL * v185++ + 16);
            }
            while ( v185 < v186 );
          }
          for ( j = 0; j < v291; ++j )
          {
            if ( *(_DWORD *)&v326[24 * j + 4] < v324[j] )
            {
              v273 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 8LL))(*(_QWORD *)v16 + 16LL);
              v278 = (struct INumaManager *)(**(__int64 (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
              VmEventWrite<unsigned short const *,unsigned short const *>(
                &MSVML_MM_NUMA_RESOURCES_NOT_ALIGNED_WARNING,
                1u,
                (__int64)&v273);
              break;
            }
          }
        }
        if ( v274 && v272 > 1u )
        {
          *(_OWORD *)v298 = 0;
          *(_QWORD *)&v299 = 0;
          v190 = v140 * v140;
          if ( v190 )
            std::vector<unsigned char const *>::_Resize_reallocate<std::_Value_init_tag>((__int64)v298, v190);
          v290 = 0;
          v191 = v274;
          if ( v274 == 2 )
            goto LABEL_279;
          while ( 1 )
          {
            LODWORD(v296) = gsl::narrow<unsigned int,unsigned __int64,0>(((char *)v298[1] - (char *)v298[0]) & 0xFFFFFFFFFFFFFFF8uLL);
            v266 = (int)v298[0];
            if ( (unsigned int)VidQueryPartitionInformation(*v165, 0, &v290, 4) )
              break;
            if ( v191 != 3 )
            {
              v240 = GetLastError();
              v241 = v240;
              if ( v240 > 0 )
                v241 = (unsigned __int16)v240 | 0x80070000;
              v242 = VmWorkerTrace::Provider();
              v243 = (int)v242;
              if ( *(_DWORD *)v242 > 2u && (unsigned __int8)tlgKeywordOn(v242, 0) )
              {
                v275 = v241;
                v271 = v191;
                v244 = Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::operator->(v16);
                v273 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(v244 + 16) + 16LL))(v244 + 16);
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>>(
                  v243,
                  (unsigned int)&byte_140360A8F,
                  v245,
                  v246,
                  (__int64)&v273,
                  (__int64)&v271,
                  (__int64)&v275);
              }
              v247 = wil::verify_hresult<long>(v241);
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x740,
                (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                (const char *)v247,
                v266);
            }
            v191 = 2;
            v290 = 0;
LABEL_279:
            v290 = 1;
          }
          v192 = VmWorkerTrace::Provider();
          v193 = (int)v192;
          if ( *(_DWORD *)v192 > 4u && (unsigned __int8)tlgKeywordOn(v192, 4096) )
          {
            v271 = v191;
            v327[0] = (char *)v298[0];
            LOWORD(v327[1]) = ((char *)v298[1] - (char *)v298[0]) >> 3;
            v273 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 16LL))(*(_QWORD *)v16 + 16LL);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<8>,_tlgWrapperByVal<1>>(
              v193,
              (__int64)&v273,
              (__int64)v327,
              (__int64)&v271);
          }
          (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v284 + 440LL))(v284, v298);
          std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<MigrationTransferEndpointTarget>>>>>>>(v298);
        }
        v194 = operator new(0x90u);
        v273 = (__int64)v194;
        memset_0(v194, 0, 0x90u);
        v195 = WorkerStatsPanel::WorkerStatsPanel((WorkerStatsPanel *)v194);
        *((_QWORD *)v161 + 9) = v195;
        v196 = *v281;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)v16 + 16LL) + 16LL))(*(_QWORD *)v16 + 16LL);
        (**(void (__fastcall ***)(__int64))(*(_QWORD *)v16 + 16LL))(*(_QWORD *)v16 + 16LL);
        v199 = WorkerStatsPanel::Initialize(v195, *v165, v197, v198, v196);
        if ( v199 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x75D,
            (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
            (const char *)(unsigned int)v199,
            v267);
        (*(void (__fastcall **)(struct INumaManager *))(*(_QWORD *)v182 + 120LL))(v182);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v321);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v308);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v306);
        std::vector<_VID_VSM_MBP_PERMISSIONS>::_Tidy(&v310);
        Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits>(&v301);
        return 0;
      }
      gsl::details::terminate(v31);
    }
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x146,
      (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
      v19);
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x763,
                           (unsigned int)"onecore\\vm\\worker\\vidpartition\\vidpartitionmanager.cpp",
                           v200);
  }
  return result;
}

```

## disassembly

```asm
0x1402766ec  push    rbx
0x1402766ee  push    rsi
0x1402766ef  push    rdi
0x1402766f0  push    r12
0x1402766f2  push    r13
0x1402766f4  push    r14
0x1402766f6  push    r15
0x1402766f8  mov     eax, 1880h
0x1402766fd  call    _alloca_probe
0x140276702  sub     rsp, rax
0x140276705  movaps  [rsp+18B8h+var_48], xmm6
0x14027670d  mov     rax, cs:__security_cookie
0x140276714  xor     rax, rsp
0x140276717  mov     [rsp+18B8h+var_58], rax
0x14027671f  mov     r15, r9
0x140276722  mov     [rsp+18B8h+var_1840], r9
0x140276727  mov     rbx, r8
0x14027672a  mov     [rsp+18B8h+var_1858], rbx
0x14027672f  mov     [rsp+18B8h+var_1808], rdx
0x140276737  mov     rsi, rcx
0x14027673a  mov     [rsp+18B8h+var_1848], rcx
0x14027673f  mov     [rsp+18B8h+var_1810], rcx
0x140276747  mov     [rsp+18B8h+var_1850], rbx
0x14027674c  mov     [rsp+18B8h+var_1870], r9
0x140276751  mov     rcx, [rsp+18B8h+arg_28]
0x140276759  mov     [rsp+18B8h+var_1800], rcx
0x140276761  mov     r12, [rsp+18B8h+arg_48]
0x140276769  mov     [rsp+18B8h+var_1780], r12
0x140276771  mov     rdi, [rsp+18B8h+arg_60]
0x140276779  mov     [rsp+18B8h+var_1860], rdi
0x14027677e  lea     r13, [rsi+68h]
0x140276782  mov     rcx, r13
0x140276785  call    ?Reset@?$VmReferencePtr@UIVirtualMachine@@VVmWeakReferenceTraits@Vml@@@Vml@@QEAAXPEAUIVirtualMachine@@@Z; Vml::VmReferencePtr<IVirtualMachine,Vml::VmWeakReferenceTraits>::Reset(IVirtualMachine *)
0x14027678a  mov     rax, [r15]
0x14027678d  mov     rcx, r15
0x140276790  mov     rax, [rax+0B8h]
0x140276797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027679c  xor     r14d, r14d
0x14027679f  test    eax, eax
0x1402767a1  setnz   al
0x1402767a4  mov     [rsi+72h], al
0x1402767a7  call    cs:__imp_VidOpenStatisticsHandle
0x1402767ae  nop     dword ptr [rax+rax+00h]
0x1402767b3  mov     [rsi+50h], rax
0x1402767b7  dec     rax
0x1402767ba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1402767be  ja      loc_140279270
0x1402767c4  mov     rcx, [r13+0]
0x1402767c8  mov     rax, [rcx]
0x1402767cb  mov     rax, [rax+30h]
0x1402767cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402767d4  mov     rdx, rax
0x1402767d7  mov     rcx, [rax]
0x1402767da  mov     rax, [rcx+98h]
0x1402767e1  mov     rcx, rdx
0x1402767e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402767e9  lea     rcx, [rsi+58h]
0x1402767ed  mov     [rsp+18B8h+var_1838], rcx
0x1402767f5  mov     [rcx], eax
0x1402767f7  call    _lambda_997682190daf7855ab97ce0562d05e09___operator__
0x1402767fc  movzx   r12d, al
0x140276800  mov     byte ptr [rsp+18B8h+var_1878], r12b
0x140276805  mov     [rsp+18B8h+var_1768], r14
0x14027680d  mov     dword ptr [rsp+18B8h+var_17DC], r14d
0x140276815  mov     dword ptr [rsp+18B8h+var_17E4], r14d
0x14027681d  mov     [rsp+18B8h+var_1788], r14
0x140276825  mov     rcx, [r13+0]
0x140276829  mov     rdx, [rcx]
0x14027682c  mov     rax, [rdx+38h]
0x140276830  lea     rdx, [rsp+18B8h+var_1788]
0x140276838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027683d  nop
0x14027683e  xorps   xmm0, xmm0
0x140276841  movups  xmmword ptr [rsp+18B8h+var_78], xmm0
0x140276849  xor     r8d, r8d
0x14027684c  mov     rdx, [rsp+18B8h+var_1788]
0x140276854  lea     rcx, [rsp+18B8h+var_78]
0x14027685c  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x140276861  nop
0x140276862  mov     r9d, dword ptr [rsp+18B8h+var_78+8]; char *
0x14027686a  mov     rcx, [rsp+18B8h]; this
0x140276872  test    r9d, r9d
0x140276875  js      loc_140278990
0x14027687b  mov     rcx, [rsp+18B8h+var_1788]
0x140276883  mov     rax, [rcx]
0x140276886  lea     rdx, [rsp+18B8h+var_17DC]
0x14027688e  mov     rax, [rax+120h]
0x140276895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14027689a  mov     rcx, [rsp+18B8h]; this
0x1402768a2  test    eax, eax
0x1402768a4  js      loc_1402789A1
0x1402768aa  mov     rcx, [rsp+18B8h+var_1788]
0x1402768b2  mov     rax, [rcx]
0x1402768b5  lea     r8, [rsp+18B8h+var_1768]
0x1402768bd  lea     rdx, ?VIRTUAL_MACHINE_DEBUG_CHANNELID@@3QBGB; "/configuration/global_settings/debug/ch"...
0x1402768c4  mov     rax, [rax+70h]
0x1402768c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402768cd  mov     rcx, [rsp+18B8h+var_1788]
0x1402768d5  mov     rax, [rcx]
0x1402768d8  lea     rdx, [rsp+18B8h+var_17E4]
0x1402768e0  mov     rax, [rax+140h]
0x1402768e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1402768ec  xorps   xmm0, xmm0
0x1402768ef  movdqa  [rsp+18B8h+var_1718], xmm0
0x1402768f8  mov     [rsp+18B8h+var_1708], r14
0x140276900  mov     [rsp+18B8h+var_1700], r14
0x140276908  mov     qword ptr [rsp+18B8h+var_16F8], r14
0x140276910  mov     qword ptr [rsp+18B8h+var_16F8+8], r14
0x140276918  movdqa  [rsp+18B8h+var_16E8], xmm0
0x140276921  mov     [rsp+18B8h+var_16D8], r14
0x140276929  mov     [rsp+18B8h+var_16D0], r14
0x140276931  mov     [rsp+18B8h+var_16C8], r14d
0x140276939  lea     r8, [rsp+18B8h+var_1718]
0x140276941  lea     rdx, [rsp+18B8h+var_1788]
0x140276949  lea     rcx, [rsp+18B8h+var_17B8]
0x140276951  call    ??$FromRepository@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@UTopologySettings@VmWorkerProcess@Config@@$$V@Marshal@@YA?AU?$pair@_NV?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@@std@@AEBV?$VmReferencePtr@VVmRepository@@VVmUserReferenceTraits@Vml@@@Vml@@PEAUTopologySettings@VmWorkerProcess@Config@@W4UnmarshalFlags@0@@Z; Marshal::FromRepository<Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings,>(Vml::VmReferencePtr<VmRepository,Vml::VmUserReferenceTraits> const &,Config::VmWorkerProcess::TopologySettings *,Marshal::UnmarshalFlags)
0x140276956  nop
0x140276957  mov     rcx, [rsp+18B8h]; this
0x14027695f  cmp     [rax], r14b
0x140276962  jz      loc_1402789B6
0x140276968  lea     rcx, [rsp+18B8h+var_17B8+8]
0x140276970  call    ?_Tidy@?$vector@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@V?$allocator@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4UnmarshalError@Marshal@@@std@@@2@@std@@AEAAXXZ; std::vector<std::pair<std::wstring,Marshal::UnmarshalError>>::_Tidy(void)
0x140276975  mov     edx, dword ptr [rsp+18B8h+var_16D8]
0x14027697c  mov     [rsp+18B8h+var_1868], edx
0x140276980  mov     [rsp+18B8h+var_1864], edx
0x140276984  mov     rcx, [rsp+18B8h]; this
0x14027698c  cmp     edx, 3
0x14027698f  ja      loc_1402789CE
0x140276995  mov     eax, dword ptr [rsp+18B8h+var_17DC]
0x14027699c  test    edx, edx
0x14027699e  jz      short loc_1402769B5
0x1402769a0  cmp     eax, 903h
0x1402769a5  jb      short loc_1402769B1
0x1402769a7  cmp     dword ptr [rsp+18B8h+var_17E4], 1
0x1402769af  jz      short loc_1402769B5
0x1402769b1  mov     cl, 1
0x1402769b3  jmp     short loc_1402769B8
0x1402769b5  mov     cl, r14b
0x1402769b8  mov     r10, [rsp+18B8h]
0x1402769c0  test    cl, cl
0x1402769c2  jnz     loc_1402789E5
0x1402769c8  test    r12b, r12b
0x1402769cb  jnz     short loc_1402769EE
0x1402769cd  cmp     edx, 3
0x1402769d0  jnz     short loc_1402769DB
0x1402769d2  cmp     eax, 0B00h
0x1402769d7  mov     al, 1
0x1402769d9  jb      short loc_1402769DE
0x1402769db  mov     al, r14b
0x1402769de  mov     rcx, [rsp+18B8h]; this
0x1402769e6  test    al, al
0x1402769e8  jnz     loc_1402789FF
0x1402769ee  lea     rcx, [rsp+18B8h+var_78]; this
0x1402769f6  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1402769fb  mov     rax, [rbx]
0x1402769fe  mov     rcx, rbx
0x140276a01  mov     rax, [rax+8]
0x140276a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140276a0a  mov     rcx, rax
0x140276a0d  mov     [rsp+18B8h+var_1818], rax
0x140276a15  mov     rax, [rax]
0x140276a18  mov     rax, [rax+58h]
0x140276a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140276a21  mov     [rsp+18B8h+var_1820], rax
0x140276a29  mov     al, [rax+110h]
0x140276a2f  mov     byte ptr [rsp+18B8h+var_1878+1], al
0x140276a33  mov     [rsi+5Ch], al
0x140276a36  xorps   xmm1, xmm1
0x140276a39  movdqu  [rsp+18B8h+var_1730], xmm1
0x140276a42  mov     [rsp+18B8h+var_1720], r14
0x140276a4a  movdqu  [rsp+18B8h+var_1760], xmm1
0x140276a53  mov     [rsp+18B8h+var_1750], r14
0x140276a5b  mov     dl, 1
0x140276a5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x140276a64  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140276a69  cmp     [rsi+72h], r14b
0x140276a6d  jz      short loc_140276A9C
0x140276a6f  lea     rdx, [rdi+10h]
0x140276a73  cmp     [rdx], r14w
0x140276a77  jz      short loc_140276A86
0x140276a79  lea     rcx, [rsp+18B8h+var_1760]
0x140276a81  call    ?Initialize@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@@QEAAXAEBU_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES const &)
0x140276a86  cmp     [rdi], r14w
0x140276a8a  jz      short loc_140276A9C
0x140276a8c  mov     rdx, rdi
0x140276a8f  lea     rcx, [rsp+18B8h+var_1730]
0x140276a97  call    ?Initialize@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@@QEAAXAEBU_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES@@@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES>::Initialize(_HV_PARTITION_PROPERTY_ASSIGNABLE_SYNTHETIC_PROCESSOR_FEATURES const &)
0x140276a9c  xorps   xmm1, xmm1
0x140276a9f  movdqu  [rsp+18B8h+var_1748], xmm1
0x140276aa8  mov     [rsp+18B8h+var_1738], r14
0x140276ab0  mov     r8, [rdi+20h]
0x140276ab4  test    r8, r8
0x140276ab7  jz      short loc_140276AD7
0x140276ab9  mov     rdx, [rdi+40h]
0x140276abd  test    rdx, rdx
0x140276ac0  jz      short loc_140276AD7
0x140276ac2  lea     r8, ds:8[r8*8]
0x140276aca  lea     rcx, [rsp+18B8h+var_1748]
0x140276ad2  call    ?InitializeFromBuffer@?$HvPartitionPropertyPayload@U_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX@@@@QEAAXPEBU_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX@@_K@Z; HvPartitionPropertyPayload<_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX>::InitializeFromBuffer(_HV_PARTITION_PROPERTY_PROCESSOR_FEATURES_EX const *,unsigned __int64)
0x140276ad7  xorps   xmm0, xmm0
0x140276ada  xor     eax, eax
0x140276adc  movups  [rsp+18B8h+var_1698], xmm0
0x140276ae4  mov     [rsp+18B8h+var_1688], rax
0x140276aec  mov     rcx, qword ptr [rsp+18B8h+var_1748+8]
0x140276af4  sub     rcx, qword ptr [rsp+18B8h+var_1748]
0x140276afc  sub     rcx, qword ptr [rsp+18B8h+var_1760]
0x140276b04  sub     rcx, qword ptr [rsp+18B8h+var_1730]
0x140276b0c  add     rcx, qword ptr [rsp+18B8h+var_1760+8]
0x140276b14  mov     rdx, qword ptr [rsp+18B8h+var_1730+8]
0x140276b1c  add     rdx, 10C60h
0x140276b23  add     rdx, rcx
0x140276b26  lea     rcx, [rsp+18B8h+var_1698]
0x140276b2e  call    ??0?$vector@W4byte@gsl@@V?$allocator@W4byte@gsl@@@std@@@std@@QEAA@_KAEBV?$allocator@W4byte@gsl@@@1@@Z; std::vector<gsl::byte>::vector<gsl::byte>(unsigned __int64,std::allocator<gsl::byte> const &)
0x140276b33  nop
0x140276b34  xorps   xmm0, xmm0
0x140276b37  movups  xmmword ptr [rsp+18B8h+var_17B8], xmm0
0x140276b3f  lea     rdx, [rsp+18B8h+var_1698]
0x140276b47  lea     rcx, [rsp+18B8h+var_17B8]
0x140276b4f  call    ??$?0$0?0V?$vector@EV?$allocator@E@std@@@std@@$0A@@?$span@E$0?0@gsl@@QEAA@AEAV?$vector@EV?$allocator@E@std@@@std@@@Z; gsl::span<uchar,-1>::span<uchar,-1>(std::vector<uchar> &)
0x140276b54  mov     r15, [rsp+18B8h+var_17B8+8]
0x140276b5c  mov     rax, [rsp+18B8h+var_17B8]
0x140276b64  mov     [rsp+18B8h+var_78], rax
0x140276b6c  mov     [rsp+18B8h+var_78+8], r15
0x140276b74  lea     rcx, [rsp+18B8h+var_78]
0x140276b7c  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276b81  mov     ebx, 10B40h
0x140276b86  cmp     rax, rbx
0x140276b89  jb      loc_14027926A
0x140276b8f  lea     rcx, [rsp+18B8h+var_78]
0x140276b97  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276b9c  mov     r8d, ebx; Size
0x140276b9f  xor     edx, edx; Val
0x140276ba1  mov     rcx, r15; void *
0x140276ba4  call    memset_0
0x140276ba9  mov     ecx, 10C60h
0x140276bae  call    ??$narrow@I_K$0A@@gsl@@YAI_K@Z; gsl::narrow<uint,unsigned __int64,0>(unsigned __int64)
0x140276bb3  mov     edi, eax
0x140276bb5  mov     [rsp+18B8h+var_78], r14
0x140276bbd  mov     r9d, 120h
0x140276bc3  mov     r8d, ebx
0x140276bc6  lea     rdx, [rsp+18B8h+var_1830]
0x140276bce  lea     rcx, [rsp+18B8h+var_17B8]
0x140276bd6  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140276bdb  movups  xmm6, xmmword ptr [rax]
0x140276bde  movaps  [rsp+18B8h+var_17C8], xmm6
0x140276be6  lea     rcx, [rsp+18B8h+var_17C8]
0x140276bee  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276bf3  test    al, 0Fh
0x140276bf5  jnz     loc_140279264
0x140276bfb  movdqa  [rsp+18B8h+var_17C8], xmm6
0x140276c04  psrldq  xmm6, 8
0x140276c09  movq    rbx, xmm6
0x140276c0e  lea     rcx, [rsp+18B8h+var_17C8]
0x140276c16  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276c1b  shr     rax, 4
0x140276c1f  mov     rdx, rax
0x140276c22  lea     rcx, [rsp+18B8h+var_78]
0x140276c2a  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140276c2f  mov     [rsp+18B8h+var_78+8], rbx
0x140276c37  cmp     [rsp+18B8h+var_78], 0FFFFFFFFFFFFFFFFh
0x140276c40  jz      loc_140279264
0x140276c46  test    rbx, rbx
0x140276c49  jnz     short loc_140276C59
0x140276c4b  cmp     [rsp+18B8h+var_78], r14
0x140276c53  jnz     loc_140279264
0x140276c59  mov     qword ptr [rsp+18B8h+var_17C8], r14
0x140276c61  mov     r8, rdi
0x140276c64  or      r9, 0FFFFFFFFFFFFFFFFh
0x140276c68  lea     rdx, [rsp+18B8h+var_1830]
0x140276c70  lea     rcx, [rsp+18B8h+var_17B8]
0x140276c78  call    ?subspan@?$span@$$CBW4byte@gsl@@$0?0@gsl@@QEBA?AV12@_K0@Z; gsl::span<gsl::byte const,-1>::subspan(unsigned __int64,unsigned __int64)
0x140276c7d  movups  xmm6, xmmword ptr [rax]
0x140276c80  movaps  xmmword ptr [rsp+18B8h+var_17B8], xmm6
0x140276c88  lea     rcx, [rsp+18B8h+var_17B8]
0x140276c90  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276c95  movdqa  xmmword ptr [rsp+18B8h+var_17B8], xmm6
0x140276c9e  psrldq  xmm6, 8
0x140276ca3  movq    rbx, xmm6
0x140276ca8  lea     rcx, [rsp+18B8h+var_17B8]
0x140276cb0  call    ?size_bytes@?$span@E$0?0@gsl@@QEBA_KXZ; gsl::span<uchar,-1>::size_bytes(void)
0x140276cb5  mov     rdx, rax
0x140276cb8  lea     rcx, [rsp+18B8h+var_17C8]
0x140276cc0  call    ??0?$extent_type@$0?0@details@gsl@@QEAA@_K@Z; gsl::details::extent_type<-1>::extent_type<-1>(unsigned __int64)
0x140276cc5  mov     qword ptr [rsp+18B8h+var_17C8+8], rbx
0x140276ccd  cmp     qword ptr [rsp+18B8h+var_17C8], 0FFFFFFFFFFFFFFFFh
0x140276cd6  jz      loc_14027925E
0x140276cdc  test    rbx, rbx
0x140276cdf  jnz     short loc_140276CEF
0x140276ce1  cmp     qword ptr [rsp+18B8h+var_17C8], r14
0x140276ce9  jnz     loc_14027925E
0x140276cef  mov     qword ptr [rsp+18B8h+var_1718], r15
0x140276cf7  movups  xmm0, xmmword ptr [rsp+18B8h+var_78]
0x140276cff  movdqu  [rsp+18B8h+var_1718+8], xmm0
0x140276d08  mov     dword ptr [rsp+18B8h+var_1700], edi
0x140276d0f  movups  xmm1, [rsp+18B8h+var_17C8]
0x140276d17  movdqu  [rsp+18B8h+var_16F8], xmm1
0x140276d20  mov     dl, 1
0x140276d22  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures> `wil::Feature<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::GetImpl(void)'::`2'::impl
0x140276d29  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_L1VH_VMMFeatures@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_L1VH_VMMFeatures>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x140276d2e  cmp     [rsi+72h], r14b
  ... truncated ...
```
