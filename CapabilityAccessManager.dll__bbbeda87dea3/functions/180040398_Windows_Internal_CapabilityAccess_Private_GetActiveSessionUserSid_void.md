# Windows::Internal::CapabilityAccess::Private::GetActiveSessionUserSid(void)

- ea: `0x180040398`
- end: `0x18004044c`
- name: `?GetActiveSessionUserSid@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180040454`

## callees

- `0x18002392c`
- `0x180039e9c`
- `0x18003f4a0`
- `0x180040398`
- `0x18004338c`
- `0x1800464d0`

## import_xrefs

- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x1800403f2`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x1800403f2`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1800403b7`
- `ext-ms-win-session-usertoken-l1-1-0!QueryActiveSession` at `0x1800403b7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::GetActiveSessionUserSid(_QWORD *a1)
{
  const char *v2; // r9
  int SessionActiveShellUserToken; // eax
  int v5; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  unsigned int v7; // [rsp+48h] [rbp+10h] BYREF
  HANDLE v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = 0;
  if ( !(unsigned int)QueryActiveSession(&v7) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x74,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
      v2);
  v8 = 0;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v8,
    0);
  SessionActiveShellUserToken = UMgrGetSessionActiveShellUserToken(v7, &v8);
  if ( SessionActiveShellUserToken == -2147023584 )
  {
    *a1 = 0;
  }
  else
  {
    if ( SessionActiveShellUserToken < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\clienthelpers.cpp",
        (const char *)(unsigned int)SessionActiveShellUserToken,
        v5);
    Windows::Internal::CapabilityAccess::Private::GetUserSidFromToken(a1, &v8);
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v8);
  return a1;
}

```

## disassembly

```asm
0x180040398  mov     [rsp+arg_0], rbx
0x18004039d  push    rdi
0x18004039e  sub     rsp, 30h
0x1800403a2  mov     rbx, rcx
0x1800403a5  mov     [rsp+38h+arg_8], 0
0x1800403ad  mov     rdi, [rsp+38h]
0x1800403b2  lea     rcx, [rsp+38h+arg_8]
0x1800403b7  call    cs:__imp_QueryActiveSession
0x1800403bd  test    eax, eax
0x1800403bf  jnz     short loc_1800403D4
0x1800403c1  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x1800403c8  lea     edx, [rax+74h]; void *
0x1800403cb  mov     rcx, rdi; this
0x1800403ce  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800403d4  mov     [rsp+38h+arg_10], 0
0x1800403dd  xor     edx, edx
0x1800403df  lea     rcx, [rsp+38h+arg_10]
0x1800403e4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800403e9  lea     rdx, [rsp+38h+arg_10]
0x1800403ee  mov     ecx, [rsp+38h+arg_8]
0x1800403f2  call    cs:__imp_UMgrGetSessionActiveShellUserToken
0x1800403f8  cmp     eax, 80070520h
0x1800403fd  jnz     short loc_180040408
0x1800403ff  mov     qword ptr [rbx], 0
0x180040406  jmp     short loc_180040434
0x180040408  mov     rcx, [rsp+38h]; this
0x18004040d  test    eax, eax
0x18004040f  jns     short loc_180040426
0x180040411  mov     r9d, eax; char *
0x180040414  lea     r8, aOnecoreBaseDev_39; "onecore\\base\\devices\\cam\\core\\clie"...
0x18004041b  mov     edx, 7Dh ; '}'; void *
0x180040420  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180040426  lea     rdx, [rsp+38h+arg_10]
0x18004042b  mov     rcx, rbx
0x18004042e  call    ?GetUserSidFromToken@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@6@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidFromToken(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180040433  nop
0x180040434  lea     rcx, [rsp+38h+arg_10]
0x180040439  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18004043e  mov     rax, rbx
0x180040441  mov     rbx, [rsp+38h+arg_0]
0x180040446  add     rsp, 30h
0x18004044a  pop     rdi
0x18004044b  retn
```
