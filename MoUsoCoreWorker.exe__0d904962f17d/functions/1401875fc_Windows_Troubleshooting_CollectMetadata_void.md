# Windows::Troubleshooting::CollectMetadata(void)

- ea: `0x1401875fc`
- end: `0x140187c5c`
- name: `?CollectMetadata@Troubleshooting@Windows@@AEAAXXZ`
- size: `1632`
- prototype: `void __fastcall(Windows::Troubleshooting *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config`

## callers

- `0x1401872f8`

## callees

- `0x14003c578`
- `0x1400430dc`
- `0x140043354`
- `0x140045404`
- `0x14004a998`
- `0x14004b800`
- `0x14004f25c`
- `0x140117c70`
- `0x1401875fc`
- `0x14018968c`
- `0x140189734`
- `0x14018989c`
- `0x14018a35c`
- `0x14018aaec`
- `0x14018b218`
- `0x140379070`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140187b7f`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x140187b7f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14018798f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140187a11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140187a93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140187b15`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14018798f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140187a11`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140187a93`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140187b15`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401876df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14018792e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1401876df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14018792e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140187b56`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140187b56`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Windows::Troubleshooting::CollectMetadata(Windows::Troubleshooting *this)
{
  __int64 v2; // rax
  LSTATUS v3; // eax
  __int64 v4; // r8
  signed int v5; // ecx
  __int64 v6; // r8
  char v7; // al
  __int64 v8; // rax
  _QWORD *v9; // rdx
  __int64 v10; // rax
  __int64 v11; // r8
  char v12; // al
  __int64 v13; // rax
  _QWORD *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r8
  char v17; // al
  __int64 v18; // rax
  _QWORD *v19; // rdx
  __int64 v20; // rax
  char v21; // al
  __int64 v22; // rax
  _QWORD *v23; // rdx
  __int64 v24; // rax
  HKEY v25; // rcx
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  __int64 v33; // rax
  const char *v34; // r9
  __int64 v35; // rax
  __int64 v36; // rax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  _BYTE v43[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE Src[32]; // [rsp+60h] [rbp-A0h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+80h] [rbp-80h] BYREF
  HKEY phkResult; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD v47[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v48; // [rsp+1B8h] [rbp+B8h]
  unsigned __int64 v49; // [rsp+1C0h] [rbp+C0h]
  __int64 v50; // [rsp+1C8h] [rbp+C8h]
  HKEY hkey[2]; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v52[34]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE pvData[528]; // [rsp+2F0h] [rbp+1F0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+518h] [rbp+418h]

  memset(v52, 0, 0x108u);
  hkey[0] = (HKEY)L"metadata.ini";
  hkey[1] = (HKEY)12;
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v43, hkey);
  v2 = std::filesystem::operator/(Src, (char *)this + 16, v43);
  std::wofstream::wofstream(v52, v2);
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v43);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl'::`2'::impl) )
  {
    phkResult = 0;
    v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Versions", 0, 0x20019u, &phkResult);
    v5 = (unsigned __int16)v3 | 0x80070000;
    if ( v3 <= 0 )
      v5 = v3;
    if ( v5 >= 0 )
    {
      wil::reg::try_get_value_string(v47, phkResult, v4, L"Label");
      v7 = v50;
      if ( (_BYTE)v50 )
      {
        v8 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"bldbrch=");
        v9 = v47;
        if ( v49 > 7 )
          v9 = (_QWORD *)v47[0];
        v10 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v8, v9, v48);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v10);
        v7 = v50;
      }
      if ( v7 )
        std::wstring::~wstring(v47);
      wil::reg::try_get_value_string(v47, phkResult, v6, L"ParentBranchBuild");
      v12 = v50;
      if ( (_BYTE)v50 )
      {
        v13 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"Build=");
        v14 = v47;
        if ( v49 > 7 )
          v14 = (_QWORD *)v47[0];
        v15 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v13, v14, v48);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v15);
        v12 = v50;
      }
      if ( v12 )
        std::wstring::~wstring(v47);
      wil::reg::try_get_value_string(v47, phkResult, v11, L"Builder");
      v17 = v50;
      if ( (_BYTE)v50 )
      {
        v18 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"builder=");
        v19 = v47;
        if ( v49 > 7 )
          v19 = (_QWORD *)v47[0];
        v20 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v18, v19, v48);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v20);
        v17 = v50;
      }
      if ( v17 )
        std::wstring::~wstring(v47);
      wil::reg::try_get_value_string(v47, phkResult, v16, L"TimeStamp");
      v21 = v50;
      if ( (_BYTE)v50 )
      {
        v22 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"BuildTimestamp=");
        v23 = v47;
        if ( v49 > 7 )
          v23 = (_QWORD *)v47[0];
        v24 = std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(v22, v23, v48);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v24);
        v21 = v50;
      }
      if ( v21 )
        std::wstring::~wstring(v47);
    }
    v25 = phkResult;
  }
  else
  {
    hkey[0] = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Versions", 0, 0x20019u, hkey) )
    {
      memset(pvData, 0, 0x208u);
      LODWORD(phkResult) = 520;
      if ( !RegGetValueW(hkey[0], 0, L"Label", 2u, 0, pvData, (LPDWORD)&phkResult) )
      {
        v26 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"bldbrch=");
        v27 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v26, pvData);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v27);
      }
      memset(pvData, 0, 0x208u);
      LODWORD(phkResult) = 520;
      if ( !RegGetValueW(hkey[0], 0, L"ParentBranchBuild", 2u, 0, pvData, (LPDWORD)&phkResult) )
      {
        v28 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"Build=");
        v29 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v28, pvData);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v29);
      }
      memset(pvData, 0, 0x208u);
      LODWORD(phkResult) = 520;
      if ( !RegGetValueW(hkey[0], 0, L"Builder", 2u, 0, pvData, (LPDWORD)&phkResult) )
      {
        v30 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"builder=");
        v31 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v30, pvData);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v31);
      }
      memset(pvData, 0, 0x208u);
      LODWORD(phkResult) = 520;
      if ( !RegGetValueW(hkey[0], 0, L"TimeStamp", 2u, 0, pvData, (LPDWORD)&phkResult) )
      {
        v32 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"BuildTimestamp=");
        v33 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v32, pvData);
        std::endl<wchar_t,std::char_traits<wchar_t>>(v33);
      }
    }
    v25 = hkey[0];
  }
  if ( v25 )
    RegCloseKey(v25);
  memset(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  if ( !GetVersionExW(&VersionInformation) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xB0,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\troubleshooting\\Troubleshooting.cpp",
      v34);
  v35 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v52, L"OsVersion=");
  v36 = std::wostream::operator<<(v35, VersionInformation.dwMajorVersion);
  v37 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v36, L".");
  v38 = std::wostream::operator<<(v37, VersionInformation.dwMinorVersion);
  v39 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v38, L".");
  v40 = std::wostream::operator<<(v39, LOWORD(VersionInformation.dwBuildNumber));
  v41 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v40, L".");
  v42 = std::wostream::operator<<(v41, HIWORD(VersionInformation.dwBuildNumber));
  std::endl<wchar_t,std::char_traits<wchar_t>>(v42);
  std::wofstream::~wofstream<wchar_t,std::char_traits<wchar_t>>(&v52[21]);
  v52[21] = &std::wios::`vftable';
  std::ios_base::~ios_base((std::ios_base *)&v52[21]);
}

```

## disassembly

```asm
0x1401875fc  mov     [rsp-8+arg_8], rbx
0x140187601  push    rbp
0x140187602  lea     rbp, [rsp-410h]
0x14018760a  sub     rsp, 510h
0x140187611  mov     rax, cs:__security_cookie
0x140187618  xor     rax, rsp
0x14018761b  mov     [rbp+410h+var_10], rax
0x140187622  mov     rbx, rcx
0x140187625  xor     edx, edx; Val
0x140187627  mov     r8d, 108h; Size
0x14018762d  lea     rcx, [rbp+410h+var_330]; void *
0x140187634  call    memset
0x140187639  lea     rax, aMetadataIni; "metadata.ini"
0x140187640  mov     [rbp+410h+hkey], rax
0x140187647  mov     [rbp+410h+var_338], 0Ch
0x140187652  lea     rdx, [rbp+410h+hkey]
0x140187659  lea     rcx, [rsp+510h+var_4D0]
0x14018765e  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x140187663  nop
0x140187664  lea     rdx, [rbx+10h]; void *
0x140187668  lea     r8, [rsp+510h+var_4D0]; void *
0x14018766d  lea     rcx, [rsp+510h+Src]; Src
0x140187672  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x140187677  nop
0x140187678  mov     rdx, rax
0x14018767b  lea     rcx, [rbp+410h+var_330]
0x140187682  call    ??$?0Vpath@filesystem@std@@$0A@@?$basic_ofstream@_WU?$char_traits@_W@std@@@std@@QEAA@AEBVpath@filesystem@1@HH@Z; std::wofstream::wofstream(std::filesystem::path const &,int,int)
0x140187687  nop
0x140187688  lea     rcx, [rsp+510h+Src]
0x14018768d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140187692  nop
0x140187693  lea     rcx, [rsp+510h+var_4D0]
0x140187698  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14018769d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::GetImpl(void)'::`2'::impl
0x1401876a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_LintFixes_57550863>::__private_IsEnabled(void)
0x1401876a9  test    al, al
0x1401876ab  jz      loc_140187900
0x1401876b1  mov     [rbp+410h+var_370], 0
0x1401876bc  lea     rax, [rbp+410h+var_370]
0x1401876c3  mov     [rsp+510h+phkResult], rax; phkResult
0x1401876c8  mov     r9d, 20019h; samDesired
0x1401876ce  xor     r8d, r8d; ulOptions
0x1401876d1  lea     rdx, aSystemVersions; "System\\Versions"
0x1401876d8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1401876df  call    cs:__imp_RegOpenKeyExW
0x1401876e5  movzx   ecx, ax
0x1401876e8  or      ecx, 80070000h
0x1401876ee  test    eax, eax
0x1401876f0  cmovle  ecx, eax
0x1401876f3  test    ecx, ecx
0x1401876f5  js      loc_1401878F4
0x1401876fb  lea     r9, Value; "Label"
0x140187702  mov     rdx, [rbp+410h+var_370]
0x140187709  lea     rcx, [rbp+410h+var_368]
0x140187710  call    ?try_get_value_string@reg@wil@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x140187715  nop
0x140187716  mov     rax, [rbp+410h+var_348]
0x14018771d  test    al, al
0x14018771f  jz      short loc_140187769
0x140187721  lea     rdx, aBldbrch; "bldbrch="
0x140187728  lea     rcx, [rbp+410h+var_330]
0x14018772f  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187734  lea     rdx, [rbp+410h+var_368]
0x14018773b  cmp     [rbp+410h+var_350], 7
0x140187743  cmova   rdx, [rbp+410h+var_368]
0x14018774b  mov     r8, [rbp+410h+var_358]
0x140187752  mov     rcx, rax
0x140187755  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x14018775a  mov     rcx, rax
0x14018775d  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x140187762  mov     rax, [rbp+410h+var_348]
0x140187769  test    al, al
0x14018776b  jz      short loc_140187779
0x14018776d  lea     rcx, [rbp+410h+var_368]
0x140187774  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140187779  lea     r9, aParentbranchbu; "ParentBranchBuild"
0x140187780  mov     rdx, [rbp+410h+var_370]
0x140187787  lea     rcx, [rbp+410h+var_368]
0x14018778e  call    ?try_get_value_string@reg@wil@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x140187793  nop
0x140187794  mov     rax, [rbp+410h+var_348]
0x14018779b  test    al, al
0x14018779d  jz      short loc_1401877E7
0x14018779f  lea     rdx, aBuild; "Build="
0x1401877a6  lea     rcx, [rbp+410h+var_330]
0x1401877ad  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1401877b2  lea     rdx, [rbp+410h+var_368]
0x1401877b9  cmp     [rbp+410h+var_350], 7
0x1401877c1  cmova   rdx, [rbp+410h+var_368]
0x1401877c9  mov     r8, [rbp+410h+var_358]
0x1401877d0  mov     rcx, rax
0x1401877d3  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1401877d8  mov     rcx, rax
0x1401877db  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x1401877e0  mov     rax, [rbp+410h+var_348]
0x1401877e7  test    al, al
0x1401877e9  jz      short loc_1401877F7
0x1401877eb  lea     rcx, [rbp+410h+var_368]
0x1401877f2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1401877f7  lea     r9, aBuilder; "Builder"
0x1401877fe  mov     rdx, [rbp+410h+var_370]
0x140187805  lea     rcx, [rbp+410h+var_368]
0x14018780c  call    ?try_get_value_string@reg@wil@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x140187811  nop
0x140187812  mov     rax, [rbp+410h+var_348]
0x140187819  test    al, al
0x14018781b  jz      short loc_140187865
0x14018781d  lea     rdx, aBuilder_0; "builder="
0x140187824  lea     rcx, [rbp+410h+var_330]
0x14018782b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187830  lea     rdx, [rbp+410h+var_368]
0x140187837  cmp     [rbp+410h+var_350], 7
0x14018783f  cmova   rdx, [rbp+410h+var_368]
0x140187847  mov     r8, [rbp+410h+var_358]
0x14018784e  mov     rcx, rax
0x140187851  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x140187856  mov     rcx, rax
0x140187859  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x14018785e  mov     rax, [rbp+410h+var_348]
0x140187865  test    al, al
0x140187867  jz      short loc_140187875
0x140187869  lea     rcx, [rbp+410h+var_368]
0x140187870  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140187875  lea     r9, aTimestamp; "TimeStamp"
0x14018787c  mov     rdx, [rbp+410h+var_370]
0x140187883  lea     rcx, [rbp+410h+var_368]
0x14018788a  call    ?try_get_value_string@reg@wil@@YA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAUHKEY__@@PEB_W1@Z; wil::reg::try_get_value_string(HKEY__ *,wchar_t const *,wchar_t const *)
0x14018788f  nop
0x140187890  mov     rax, [rbp+410h+var_348]
0x140187897  test    al, al
0x140187899  jz      short loc_1401878E3
0x14018789b  lea     rdx, aBuildtimestamp; "BuildTimestamp="
0x1401878a2  lea     rcx, [rbp+410h+var_330]
0x1401878a9  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1401878ae  lea     rdx, [rbp+410h+var_368]
0x1401878b5  cmp     [rbp+410h+var_350], 7
0x1401878bd  cmova   rdx, [rbp+410h+var_368]
0x1401878c5  mov     r8, [rbp+410h+var_358]
0x1401878cc  mov     rcx, rax
0x1401878cf  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x1401878d4  mov     rcx, rax
0x1401878d7  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x1401878dc  mov     rax, [rbp+410h+var_348]
0x1401878e3  test    al, al
0x1401878e5  jz      short loc_1401878F4
0x1401878e7  lea     rcx, [rbp+410h+var_368]
0x1401878ee  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1401878f3  nop
0x1401878f4  mov     rcx, [rbp+410h+var_370]
0x1401878fb  jmp     loc_140187B51
0x140187900  mov     [rbp+410h+hkey], 0
0x14018790b  lea     rax, [rbp+410h+hkey]
0x140187912  mov     [rsp+510h+phkResult], rax; phkResult
0x140187917  mov     r9d, 20019h; samDesired
0x14018791d  xor     r8d, r8d; ulOptions
0x140187920  lea     rdx, aSystemVersions; "System\\Versions"
0x140187927  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14018792e  call    cs:__imp_RegOpenKeyExW
0x140187934  test    eax, eax
0x140187936  jnz     loc_140187B4A
0x14018793c  mov     ebx, 208h
0x140187941  mov     r8d, ebx; Size
0x140187944  xor     edx, edx; Val
0x140187946  lea     rcx, [rbp+410h+var_220]; void *
0x14018794d  call    memset
0x140187952  mov     dword ptr [rbp+410h+var_370], ebx
0x140187958  lea     rax, [rbp+410h+var_370]
0x14018795f  mov     [rsp+510h+pcbData], rax; pcbData
0x140187964  lea     rax, [rbp+410h+var_220]
0x14018796b  mov     [rsp+510h+pvData], rax; pvData
0x140187970  mov     [rsp+510h+phkResult], 0; pdwType
0x140187979  mov     r9d, 2; dwFlags
0x14018797f  lea     r8, Value; "Label"
0x140187986  xor     edx, edx; lpSubKey
0x140187988  mov     rcx, [rbp+410h+hkey]; hkey
0x14018798f  call    cs:__imp_RegGetValueW
0x140187995  test    eax, eax
0x140187997  jnz     short loc_1401879C3
0x140187999  lea     rdx, aBldbrch; "bldbrch="
0x1401879a0  lea     rcx, [rbp+410h+var_330]
0x1401879a7  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1401879ac  mov     rcx, rax
0x1401879af  lea     rdx, [rbp+410h+var_220]
0x1401879b6  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x1401879bb  mov     rcx, rax
0x1401879be  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x1401879c3  mov     r8, rbx; Size
0x1401879c6  xor     edx, edx; Val
0x1401879c8  lea     rcx, [rbp+410h+var_220]; void *
0x1401879cf  call    memset
0x1401879d4  mov     dword ptr [rbp+410h+var_370], ebx
0x1401879da  lea     rax, [rbp+410h+var_370]
0x1401879e1  mov     [rsp+510h+pcbData], rax; pcbData
0x1401879e6  lea     rax, [rbp+410h+var_220]
0x1401879ed  mov     [rsp+510h+pvData], rax; pvData
0x1401879f2  mov     [rsp+510h+phkResult], 0; pdwType
0x1401879fb  mov     r9d, 2; dwFlags
0x140187a01  lea     r8, aParentbranchbu; "ParentBranchBuild"
0x140187a08  xor     edx, edx; lpSubKey
0x140187a0a  mov     rcx, [rbp+410h+hkey]; hkey
0x140187a11  call    cs:__imp_RegGetValueW
0x140187a17  test    eax, eax
0x140187a19  jnz     short loc_140187A45
0x140187a1b  lea     rdx, aBuild; "Build="
0x140187a22  lea     rcx, [rbp+410h+var_330]
0x140187a29  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187a2e  mov     rcx, rax
0x140187a31  lea     rdx, [rbp+410h+var_220]
0x140187a38  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187a3d  mov     rcx, rax
0x140187a40  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x140187a45  mov     r8, rbx; Size
0x140187a48  xor     edx, edx; Val
0x140187a4a  lea     rcx, [rbp+410h+var_220]; void *
0x140187a51  call    memset
0x140187a56  mov     dword ptr [rbp+410h+var_370], ebx
0x140187a5c  lea     rax, [rbp+410h+var_370]
0x140187a63  mov     [rsp+510h+pcbData], rax; pcbData
0x140187a68  lea     rax, [rbp+410h+var_220]
0x140187a6f  mov     [rsp+510h+pvData], rax; pvData
0x140187a74  mov     [rsp+510h+phkResult], 0; pdwType
0x140187a7d  mov     r9d, 2; dwFlags
0x140187a83  lea     r8, aBuilder; "Builder"
0x140187a8a  xor     edx, edx; lpSubKey
0x140187a8c  mov     rcx, [rbp+410h+hkey]; hkey
0x140187a93  call    cs:__imp_RegGetValueW
0x140187a99  test    eax, eax
0x140187a9b  jnz     short loc_140187AC7
0x140187a9d  lea     rdx, aBuilder_0; "builder="
0x140187aa4  lea     rcx, [rbp+410h+var_330]
0x140187aab  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187ab0  mov     rcx, rax
0x140187ab3  lea     rdx, [rbp+410h+var_220]
0x140187aba  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187abf  mov     rcx, rax
0x140187ac2  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x140187ac7  mov     r8, rbx; Size
0x140187aca  xor     edx, edx; Val
0x140187acc  lea     rcx, [rbp+410h+var_220]; void *
0x140187ad3  call    memset
0x140187ad8  mov     dword ptr [rbp+410h+var_370], ebx
0x140187ade  lea     rax, [rbp+410h+var_370]
0x140187ae5  mov     [rsp+510h+pcbData], rax; pcbData
0x140187aea  lea     rax, [rbp+410h+var_220]
0x140187af1  mov     [rsp+510h+pvData], rax; pvData
0x140187af6  mov     [rsp+510h+phkResult], 0; pdwType
0x140187aff  mov     r9d, 2; dwFlags
0x140187b05  lea     r8, aTimestamp; "TimeStamp"
0x140187b0c  xor     edx, edx; lpSubKey
0x140187b0e  mov     rcx, [rbp+410h+hkey]; hkey
0x140187b15  call    cs:__imp_RegGetValueW
0x140187b1b  test    eax, eax
0x140187b1d  jnz     short loc_140187B4A
0x140187b1f  lea     rdx, aBuildtimestamp; "BuildTimestamp="
0x140187b26  lea     rcx, [rbp+410h+var_330]
0x140187b2d  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187b32  mov     rcx, rax
0x140187b35  lea     rdx, [rbp+410h+var_220]
0x140187b3c  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187b41  mov     rcx, rax
0x140187b44  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x140187b49  nop
0x140187b4a  mov     rcx, [rbp+410h+hkey]; hKey
0x140187b51  test    rcx, rcx
0x140187b54  jz      short loc_140187B5C
0x140187b56  call    cs:__imp_RegCloseKey
0x140187b5c  xor     edx, edx; Val
0x140187b5e  mov     r8d, 118h; Size
0x140187b64  lea     rcx, [rbp+410h+VersionInformation.dwMajorVersion]; void *
0x140187b68  call    memset
0x140187b6d  mov     [rbp+410h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x140187b74  mov     rbx, [rbp+418h]
0x140187b7b  lea     rcx, [rbp+410h+VersionInformation]; lpVersionInformation
0x140187b7f  call    cs:__imp_GetVersionExW
0x140187b85  test    eax, eax
0x140187b87  jz      loc_140187C47
0x140187b8d  lea     rdx, aOsversion_0; "OsVersion="
0x140187b94  lea     rcx, [rbp+410h+var_330]
0x140187b9b  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187ba0  mov     edx, [rbp+410h+VersionInformation.dwMajorVersion]
0x140187ba3  mov     rcx, rax
0x140187ba6  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x140187bab  mov     rcx, rax
0x140187bae  lea     rbx, asc_140416A68; "."
0x140187bb5  mov     rdx, rbx
0x140187bb8  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187bbd  mov     edx, [rbp+410h+VersionInformation.dwMinorVersion]
0x140187bc0  mov     rcx, rax
0x140187bc3  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@K@Z; std::wostream::operator<<(ulong)
0x140187bc8  mov     rcx, rax
0x140187bcb  mov     rdx, rbx
0x140187bce  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187bd3  movzx   edx, word ptr [rbp+410h+VersionInformation.dwBuildNumber]
0x140187bd7  mov     rcx, rax
0x140187bda  call    ??6?$basic_ostream@_WU?$char_traits@_W@std@@@std@@QEAAAEAV01@G@Z; std::wostream::operator<<(ushort)
0x140187bdf  mov     rcx, rax
0x140187be2  mov     rdx, rbx
0x140187be5  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x140187bea  mov     edx, [rbp+410h+VersionInformation.dwBuildNumber]
0x140187bed  shr     edx, 10h
  ... truncated ...
```
