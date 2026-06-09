# ApplicationKbFinder::GetEvidenceFromArp(ConfigSettings const &,HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::vector<ApplicationKb,std::allocator<ApplicationKb>> &)

- ea: `0x18005241c`
- end: `0x180052bf3`
- name: `?GetEvidenceFromArp@ApplicationKbFinder@@SAXAEBVConfigSettings@@QEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@VApplicationKb@@V?$allocator@VApplicationKb@@@std@@@5@@Z`
- size: `2007`
- prototype: `__int64 __fastcall(struct ConfigSettings *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180111bbc`

## callees

- `0x18000b7cc`
- `0x1800118d0`
- `0x1800150ac`
- `0x180017724`
- `0x180018450`
- `0x180018a60`
- `0x1800197d4`
- `0x18001d350`
- `0x18001e0d0`
- `0x18001ea80`
- `0x18002bff4`
- `0x180030c70`
- `0x180030ff4`
- `0x1800404c4`
- `0x1800417a8`
- `0x180044c88`
- `0x180045480`
- `0x180050030`
- `0x18005241c`
- `0x180052bfc`
- `0x180059920`
- `0x1800679f8`
- `0x1801034dc`
- `0x18011188c`
- `0x1801149bc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180052490`
- `ADVAPI32!RegOpenKeyExW` at `0x180052629`
- `ADVAPI32!RegOpenKeyExW` at `0x180052490`
- `ADVAPI32!RegOpenKeyExW` at `0x180052629`
- `ADVAPI32!RegEnumKeyExW` at `0x180052569`
- `ADVAPI32!RegEnumKeyExW` at `0x1800527c0`
- `ADVAPI32!RegEnumKeyExW` at `0x180052569`
- `ADVAPI32!RegEnumKeyExW` at `0x1800527c0`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800524e6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180052680`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800524e6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x180052680`

## string_xrefs

- `0x18005291e`: `Installed`
- `0x180052506`: `base\appcompat\inventory\software\inv2\lib\applicationkbfinder.cpp`
- `0x180052bb7`: `base\appcompat\inventory\software\inv2\lib\applicationkbfinder.cpp`
- `0x180052bcc`: `base\appcompat\inventory\software\inv2\lib\applicationkbfinder.cpp`
- `0x180052be1`: `base\appcompat\inventory\software\inv2\lib\applicationkbfinder.cpp`
- `0x1800526ed`: `\InstallProperties`
- `0x18005283d`: `Patch ID path: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall ApplicationKbFinder::GetEvidenceFromArp(
        struct ConfigSettings *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  const WCHAR *v7; // rdx
  int v8; // eax
  DWORD i; // esi
  WCHAR *v10; // r8
  LSTATUS v11; // eax
  const WCHAR *v12; // rdx
  int v13; // eax
  unsigned int v14; // r9d
  const unsigned __int16 *v15; // r8
  ArpApplication *v16; // rax
  DWORD j; // edi
  WCHAR *v18; // r8
  LSTATUS v19; // eax
  int RegValueDword; // ebx
  __int64 RegValueString; // rax
  __int64 v22; // rax
  void **v23; // rdx
  int phkResult; // [rsp+28h] [rbp-E0h]
  int phkResulta; // [rsp+28h] [rbp-E0h]
  int phkResultb; // [rsp+28h] [rbp-E0h]
  int phkResultc; // [rsp+28h] [rbp-E0h]
  DWORD cchName; // [rsp+68h] [rbp-A0h] BYREF
  DWORD v30; // [rsp+6Ch] [rbp-9Ch] BYREF
  DWORD cSubKeys; // [rsp+70h] [rbp-98h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+74h] [rbp-94h] BYREF
  DWORD lpcbMaxSubKeyLen[2]; // [rsp+78h] [rbp-90h] BYREF
  HKEY v34; // [rsp+80h] [rbp-88h] BYREF
  HKEY hKey[2]; // [rsp+88h] [rbp-80h] BYREF
  WCHAR v36[12]; // [rsp+98h] [rbp-70h] BYREF
  LPWSTR v37[4]; // [rsp+B8h] [rbp-50h] BYREF
  LPWSTR Src[2]; // [rsp+D8h] [rbp-30h] BYREF
  LPWSTR lpName[4]; // [rsp+F8h] [rbp-10h] BYREF
  WCHAR v40[16]; // [rsp+118h] [rbp+10h] BYREF
  unsigned __int16 *v41[4]; // [rsp+138h] [rbp+30h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+158h] [rbp+50h] BYREF
  _BYTE v43[32]; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v44[32]; // [rsp+198h] [rbp+90h] BYREF
  _BYTE v45[32]; // [rsp+1B8h] [rbp+B0h] BYREF
  void **v46; // [rsp+1D8h] [rbp+D0h] BYREF
  _BYTE v47[32]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v48[32]; // [rsp+200h] [rbp+F8h] BYREF
  _BYTE v49[32]; // [rsp+220h] [rbp+118h] BYREF
  _BYTE v50[32]; // [rsp+240h] [rbp+138h] BYREF
  _BYTE v51[32]; // [rsp+260h] [rbp+158h] BYREF
  _BYTE v52[40]; // [rsp+280h] [rbp+178h] BYREF
  void **v53; // [rsp+2A8h] [rbp+1A0h] BYREF
  _QWORD v54[4]; // [rsp+2B0h] [rbp+1A8h] BYREF
  _BYTE v55[32]; // [rsp+2D0h] [rbp+1C8h] BYREF
  _BYTE v56[32]; // [rsp+2F0h] [rbp+1E8h] BYREF
  _BYTE v57[32]; // [rsp+310h] [rbp+208h] BYREF
  _BYTE v58[32]; // [rsp+330h] [rbp+228h] BYREF
  _BYTE v59[840]; // [rsp+350h] [rbp+248h] BYREF
  _BYTE v60[56]; // [rsp+698h] [rbp+590h] BYREF
  _BYTE v61[40]; // [rsp+6D0h] [rbp+5C8h] BYREF
  _BYTE v62[32]; // [rsp+6F8h] [rbp+5F0h] BYREF
  _BYTE v63[32]; // [rsp+718h] [rbp+610h] BYREF
  _BYTE v64[848]; // [rsp+738h] [rbp+630h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+AD0h] [rbp+9C8h]

  hKey[1] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  hKey[0] = 0;
  if ( *(_QWORD *)(a3 + 24) <= 7u )
    v7 = (const WCHAR *)a3;
  else
    v7 = *(const WCHAR **)a3;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0x20019u, hKey) )
  {
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v8 = RegQueryInfoKeyW(hKey[0], 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkbfinder.cpp",
        (const char *)(unsigned int)v8,
        phkResult);
    for ( i = 0; i < cSubKeys; ++i )
    {
      cchName = cbMaxSubKeyLen + 1;
      std::wstring::wstring(lpName, cbMaxSubKeyLen + 1);
      v10 = (WCHAR *)lpName;
      if ( lpName[3] > (LPWSTR)7 )
        v10 = lpName[0];
      v11 = RegEnumKeyExW(hKey[0], i, v10, &cchName, 0, 0, 0, 0);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkbfinder.cpp",
          (const char *)(unsigned int)v11,
          phkResulta);
      std::wstring::resize(lpName, cchName);
      std::wstring::wstring(lpSubKey);
      std::wstring::wstring(Src);
      std::wstring::operator=(Src, a3);
      std::wstring::_Append<unsigned short>(Src);
      std::wstring::_Append<unsigned short>(Src);
      std::wstring::operator=(lpSubKey, Src);
      std::wstring::_Append<unsigned short>(lpSubKey);
      v34 = 0;
      v12 = (const WCHAR *)lpSubKey;
      if ( lpSubKey[3] > (LPCWSTR)7 )
        v12 = lpSubKey[0];
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, v12, 0, 0x20019u, &v34) )
      {
        v30 = 0;
        lpcbMaxSubKeyLen[0] = 0;
        v13 = RegQueryInfoKeyW(v34, 0, 0, 0, &v30, lpcbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        if ( v13 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xD4,
            (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkbfinder.cpp",
            (const char *)(unsigned int)v13,
            phkResultb);
        if ( v30 )
        {
          std::wstring::wstring(v41);
          std::wstring::_Assign<unsigned short>(v41, L"HKEY_LOCAL_MACHINE\\");
          std::wstring::_Append<unsigned short>(v41);
          std::wstring::_Append<unsigned short>(v41);
          Application::Application((Application *)v60);
          v15 = (const unsigned __int16 *)v41;
          if ( v41[3] > (unsigned __int16 *)7 )
            v15 = v41[0];
          v16 = ArpApplication::ArpApplication((ArpApplication *)&v53, a1, v15, v14);
          Application::operator=(v60, v16);
          v53 = &EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'};
          v54[0] = &AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'};
          v54[1] = &SteamApplication::`vftable';
          Application::~Application((Application *)&v53);
          for ( j = 0; j < v30; ++j )
          {
            cchName = lpcbMaxSubKeyLen[0] + 1;
            std::wstring::wstring(v37, lpcbMaxSubKeyLen[0] + 1);
            v18 = (WCHAR *)v37;
            if ( v37[3] > (LPWSTR)7 )
              v18 = v37[0];
            v19 = RegEnumKeyExW(v34, j, v18, &cchName, 0, 0, 0, 0);
            if ( v19 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0xF0,
                (unsigned int)"base\\appcompat\\inventory\\software\\inv2\\lib\\applicationkbfinder.cpp",
                (const char *)(unsigned int)v19,
                phkResultc);
            std::wstring::resize(v37, cchName);
            std::wstring::wstring(v36);
            std::wstring::operator=(v36, lpSubKey);
            std::wstring::_Append<unsigned short>(v36);
            std::wstring::_Append<unsigned short>(v36);
            AslLogCallPrintf(
              3,
              (unsigned int)"ApplicationKbFinder::GetEvidenceFromArp",
              249,
              (unsigned int)"Patch ID path: %ws");
            std::wstring::wstring(v40, L"State");
            RegValueDword = Utility::GetRegValueDword(HKEY_LOCAL_MACHINE, v36, v40, 0);
            std::wstring::~wstring(v40);
            if ( RegValueDword == 1 )
            {
              std::wstring::wstring(v43);
              std::wstring::wstring(v40, L"DisplayName");
              RegValueString = Utility::GetRegValueString((__int64)v45, HKEY_LOCAL_MACHINE, v36, v40);
              std::wstring::operator=(v43, RegValueString);
              std::wstring::~wstring(v45);
              std::wstring::~wstring(v40);
              if ( (unsigned __int8)Application::IsUpdate(v43) )
              {
                std::wstring::wstring(v44);
                std::wstring::wstring(v40, L"Installed");
                v22 = Utility::GetRegValueString((__int64)v45, HKEY_LOCAL_MACHINE, v36, v40);
                std::wstring::operator=(v44, v22);
                std::wstring::~wstring(v45);
                std::wstring::~wstring(v40);
                v46 = &ApplicationKb::`vftable';
                std::wstring::wstring(v47);
                std::wstring::wstring(v48);
                std::wstring::wstring(v49);
                std::wstring::wstring(v50);
                std::wstring::wstring(v51);
                std::wstring::wstring(v52);
                v53 = v23;
                std::wstring::wstring(v54, v61);
                std::wstring::wstring(v55, v43);
                std::wstring::wstring(v56, v62);
                std::wstring::wstring(v57, v63);
                std::wstring::wstring(v58, v64);
                std::wstring::wstring(v59, v44);
                std::wstring::operator=(v47, v54);
                std::wstring::operator=(v48, v55);
                std::wstring::operator=(v49, v56);
                std::wstring::operator=(v50, v57);
                std::wstring::operator=(v51, v58);
                std::wstring::operator=(v52, v59);
                ApplicationKb::~ApplicationKb((ApplicationKb *)&v53);
                if ( *(_QWORD *)(a4 + 8) == *(_QWORD *)(a4 + 16) )
                {
                  std::vector<ApplicationKb>::_Emplace_reallocate<ApplicationKb const &>(a4, *(_QWORD *)(a4 + 8), &v46);
                }
                else
                {
                  ApplicationKb::ApplicationKb(*(ApplicationKb **)(a4 + 8), (const struct ApplicationKb *)&v46);
                  *(_QWORD *)(a4 + 8) += 200LL;
                }
                ApplicationKb::~ApplicationKb((ApplicationKb *)&v46);
                std::wstring::~wstring(v44);
              }
              std::wstring::~wstring(v43);
              std::wstring::~wstring(v36);
            }
            else
            {
              std::wstring::~wstring(v36);
            }
            std::wstring::~wstring(v37);
          }
          Application::~Application((Application *)v60);
          std::wstring::~wstring(v41);
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v34);
      std::wstring::~wstring(Src);
      std::wstring::~wstring(lpSubKey);
      std::wstring::~wstring(lpName);
    }
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
}

```

## disassembly

```asm
0x18005241c  mov     rax, rsp
0x18005241f  push    rbp
0x180052420  push    rsi
0x180052421  push    rdi
0x180052422  push    r12
0x180052424  push    r13
0x180052426  push    r14
0x180052428  push    r15
0x18005242a  lea     rbp, [rax-9C8h]
0x180052431  sub     rsp, 0A90h
0x180052438  mov     [rbp+9C0h+var_A38], 0FFFFFFFFFFFFFFFEh
0x180052440  mov     [rax+10h], rbx
0x180052444  mov     rax, cs:__security_cookie
0x18005244b  xor     rax, rsp
0x18005244e  mov     [rbp+9C0h+var_40], rax
0x180052455  mov     r15, r9
0x180052458  mov     r14, r8
0x18005245b  mov     r12, rcx
0x18005245e  xor     r13d, r13d
0x180052461  mov     [rbp+9C0h+hKey], r13
0x180052465  cmp     qword ptr [r8+18h], 7
0x18005246a  jbe     short loc_180052471
0x18005246c  mov     rdx, [r8]
0x18005246f  jmp     short loc_180052474
0x180052471  mov     rdx, r14; lpSubKey
0x180052474  lea     rax, [rbp+9C0h+hKey]
0x180052478  mov     [rsp+0AC0h+phkResult], rax; phkResult
0x18005247d  mov     r9d, 20019h; samDesired
0x180052483  xor     r8d, r8d; ulOptions
0x180052486  mov     rbx, 0FFFFFFFF80000002h
0x18005248d  mov     rcx, rbx; hKey
0x180052490  call    cs:__imp_RegOpenKeyExW
0x180052496  test    eax, eax
0x180052498  jnz     loc_180052B81
0x18005249e  mov     [rsp+0AC0h+cSubKeys], r13d
0x1800524a3  mov     [rsp+0AC0h+cbMaxSubKeyLen], r13d
0x1800524a8  mov     [rsp+0AC0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x1800524ad  mov     [rsp+0AC0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x1800524b2  mov     [rsp+0AC0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x1800524b7  mov     [rsp+0AC0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800524bc  mov     [rsp+0AC0h+lpcValues], r13; lpcValues
0x1800524c1  mov     [rsp+0AC0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800524c6  lea     rax, [rsp+0AC0h+cbMaxSubKeyLen]
0x1800524cb  mov     [rsp+0AC0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800524d0  lea     rax, [rsp+0AC0h+cSubKeys]
0x1800524d5  mov     [rsp+0AC0h+phkResult], rax; int
0x1800524da  xor     r9d, r9d; lpReserved
0x1800524dd  xor     r8d, r8d; lpcchClass
0x1800524e0  xor     edx, edx; lpClass
0x1800524e2  mov     rcx, [rbp+9C0h+hKey]; hKey
0x1800524e6  call    cs:__imp_RegQueryInfoKeyW
0x1800524ec  test    eax, eax
0x1800524ee  jle     short loc_1800524F8
0x1800524f0  movzx   eax, ax
0x1800524f3  or      eax, 80070000h
0x1800524f8  mov     rcx, [rbp+9C8h]; this
0x1800524ff  test    eax, eax
0x180052501  jns     short loc_180052518
0x180052503  mov     r9d, eax; char *
0x180052506  lea     r8, aBaseAppcompatI_7; "base\\appcompat\\inventory\\software\\i"...
0x18005250d  mov     edx, 0A3h; void *
0x180052512  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180052518  mov     esi, r13d
0x18005251b  cmp     [rsp+0AC0h+cSubKeys], r13d
0x180052520  jbe     loc_180052B81
0x180052526  mov     eax, [rsp+0AC0h+cbMaxSubKeyLen]
0x18005252a  inc     eax
0x18005252c  mov     [rsp+0AC0h+cchName], eax
0x180052530  mov     edx, eax
0x180052532  lea     rcx, [rbp+9C0h+lpName]
0x180052536  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x18005253b  nop
0x18005253c  lea     r8, [rbp+9C0h+lpName]
0x180052540  cmp     [rbp+9C0h+var_9B8], 7
0x180052545  cmova   r8, [rbp+9C0h+lpName]; lpName
0x18005254a  mov     [rsp+0AC0h+lpcValues], r13; lpftLastWriteTime
0x18005254f  mov     [rsp+0AC0h+lpcbMaxClassLen], r13; lpcchClass
0x180052554  mov     [rsp+0AC0h+lpcbMaxSubKeyLen], r13; lpClass
0x180052559  mov     [rsp+0AC0h+phkResult], r13; int
0x18005255e  lea     r9, [rsp+0AC0h+cchName]; lpcchName
0x180052563  mov     edx, esi; dwIndex
0x180052565  mov     rcx, [rbp+9C0h+hKey]; hKey
0x180052569  call    cs:__imp_RegEnumKeyExW
0x18005256f  mov     rcx, [rbp+9C8h]; this
0x180052576  test    eax, eax
0x180052578  js      loc_180052BDE
0x18005257e  mov     edx, [rsp+0AC0h+cchName]
0x180052582  lea     rcx, [rbp+9C0h+lpName]
0x180052586  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005258b  lea     rcx, [rbp+9C0h+lpSubKey]
0x18005258f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180052594  nop
0x180052595  lea     rcx, [rbp+9C0h+Src]
0x180052599  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005259e  nop
0x18005259f  mov     rdx, r14
0x1800525a2  lea     rcx, [rbp+9C0h+Src]
0x1800525a6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800525ab  mov     r8d, 1
0x1800525b1  lea     rdx, SubBlock; "\\"
0x1800525b8  lea     rcx, [rbp+9C0h+Src]; Src
0x1800525bc  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800525c1  lea     rdx, [rbp+9C0h+lpName]
0x1800525c5  cmp     [rbp+9C0h+var_9B8], 7
0x1800525ca  cmova   rdx, [rbp+9C0h+lpName]
0x1800525cf  mov     r8, [rbp+9C0h+var_9C0]
0x1800525d3  lea     rcx, [rbp+9C0h+Src]; Src
0x1800525d7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800525dc  lea     rdx, [rbp+9C0h+Src]
0x1800525e0  lea     rcx, [rbp+9C0h+lpSubKey]
0x1800525e4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800525e9  mov     r8d, 8
0x1800525ef  lea     rdx, aPatches; "\\Patches"
0x1800525f6  lea     rcx, [rbp+9C0h+lpSubKey]; Src
0x1800525fa  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800525ff  nop
0x180052600  mov     [rsp+0AC0h+var_A48], r13
0x180052605  lea     rdx, [rbp+9C0h+lpSubKey]
0x180052609  cmp     [rbp+9C0h+var_958], 7
0x18005260e  cmova   rdx, [rbp+9C0h+lpSubKey]; lpSubKey
0x180052613  lea     rax, [rsp+0AC0h+var_A48]
0x180052618  mov     [rsp+0AC0h+phkResult], rax; phkResult
0x18005261d  mov     r9d, 20019h; samDesired
0x180052623  xor     r8d, r8d; ulOptions
0x180052626  mov     rcx, rbx; hKey
0x180052629  call    cs:__imp_RegOpenKeyExW
0x18005262f  test    eax, eax
0x180052631  jnz     loc_180052B4D
0x180052637  mov     [rsp+0AC0h+var_A5C], r13d
0x18005263c  mov     [rsp+0AC0h+var_A50], r13d
0x180052641  mov     [rsp+0AC0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180052646  mov     [rsp+0AC0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18005264b  mov     [rsp+0AC0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x180052650  mov     [rsp+0AC0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180052655  mov     [rsp+0AC0h+lpcValues], r13; lpcValues
0x18005265a  mov     [rsp+0AC0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18005265f  lea     rax, [rsp+0AC0h+var_A50]
0x180052664  mov     [rsp+0AC0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180052669  lea     rax, [rsp+0AC0h+var_A5C]
0x18005266e  mov     [rsp+0AC0h+phkResult], rax; int
0x180052673  xor     r9d, r9d; lpReserved
0x180052676  xor     r8d, r8d; lpcchClass
0x180052679  xor     edx, edx; lpClass
0x18005267b  mov     rcx, [rsp+0AC0h+var_A48]; hKey
0x180052680  call    cs:__imp_RegQueryInfoKeyW
0x180052686  test    eax, eax
0x180052688  jle     short loc_180052692
0x18005268a  movzx   eax, ax
0x18005268d  or      eax, 80070000h
0x180052692  mov     rcx, [rbp+9C8h]; this
0x180052699  test    eax, eax
0x18005269b  js      loc_180052BC9
0x1800526a1  cmp     [rsp+0AC0h+var_A5C], r13d
0x1800526a6  jbe     loc_180052B4D
0x1800526ac  lea     rcx, [rbp+9C0h+var_990]
0x1800526b0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800526b5  nop
0x1800526b6  mov     r8d, 13h
0x1800526bc  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\"
0x1800526c3  lea     rcx, [rbp+9C0h+var_990]
0x1800526c7  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800526cc  lea     rdx, [rbp+9C0h+Src]
0x1800526d0  cmp     [rbp+9C0h+var_9D8], 7
0x1800526d5  cmova   rdx, [rbp+9C0h+Src]
0x1800526da  mov     r8, [rbp+9C0h+var_9E0]
0x1800526de  lea     rcx, [rbp+9C0h+var_990]; Src
0x1800526e2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800526e7  mov     r8d, 12h
0x1800526ed  lea     rdx, aInstallpropert; "\\InstallProperties"
0x1800526f4  lea     rcx, [rbp+9C0h+var_990]; Src
0x1800526f8  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800526fd  lea     rcx, [rbp+9C0h+var_430]; this
0x180052704  call    ??0Application@@QEAA@XZ; Application::Application(void)
0x180052709  nop
0x18005270a  lea     r8, [rbp+9C0h+var_990]
0x18005270e  cmp     [rbp+9C0h+var_978], 7
0x180052713  cmova   r8, [rbp+9C0h+var_990]; unsigned __int16 *
0x180052718  mov     rdx, r12; struct ConfigSettings *
0x18005271b  lea     rcx, [rbp+9C0h+var_820]; this
0x180052722  call    ??0ArpApplication@@QEAA@AEBVConfigSettings@@PEBGK@Z; ArpApplication::ArpApplication(ConfigSettings const &,ushort const *,ulong)
0x180052727  nop
0x180052728  mov     rdx, rax
0x18005272b  lea     rcx, [rbp+9C0h+var_430]
0x180052732  call    ??4Application@@QEAAAEAV0@AEBV0@@Z; Application::operator=(Application const &)
0x180052737  nop
0x180052738  lea     rax, ??_7EpicGamesApplication@@6BIAmiInventoryTelemetryItem@@@; const EpicGamesApplication::`vftable'{for `IAmiInventoryTelemetryItem'}
0x18005273f  mov     [rbp+9C0h+var_820], rax
0x180052746  lea     rax, ??_7AppvApplication@@6BIInventoryDataProvider@Inventory@Compat@Windows@@@; const AppvApplication::`vftable'{for `Windows::Compat::Inventory::IInventoryDataProvider'}
0x18005274d  mov     [rbp+9C0h+var_818], rax
0x180052754  lea     rax, ??_7SteamApplication@@6B@; const SteamApplication::`vftable'
0x18005275b  mov     [rbp+9C0h+var_810], rax
0x180052762  lea     rcx, [rbp+9C0h+var_820]; this
0x180052769  call    ??1Application@@UEAA@XZ; Application::~Application(void)
0x18005276e  mov     edi, r13d
0x180052771  cmp     [rsp+0AC0h+var_A5C], r13d
0x180052776  jbe     loc_180052B36
0x18005277c  mov     eax, [rsp+0AC0h+var_A50]
0x180052780  inc     eax
0x180052782  mov     [rsp+0AC0h+cchName], eax
0x180052786  mov     edx, eax
0x180052788  lea     rcx, [rbp+9C0h+var_A10]
0x18005278c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180052791  nop
0x180052792  lea     r8, [rbp+9C0h+var_A10]
0x180052796  cmp     [rbp+9C0h+var_9F8], 7
0x18005279b  cmova   r8, [rbp+9C0h+var_A10]; lpName
0x1800527a0  mov     [rsp+0AC0h+lpcValues], r13; lpftLastWriteTime
0x1800527a5  mov     [rsp+0AC0h+lpcbMaxClassLen], r13; lpcchClass
0x1800527aa  mov     [rsp+0AC0h+lpcbMaxSubKeyLen], r13; lpClass
0x1800527af  mov     [rsp+0AC0h+phkResult], r13; int
0x1800527b4  lea     r9, [rsp+0AC0h+cchName]; lpcchName
0x1800527b9  mov     edx, edi; dwIndex
0x1800527bb  mov     rcx, [rsp+0AC0h+var_A48]; hKey
0x1800527c0  call    cs:__imp_RegEnumKeyExW
0x1800527c6  mov     rcx, [rbp+9C8h]; this
0x1800527cd  test    eax, eax
0x1800527cf  js      loc_180052BB4
0x1800527d5  mov     edx, [rsp+0AC0h+cchName]
0x1800527d9  lea     rcx, [rbp+9C0h+var_A10]
0x1800527dd  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800527e2  lea     rcx, [rbp+9C0h+var_A30]
0x1800527e6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800527eb  nop
0x1800527ec  lea     rdx, [rbp+9C0h+lpSubKey]
0x1800527f0  lea     rcx, [rbp+9C0h+var_A30]
0x1800527f4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800527f9  mov     r8d, 1
0x1800527ff  lea     rdx, SubBlock; "\\"
0x180052806  lea     rcx, [rbp+9C0h+var_A30]; Src
0x18005280a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005280f  lea     rdx, [rbp+9C0h+var_A10]
0x180052813  cmp     [rbp+9C0h+var_9F8], 7
0x180052818  cmova   rdx, [rbp+9C0h+var_A10]
0x18005281d  mov     r8, [rbp+9C0h+var_A00]
0x180052821  lea     rcx, [rbp+9C0h+var_A30]; Src
0x180052825  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005282a  lea     rax, [rbp+9C0h+var_A30]
0x18005282e  cmp     [rbp+9C0h+var_A18], 7
0x180052833  cmova   rax, qword ptr [rbp+9C0h+var_A30]
0x180052838  mov     [rsp+0AC0h+phkResult], rax
0x18005283d  lea     r9, aPatchIdPathWs; "Patch ID path: %ws"
0x180052844  mov     r8d, 0F9h
0x18005284a  lea     rdx, aApplicationkbf; "ApplicationKbFinder::GetEvidenceFromArp"
0x180052851  mov     ecx, 3
0x180052856  call    AslLogCallPrintf
0x18005285b  lea     rdx, aState; "State"
0x180052862  lea     rcx, [rbp+9C0h+var_9B0]
0x180052866  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005286b  nop
0x18005286c  xor     r9d, r9d
0x18005286f  lea     r8, [rbp+9C0h+var_9B0]
0x180052873  lea     rdx, [rbp+9C0h+var_A30]
0x180052877  mov     rcx, rbx
0x18005287a  call    ?GetRegValueDword@Utility@@SAKQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@1K@Z; Utility::GetRegValueDword(HKEY__ * const,std::wstring const &,std::wstring const &,ulong)
0x18005287f  mov     ebx, eax
0x180052881  lea     rcx, [rbp+9C0h+var_9B0]
0x180052885  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005288a  cmp     ebx, 1
0x18005288d  jz      short loc_1800528A5
0x18005288f  lea     rcx, [rbp+9C0h+var_A30]
0x180052893  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052898  nop
0x180052899  mov     rbx, 0FFFFFFFF80000002h
0x1800528a0  jmp     loc_180052B21
0x1800528a5  lea     rcx, [rbp+9C0h+var_950]
0x1800528a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800528ae  nop
0x1800528af  lea     rdx, aDisplayname_0; "DisplayName"
0x1800528b6  lea     rcx, [rbp+9C0h+var_9B0]
0x1800528ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800528bf  nop
0x1800528c0  lea     r9, [rbp+9C0h+var_9B0]
0x1800528c4  lea     r8, [rbp+9C0h+var_A30]
0x1800528c8  mov     rbx, 0FFFFFFFF80000002h
0x1800528cf  mov     rdx, rbx
0x1800528d2  lea     rcx, [rbp+9C0h+var_910]
0x1800528d9  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800528de  mov     rdx, rax
0x1800528e1  lea     rcx, [rbp+9C0h+var_950]
0x1800528e5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800528ea  lea     rcx, [rbp+9C0h+var_910]
0x1800528f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800528f6  nop
0x1800528f7  lea     rcx, [rbp+9C0h+var_9B0]
0x1800528fb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180052900  lea     rcx, [rbp+9C0h+var_950]
0x180052904  call    ?IsUpdate@Application@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Application::IsUpdate(std::wstring const &)
0x180052909  test    al, al
0x18005290b  jz      loc_180052B0D
0x180052911  lea     rcx, [rbp+9C0h+var_930]
0x180052918  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005291d  nop
0x18005291e  lea     rdx, aInstalled; "Installed"
0x180052925  lea     rcx, [rbp+9C0h+var_9B0]
0x180052929  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005292e  nop
0x18005292f  lea     r9, [rbp+9C0h+var_9B0]
0x180052933  lea     r8, [rbp+9C0h+var_A30]
0x180052937  mov     rdx, rbx
0x18005293a  lea     rcx, [rbp+9C0h+var_910]
  ... truncated ...
```
