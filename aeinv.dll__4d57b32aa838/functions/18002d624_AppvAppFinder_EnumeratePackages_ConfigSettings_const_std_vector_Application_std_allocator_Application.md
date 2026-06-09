# AppvAppFinder::EnumeratePackages(ConfigSettings const &,std::vector<Application,std::allocator<Application>> &)

- ea: `0x18002d624`
- end: `0x18002da42`
- name: `?EnumeratePackages@AppvAppFinder@@SAXAEBVConfigSettings@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@@Z`
- size: `1054`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x180031a40`
- `0x180045740`

## callees

- `0x1800176e0`
- `0x180018a60`
- `0x1800197d4`
- `0x18002d624`
- `0x18002da48`
- `0x18002debc`
- `0x1800404c4`
- `0x180040500`
- `0x18004082c`
- `0x180041d4c`
- `0x180044c44`
- `0x18004826c`
- `0x1800487ac`
- `0x180050030`
- `0x18005113c`
- `0x180059920`
- `0x18005a0ac`
- `0x18005a8bc`
- `0x18005f210`
- `0x180102fe4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002d6ea`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d843`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d6ea`
- `ADVAPI32!RegOpenKeyExW` at `0x18002d843`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d7e0`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d984`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d9de`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d7e0`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d984`
- `ADVAPI32!RegEnumKeyExW` at `0x18002d9de`
- `ADVAPI32!RegCloseKey` at `0x18002d6ab`
- `ADVAPI32!RegCloseKey` at `0x18002da11`
- `ADVAPI32!RegCloseKey` at `0x18002d6ab`
- `ADVAPI32!RegCloseKey` at `0x18002da11`

## string_xrefs

- `0x18002d70d`: `RegOpenKeyEx failed to open appv root key, %ws, (%d)`
- `0x18002d864`: `RegOpenKeyEx failed to open versions key: %ws, (%d)`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
LSTATUS __fastcall AppvAppFinder::EnumeratePackages(__int64 a1, __int64 a2)
{
  const WCHAR *p_lpSubKey_8; // rdx
  AmiPackageIdItem *v5; // rax
  DWORD v6; // ebx
  const WCHAR *v7; // rdx
  DWORD v8; // esi
  DWORD i; // edx
  __int64 v10; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  LSTATUS result; // eax
  DWORD cchName[2]; // [rsp+48h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-B0h] BYREF
  AmiPackageIdItem *v18[2]; // [rsp+60h] [rbp-A8h] BYREF
  __int128 lpSubKey_8; // [rsp+70h] [rbp-98h] BYREF
  __int64 v20; // [rsp+80h] [rbp-88h]
  unsigned __int64 v21; // [rsp+88h] [rbp-80h]
  LPCWSTR v22[4]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v23[32]; // [rsp+B0h] [rbp-58h] BYREF
  _BYTE v24[32]; // [rsp+D0h] [rbp-38h] BYREF
  _BYTE v25[32]; // [rsp+F0h] [rbp-18h] BYREF
  _BYTE v26[32]; // [rsp+110h] [rbp+8h] BYREF
  _BYTE v27[32]; // [rsp+130h] [rbp+28h] BYREF
  _BYTE v28[40]; // [rsp+150h] [rbp+48h] BYREF
  WCHAR Name[264]; // [rsp+178h] [rbp+70h] BYREF

  v18[1] = (AmiPackageIdItem *)-2LL;
  lpSubKey_8 = 0;
  v20 = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&lpSubKey_8);
  hKey = 0;
  p_lpSubKey_8 = (const WCHAR *)&lpSubKey_8;
  if ( v21 > 7 )
    p_lpSubKey_8 = (const WCHAR *)lpSubKey_8;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, p_lpSubKey_8, 0, 0x20019u, &hKey) )
  {
    AslLogCallPrintf(
      3,
      (unsigned int)"AppvAppFinder::EnumeratePackages",
      628,
      (unsigned int)"RegOpenKeyEx failed to open appv root key, %ws, (%d)");
  }
  else
  {
    if ( !qword_1801833B8 )
    {
      v18[0] = (AmiPackageIdItem *)operator new(0x48u);
      v5 = AmiPackageIdItem::AmiPackageIdItem(v18[0]);
      TelCacheProvider::Initialize(
        AppvPackage::m_packageIdLookupStore,
        L"InventoryApplicationAppV",
        (__int64)v5,
        0,
        1,
        3u,
        0x64u);
    }
    if ( *(_BYTE *)(a1 + 48) && *(_BYTE *)(a1 + 49) )
      TelCacheProvider::ClearData((TelCacheProvider *)AppvPackage::m_packageIdLookupStore);
    TelCacheProvider::BatchBegin((TelCacheProvider *)AppvPackage::m_packageIdLookupStore);
    memset_0(Name, 0, 0x208u);
    v6 = 0;
    for ( cchName[0] = 260; !RegEnumKeyExW(hKey, v6, Name, cchName, 0, 0, 0, 0); cchName[0] = 260 )
    {
      std::wstring::wstring(v23, Name);
      std::operator+<unsigned short>(v22, v23, L"\\Versions");
      phkResult = 0;
      v7 = (const WCHAR *)v22;
      if ( v22[3] > (LPCWSTR)7 )
        v7 = v22[0];
      if ( RegOpenKeyExW(hKey, v7, 0, 0x20019u, &phkResult) )
      {
        AslLogCallPrintf(
          3,
          (unsigned int)"AppvAppFinder::EnumeratePackages",
          679,
          (unsigned int)"RegOpenKeyEx failed to open versions key: %ws, (%d)");
      }
      else
      {
        v8 = 0;
        for ( i = 0; ; i = v8 )
        {
          cchName[0] = 260;
          if ( RegEnumKeyExW(phkResult, i, Name, cchName, 0, 0, 0, 0) )
            break;
          v18[0] = (AmiPackageIdItem *)&StoreAppFinder::`vftable';
          std::wstring::wstring(v24, Name);
          v10 = std::operator+<unsigned short>(v28, &lpSubKey_8, L"\\");
          v11 = std::operator+<unsigned short>(v27, v10, v22);
          v12 = std::operator+<unsigned short>(v26, v11, L"\\");
          v13 = std::operator+<unsigned short>(v25, v12, Name);
          AppvPackage::Initialize((__int64)v18, a1, a2, -2147483646, v13, (__int64)v23, (__int64)v24);
          std::wstring::~wstring(v25);
          std::wstring::~wstring(v26);
          std::wstring::~wstring(v27);
          std::wstring::~wstring(v28);
          std::wstring::~wstring(v24);
          v18[0] = (AmiPackageIdItem *)&StoreAppFinder::`vftable';
          ++v8;
        }
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      std::wstring::~wstring(v22);
      std::wstring::~wstring(v23);
      ++v6;
    }
    TelCacheProvider::BatchEnd((TelCacheProvider *)AppvPackage::m_packageIdLookupStore);
  }
  result = std::wstring::~wstring(&lpSubKey_8);
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18002d624  mov     rax, rsp
0x18002d627  push    rbp
0x18002d628  push    rdi
0x18002d629  push    r12
0x18002d62b  push    r14
0x18002d62d  push    r15
0x18002d62f  lea     rbp, [rax-2B8h]
0x18002d636  sub     rsp, 390h
0x18002d63d  mov     qword ptr [rsp+3B0h+lpSubKey], 0FFFFFFFFFFFFFFFEh
0x18002d646  mov     [rax+18h], rbx
0x18002d64a  mov     [rax+20h], rsi
0x18002d64e  mov     rax, cs:__security_cookie
0x18002d655  xor     rax, rsp
0x18002d658  mov     [rbp+2B0h+var_30], rax
0x18002d65f  mov     r14, rdx
0x18002d662  mov     rdi, rcx
0x18002d665  xor     r15d, r15d
0x18002d668  mov     [rsp+3B0h+hKey], r15
0x18002d66d  xorps   xmm0, xmm0
0x18002d670  movups  xmmword ptr [rsp+3B0h+lpSubKey+8], xmm0
0x18002d675  mov     [rsp+3B0h+var_338], r15
0x18002d67a  mov     [rbp+2B0h+var_330], r15
0x18002d67e  lea     r8d, [r15+27h]
0x18002d682  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\AppV\\Client\\Pack"...
0x18002d689  lea     rcx, [rsp+3B0h+lpSubKey+8]
0x18002d68e  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18002d693  nop
0x18002d694  mov     rbx, [rsp+3B0h+hKey]
0x18002d699  test    rbx, rbx
0x18002d69c  jz      short loc_18002D6BB
0x18002d69e  lea     rcx, [rsp+3B0h+var_358]; this
0x18002d6a3  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18002d6a8  mov     rcx, rbx; hKey
0x18002d6ab  call    cs:__imp_RegCloseKey
0x18002d6b1  lea     rcx, [rsp+3B0h+var_358]; this
0x18002d6b6  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18002d6bb  mov     [rsp+3B0h+hKey], r15
0x18002d6c0  lea     rdx, [rsp+3B0h+lpSubKey+8]
0x18002d6c5  cmp     [rbp+2B0h+var_330], 7
0x18002d6ca  cmova   rdx, qword ptr [rsp+3B0h+lpSubKey+8]; lpSubKey
0x18002d6d0  lea     rax, [rsp+3B0h+hKey]
0x18002d6d5  mov     [rsp+3B0h+phkResult], rax; phkResult
0x18002d6da  mov     r9d, 20019h; samDesired
0x18002d6e0  xor     r8d, r8d; ulOptions
0x18002d6e3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002d6ea  call    cs:__imp_RegOpenKeyExW
0x18002d6f0  test    eax, eax
0x18002d6f2  jz      short loc_18002D730
0x18002d6f4  lea     rcx, [rsp+3B0h+lpSubKey+8]
0x18002d6f9  cmp     [rbp+2B0h+var_330], 7
0x18002d6fe  cmova   rcx, qword ptr [rsp+3B0h+lpSubKey+8]
0x18002d704  mov     dword ptr [rsp+3B0h+lpClass], eax
0x18002d708  mov     [rsp+3B0h+phkResult], rcx
0x18002d70d  lea     r9, aRegopenkeyexFa_0; "RegOpenKeyEx failed to open appv root k"...
0x18002d714  mov     r8d, 274h
0x18002d71a  lea     rdx, aAppvappfinderE; "AppvAppFinder::EnumeratePackages"
0x18002d721  mov     ecx, 3
0x18002d726  call    AslLogCallPrintf
0x18002d72b  jmp     loc_18002D9FC
0x18002d730  lea     r12, ?m_packageIdLookupStore@AppvPackage@@2VTelCacheProvider@@A; TelCacheProvider AppvPackage::m_packageIdLookupStore
0x18002d737  cmp     cs:qword_1801833B8, r15
0x18002d73e  jnz     short loc_18002D784
0x18002d740  mov     ecx, 48h ; 'H'; Size
0x18002d745  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002d74a  mov     [rsp+3B0h+var_358], rax
0x18002d74f  mov     rcx, rax; this
0x18002d752  call    ??0AmiPackageIdItem@@QEAA@XZ; AmiPackageIdItem::AmiPackageIdItem(void)
0x18002d757  mov     dword ptr [rsp+3B0h+lpcchClass], 64h ; 'd'
0x18002d75f  mov     dword ptr [rsp+3B0h+lpClass], 3
0x18002d767  mov     dword ptr [rsp+3B0h+phkResult], 1
0x18002d76f  xor     r9d, r9d
0x18002d772  mov     r8, rax
0x18002d775  lea     rdx, aInventoryappli_7; "InventoryApplicationAppV"
0x18002d77c  mov     rcx, r12
0x18002d77f  call    ?Initialize@TelCacheProvider@@QEAAJPEBGPEAVIAmiInventoryItem@@KW4TelCacheTempBehavior@@KK@Z; TelCacheProvider::Initialize(ushort const *,IAmiInventoryItem *,ulong,TelCacheTempBehavior,ulong,ulong)
0x18002d784  cmp     [rdi+30h], r15b
0x18002d788  jz      short loc_18002D798
0x18002d78a  cmp     [rdi+31h], r15b
0x18002d78e  jz      short loc_18002D798
0x18002d790  mov     rcx, r12; this
0x18002d793  call    ?ClearData@TelCacheProvider@@QEAAJXZ; TelCacheProvider::ClearData(void)
0x18002d798  mov     rcx, r12; this
0x18002d79b  call    ?BatchBegin@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchBegin(void)
0x18002d7a0  xor     edx, edx; Val
0x18002d7a2  mov     r8d, 208h; Size
0x18002d7a8  lea     rcx, [rbp+2B0h+Name]; void *
0x18002d7ac  call    memset_0
0x18002d7b1  mov     ebx, r15d
0x18002d7b4  mov     [rsp+3B0h+cchName], 104h
0x18002d7bc  mov     [rsp+3B0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002d7c1  mov     [rsp+3B0h+lpcchClass], r15; lpcchClass
0x18002d7c6  mov     [rsp+3B0h+lpClass], r15; lpClass
0x18002d7cb  mov     [rsp+3B0h+phkResult], r15; lpReserved
0x18002d7d0  lea     r9, [rsp+3B0h+cchName]; lpcchName
0x18002d7d5  lea     r8, [rbp+2B0h+Name]; lpName
0x18002d7d9  xor     edx, edx; dwIndex
0x18002d7db  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18002d7e0  call    cs:__imp_RegEnumKeyExW
0x18002d7e6  test    eax, eax
0x18002d7e8  jnz     loc_18002D9F3
0x18002d7ee  lea     r12, ??_7StoreAppFinder@@6B@; const StoreAppFinder::`vftable'
0x18002d7f5  lea     rdx, [rbp+2B0h+Name]
0x18002d7f9  lea     rcx, [rbp+2B0h+var_308]
0x18002d7fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002d802  nop
0x18002d803  lea     r8, aVersions; "\\Versions"
0x18002d80a  lea     rdx, [rbp+2B0h+var_308]
0x18002d80e  lea     rcx, [rbp+2B0h+var_328]
0x18002d812  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002d817  nop
0x18002d818  mov     [rsp+3B0h+var_360], r15
0x18002d81d  lea     rdx, [rbp+2B0h+var_328]
0x18002d821  cmp     [rbp+2B0h+var_310], 7
0x18002d826  cmova   rdx, [rbp+2B0h+var_328]; lpSubKey
0x18002d82b  lea     rax, [rsp+3B0h+var_360]
0x18002d830  mov     [rsp+3B0h+phkResult], rax; phkResult
0x18002d835  mov     r9d, 20019h; samDesired
0x18002d83b  xor     r8d, r8d; ulOptions
0x18002d83e  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18002d843  call    cs:__imp_RegOpenKeyExW
0x18002d849  test    eax, eax
0x18002d84b  jz      short loc_18002D887
0x18002d84d  lea     rcx, [rbp+2B0h+var_328]
0x18002d851  cmp     [rbp+2B0h+var_310], 7
0x18002d856  cmova   rcx, [rbp+2B0h+var_328]
0x18002d85b  mov     dword ptr [rsp+3B0h+lpClass], eax
0x18002d85f  mov     [rsp+3B0h+phkResult], rcx
0x18002d864  lea     r9, aRegopenkeyexFa; "RegOpenKeyEx failed to open versions ke"...
0x18002d86b  mov     r8d, 2A7h
0x18002d871  lea     rdx, aAppvappfinderE; "AppvAppFinder::EnumeratePackages"
0x18002d878  mov     ecx, 3
0x18002d87d  call    AslLogCallPrintf
0x18002d882  jmp     loc_18002D992
0x18002d887  mov     esi, r15d
0x18002d88a  xor     edx, edx
0x18002d88c  jmp     loc_18002D95A
0x18002d891  mov     [rsp+3B0h+var_358], r12
0x18002d896  lea     rdx, [rbp+2B0h+Name]
0x18002d89a  lea     rcx, [rbp+2B0h+var_2E8]
0x18002d89e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002d8a3  nop
0x18002d8a4  lea     r8, SubBlock; "\\"
0x18002d8ab  lea     rdx, [rsp+3B0h+lpSubKey+8]
0x18002d8b0  lea     rcx, [rbp+2B0h+var_268]
0x18002d8b4  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18002d8b9  nop
0x18002d8ba  lea     r8, [rbp+2B0h+var_328]
0x18002d8be  mov     rdx, rax
0x18002d8c1  lea     rcx, [rbp+2B0h+var_288]
0x18002d8c5  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18002d8ca  nop
0x18002d8cb  lea     r8, SubBlock; "\\"
0x18002d8d2  mov     rdx, rax
0x18002d8d5  lea     rcx, [rbp+2B0h+var_2A8]
0x18002d8d9  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002d8de  nop
0x18002d8df  lea     r8, [rbp+2B0h+Name]
0x18002d8e3  mov     rdx, rax
0x18002d8e6  lea     rcx, [rbp+2B0h+var_2C8]
0x18002d8ea  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18002d8ef  nop
0x18002d8f0  lea     rcx, [rbp+2B0h+var_2E8]
0x18002d8f4  mov     [rsp+3B0h+lpcchClass], rcx
0x18002d8f9  lea     rcx, [rbp+2B0h+var_308]
0x18002d8fd  mov     [rsp+3B0h+lpClass], rcx
0x18002d902  mov     [rsp+3B0h+phkResult], rax
0x18002d907  mov     r9, 0FFFFFFFF80000002h
0x18002d90e  mov     r8, r14
0x18002d911  mov     rdx, rdi
0x18002d914  lea     rcx, [rsp+3B0h+var_358]
0x18002d919  call    ?Initialize@AppvPackage@@QEAAXAEBVConfigSettings@@AEAV?$vector@VApplication@@V?$allocator@VApplication@@@std@@@std@@PEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@33@Z; AppvPackage::Initialize(ConfigSettings const &,std::vector<Application> &,HKEY__ *,std::wstring const &,std::wstring const &,std::wstring const &)
0x18002d91e  nop
0x18002d91f  lea     rcx, [rbp+2B0h+var_2C8]
0x18002d923  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d928  nop
0x18002d929  lea     rcx, [rbp+2B0h+var_2A8]
0x18002d92d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d932  nop
0x18002d933  lea     rcx, [rbp+2B0h+var_288]
0x18002d937  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d93c  nop
0x18002d93d  lea     rcx, [rbp+2B0h+var_268]
0x18002d941  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d946  nop
0x18002d947  lea     rcx, [rbp+2B0h+var_2E8]
0x18002d94b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d950  nop
0x18002d951  mov     [rsp+3B0h+var_358], r12
0x18002d956  inc     esi
0x18002d958  mov     edx, esi; dwIndex
0x18002d95a  mov     [rsp+3B0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002d95f  mov     [rsp+3B0h+lpcchClass], r15; lpcchClass
0x18002d964  mov     [rsp+3B0h+lpClass], r15; lpClass
0x18002d969  mov     [rsp+3B0h+phkResult], r15; lpReserved
0x18002d96e  mov     [rsp+3B0h+cchName], 104h
0x18002d976  lea     r9, [rsp+3B0h+cchName]; lpcchName
0x18002d97b  lea     r8, [rbp+2B0h+Name]; lpName
0x18002d97f  mov     rcx, [rsp+3B0h+var_360]; hKey
0x18002d984  call    cs:__imp_RegEnumKeyExW
0x18002d98a  test    eax, eax
0x18002d98c  jz      loc_18002D891
0x18002d992  lea     rcx, [rsp+3B0h+var_360]
0x18002d997  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d99c  nop
0x18002d99d  lea     rcx, [rbp+2B0h+var_328]
0x18002d9a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d9a6  nop
0x18002d9a7  lea     rcx, [rbp+2B0h+var_308]
0x18002d9ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002d9b0  inc     ebx
0x18002d9b2  mov     [rsp+3B0h+cchName], 104h
0x18002d9ba  mov     [rsp+3B0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18002d9bf  mov     [rsp+3B0h+lpcchClass], r15; lpcchClass
0x18002d9c4  mov     [rsp+3B0h+lpClass], r15; lpClass
0x18002d9c9  mov     [rsp+3B0h+phkResult], r15; lpReserved
0x18002d9ce  lea     r9, [rsp+3B0h+cchName]; lpcchName
0x18002d9d3  lea     r8, [rbp+2B0h+Name]; lpName
0x18002d9d7  mov     edx, ebx; dwIndex
0x18002d9d9  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18002d9de  call    cs:__imp_RegEnumKeyExW
0x18002d9e4  test    eax, eax
0x18002d9e6  jz      loc_18002D7F5
0x18002d9ec  lea     r12, ?m_packageIdLookupStore@AppvPackage@@2VTelCacheProvider@@A; TelCacheProvider AppvPackage::m_packageIdLookupStore
0x18002d9f3  mov     rcx, r12; this
0x18002d9f6  call    ?BatchEnd@TelCacheProvider@@QEAAJXZ; TelCacheProvider::BatchEnd(void)
0x18002d9fb  nop
0x18002d9fc  lea     rcx, [rsp+3B0h+lpSubKey+8]
0x18002da01  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002da06  nop
0x18002da07  mov     rcx, [rsp+3B0h+hKey]; hKey
0x18002da0c  test    rcx, rcx
0x18002da0f  jz      short loc_18002DA17
0x18002da11  call    cs:__imp_RegCloseKey
0x18002da17  mov     rcx, [rbp+2B0h+var_30]
0x18002da1e  xor     rcx, rsp; StackCookie
0x18002da21  call    __security_check_cookie
0x18002da26  lea     r11, [rsp+3B0h+var_20]
0x18002da2e  mov     rbx, [r11+40h]
0x18002da32  mov     rsi, [r11+48h]
0x18002da36  mov     rsp, r11
0x18002da39  pop     r15
0x18002da3b  pop     r14
0x18002da3d  pop     r12
0x18002da3f  pop     rdi
0x18002da40  pop     rbp
0x18002da41  retn
```
