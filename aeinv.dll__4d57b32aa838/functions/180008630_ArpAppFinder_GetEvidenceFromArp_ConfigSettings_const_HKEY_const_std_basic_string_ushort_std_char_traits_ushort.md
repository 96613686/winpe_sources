# ArpAppFinder::GetEvidenceFromArp(ConfigSettings const &,HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x180008630`
- end: `0x180008e50`
- name: `?GetEvidenceFromArp@ArpAppFinder@@SAXAEBVConfigSettings@@QEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@5@@Z`
- size: `2080`
- prototype: `LSTATUS __fastcall(__int64, HKEY, const WCHAR *, __int64, __int64)`
- caller_count: `2`
- callee_count: `34`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180037cfc`
- `0x1801037f8`

## callees

- `0x1800076b4`
- `0x180008400`
- `0x180008630`
- `0x18000a194`
- `0x18000a49c`
- `0x18000b364`
- `0x18000b7cc`
- `0x18000e458`
- `0x18001405c`
- `0x1800150ac`
- `0x1800176e0`
- `0x180017968`
- `0x180018450`
- `0x180018a60`
- `0x180018ff4`
- `0x1800197d4`
- `0x18001ea80`
- `0x1800402b4`
- `0x180040500`
- `0x1800417a8`
- `0x180041d4c`
- `0x180041dbc`
- `0x180044c44`
- `0x180044c88`
- `0x180045468`
- `0x1800493b8`
- `0x180052bfc`
- `0x180052f28`
- `0x180059920`
- `0x18005d690`
- `0x1800679f8`
- `0x1801034dc`
- `0x180125400`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800086bb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800086bb`
- `ADVAPI32!RegOpenKeyExW` at `0x1800086f8`
- `ADVAPI32!RegOpenKeyExW` at `0x1800086f8`
- `ADVAPI32!RegEnumKeyExW` at `0x1800087f0`
- `ADVAPI32!RegEnumKeyExW` at `0x1800087f0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000875b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000875b`
- `ADVAPI32!RegCloseKey` at `0x180008e23`
- `ADVAPI32!RegCloseKey` at `0x180008e23`

## string_xrefs

- `0x1800086b4`: `Software\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`
- `0x18000877c`: `base\appcompat\inventory\software\inv2\lib\arpappfinder.cpp`
- `0x1800088b1`: `base\appcompat\inventory\software\inv2\lib\arpappfinder.cpp`
- `0x1800088c6`: `base\appcompat\inventory\software\inv2\lib\arpappfinder.cpp`

## pseudocode

```c
LSTATUS __fastcall ArpAppFinder::GetEvidenceFromArp(__int64 a1, HKEY a2, const WCHAR *a3, __int64 a4, __int64 a5)
{
  const WCHAR *v5; // rsi
  HKEY v6; // r15
  const WCHAR *v7; // rcx
  REGSAM v8; // ebx
  const WCHAR *v9; // rdx
  LSTATUS result; // eax
  int v11; // eax
  DWORD i; // r14d
  WCHAR *v13; // r8
  LSTATUS v14; // eax
  _QWORD *v15; // rbx
  __m128i si128; // xmm6
  _QWORD *v17; // rdx
  __int64 v18; // r8
  void *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int128 *v22; // rcx
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rax
  void *v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // r14
  const struct wil::FailureInfo *v30; // r9
  int phkResult; // [rsp+20h] [rbp-1AA8h]
  int v32; // [rsp+60h] [rbp-1A68h]
  DWORD cchName; // [rsp+64h] [rbp-1A64h] BYREF
  DWORD cSubKeys; // [rsp+68h] [rbp-1A60h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+6Ch] [rbp-1A5Ch] BYREF
  _QWORD *v36; // [rsp+70h] [rbp-1A58h]
  HKEY hKey; // [rsp+78h] [rbp-1A50h] BYREF
  HKEY v38; // [rsp+80h] [rbp-1A48h]
  const WCHAR *v39; // [rsp+88h] [rbp-1A40h]
  __int64 v40; // [rsp+90h] [rbp-1A38h]
  __int64 v41; // [rsp+A0h] [rbp-1A28h]
  __int64 v42; // [rsp+A8h] [rbp-1A20h]
  _QWORD v43[4]; // [rsp+B0h] [rbp-1A18h] BYREF
  void **v44; // [rsp+D0h] [rbp-19F8h] BYREF
  __int64 v45; // [rsp+D8h] [rbp-19F0h] BYREF
  _BYTE v46[40]; // [rsp+F0h] [rbp-19D8h] BYREF
  __int128 v47; // [rsp+118h] [rbp-19B0h]
  __int128 v48; // [rsp+128h] [rbp-19A0h]
  __int128 v49; // [rsp+138h] [rbp-1990h]
  __int128 v50; // [rsp+148h] [rbp-1980h]
  __int128 v51; // [rsp+158h] [rbp-1970h]
  __int128 v52; // [rsp+168h] [rbp-1960h]
  __int128 v53; // [rsp+178h] [rbp-1950h]
  __int128 v54; // [rsp+188h] [rbp-1940h]
  __int64 v55; // [rsp+198h] [rbp-1930h]
  LPWSTR lpName[2]; // [rsp+1C0h] [rbp-1908h] BYREF
  __m128i v57; // [rsp+1D0h] [rbp-18F8h]
  __int128 v58; // [rsp+1E0h] [rbp-18E8h] BYREF
  __int64 v59; // [rsp+1F0h] [rbp-18D8h]
  __int64 v60; // [rsp+1F8h] [rbp-18D0h]
  __int128 v61; // [rsp+200h] [rbp-18C8h] BYREF
  __m128i v62; // [rsp+210h] [rbp-18B8h]
  _BYTE Src[32]; // [rsp+220h] [rbp-18A8h] BYREF
  _BYTE v64[32]; // [rsp+240h] [rbp-1888h] BYREF
  _BYTE v65[16]; // [rsp+260h] [rbp-1868h] BYREF
  __int64 v66; // [rsp+270h] [rbp-1858h]
  __int128 v67; // [rsp+280h] [rbp-1848h] BYREF
  __int128 v68; // [rsp+290h] [rbp-1838h]
  __int128 v69; // [rsp+2A0h] [rbp-1828h]
  __int128 v70; // [rsp+2B0h] [rbp-1818h]
  __int128 v71; // [rsp+2C0h] [rbp-1808h]
  __int128 v72; // [rsp+2D0h] [rbp-17F8h]
  __int128 v73; // [rsp+2E0h] [rbp-17E8h]
  __int128 v74; // [rsp+2F0h] [rbp-17D8h]
  __int128 v75; // [rsp+300h] [rbp-17C8h]
  __int64 v76; // [rsp+310h] [rbp-17B8h]
  char v77[32]; // [rsp+670h] [rbp-1458h] BYREF
  _BYTE v78[16]; // [rsp+690h] [rbp-1438h] BYREF
  _QWORD v79[124]; // [rsp+6A0h] [rbp-1428h] BYREF
  _BYTE v80[4096]; // [rsp+A80h] [rbp-1048h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1AC8h] [rbp+0h]

  v43[3] = -2;
  v5 = a3;
  v6 = a2;
  v40 = a1;
  v38 = a2;
  v39 = a3;
  v41 = a4;
  v42 = a5;
  v32 = 0;
  v7 = a3;
  if ( *((_QWORD *)a3 + 3) > 7u )
    v7 = *(const WCHAR **)a3;
  v8 = (unsigned int)_o__wcsicmp(v7, L"Software\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall") != 0
     ? 131353
     : 131097;
  hKey = 0;
  if ( *((_QWORD *)v5 + 3) <= 7u )
    v9 = v5;
  else
    v9 = *(const WCHAR **)v5;
  result = RegOpenKeyExW(v6, v9, 0, v8, &hKey);
  if ( !result )
  {
    std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(v43);
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v11 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v11 > 0 )
      v11 = (unsigned __int16)v11 | 0x80070000;
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xCA,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\arpappfinder.cpp",
        (const char *)(unsigned int)v11,
        phkResult);
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = cbMaxSubKeyLen + 1;
      std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
      v13 = (WCHAR *)lpName;
      if ( v57.m128i_i64[1] > 7uLL )
        v13 = lpName[0];
      v14 = RegEnumKeyExW(hKey, i, v13, &cchName, 0, 0, 0, 0);
      if ( v14 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xD9,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\arpappfinder.cpp",
          (const char *)(unsigned int)v14,
          phkResult);
      std::wstring::resize(lpName, cchName);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(v43, lpName);
      std::wstring::~wstring(lpName);
    }
    cchName = v8;
    Application::Application((Application *)v78);
    if ( *(_BYTE *)(v40 + 219) )
      Application::ForceFullAppScan = 1;
    v15 = (_QWORD *)v43[0];
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    while ( 1 )
    {
      v36 = v15;
      if ( v15 == (_QWORD *)v43[1] )
      {
        Application::~Application((Application *)v78);
        result = std::vector<std::wstring>::_Tidy(v43);
        break;
      }
      Utility::KickWatchdogTimer();
      if ( Utility::IsCrmWindowClosed )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xF0,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\arpappfinder.cpp",
          (const char *)0x80004004LL,
          phkResult);
      Application::Reset((Application *)v78);
      if ( v15[3] <= 7u )
        v17 = v15;
      else
        v17 = (_QWORD *)*v15;
      v58 = 0;
      v59 = 0;
      v60 = 0;
      v18 = -1;
      do
        ++v18;
      while ( *((_WORD *)v17 + v18) );
      try
      {
        std::wstring::_Construct<1,unsigned short const *>(&v58);
        *(_OWORD *)lpName = 0;
        v57 = 0;
        std::wstring::_Construct_empty(lpName);
        if ( v6 == HKEY_LOCAL_MACHINE )
        {
          v19 = (void *)std::operator+<unsigned short>(v64, L"HKEY_LOCAL_MACHINE\\", v5);
          v20 = std::wstring::_Append<unsigned short>(v19);
          std::wstring::wstring(Src, v20);
          v21 = std::wstring::_Append<unsigned short>(Src);
          std::wstring::wstring(&v61, v21);
          v32 |= 6u;
          std::wstring::_Tidy_deallocate(lpName);
          *(_OWORD *)lpName = v61;
          v57 = v62;
          v62 = si128;
          LOWORD(v61) = 0;
          std::wstring::~wstring(&v61);
          std::wstring::~wstring(Src);
          v22 = (__int128 *)v64;
        }
        else
        {
          if ( v6 != HKEY_USERS )
          {
            AslLogCallPrintf(
              1,
              (unsigned int)"ArpAppFinder::GetEvidenceFromArp",
              260,
              (unsigned int)"Unsupported rootKey");
            std::wstring::~wstring(lpName);
            std::wstring::~wstring(&v58);
            goto LABEL_49;
          }
          v23 = std::operator+<unsigned short>(&v61, L"HKEY_USERS\\", v5);
          v24 = std::operator+<unsigned short>(Src, v23, L"\\");
          v25 = std::operator+<unsigned short>(v64, v24, &v58);
          std::wstring::operator=(lpName, v25);
          std::wstring::~wstring(v64);
          std::wstring::~wstring(Src);
          v22 = &v61;
        }
        std::wstring::~wstring(v22);
        MsiApplication::GetMsiProductCode(v65, lpName);
        if ( v66 )
        {
          try
          {
            v26 = (void *)std::operator+<unsigned short>(v64, v5, L"\\");
            v27 = std::wstring::_Append<unsigned short>(v26);
            std::wstring::wstring(Src, v27);
            v32 |= 0x10u;
            Application::Application((Application *)&v67);
            *(_QWORD *)&v67 = &MsiApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
            *((_QWORD *)&v67 + 1) = &MsiApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
            *(_QWORD *)&v68 = &MsiApplication::`vftable';
            std::wstring::wstring(v77);
            MsiApplication::GetMsiApplication((Application *)&v67, (__int64)Src, v41);
            Application::operator=(v78, &v67);
            MsiApplication::~MsiApplication((MsiApplication *)&v67);
            std::wstring::~wstring(Src);
            std::wstring::~wstring(v64);
          }
          catch ( ... )
          {
            Application::Reset((Application *)v78);
            v15 = v36;
            si128 = _mm_load_si128((const __m128i *)&_xmm);
            v6 = v38;
            v5 = v39;
          }
        }
        if ( !*(_QWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v79[0] + 16LL))(v79) + 16) )
        {
          v28 = ArpApplication::ArpApplication(
                  (unsigned int)&v67,
                  v40,
                  (_DWORD)v6,
                  (unsigned int)&v58,
                  (__int64)v5,
                  v41,
                  cchName);
          Application::operator=(v78, v28);
          *(_QWORD *)&v67 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
          *((_QWORD *)&v67 + 1) = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
          *(_QWORD *)&v68 = &SteamApplication::`vftable';
          Application::~Application((Application *)&v67);
        }
        if ( v79[12] )
        {
          v29 = v42;
          if ( *(_QWORD *)(v42 + 8) == *(_QWORD *)(v42 + 16) )
          {
            std::vector<Application>::_Emplace_reallocate<Application const &>(v42, *(_QWORD *)(v42 + 8), v78);
          }
          else
          {
            Application::Application(*(Application **)(v42 + 8), (const struct Application *)v78);
            *(_QWORD *)(v29 + 8) += 1008LL;
          }
        }
        std::wstring::~wstring(v65);
        std::wstring::~wstring(lpName);
        std::wstring::~wstring(&v58);
      }
      catch ( wil::ResultException v46 )
      {
        memset_0(v80, 0, sizeof(v80));
        v67 = *(_OWORD *)&v46[24];
        v68 = v47;
        v69 = v48;
        v70 = v49;
        v71 = v50;
        v72 = v51;
        v73 = v52;
        v74 = v53;
        v75 = v54;
        v76 = v55;
        wil::GetFailureLogString((wil *)v80, (unsigned __int16 *)0x800, (unsigned __int64)&v67, v30);
        AslLogCallPrintf(1, (unsigned int)"ArpAppFinder::GetEvidenceFromArp", 304, (unsigned int)"%ws");
        wil::ResultException::~ResultException((wil::ResultException *)v46);
        goto LABEL_42;
      }
      catch ( std::exception v44 )
      {
        GetLastError();
        AslLogCallPrintf(1, (unsigned int)"ArpAppFinder::GetEvidenceFromArp", 309, (unsigned int)"Exception: 0x%08x %s");
        v44 = &std::exception::`vftable';
        o___std_exception_destroy_0(&v45);
        goto LABEL_42;
      }
      catch ( ... )
      {
        AslLogCallPrintf(1, (unsigned int)"ArpAppFinder::GetEvidenceFromArp", 314, (unsigned int)"Exception: [0x%08x]");
LABEL_42:
        v15 = v36;
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        v6 = v38;
        v5 = v39;
      }
LABEL_49:
      v15 += 4;
    }
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x180008630  push    rbx
0x180008632  push    rsi
0x180008633  push    rdi
0x180008634  push    r14
0x180008636  push    r15
0x180008638  mov     eax, 1AA0h
0x18000863d  call    _alloca_probe
0x180008642  sub     rsp, rax
0x180008645  mov     [rsp+1AC8h+var_1A00], 0FFFFFFFFFFFFFFFEh
0x180008651  movaps  [rsp+1AC8h+var_38], xmm6
0x180008659  mov     rax, cs:__security_cookie
0x180008660  xor     rax, rsp
0x180008663  mov     [rsp+1AC8h+var_48], rax
0x18000866b  mov     rsi, r8
0x18000866e  mov     r15, rdx
0x180008671  mov     [rsp+1AC8h+var_1A38], rcx
0x180008679  mov     [rsp+1AC8h+var_1A48], rdx
0x180008681  mov     [rsp+1AC8h+var_1A40], r8
0x180008689  mov     [rsp+1AC8h+var_1A28], r9
0x180008691  mov     rax, [rsp+1AC8h+arg_20]
0x180008699  mov     [rsp+1AC8h+var_1A20], rax
0x1800086a1  xor     edi, edi
0x1800086a3  mov     [rsp+1AC8h+var_1A68], edi
0x1800086a7  mov     rcx, r8
0x1800086aa  cmp     qword ptr [r8+18h], 7
0x1800086af  jbe     short loc_1800086B4
0x1800086b1  mov     rcx, [r8]
0x1800086b4  lea     rdx, aSoftwareWow643_0; "Software\\Wow6432Node\\Microsoft\\Windo"...
0x1800086bb  call    cs:__imp__o__wcsicmp
0x1800086c1  neg     eax
0x1800086c3  sbb     ebx, ebx
0x1800086c5  and     ebx, 100h
0x1800086cb  add     ebx, 20019h
0x1800086d1  mov     [rsp+1AC8h+hKey], rdi
0x1800086d6  cmp     qword ptr [rsi+18h], 7
0x1800086db  jbe     short loc_1800086E2
0x1800086dd  mov     rdx, [rsi]
0x1800086e0  jmp     short loc_1800086E5
0x1800086e2  mov     rdx, rsi; lpSubKey
0x1800086e5  lea     rax, [rsp+1AC8h+hKey]
0x1800086ea  mov     [rsp+1AC8h+phkResult], rax; phkResult
0x1800086ef  mov     r9d, ebx; samDesired
0x1800086f2  xor     r8d, r8d; ulOptions
0x1800086f5  mov     rcx, r15; hKey
0x1800086f8  call    cs:__imp_RegOpenKeyExW
0x1800086fe  test    eax, eax
0x180008700  jnz     loc_180008E19
0x180008706  lea     rcx, [rsp+1AC8h+var_1A18]
0x18000870e  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x180008713  nop
0x180008714  mov     [rsp+1AC8h+cSubKeys], edi
0x180008718  mov     [rsp+1AC8h+cbMaxSubKeyLen], edi
0x18000871c  mov     [rsp+1AC8h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x180008721  mov     [rsp+1AC8h+lpcbSecurityDescriptor], rdi; lpcbSecurityDescriptor
0x180008726  mov     [rsp+1AC8h+lpcbMaxValueLen], rdi; lpcbMaxValueLen
0x18000872b  mov     [rsp+1AC8h+lpcbMaxValueNameLen], rdi; lpcbMaxValueNameLen
0x180008730  mov     [rsp+1AC8h+lpcValues], rdi; lpcValues
0x180008735  mov     [rsp+1AC8h+lpcbMaxClassLen], rdi; lpcbMaxClassLen
0x18000873a  lea     rax, [rsp+1AC8h+cbMaxSubKeyLen]
0x18000873f  mov     [rsp+1AC8h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180008744  lea     rax, [rsp+1AC8h+cSubKeys]
0x180008749  mov     [rsp+1AC8h+phkResult], rax; int
0x18000874e  xor     r9d, r9d; lpReserved
0x180008751  xor     r8d, r8d; lpcchClass
0x180008754  xor     edx, edx; lpClass
0x180008756  mov     rcx, [rsp+1AC8h+hKey]; hKey
0x18000875b  call    cs:__imp_RegQueryInfoKeyW
0x180008761  test    eax, eax
0x180008763  jle     short loc_18000876D
0x180008765  movzx   eax, ax
0x180008768  or      eax, 80070000h
0x18000876d  mov     rcx, [rsp+1AC8h]; this
0x180008775  test    eax, eax
0x180008777  jns     short loc_18000878E
0x180008779  mov     r9d, eax; char *
0x18000877c  lea     r8, aBaseAppcompatI; "base\\appcompat\\inventory\\software\\i"...
0x180008783  mov     edx, 0CAh; void *
0x180008788  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000878e  mov     r14d, edi
0x180008791  cmp     [rsp+1AC8h+cSubKeys], edi
0x180008795  jbe     loc_180008848
0x18000879b  mov     eax, [rsp+1AC8h+cbMaxSubKeyLen]
0x18000879f  inc     eax
0x1800087a1  mov     [rsp+1AC8h+cchName], eax
0x1800087a5  mov     edx, eax
0x1800087a7  lea     rcx, [rsp+1AC8h+lpName]
0x1800087af  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x1800087b4  nop
0x1800087b5  lea     r8, [rsp+1AC8h+lpName]
0x1800087bd  cmp     [rsp+1AC8h+var_18F0], 7
0x1800087c6  cmova   r8, [rsp+1AC8h+lpName]; lpName
0x1800087cf  mov     [rsp+1AC8h+lpcValues], rdi; lpftLastWriteTime
0x1800087d4  mov     [rsp+1AC8h+lpcbMaxClassLen], rdi; lpcchClass
0x1800087d9  mov     [rsp+1AC8h+lpcbMaxSubKeyLen], rdi; lpClass
0x1800087de  mov     [rsp+1AC8h+phkResult], rdi; int
0x1800087e3  lea     r9, [rsp+1AC8h+cchName]; lpcchName
0x1800087e8  mov     edx, r14d; dwIndex
0x1800087eb  mov     rcx, [rsp+1AC8h+hKey]; hKey
0x1800087f0  call    cs:__imp_RegEnumKeyExW
0x1800087f6  mov     rcx, [rsp+1AC8h]; this
0x1800087fe  test    eax, eax
0x180008800  js      loc_1800088C3
0x180008806  mov     edx, [rsp+1AC8h+cchName]
0x18000880a  lea     rcx, [rsp+1AC8h+lpName]
0x180008812  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180008817  lea     rdx, [rsp+1AC8h+lpName]
0x18000881f  lea     rcx, [rsp+1AC8h+var_1A18]
0x180008827  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x18000882c  nop
0x18000882d  lea     rcx, [rsp+1AC8h+lpName]
0x180008835  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000883a  inc     r14d
0x18000883d  cmp     r14d, [rsp+1AC8h+cSubKeys]
0x180008842  jb      loc_18000879B
0x180008848  mov     [rsp+1AC8h+cchName], ebx
0x18000884c  lea     rcx, [rsp+1AC8h+var_1438]; this
0x180008854  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180008859  nop
0x18000885a  mov     rax, [rsp+1AC8h+var_1A38]
0x180008862  cmp     [rax+0DBh], dil
0x180008869  jz      short loc_180008872
0x18000886b  mov     cs:?ForceFullAppScan@Application@@1_NA, 1; bool Application::ForceFullAppScan
0x180008872  mov     rbx, [rsp+1AC8h+var_1A18]
0x18000887a  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180008882  mov     [rsp+1AC8h+var_1A58], rbx
0x180008887  cmp     rbx, [rsp+1AC8h+var_1A10]
0x18000888f  jz      loc_180008DFD
0x180008895  call    ?KickWatchdogTimer@Utility@@SA_NXZ; Utility::KickWatchdogTimer(void)
0x18000889a  cmp     cs:?IsCrmWindowClosed@Utility@@2_NA, dil; bool Utility::IsCrmWindowClosed
0x1800088a1  jz      short loc_1800088D8
0x1800088a3  mov     rcx, [rsp+1AC8h]; this
0x1800088ab  mov     r9d, 80004004h; char *
0x1800088b1  lea     r8, aBaseAppcompatI; "base\\appcompat\\inventory\\software\\i"...
0x1800088b8  mov     edx, 0F0h; void *
0x1800088bd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800088c3  mov     r9d, eax; char *
0x1800088c6  lea     r8, aBaseAppcompatI; "base\\appcompat\\inventory\\software\\i"...
0x1800088cd  mov     edx, 0D9h; void *
0x1800088d2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800088d8  lea     rcx, [rsp+1AC8h+var_1438]; this
0x1800088e0  call    ?Reset@Application@@UEAAXXZ; Application::Reset(void)
0x1800088e5  nop
0x1800088e6  cmp     qword ptr [rbx+18h], 7
0x1800088eb  jbe     short loc_1800088F2
0x1800088ed  mov     rdx, [rbx]
0x1800088f0  jmp     short loc_1800088F5
0x1800088f2  mov     rdx, rbx
0x1800088f5  xorps   xmm0, xmm0
0x1800088f8  movups  [rsp+1AC8h+var_18E8], xmm0
0x180008900  mov     [rsp+1AC8h+var_18D8], rdi
0x180008908  mov     [rsp+1AC8h+var_18D0], rdi
0x180008910  or      r8, 0FFFFFFFFFFFFFFFFh
0x180008914  inc     r8
0x180008917  cmp     [rdx+r8*2], di
0x18000891c  jnz     short loc_180008914
0x18000891e  lea     rcx, [rsp+1AC8h+var_18E8]
0x180008926  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000892b  nop
0x18000892c  xorps   xmm0, xmm0
0x18000892f  movups  xmmword ptr [rsp+1AC8h+lpName], xmm0
0x180008937  xorps   xmm1, xmm1
0x18000893a  movdqu  xmmword ptr [rsp+1D0h], xmm1
0x180008943  lea     rcx, [rsp+1AC8h+lpName]
0x18000894b  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x180008950  nop
0x180008951  cmp     r15, 0FFFFFFFF80000002h
0x180008958  jnz     loc_180008A58
0x18000895e  mov     r8, rsi
0x180008961  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\"
0x180008968  lea     rcx, [rsp+1AC8h+var_1888]
0x180008970  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180008975  nop
0x180008976  mov     r8d, 1
0x18000897c  lea     rdx, SubBlock; "\\"
0x180008983  mov     rcx, rax; Src
0x180008986  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18000898b  mov     rdx, rax
0x18000898e  lea     rcx, [rsp+1AC8h+Src]
0x180008996  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18000899b  mov     r14d, [rsp+1AC8h+var_1A68]
0x1800089a0  or      r14d, 2
0x1800089a4  mov     [rsp+1AC8h+var_1A68], r14d
0x1800089a9  lea     rdx, [rsp+1AC8h+var_18E8]
0x1800089b1  cmp     [rsp+1AC8h+var_18D0], 7
0x1800089ba  cmova   rdx, qword ptr [rsp+1AC8h+var_18E8]
0x1800089c3  mov     r8, [rsp+1AC8h+var_18D8]
0x1800089cb  lea     rcx, [rsp+1AC8h+Src]; Src
0x1800089d3  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800089d8  mov     rdx, rax
0x1800089db  lea     rcx, [rsp+1AC8h+var_18C8]
0x1800089e3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1800089e8  or      r14d, 4
0x1800089ec  mov     [rsp+1AC8h+var_1A68], r14d
0x1800089f1  lea     rcx, [rsp+1AC8h+lpName]
0x1800089f9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800089fe  movups  xmm0, [rsp+1AC8h+var_18C8]
0x180008a06  movups  xmmword ptr [rsp+1AC8h+lpName], xmm0
0x180008a0e  movups  xmm1, [rsp+1AC8h+var_18B8]
0x180008a16  movups  xmmword ptr [rsp+1D0h], xmm1
0x180008a1e  movdqu  [rsp+1AC8h+var_18B8], xmm6
0x180008a27  mov     word ptr [rsp+1AC8h+var_18C8], di
0x180008a2f  lea     rcx, [rsp+1AC8h+var_18C8]
0x180008a37  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a3c  nop
0x180008a3d  lea     rcx, [rsp+1AC8h+Src]
0x180008a45  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008a4a  nop
0x180008a4b  lea     rcx, [rsp+1AC8h+var_1888]
0x180008a53  jmp     loc_180008AE1
0x180008a58  cmp     r15, 0FFFFFFFF80000003h
0x180008a5f  jnz     loc_180008D94
0x180008a65  mov     r8, rsi
0x180008a68  lea     rdx, aHkeyUsers_0; "HKEY_USERS\\"
0x180008a6f  lea     rcx, [rsp+1AC8h+var_18C8]
0x180008a77  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@QEBGAEBV10@@Z; std::operator+<ushort>(ushort const * const,std::wstring const &)
0x180008a7c  nop
0x180008a7d  lea     r8, SubBlock; "\\"
0x180008a84  mov     rdx, rax
0x180008a87  lea     rcx, [rsp+1AC8h+Src]
0x180008a8f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180008a94  nop
0x180008a95  lea     r8, [rsp+1AC8h+var_18E8]
0x180008a9d  mov     rdx, rax
0x180008aa0  lea     rcx, [rsp+1AC8h+var_1888]
0x180008aa8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180008aad  mov     rdx, rax
0x180008ab0  lea     rcx, [rsp+1AC8h+lpName]
0x180008ab8  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180008abd  lea     rcx, [rsp+1AC8h+var_1888]
0x180008ac5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008aca  nop
0x180008acb  lea     rcx, [rsp+1AC8h+Src]
0x180008ad3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008ad8  nop
0x180008ad9  lea     rcx, [rsp+1AC8h+var_18C8]
0x180008ae1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008ae6  lea     rdx, [rsp+1AC8h+lpName]
0x180008aee  lea     rcx, [rsp+1AC8h+var_1868]
0x180008af6  call    ?GetMsiProductCode@MsiApplication@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; MsiApplication::GetMsiProductCode(std::wstring const &)
0x180008afb  nop
0x180008afc  cmp     [rsp+1AC8h+var_1858], rdi
0x180008b04  jz      loc_180008C46
0x180008b0a  lea     r8, SubBlock; "\\"
0x180008b11  mov     rdx, rsi
0x180008b14  lea     rcx, [rsp+1AC8h+var_1888]
0x180008b1c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180008b21  nop
0x180008b22  lea     rdx, [rsp+1AC8h+var_18E8]
0x180008b2a  cmp     [rsp+1AC8h+var_18D0], 7
0x180008b33  cmova   rdx, qword ptr [rsp+1AC8h+var_18E8]
0x180008b3c  mov     r8, [rsp+1AC8h+var_18D8]
0x180008b44  mov     rcx, rax; Src
0x180008b47  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180008b4c  mov     rdx, rax
0x180008b4f  lea     rcx, [rsp+1AC8h+Src]
0x180008b57  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180008b5c  or      [rsp+1AC8h+var_1A68], 10h
0x180008b61  lea     rcx, [rsp+1AC8h+var_1848]; this
0x180008b69  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180008b6e  nop
0x180008b6f  lea     rax, ??_7MsiApplication@@6BIAmiInventoryTelemetryItem@@@; const MsiApplication::`vftable'{for `IAmiInventoryTelemetryItem'}
0x180008b76  mov     [rsp+1AC8h+var_1848], rax
0x180008b7e  lea     rax, ??_7MsiApplication@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const MsiApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x180008b85  mov     [rsp+1AC8h+var_1840], rax
0x180008b8d  lea     rax, ??_7MsiApplication@@6B@; const MsiApplication::`vftable'
0x180008b94  mov     qword ptr [rsp+1AC8h+var_1838], rax
0x180008b9c  lea     rcx, [rsp+1AC8h+var_1458]
0x180008ba4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180008ba9  nop
0x180008baa  mov     rax, [rsp+1AC8h+var_1A28]
0x180008bb2  mov     [rsp+1AC8h+lpcbMaxSubKeyLen], rax; __int64
0x180008bb7  lea     rax, [rsp+1AC8h+Src]
0x180008bbf  mov     [rsp+1AC8h+phkResult], rax; __int64
0x180008bc4  mov     r9, r15
0x180008bc7  lea     r8, [rsp+1AC8h+var_1868]
0x180008bcf  mov     rdx, [rsp+1AC8h+var_1A38]
0x180008bd7  lea     rcx, [rsp+1AC8h+var_1848]; this
0x180008bdf  call    ?GetMsiApplication@MsiApplication@@QEAAXAEBVConfigSettings@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@11@Z; MsiApplication::GetMsiApplication(ConfigSettings const &,std::wstring const &,HKEY__ * const,std::wstring const &,std::wstring const &)
0x180008be4  nop
0x180008be5  lea     rdx, [rsp+1AC8h+var_1848]
0x180008bed  lea     rcx, [rsp+1AC8h+var_1438]
0x180008bf5  call    ??4Application@@QEAAAEAV0@AEBV0@@Z; Application::operator=(Application const &)
0x180008bfa  nop
0x180008bfb  lea     rcx, [rsp+1AC8h+var_1848]; this
0x180008c03  call    ??1MsiApplication@@UEAA@XZ; MsiApplication::~MsiApplication(void)
0x180008c08  nop
0x180008c09  lea     rcx, [rsp+1AC8h+Src]
0x180008c11  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008c16  nop
0x180008c17  lea     rcx, [rsp+1AC8h+var_1888]
0x180008c1f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008c24  nop
0x180008c25  jmp     short loc_180008C46
0x180008c27  xor     edi, edi
0x180008c29  mov     rbx, [rsp+1AC8h+var_1A58]
0x180008c2e  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180008c36  mov     r15, [rsp+1AC8h+var_1A48]
0x180008c3e  mov     rsi, [rsp+1AC8h+var_1A40]
0x180008c46  mov     rax, [rsp+1AC8h+var_1428]
0x180008c4e  lea     rcx, [rsp+1AC8h+var_1428]
  ... truncated ...
```
