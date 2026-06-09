# SystemSettings::StorageSenseHandlers::CleanmgrHelper::Initialize(ushort const *)

- ea: `0x1800c4ca0`
- end: `0x1800c616d`
- name: `?Initialize@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@UEAAJPEBG@Z`
- size: `5325`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CleanmgrHelper *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `38`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000171c`
- `0x18000518c`
- `0x1800052ec`
- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x18000e6cc`
- `0x180016ef4`
- `0x18001fe08`
- `0x180023578`
- `0x180023928`
- `0x1800352b4`
- `0x18003b450`
- `0x18005d26c`
- `0x180085df8`
- `0x180086154`
- `0x18008657c`
- `0x180086c98`
- `0x180087980`
- `0x18009307c`
- `0x180093454`
- `0x1800c3ca4`
- `0x1800c3d68`
- `0x1800c3fc8`
- `0x1800c4004`
- `0x1800c4394`
- `0x1800c4468`
- `0x1800c4518`
- `0x1800c46a4`
- `0x1800c4700`
- `0x1800c472c`
- `0x1800c4758`
- `0x1800c4ca0`
- `0x1800c65e4`
- `0x1800c6708`
- `0x1800c6858`
- `0x1800c71e8`
- `0x1800e3010`

## import_xrefs

- `ntdll!RtlInitializeCorrelationVector` at `0x1800c4d81`
- `ntdll!RtlInitializeCorrelationVector` at `0x1800c4d81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c579c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c57ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c5780`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c579c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c57ab`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c5052`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800c5052`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c4d54`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x1800c4d54`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c52a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800c52a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c4da8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c5265`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c52ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c561a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c56f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c4da8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c5265`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c52ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c561a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800c56f7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4e77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4fc4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4e77`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800c4fc4`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c4ed1`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800c4ed1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c511f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c516a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c511f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800c516a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c4f57`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c4f57`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c501f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800c501f`

## string_xrefs

- `0x1800c4e69`: `Software\Microsoft\Windows\CurrentVersion\Explorer\VolumeCaches`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::StorageSenseHandlers::CleanmgrHelper::Initialize(
        SystemSettings::StorageSenseHandlers::CleanmgrHelper *this,
        const unsigned __int16 *a2)
{
  float v4; // xmm10_4
  float v5; // xmm11_4
  float v6; // xmm14_4
  int v7; // ebx
  char *v8; // r15
  _QWORD *v9; // r13
  __int64 v10; // rax
  _QWORD *v11; // r14
  __int64 v12; // rax
  _QWORD *v13; // r12
  __int64 v14; // rax
  _QWORD *v15; // rsi
  __int64 v16; // rax
  char *v17; // rdi
  bool v18; // sf
  __int64 v19; // rdx
  LSTATUS v20; // eax
  unsigned int v21; // eax
  __m128i si128; // xmm13
  int v23; // eax
  int v24; // edx
  LSTATUS v25; // eax
  bool v26; // sf
  LSTATUS v27; // eax
  bool v28; // sf
  const unsigned __int16 *v29; // rax
  unsigned int v30; // edi
  int v31; // r9d
  __int64 v32; // rax
  __int64 v33; // rdx
  ULONGLONG TickCount64; // rbx
  __int64 v35; // rcx
  float v36; // xmm8_4
  float v37; // xmm8_4
  __int64 v38; // rax
  __int64 v39; // r9
  __int64 v40; // rcx
  __int64 v41; // r8
  int v42; // edx
  const unsigned __int16 *v43; // rax
  int v44; // r8d
  _OWORD *v45; // rax
  _OWORD *v46; // rdx
  const unsigned __int16 *v47; // rax
  int v48; // r9d
  __int64 v49; // rax
  __int64 v50; // rdx
  LPVOID v51; // rdi
  __int64 (__fastcall *v52)(LPVOID, GUID *, __int64 *); // rbx
  int v53; // eax
  __int64 v54; // rax
  __int64 v55; // r10
  signed int v56; // eax
  __int64 v57; // rax
  __int64 v58; // r10
  ULONGLONG v59; // rcx
  ULONGLONG v60; // rdx
  float v61; // xmm7_4
  float v62; // xmm7_4
  __int64 v63; // rcx
  float v64; // xmm6_4
  float v65; // xmm6_4
  __int64 v66; // rcx
  int v67; // ebx
  __int128 v68; // xmm0
  __int128 v69; // xmm1
  __int128 v70; // xmm2
  __int128 v71; // xmm3
  __int128 v72; // xmm4
  __int128 v73; // xmm5
  __int128 v74; // xmm8
  __int128 v75; // xmm9
  __int16 v76; // dx
  int v77; // r11d
  __int64 v78; // rax
  HKEY *v79; // r9
  __int64 v80; // rcx
  __int64 v81; // r8
  __int64 v82; // r10
  int v83; // r11d
  const unsigned __int16 *v84; // rax
  int v85; // r8d
  _OWORD *v86; // rax
  _OWORD *v87; // rdx
  __int128 v88; // xmm0
  __int128 v89; // xmm1
  __int128 v90; // xmm2
  __int128 v91; // xmm3
  __int128 v92; // xmm6
  __int128 v93; // xmm7
  __int64 v94; // rax
  __int128 v95; // xmm4
  __int128 v96; // xmm5
  __int16 v97; // dx
  __int64 v98; // r8
  int v99; // edi
  DWORD v100; // ebx
  __int64 v101; // rdx
  const struct _tlgProvider_t *v102; // r8
  int v103; // r8d
  int v104; // r9d
  __int64 v105; // rdx
  const struct _tlgProvider_t *v106; // r8
  int v107; // r8d
  int v108; // r9d
  __int64 v109; // rax
  DWORD v110; // ebx
  __int64 v111; // rdx
  const struct _tlgProvider_t *v112; // r8
  int v113; // r8d
  int v114; // r9d
  __int64 v115; // rdx
  const struct _tlgProvider_t *v116; // r8
  int v117; // r8d
  int v118; // r9d
  __int64 v119; // rax
  int phkResult; // [rsp+28h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+28h] [rbp-E0h]
  unsigned int pvData; // [rsp+78h] [rbp-90h] BYREF
  DWORD pcbData; // [rsp+7Ch] [rbp-8Ch] BYREF
  int v125; // [rsp+80h] [rbp-88h] BYREF
  DWORD cbData; // [rsp+84h] [rbp-84h] BYREF
  DWORD cchName; // [rsp+88h] [rbp-80h] BYREF
  HKEY hkey; // [rsp+90h] [rbp-78h] BYREF
  DWORD cSubKeys; // [rsp+98h] [rbp-70h] BYREF
  LPVOID v130; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v131; // [rsp+A8h] [rbp-60h] BYREF
  LPVOID v132; // [rsp+B0h] [rbp-58h] BYREF
  DWORD v133; // [rsp+B8h] [rbp-50h]
  char *v134; // [rsp+C0h] [rbp-48h]
  LPVOID pv; // [rsp+C8h] [rbp-40h] BYREF
  int v136; // [rsp+D0h] [rbp-38h]
  unsigned int v137; // [rsp+D8h] [rbp-30h]
  struct _GUID v138; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v139; // [rsp+F8h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+100h] [rbp-8h] BYREF
  _OWORD v141[2]; // [rsp+108h] [rbp+0h] BYREF
  __int128 v142; // [rsp+128h] [rbp+20h] BYREF
  __int64 v143; // [rsp+138h] [rbp+30h]
  __int64 v144; // [rsp+140h] [rbp+38h]
  __int128 v145; // [rsp+148h] [rbp+40h] BYREF
  __int64 v146; // [rsp+158h] [rbp+50h]
  __int64 v147; // [rsp+160h] [rbp+58h]
  _OWORD v148[2]; // [rsp+168h] [rbp+60h] BYREF
  __int128 v149; // [rsp+188h] [rbp+80h]
  __m128i v150; // [rsp+198h] [rbp+90h]
  __int128 v151; // [rsp+1A8h] [rbp+A0h]
  __m128i v152; // [rsp+1B8h] [rbp+B0h]
  unsigned int v153[4]; // [rsp+1C8h] [rbp+C0h]
  LPVOID ppv; // [rsp+1D8h] [rbp+D0h] BYREF
  int v155[4]; // [rsp+1E0h] [rbp+D8h]
  GUID pclsid; // [rsp+1F8h] [rbp+F0h] BYREF
  struct _GUID v157; // [rsp+208h] [rbp+100h] BYREF
  __int128 v158; // [rsp+228h] [rbp+120h] BYREF
  __int128 v159; // [rsp+238h] [rbp+130h]
  __int128 v160; // [rsp+248h] [rbp+140h]
  __int128 v161; // [rsp+258h] [rbp+150h]
  __int128 v162; // [rsp+268h] [rbp+160h]
  __int128 v163; // [rsp+278h] [rbp+170h]
  __int128 v164; // [rsp+288h] [rbp+180h]
  __int128 v165; // [rsp+298h] [rbp+190h]
  __int16 v166; // [rsp+2A8h] [rbp+1A0h]
  GUID pguid; // [rsp+2B8h] [rbp+1B0h] BYREF
  __int128 v168; // [rsp+2C8h] [rbp+1C0h] BYREF
  __int128 v169; // [rsp+2D8h] [rbp+1D0h]
  __int128 v170; // [rsp+2E8h] [rbp+1E0h]
  __int128 v171; // [rsp+2F8h] [rbp+1F0h]
  __int128 v172; // [rsp+308h] [rbp+200h]
  __int128 v173; // [rsp+318h] [rbp+210h]
  __int128 v174; // [rsp+328h] [rbp+220h]
  __int128 v175; // [rsp+338h] [rbp+230h]
  __int16 v176; // [rsp+348h] [rbp+240h]
  _BYTE v177[336]; // [rsp+388h] [rbp+280h] BYREF
  _BYTE v178[336]; // [rsp+4D8h] [rbp+3D0h] BYREF
  _QWORD v179[42]; // [rsp+628h] [rbp+520h] BYREF
  OLECHAR Data[40]; // [rsp+778h] [rbp+670h] BYREF
  WCHAR Name[264]; // [rsp+7C8h] [rbp+6C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AB0h] [rbp+9A8h]

  hKey = 0;
  cSubKeys = 0;
  *(_QWORD *)((char *)&v157.Data1 + 2) = 6029370;
  v4 = 0.0;
  v125 = 0;
  v5 = 0.0;
  cchName = 0;
  v6 = 0.0;
  pcbData = 0;
  pguid = 0;
  CoCreateGuid(&pguid);
  memset_0(&v158, 0, 0x82u);
  RtlInitializeCorrelationVector(&v158, 2, &pguid);
  wil::ActivityBase<SettingsHandlersStorageSenseLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsHandlersStorageSenseLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v179);
  v179[0] = &SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrInitialize::`vftable';
  SystemSettings::StorageSenseHandlers::Internal::beforeInitializationTick = GetTickCount64();
  if ( !a2 )
  {
    v7 = -2147024809;
    goto LABEL_128;
  }
  v8 = (char *)this + 48;
  if ( *((_QWORD *)this + 6) != *((_QWORD *)this + 7) )
  {
    std::_Destroy_range<std::allocator<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo>>(*(SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo **)v8);
    *((_QWORD *)this + 7) = *((_QWORD *)this + 6);
  }
  v9 = (_QWORD *)((char *)this + 72);
  v10 = *((_QWORD *)this + 9);
  if ( v10 != *((_QWORD *)this + 10) )
    *((_QWORD *)this + 10) = v10;
  v11 = (_QWORD *)((char *)this + 96);
  v12 = *((_QWORD *)this + 12);
  if ( v12 != *((_QWORD *)this + 13) )
    *((_QWORD *)this + 13) = v12;
  v13 = (_QWORD *)((char *)this + 120);
  v14 = *((_QWORD *)this + 15);
  if ( v14 != *((_QWORD *)this + 16) )
    *((_QWORD *)this + 16) = v14;
  v15 = (_QWORD *)((char *)this + 144);
  v16 = *((_QWORD *)this + 18);
  if ( v16 != *((_QWORD *)this + 19) )
    *((_QWORD *)this + 19) = v16;
  LOWORD(v157.Data1) = *a2;
  v17 = (char *)this + 16;
  v134 = (char *)this + 16;
  std::wstring::assign((char *)this + 16, &v157);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v7 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\VolumeCaches",
         0,
         0x20019u,
         &hKey);
  v18 = v7 < 0;
  if ( v7 > 0 )
  {
    v7 = (unsigned __int16)v7 | 0x80070000;
    v18 = v7 < 0;
  }
  if ( v18 )
  {
    v19 = 78;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\cleanmgrhelperimpl.cpp",
      (const char *)(unsigned int)v7,
      phkResult);
    goto LABEL_128;
  }
  v20 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v7 = v20;
  if ( v20 > 0 )
    v7 = (unsigned __int16)v20 | 0x80070000;
  if ( v7 < 0 )
  {
    v19 = 92;
    goto LABEL_21;
  }
  v133 = 0;
  v21 = 0;
  v137 = 0;
  if ( !cSubKeys )
    goto LABEL_90;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  do
  {
    cchName = 260;
    v23 = RegEnumKeyExW(hKey, v21, Name, &cchName, 0, 0, 0, 0);
    if ( v23 > 0 )
      v23 = (unsigned __int16)v23 | 0x80070000;
    LODWORD(v131) = v23;
    if ( v23 >= 0 )
    {
      SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::StorageSenseCleanmgrPluginInstantiate(
        (unsigned int)v177,
        v24,
        (unsigned int)Name,
        (unsigned int)&v131,
        (__int64)&v158);
      hkey = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      v25 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &hkey);
      v26 = v25 < 0;
      if ( v25 > 0 )
        v26 = 1;
      if ( v26 )
        goto LABEL_30;
      cbData = 78;
      v27 = RegQueryValueExW(hkey, 0, 0, 0, (LPBYTE)Data, &cbData);
      v28 = v27 < 0;
      if ( v27 > 0 )
        v28 = 1;
      if ( v28 || (pclsid = GUID_NULL, CLSIDFromString(Data, &pclsid) < 0) )
      {
LABEL_30:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::~StorageSenseCleanmgrPluginInstantiate((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate *)v177);
        goto LABEL_88;
      }
      v141[0] = 0;
      v141[1] = si128;
      LOWORD(v141[0]) = 0;
      v142 = 0;
      v143 = 0;
      v144 = 7;
      LOWORD(v142) = 0;
      v145 = 0;
      v146 = 0;
      v147 = 7;
      LOWORD(v145) = 0;
      v148[0] = 0;
      v148[1] = si128;
      LOWORD(v148[0]) = 0;
      v149 = 0;
      v150 = si128;
      LOWORD(v149) = 0;
      v151 = 0;
      v152 = si128;
      LOWORD(v151) = 0;
      *(_OWORD *)v153 = 0;
      ppv = 0;
      *(_OWORD *)v155 = 0;
      pvData = 0;
      pcbData = 4;
      if ( RegGetValueW(hkey, 0, L"Autorun", 0x18u, 0, &pvData, &pcbData) )
        LOBYTE(v153[0]) = 0;
      else
        LOBYTE(v153[0]) = pvData & 1;
      pvData = 0;
      if ( !RegGetValueW(hkey, 0, L"ReserveIDHint", 0x18u, 0, &pvData, &pcbData) )
        *(_QWORD *)&v153[2] = pvData;
      std::wstring::assign(v148, Name);
      v157 = pclsid;
      v29 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
      v30 = v137;
      v32 = SystemSettings::StorageSenseHandlers::PluginScanStart::PluginScanStart(
              (SystemSettings::StorageSenseHandlers::PluginScanStart *)&v168,
              v29,
              &v157,
              v31,
              v137);
      v33 = v9[1];
      if ( v33 == v9[2] )
      {
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationPhaseStartData>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationPhaseStartData>(
          v9,
          v33,
          v32);
      }
      else
      {
        *(_OWORD *)v33 = *(_OWORD *)v32;
        *(_OWORD *)(v33 + 16) = *(_OWORD *)(v32 + 16);
        *(_OWORD *)(v33 + 32) = *(_OWORD *)(v32 + 32);
        *(_OWORD *)(v33 + 48) = *(_OWORD *)(v32 + 48);
        *(_OWORD *)(v33 + 64) = *(_OWORD *)(v32 + 64);
        *(_OWORD *)(v33 + 80) = *(_OWORD *)(v32 + 80);
        *(_OWORD *)(v33 + 96) = *(_OWORD *)(v32 + 96);
        *(_OWORD *)(v33 + 112) = *(_OWORD *)(v32 + 112);
        *(_OWORD *)(v33 + 128) = *(_OWORD *)(v32 + 128);
        *(_OWORD *)(v33 + 144) = *(_OWORD *)(v32 + 144);
        *(_OWORD *)(v33 + 160) = *(_OWORD *)(v32 + 160);
        *(_QWORD *)(v33 + 176) = *(_QWORD *)(v32 + 176);
        v9[1] += 184LL;
      }
      TickCount64 = GetTickCount64();
      *(_QWORD *)&v157.Data1 = TickCount64;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&ppv);
      v155[2] = CoCreateInstance(&pclsid, 0, 1u, &IID_IEmptyVolumeCache, &ppv);
      v35 = GetTickCount64() - TickCount64;
      if ( v35 < 0 )
        v36 = (float)(v35 & 1 | (unsigned int)((unsigned __int64)v35 >> 1))
            + (float)(v35 & 1 | (unsigned int)((unsigned __int64)v35 >> 1));
      else
        v36 = (float)(int)v35;
      v37 = v36 / 1000.0;
      v6 = v6 + v37;
      std::wstring::assign(v141, Data);
      v168 = v158;
      v169 = v159;
      v170 = v160;
      v171 = v161;
      v172 = v162;
      v173 = v163;
      v174 = v164;
      v175 = v165;
      v176 = v166;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v141);
      v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
      LOBYTE(v39) = v153[0];
      SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::Stop(
        v40,
        v38,
        v41,
        v39,
        v153[2],
        v37,
        v155[2],
        &v168);
      if ( v155[2] < 0 )
        goto LABEL_47;
      ++v133;
      v131 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v141);
      *(_QWORD *)&v138.Data1 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
      SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInitialize::StorageSenseCleanmgrPluginInitialize(
        (unsigned int)v178,
        v42,
        (unsigned int)&v138,
        (unsigned int)&v131,
        (__int64)&v158);
      v138 = pclsid;
      v43 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
      v45 = (_OWORD *)SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationStopData::PluginInstantiationStopData(
                        (SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationStopData *)&v168,
                        v43,
                        &v138,
                        v37,
                        v155[2],
                        v44,
                        v153[2]);
      v46 = (_OWORD *)v11[1];
      if ( v46 == (_OWORD *)v11[2] )
      {
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>(
          v11,
          v46,
          v45);
      }
      else
      {
        *v46 = *v45;
        v46[1] = v45[1];
        v46[2] = v45[2];
        v46[3] = v45[3];
        v46[4] = v45[4];
        v46[5] = v45[5];
        v46[6] = v45[6];
        v46[7] = v45[7];
        v46[8] = v45[8];
        v46[9] = v45[9];
        v46[10] = v45[10];
        v46[11] = v45[11];
        v11[1] += 192LL;
      }
      if ( v155[2] < 0 )
      {
        SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInitialize::~StorageSenseCleanmgrPluginInitialize((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInitialize *)v178);
LABEL_47:
        SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo::~PluginInfo((SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo *)v141);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::~StorageSenseCleanmgrPluginInstantiate((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate *)v177);
        v17 = v134;
        goto LABEL_88;
      }
      v138 = pclsid;
      v47 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
      v49 = SystemSettings::StorageSenseHandlers::PluginScanStart::PluginScanStart(
              (SystemSettings::StorageSenseHandlers::PluginScanStart *)&v168,
              v47,
              &v138,
              v48,
              v30);
      v50 = v13[1];
      if ( v50 == v13[2] )
      {
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationPhaseStartData>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationPhaseStartData>(
          v13,
          v50,
          v49);
      }
      else
      {
        *(_OWORD *)v50 = *(_OWORD *)v49;
        *(_OWORD *)(v50 + 16) = *(_OWORD *)(v49 + 16);
        *(_OWORD *)(v50 + 32) = *(_OWORD *)(v49 + 32);
        *(_OWORD *)(v50 + 48) = *(_OWORD *)(v49 + 48);
        *(_OWORD *)(v50 + 64) = *(_OWORD *)(v49 + 64);
        *(_OWORD *)(v50 + 80) = *(_OWORD *)(v49 + 80);
        *(_OWORD *)(v50 + 96) = *(_OWORD *)(v49 + 96);
        *(_OWORD *)(v50 + 112) = *(_OWORD *)(v49 + 112);
        *(_OWORD *)(v50 + 128) = *(_OWORD *)(v49 + 128);
        *(_OWORD *)(v50 + 144) = *(_OWORD *)(v49 + 144);
        *(_OWORD *)(v50 + 160) = *(_OWORD *)(v49 + 160);
        *(_QWORD *)(v50 + 176) = *(_QWORD *)(v49 + 176);
        v13[1] += 184LL;
      }
      v125 = 128;
      pv = 0;
      v130 = 0;
      v132 = 0;
      *(_QWORD *)&v138.Data1 = GetTickCount64();
      v139 = 0;
      v51 = ppv;
      v52 = **(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v139);
      v53 = v52(v51, &IID_IEmptyVolumeCache2, &v139);
      v17 = v134;
      if ( v53 < 0 )
      {
        v57 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
        v56 = (*(__int64 (__fastcall **)(__int64, HKEY, __int64, LPVOID *, LPVOID *, int *))(*(_QWORD *)v58 + 24LL))(
                v58,
                hkey,
                v57,
                &pv,
                &v130,
                &v125);
      }
      else
      {
        v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
        v56 = (*(__int64 (__fastcall **)(__int64, HKEY, __int64, WCHAR *, LPVOID *, LPVOID *, LPVOID *, int *))(*(_QWORD *)v55 + 64LL))(
                v55,
                hkey,
                v54,
                Name,
                &pv,
                &v130,
                &v132,
                &v125);
      }
      if ( v56 > 0 )
        v56 = (unsigned __int16)v56 | 0x80070000;
      v155[2] = v56;
      v59 = GetTickCount64();
      v60 = v59 - *(_QWORD *)&v138.Data1;
      if ( (__int64)(v59 - *(_QWORD *)&v138.Data1) < 0 )
        v61 = (float)(int)(v60 & 1 | (v60 >> 1)) + (float)(int)(v60 & 1 | (v60 >> 1));
      else
        v61 = (float)(int)v60;
      v62 = v61 / 1000.0;
      v63 = v59 - *(_QWORD *)&v157.Data1;
      if ( v63 < 0 )
        v64 = (float)(v63 & 1 | (unsigned int)((unsigned __int64)v63 >> 1))
            + (float)(v63 & 1 | (unsigned int)((unsigned __int64)v63 >> 1));
      else
        v64 = (float)(int)v63;
      v65 = v64 / 1000.0;
      v5 = v5 + v62;
      v4 = v4 + v65;
      if ( pv )
      {
        std::wstring::assign(&v142, pv);
        CoTaskMemFree(pv);
      }
      if ( v130 )
      {
        std::wstring::assign(&v145, v130);
        CoTaskMemFree(v130);
      }
      if ( v132 )
        CoTaskMemFree(v132);
      std::wstring::wstring(&v157);
      v67 = SystemSettings::StorageSenseHandlers::CleanmgrHelper::_LoadStringProperties(v66, &hkey, &v157, v141);
      std::wstring::_Tidy_deallocate(&v157);
      v68 = v158;
      v69 = v159;
      v70 = v160;
      v71 = v161;
      v72 = v162;
      v73 = v163;
      v74 = v164;
      v75 = v165;
      v76 = v166;
      v77 = v155[2];
      if ( v155[2] >= 0 && v146 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v145);
      if ( v77 >= 0 && v143 )
        std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v142);
      v168 = v68;
      v169 = v69;
      v170 = v70;
      v171 = v71;
      v172 = v72;
      v173 = v73;
      v174 = v74;
      v175 = v75;
      v176 = v76;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v141);
      v78 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
      phkResulta = v79;
      LOBYTE(v79) = v153[0];
      SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInitialize::Stop(
        v80,
        v78,
        v81,
        v79,
        phkResulta,
        v82,
        v62,
        v65,
        v83,
        &v168);
      if ( v155[2] >= 0 && v67 >= 0 )
      {
        if ( *((_QWORD *)v8 + 1) == *((_QWORD *)v8 + 2) )
        {
          std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo const &>(
            v8,
            *((_QWORD *)v8 + 1),
            v141);
        }
        else
        {
          SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo::PluginInfo(
            *((SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo **)v8 + 1),
            (const struct SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo *)v141);
          *((_QWORD *)v8 + 1) += 232LL;
        }
        v157 = pclsid;
        v84 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v148);
        v86 = (_OWORD *)SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData::PluginInitializeStopData(
                          (SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData *)&v168,
                          v84,
                          &v157,
                          v62,
                          v65,
                          v155[2],
                          v85);
        v87 = (_OWORD *)v15[1];
        if ( v87 == (_OWORD *)v15[2] )
        {
          std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>::_Emplace_reallocate<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>(
            v15,
            v87,
            v86);
        }
        else
        {
          *v87 = *v86;
          v87[1] = v86[1];
          v87[2] = v86[2];
          v87[3] = v86[3];
          v87[4] = v86[4];
          v87[5] = v86[5];
          v87[6] = v86[6];
          v87[7] = v86[7];
          v87[8] = v86[8];
          v87[9] = v86[9];
          v87[10] = v86[10];
          v87[11] = v86[11];
          v15[1] += 192LL;
        }
      }
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v139);
      SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInitialize::~StorageSenseCleanmgrPluginInitialize((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInitialize *)v178);
      SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo::~PluginInfo((SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo *)v141);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::~StorageSenseCleanmgrPluginInstantiate((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate *)v177);
    }
LABEL_88:
    v21 = v137 + 1;
    v137 = v21;
  }
  while ( v21 < cSubKeys );
  v125 = LODWORD(v4);
  cchName = LODWORD(v5);
  pcbData = LODWORD(v6);
LABEL_90:
  v88 = v158;
  v89 = v159;
  v90 = v160;
  v91 = v161;
  v92 = v164;
  v93 = v165;
  v94 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
  v168 = v88;
  v169 = v89;
  v170 = v90;
  v171 = v91;
  v172 = v95;
  v173 = v96;
  v174 = v92;
  v175 = v93;
  v176 = v97;
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrInitialize::Stop(
    &v168,
    v94,
    v98,
    0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)v8 + 1) - *(_QWORD *)v8) >> 3),
    &v168);
  v99 = v125;
  v100 = pcbData;
  if ( 0xD37A6F4DE9BD37A7uLL * ((__int64)(v9[1] - *v9) >> 3) )
  {
    LOWORD(pvData) = 14247 * ((__int64)(v9[1] - *v9) >> 3);
    v102 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v102 && (unsigned __int8)tlgKeywordOn(v102, 0x400000000000LL) )
    {
      *(_QWORD *)&pclsid.Data1 = *v9;
      *(_DWORD *)pclsid.Data4 = 184 * (unsigned __int16)pvData;
      pv = &pvData;
      v136 = 2;
      *(_QWORD *)&v157.Data1 = (char *)&v158 + 1;
      cbData = v133;
      LODWORD(v131) = v100;
      v125 = v99;
      *(_QWORD *)&v138.Data1 = 0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)v8 + 1) - *(_QWORD *)v8) >> 3);
      pcbData = cSubKeys;
      v132 = (LPVOID)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
      v130 = (LPVOID)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v103,
        (unsigned int)&unk_180155B60,
        v103,
        v104,
        (__int64)&v130,
        (__int64)&v132,
        (__int64)&pcbData,
        (__int64)&v138,
        (__int64)&v125,
        (__int64)&v131,
        (__int64)&cbData,
        (__int64)&v157,
        (__int64)&pv,
        (__int64)&pclsid);
    }
    if ( *v9 != v9[1] )
      v9[1] = *v9;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart>::shrink_to_fit(v9, v101, v102);
  }
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v11[1] - *v11) >> 6) )
  {
    LOWORD(pvData) = -21845 * ((__int64)(v11[1] - *v11) >> 6);
    v106 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v106 && (unsigned __int8)tlgKeywordOn(v106, 0x400000000000LL) )
    {
      *(_QWORD *)&pclsid.Data1 = *v11;
      *(_DWORD *)pclsid.Data4 = 192 * (unsigned __int16)pvData;
      pv = &pvData;
      v136 = 2;
      *(_QWORD *)&v157.Data1 = (char *)&v158 + 1;
      cbData = v133;
      LODWORD(v131) = v100;
      v125 = v99;
      *(_QWORD *)&v138.Data1 = 0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)v8 + 1) - *(_QWORD *)v8) >> 3);
      pcbData = cSubKeys;
      v132 = (LPVOID)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
      v130 = (LPVOID)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v107,
        (unsigned int)&unk_180155A44,
        v107,
        v108,
        (__int64)&v130,
        (__int64)&v132,
        (__int64)&pcbData,
        (__int64)&v138,
        (__int64)&v125,
        (__int64)&v131,
        (__int64)&cbData,
        (__int64)&v157,
        (__int64)&pv,
        (__int64)&pclsid);
    }
    v109 = *v11;
    if ( *v11 == v11[1] )
      v109 = v11[1];
    else
      v11[1] = v109;
    if ( v109 != v11[2] )
    {
      if ( *v11 == v109 )
      {
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationStopData>::_Tidy(
          v11,
          v105,
          v106);
      }
      else
      {
        *(_QWORD *)&v157.Data1 = 0xAAAAAAAAAAAAAAABuLL * ((v109 - *v11) >> 6);
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>::_Reallocate<1>(
          v11,
          &v157,
          v106);
      }
    }
  }
  v110 = cchName;
  if ( 0xD37A6F4DE9BD37A7uLL * ((__int64)(v13[1] - *v13) >> 3) )
  {
    LOWORD(pvData) = 14247 * ((__int64)(v13[1] - *v13) >> 3);
    v112 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v112 && (unsigned __int8)tlgKeywordOn(v112, 0x400000000000LL) )
    {
      *(_QWORD *)&pclsid.Data1 = *v13;
      *(_DWORD *)pclsid.Data4 = 184 * (unsigned __int16)pvData;
      pv = &pvData;
      v136 = 2;
      *(_QWORD *)&v157.Data1 = (char *)&v158 + 1;
      cbData = v110;
      LODWORD(v131) = v99;
      *(_QWORD *)&v138.Data1 = 0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)v8 + 1) - *(_QWORD *)v8) >> 3);
      cchName = cSubKeys;
      v132 = (LPVOID)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
      v130 = (LPVOID)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v113,
        (unsigned int)&unk_180155963,
        v113,
        v114,
        (__int64)&v130,
        (__int64)&v132,
        (__int64)&cchName,
        (__int64)&v138,
        (__int64)&v131,
        (__int64)&cbData,
        (__int64)&v157,
        (__int64)&pv,
        (__int64)&pclsid);
    }
    if ( *v13 != v13[1] )
      v13[1] = *v13;
    std::vector<SystemSettings::StorageSenseHandlers::PluginScanStart>::shrink_to_fit(v13, v111, v112);
  }
  if ( 0xAAAAAAAAAAAAAAABuLL * ((__int64)(v15[1] - *v15) >> 6) )
  {
    LOWORD(pvData) = -21845 * ((__int64)(v15[1] - *v15) >> 6);
    v116 = SettingsHandlersStorageSenseLogging::Provider();
    if ( *(_DWORD *)v116 && (unsigned __int8)tlgKeywordOn(v116, 0x400000000000LL) )
    {
      *(_QWORD *)&pclsid.Data1 = *v15;
      *(_DWORD *)pclsid.Data4 = 192 * (unsigned __int16)pvData;
      pv = &pvData;
      v136 = 2;
      *(_QWORD *)&v157.Data1 = (char *)&v158 + 1;
      cbData = v110;
      LODWORD(v131) = v99;
      *(_QWORD *)&v138.Data1 = 0x34F72C234F72C235LL * ((__int64)(*((_QWORD *)v8 + 1) - *(_QWORD *)v8) >> 3);
      cchName = cSubKeys;
      v132 = (LPVOID)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v134);
      v130 = (LPVOID)0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v117,
        (unsigned int)&unk_18015585F,
        v117,
        v118,
        (__int64)&v130,
        (__int64)&v132,
        (__int64)&cchName,
        (__int64)&v138,
        (__int64)&v131,
        (__int64)&cbData,
        (__int64)&v157,
        (__int64)&pv,
        (__int64)&pclsid);
    }
    v119 = *v15;
    if ( *v15 == v15[1] )
      v119 = v15[1];
    else
      v15[1] = v119;
    if ( v119 != v15[2] )
    {
      if ( *v15 == v119 )
      {
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInstantiationStopData>::_Tidy(
          v15,
          v115,
          v116);
      }
      else
      {
        *(_QWORD *)&v157.Data1 = 0xAAAAAAAAAAAAAAABuLL * ((v119 - *v15) >> 6);
        std::vector<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInitializeStopData>::_Reallocate<1>(
          v15,
          &v157,
          v116);
      }
    }
  }
  v7 = 0;
  if ( *((_QWORD *)v8 + 1) == *(_QWORD *)v8 )
    v7 = -2147467259;
LABEL_128:
  SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrInitialize::~StorageSenseCleanmgrInitialize((SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrInitialize *)v179);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800c4ca0  mov     rax, rsp
0x1800c4ca3  push    rbp
0x1800c4ca4  push    rbx
0x1800c4ca5  push    rsi
0x1800c4ca6  push    rdi
0x1800c4ca7  push    r12
0x1800c4ca9  push    r13
0x1800c4cab  push    r14
0x1800c4cad  push    r15
0x1800c4caf  lea     rbp, [rax-9A8h]
0x1800c4cb6  sub     rsp, 0A68h
0x1800c4cbd  movaps  xmmword ptr [rax-58h], xmm6
0x1800c4cc1  movaps  xmmword ptr [rax-68h], xmm7
0x1800c4cc5  movaps  xmmword ptr [rax-78h], xmm8
0x1800c4cca  movaps  xmmword ptr [rax-88h], xmm9
0x1800c4cd2  movaps  xmmword ptr [rax-98h], xmm10
0x1800c4cda  movaps  xmmword ptr [rax-0A8h], xmm11
0x1800c4ce2  movaps  xmmword ptr [rax-0B8h], xmm13
0x1800c4cea  movaps  xmmword ptr [rax-0C8h], xmm14
0x1800c4cf2  mov     rax, cs:__security_cookie
0x1800c4cf9  xor     rax, rsp
0x1800c4cfc  mov     [rbp+9A0h+var_D0], rax
0x1800c4d03  mov     rdi, rdx
0x1800c4d06  mov     rbx, rcx
0x1800c4d09  mov     [rbp+9A0h+hKey], 0
0x1800c4d11  mov     [rbp+9A0h+cSubKeys], 0
0x1800c4d18  mov     qword ptr [rbp+9A0h+var_8A0.Data1+2], 5C003Ah
0x1800c4d23  xorps   xmm10, xmm10
0x1800c4d27  movss   [rsp+0AA0h+var_A28], xmm10
0x1800c4d2e  xorps   xmm11, xmm11
0x1800c4d32  movss   [rbp+9A0h+cchName], xmm11
0x1800c4d38  xorps   xmm14, xmm14
0x1800c4d3c  movss   [rsp+0AA0h+pcbData], xmm14
0x1800c4d43  xorps   xmm0, xmm0
0x1800c4d46  movups  xmmword ptr [rbp+9A0h+pguid.Data1], xmm0
0x1800c4d4d  lea     rcx, [rbp+9A0h+pguid]; pguid
0x1800c4d54  call    cs:__imp_CoCreateGuid
0x1800c4d5a  xor     edx, edx; Val
0x1800c4d5c  mov     r8d, 82h; Size
0x1800c4d62  lea     rcx, [rbp+9A0h+var_880]; void *
0x1800c4d69  call    memset_0
0x1800c4d6e  lea     r8, [rbp+9A0h+pguid]
0x1800c4d75  mov     edx, 2
0x1800c4d7a  lea     rcx, [rbp+9A0h+var_880]
0x1800c4d81  call    cs:__imp_RtlInitializeCorrelationVector
0x1800c4d87  lea     rdx, aStoragesensecl_1; "StorageSenseCleanmgrInitialize"
0x1800c4d8e  lea     rcx, [rbp+9A0h+var_480]; struct wil::details::IFailureCallback *
0x1800c4d95  call    ??0?$ActivityBase@VSettingsHandlersStorageSenseLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<SettingsHandlersStorageSenseLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<SettingsHandlersStorageSenseLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800c4d9a  lea     rax, ??_7StorageSenseCleanmgrInitialize@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@6B@; const SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrInitialize::`vftable'
0x1800c4da1  mov     [rbp+9A0h+var_480], rax
0x1800c4da8  call    cs:__imp_GetTickCount64
0x1800c4dae  mov     cs:?beforeInitializationTick@Internal@StorageSenseHandlers@SystemSettings@@3_KA, rax; unsigned __int64 SystemSettings::StorageSenseHandlers::Internal::beforeInitializationTick
0x1800c4db5  test    rdi, rdi
0x1800c4db8  jnz     short loc_1800C4DC4
0x1800c4dba  mov     ebx, 80070057h
0x1800c4dbf  jmp     loc_1800C4F06
0x1800c4dc4  lea     r15, [rbx+30h]
0x1800c4dc8  mov     rdx, [r15+8]
0x1800c4dcc  cmp     [r15], rdx
0x1800c4dcf  jz      short loc_1800C4DE0
0x1800c4dd1  mov     rcx, [r15]; this
0x1800c4dd4  call    ??$_Destroy_range@V?$allocator@UPluginInfo@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@@std@@@std@@YAXPEAUPluginInfo@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@QEAU1234@AEAV?$allocator@UPluginInfo@CleanmgrHelper@StorageSenseHandlers@SystemSettings@@@0@@Z; std::_Destroy_range<std::allocator<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo>>(SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo *,SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo * const,std::allocator<SystemSettings::StorageSenseHandlers::CleanmgrHelper::PluginInfo> &)
0x1800c4dd9  mov     rax, [r15]
0x1800c4ddc  mov     [r15+8], rax
0x1800c4de0  lea     r13, [rbx+48h]
0x1800c4de4  mov     rax, [r13+0]
0x1800c4de8  cmp     rax, [r13+8]
0x1800c4dec  jz      short loc_1800C4DF2
0x1800c4dee  mov     [r13+8], rax
0x1800c4df2  lea     r14, [rbx+60h]
0x1800c4df6  mov     rax, [r14]
0x1800c4df9  cmp     rax, [r14+8]
0x1800c4dfd  jz      short loc_1800C4E03
0x1800c4dff  mov     [r14+8], rax
0x1800c4e03  lea     r12, [rbx+78h]
0x1800c4e07  mov     rax, [r12]
0x1800c4e0b  cmp     rax, [r12+8]
0x1800c4e10  jz      short loc_1800C4E17
0x1800c4e12  mov     [r12+8], rax
0x1800c4e17  lea     rsi, [rbx+90h]
0x1800c4e1e  mov     rax, [rsi]
0x1800c4e21  cmp     rax, [rsi+8]
0x1800c4e25  jz      short loc_1800C4E2B
0x1800c4e27  mov     [rsi+8], rax
0x1800c4e2b  movzx   eax, word ptr [rdi]
0x1800c4e2e  mov     word ptr [rbp+9A0h+var_8A0.Data1], ax
0x1800c4e35  lea     rdi, [rbx+10h]
0x1800c4e39  mov     [rbp+9A0h+var_9E8], rdi
0x1800c4e3d  lea     rdx, [rbp+9A0h+var_8A0]
0x1800c4e44  mov     rcx, rdi
0x1800c4e47  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800c4e4c  xor     edx, edx
0x1800c4e4e  lea     rcx, [rbp+9A0h+hKey]
0x1800c4e52  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c4e57  lea     rax, [rbp+9A0h+hKey]
0x1800c4e5b  mov     [rsp+0AA0h+phkResult], rax; phkResult
0x1800c4e60  mov     r9d, 20019h; samDesired
0x1800c4e66  xor     r8d, r8d; ulOptions
0x1800c4e69  lea     rdx, aSoftwareMicros_22; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800c4e70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800c4e77  call    cs:__imp_RegOpenKeyExW
0x1800c4e7d  mov     ebx, eax
0x1800c4e7f  xor     eax, eax
0x1800c4e81  test    ebx, ebx
0x1800c4e83  jle     short loc_1800C4E90
0x1800c4e85  movzx   ebx, bx
0x1800c4e88  or      ebx, 80070000h
0x1800c4e8e  test    ebx, ebx
0x1800c4e90  jns     short loc_1800C4E99
0x1800c4e92  mov     edx, 4Eh ; 'N'
0x1800c4e97  jmp     short loc_1800C4EEF
0x1800c4e99  mov     [rsp+0AA0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800c4e9e  mov     [rsp+0AA0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800c4ea3  mov     [rsp+0AA0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800c4ea8  mov     [rsp+0AA0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800c4ead  mov     [rsp+0AA0h+lpcValues], rax; lpcValues
0x1800c4eb2  mov     [rsp+0AA0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800c4eb7  mov     [rsp+0AA0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800c4ebc  lea     rax, [rbp+9A0h+cSubKeys]
0x1800c4ec0  mov     [rsp+0AA0h+phkResult], rax; int
0x1800c4ec5  xor     r9d, r9d; lpReserved
0x1800c4ec8  xor     r8d, r8d; lpcchClass
0x1800c4ecb  xor     edx, edx; lpClass
0x1800c4ecd  mov     rcx, [rbp+9A0h+hKey]; hKey
0x1800c4ed1  call    cs:__imp_RegQueryInfoKeyW
0x1800c4ed7  mov     ebx, eax
0x1800c4ed9  test    eax, eax
0x1800c4edb  jle     short loc_1800C4EE6
0x1800c4edd  movzx   ebx, ax
0x1800c4ee0  or      ebx, 80070000h
0x1800c4ee6  test    ebx, ebx
0x1800c4ee8  jns     short loc_1800C4F0B
0x1800c4eea  mov     edx, 5Ch ; '\'; void *
0x1800c4eef  mov     r9d, ebx; char *
0x1800c4ef2  lea     r8, aOnecoreuapShel_12; "onecoreuap\\shell\\coresettinghandlers"...
0x1800c4ef9  mov     rcx, [rbp+9A8h]; this
0x1800c4f00  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c4f05  nop
0x1800c4f06  jmp     loc_1800C6103
0x1800c4f0b  xor     ebx, ebx
0x1800c4f0d  mov     [rbp+9A0h+var_9F0], ebx
0x1800c4f10  mov     eax, ebx
0x1800c4f12  mov     [rbp+9A0h+var_9D0], ebx
0x1800c4f15  mov     r8d, [rbp+9A0h+cSubKeys]
0x1800c4f19  test    r8d, r8d
0x1800c4f1c  jz      loc_1800C5A91
0x1800c4f22  movdqa  xmm13, cs:__xmm@00000000000000070000000000000000
0x1800c4f2b  mov     [rbp+9A0h+cchName], 104h
0x1800c4f32  mov     [rsp+0AA0h+lpcValues], rbx; lpftLastWriteTime
0x1800c4f37  mov     [rsp+0AA0h+lpcbMaxClassLen], rbx; lpcchClass
0x1800c4f3c  mov     [rsp+0AA0h+lpcbMaxSubKeyLen], rbx; lpClass
0x1800c4f41  mov     [rsp+0AA0h+phkResult], rbx; lpReserved
0x1800c4f46  lea     r9, [rbp+9A0h+cchName]; lpcchName
0x1800c4f4a  lea     r8, [rbp+9A0h+Name]; lpName
0x1800c4f51  mov     edx, eax; dwIndex
0x1800c4f53  mov     rcx, [rbp+9A0h+hKey]; hKey
0x1800c4f57  call    cs:__imp_RegEnumKeyExW
0x1800c4f5d  test    eax, eax
0x1800c4f5f  jle     short loc_1800C4F69
0x1800c4f61  movzx   eax, ax
0x1800c4f64  or      eax, 80070000h
0x1800c4f69  mov     dword ptr [rbp+9A0h+var_A00], eax
0x1800c4f6c  test    eax, eax
0x1800c4f6e  js      loc_1800C5A68
0x1800c4f74  lea     rax, [rbp+9A0h+var_880]
0x1800c4f7b  mov     [rsp+0AA0h+phkResult], rax
0x1800c4f80  lea     r9, [rbp+9A0h+var_A00]
0x1800c4f84  lea     r8, [rbp+9A0h+Name]
0x1800c4f8b  lea     rcx, [rbp+9A0h+var_720]
0x1800c4f92  call    ??$?0AEAY0BAE@GAEAJAEAUCORRELATION_VECTOR@@@StorageSenseCleanmgrPluginInstantiate@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@AEAA@U?$integral_constant@D$0A@@wistd@@AEAY0BAE@GAEAJAEAUCORRELATION_VECTOR@@@Z; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::StorageSenseCleanmgrPluginInstantiate(wistd::integral_constant<char,0>,ushort (&)[260],long &,CORRELATION_VECTOR &)
0x1800c4f97  nop
0x1800c4f98  mov     [rbp+9A0h+hkey], rbx
0x1800c4f9c  xor     edx, edx
0x1800c4f9e  lea     rcx, [rbp+9A0h+hkey]
0x1800c4fa2  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800c4fa7  lea     rax, [rbp+9A0h+hkey]
0x1800c4fab  mov     [rsp+0AA0h+phkResult], rax; phkResult
0x1800c4fb0  mov     r9d, 20019h; samDesired
0x1800c4fb6  xor     r8d, r8d; ulOptions
0x1800c4fb9  lea     rdx, [rbp+9A0h+Name]; lpSubKey
0x1800c4fc0  mov     rcx, [rbp+9A0h+hKey]; hKey
0x1800c4fc4  call    cs:__imp_RegOpenKeyExW
0x1800c4fca  test    eax, eax
0x1800c4fcc  jle     short loc_1800C4FD8
0x1800c4fce  movzx   eax, ax
0x1800c4fd1  or      eax, 80070000h
0x1800c4fd6  test    eax, eax
0x1800c4fd8  jns     short loc_1800C4FF5
0x1800c4fda  lea     rcx, [rbp+9A0h+hkey]
0x1800c4fde  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800c4fe3  nop
0x1800c4fe4  lea     rcx, [rbp+9A0h+var_720]; this
0x1800c4feb  call    ??1StorageSenseCleanmgrPluginInstantiate@SSTelemetry@Internal@StorageSenseHandlers@SystemSettings@@QEAA@XZ; SystemSettings::StorageSenseHandlers::Internal::SSTelemetry::StorageSenseCleanmgrPluginInstantiate::~StorageSenseCleanmgrPluginInstantiate(void)
0x1800c4ff0  jmp     loc_1800C5A68
0x1800c4ff5  mov     [rsp+0AA0h+cbData], 4Eh ; 'N'
0x1800c4ffd  lea     rax, [rsp+0AA0h+cbData]
0x1800c5002  mov     [rsp+0AA0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800c5007  lea     rax, [rbp+9A0h+Data]
0x1800c500e  mov     [rsp+0AA0h+phkResult], rax; lpData
0x1800c5013  xor     r9d, r9d; lpType
0x1800c5016  xor     r8d, r8d; lpReserved
0x1800c5019  xor     edx, edx; lpValueName
0x1800c501b  mov     rcx, [rbp+9A0h+hkey]; hKey
0x1800c501f  call    cs:__imp_RegQueryValueExW
0x1800c5025  test    eax, eax
0x1800c5027  jle     short loc_1800C5033
0x1800c5029  movzx   eax, ax
0x1800c502c  or      eax, 80070000h
0x1800c5031  test    eax, eax
0x1800c5033  js      short loc_1800C4FDA
0x1800c5035  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800c503c  movdqu  xmmword ptr [rbp+9A0h+pclsid.Data1], xmm0
0x1800c5044  lea     rdx, [rbp+9A0h+pclsid]; pclsid
0x1800c504b  lea     rcx, [rbp+9A0h+Data]; lpsz
0x1800c5052  call    cs:__imp_CLSIDFromString
0x1800c5058  test    eax, eax
0x1800c505a  js      loc_1800C4FDA
0x1800c5060  xorps   xmm0, xmm0
0x1800c5063  movups  [rbp+9A0h+var_9A0], xmm0
0x1800c5067  movdqa  [rbp+9A0h+var_990], xmm13
0x1800c506d  mov     word ptr [rbp+9A0h+var_9A0], bx
0x1800c5071  movups  [rbp+9A0h+var_980], xmm0
0x1800c5075  mov     [rbp+9A0h+var_970], rbx
0x1800c5079  mov     ecx, 7
0x1800c507e  mov     [rbp+9A0h+var_968], rcx
0x1800c5082  mov     word ptr [rbp+9A0h+var_980], bx
0x1800c5086  movups  [rbp+9A0h+var_960], xmm0
0x1800c508a  mov     [rbp+9A0h+var_950], rbx
0x1800c508e  mov     [rbp+9A0h+var_948], rcx
0x1800c5092  mov     word ptr [rbp+9A0h+var_960], bx
0x1800c5096  movups  [rbp+9A0h+var_940], xmm0
0x1800c509a  movdqa  [rbp+9A0h+var_930], xmm13
0x1800c50a0  mov     word ptr [rbp+9A0h+var_940], bx
0x1800c50a4  movups  [rbp+9A0h+var_920], xmm0
0x1800c50ab  movdqa  [rbp+9A0h+var_910], xmm13
0x1800c50b4  mov     word ptr [rbp+9A0h+var_920], bx
0x1800c50bb  movups  [rbp+9A0h+var_900], xmm0
0x1800c50c2  movdqa  [rbp+9A0h+var_8F0], xmm13
0x1800c50cb  mov     word ptr [rbp+9A0h+var_900], bx
0x1800c50d2  movups  xmmword ptr [rbp+9A0h+var_8E0], xmm0
0x1800c50d9  mov     [rbp+9A0h+ppv], rbx
0x1800c50e0  movups  xmmword ptr [rbp+9A0h+var_8C8], xmm0
0x1800c50e7  mov     [rsp+0AA0h+pvData], ebx
0x1800c50eb  mov     [rsp+0AA0h+pcbData], 4
0x1800c50f3  lea     rax, [rsp+0AA0h+pcbData]
0x1800c50f8  mov     [rsp+0AA0h+lpcbMaxClassLen], rax; pcbData
0x1800c50fd  lea     rax, [rsp+0AA0h+pvData]
0x1800c5102  mov     [rsp+0AA0h+lpcbMaxSubKeyLen], rax; pvData
0x1800c5107  mov     [rsp+0AA0h+phkResult], rbx; pdwType
0x1800c510c  lea     edi, [rcx+11h]
0x1800c510f  mov     r9d, edi; dwFlags
0x1800c5112  lea     r8, aAutorun; "Autorun"
0x1800c5119  xor     edx, edx; lpSubKey
0x1800c511b  mov     rcx, [rbp+9A0h+hkey]; hkey
0x1800c511f  call    cs:__imp_RegGetValueW
0x1800c5125  test    eax, eax
0x1800c5127  jnz     short loc_1800C5137
0x1800c5129  mov     al, byte ptr [rsp+0AA0h+pvData]
0x1800c512d  and     al, 1
0x1800c512f  mov     byte ptr [rbp+9A0h+var_8E0], al
0x1800c5135  jmp     short loc_1800C513D
0x1800c5137  mov     byte ptr [rbp+9A0h+var_8E0], bl
0x1800c513d  mov     [rsp+0AA0h+pvData], ebx
0x1800c5141  lea     rax, [rsp+0AA0h+pcbData]
0x1800c5146  mov     [rsp+0AA0h+lpcbMaxClassLen], rax; pcbData
0x1800c514b  lea     rax, [rsp+0AA0h+pvData]
0x1800c5150  mov     [rsp+0AA0h+lpcbMaxSubKeyLen], rax; pvData
0x1800c5155  mov     [rsp+0AA0h+phkResult], rbx; pdwType
0x1800c515a  mov     r9d, edi; dwFlags
0x1800c515d  lea     r8, aReserveidhint; "ReserveIDHint"
0x1800c5164  xor     edx, edx; lpSubKey
0x1800c5166  mov     rcx, [rbp+9A0h+hkey]; hkey
0x1800c516a  call    cs:__imp_RegGetValueW
0x1800c5170  test    eax, eax
0x1800c5172  jnz     short loc_1800C517F
0x1800c5174  mov     eax, [rsp+0AA0h+pvData]
0x1800c5178  mov     qword ptr [rbp+9A0h+var_8E0+8], rax
0x1800c517f  lea     rdx, [rbp+9A0h+Name]
0x1800c5186  lea     rcx, [rbp+9A0h+var_940]
0x1800c518a  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x1800c518f  movaps  xmm0, xmmword ptr [rbp+9A0h+pclsid.Data1]
0x1800c5196  movdqa  xmmword ptr [rbp+9A0h+var_8A0.Data1], xmm0
0x1800c519e  movzx   r9d, byte ptr [rbp+9A0h+var_8E0]
0x1800c51a6  lea     rcx, [rbp+9A0h+var_940]
0x1800c51aa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800c51af  mov     rdx, rax; unsigned __int16 *
0x1800c51b2  mov     edi, [rbp+9A0h+var_9D0]
0x1800c51b5  mov     dword ptr [rsp+0AA0h+phkResult], edi; unsigned int
0x1800c51b9  lea     r8, [rbp+9A0h+var_8A0]; struct _GUID
0x1800c51c0  lea     rcx, [rbp+9A0h+var_7E0]; this
0x1800c51c7  call    ??0PluginScanStart@StorageSenseHandlers@SystemSettings@@QEAA@PEBGU_GUID@@HI@Z; SystemSettings::StorageSenseHandlers::PluginScanStart::PluginScanStart(ushort const *,_GUID,int,uint)
0x1800c51cc  mov     rdx, [r13+8]
0x1800c51d0  cmp     rdx, [r13+10h]
0x1800c51d4  jz      loc_1800C525A
0x1800c51da  movups  xmm0, xmmword ptr [rax]
0x1800c51dd  movups  xmmword ptr [rdx], xmm0
0x1800c51e0  movups  xmm1, xmmword ptr [rax+10h]
0x1800c51e4  movups  xmmword ptr [rdx+10h], xmm1
0x1800c51e8  movups  xmm0, xmmword ptr [rax+20h]
0x1800c51ec  movups  xmmword ptr [rdx+20h], xmm0
  ... truncated ...
```
