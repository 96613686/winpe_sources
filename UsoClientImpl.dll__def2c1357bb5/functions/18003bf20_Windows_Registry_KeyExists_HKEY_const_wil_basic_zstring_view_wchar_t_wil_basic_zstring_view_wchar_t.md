# Windows::Registry::KeyExists(HKEY__ * const,wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)

- ea: `0x18003bf20`
- end: `0x18003c011`
- name: `?KeyExists@Registry@Windows@@QEAA_NQEAUHKEY__@@V?$basic_zstring_view@_W@wil@@1@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18000cde8`
- `0x180023830`

## callees

- `0x180009380`
- `0x18003bf20`
- `0x18003c020`
- `0x18003df70`
- `0x180056500`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bfe2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003bfe2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bf91`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003bf91`

## string_xrefs

- `0x18003bfc6`: `C:\__w\1\s\src\orchestrator\system\windows\servicesystem\Registry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Windows::Registry::KeyExists(__int64 a1, __int64 a2, __int128 *a3, __int128 *a4)
{
  const WCHAR *v4; // rdx
  unsigned int v5; // eax
  const char *v6; // r9
  char v7; // bl
  LPCWSTR *v8; // rax
  __int128 v10; // [rsp+30h] [rbp-50h] BYREF
  __int128 v11; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-30h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v14; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v10 = *a4;
  v11 = *a3;
  Windows::Registry::GetRedirectedRegistryKeyName(a1, lpSubKey, &v11, &v10);
  hKey = 0;
  v4 = (const WCHAR *)lpSubKey;
  if ( v14 > 7 )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = (const char *)v5;
  if ( v5 == 2 )
  {
    v7 = 0;
  }
  else
  {
    v8 = lpSubKey;
    if ( v14 > 7 )
      v8 = (LPCWSTR *)lpSubKey[0];
    wil::details::in1diag3::Throw_IfWin32ErrorMsg(
      retaddr,
      (void *)0xC7,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\servicesystem\\Registry.cpp",
      v6,
      (unsigned int)"%ws",
      (const char *)v8);
    v7 = 1;
  }
  if ( hKey )
    RegCloseKey(hKey);
  std::wstring::~wstring(lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x18003bf20  mov     [rsp-8+arg_0], rbx
0x18003bf25  push    rbp
0x18003bf26  mov     rbp, rsp
0x18003bf29  sub     rsp, 80h
0x18003bf30  mov     rax, cs:__security_cookie
0x18003bf37  xor     rax, rsp
0x18003bf3a  mov     [rbp+var_8], rax
0x18003bf3e  movaps  xmm0, xmmword ptr [r9]
0x18003bf42  movdqa  [rbp+var_50], xmm0
0x18003bf47  movaps  xmm1, xmmword ptr [r8]
0x18003bf4b  movdqa  [rbp+var_40], xmm1
0x18003bf50  lea     r9, [rbp+var_50]
0x18003bf54  lea     r8, [rbp+var_40]
0x18003bf58  lea     rdx, [rbp+lpSubKey]
0x18003bf5c  call    ?GetRedirectedRegistryKeyName@Registry@Windows@@UEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@0@Z; Windows::Registry::GetRedirectedRegistryKeyName(wil::basic_zstring_view<wchar_t>,wil::basic_zstring_view<wchar_t>)
0x18003bf61  nop
0x18003bf62  mov     [rbp+hKey], 0
0x18003bf6a  lea     rdx, [rbp+lpSubKey]
0x18003bf6e  cmp     [rbp+var_10], 7
0x18003bf73  cmova   rdx, [rbp+lpSubKey]; lpSubKey
0x18003bf78  lea     rax, [rbp+hKey]
0x18003bf7c  mov     [rsp+80h+phkResult], rax; phkResult
0x18003bf81  mov     r9d, 20019h; samDesired
0x18003bf87  xor     r8d, r8d; ulOptions
0x18003bf8a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003bf91  call    cs:__imp_RegOpenKeyExW
0x18003bf97  mov     r9d, eax; char *
0x18003bf9a  cmp     eax, 2
0x18003bf9d  jnz     short loc_18003BFA3
0x18003bf9f  xor     bl, bl
0x18003bfa1  jmp     short loc_18003BFD9
0x18003bfa3  lea     rax, [rbp+lpSubKey]
0x18003bfa7  cmp     [rbp+var_10], 7
0x18003bfac  cmova   rax, [rbp+lpSubKey]
0x18003bfb1  mov     rcx, [rbp+8]; this
0x18003bfb5  mov     [rsp+80h+var_58], rax; char *
0x18003bfba  lea     rax, aWs; "%ws"
0x18003bfc1  mov     [rsp+80h+phkResult], rax; unsigned int
0x18003bfc6  lea     r8, aCW1SSrcOrchest_2; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x18003bfcd  mov     edx, 0C7h; void *
0x18003bfd2  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003bfd7  mov     bl, 1
0x18003bfd9  mov     rcx, [rbp+hKey]; hKey
0x18003bfdd  test    rcx, rcx
0x18003bfe0  jz      short loc_18003BFE9
0x18003bfe2  call    cs:__imp_RegCloseKey
0x18003bfe8  nop
0x18003bfe9  lea     rcx, [rbp+lpSubKey]; void *
0x18003bfed  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003bff2  mov     al, bl
0x18003bff4  mov     rcx, [rbp+var_8]
0x18003bff8  xor     rcx, rsp; StackCookie
0x18003bffb  call    __security_check_cookie
0x18003c000  mov     rbx, [rsp+80h+arg_0]
0x18003c008  add     rsp, 80h
0x18003c00f  pop     rbp
0x18003c010  retn
```
