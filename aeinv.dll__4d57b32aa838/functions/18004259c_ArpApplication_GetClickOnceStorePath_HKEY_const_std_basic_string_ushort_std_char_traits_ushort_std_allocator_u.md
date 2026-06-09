# ArpApplication::GetClickOnceStorePath(HKEY__ * const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004259c`
- end: `0x1800429fa`
- name: `?GetClickOnceStorePath@ArpApplication@@SAXQEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV34@@Z`
- size: `1118`
- prototype: `__int64 __fastcall(HKEY hKey, const WCHAR *, __int64)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18002e8f8`

## callees

- `0x1800150ac`
- `0x1800175b0`
- `0x1800176e0`
- `0x180017724`
- `0x180018450`
- `0x180018a60`
- `0x18001e0d0`
- `0x180041d4c`
- `0x18004259c`
- `0x180044c44`
- `0x18004826c`
- `0x1800487ac`
- `0x180050030`
- `0x180059920`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180042602`
- `ADVAPI32!RegOpenKeyExW` at `0x18004269e`
- `ADVAPI32!RegOpenKeyExW` at `0x180042602`
- `ADVAPI32!RegOpenKeyExW` at `0x18004269e`
- `ADVAPI32!RegCloseKey` at `0x180042664`
- `ADVAPI32!RegCloseKey` at `0x180042664`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ArpApplication::GetClickOnceStorePath(HKEY hKey, const WCHAR *a2, __int64 a3)
{
  const WCHAR *v4; // rbx
  __int64 v6; // rax
  const WCHAR *v7; // rdx
  __int64 RegValueString; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  HKEY hKeya; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult[3]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v24[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v25; // [rsp+60h] [rbp-A0h]
  _BYTE v26[32]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v27[32]; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v29[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v30; // [rsp+E0h] [rbp-20h]
  WCHAR v31[16]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR v32[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v33[32]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v34[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v35[32]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR v36[16]; // [rsp+190h] [rbp+90h] BYREF
  _BYTE v37[32]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE v38[32]; // [rsp+1D0h] [rbp+D0h] BYREF
  _BYTE v39[32]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v40[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE v41[32]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v42[32]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v43[32]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v44[32]; // [rsp+290h] [rbp+190h] BYREF
  _BYTE v45[32]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _BYTE v46[32]; // [rsp+2D0h] [rbp+1D0h] BYREF

  phkResult[2] = HKEY_DYN_DATA|0x7FFFFFF8LL;
  v4 = a2;
  phkResult[0] = 0;
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(const WCHAR **)a2;
  if ( !RegOpenKeyExW(hKey, a2, 0, 0x20019u, phkResult) )
  {
    v6 = std::operator+<unsigned short>(v27, v4, L"\\");
    std::operator+<unsigned short>(lpSubKey, v6, Application::ClickOnceAppStorePath);
    std::wstring::~wstring(v27);
    hKeya = 0;
    v7 = (const WCHAR *)lpSubKey;
    if ( lpSubKey[3] > (LPCWSTR)7 )
      v7 = lpSubKey[0];
    if ( !RegOpenKeyExW(hKey, v7, 0, 0x20019u, &hKeya) )
    {
      std::wstring::wstring(v36, Application::ClickOnceAppStoreName);
      std::wstring::wstring(v24);
      RegValueString = Utility::GetRegValueString((__int64)v27, hKey, (const WCHAR *)lpSubKey, v36);
      std::wstring::operator=(v24, RegValueString);
      std::wstring::~wstring(v27);
      if ( v25 == 24 )
      {
        std::wstring::substr(v24, v27, 0, 8);
        std::wstring::substr(v24, v35, 8, 3);
        std::wstring::substr(v24, v34, 11, 8);
        std::wstring::substr(v24, v33, 19, 3);
        v9 = std::operator+<unsigned short>(v26, v4, L"\\");
        std::operator+<unsigned short>(v32, v9, Application::ClickOnceUserAppData);
        std::wstring::~wstring(v26);
        std::wstring::wstring(v31, Application::ClickOnceUserAppDataName);
        std::wstring::wstring(v29);
        v10 = Utility::GetRegValueString((__int64)v26, hKey, v32, v31);
        std::wstring::operator=(v29, v10);
        std::wstring::~wstring(v26);
        if ( v30 )
        {
          v11 = std::operator+<unsigned short>(v37, v29, L"\\");
          std::operator+<unsigned short>(v26, v11, Application::ClickOnceStoreRoot);
          std::wstring::~wstring(v37);
          v12 = std::operator+<unsigned short>(v46, v26, L"\\");
          v13 = std::operator+<unsigned short>(v45, v12, v27);
          v14 = std::operator+<unsigned short>(v44, v13, L".");
          v15 = std::operator+<unsigned short>(v43, v14, v35);
          v16 = std::operator+<unsigned short>(v42, v15, L"\\");
          v17 = std::operator+<unsigned short>(v41, v16, v34);
          v18 = std::operator+<unsigned short>(v40, v17, L".");
          v19 = std::operator+<unsigned short>(v39, v18, v33);
          v20 = std::operator+<unsigned short>(v38, v19, L"\\");
          std::wstring::operator=(a3, v20);
          std::wstring::~wstring(v38);
          std::wstring::~wstring(v39);
          std::wstring::~wstring(v40);
          std::wstring::~wstring(v41);
          std::wstring::~wstring(v42);
          std::wstring::~wstring(v43);
          std::wstring::~wstring(v44);
          std::wstring::~wstring(v45);
          std::wstring::~wstring(v46);
          std::wstring::~wstring(v26);
        }
        std::wstring::~wstring(v29);
        std::wstring::~wstring(v31);
        std::wstring::~wstring(v32);
        std::wstring::~wstring(v33);
        std::wstring::~wstring(v34);
        std::wstring::~wstring(v35);
        std::wstring::~wstring(v27);
      }
      std::wstring::~wstring(v24);
      std::wstring::~wstring(v36);
    }
    std::wstring::~wstring(lpSubKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeya);
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResult);
}

```

## disassembly

```asm
0x18004259c  push    rbp
0x18004259e  push    rbx
0x18004259f  push    rsi
0x1800425a0  push    rdi
0x1800425a1  push    r13
0x1800425a3  push    r14
0x1800425a5  push    r15
0x1800425a7  lea     rbp, [rsp-200h]
0x1800425af  sub     rsp, 300h
0x1800425b6  mov     [rsp+330h+var_2E8], 0FFFFFFFFFFFFFFFEh
0x1800425bf  mov     rax, cs:__security_cookie
0x1800425c6  xor     rax, rsp
0x1800425c9  mov     [rbp+230h+var_40], rax
0x1800425d0  mov     r14, r8
0x1800425d3  mov     rbx, rdx
0x1800425d6  mov     rdi, rcx
0x1800425d9  mov     [rsp+330h+var_2F8], 0
0x1800425e2  cmp     qword ptr [rdx+18h], 7
0x1800425e7  jbe     short loc_1800425EC
0x1800425e9  mov     rdx, [rdx]; lpSubKey
0x1800425ec  lea     rax, [rsp+330h+var_2F8]
0x1800425f1  mov     [rsp+330h+phkResult], rax; phkResult
0x1800425f6  mov     r15d, 20019h
0x1800425fc  mov     r9d, r15d; samDesired
0x1800425ff  xor     r8d, r8d; ulOptions
0x180042602  call    cs:__imp_RegOpenKeyExW
0x180042608  test    eax, eax
0x18004260a  jnz     loc_1800429CF
0x180042610  mov     [rsp+330h+hKey], 0
0x180042619  lea     r13, SubBlock; "\\"
0x180042620  mov     r8, r13
0x180042623  mov     rdx, rbx
0x180042626  lea     rcx, [rbp+230h+var_2A0]
0x18004262a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004262f  nop
0x180042630  lea     r8, ?ClickOnceAppStorePath@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ClickOnceAppStorePath
0x180042637  mov     rdx, rax
0x18004263a  lea     rcx, [rbp+230h+lpSubKey]
0x18004263e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180042643  nop
0x180042644  lea     rcx, [rbp+230h+var_2A0]
0x180042648  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004264d  mov     rsi, [rsp+330h+hKey]
0x180042652  test    rsi, rsi
0x180042655  jz      short loc_180042674
0x180042657  lea     rcx, [rsp+330h+var_2F0]; this
0x18004265c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180042661  mov     rcx, rsi; hKey
0x180042664  call    cs:__imp_RegCloseKey
0x18004266a  lea     rcx, [rsp+330h+var_2F0]; this
0x18004266f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180042674  mov     [rsp+330h+hKey], 0
0x18004267d  lea     rdx, [rbp+230h+lpSubKey]
0x180042681  cmp     [rbp+230h+var_268], 7
0x180042686  cmova   rdx, [rbp+230h+lpSubKey]; lpSubKey
0x18004268b  lea     rax, [rsp+330h+hKey]
0x180042690  mov     [rsp+330h+phkResult], rax; phkResult
0x180042695  mov     r9d, r15d; samDesired
0x180042698  xor     r8d, r8d; ulOptions
0x18004269b  mov     rcx, rdi; hKey
0x18004269e  call    cs:__imp_RegOpenKeyExW
0x1800426a4  test    eax, eax
0x1800426a6  jnz     loc_1800429BA
0x1800426ac  lea     rdx, ?ClickOnceAppStoreName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ClickOnceAppStoreName
0x1800426b3  lea     rcx, [rbp+230h+var_1A0]
0x1800426ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800426bf  nop
0x1800426c0  lea     rcx, [rsp+330h+var_2E0]
0x1800426c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800426ca  nop
0x1800426cb  lea     r9, [rbp+230h+var_1A0]
0x1800426d2  lea     r8, [rbp+230h+lpSubKey]
0x1800426d6  mov     rdx, rdi
0x1800426d9  lea     rcx, [rbp+230h+var_2A0]
0x1800426dd  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800426e2  mov     rdx, rax
0x1800426e5  lea     rcx, [rsp+330h+var_2E0]
0x1800426ea  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800426ef  lea     rcx, [rbp+230h+var_2A0]
0x1800426f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800426f8  cmp     [rsp+330h+var_2D0], 18h
0x1800426fe  jnz     loc_1800429A2
0x180042704  mov     r15d, 8
0x18004270a  mov     r9d, r15d
0x18004270d  xor     r8d, r8d
0x180042710  lea     rdx, [rbp+230h+var_2A0]
0x180042714  lea     rcx, [rsp+330h+var_2E0]
0x180042719  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18004271e  nop
0x18004271f  lea     esi, [r15-5]
0x180042723  mov     r9d, esi
0x180042726  mov     r8d, r15d
0x180042729  lea     rdx, [rbp+230h+var_1C0]
0x18004272d  lea     rcx, [rsp+330h+var_2E0]
0x180042732  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180042737  nop
0x180042738  mov     r9d, r15d
0x18004273b  lea     r8d, [r15+3]
0x18004273f  lea     rdx, [rbp+230h+var_1E0]
0x180042743  lea     rcx, [rsp+330h+var_2E0]
0x180042748  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18004274d  nop
0x18004274e  mov     r9d, esi
0x180042751  lea     r8d, [r15+0Bh]
0x180042755  lea     rdx, [rbp+230h+var_200]
0x180042759  lea     rcx, [rsp+330h+var_2E0]
0x18004275e  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180042763  nop
0x180042764  mov     r8, r13
0x180042767  mov     rdx, rbx
0x18004276a  lea     rcx, [rsp+330h+var_2C0]
0x18004276f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180042774  nop
0x180042775  lea     r8, ?ClickOnceUserAppData@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ClickOnceUserAppData
0x18004277c  mov     rdx, rax
0x18004277f  lea     rcx, [rbp+230h+var_220]
0x180042783  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180042788  nop
0x180042789  lea     rcx, [rsp+330h+var_2C0]
0x18004278e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042793  lea     rdx, ?ClickOnceUserAppDataName@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ClickOnceUserAppDataName
0x18004279a  lea     rcx, [rbp+230h+var_240]
0x18004279e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800427a3  nop
0x1800427a4  lea     rcx, [rbp+230h+var_260]
0x1800427a8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800427ad  nop
0x1800427ae  lea     r9, [rbp+230h+var_240]
0x1800427b2  lea     r8, [rbp+230h+var_220]
0x1800427b6  mov     rdx, rdi
0x1800427b9  lea     rcx, [rsp+330h+var_2C0]
0x1800427be  call    ?GetRegValueString@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAUHKEY__@@AEBV23@1_N@Z; Utility::GetRegValueString(HKEY__ * const,std::wstring const &,std::wstring const &,bool)
0x1800427c3  mov     rdx, rax
0x1800427c6  lea     rcx, [rbp+230h+var_260]
0x1800427ca  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800427cf  lea     rcx, [rsp+330h+var_2C0]
0x1800427d4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800427d9  cmp     [rbp+230h+var_250], 0
0x1800427de  jbe     loc_18004295C
0x1800427e4  mov     r8, r13
0x1800427e7  lea     rdx, [rbp+230h+var_260]
0x1800427eb  lea     rcx, [rbp+230h+var_180]
0x1800427f2  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1800427f7  nop
0x1800427f8  lea     r8, ?ClickOnceStoreRoot@Application@@2V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@B; std::wstring const Application::ClickOnceStoreRoot
0x1800427ff  mov     rdx, rax
0x180042802  lea     rcx, [rsp+330h+var_2C0]
0x180042807  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004280c  nop
0x18004280d  lea     rcx, [rbp+230h+var_180]
0x180042814  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042819  mov     r8, r13
0x18004281c  lea     rdx, [rsp+330h+var_2C0]
0x180042821  lea     rcx, [rbp+230h+var_60]
0x180042828  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18004282d  nop
0x18004282e  lea     r8, [rbp+230h+var_2A0]
0x180042832  mov     rdx, rax
0x180042835  lea     rcx, [rbp+230h+var_80]
0x18004283c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180042841  nop
0x180042842  lea     r8, asc_180139934; "."
0x180042849  mov     rdx, rax
0x18004284c  lea     rcx, [rbp+230h+var_A0]
0x180042853  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180042858  nop
0x180042859  lea     r8, [rbp+230h+var_1C0]
0x18004285d  mov     rdx, rax
0x180042860  lea     rcx, [rbp+230h+var_C0]
0x180042867  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18004286c  nop
0x18004286d  mov     r8, r13
0x180042870  mov     rdx, rax
0x180042873  lea     rcx, [rbp+230h+var_E0]
0x18004287a  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18004287f  nop
0x180042880  lea     r8, [rbp+230h+var_1E0]
0x180042884  mov     rdx, rax
0x180042887  lea     rcx, [rbp+230h+var_100]
0x18004288e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180042893  nop
0x180042894  lea     r8, asc_180139934; "."
0x18004289b  mov     rdx, rax
0x18004289e  lea     rcx, [rbp+230h+var_120]
0x1800428a5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800428aa  nop
0x1800428ab  lea     r8, [rbp+230h+var_200]
0x1800428af  mov     rdx, rax
0x1800428b2  lea     rcx, [rbp+230h+var_140]
0x1800428b9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800428be  nop
0x1800428bf  mov     r8, r13
0x1800428c2  mov     rdx, rax
0x1800428c5  lea     rcx, [rbp+230h+var_160]
0x1800428cc  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x1800428d1  mov     rdx, rax
0x1800428d4  mov     rcx, r14
0x1800428d7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800428dc  lea     rcx, [rbp+230h+var_160]
0x1800428e3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800428e8  nop
0x1800428e9  lea     rcx, [rbp+230h+var_140]
0x1800428f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800428f5  nop
0x1800428f6  lea     rcx, [rbp+230h+var_120]
0x1800428fd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042902  nop
0x180042903  lea     rcx, [rbp+230h+var_100]
0x18004290a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004290f  nop
0x180042910  lea     rcx, [rbp+230h+var_E0]
0x180042917  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004291c  nop
0x18004291d  lea     rcx, [rbp+230h+var_C0]
0x180042924  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042929  nop
0x18004292a  lea     rcx, [rbp+230h+var_A0]
0x180042931  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042936  nop
0x180042937  lea     rcx, [rbp+230h+var_80]
0x18004293e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042943  nop
0x180042944  lea     rcx, [rbp+230h+var_60]
0x18004294b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042950  nop
0x180042951  lea     rcx, [rsp+330h+var_2C0]
0x180042956  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004295b  nop
0x18004295c  lea     rcx, [rbp+230h+var_260]
0x180042960  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042965  nop
0x180042966  lea     rcx, [rbp+230h+var_240]
0x18004296a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004296f  nop
0x180042970  lea     rcx, [rbp+230h+var_220]
0x180042974  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042979  nop
0x18004297a  lea     rcx, [rbp+230h+var_200]
0x18004297e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042983  nop
0x180042984  lea     rcx, [rbp+230h+var_1E0]
0x180042988  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004298d  nop
0x18004298e  lea     rcx, [rbp+230h+var_1C0]
0x180042992  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180042997  nop
0x180042998  lea     rcx, [rbp+230h+var_2A0]
0x18004299c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800429a1  nop
0x1800429a2  lea     rcx, [rsp+330h+var_2E0]
0x1800429a7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800429ac  nop
0x1800429ad  lea     rcx, [rbp+230h+var_1A0]
0x1800429b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800429b9  nop
0x1800429ba  lea     rcx, [rbp+230h+lpSubKey]
0x1800429be  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800429c3  nop
0x1800429c4  lea     rcx, [rsp+330h+hKey]
0x1800429c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800429ce  nop
0x1800429cf  lea     rcx, [rsp+330h+var_2F8]
0x1800429d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800429d9  mov     rcx, [rbp+230h+var_40]
0x1800429e0  xor     rcx, rsp; StackCookie
0x1800429e3  call    __security_check_cookie
0x1800429e8  add     rsp, 300h
0x1800429ef  pop     r15
0x1800429f1  pop     r14
0x1800429f3  pop     r13
0x1800429f5  pop     rdi
0x1800429f6  pop     rsi
0x1800429f7  pop     rbx
0x1800429f8  pop     rbp
0x1800429f9  retn
```
