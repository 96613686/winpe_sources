# PackageEnroller::GetPackageIdFromEnrollmentId(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x1800b4b04`
- end: `0x1800b4d71`
- name: `?GetPackageIdFromEnrollmentId@PackageEnroller@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@@Z`
- size: `621`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ae8c0`

## callees

- `0x180016698`
- `0x180017078`
- `0x180017118`
- `0x180020970`
- `0x18003973c`
- `0x18003e5d4`
- `0x18007a7a0`
- `0x18007b580`
- `0x18007b8e8`
- `0x1800ac230`
- `0x1800af4cc`
- `0x1800b4b04`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4cf8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4cf8`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b4ccc`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800b4ccc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b4bf8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800b4bf8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b4b84`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800b4b84`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PackageEnroller::GetPackageIdFromEnrollmentId(__int64 a1, __int64 a2)
{
  bool IsStateSeparationEnabled; // al
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax
  DWORD v7; // r8d
  DWORD v8; // edx
  DWORD v9; // eax
  const char *v10; // r9
  DWORD i; // ebx
  unsigned int v12; // eax
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
  v4 = L"OSData\\SOFTWARE\\Microsoft\\Provisioning\\Enrollments";
  if ( !IsStateSeparationEnabled )
    v4 = L"SOFTWARE\\Microsoft\\Provisioning\\Enrollments";
  v5 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0, 0, 0x20019u, 0, &hKey, 0);
  if ( v5 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)v5,
      dwOptions);
  cbMaxValueNameLen = 0;
  cbMaxValueLen = 0;
  cValues = 0;
  v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
  if ( v6 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0x42,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      (const char *)v6,
      dwOptionsa);
  v7 = cbMaxValueNameLen;
  v8 = cbMaxValueNameLen + 1;
  v9 = -1;
  if ( cbMaxValueNameLen + 1 >= cbMaxValueNameLen )
    v9 = cbMaxValueNameLen + 1;
  v10 = v8 < cbMaxValueNameLen ? (const char *)0x80070216LL : 0LL;
  cbMaxValueNameLen = v9;
  if ( v8 < v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x45,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
      v10,
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
    v12 = RegEnumValueW(hKey, i, lpValueName[0], &cchValueName, 0, &Type, lpData[0], &cbData);
    if ( v12 == 259 )
      break;
    if ( v12 )
      wil::details::in1diag3::_Throw_Win32(
        retaddr,
        (void *)0x5F,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packageenroller.cpp",
        (const char *)v12,
        dwOptionsb);
    if ( Type == 1 && (unsigned int)_o__wcsicmp(lpData[0], &word_1800D5B40) )
    {
      std::wstring::operator=(a2, lpValueName[0]);
      goto LABEL_20;
    }
  }
  std::wstring::operator=(a2);
LABEL_20:
  std::vector<unsigned short>::_Tidy(lpData);
  std::vector<unsigned short>::_Tidy(lpValueName);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800b4b04  mov     [rsp-8+arg_0], rbx
0x1800b4b09  mov     [rsp-8+arg_8], rsi
0x1800b4b0e  push    rbp
0x1800b4b0f  push    rdi
0x1800b4b10  push    r14
0x1800b4b12  lea     rbp, [rsp-47h]
0x1800b4b17  sub     rsp, 0B0h
0x1800b4b1e  mov     rdi, rdx
0x1800b4b21  mov     rsi, rcx
0x1800b4b24  mov     rcx, rdx
0x1800b4b27  call    ?_Eos@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAX_K@Z; std::wstring::_Eos(unsigned __int64)
0x1800b4b2c  xor     r14d, r14d
0x1800b4b2f  mov     [rbp+57h+hKey], r14
0x1800b4b33  xor     edx, edx
0x1800b4b35  lea     rcx, [rbp+57h+hKey]
0x1800b4b39  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800b4b3e  call    ?ProvIsStateSeparationEnabled@@YA_NXZ; ProvIsStateSeparationEnabled(void)
0x1800b4b43  lea     rcx, aSoftwareMicros_15; "SOFTWARE\\Microsoft\\Provisioning\\Enro"...
0x1800b4b4a  lea     rdx, aOsdataSoftware_0; "OSData\\SOFTWARE\\Microsoft\\Provisioni"...
0x1800b4b51  test    al, al
0x1800b4b53  cmovz   rdx, rcx; lpSubKey
0x1800b4b57  mov     [rsp+0C0h+lpdwDisposition], r14; lpdwDisposition
0x1800b4b5c  lea     rax, [rbp+57h+hKey]
0x1800b4b60  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800b4b65  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800b4b6a  mov     [rsp+0C0h+samDesired], 20019h; samDesired
0x1800b4b72  mov     [rsp+0C0h+dwOptions], r14d; unsigned int
0x1800b4b77  xor     r9d, r9d; lpClass
0x1800b4b7a  xor     r8d, r8d; Reserved
0x1800b4b7d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b4b84  call    cs:__imp_RegCreateKeyExW
0x1800b4b8b  nop     dword ptr [rax+rax+00h]
0x1800b4b90  mov     rcx, [rbp+5Fh]; this
0x1800b4b94  test    eax, eax
0x1800b4b96  jz      short loc_1800B4BAC
0x1800b4b98  mov     r9d, eax; char *
0x1800b4b9b  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b4ba2  lea     edx, [r14+3Bh]; void *
0x1800b4ba6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b4bac  mov     [rbp+57h+cbMaxValueNameLen], r14d
0x1800b4bb0  mov     [rbp+57h+cbMaxValueLen], r14d
0x1800b4bb4  mov     [rbp+57h+cValues], r14d
0x1800b4bb8  mov     [rsp+0C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800b4bbd  mov     [rsp+0C0h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x1800b4bc2  lea     rax, [rbp+57h+cbMaxValueLen]
0x1800b4bc6  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800b4bcb  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x1800b4bcf  mov     [rsp+0C0h+lpdwDisposition], rax; lpcbMaxValueNameLen
0x1800b4bd4  lea     rax, [rbp+57h+cValues]
0x1800b4bd8  mov     [rsp+0C0h+phkResult], rax; lpcValues
0x1800b4bdd  mov     [rsp+0C0h+lpSecurityAttributes], r14; lpcbMaxClassLen
0x1800b4be2  mov     qword ptr [rsp+0C0h+samDesired], r14; lpcbMaxSubKeyLen
0x1800b4be7  mov     qword ptr [rsp+0C0h+dwOptions], r14; int
0x1800b4bec  xor     r9d, r9d; lpReserved
0x1800b4bef  xor     r8d, r8d; lpcchClass
0x1800b4bf2  xor     edx, edx; lpClass
0x1800b4bf4  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b4bf8  call    cs:__imp_RegQueryInfoKeyW
0x1800b4bff  nop     dword ptr [rax+rax+00h]
0x1800b4c04  mov     rcx, [rbp+5Fh]; this
0x1800b4c08  test    eax, eax
0x1800b4c0a  jz      short loc_1800B4C21
0x1800b4c0c  mov     r9d, eax; char *
0x1800b4c0f  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b4c16  mov     edx, 42h ; 'B'; void *
0x1800b4c1b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b4c21  mov     r8d, [rbp+57h+cbMaxValueNameLen]
0x1800b4c25  lea     edx, [r8+1]
0x1800b4c29  or      eax, 0FFFFFFFFh
0x1800b4c2c  cmp     edx, r8d
0x1800b4c2f  cmovnb  eax, edx
0x1800b4c32  sbb     r9d, r9d
0x1800b4c35  and     r9d, 80070216h; char *
0x1800b4c3c  mov     [rbp+57h+cbMaxValueNameLen], eax
0x1800b4c3f  mov     rcx, [rbp+5Fh]; this
0x1800b4c43  cmp     edx, r8d
0x1800b4c46  jnb     short loc_1800B4C5A
0x1800b4c48  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b4c4f  mov     edx, 45h ; 'E'; void *
0x1800b4c54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b4c5a  lea     rcx, [rbp+57h+lpValueName]
0x1800b4c5e  call    ??0?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(void)
0x1800b4c63  nop
0x1800b4c64  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x1800b4c67  lea     rcx, [rbp+57h+lpValueName]
0x1800b4c6b  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800b4c70  lea     rcx, [rbp+57h+lpData]
0x1800b4c74  call    ??0?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::vector<std::vector<std::wstring>>(void)
0x1800b4c79  nop
0x1800b4c7a  mov     edx, [rbp+57h+cbMaxValueLen]
0x1800b4c7d  inc     edx
0x1800b4c7f  shr     rdx, 1
0x1800b4c82  lea     rcx, [rbp+57h+lpData]
0x1800b4c86  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x1800b4c8b  mov     ebx, r14d
0x1800b4c8e  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800b4c91  mov     [rbp+57h+cbData], eax
0x1800b4c94  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800b4c97  mov     [rbp+57h+cchValueName], eax
0x1800b4c9a  mov     [rbp+57h+Type], r14d
0x1800b4c9e  mov     rax, [rbp+57h+lpData]
0x1800b4ca2  lea     rcx, [rbp+57h+cbData]
0x1800b4ca6  mov     [rsp+0C0h+phkResult], rcx; lpcbData
0x1800b4cab  mov     [rsp+0C0h+lpSecurityAttributes], rax; lpData
0x1800b4cb0  lea     rax, [rbp+57h+Type]
0x1800b4cb4  mov     qword ptr [rsp+0C0h+samDesired], rax; lpType
0x1800b4cb9  mov     qword ptr [rsp+0C0h+dwOptions], r14; unsigned int
0x1800b4cbe  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800b4cc2  mov     r8, [rbp+57h+lpValueName]; lpValueName
0x1800b4cc6  mov     edx, ebx; dwIndex
0x1800b4cc8  mov     rcx, [rbp+57h+hKey]; hKey
0x1800b4ccc  call    cs:__imp_RegEnumValueW
0x1800b4cd3  nop     dword ptr [rax+rax+00h]
0x1800b4cd8  cmp     eax, 103h
0x1800b4cdd  jz      short loc_1800B4D2F
0x1800b4cdf  mov     rcx, [rbp+5Fh]; this
0x1800b4ce3  test    eax, eax
0x1800b4ce5  jnz     short loc_1800B4D1A
0x1800b4ce7  cmp     [rbp+57h+Type], 1
0x1800b4ceb  jnz     short loc_1800B4D08
0x1800b4ced  lea     rdx, word_1800D5B40
0x1800b4cf4  mov     rcx, [rbp+57h+lpData]
0x1800b4cf8  call    cs:__imp__o__wcsicmp
0x1800b4cff  nop     dword ptr [rax+rax+00h]
0x1800b4d04  test    eax, eax
0x1800b4d06  jnz     short loc_1800B4D0C
0x1800b4d08  inc     ebx
0x1800b4d0a  jmp     short loc_1800B4C8E
0x1800b4d0c  mov     rdx, [rbp+57h+lpValueName]
0x1800b4d10  mov     rcx, rdi
0x1800b4d13  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@QEBG@Z; std::wstring::operator=(ushort const * const)
0x1800b4d18  jmp     short loc_1800B4D3B
0x1800b4d1a  mov     r9d, eax; char *
0x1800b4d1d  lea     r8, aOnecoreuapAdmi_17; "onecoreuap\\admin\\prov\\lib\\packageen"...
0x1800b4d24  mov     edx, 5Fh ; '_'; void *
0x1800b4d29  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x1800b4d2f  mov     rdx, rsi
0x1800b4d32  mov     rcx, rdi
0x1800b4d35  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800b4d3a  nop
0x1800b4d3b  lea     rcx, [rbp+57h+lpData]
0x1800b4d3f  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b4d44  nop
0x1800b4d45  lea     rcx, [rbp+57h+lpValueName]
0x1800b4d49  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b4d4e  nop
0x1800b4d4f  lea     rcx, [rbp+57h+hKey]
0x1800b4d53  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800b4d58  lea     r11, [rsp+0C0h+var_10]
0x1800b4d60  mov     rbx, [r11+20h]
0x1800b4d64  mov     rsi, [r11+28h]
0x1800b4d68  mov     rsp, r11
0x1800b4d6b  pop     r14
0x1800b4d6d  pop     rdi
0x1800b4d6e  pop     rbp
0x1800b4d6f  retn
```
