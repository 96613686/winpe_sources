# PackageEnroller::GetPackageIdFromEnrollmentId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800b1730`
- end: `0x1800b1984`
- name: `?GetPackageIdFromEnrollmentId@PackageEnroller@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ab7a4`

## callees

- `0x180015f70`
- `0x180016918`
- `0x1800169b8`
- `0x180022334`
- `0x18003a430`
- `0x18003ec00`
- `0x180078f9c`
- `0x180079d34`
- `0x18007a084`
- `0x1800a8d18`
- `0x1800ac350`
- `0x1800b1730`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b1912`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b1912`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b18ec`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b18ec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b17b0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b17b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b181e`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b181e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PackageEnroller::GetPackageIdFromEnrollmentId(__int64 a1, __int64 a2)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  unsigned int v7; // eax
  DWORD v8; // r8d
  DWORD v9; // edx
  DWORD v10; // eax
  const char *v11; // r9
  DWORD i; // ebx
  unsigned int v13; // eax
  unsigned int dwOptions; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-49h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-49h]
  HKEY hKey; // [rsp+60h] [rbp-9h] BYREF
  DWORD Type; // [rsp+68h] [rbp-1h] BYREF
  DWORD cValues; // [rsp+6Ch] [rbp+3h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+7h] BYREF
  DWORD cchValueName; // [rsp+74h] [rbp+Bh] BYREF
  LPBYTE lpData[3]; // [rsp+78h] [rbp+Fh] BYREF
  LPWSTR lpValueName[4]; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  DWORD cbMaxValueNameLen; // [rsp+E0h] [rbp+77h] BYREF
  DWORD cbMaxValueLen; // [rsp+E8h] [rbp+7Fh] BYREF

  std::wstring::_Eos(a2);
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  IsStateSeparationEnabled = ProvIsStateSeparationEnabled();
  v5 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Enrollments";
  if ( !IsStateSeparationEnabled )
    v5 = L"SOFTWARE\\Microsoft\\Provisioning\\Enrollments";
  v6 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0, 0, 0x20019u, 0, &hKey, 0);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)v6,
      dwOptions);
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  v7 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)v7,
      dwOptionsa);
  v8 = cbMaxValueNameLen;
  v9 = cbMaxValueNameLen + 1;
  v10 = -1;
  if ( cbMaxValueNameLen + 1 >= cbMaxValueNameLen )
    v10 = cbMaxValueNameLen + 1;
  v11 = v9 < cbMaxValueNameLen ? (const char *)0x80070216LL : 0LL;
  cbMaxValueNameLen = v10;
  if ( v9 < v8 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      v11,
      dwOptionsa);
  std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(lpValueName);
  std::vector<unsigned short>::resize(lpValueName, cbMaxValueNameLen);
  std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(lpData);
  std::vector<unsigned short>::resize(lpData, (unsigned __int64)(cbMaxValueLen + 1) >> 1);
  for ( i = 0; ; ++i )
  {
    cbData = cbMaxValueLen;
    cchValueName = cbMaxValueNameLen;
    Type = 0;
    v13 = RegEnumValueW(hKey, i, lpValueName[0], &cchValueName, 0, &Type, lpData[0], &cbData);
    if ( v13 == 259 )
      break;
    if ( v13 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
        (const char *)v13,
        dwOptionsb);
    if ( Type == 1 && (unsigned int)_o__wcsicmp(lpData[0], &word_1800D1BC0) )
    {
      std::wstring::operator=(a2, lpValueName[0]);
      goto LABEL_20;
    }
  }
  std::wstring::operator=(a2, a1);
LABEL_20:
  std::vector<unsigned short>::_Tidy(lpData);
  std::vector<unsigned short>::_Tidy(lpValueName);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800b1730  mov     [rsp-8+arg_0], rbx
0x1800b1735  mov     [rsp-8+arg_8], rsi
0x1800b173a  push    rbp
0x1800b173b  push    rdi
0x1800b173c  push    r14
0x1800b173e  lea     rbp, [rsp-47h]
0x1800b1743  sub     rsp, 0B0h
0x1800b174a  mov     rdi, rdx
0x1800b174d  mov     rsi, rcx
0x1800b1750  mov     rcx, rdx
0x1800b1753  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800b1758  xor     r14d, r14d
0x1800b175b  mov     [rbp+57h+hKey], r14
0x1800b175f  xor     edx, edx
0x1800b1761  lea     rcx, [rbp+57h+hKey]
0x1800b1765  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b176a  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800b176f  lea     rcx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Provisioning\\Enro"...
0x1800b1776  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800b177d  test    al, al
0x1800b177f  cmovz   rdx, rcx; lpSubKey
0x1800b1783  mov     [rsp+0C0h+lpdwDisposition], r14; lpdwDisposition
0x1800b1788  lea     rax, [rbp+57h+hKey]
0x1800b178c  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800b1791  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800b1796  mov     [rsp+0C0h+samDesired], 20019h; samDesired
0x1800b179e  mov     [rsp+0C0h+dwOptions], r14d; unsigned int
0x1800b17a3  xor     r9d, r9d; lpClass
0x1800b17a6  xor     r8d, r8d; Reserved
0x1800b17a9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b17b0  call    cs:__imp_RegCreateKeyExW
0x1800b17b6  mov     rcx, [rbp+5Fh]; this
0x1800b17ba  test    eax, eax
0x1800b17bc  jz      short loc_1800B17D2
0x1800b17be  mov     r9d, eax; char *
0x1800b17c1  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b17c8  lea     edx, [r14+3Bh]; void *
0x1800b17cc  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b17d2  mov     [rbp+57h+cbMaxValueNameLen], r14d
0x1800b17d6  mov     [rbp+57h+cbMaxValueLen], r14d
0x1800b17da  mov     [rbp+57h+cValues], r14d
0x1800b17de  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800b17e3  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800b17e8  lea     rax, [rbp+57h+cbMaxValueLen]
0x1800b17ec  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800b17f1  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800b17f5  mov     [rsp+0C0h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x1800b17fa  lea     rax, [rbp+57h+cValues]
0x1800b17fe  mov     [rsp+0C0h+phkResult], rax; lpcValues
0x1800b1803  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x1800b1808  mov     qword ptr [rsp+0C0h+samDesired], r14; lpcbMaxSubKeyLen
0x1800b180d  mov     qword ptr [rsp+0C0h+dwOptions], r14; int
0x1800b1812  xor     r9d, r9d; lpReserved
0x1800b1815  xor     r8d, r8d; lpcchClass
0x1800b1818  xor     edx, edx; lpClass
0x1800b181a  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b181e  call    cs:__imp_RegQueryInfoKeyW
0x1800b1824  mov     rcx, [rbp+5Fh]; this
0x1800b1828  test    eax, eax
0x1800b182a  jz      short loc_1800B1841
0x1800b182c  mov     r9d, eax; char *
0x1800b182f  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b1836  mov     edx, 42h ; 'B'; void *
0x1800b183b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b1841  mov     r8d, [rbp+57h+cbMaxValueNameLen]
0x1800b1845  lea     edx, [r8+1]
0x1800b1849  or      eax, 0FFFFFFFFh
0x1800b184c  cmp     edx, r8d
0x1800b184f  cmovnb  eax, edx
0x1800b1852  sbb     r9d, r9d
0x1800b1855  and     r9d, 80070216h; char *
0x1800b185c  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1800b185f  mov     rcx, [rbp+5Fh]; this
0x1800b1863  cmp     edx, r8d
0x1800b1866  jnb     short loc_1800B187A
0x1800b1868  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b186f  mov     edx, 45h ; 'E'; void *
0x1800b1874  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b187a  lea     rcx, [rbp+57h+lpValueName]
0x1800b187e  call    ??0?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(void)
0x1800b1883  nop
0x1800b1884  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x1800b1887  lea     rcx, [rbp+57h+lpValueName]
0x1800b188b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800b1890  lea     rcx, [rbp+57h+lpData]
0x1800b1894  call    ??0?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(void)
0x1800b1899  nop
0x1800b189a  mov     edx, [rbp+57h+cbMaxValueLen]
0x1800b189d  inc     edx
0x1800b189f  shr     rdx, 1
0x1800b18a2  lea     rcx, [rbp+57h+lpData]
0x1800b18a6  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800b18ab  mov     ebx, r14d
0x1800b18ae  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800b18b1  mov     [rbp+57h+cbData], eax
0x1800b18b4  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800b18b7  mov     [rbp+57h+cchValueName], eax
0x1800b18ba  mov     [rbp+57h+Type], r14d
0x1800b18be  mov     rax, [rbp+57h+lpData]
0x1800b18c2  lea     rcx, [rbp+57h+cbData]
0x1800b18c6  mov     [rsp+0C0h+phkResult], rcx; lpcbData
0x1800b18cb  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpData
0x1800b18d0  lea     rax, [rbp+57h+Type]
0x1800b18d4  mov     qword ptr [rsp+0C0h+samDesired], rax; lpType
0x1800b18d9  mov     qword ptr [rsp+0C0h+dwOptions], r14; unsigned int
0x1800b18de  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800b18e2  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x1800b18e6  mov     edx, ebx; dwIndex
0x1800b18e8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b18ec  call    cs:__imp_RegEnumValueW
0x1800b18f2  cmp     eax, 103h
0x1800b18f7  jz      short loc_1800B1943
0x1800b18f9  mov     rcx, [rbp+5Fh]; this
0x1800b18fd  test    eax, eax
0x1800b18ff  jnz     short loc_1800B192E
0x1800b1901  cmp     [rbp+57h+Type], 1
0x1800b1905  jnz     short loc_1800B191C
0x1800b1907  lea     rdx, word_1800D1BC0
0x1800b190e  mov     rcx, [rbp+57h+lpData]
0x1800b1912  call    cs:__imp__o__wcsicmp
0x1800b1918  test    eax, eax
0x1800b191a  jnz     short loc_1800B1920
0x1800b191c  inc     ebx
0x1800b191e  jmp     short loc_1800B18AE
0x1800b1920  mov     rdx, [rbp+57h+lpValueName]
0x1800b1924  mov     rcx, rdi
0x1800b1927  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800b192c  jmp     short loc_1800B194F
0x1800b192e  mov     r9d, eax; char *
0x1800b1931  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b1938  mov     edx, 5Fh ; '_'; void *
0x1800b193d  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b1943  mov     rdx, rsi
0x1800b1946  mov     rcx, rdi
0x1800b1949  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800b194e  nop
0x1800b194f  lea     rcx, [rbp+57h+lpData]
0x1800b1953  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b1958  nop
0x1800b1959  lea     rcx, [rbp+57h+lpValueName]
0x1800b195d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b1962  nop
0x1800b1963  lea     rcx, [rbp+57h+hKey]
0x1800b1967  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b196c  lea     r11, [rsp+0C0h+var_10]
0x1800b1974  mov     rbx, [r11+20h]
0x1800b1978  mov     rsi, [r11+28h]
0x1800b197c  mov     rsp, r11
0x1800b197f  pop     r14
0x1800b1981  pop     rdi
0x1800b1982  pop     rbp
0x1800b1983  retn
```
