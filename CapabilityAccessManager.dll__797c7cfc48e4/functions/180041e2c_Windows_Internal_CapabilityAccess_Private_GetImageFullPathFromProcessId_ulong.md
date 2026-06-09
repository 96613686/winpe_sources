# Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(ulong)

- ea: `0x180041e2c`
- end: `0x180041f25`
- name: `?GetImageFullPathFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `249`
- prototype: ``
- caller_count: `12`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180064304`
- `0x180067a38`
- `0x18006874c`
- `0x18006ae88`
- `0x18006cbe4`
- `0x18006f230`
- `0x1800bf27c`
- `0x1800bf36f`
- `0x1800bf479`
- `0x1800bf5e3`
- `0x1800bf9d1`
- `0x1800bfae6`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x18001649c`
- `0x180039e9c`
- `0x18003f4a0`
- `0x180041e2c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180041e62`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180041e62`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180041ec6`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180041ec6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(__int64 a1, DWORD a2)
{
  HANDLE v3; // rbx
  const char *v4; // r9
  const char *v5; // r9
  DWORD dwSize; // [rsp+20h] [rbp-248h] BYREF
  HANDLE v8[3]; // [rsp+28h] [rbp-240h] BYREF
  WCHAR ExeName[264]; // [rsp+40h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  v3 = OpenProcess(0x1000u, 0, a2);
  v8[0] = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1C1,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  memset_0(ExeName, 0, 0x208u);
  dwSize = 260;
  if ( !QueryFullProcessImageNameW(v3, 0, ExeName, &dwSize) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CA,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v5);
  std::wstring::wstring(a1, ExeName);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v8);
  return a1;
}

```

## disassembly

```asm
0x180041e2c  mov     [rsp+arg_10], rbx
0x180041e31  mov     [rsp+arg_18], rsi
0x180041e36  push    rdi
0x180041e37  sub     rsp, 260h
0x180041e3e  mov     rax, cs:__security_cookie
0x180041e45  xor     rax, rsp
0x180041e48  mov     [rsp+268h+var_18], rax
0x180041e50  mov     rdi, rcx
0x180041e53  mov     [rsp+268h+var_240], rcx
0x180041e58  mov     r8d, edx; dwProcessId
0x180041e5b  xor     edx, edx; bInheritHandle
0x180041e5d  mov     ecx, 1000h; dwDesiredAccess
0x180041e62  call    cs:__imp_OpenProcess
0x180041e68  mov     rbx, rax
0x180041e6b  mov     [rsp+268h+var_240], rax
0x180041e70  inc     rax
0x180041e73  test    rax, 0FFFFFFFFFFFFFFFEh
0x180041e79  jnz     short loc_180041E95
0x180041e7b  mov     rcx, [rsp+268h]; this
0x180041e83  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041e8a  mov     edx, 1C1h; void *
0x180041e8f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180041e95  xor     edx, edx; Val
0x180041e97  mov     r8d, 208h; Size
0x180041e9d  lea     rcx, [rsp+268h+ExeName]; void *
0x180041ea2  call    memset_0
0x180041ea7  mov     [rsp+268h+dwSize], 104h
0x180041eaf  mov     rsi, [rsp+268h]
0x180041eb7  lea     r9, [rsp+268h+dwSize]; lpdwSize
0x180041ebc  lea     r8, [rsp+268h+ExeName]; lpExeName
0x180041ec1  xor     edx, edx; dwFlags
0x180041ec3  mov     rcx, rbx; hProcess
0x180041ec6  call    cs:__imp_QueryFullProcessImageNameW
0x180041ecc  test    eax, eax
0x180041ece  jnz     short loc_180041EE5
0x180041ed0  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180041ed7  mov     edx, 1CAh; void *
0x180041edc  mov     rcx, rsi; this
0x180041edf  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180041ee5  lea     rdx, [rsp+268h+ExeName]
0x180041eea  mov     rcx, rdi
0x180041eed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180041ef2  nop
0x180041ef3  lea     rcx, [rsp+268h+var_240]
0x180041ef8  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180041efd  mov     rax, rdi
0x180041f00  mov     rcx, [rsp+268h+var_18]
0x180041f08  xor     rcx, rsp; StackCookie
0x180041f0b  call    __security_check_cookie
0x180041f10  lea     r11, [rsp+268h+var_8]
0x180041f18  mov     rbx, [r11+20h]
0x180041f1c  mov     rsi, [r11+28h]
0x180041f20  mov     rsp, r11
0x180041f23  pop     rdi
0x180041f24  retn
```
