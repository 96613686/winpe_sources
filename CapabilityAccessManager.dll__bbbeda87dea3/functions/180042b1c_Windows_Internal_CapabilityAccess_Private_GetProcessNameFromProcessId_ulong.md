# Windows::Internal::CapabilityAccess::Private::GetProcessNameFromProcessId(ulong)

- ea: `0x180042b1c`
- end: `0x180042c44`
- name: `?GetProcessNameFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z`
- size: `296`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18007a804`
- `0x18007af9c`
- `0x180092eec`

## callees

- `0x1800094c0`
- `0x18001c3b4`
- `0x180029408`
- `0x18002f93c`
- `0x180039e9c`
- `0x18003f2d8`
- `0x18003f4a0`
- `0x180042b1c`
- `0x1800463e4`
- `0x1800465b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042b54`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180042b54`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180042bb2`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessImageFileNameW` at `0x180042bb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::GetProcessNameFromProcessId(__int64 a1, DWORD a2)
{
  HANDLE v3; // rbx
  const char *v4; // r9
  WCHAR *v5; // rax
  const char *v6; // r9
  unsigned __int64 last_of; // r8
  __int64 v8; // rax
  _QWORD v10[2]; // [rsp+28h] [rbp-40h] BYREF
  _BYTE v11[32]; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v10[1] = a1;
  v3 = OpenProcess(0x1000u, 0, a2);
  v10[0] = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2AA,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v4);
  std::wstring::wstring(a1, 260);
  v5 = (WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  if ( !K32GetProcessImageFileNameW(v3, v5, 0x104u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2AE,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v6);
  last_of = std::wstring::find_last_of(a1);
  if ( last_of != -1 && last_of < *(_QWORD *)(a1 + 16) - 1LL )
  {
    v8 = std::wstring::substr(a1, v11, last_of + 1, -1);
    std::wstring::operator=(a1, v8);
    std::wstring::_Tidy_deallocate(v11);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v10);
  return a1;
}

```

## disassembly

```asm
0x180042b1c  mov     [rsp+arg_10], rbx
0x180042b21  mov     [rsp+arg_18], rsi
0x180042b26  push    rdi
0x180042b27  sub     rsp, 60h
0x180042b2b  mov     rax, cs:__security_cookie
0x180042b32  xor     rax, rsp
0x180042b35  mov     [rsp+68h+var_10], rax
0x180042b3a  mov     rdi, rcx
0x180042b3d  mov     [rsp+68h+var_38], rcx
0x180042b42  mov     [rsp+68h+var_48], 0
0x180042b4a  mov     r8d, edx; dwProcessId
0x180042b4d  xor     edx, edx; bInheritHandle
0x180042b4f  mov     ecx, 1000h; dwDesiredAccess
0x180042b54  call    cs:__imp_OpenProcess
0x180042b5a  mov     rbx, rax
0x180042b5d  mov     [rsp+68h+var_40], rax
0x180042b62  mov     rcx, [rsp+68h]; this
0x180042b67  inc     rax
0x180042b6a  test    rax, 0FFFFFFFFFFFFFFFEh
0x180042b70  jnz     short loc_180042B84
0x180042b72  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042b79  mov     edx, 2AAh; void *
0x180042b7e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042b84  mov     edx, 104h
0x180042b89  mov     rcx, rdi
0x180042b8c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@_KG@Z; std::wstring::wstring(unsigned __int64,ushort)
0x180042b91  mov     [rsp+68h+var_48], 1
0x180042b99  mov     rcx, rdi
0x180042b9c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180042ba1  mov     rsi, [rsp+68h]
0x180042ba6  mov     r8d, 104h; nSize
0x180042bac  mov     rdx, rax; lpImageFileName
0x180042baf  mov     rcx, rbx; hProcess
0x180042bb2  call    cs:__imp_K32GetProcessImageFileNameW
0x180042bb8  test    eax, eax
0x180042bba  jnz     short loc_180042BD1
0x180042bbc  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x180042bc3  mov     edx, 2AEh; void *
0x180042bc8  mov     rcx, rsi; this
0x180042bcb  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180042bd1  mov     rcx, rdi
0x180042bd4  call    ?find_last_of@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find_last_of(ushort,unsigned __int64)
0x180042bd9  mov     r8, rax
0x180042bdc  or      r9, 0FFFFFFFFFFFFFFFFh
0x180042be0  cmp     rax, r9
0x180042be3  jz      short loc_180042C17
0x180042be5  mov     rax, [rdi+10h]
0x180042be9  dec     rax
0x180042bec  cmp     r8, rax
0x180042bef  jnb     short loc_180042C17
0x180042bf1  inc     r8
0x180042bf4  lea     rdx, [rsp+68h+var_30]
0x180042bf9  mov     rcx, rdi
0x180042bfc  call    ?substr@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180042c01  mov     rdx, rax
0x180042c04  mov     rcx, rdi
0x180042c07  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180042c0c  lea     rcx, [rsp+68h+var_30]
0x180042c11  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180042c16  nop
0x180042c17  lea     rcx, [rsp+68h+var_40]
0x180042c1c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042c21  mov     rax, rdi
0x180042c24  mov     rcx, [rsp+68h+var_10]
0x180042c29  xor     rcx, rsp; StackCookie
0x180042c2c  call    __security_check_cookie
0x180042c31  lea     r11, [rsp+68h+var_8]
0x180042c36  mov     rbx, [r11+20h]
0x180042c3a  mov     rsi, [r11+28h]
0x180042c3e  mov     rsp, r11
0x180042c41  pop     rdi
0x180042c42  retn
```
