# Windows::Registry::SetSystemVolatileKey(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x180023730`
- end: `0x180023829`
- name: `?SetSystemVolatileKey@Registry@Windows@@UEAAXV?$basic_zstring_view@_W@wil@@0@Z`
- size: `249`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task`

## callees

- `0x180009380`
- `0x180023730`
- `0x18003c020`
- `0x18003df70`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023804`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023804`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800237bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800237bd`

## string_xrefs

- `0x1800237e9`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Windows::Registry::SetSystemVolatileKey(__int64 a1, __int128 *a2, __int128 *a3)
{
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  LPCWSTR *v5; // rdx
  __int128 v6; // [rsp+50h] [rbp+7h] BYREF
  __int128 v7; // [rsp+60h] [rbp+17h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+27h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+78h] [rbp+2Fh] BYREF
  unsigned __int64 v10; // [rsp+90h] [rbp+47h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v6 = *a3;
  v7 = *a2;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v7, &v6);
  hKey = 0;
  v3 = (const WCHAR *)lpSubKey;
  if ( v10 > 7 )
    v3 = lpSubKey[0];
  v4 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0, 1u, 0x2001Fu, 0, &hKey, 0);
  v5 = lpSubKey;
  if ( v10 > 7 )
    v5 = (LPCWSTR *)lpSubKey[0];
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x112,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
    (const char *)v4,
    (unsigned int)"%ws",
    (const char *)v5);
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
}

```

## disassembly

```asm
0x180023730  push    rbp
0x180023732  lea     rbp, [rsp-57h]
0x180023737  sub     rsp, 0A0h
0x18002373e  mov     rax, cs:__security_cookie
0x180023745  xor     rax, rsp
0x180023748  mov     [rbp+57h+var_8], rax
0x18002374c  movups  xmm0, xmmword ptr [r8]
0x180023750  movdqu  [rbp+57h+var_50], xmm0
0x180023755  movups  xmm1, xmmword ptr [rdx]
0x180023758  movdqu  [rbp+57h+var_40], xmm1
0x18002375d  lea     r9, [rbp+57h+var_50]
0x180023761  lea     r8, [rbp+57h+var_40]
0x180023765  lea     rdx, [rbp+57h+lpSubKey]
0x180023769  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18002376e  nop
0x18002376f  mov     [rbp+57h+hKey], 0
0x180023777  lea     rdx, [rbp+57h+lpSubKey]
0x18002377b  cmp     [rbp+57h+var_10], 7
0x180023780  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180023785  mov     [rsp+0A0h+lpdwDisposition], 0; lpdwDisposition
0x18002378e  lea     rax, [rbp+57h+hKey]
0x180023792  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180023797  mov     [rsp+0A0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800237a0  mov     [rsp+0A0h+samDesired], 2001Fh; samDesired
0x1800237a8  mov     [rsp+0A0h+dwOptions], 1; dwOptions
0x1800237b0  xor     r9d, r9d; lpClass
0x1800237b3  xor     r8d, r8d; Reserved
0x1800237b6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800237bd  call    cs:__imp_RegCreateKeyExW
0x1800237c3  lea     rdx, [rbp+57h+lpSubKey]
0x1800237c7  cmp     [rbp+57h+var_10], 7
0x1800237cc  cmova   rdx, [rbp+57h+lpSubKey]
0x1800237d1  mov     rcx, [rbp+5Fh]; this
0x1800237d5  mov     qword ptr [rsp+0A0h+samDesired], rdx; char *
0x1800237da  lea     rdx, aWs; "%ws"
0x1800237e1  mov     qword ptr [rsp+0A0h+dwOptions], rdx; unsigned int
0x1800237e6  mov     r9d, eax; char *
0x1800237e9  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800237f0  mov     edx, 112h; void *
0x1800237f5  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800237fa  nop
0x1800237fb  mov     rcx, [rbp+57h+hKey]; hKey
0x1800237ff  test    rcx, rcx
0x180023802  jz      short loc_18002380B
0x180023804  call    cs:__imp_RegCloseKey
0x18002380a  nop
0x18002380b  lea     rcx, [rbp+57h+lpSubKey]; void *
0x18002380f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180023814  mov     rcx, [rbp+57h+var_8]
0x180023818  xor     rcx, rsp; StackCookie
0x18002381b  call    __security_check_cookie
0x180023820  add     rsp, 0A0h
0x180023827  pop     rbp
0x180023828  retn
```
