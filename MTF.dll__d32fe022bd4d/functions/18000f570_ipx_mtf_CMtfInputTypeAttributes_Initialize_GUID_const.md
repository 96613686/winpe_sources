# ipx::mtf::CMtfInputTypeAttributes::Initialize(_GUID const &)

- ea: `0x18000f570`
- end: `0x18000f95c`
- name: `?Initialize@CMtfInputTypeAttributes@mtf@ipx@@UEAAJAEBU_GUID@@@Z`
- size: `1004`
- prototype: `__int64 __fastcall(ipx::mtf::CMtfInputTypeAttributes *__hidden this, const struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800068a4`
- `0x18000ecc8`
- `0x18000ee80`
- `0x18000f570`
- `0x18000fea4`
- `0x18000ff34`
- `0x18002bca0`
- `0x18002bd60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f63a`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000f63a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f6e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f71b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f772`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f7ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f80a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f872`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8fe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f6e1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f71b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f772`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f7ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f80a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f872`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000f8fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f929`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000f929`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f683`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000f683`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f81f`
- `OLEAUT32!__imp_SysAllocString` at `0x18000f81f`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f61c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f61c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f60b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f82f`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f60b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000f82f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::CMtfInputTypeAttributes::Initialize(
        ipx::mtf::CMtfInputTypeAttributes *this,
        const struct _GUID *a2)
{
  int v5; // edi
  OLECHAR *v6; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  BYTE v9[4]; // [rsp+38h] [rbp-C8h] BYREF
  DWORD Type; // [rsp+3Ch] [rbp-C4h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v12; // [rsp+48h] [rbp-B8h] BYREF
  OLECHAR v13[24]; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR SubKey[256]; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[5008]; // [rsp+2D0h] [rbp+1D0h] BYREF

  if ( *((_QWORD *)this + 22) == *(_QWORD *)&a2->Data1 && *((_QWORD *)this + 23) == *(_QWORD *)a2->Data4 )
    return 0;
  hKey = 0;
  ipx::mtf::CFuzzyTable::RemoveAllEntries((ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 8));
  ipx::mtf::CFuzzyTable::RemoveAllEntries((ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 48));
  ipx::mtf::CFuzzyHiraganaTable::RemoveAllEntries((ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 88));
  ipx::mtf::CFuzzyHiraganaTable::RemoveAllEntries((ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 128));
  if ( SysStringLen(*((BSTR *)this + 21)) )
  {
    SysFreeString(*((BSTR *)this + 21));
    *((_QWORD *)this + 21) = 0;
  }
  v5 = StringFromGUID2(a2, sz, 39);
  if ( v5 >= 0 )
  {
    v5 = StringCchPrintfW(SubKey, 0x100u, L"Software\\Microsoft\\MTFInputType\\%s", sz);
    if ( v5 >= 0 )
      RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
  }
  if ( hKey )
  {
    cbData = 2500;
    lpcbData = 4;
    v12 = 4;
    Type = 3;
    *(_DWORD *)v9 = 0;
    if ( !RegQueryValueExW(hKey, L"KeyTable", 0, &Type, Data, &cbData) )
    {
      lpcbData = 4;
      RegQueryValueExW(hKey, L"HaveKeyTableScore", 0, &v12, v9, &lpcbData);
      if ( cbData )
        ipx::mtf::CFuzzyTable::BuildTable(
          (ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 8),
          Data,
          cbData,
          *(int *)v9);
    }
    cbData = 2500;
    if ( !RegQueryValueExW(hKey, L"AccentTable", 0, &Type, Data, &cbData) )
    {
      lpcbData = 4;
      RegQueryValueExW(hKey, L"HaveAccentTableScore", 0, &v12, v9, &lpcbData);
      if ( cbData )
        ipx::mtf::CFuzzyTable::BuildTable(
          (ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 48),
          Data,
          cbData,
          *(int *)v9);
    }
    cbData = 20;
    Type = 1;
    if ( !RegQueryValueExW(hKey, L"SymbolsToInsert", 0, &Type, (LPBYTE)v13, &cbData) )
    {
      if ( cbData )
      {
        v6 = SysAllocString(v13);
        *((_QWORD *)this + 21) = v6;
        if ( !SysStringLen(v6) )
          v5 = -2147024882;
      }
    }
    cbData = 2500;
    if ( !RegQueryValueExW(hKey, L"HiraganaFuzzyTable", 0, &Type, Data, &cbData) )
    {
      lpcbData = 4;
      RegQueryValueExW(hKey, L"HaveHiraganaScore", 0, &v12, v9, &lpcbData);
      if ( cbData )
        ipx::mtf::CFuzzyHiraganaTable::BuildTable(
          (ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 88),
          Data,
          cbData,
          *(int *)v9);
    }
    cbData = 2500;
    if ( !RegQueryValueExW(hKey, L"RomajiFuzzyTable", 0, &Type, Data, &cbData) )
    {
      if ( cbData )
        ipx::mtf::CFuzzyHiraganaTable::BuildTable(
          (ipx::mtf::CMtfInputTypeAttributes *)((char *)this + 128),
          Data,
          cbData,
          1);
    }
    RegCloseKey(hKey);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000f570  mov     [rsp-8+arg_10], rbx
0x18000f575  mov     [rsp-8+arg_18], rsi
0x18000f57a  push    rbp
0x18000f57b  push    rdi
0x18000f57c  push    r12
0x18000f57e  push    r14
0x18000f580  push    r15
0x18000f582  lea     rbp, [rsp-1570h]
0x18000f58a  mov     eax, 1670h
0x18000f58f  call    _alloca_probe
0x18000f594  sub     rsp, rax
0x18000f597  mov     rax, cs:__security_cookie
0x18000f59e  xor     rax, rsp
0x18000f5a1  mov     [rbp+1590h+var_30], rax
0x18000f5a8  mov     rax, [rcx+0B0h]
0x18000f5af  mov     rdi, rdx
0x18000f5b2  mov     rbx, rcx
0x18000f5b5  cmp     rax, [rdx]
0x18000f5b8  jnz     short loc_18000F5CE
0x18000f5ba  mov     rax, [rcx+0B8h]
0x18000f5c1  cmp     rax, [rdx+8]
0x18000f5c5  jnz     short loc_18000F5CE
0x18000f5c7  xor     eax, eax
0x18000f5c9  jmp     loc_18000F931
0x18000f5ce  add     rcx, 8; this
0x18000f5d2  mov     [rsp+1690h+hKey], 0
0x18000f5db  call    ?RemoveAllEntries@CFuzzyTable@mtf@ipx@@QEAAXXZ; ipx::mtf::CFuzzyTable::RemoveAllEntries(void)
0x18000f5e0  lea     rcx, [rbx+30h]; this
0x18000f5e4  call    ?RemoveAllEntries@CFuzzyTable@mtf@ipx@@QEAAXXZ; ipx::mtf::CFuzzyTable::RemoveAllEntries(void)
0x18000f5e9  lea     r15, [rbx+58h]
0x18000f5ed  mov     rcx, r15; this
0x18000f5f0  call    ?RemoveAllEntries@CFuzzyHiraganaTable@mtf@ipx@@QEAAXXZ; ipx::mtf::CFuzzyHiraganaTable::RemoveAllEntries(void)
0x18000f5f5  lea     r12, [rbx+80h]
0x18000f5fc  mov     rcx, r12; this
0x18000f5ff  call    ?RemoveAllEntries@CFuzzyHiraganaTable@mtf@ipx@@QEAAXXZ; ipx::mtf::CFuzzyHiraganaTable::RemoveAllEntries(void)
0x18000f604  mov     rcx, [rbx+0A8h]; pbstr
0x18000f60b  call    cs:__imp_SysStringLen
0x18000f611  test    eax, eax
0x18000f613  jz      short loc_18000F62D
0x18000f615  mov     rcx, [rbx+0A8h]; bstrString
0x18000f61c  call    cs:__imp_SysFreeString
0x18000f622  mov     qword ptr [rbx+0A8h], 0
0x18000f62d  mov     r8d, 27h ; '''; cchMax
0x18000f633  lea     rdx, [rbp+1590h+sz]; lpsz
0x18000f637  mov     rcx, rdi; rguid
0x18000f63a  call    cs:__imp_StringFromGUID2
0x18000f640  mov     edi, eax
0x18000f642  test    eax, eax
0x18000f644  js      short loc_18000F689
0x18000f646  lea     r9, [rbp+1590h+sz]
0x18000f64a  mov     edx, 100h; unsigned __int64
0x18000f64f  lea     r8, aSoftwareMicros; "Software\\Microsoft\\MTFInputType\\%s"
0x18000f656  lea     rcx, [rbp+1590h+SubKey]; unsigned __int16 *
0x18000f65a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000f65f  mov     edi, eax
0x18000f661  test    eax, eax
0x18000f663  js      short loc_18000F689
0x18000f665  lea     rax, [rsp+1690h+hKey]
0x18000f66a  mov     r9d, 20019h; samDesired
0x18000f670  xor     r8d, r8d; ulOptions
0x18000f673  mov     [rsp+1690h+phkResult], rax; phkResult
0x18000f678  lea     rdx, [rbp+1590h+SubKey]; lpSubKey
0x18000f67c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000f683  call    cs:__imp_RegOpenKeyExW
0x18000f689  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f68e  test    rcx, rcx
0x18000f691  jz      loc_18000F92F
0x18000f697  mov     eax, 4
0x18000f69c  mov     [rsp+1690h+cbData], 9C4h
0x18000f6a4  mov     [rsp+1690h+var_165C], eax
0x18000f6a8  lea     r9, [rsp+1690h+Type]; lpType
0x18000f6ad  mov     [rsp+1690h+var_1648], eax
0x18000f6b1  lea     rdx, ValueName; "KeyTable"
0x18000f6b8  lea     rax, [rsp+1690h+cbData]
0x18000f6bd  mov     [rsp+1690h+Type], 3
0x18000f6c5  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f6ca  xor     r8d, r8d; lpReserved
0x18000f6cd  lea     rax, [rbp+1590h+Data]
0x18000f6d4  mov     dword ptr [rsp+1690h+var_1658], 0
0x18000f6dc  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f6e1  call    cs:__imp_RegQueryValueExW
0x18000f6e7  test    eax, eax
0x18000f6e9  jnz     short loc_18000F740
0x18000f6eb  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f6f0  lea     rax, [rsp+1690h+var_165C]
0x18000f6f5  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f6fa  lea     r9, [rsp+1690h+var_1648]; lpType
0x18000f6ff  lea     rax, [rsp+1690h+var_1658]
0x18000f704  mov     [rsp+1690h+var_165C], 4
0x18000f70c  xor     r8d, r8d; lpReserved
0x18000f70f  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f714  lea     rdx, aHavekeytablesc; "HaveKeyTableScore"
0x18000f71b  call    cs:__imp_RegQueryValueExW
0x18000f721  mov     r8d, [rsp+1690h+cbData]; unsigned int
0x18000f726  test    r8d, r8d
0x18000f729  jz      short loc_18000F740
0x18000f72b  mov     r9d, dword ptr [rsp+1690h+var_1658]; int
0x18000f730  lea     rdx, [rbp+1590h+Data]; unsigned __int8 *
0x18000f737  lea     rcx, [rbx+8]; this
0x18000f73b  call    ?BuildTable@CFuzzyTable@mtf@ipx@@QEAAJPEBEKH@Z; ipx::mtf::CFuzzyTable::BuildTable(uchar const *,ulong,int)
0x18000f740  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f745  lea     rax, [rsp+1690h+cbData]
0x18000f74a  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f74f  lea     r9, [rsp+1690h+Type]; lpType
0x18000f754  lea     rax, [rbp+1590h+Data]
0x18000f75b  mov     [rsp+1690h+cbData], 9C4h
0x18000f763  xor     r8d, r8d; lpReserved
0x18000f766  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f76b  lea     rdx, aAccenttable; "AccentTable"
0x18000f772  call    cs:__imp_RegQueryValueExW
0x18000f778  test    eax, eax
0x18000f77a  jnz     short loc_18000F7D1
0x18000f77c  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f781  lea     rax, [rsp+1690h+var_165C]
0x18000f786  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f78b  lea     r9, [rsp+1690h+var_1648]; lpType
0x18000f790  lea     rax, [rsp+1690h+var_1658]
0x18000f795  mov     [rsp+1690h+var_165C], 4
0x18000f79d  xor     r8d, r8d; lpReserved
0x18000f7a0  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f7a5  lea     rdx, aHaveaccenttabl; "HaveAccentTableScore"
0x18000f7ac  call    cs:__imp_RegQueryValueExW
0x18000f7b2  mov     r8d, [rsp+1690h+cbData]; unsigned int
0x18000f7b7  test    r8d, r8d
0x18000f7ba  jz      short loc_18000F7D1
0x18000f7bc  mov     r9d, dword ptr [rsp+1690h+var_1658]; int
0x18000f7c1  lea     rdx, [rbp+1590h+Data]; unsigned __int8 *
0x18000f7c8  lea     rcx, [rbx+30h]; this
0x18000f7cc  call    ?BuildTable@CFuzzyTable@mtf@ipx@@QEAAJPEBEKH@Z; ipx::mtf::CFuzzyTable::BuildTable(uchar const *,ulong,int)
0x18000f7d1  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f7d6  lea     rax, [rsp+1690h+cbData]
0x18000f7db  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f7e0  lea     r9, [rsp+1690h+Type]; lpType
0x18000f7e5  lea     rax, [rsp+1690h+var_1640]
0x18000f7ea  mov     [rsp+1690h+cbData], 14h
0x18000f7f2  mov     esi, 1
0x18000f7f7  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f7fc  xor     r8d, r8d; lpReserved
0x18000f7ff  mov     [rsp+1690h+Type], esi
0x18000f803  lea     rdx, aSymbolstoinser; "SymbolsToInsert"
0x18000f80a  call    cs:__imp_RegQueryValueExW
0x18000f810  test    eax, eax
0x18000f812  jnz     short loc_18000F83F
0x18000f814  cmp     [rsp+1690h+cbData], eax
0x18000f818  jbe     short loc_18000F83F
0x18000f81a  lea     rcx, [rsp+1690h+var_1640]; psz
0x18000f81f  call    cs:__imp_SysAllocString
0x18000f825  mov     rcx, rax; pbstr
0x18000f828  mov     [rbx+0A8h], rax
0x18000f82f  call    cs:__imp_SysStringLen
0x18000f835  test    eax, eax
0x18000f837  mov     ecx, 8007000Eh
0x18000f83c  cmovz   edi, ecx
0x18000f83f  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f844  lea     rax, [rsp+1690h+cbData]
0x18000f849  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f84e  lea     r9, [rsp+1690h+Type]; lpType
0x18000f853  lea     rax, [rbp+1590h+Data]
0x18000f85a  mov     ebx, 9C4h
0x18000f85f  xor     r8d, r8d; lpReserved
0x18000f862  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f867  lea     rdx, aHiraganafuzzyt; "HiraganaFuzzyTable"
0x18000f86e  mov     [rsp+1690h+cbData], ebx
0x18000f872  call    cs:__imp_RegQueryValueExW
0x18000f878  test    eax, eax
0x18000f87a  jnz     short loc_18000F8D0
0x18000f87c  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f881  lea     rax, [rsp+1690h+var_165C]
0x18000f886  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f88b  lea     r9, [rsp+1690h+var_1648]; lpType
0x18000f890  lea     rax, [rsp+1690h+var_1658]
0x18000f895  mov     [rsp+1690h+var_165C], 4
0x18000f89d  xor     r8d, r8d; lpReserved
0x18000f8a0  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f8a5  lea     rdx, aHavehiraganasc; "HaveHiraganaScore"
0x18000f8ac  call    cs:__imp_RegQueryValueExW
0x18000f8b2  mov     r8d, [rsp+1690h+cbData]; unsigned int
0x18000f8b7  test    r8d, r8d
0x18000f8ba  jz      short loc_18000F8D0
0x18000f8bc  mov     r9d, dword ptr [rsp+1690h+var_1658]; int
0x18000f8c1  lea     rdx, [rbp+1590h+Data]; unsigned __int8 *
0x18000f8c8  mov     rcx, r15; this
0x18000f8cb  call    ?BuildTable@CFuzzyHiraganaTable@mtf@ipx@@QEAAJPEBEKH@Z; ipx::mtf::CFuzzyHiraganaTable::BuildTable(uchar const *,ulong,int)
0x18000f8d0  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f8d5  lea     rax, [rsp+1690h+cbData]
0x18000f8da  mov     [rsp+1690h+lpcbData], rax; lpcbData
0x18000f8df  lea     r9, [rsp+1690h+Type]; lpType
0x18000f8e4  lea     rax, [rbp+1590h+Data]
0x18000f8eb  mov     [rsp+1690h+cbData], ebx
0x18000f8ef  xor     r8d, r8d; lpReserved
0x18000f8f2  mov     [rsp+1690h+phkResult], rax; lpData
0x18000f8f7  lea     rdx, aRomajifuzzytab; "RomajiFuzzyTable"
0x18000f8fe  call    cs:__imp_RegQueryValueExW
0x18000f904  test    eax, eax
0x18000f906  jnz     short loc_18000F924
0x18000f908  mov     r8d, [rsp+1690h+cbData]; unsigned int
0x18000f90d  test    r8d, r8d
0x18000f910  jz      short loc_18000F924
0x18000f912  mov     r9d, esi; int
0x18000f915  lea     rdx, [rbp+1590h+Data]; unsigned __int8 *
0x18000f91c  mov     rcx, r12; this
0x18000f91f  call    ?BuildTable@CFuzzyHiraganaTable@mtf@ipx@@QEAAJPEBEKH@Z; ipx::mtf::CFuzzyHiraganaTable::BuildTable(uchar const *,ulong,int)
0x18000f924  mov     rcx, [rsp+1690h+hKey]; hKey
0x18000f929  call    cs:__imp_RegCloseKey
0x18000f92f  mov     eax, edi
0x18000f931  mov     rcx, [rbp+1590h+var_30]
0x18000f938  xor     rcx, rsp; StackCookie
0x18000f93b  call    __security_check_cookie
0x18000f940  lea     r11, [rsp+1690h+var_20]
0x18000f948  mov     rbx, [r11+40h]
0x18000f94c  mov     rsi, [r11+48h]
0x18000f950  mov     rsp, r11
0x18000f953  pop     r15
0x18000f955  pop     r14
0x18000f957  pop     r12
0x18000f959  pop     rdi
0x18000f95a  pop     rbp
0x18000f95b  retn
```
