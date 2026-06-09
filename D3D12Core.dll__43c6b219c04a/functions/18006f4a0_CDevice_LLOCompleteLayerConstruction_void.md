# CDevice::LLOCompleteLayerConstruction(void)

- ea: `0x18006f4a0`
- end: `0x180071828`
- name: `?LLOCompleteLayerConstruction@CDevice@@QEAAJXZ`
- size: `9096`
- prototype: `__int64 __fastcall(CDevice *__hidden this)`
- caller_count: `1`
- callee_count: `140`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18006f490`

## callees

- `0x180003c84`
- `0x180004624`
- `0x180004a38`
- `0x180005650`
- `0x180007f20`
- `0x18000b010`
- `0x18000b920`
- `0x18000d770`
- `0x180012c2c`
- `0x1800235dc`
- `0x180024c70`
- `0x180026910`
- `0x180028038`
- `0x18002a710`
- `0x18002a900`
- `0x180037730`
- `0x18003f690`
- `0x180040fa8`
- `0x180040fd0`
- `0x180044b5c`
- `0x180048644`
- `0x180048810`
- `0x18004d040`
- `0x18004ec1c`
- `0x18004ed64`
- `0x18004ef60`
- `0x18004fc44`
- `0x18004fc58`
- `0x180053b74`
- `0x180054550`
- `0x1800579a0`
- `0x180057d98`
- `0x180059620`
- `0x18005996c`
- `0x18005de60`
- `0x18005f1fc`
- `0x18005f4f0`
- `0x180060870`
- `0x180062b24`
- `0x180062ff8`
- `0x180063ffc`
- `0x18006482c`
- `0x1800648ac`
- `0x180065d18`
- `0x18006705c`
- `0x1800683d0`
- `0x180068690`
- `0x180069ffc`
- `0x18006b41c`
- `0x18006bb54`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18007103b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x18007103b`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x1800716c1`
- `ntdll!RtlIsCriticalSectionLockedByThread` at `0x1800716c1`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x18006f63f`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x18006fce2`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x18006fd70`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x1800701c4`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180070479`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180070d90`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180070ef2`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180070f72`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180070ff2`
- `ext-ms-win-dx-d3dkmt-dxcore-l1-1-0!__imp_D3DKMTQueryAdapterInfo` at `0x180071104`

## string_xrefs

- `0x18006fc3a`: `Driver did not correctly respond to D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY caps query.`
- `0x18006f6a8`: `ForceComputeOnlyDevice`
- `0x1800707ff`: `Driver specified incompatible cross-node sharing tier`
- `0x180071405`: `FL12.2+ driver incorrectly did not report support for direct, compute, and bundle WriteBufferImmediate support.`
- `0x180071655`: `BackgroundThreadCount`
- `0x18007167a`: `ForegroundThreadCount`
- `0x1800714d9`: `FL12.2+ driver incorrectly did not report support for the CopyQueueTimestampQueriesSupported capability`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDevice::LLOCompleteLayerConstruction(CDevice *this)
{
  _QWORD *v2; // r14
  CDevice *v3; // rcx
  _QWORD *v4; // r15
  bool v5; // bl
  __int64 v6; // rbx
  NDXGI::CUMDAdapter *v7; // r12
  char v8; // al
  int DriverInstance; // ecx
  __int64 v10; // rcx
  __int64 v11; // r9
  CJournal *v12; // rcx
  __int64 v13; // r8
  int v14; // eax
  int *v15; // rbx
  _DWORD *v16; // rax
  bool v17; // sf
  CJournal *v18; // rcx
  CJournal *v19; // rcx
  __int64 v20; // r8
  _DWORD *v21; // rax
  int v22; // edx
  void ***DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z; // rax
  void **v24; // rcx
  __int64 v25; // rdx
  NDXGI::CUMDAdapter *v26; // rbx
  __int64 v27; // rcx
  __int64 v28; // r9
  __int64 v29; // rdx
  __int64 v30; // rdx
  unsigned int Caps; // eax
  int v32; // eax
  __int64 v33; // rcx
  __int64 v34; // r9
  bool v35; // al
  int v36; // r8d
  CJournal *v37; // rcx
  unsigned int v38; // eax
  int v39; // eax
  unsigned int v40; // eax
  int v41; // eax
  __int64 v42; // rdx
  CJournal *v43; // rcx
  __int64 v44; // rdx
  CJournal *v45; // rcx
  unsigned int i; // eax
  enum DXGI_FORMAT Format; // eax
  enum DXGI_FORMAT v48; // ebx
  _QWORD *v49; // rax
  __int64 v50; // rcx
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // r9
  unsigned int j; // r8d
  _QWORD *v55; // rax
  int v56; // r8d
  unsigned int v57; // r8d
  _DWORD *FormatCastSet; // r10
  _QWORD *v59; // rax
  __int64 v60; // rcx
  __int64 v61; // r8
  int v62; // eax
  int v63; // r11d
  unsigned int v64; // eax
  _QWORD *v65; // rax
  _DWORD *v66; // r10
  __int64 v67; // rcx
  __int64 v68; // r9
  __int64 v69; // rcx
  NDXGI::CUMDAdapter *v70; // rbx
  struct ID3DShaderCacheApplication *v71; // rbx
  unsigned int v72; // eax
  int v73; // eax
  __int64 v74; // rcx
  __int64 v75; // r9
  unsigned int v76; // eax
  __int64 v77; // rcx
  void *v78; // r9
  unsigned int v79; // r8d
  char *v80; // rcx
  _DWORD *v81; // rax
  int v82; // r8d
  __int64 v83; // r9
  unsigned int v84; // r10d
  __int64 v85; // r9
  void *v86; // r8
  char *v87; // rcx
  int v88; // r9d
  unsigned int k; // eax
  unsigned __int64 v90; // rax
  unsigned __int64 v91; // rdx
  __int64 v92; // rax
  __int64 v93; // rcx
  __int64 v94; // rcx
  __int64 v95; // r9
  unsigned int *v96; // rax
  __int64 v97; // r9
  int ShaderCacheABIInfo; // eax
  __int64 RegisteredApp; // rax
  int v100; // eax
  _BYTE *v101; // rax
  __int64 v102; // rdx
  __int64 v103; // r8
  __int64 v104; // r9
  __int64 v105; // rax
  __int64 v106; // rdx
  __int64 v107; // r8
  __int64 v108; // r9
  __int64 v109; // r9
  int v110; // eax
  CDevice *v111; // rcx
  unsigned int ImplicitPhysicalAdapterMask; // eax
  __int64 v113; // rcx
  __int64 v114; // r9
  int v115; // eax
  __int64 v116; // rdx
  __int64 v117; // r8
  __int64 v118; // r9
  __int64 v119; // rax
  __int64 v120; // r10
  __int64 m; // r9
  __int64 v122; // r9
  CDevice *v123; // rcx
  CDevice *v124; // rcx
  bool v125; // cl
  BOOL v126; // eax
  bool v127; // al
  __int64 v128; // rdx
  VersionedDeviceData *v129; // rcx
  int v130; // eax
  BOOL v131; // eax
  BOOL v132; // eax
  __int64 v133; // rdx
  CDevice *v134; // rcx
  CJournal *v135; // rcx
  CJournal *v136; // rcx
  int v137; // eax
  unsigned int v138; // eax
  int v139; // eax
  unsigned int n; // r8d
  CPagingQueue *v141; // rax
  unsigned int v142; // r8d
  __int64 v143; // rax
  _QWORD *v144; // rax
  __int64 v145; // r8
  unsigned int v146; // eax
  int v147; // eax
  bool v148; // al
  unsigned int v149; // eax
  int v150; // eax
  _QWORD *v151; // rbx
  unsigned int v152; // eax
  int v153; // eax
  unsigned __int64 v154; // rcx
  unsigned int ii; // eax
  unsigned int v156; // eax
  CDevice *v157; // rax
  CDevice *v158; // rcx
  int v159; // eax
  CJournal *v160; // rcx
  __int64 v161; // r9
  __int64 v162; // rcx
  __int64 v163; // r9
  __int64 v164; // rcx
  __int64 v165; // r9
  __int64 v166; // rcx
  __int64 v167; // r9
  __int64 v168; // rcx
  __int64 v169; // r8
  __int64 v170; // r9
  __int64 v171; // r8
  __int64 v172; // rcx
  __int64 v173; // r9
  __int64 v174; // rcx
  __int64 v175; // r9
  __int64 v176; // r9
  int v177; // eax
  enum D3D12_COMMAND_POOL_FLAGS v178; // edx
  const struct _GUID *v179; // r8
  int v180; // eax
  int v181; // eax
  bool v182; // al
  __int64 v183; // rdx
  __int64 result; // rax
  struct SShaderCacheApplicationIdentity *v185; // [rsp+20h] [rbp-398h]
  char v186; // [rsp+40h] [rbp-378h]
  bool v187; // [rsp+40h] [rbp-378h]
  unsigned int v188; // [rsp+44h] [rbp-374h] BYREF
  unsigned int v189; // [rsp+48h] [rbp-370h] BYREF
  char v190; // [rsp+4Ch] [rbp-36Ch]
  void *v191; // [rsp+50h] [rbp-368h] BYREF
  unsigned int v192; // [rsp+58h] [rbp-360h]
  char v193; // [rsp+5Ch] [rbp-35Ch]
  NDXGI::CUMDAdapter *v194; // [rsp+60h] [rbp-358h]
  __int64 v195; // [rsp+68h] [rbp-350h] BYREF
  __int64 v196; // [rsp+70h] [rbp-348h] BYREF
  CDevice *jj; // [rsp+78h] [rbp-340h] BYREF
  struct ID3DShaderCacheApplication *v198; // [rsp+80h] [rbp-338h] BYREF
  __int128 v199; // [rsp+88h] [rbp-330h] BYREF
  __int64 v200; // [rsp+98h] [rbp-320h]
  __int64 v201; // [rsp+A0h] [rbp-318h] BYREF
  char v202[8]; // [rsp+A8h] [rbp-310h] BYREF
  char v203[8]; // [rsp+B0h] [rbp-308h] BYREF
  _com_error *v204; // [rsp+B8h] [rbp-300h] BYREF
  __int128 v205; // [rsp+C0h] [rbp-2F8h] BYREF
  __int128 v206; // [rsp+D0h] [rbp-2E8h]
  __int64 v207; // [rsp+E0h] [rbp-2D8h]
  _SYSTEM_INFO SystemInfo; // [rsp+F0h] [rbp-2C8h] BYREF
  _BYTE v209[32]; // [rsp+120h] [rbp-298h] BYREF
  __int64 v210; // [rsp+140h] [rbp-278h]
  __int64 v211; // [rsp+148h] [rbp-270h]
  __int64 v212; // [rsp+150h] [rbp-268h]
  __int64 v213; // [rsp+158h] [rbp-260h]
  _BYTE v214[32]; // [rsp+160h] [rbp-258h] BYREF
  char v215[32]; // [rsp+180h] [rbp-238h] BYREF
  __int64 v216; // [rsp+1A0h] [rbp-218h]
  char v217[32]; // [rsp+1A8h] [rbp-210h] BYREF
  __int64 v218; // [rsp+1C8h] [rbp-1F0h]
  __int64 v219; // [rsp+1D0h] [rbp-1E8h]
  _BYTE v220[256]; // [rsp+1E0h] [rbp-1D8h] BYREF
  __int64 v221; // [rsp+2E0h] [rbp-D8h]
  __int64 v222; // [rsp+2E8h] [rbp-D0h]
  __int64 v223; // [rsp+2F0h] [rbp-C8h]
  __int64 v224; // [rsp+2F8h] [rbp-C0h]
  _DWORD v225[8]; // [rsp+300h] [rbp-B8h] BYREF
  char v226[32]; // [rsp+320h] [rbp-98h] BYREF
  __int64 v227; // [rsp+340h] [rbp-78h]
  char v228[32]; // [rsp+348h] [rbp-70h] BYREF
  __int64 v229; // [rsp+368h] [rbp-50h]

  try
  {
    v2 = (_QWORD *)((char *)this + 760);
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 86))(
      *((_QWORD *)this + 86),
      &GUID_00000040_0209_4b96_9b67_bdb7271d9371,
      (char *)this + 760);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 16LL))(*v2);
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 86))(
      *((_QWORD *)this + 86),
      &GUID_189819f1_1db6_4b57_be54_1821339b85f7,
      (char *)this + 768);
    v3 = (CDevice *)*((_QWORD *)this + 96);
    *((_BYTE *)this + 713) = this == v3;
    (*(void (__fastcall **)(CDevice *))(*(_QWORD *)v3 + 16LL))(v3);
    v4 = (_QWORD *)((char *)this + 776);
    (***((void (__fastcall ****)(_QWORD, GUID *, char *))this + 86))(
      *((_QWORD *)this + 86),
      &GUID_16266e32_a95b_41da_89e4_a14379c0c6e4,
      (char *)this + 776);
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 16LL))(*v4);
    v5 = 0;
    if ( *((int *)this + 391) >= 11 )
      v5 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v4 + 24LL))(*v4) != 0;
    *((_BYTE *)this + 641) = v5;
    v6 = *v2;
    v7 = *(NDXGI::CUMDAdapter **)(*v2 + 40LL);
    v194 = v7;
    jj = v7;
    *((_BYTE *)this + 708) = NDXGI::CUMDAdapter::IsWARP(v7);
    v188 = 0;
    v205 = 0;
    *(_QWORD *)&v206 = 0;
    LODWORD(v205) = *(_DWORD *)(*(_QWORD *)(v6 + 40) + 448LL);
    DWORD1(v205) = 27;
    *((_QWORD *)&v205 + 1) = &v188;
    LODWORD(v206) = 4;
    if ( (int)CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                D3DKMTQueryAdapterInfo,
                "QueryAdapterInfo (IsXbox)",
                CLayeredObject<CCommandAllocator>::AddRef,
                &v205) < 0
      || (v8 = 1, !v188) )
    {
      v8 = 0;
    }
    *((_BYTE *)this + 712) = v8;
    NDXGI::CUMDAdapter::GetUMDFileVersion(v7, (union _LARGE_INTEGER *)this + 842);
    v196 = 0;
    v191 = 0;
    if ( (unsigned int)GetBehaviorValue("ForceGenericOnlyDevice", &v191) && v191 )
    {
      *((_DWORD *)this + 362) = 256;
    }
    else if ( (unsigned int)GetBehaviorValue("ForceComputeOnlyDevice", &v196) && v196 )
    {
      *((_DWORD *)this + 362) = 4096;
    }
    *((_QWORD *)this + 646) = NDXGI::CUMDAdapter::GetTotalL1ExclusiveMemorySize(v7);
    LODWORD(v196) = CDevice::DDIFlags();
    DriverInstance = NDXGI::CDevice::CreateDriverInstance(
                       *v2,
                       (char *)this + 8288,
                       this,
                       (char *)this + 5392,
                       v196,
                       *((_QWORD *)qword_180339C50 + 4),
                       (__int64)(*((_QWORD *)qword_180339C50 + 5) - *((_QWORD *)qword_180339C50 + 4)) >> 4);
    ThrowFailure(DriverInstance);
    *((_BYTE *)this + 2960) = 1;
    VersionedDeviceData::GetShaderCaps((CDevice *)((char *)this + 288));
    v188 = 0;
    VersionedDeviceData::GetD3D12ShaderModel((CDevice *)((char *)this + 288), &v188);
    if ( (int)VersionedDeviceData::GetD3D12OptionsInternal(
                (CDevice *)((char *)this + 288),
                (CDevice *)((char *)this + 356)) < 0 )
    {
      CJournal::RecordJournal(
        v10,
        -2005270496,
        (__int64)"Driver did not respond to D3D12DDICAPS_TYPE_D3D12_OPTIONS caps query",
        v11,
        0);
      ThrowFailure(-2005270496);
    }
    VersionedDeviceData::ValidateAndClampD3D12Options((CDevice *)((char *)this + 288), (CDevice *)((char *)this + 356));
    if ( *((_BYTE *)this + 296) < 0x32u
      || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1077, v13, (char *)this + 480, 4) < 0 )
    {
      *((_DWORD *)this + 120) = 0;
    }
    if ( *((_BYTE *)this + 296) < 0x33u
      || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1078, v13, (char *)this + 484, 16) < 0 )
    {
      *(_OWORD *)((char *)this + 484) = 0;
    }
    if ( *((_BYTE *)this + 296) < 0x35u
      || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1079, v13, (char *)this + 500, 8) < 0 )
    {
      *(_QWORD *)((char *)this + 500) = 0;
    }
    if ( *((_BYTE *)this + 296) < 0x3Au
      || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1080, v13, (char *)this + 508, 4) < 0 )
    {
      *((_DWORD *)this + 127) = 0;
    }
    v14 = *((_DWORD *)this + 76);
    if ( (v14 == 4096 || v14 == 256)
      && (*((_BYTE *)this + 296) < 0x3Du
       || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1081, v13, (char *)this + 512, 4) < 0) )
    {
      *((_DWORD *)this + 128) = 0;
    }
    v15 = (int *)((char *)this + 532);
    if ( *((_BYTE *)this + 296) < 0x3Fu
      || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1013, v13, (char *)this + 532, 4) < 0 )
    {
      *v15 = 0;
    }
    if ( *v15 >= 0 )
    {
      if ( *v15 > 10 )
        *v15 = 10;
    }
    else
    {
      CJournal::ReportDriverError(
        v12,
        -2005270496,
        "Driver filled out an invalid value in D3D12DDI_OPTIONS1_DATA_0103::WorkGraphsTier");
    }
    if ( *((_BYTE *)this + 296) < 0x45u
      || (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1087, v13, (char *)this + 536, 4) < 0 )
    {
      *((_DWORD *)this + 134) = 0;
    }
    v16 = (_DWORD *)((char *)this + 540);
    if ( *((_BYTE *)this + 296) < 0x46u
      || (v17 = (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1088, v13, (char *)this + 540, 4) < 0,
          v16 = (_DWORD *)((char *)this + 540),
          v17) )
    {
      *v16 = 10;
    }
    v18 = (CJournal *)(unsigned int)*v16;
    if ( (int)v18 >= 10 )
    {
      if ( (int)v18 >= 12 )
        *((_DWORD *)this + 135) = 11;
    }
    else
    {
      CJournal::ReportDriverError(
        v18,
        -2005270496,
        "Driver filled out an invalid value in D3D12DDI_D3D12_OPTIONS_110::ExecuteIndirectTier.");
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12TightAlignment>::GetImpl'::`2'::impl) )
      CDevice::GetTightAlignmentTierData(this, (CDevice *)((char *)this + 2740));
    v21 = (_DWORD *)((char *)this + 544);
    if ( *((_BYTE *)this + 296) < 0x4Eu
      || (v17 = (int)VersionedDeviceData::DDIGetCaps((char *)this + 288, 1095, v20, (char *)this + 544, 4) < 0,
          v21 = (_DWORD *)((char *)this + 544),
          v17) )
    {
      *v21 = 0;
    }
    if ( *v21 && *((int *)this + 140) < 105 )
    {
      CJournal::ReportDriverError(
        v19,
        -2005270496,
        "Driver filled out an invalid value in D3D12DDI_D3D12_OPTIONS_118::ShaderExecutionReorderingActuallyReorders.");
      *((_DWORD *)this + 136) = 0;
    }
    VersionedDeviceData::GetOptions0122((CDevice *)((char *)this + 288));
    NDXGI::CDevice::InitializeDeviceDDIs(*((NDXGI::CDevice **)this + 95));
    *((_QWORD *)this + 661) = *(_QWORD *)(*((_QWORD *)this + 95) + 656LL);
    v22 = *((_DWORD *)this + 718);
    if ( v22 == 1 )
    {
      DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z = (void ***)operator new(8u);
      if ( DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z )
      {
        v24 = &DDITraits<1,0>::`vftable';
LABEL_60:
        *DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z = v24;
LABEL_66:
        std::unique_ptr<TableDDIMap<0>>::reset(
          (char *)this + 5296,
          DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z);
        *((_QWORD *)this + 665) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1104LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 666) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1096LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 667) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1120LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 668) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1128LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 669) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1136LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 670) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1112LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 671) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1152LL))(*((_QWORD *)this + 662));
        *((_QWORD *)this + 672) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1160LL))(*((_QWORD *)this + 662));
        LOBYTE(v25) = 40;
        if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v25) )
          *((_QWORD *)this + 673) = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 662) + 1144LL))(*((_QWORD *)this + 662));
        VersionedDeviceData::ValidateCapsForFeatureLevel((CDevice *)((char *)this + 288));
        v26 = v194;
        if ( (int)NDXGI::CUMDAdapter::GetCaps(v194, 1005, 0, (char *)this + 2736, 4) < 0 )
        {
          CJournal::RecordJournal(
            v27,
            -2005270496,
            (__int64)"Driver did not respond to D3D12DDICAPS_TYPE_ARCHITECTURE_INFO caps query",
            v28,
            0);
          ThrowFailure(-2005270496);
        }
        VersionedDeviceData::QueryShaderModel66AndLater((CDevice *)((char *)this + 288), v188);
        LOBYTE(v29) = 11;
        if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v29) )
        {
          v188 = 0;
          Caps = NDXGI::CUMDAdapter::GetCaps(v26, 1062, 0, &v188, 4);
          v32 = operator&(127, v188, Caps);
          v35 = v32 == (_DWORD)v30;
          if ( v36 >= 0 && v35 )
          {
            *((_DWORD *)this + 687) = v30;
          }
          else
          {
            CJournal::RecordJournal(
              v33,
              -2005270496,
              (__int64)"Driver did not correctly respond to D3D12DDICAPS_TYPE_0023_UMD_BASED_COMMAND_QUEUE_PRIORITY caps query.",
              v34,
              0);
            ThrowFailure(-2005270496);
          }
        }
        LOBYTE(v30) = 26;
        if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v30)
          && (int)NDXGI::CUMDAdapter::GetCaps(v26, 1067, 0, (char *)this + 2836, 4) < 0 )
        {
          CJournal::ReportDriverError(
            v37,
            -2005270496,
            "Driver did not correctly respond to D3D12DDICAPS_TYPE_0050_HARDWARE_SCHEDULING_CAPS caps query.");
          ThrowFailure(-2005270496);
        }
        SystemInfo.dwOemId = *((_DWORD *)v26 + 112);
        SystemInfo.dwPageSize = 13;
        SystemInfo.lpMinimumApplicationAddress = (char *)this + 1560;
        SystemInfo.lpMaximumApplicationAddress = (LPVOID)4;
        v38 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                D3DKMTQueryAdapterInfo,
                "QueryAdapterInfo (KMTQAITYPE_DRIVERVERSION)",
                CLayeredObject<CCommandAllocator>::AddRef,
                &SystemInfo);
        v39 = NDXGI::CUMDAdapter::NTStatusToHResult(v38, 1);
        ThrowFailure(v39);
        CDevice::EnsureDXGKExclusiveEngineAccessSupport(this);
        if ( CDevice::NativeFencesKernelFeatureEnabled(this) && *((int *)this + 390) >= 3100 )
        {
          SystemInfo.dwOemId = *((_DWORD *)v26 + 112);
          SystemInfo.dwPageSize = 80;
          SystemInfo.lpMinimumApplicationAddress = (char *)this + 5308;
          SystemInfo.lpMaximumApplicationAddress = (LPVOID)4;
          v40 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                  D3DKMTQueryAdapterInfo,
                  "QueryAdapterInfo (KMTQAITYPE_WDDM_3_1_CAPS)",
                  CLayeredObject<CCommandAllocator>::AddRef,
                  &SystemInfo);
          v41 = NDXGI::CUMDAdapter::NTStatusToHResult(v40, 1);
          ThrowFailure(v41);
          if ( (*((_BYTE *)this + 5308) & 1) != 0
            && (LOBYTE(v42) = 72, (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater(
                                                     (char *)this + 288,
                                                     v42)) )
          {
            wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12_NativeFence>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_D3D12_NativeFence>::GetImpl'::`2'::impl);
            v26 = v194;
            if ( (int)NDXGI::CUMDAdapter::GetCaps(v194, 1093, 0, (char *)this + 2840, 4) < 0 )
            {
              CJournal::ReportDriverError(
                v43,
                -2005270496,
                "Driver did not correctly respond to D3D12DDICAPS_TYPE_0112_NATIVE_FENCE_SUPPORT caps query.");
              ThrowFailure(-2005270496);
            }
          }
          else
          {
            v26 = v194;
          }
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ApplicationSpecificDriverState>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ApplicationSpecificDriverState>::GetImpl'::`2'::impl) )
        {
          LOBYTE(v44) = 73;
          if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v44) )
          {
            if ( (int)NDXGI::CUMDAdapter::GetCaps(v26, 1094, 0, (char *)this + 2844, 4) < 0 )
            {
              CJournal::ReportDriverError(
                v45,
                -2005270496,
                "Driver did not correctly respond to D3D12DDI_APPLICATION_SPECIFIC_DRIVER_STATE_113 caps query.");
              ThrowFailure(-2005270496);
            }
          }
        }
        if ( *((int *)this + 362) >= 40960 )
        {
          for ( i = 0; ; i = v189 + 1 )
          {
            v189 = i;
            Format = D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetFormat(i);
            v48 = Format;
            if ( Format == DXGI_FORMAT_FORCE_UINT )
              goto LABEL_122;
            if ( (unsigned __int8)CD3D11FormatHelper::APIFormatExists(
                                    (unsigned int)Format,
                                    *((unsigned int *)this + 362),
                                    *((unsigned int *)this + 363))
              && (unsigned int)D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetTypeLevel((unsigned int)v48) == -2 )
            {
              break;
            }
LABEL_121:
            ;
          }
          LODWORD(v201) = 0;
          v49 = (_QWORD *)CDevice::DDIHandle(this, v202);
          TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,0,void>,void,void,D3D10DDI_HDEVICE,enum DXGI_FORMAT,unsigned int *>::Call<CDevice>(
            v50,
            *v49,
            (unsigned int)v48,
            &v201);
          v51 = CD3D11FormatHelper::MultisampleRenderTargetSupport(
                  (unsigned int)v48,
                  *((unsigned int *)this + 362),
                  *((unsigned int *)this + 363));
          if ( (v201 & 8) != 0
            && v51 == -1
            && (unsigned int)D3D12_PROPERTY_LAYOUT_FORMAT_TABLE::GetLayout((unsigned int)v48) == -1 )
          {
            CJournal::RecordJournal(v52, -2005270496, (__int64)"Driver claimed MSAA support when it shouldn't", v53, 0);
            ThrowFailure(-2005270496);
          }
          for ( j = 2; ; j = v57 + 1 )
          {
            v192 = j;
            if ( j >= 0x20 )
              break;
            v188 = 0;
            v55 = (_QWORD *)CDevice::DDIHandle(this, v203);
            LODWORD(v185) = 0;
            TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,1,void>,void,void,D3D10DDI_HDEVICE,enum DXGI_FORMAT,unsigned int,enum D3D12DDI_MULTISAMPLE_QUALITY_LEVEL_FLAGS,unsigned int *>::Call<CDevice>(
              (_DWORD)this,
              *v55,
              v48,
              v56,
              (__int64)v185,
              (__int64)&v188);
            v57 = v192;
            v225[v192] = v188;
          }
          FormatCastSet = (_DWORD *)CD3D11FormatHelper::GetFormatCastSet(
                                      (unsigned int)v48,
                                      *((unsigned int *)this + 362),
                                      *((unsigned int *)this + 363));
          v191 = FormatCastSet;
          v190 = 0;
          v186 = 0;
          while ( 1 )
          {
            if ( !*FormatCastSet )
              goto LABEL_121;
            if ( *FormatCastSet != v48 )
              break;
LABEL_120:
            v191 = ++FormatCastSet;
          }
          LODWORD(v198) = 0;
          v59 = (_QWORD *)CDevice::DDIHandle(this, &v199);
          TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,0,void>,void,void,D3D10DDI_HDEVICE,enum DXGI_FORMAT,unsigned int *>::Call<CDevice>(
            v60,
            *v59,
            v61,
            &v198);
          LODWORD(v195) = (unsigned __int8)v198 & 8;
          v193 = (_DWORD)v195 != 0;
          v62 = CD3D11FormatHelper::MultisampleRenderTargetSupport(
                  *(unsigned int *)v191,
                  *((unsigned int *)this + 362),
                  *((unsigned int *)this + 363));
          if ( v63 )
          {
            if ( v62 == -1 )
              goto LABEL_110;
          }
          else if ( v62 == -1 )
          {
            goto LABEL_112;
          }
          if ( !v186 )
          {
            v190 = v193;
            v186 = 1;
LABEL_112:
            v64 = 2;
            while ( 1 )
            {
              v192 = v64;
              if ( v64 >= 0x20 )
                break;
              v188 = 0;
              v65 = (_QWORD *)CDevice::DDIHandle(this, &v205);
              LODWORD(v185) = 0;
              TableFunctionTraits<0>::Detail::InvokerImpl<TableFunctionTraitsImpl<0>::FunctionTraits<83,1,void>,void,void,D3D10DDI_HDEVICE,enum DXGI_FORMAT,unsigned int,enum D3D12DDI_MULTISAMPLE_QUALITY_LEVEL_FLAGS,unsigned int *>::Call<CDevice>(
                (_DWORD)this,
                *v65,
                *v66,
                v192,
                (__int64)v185,
                (__int64)&v188);
              if ( (_DWORD)v195 )
              {
                v69 = (unsigned int)v225[v192];
                if ( v188 != (_DWORD)v69 )
                {
                  CJournal::RecordJournal(v69, -2005270496, (__int64)"MSAA quality for parent != child", v68, 0);
                  ThrowFailure(-2005270496);
                }
              }
              else if ( v188 )
              {
                CJournal::RecordJournal(v67, -2005270496, (__int64)"MSAA quality reported to be 0", v68, 0);
                ThrowFailure(-2005270496);
              }
              v64 = v192 + 1;
              FormatCastSet = v191;
            }
            goto LABEL_120;
          }
          if ( v190 == v193 )
            goto LABEL_112;
LABEL_110:
          ThrowFailure(-2005270496);
          FormatCastSet = v191;
          goto LABEL_112;
        }
LABEL_122:
        *((_DWORD *)this + 176) |= 1u;
        CDevice::MakeResidentCaps(this);
        v70 = v194;
        if ( NDXGI::CUMDAdapter::IsWARP(v194) )
        {
          *((_DWORD *)this + 176) |= 1u;
          *((_BYTE *)this + 2936) = 1;
          *((_QWORD *)this + 625) = D3DXPlat::unique_module::proc_address<void (*)(UMDevice *,void *)>((char *)v70 + 384);
        }
        v71 = 0;
        v198 = 0;
        v189 = 0;
        LODWORD(v199) = *((_DWORD *)v194 + 112);
        DWORD1(v199) = 30;
        *((_QWORD *)&v199 + 1) = &v189;
        v200 = 4;
        v72 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                D3DKMTQueryAdapterInfo,
                "QueryAdapterInfo (KMTQAITYPE_PHYSICALADAPTERCOUNT)",
                CLayeredObject<CCommandAllocator>::AddRef,
                &v199);
        v73 = NDXGI::CUMDAdapter::NTStatusToHResult(v72, 1);
        ThrowFailure(v73);
        v76 = v189;
        v192 = v189;
        if ( v189 > 0x20 )
        {
          CJournal::RecordJournal(v74, -2005270496, (__int64)"More than 32 nodes are exposed at the API", v75, 0);
          ThrowFailure(-2005270496);
          v76 = v192;
        }
        v201 = v76;
        std::vector<unsigned int>::resize((char *)this + 5624, v76);
        CDevice::VersionedQueryNodeMap(this, v192, *((unsigned int **)this + 703));
        v78 = (void *)std::count_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_unsigned_int_______lambda_dad867b8445591ece85a0c3c276f96b0___(
                        *((_QWORD *)this + 703),
                        *((_QWORD *)this + 704));
        v191 = v78;
        if ( !(_DWORD)v78 )
        {
          CJournal::RecordJournal(v77, -2005270496, (__int64)"No nodes are exposed at the API", (__int64)v78, 0);
          ThrowFailure(-2005270496);
        }
        v79 = 0;
        if ( v192 )
        {
          v80 = (char *)this + 5624;
          while ( 1 )
          {
            v81 = (_DWORD *)std::vector<unsigned int>::operator[](v80, v79);
            if ( *v81 != v82 )
              break;
            v79 = v82 + 1;
            if ( v79 >= v84 )
              goto LABEL_135;
          }
          if ( (unsigned int)v83 > 1 )
          {
            CJournal::RecordJournal(
              (__int64)v80,
              -2005270496,
              (__int64)"Driver specified a non-identity node remapping with more than 1 API-visible node",
              v83,
              0);
            ThrowFailure(-2005270496);
          }
        }
LABEL_135:
        std::vector<unsigned int>::resize((char *)this + 5600, (unsigned int)v191);
        v85 = 0;
        v86 = v191;
        if ( (_DWORD)v191 )
        {
          v87 = (char *)this + 5600;
          do
          {
            *(_DWORD *)std::vector<unsigned int>::operator[](v87, (unsigned int)v85) = -1;
            v85 = (unsigned int)(v88 + 1);
          }
          while ( (unsigned int)v85 < (unsigned int)v86 );
        }
        for ( k = 0; ; k = v188 + 1 )
        {
          v188 = k;
          v90 = std::vector<unsigned int>::size((char *)this + 5624, k, v86, v85);
          if ( v91 >= v90 )
            break;
          v92 = *(unsigned int *)std::vector<unsigned int>::operator[]((char *)this + 5624, v91);
          LODWORD(v195) = v92;
          if ( (_DWORD)v92 != -1 )
          {
            if ( (unsigned int)v92 >= (unsigned int)v86 )
            {
              CJournal::RecordJournal(
                v93,
                -2005270496,
                (__int64)"Driver specified invalid API index in node remapping",
                v85,
                0);
              ThrowFailure(-2005270496);
              v92 = (unsigned int)v195;
            }
            v195 = v92;
            if ( *(_DWORD *)std::vector<unsigned int>::operator[]((char *)this + 5600, v92) != -1 )
            {
              CJournal::RecordJournal(
                v94,
                -2005270496,
                (__int64)"Driver specified duplicate API index in node remapping",
                v95,
                0);
              ThrowFailure(-2005270496);
            }
            v96 = (unsigned int *)std::vector<unsigned int>::operator[]((char *)this + 5600, v195);
            *v96 = v188;
            v86 = v191;
          }
        }
        CDevice::AttemptToLoadShaderCacheDdiTable(this);
        if ( CDevice::IsShaderCachingFeatureVersionOrLater(this, 2u) )
        {
          SystemInfo.dwOemId = *(_DWORD *)std::vector<unsigned int>::operator[](v97, 0);
          memset(&SystemInfo.dwPageSize, 0, 24);
          LODWORD(v205) = *((_DWORD *)v194 + 112);
          DWORD1(v205) = 31;
          *((_QWORD *)&v205 + 1) = &SystemInfo;
          *(_QWORD *)&v206 = 28;
          v199 = v205;
          v200 = 28;
          CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
            D3DKMTQueryAdapterInfo,
            "QueryAdapterInfo (KMTQAITYPE_PHYSICALADAPTERDEVICEIDS)",
            CLayeredObject<CCommandAllocator>::AddRef,
            &v199);
          memset_0(v220, 0, 0x120u);
          ShaderCacheABIInfo = CDevice::GetShaderCacheABIInfo(
                                 this,
                                 (struct D3D12_FEATURE_DATA_SHADERCACHE_ABI_SUPPORT *)v220);
          ThrowFailure(ShaderCacheABIInfo);
          SShaderCacheDriverIdentity::SShaderCacheDriverIdentity((SShaderCacheDriverIdentity *)v209);
          std::wstring::operator=(v209, v220);
          v210 = v221;
          v211 = v222;
          v212 = v223;
          v213 = v224;
          RegisteredApp = NDXGI::CUMDAdapter::GetRegisteredApp(*(_QWORD *)(*((_QWORD *)this + 95) + 40LL), &v191);
          ATL::CComPtr<ID3DShaderCacheApplication>::operator=(&v198, RegisteredApp);
          ATL::CComPtrBase<ID3DShaderCacheInstallerFactory>::~CComPtrBase<ID3DShaderCacheInstallerFactory>(&v191);
          SShaderCacheApplicationIdentity::SShaderCacheApplicationIdentity((SShaderCacheApplicationIdentity *)v214);
          v219 = v224;
          v71 = v198;
          if ( v198 )
          {
            v205 = 0;
            v206 = 0;
            v207 = 0;
            v100 = (*(__int64 (__fastcall **)(struct ID3DShaderCacheApplication *, __int128 *))(*(_QWORD *)v198 + 32LL))(
                     v198,
                     &v205);
            ThrowFailure(v100);
            std::wstring::operator=(v214, v205);
            std::wstring::operator=(v215, *((_QWORD *)&v205 + 1));
            v216 = v206;
            std::wstring::operator=(v217, *((_QWORD *)&v206 + 1));
            v218 = v207;
          }
          SShaderCacheApplicationIdentity::SShaderCacheApplicationIdentity(
            (SShaderCacheApplicationIdentity *)v225,
            (const struct SShaderCacheApplicationIdentity *)v214);
          v101 = *(_BYTE **)(*((_QWORD *)this + 95) + 40LL);
          v191 = v101;
          if ( v101[136] )
          {
            std::wstring::operator=(v225, v101 + 144);
            std::wstring::operator=(v226, (char *)v191 + 176);
            v227 = *((_QWORD *)v191 + 26);
            std::wstring::operator=(v228, (char *)v191 + 216);
            v229 = *((_QWORD *)v191 + 31);
          }
          CShaderCacheAdapter::Init(
            (CDevice *)((char *)this + 5648),
            *(struct _LUID *)((char *)this + 6744),
            (const struct _D3DKMT_DEVICE_IDS *)&SystemInfo.dwPageSize,
            (const struct SShaderCacheDriverIdentity *)v209,
            (const struct SShaderCacheApplicationIdentity *)v225,
            (const struct SShaderCacheApplicationIdentity *)v214);
          D3D12ShaderCacheApplicationIdentity::~D3D12ShaderCacheApplicationIdentity((D3D12ShaderCacheApplicationIdentity *)v225);
          D3D12ShaderCacheApplicationIdentity::~D3D12ShaderCacheApplicationIdentity((D3D12ShaderCacheApplicationIdentity *)v214);
          std::wstring::_Tidy_deallocate(v209);
        }
        else
        {
          v105 = lambda_1414c748bcfcc4c5f68c1aa28d5e8d9e_::_lambda_1414c748bcfcc4c5f68c1aa28d5e8d9e_(&v205, this, &jj);
          std::function_void___cdecl_unsigned_int__D3DKMT_DEVICE_IDS____::function_void___cdecl_unsigned_int__D3DKMT_DEVICE_IDS______lambda_1414c748bcfcc4c5f68c1aa28d5e8d9e__0_(
            v209,
            v105);
          v109 = std::vector<unsigned int>::size(v108, v106, v107, v108);
          v110 = CShaderCacheAdapter::Init(
                   (char *)this + 5648,
                   *((_QWORD *)this + 843),
                   *(_QWORD *)(*(_QWORD *)(*((_QWORD *)this + 95) + 40LL) + 384LL),
                   v109,
                   v209);
          ThrowFailure(v110);
          std::function<PSVSignatureElement (unsigned int)>::~function<PSVSignatureElement (unsigned int)>(v209);
        }
        v111 = this;
        if ( v192 <= 1 )
        {
          ImplicitPhysicalAdapterMask = 0;
        }
        else
        {
          ImplicitPhysicalAdapterMask = CDevice::VersionedGetImplicitPhysicalAdapterMask(this);
          v111 = this;
        }
        *((_DWORD *)v111 + 708) = ImplicitPhysicalAdapterMask;
        v190 = (unsigned __int64)std::vector<unsigned int>::size((char *)this + 5600, v102, v103, v104) > 1;
        v115 = *((_DWORD *)this + 92);
        if ( v115 )
        {
          if ( v115 > 4 )
          {
            CJournal::RecordJournal(
              v113,
              -2005270496,
              (__int64)"Driver specified unrecognized cross-node sharing tier",
              v114,
              0);
            ThrowFailure(-2005270496);
            LOBYTE(v115) = 0;
          }
          else
          {
            LOBYTE(v115) = 1;
          }
        }
        if ( v190 != (_BYTE)v115 )
        {
          CJournal::RecordJournal(
            v113,
            -2005270496,
            (__int64)"Driver specified incompatible cross-node sharing tier",
            v114,
            0);
          ThrowFailure(-2005270496);
        }
        CDevice::CacheHeapCaps(this);
        v119 = std::vector<unsigned int>::size((char *)this + 5600, v116, v117, v118);
        std::vector<std::array<enum D3D12DDICAPS_USERMODE_SUBMISSION_SUPPORT_FLAGS_0123,7>>::resize(
          (char *)this + 2848,
          v119);
        if ( *((_DWORD *)this + 710) )
          CDevice::UsermodeSubmissionKernelFeatureEnabled(this);
        v120 = *((_QWORD *)this + 357);
        for ( m = *((_QWORD *)this + 356); m != v120; m = v122 + 28 )
        {
          LODWORD(v195) = 0;
          std::array<enum D3D12DDICAPS_USERMODE_SUBMISSION_SUPPORT_FLAGS_0123,7>::fill(m, &v195);
        }
        CDevice::AttemptToLoadRenderPassDdiTable(this);
        CDevice::AttemptToLoadCpuResolveQueryDdiTable(this);
        CDevice::AttemptToLoadGuidTextureLayoutDdiTable(this);
        *((_DWORD *)this + 395) = *((_DWORD *)this + 102);
        *((_DWORD *)this + 396) = CDevice::GetSharedResourceCompatibilityTier(this);
        *((_DWORD *)this + 398) = *((_DWORD *)this + 104);
        *((_DWORD *)this + 400) = *((_DWORD *)this + 106);
        *((_DWORD *)this + 403) = *((_DWORD *)this + 107);
        *((_DWORD *)this + 402) = *((_DWORD *)this + 108);
        *((_DWORD *)this + 401) = *((_DWORD *)this + 109);
        *((_DWORD *)this + 404) = *((_DWORD *)this + 110);
        *((_DWORD *)this + 406) = *((_DWORD *)this + 112);
        *((_DWORD *)this + 407) = *((_DWORD *)this + 113);
        *((_DWORD *)this + 408) = 1;
        *((_DWORD *)this + 409) = CDevice::MeshShaderPipelineStatisticsSupported(v123);
        *((_DWORD *)this + 410) = CDevice::MeshShaderSupportsFullRangeRenderTargetArrayIndex(this);
        *((_DWORD *)this + 411) = *((_DWORD *)this + 152);
        *((_DWORD *)this + 412) = *((_DWORD *)this + 153);
        *((_DWORD *)this + 413) = *((_DWORD *)this + 154);
        *((_DWORD *)this + 414) = *((_DWORD *)this + 155);
        *((_DWORD *)this + 415) = CDevice::VariableRateShadingSumCombinerSupported(this);
        *((_DWORD *)this + 416) = VersionedDeviceData::MeshShaderPerPrimitiveShadingRateSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 417) = *((_DWORD *)this + 156);
        *((_DWORD *)this + 418) = CDevice::MSPrimitivesPipelineStatisticIncludesCulledPrimitives(this);
        *((_DWORD *)this + 419) = CDevice::DriverSupportsEnhancedBarriers(v124);
        *((_DWORD *)this + 420) = CDevice::RelaxedFormatCastingSupported(this);
        *((_DWORD *)this + 421) = CDevice::UnrestrictedBufferTextureCopyPitchSupported(this);
        *((_DWORD *)this + 422) = VersionedDeviceData::UnrestrictedVertexElementAlignmentSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 423) = CDevice::InvertedViewportHeightFlipsYSupported(this);
        *((_DWORD *)this + 424) = CDevice::InvertedViewportDepthFlipsZSupported(this);
        *((_DWORD *)this + 425) = CDevice::TextureCopyBetweenDimensionsSupported(this);
        *((_DWORD *)this + 426) = VersionedDeviceData::AlphaBlendFactorSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 427) = VersionedDeviceData::AdvancedTextureOpsSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 428) = VersionedDeviceData::WriteableMSAATexturesSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 429) = VersionedDeviceData::IndependentFrontAndBackStencilRefMaskSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 431) = VersionedDeviceData::DynamicIndexBufferStripCutSupported((CDevice *)((char *)this + 288));
        *((_DWORD *)this + 430) = CDevice::TriangleFanSupported(this);
        v187 = CDevice::GPUUploadHeapDriverSupported(this);
        v125 = CDevice::GPUUploadHeapOSSupported(this) || CDevice::GPUUploadHeapsEnabledOnUnsupportedOS(this);
        v126 = v187 && v125;
        *((_DWORD *)this + 433) = v126;
        *((_DWORD *)this + 432) = VersionedDeviceData::DynamicIndexBufferStripCutSupported((CDevice *)((char *)this + 288));
        v127 = VersionedDeviceData::NonNormalizedCoordinateSamplersSupported((CDevice *)((char *)this + 288));
        *((_QWORD *)this + 217) = v127;
        *((_DWORD *)this + 436) = CDevice::IsRenderPassSupported((CDevice *)v127);
        *((_DWORD *)this + 446) = CDevice::ComputeOnlyCustomHeapSupported(this);
        LOBYTE(v128) = 62;
        if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v128) )
        {
          VersionedDeviceData::GetOptions0102(v129);
          if ( *((int *)this + 362) >= 45056 )
          {
            *((_DWORD *)this + 437) = 1;
            *((_DWORD *)this + 438) = VersionedDeviceData::SupportedSampleCountsWithNoOutputs((CDevice *)((char *)this + 288));
            *((_DWORD *)this + 441) = 1;
            *((_DWORD *)this + 439) = 1;
            *((_DWORD *)this + 442) = 1;
            *((_DWORD *)this + 443) = *((_DWORD *)this + 130);
            *((_DWORD *)this + 444) = *((_DWORD *)this + 131);
          }
          *((_DWORD *)this + 445) = *((_DWORD *)this + 132);
          *((_DWORD *)this + 370) |= 8u;
        }
        if ( *((int *)this + 390) >= 3000 )
          *((_DWORD *)this + 447) = 1;
        *((_DWORD *)this + 448) = CDevice::RecreateAtTier(this);
        *((_DWORD *)this + 450) = *((_DWORD *)this + 135);
        v130 = 0;
        if ( *((int *)this + 133) >= 10 )
          v130 = *((_DWORD *)this + 133);
        *((_DWORD *)this + 449) = v130;
        v131 = *((int *)this + 140) >= 104 && (*((int *)this + 362) >= 49664 || *((_DWORD *)this + 158));
        *((_DWORD *)this + 452) = v131;
        v132 = *((int *)this + 140) >= 104 && *((_DWORD *)this + 157);
        *((_DWORD *)this + 451) = v132;
        *((_DWORD *)this + 453) = *((_DWORD *)this + 136);
        *((_DWORD *)this + 454) = CDevice::IsViewCreationByteOffsetSupportedAndImplemented(this);
        *((_DWORD *)this + 455) = *((_DWORD *)this + 137);
        *((_DWORD *)this + 456) = *((_DWORD *)this + 138);
        *((_DWORD *)this + 457) = CDevice::TightAlignmentTier(this);
        LOBYTE(v133) = 61;
        if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v133)
          && CDevice::IsRenderPassSupported(v134) )
        {
          if ( !*((_DWORD *)this + 105) )
            goto LABEL_313;
          if ( !CDevice::IsRenderPassFeatureVersionOrLater(this, 1u) )
          {
            CJournal::ReportDriverError(
              v135,
              "Driver reported TIER_1 or greater Render Pass support despite not implementing DDI table.");
            ThrowFailure(-2005270496);
          }
          if ( !*((_DWORD *)this + 105) )
          {
LABEL_313:
            if ( CDevice::IsRenderPassFeatureVersionOrLater(this, 1u) )
            {
              CJournal::ReportDriverError(v136, "Driver reported TIER_NOT_SUPPORTED despite implementing DDI table.");
              ThrowFailure(-2005270496);
            }
          }
          v137 = *((_DWORD *)this + 105);
        }
        else
        {
          v137 = 0;
        }
        *((_DWORD *)this + 399) = v137;
        *((_BYTE *)this + 1488) = *((_DWORD *)this + 92) >= 4;
        jj = this;
        std::function_bool___cdecl_void__::operator___lambda_63b45e58626d2836ecbdc101d5df4f65__0_(
          (char *)this + 1496,
          &jj);
        *((_DWORD *)this + 361) = 0;
        *((_BYTE *)this + 1832) = CDevice::IsImplicitHeapFlagSupported(this);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12Displayable>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_D3D12Displayable>::GetImpl'::`2'::impl) )
        {
          *((_BYTE *)this + 1489) = 1;
          LODWORD(v195) = *((_DWORD *)this + 1416);
          v205 = 0;
          *(_QWORD *)&v206 = 0;
          LODWORD(v205) = *((_DWORD *)v194 + 112);
          DWORD1(v205) = 77;
          v189 = 0;
          LODWORD(v206) = 4;
          *((_QWORD *)&v205 + 1) = &v189;
          v138 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                   D3DKMTQueryAdapterInfo,
                   "QueryAdapterInfo (KMTQAITYPE_WDDM_3_0_CAPS)",
                   CLayeredObject<CCommandAllocator>::AddRef,
                   &v205);
          if ( (int)NDXGI::CUMDAdapter::NTStatusToHResult(v138, 1) >= 0 )
          {
            v139 = *((_DWORD *)this + 390);
            if ( v139 >= 2700 && (v189 & 8) != 0 && ((_DWORD)v195 != 4098 || v139 >= 3100) )
              *((_BYTE *)this + 1490) = 1;
          }
          else
          {
            *((_BYTE *)this + 1490) = 0;
          }
          if ( *((_BYTE *)this + 1490) && *((_BYTE *)this + 1489) )
            *((_BYTE *)this + 1491) = 1;
        }
        CSynchronizationContext::Init((CDevice *)((char *)this + 5144), this);
        std::vector<CPagingQueue>::resize((char *)this + 5016, v201);
        std::vector<D3D12DDI_HRTPAGINGQUEUE>::resize((char *)this + 5040, v201);
        for ( n = 0; ; n = v189 + 1 )
        {
          v189 = n;
          if ( n >= v192 )
            break;
          jj = (CDevice *)n;
          v141 = (CPagingQueue *)std::vector<CPagingQueue>::operator[]((char *)this + 5016, n);
          CPagingQueue::Init(v141, this, v142);
          v143 = std::vector<CPagingQueue>::operator[]((char *)this + 5016, jj);
          v144 = (_QWORD *)std::vector<D3D12DDI_HRTPAGINGQUEUE>::operator[]((char *)this + 5040, jj, v143);
          *v144 = v145;
        }
        CDevice::InitializePsoDatabase(this);
        CDevice::CreateDefaults((struct ID3D12Device *)this, v71);
        SystemInfo.dwOemId = *((_DWORD *)v194 + 112);
        SystemInfo.dwPageSize = 15;
        SystemInfo.lpMinimumApplicationAddress = (char *)this + 5312;
        SystemInfo.lpMaximumApplicationAddress = (LPVOID)4;
        v146 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                 D3DKMTQueryAdapterInfo,
                 "QueryAdapterInfo (KMTQAITYPE_ADAPTERTYPE)",
                 CLayeredObject<CCommandAllocator>::AddRef,
                 &SystemInfo);
        v147 = NDXGI::CUMDAdapter::NTStatusToHResult(v146, 1);
        ThrowFailure(v147);
        v148 = (*((_DWORD *)this + 1328) & 2) != 0;
        *((_BYTE *)this + 5316) = v148;
        if ( v148 )
        {
          v189 = 0;
          SystemInfo.dwOemId = *((_DWORD *)v194 + 112);
          SystemInfo.dwPageSize = 19;
          SystemInfo.lpMinimumApplicationAddress = &v189;
          SystemInfo.lpMaximumApplicationAddress = (LPVOID)4;
          v149 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                   D3DKMTQueryAdapterInfo,
                   "QueryAdapterInfo (KMTQAITYPE_DIRECTFLIP_SUPPORT)",
                   CLayeredObject<CCommandAllocator>::AddRef,
                   &SystemInfo);
          v150 = NDXGI::CUMDAdapter::NTStatusToHResult(v149, 1);
          ThrowFailure(v150);
          *((_BYTE *)this + 5316) = v189 != 0;
        }
        v151 = (_QWORD *)((char *)this + 1568);
        LODWORD(v199) = *((_DWORD *)v194 + 112);
        DWORD1(v199) = 24;
        *((_QWORD *)&v199 + 1) = (char *)this + 5304;
        v200 = 4;
        v152 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                 D3DKMTQueryAdapterInfo,
                 "QueryAdapterInfo (KMTQAITYPE_WDDM_2_0_CAPS)",
                 CLayeredObject<CCommandAllocator>::AddRef,
                 &v199);
        v153 = NDXGI::CUMDAdapter::NTStatusToHResult(v152, 1);
        ThrowFailure(v153);
        if ( (*((_BYTE *)this + 5304) & 4) != 0 )
        {
          memset(&SystemInfo, 0, sizeof(SystemInfo));
          GetSystemInfo(&SystemInfo);
          _BitScanReverse64(
            &v154,
            (char *)SystemInfo.lpMaximumApplicationAddress - (char *)SystemInfo.lpMinimumApplicationAddress);
          *((_DWORD *)this + 393) = v154;
          ++*((_DWORD *)this + 393);
        }
        else
        {
          *((_DWORD *)this + 393) = 64;
        }
        if ( (*((_BYTE *)this + 5304) & 2) != 0 )
        {
          for ( ii = 0; ; ii = v189 + 1 )
          {
            v189 = ii;
            if ( ii >= v192 )
              break;
            LODWORD(v205) = ii;
            *(_QWORD *)((char *)&v205 + 4) = 0;
            SystemInfo.dwOemId = *((_DWORD *)v194 + 112);
            SystemInfo.dwPageSize = 34;
            SystemInfo.lpMinimumApplicationAddress = &v205;
            SystemInfo.lpMaximumApplicationAddress = (LPVOID)12;
            v199 = *(_OWORD *)&SystemInfo.dwOemId;
            v200 = 12;
            v156 = CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(
                     D3DKMTQueryAdapterInfo,
                     "QueryAdapterInfo (KMTQAITYPE_QUERY_GPUMMU_CAPS)",
                     CLayeredObject<CCommandAllocator>::AddRef,
                     &v199);
            if ( (int)NDXGI::CUMDAdapter::NTStatusToHResult(v156, 1) < 0 )
            {
              *v151 = 0x2600000026LL;
              break;
            }
            *((_DWORD *)this + 393) = *(_DWORD *)std::min<unsigned int>((char *)this + 1572, (char *)&v205 + 8);
          }
        }
        *((_DWORD *)this + 392) = *((_DWORD *)this + 393);
        v157 = (CDevice *)*((_QWORD *)this + 700);
        v158 = (CDevice *)*((_QWORD *)this + 701);
        for ( jj = v158; ; v158 = jj )
        {
          v191 = v157;
          if ( v157 == v158 )
            break;
          LODWORD(v195) = *(_DWORD *)v157;
          v188 = 0;
          v159 = NDXGI::CUMDAdapter::GetCaps(v194, 1009, &v195, &v188, 4);
          if ( v159 >= 0 )
          {
            if ( v188 )
            {
              *(_DWORD *)v151 = *(_DWORD *)std::min<unsigned int>((char *)this + 1568, &v188);
            }
            else
            {
              CJournal::ReportDriverError(v160, "Driver set MaxGPUVirtualAddressBitsPerResource to 0.\n");
              CJournal::RecordJournal(v162, -2005270496, (__int64)"MaxGPUVirtualAddressBitsPerResource error", v163, 0);
              ThrowFailure(-2005270496);
            }
          }
          else
          {
            CJournal::RecordJournal((__int64)v160, v159, (__int64)"GetCaps (D3D12DDICAPS_TYPE_GPUVA_CAPS)", v161, 0);
          }
          v157 = (CDevice *)((char *)v191 + 4);
        }
        *((_DWORD *)this + 2024) = CDevice::GetWriteBufferImmediateSupportFlags(this);
        if ( *((int *)this + 362) >= 49664 )
        {
          if ( *((int *)this + 140) < 101 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for shader model at least 6_5",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 106) < 11 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for raytracing tier at least 1.1",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 107) < 2 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for variable rate shading tier at least 2",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 112) < 10 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for mesh shader tier at least 1",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 113) < 90 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for sampler feedback tier at least 0.9",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 89) < 3 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for resource binding tier at least 3",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 91) < 3 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for tiled resource tier at least 3",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((int *)this + 90) < 3 )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for conservative rasterization tier at least 3",
              v165,
              0);
            ThrowFailure(-2005270496);
          }
          if ( VersionedDeviceData::DriverRootSignatureVersion((CDevice *)((char *)this + 288)) < D3D_ROOT_SIGNATURE_VERSION_1_1 )
          {
            CJournal::RecordJournal(
              v166,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for root signature version at least 1.1",
              v167,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !*((_DWORD *)this + 96) )
          {
            CJournal::RecordJournal(
              v166,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for depth bounds testing",
              v167,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !(unsigned int)operator&(*((unsigned int *)this + 2024), 1, *((unsigned int *)this + 2024))
            || !(unsigned int)operator&((unsigned int)v169, 4, v169)
            || !(unsigned int)operator&((unsigned int)v171, 2, v171) )
          {
            CJournal::RecordJournal(
              v168,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for direct, compute, and bundle WriteBufferImmediate support.",
              v170,
              0);
            ThrowFailure(-2005270496);
          }
          if ( *((_DWORD *)this + 393) < 0x28u || *((_DWORD *)this + 392) < 0x28u )
          {
            CJournal::RecordJournal(
              v168,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report at least 40 bits of GPU virtual address bits",
              v170,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !VersionedDeviceData::WaveOpsSupported((CDevice *)((char *)this + 288)) )
          {
            CJournal::RecordJournal(
              v172,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for wave ops",
              v173,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !*((_DWORD *)this + 94) )
          {
            CJournal::RecordJournal(
              v172,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for output merger logic ops",
              v173,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !*((_DWORD *)this + 93) )
          {
            CJournal::RecordJournal(
              v172,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for the VPAndRTArrayIndexFromAnyShaderFeedingRa"
                       "sterizerSupportedWithoutGSEmulation capability",
              v173,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !*((_DWORD *)this + 98) )
          {
            CJournal::RecordJournal(
              v172,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for the CopyQueueTimestampQueriesSupported capability",
              v173,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !CDevice::CastingFullyTypedFormatsSupported(this) )
          {
            CJournal::RecordJournal(
              v174,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for the CastingFullyTypedFormatSupported capability",
              v175,
              0);
            ThrowFailure(-2005270496);
          }
          if ( !VersionedDeviceData::Int64ShaderOpsSupported((CDevice *)((char *)this + 288)) )
          {
            CJournal::RecordJournal(
              v164,
              -2005270496,
              (__int64)"FL12.2+ driver incorrectly did not report support for 64-bit integer shader ops",
              v176,
              0);
            ThrowFailure(-2005270496);
          }
        }
        v177 = *((_DWORD *)this + 403);
        if ( v177 )
        {
          v164 = *((unsigned int *)this + 404);
          if ( (_DWORD)v164 )
          {
            if ( (((_DWORD)v164 - 8) & 0xFFFFFFE7) != 0 || (_DWORD)v164 == 24 )
            {
              CJournal::ReportDriverError(
                (CJournal *)v164,
                "Driver reported VRS TIER_1 or greater, but did not provide a valid tile size.");
              ThrowFailure(-2005270496);
            }
          }
          else if ( v177 == 2 )
          {
            CJournal::ReportDriverError(
              (CJournal *)v164,
              "Driver reported VRS TIER_2, but did not provide a valid nonzero tile size.");
          }
        }
        CD3D12TelemetryHelper::LogImplicitMultiGPU(v164, this, (unsigned int)v196, *((unsigned int *)this + 708));
        *((_DWORD *)this + 706) = CDevice::GetDDIDescriptorHandleIncrementSize(this, D3D12_DESCRIPTOR_HEAP_TYPE_RTV);
        *((_DWORD *)this + 707) = CDevice::GetDescriptorHandleIncrementSize(this, D3D12_DESCRIPTOR_HEAP_TYPE_RTV);
        v191 = 0;
        v180 = CDevice::CreateCommandPoolImpl(this, v178, v179, &v191);
        ThrowFailure(v180);
        v181 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v191)(
                 v191,
                 &GUID_ffffffff_335a_4bc5_9de9_43d8fb7777ae,
                 (char *)this + 7576);
        ThrowFailure(v181);
        CLockOwnerChild<CDevice,0>::UCAddUse(*((_QWORD *)this + 947) + 144LL);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 947) + 16LL))(*((_QWORD *)this + 947));
        ATL::CComPtrBase<IDXGIFactory4>::~CComPtrBase<IDXGIFactory4>(&v191);
        if ( *((_DWORD *)this + 111) )
        {
          *((_DWORD *)this + 405) = 1;
          v191 = 0;
          if ( (unsigned int)GetBehaviorValue("BackgroundThreadCount", &v191) && v191 )
            *((_DWORD *)this + 1792) = (_DWORD)v191;
          if ( (unsigned int)GetBehaviorValue("ForegroundThreadCount", &v191) && v191 )
          {
            LODWORD(v196) = (_DWORD)v191;
            *((_DWORD *)this + 1793) = *(_DWORD *)std::max<unsigned int>((char *)this + 7168, &v196);
          }
          if ( !RtlIsCriticalSectionLockedByThread(NtCurrentPeb()->LoaderLock) )
          {
            v191 = (void *)*((unsigned int *)this + 1792);
            BackgroundTaskScheduler::Scheduler::SetSchedulingMode((char *)this + 6832, v191);
          }
          CDevice::VersionedSetBackgroundProcessingMode(this, 0, 0, 0);
        }
        v182 = *((_BYTE *)this + 296) <= 0x22u;
        *((_BYTE *)this + 4912) = v182;
        v189 = 0;
        if ( v182 && (int)NDXGI::CUMDAdapter::GetCaps(v194, 1069, 0, &v189, 4) >= 0 && v189 )
          *((_BYTE *)this + 4912) = 0;
        v189 = 0;
        if ( (int)NDXGI::CUMDAdapter::GetCaps(v194, 1071, 0, &v189, 4) >= 0 && v189 )
          *((_BYTE *)this + 4913) = 1;
        *((_DWORD *)this + 683) = 0;
        v191 = this;
        lambda_056ae34a07ab82c8af8d12301fed2f8d_::operator()__lambda_85709f10a237feda8e4b255878305e9b___(
          &v191,
          (char *)this + 792);
        LOBYTE(v183) = 83;
        if ( (unsigned __int8)VersionedDeviceData::IsD3D12DDIVersionOrLater((char *)this + 288, v183)
          && CDevice::Support64BitAtomics(this) )
        {
          v205 = *(_OWORD *)lambda_269f8ec0a762f912bd20ffc6dbaa8286_::_lambda_269f8ec0a762f912bd20ffc6dbaa8286_(
                              &v199,
                              this,
                              (char *)this + 792);
          lambda_056ae34a07ab82c8af8d12301fed2f8d_::operator()__lambda_269f8ec0a762f912bd20ffc6dbaa8286___(&v191, &v205);
        }
        ATL::CComPtrBase<ID3DShaderCacheInstallerFactory>::~CComPtrBase<ID3DShaderCacheInstallerFactory>(&v198);
        return 0;
      }
    }
    else
    {
      if ( v22 != 2 )
      {
        DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z = (void ***)___FindIntegerValueInList_AEAU__CreateDDIMapImplImpl__0A__00__I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD___Z__V__YA_A_PAEAU__CreateDDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z();
        goto LABEL_66;
      }
      DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z = (void ***)operator new(8u);
      if ( DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z )
      {
        v24 = &DDITraits<2,0>::`vftable';
        goto LABEL_60;
      }
    }
    DDIMapImplImpl__0A__00__IU__integer_sequence_I_02_03_04_05_06_07_08_09_0L__0M__0N__0O__0P__0BA__0BB__0BC__0BD__0BE__0BF__0BG__0BH__0BI__0BJ__0BK__0BL__0BM__0BN__0BO__0BP__0CA__0CB__0CC__0CD__0CE__0CF__0CG__0CH__0CI__0CJ__0CK__0CL__0CM__0CN__0CO__0CP__0DA__0DB__0DC__0DD__0DE__0DF__0DG__0DH__0DI__0DJ__0DK__0DL__0DM__0DN__0DO__0DP__0EA__0EB__0EC__0ED__0EE__0EF__0EG__0EH__0EI__0EJ__0EK__0EL__0EM__0EN__0EO__0EP__0FA__0FB__0FC__0FD__std___Z = 0;
    goto LABEL_66;
  }
  catch ( std::bad_alloc )
  {
    return 2147942414LL;
  }
  catch ( _com_error *v204 )
  {
    return *((unsigned int *)v204 + 2);
  }
  return result;
}

```

## disassembly

```asm
0x18006f4a0  mov     [rsp+arg_8], rbx
0x18006f4a5  mov     [rsp+arg_10], rsi
0x18006f4aa  push    rdi
0x18006f4ab  push    r12
0x18006f4ad  push    r13
0x18006f4af  push    r14
0x18006f4b1  push    r15
0x18006f4b3  sub     rsp, 390h
0x18006f4ba  mov     rax, cs:__security_cookie
0x18006f4c1  xor     rax, rsp
0x18006f4c4  mov     [rsp+3B8h+var_38], rax
0x18006f4cc  mov     rdi, rcx
0x18006f4cf  mov     rcx, [rcx+2B0h]
0x18006f4d6  lea     r14, [rdi+2F8h]
0x18006f4dd  mov     rax, [rcx]
0x18006f4e0  mov     r8, r14
0x18006f4e3  lea     rdx, _GUID_00000040_0209_4b96_9b67_bdb7271d9371
0x18006f4ea  mov     rax, [rax]
0x18006f4ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f4f2  mov     rcx, [r14]
0x18006f4f5  mov     rax, [rcx]
0x18006f4f8  mov     rax, [rax+10h]
0x18006f4fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f501  mov     rcx, [rdi+2B0h]
0x18006f508  lea     rbx, [rdi+300h]
0x18006f50f  mov     rax, [rcx]
0x18006f512  mov     r8, rbx
0x18006f515  lea     rdx, _GUID_189819f1_1db6_4b57_be54_1821339b85f7
0x18006f51c  mov     rax, [rax]
0x18006f51f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f524  mov     rcx, [rbx]
0x18006f527  cmp     rdi, rcx
0x18006f52a  setz    al
0x18006f52d  mov     [rdi+2C9h], al
0x18006f533  mov     rax, [rcx]
0x18006f536  mov     rax, [rax+10h]
0x18006f53a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f53f  mov     rcx, [rdi+2B0h]
0x18006f546  lea     r15, [rdi+308h]
0x18006f54d  mov     rax, [rcx]
0x18006f550  mov     r8, r15
0x18006f553  lea     rdx, _GUID_16266e32_a95b_41da_89e4_a14379c0c6e4
0x18006f55a  mov     rax, [rax]
0x18006f55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f562  mov     rcx, [r15]
0x18006f565  mov     rax, [rcx]
0x18006f568  mov     rax, [rax+10h]
0x18006f56c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f571  nop
0x18006f572  xor     bl, bl
0x18006f574  lea     rsi, [rdi+318h]
0x18006f57b  cmp     dword ptr [rsi+304h], 0Bh
0x18006f582  jl      short loc_18006F5A5
0x18006f584  mov     rcx, [r15]
0x18006f587  mov     rax, [rcx]
0x18006f58a  mov     rax, [rax+18h]
0x18006f58e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f593  movzx   ebx, bl
0x18006f596  mov     r15d, 1
0x18006f59c  test    rax, rax
0x18006f59f  cmovnz  ebx, r15d
0x18006f5a3  jmp     short loc_18006F5AB
0x18006f5a5  mov     r15d, 1
0x18006f5ab  lea     r13, [rdi+120h]
0x18006f5b2  mov     [r13+161h], bl
0x18006f5b9  mov     rbx, [r14]
0x18006f5bc  mov     r12, [rbx+28h]
0x18006f5c0  mov     [rsp+3B8h+var_358], r12
0x18006f5c5  mov     [rsp+3B8h+var_340], r12
0x18006f5ca  mov     rcx, r12; this
0x18006f5cd  call    ?IsWARP@CUMDAdapter@NDXGI@@QEBA_NXZ; NDXGI::CUMDAdapter::IsWARP(void)
0x18006f5d2  mov     [rdi+2C4h], al
0x18006f5d8  mov     [rsp+3B8h+var_374], 0
0x18006f5e0  xorps   xmm0, xmm0
0x18006f5e3  xor     eax, eax
0x18006f5e5  movups  [rsp+3B8h+var_2F8], xmm0
0x18006f5ed  mov     qword ptr [rsp+3B8h+var_2E8], rax
0x18006f5f5  mov     rax, [rbx+28h]
0x18006f5f9  mov     ecx, [rax+1C0h]
0x18006f5ff  mov     dword ptr [rsp+3B8h+var_2F8], ecx
0x18006f606  mov     dword ptr [rsp+3B8h+var_2F8+4], 1Bh
0x18006f611  lea     rax, [rsp+3B8h+var_374]
0x18006f616  mov     qword ptr [rsp+3B8h+var_2F8+8], rax
0x18006f61e  mov     dword ptr [rsp+3B8h+var_2E8], 4
0x18006f629  lea     r9, [rsp+3B8h+var_2F8]
0x18006f631  lea     r8, ?AddRef@?$CLayeredObject@VCCommandAllocator@@@@UEAAKXZ; CLayeredObject<CCommandAllocator>::AddRef(void)
0x18006f638  lea     rdx, aQueryadapterin_10; "QueryAdapterInfo (IsXbox)"
0x18006f63f  mov     rcx, cs:__imp_D3DKMTQueryAdapterInfo
0x18006f646  call    ??$CallAndLogImpl@P6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEAU1@@@YAJP6AJPEAUD3DDDI_DESTROYPAGINGQUEUE@@@ZPEBDP6A?AW4RecordStatusFilterResult@@J@Z0@Z; CallAndLogImpl<long (*)(D3DDDI_DESTROYPAGINGQUEUE *),D3DDDI_DESTROYPAGINGQUEUE *>(long (*)(D3DDDI_DESTROYPAGINGQUEUE *),char const *,RecordStatusFilterResult (*)(long),D3DDDI_DESTROYPAGINGQUEUE *)
0x18006f64b  xor     ebx, ebx
0x18006f64d  test    eax, eax
0x18006f64f  js      short loc_18006F65A
0x18006f651  cmp     [rsp+3B8h+var_374], ebx
0x18006f655  mov     al, r15b
0x18006f658  jnz     short loc_18006F65C
0x18006f65a  mov     al, bl
0x18006f65c  mov     [rdi+2C8h], al
0x18006f662  lea     rdx, [rdi+1A50h]; union _LARGE_INTEGER *
0x18006f669  mov     rcx, r12; this
0x18006f66c  call    ?GetUMDFileVersion@CUMDAdapter@NDXGI@@QEAAJAEAT_LARGE_INTEGER@@@Z; NDXGI::CUMDAdapter::GetUMDFileVersion(_LARGE_INTEGER &)
0x18006f671  mov     [rsp+3B8h+var_348], rbx
0x18006f676  mov     [rsp+3B8h+var_368], rbx
0x18006f67b  lea     rdx, [rsp+3B8h+var_368]
0x18006f680  lea     rcx, aForcegenericon; "ForceGenericOnlyDevice"
0x18006f687  call    GetBehaviorValue
0x18006f68c  test    eax, eax
0x18006f68e  jz      short loc_18006F6A3
0x18006f690  cmp     [rsp+3B8h+var_368], rbx
0x18006f695  jz      short loc_18006F6A3
0x18006f697  mov     dword ptr [rsi+290h], 100h
0x18006f6a1  jmp     short loc_18006F6C9
0x18006f6a3  lea     rdx, [rsp+3B8h+var_348]
0x18006f6a8  lea     rcx, aForcecomputeon; "ForceComputeOnlyDevice"
0x18006f6af  call    GetBehaviorValue
0x18006f6b4  test    eax, eax
0x18006f6b6  jz      short loc_18006F6C9
0x18006f6b8  cmp     [rsp+3B8h+var_348], rbx
0x18006f6bd  jz      short loc_18006F6C9
0x18006f6bf  mov     dword ptr [rsi+290h], 1000h
0x18006f6c9  mov     rcx, r12; this
0x18006f6cc  call    ?GetTotalL1ExclusiveMemorySize@CUMDAdapter@NDXGI@@QEBA_KXZ; NDXGI::CUMDAdapter::GetTotalL1ExclusiveMemorySize(void)
0x18006f6d1  mov     [rdi+1430h], rax
0x18006f6d8  call    ?DDIFlags@CDevice@@SA?AW4D3D12DDI_CREATE_DEVICE_FLAGS@@XZ; CDevice::DDIFlags(void)
0x18006f6dd  mov     dword ptr [rsp+3B8h+var_348], eax
0x18006f6e1  mov     rdx, cs:qword_180339C50
0x18006f6e8  mov     r10, [rdx+20h]
0x18006f6ec  mov     r8, [rdx+28h]
0x18006f6f0  sub     r8, r10
0x18006f6f3  sar     r8, 4
0x18006f6f7  lea     r9, [rdi+1510h]
0x18006f6fe  lea     rdx, [rdi+2060h]
0x18006f705  mov     [rsp+3B8h+var_388], r8d
0x18006f70a  mov     [rsp+3B8h+var_390], r10
0x18006f70f  mov     dword ptr [rsp+3B8h+var_398], eax
0x18006f713  mov     r8, rdi
0x18006f716  mov     rcx, [r14]
0x18006f719  call    ?CreateDriverInstance@CDevice@NDXGI@@QEAAJPEAX00W4D3D12DDI_CREATE_DEVICE_FLAGS@@PEBUD3D12_GPU_VIRTUAL_ADDRESS_RANGE@@I@Z; NDXGI::CDevice::CreateDriverInstance(void *,void *,void *,D3D12DDI_CREATE_DEVICE_FLAGS,D3D12_GPU_VIRTUAL_ADDRESS_RANGE const *,uint)
0x18006f71e  mov     ecx, eax; int
0x18006f720  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006f725  mov     [rdi+0B90h], r15b
0x18006f72c  mov     rcx, r13; this
0x18006f72f  call    ?GetShaderCaps@VersionedDeviceData@@QEAAXXZ; VersionedDeviceData::GetShaderCaps(void)
0x18006f734  mov     [rsp+3B8h+var_374], ebx
0x18006f738  lea     rdx, [rsp+3B8h+var_374]; unsigned int *
0x18006f73d  mov     rcx, r13; this
0x18006f740  call    ?GetD3D12ShaderModel@VersionedDeviceData@@QEAAXAEAI@Z; VersionedDeviceData::GetD3D12ShaderModel(uint &)
0x18006f745  lea     rdx, [r13+44h]; struct D3D12DDI_D3D12_OPTIONS_DATA_0089 *
0x18006f749  mov     rcx, r13; this
0x18006f74c  call    ?GetD3D12OptionsInternal@VersionedDeviceData@@AEAAJPEAUD3D12DDI_D3D12_OPTIONS_DATA_0089@@@Z; VersionedDeviceData::GetD3D12OptionsInternal(D3D12DDI_D3D12_OPTIONS_DATA_0089 *)
0x18006f751  mov     r12d, 887A0020h
0x18006f757  test    eax, eax
0x18006f759  jns     short loc_18006F782
0x18006f75b  mov     dword ptr [rsp+3B8h+var_398], 0
0x18006f763  lea     r8, aDriverDidNotRe; "Driver did not respond to D3D12DDICAPS_"...
0x18006f76a  mov     edx, r12d
0x18006f76d  call    ?RecordJournal@CJournal@@QEAAXIPEBD_NW4RecordJournalOptions@@@Z; CJournal::RecordJournal(uint,char const *,bool,RecordJournalOptions)
0x18006f772  mov     r14d, 887A0020h
0x18006f778  mov     ecx, r14d; int
0x18006f77b  call    ?ThrowFailure@@YAXJ@Z; ThrowFailure(long)
0x18006f780  jmp     short loc_18006F788
0x18006f782  mov     r14d, 887A0020h
0x18006f788  lea     rdx, [r13+44h]; struct D3D12DDI_D3D12_OPTIONS_DATA_0089 *
0x18006f78c  mov     rcx, r13; this
0x18006f78f  call    ?ValidateAndClampD3D12Options@VersionedDeviceData@@AEAAXAEAUD3D12DDI_D3D12_OPTIONS_DATA_0089@@@Z; VersionedDeviceData::ValidateAndClampD3D12Options(D3D12DDI_D3D12_OPTIONS_DATA_0089 &)
0x18006f794  lea     rbx, [r13+0C0h]
0x18006f79b  cmp     byte ptr [r13+8], 32h ; '2'
0x18006f7a0  jb      short loc_18006F7BE
0x18006f7a2  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f7aa  mov     r9, rbx
0x18006f7ad  mov     edx, 435h
0x18006f7b2  mov     rcx, r13
0x18006f7b5  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f7ba  test    eax, eax
0x18006f7bc  jns     short loc_18006F7C2
0x18006f7be  xor     eax, eax
0x18006f7c0  mov     [rbx], eax
0x18006f7c2  lea     rbx, [r13+0C4h]
0x18006f7c9  cmp     byte ptr [r13+8], 33h ; '3'
0x18006f7ce  jb      short loc_18006F7EC
0x18006f7d0  mov     dword ptr [rsp+3B8h+var_398], 10h
0x18006f7d8  mov     r9, rbx
0x18006f7db  mov     edx, 436h
0x18006f7e0  mov     rcx, r13
0x18006f7e3  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f7e8  test    eax, eax
0x18006f7ea  jns     short loc_18006F7F2
0x18006f7ec  xorps   xmm0, xmm0
0x18006f7ef  movups  xmmword ptr [rbx], xmm0
0x18006f7f2  lea     rbx, [r13+0D4h]
0x18006f7f9  cmp     byte ptr [r13+8], 35h ; '5'
0x18006f7fe  jb      short loc_18006F81C
0x18006f800  mov     dword ptr [rsp+3B8h+var_398], 8
0x18006f808  mov     r9, rbx
0x18006f80b  mov     edx, 437h
0x18006f810  mov     rcx, r13
0x18006f813  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f818  test    eax, eax
0x18006f81a  jns     short loc_18006F821
0x18006f81c  xor     eax, eax
0x18006f81e  mov     [rbx], rax
0x18006f821  lea     rbx, [r13+0DCh]
0x18006f828  cmp     byte ptr [r13+8], 3Ah ; ':'
0x18006f82d  jb      short loc_18006F84B
0x18006f82f  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f837  mov     r9, rbx
0x18006f83a  mov     edx, 438h
0x18006f83f  mov     rcx, r13
0x18006f842  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f847  test    eax, eax
0x18006f849  jns     short loc_18006F84F
0x18006f84b  xor     eax, eax
0x18006f84d  mov     [rbx], eax
0x18006f84f  mov     eax, [rdi+130h]
0x18006f855  cmp     eax, 1000h
0x18006f85a  jz      short loc_18006F863
0x18006f85c  cmp     eax, 100h
0x18006f861  jnz     short loc_18006F891
0x18006f863  lea     rbx, [r13+0E0h]
0x18006f86a  cmp     byte ptr [r13+8], 3Dh ; '='
0x18006f86f  jb      short loc_18006F88D
0x18006f871  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f879  mov     r9, rbx
0x18006f87c  mov     edx, 439h
0x18006f881  mov     rcx, r13
0x18006f884  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f889  test    eax, eax
0x18006f88b  jns     short loc_18006F891
0x18006f88d  xor     eax, eax
0x18006f88f  mov     [rbx], eax
0x18006f891  lea     rbx, [r13+0F4h]
0x18006f898  cmp     byte ptr [r13+8], 3Fh ; '?'
0x18006f89d  jb      short loc_18006F8BB
0x18006f89f  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f8a7  mov     r9, rbx
0x18006f8aa  mov     edx, 3F5h
0x18006f8af  mov     rcx, r13
0x18006f8b2  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f8b7  test    eax, eax
0x18006f8b9  jns     short loc_18006F8BF
0x18006f8bb  xor     eax, eax
0x18006f8bd  mov     [rbx], eax
0x18006f8bf  cmp     dword ptr [rbx], 0
0x18006f8c2  jge     short loc_18006F8D5
0x18006f8c4  lea     r8, aDriverFilledOu_1; "Driver filled out an invalid value in D"...
0x18006f8cb  mov     edx, r14d; int
0x18006f8ce  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x18006f8d3  jmp     short loc_18006F8E0
0x18006f8d5  cmp     dword ptr [rbx], 0Ah
0x18006f8d8  jle     short loc_18006F8E0
0x18006f8da  mov     dword ptr [rbx], 0Ah
0x18006f8e0  lea     rbx, [r13+0F8h]
0x18006f8e7  cmp     byte ptr [r13+8], 45h ; 'E'
0x18006f8ec  jb      short loc_18006F90A
0x18006f8ee  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f8f6  mov     r9, rbx
0x18006f8f9  mov     edx, 43Fh
0x18006f8fe  mov     rcx, r13
0x18006f901  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f906  test    eax, eax
0x18006f908  jns     short loc_18006F90E
0x18006f90a  xor     eax, eax
0x18006f90c  mov     [rbx], eax
0x18006f90e  lea     rbx, [rdi+120h]
0x18006f915  lea     rax, [rbx+0FCh]
0x18006f91c  cmp     byte ptr [rbx+8], 46h ; 'F'
0x18006f920  jb      short loc_18006F945
0x18006f922  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f92a  mov     r9, rax
0x18006f92d  mov     edx, 440h
0x18006f932  mov     rcx, rbx
0x18006f935  call    ?DDIGetCaps@VersionedDeviceData@@AEAAJW4D3D12DDICAPS_TYPE@@PEAX1I@Z; VersionedDeviceData::DDIGetCaps(D3D12DDICAPS_TYPE,void *,void *,uint)
0x18006f93a  test    eax, eax
0x18006f93c  lea     rax, [rbx+0FCh]
0x18006f943  jns     short loc_18006F94B
0x18006f945  mov     dword ptr [rax], 0Ah
0x18006f94b  mov     ecx, [rax]; this
0x18006f94d  cmp     ecx, 0Ah
0x18006f950  jge     short loc_18006F963
0x18006f952  lea     r8, aDriverFilledOu_7; "Driver filled out an invalid value in D"...
0x18006f959  mov     edx, r14d; int
0x18006f95c  call    ?ReportDriverError@CJournal@@QEAAXJPEBD@Z; CJournal::ReportDriverError(long,char const *)
0x18006f961  jmp     short loc_18006F972
0x18006f963  cmp     ecx, 0Ch
0x18006f966  jl      short loc_18006F972
0x18006f968  mov     dword ptr [rbx+0FCh], 0Bh
0x18006f972  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment> `wil::Feature<__WilFeatureTraits_Feature_D3D12TightAlignment>::GetImpl(void)'::`2'::impl
0x18006f979  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_D3D12TightAlignment@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_D3D12TightAlignment>::__private_IsEnabled(void)
0x18006f97e  test    al, al
0x18006f980  jz      short loc_18006F991
0x18006f982  lea     rdx, [rdi+0AB4h]; struct D3D12DDI_TIGHT_ALIGNMENT_TIER_DATA_0111 *
0x18006f989  mov     rcx, rdi; this
0x18006f98c  call    ?GetTightAlignmentTierData@CDevice@@QEAAXPEAUD3D12DDI_TIGHT_ALIGNMENT_TIER_DATA_0111@@@Z; CDevice::GetTightAlignmentTierData(D3D12DDI_TIGHT_ALIGNMENT_TIER_DATA_0111 *)
0x18006f991  lea     rbx, [rdi+120h]
0x18006f998  lea     rax, [rbx+100h]
0x18006f99f  cmp     byte ptr [rbx+8], 4Eh ; 'N'
0x18006f9a3  jb      short loc_18006F9C8
0x18006f9a5  mov     dword ptr [rsp+3B8h+var_398], 4
0x18006f9ad  mov     r9, rax
0x18006f9b0  mov     edx, 447h
0x18006f9b5  mov     rcx, rbx
  ... truncated ...
```
