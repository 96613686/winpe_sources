# RetailDemoUtil::ExecuteAsDemoUser(std::function<void (void)> const &)

- ea: `0x18002fc68`
- end: `0x18002fd18`
- name: `?ExecuteAsDemoUser@RetailDemoUtil@@YAXAEBV?$function@$$A6AXXZ@std@@@Z`
- size: `176`
- prototype: ``
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800253f0`
- `0x1800258a0`
- `0x180025bc0`
- `0x1800263e0`
- `0x180026990`
- `0x180029b20`
- `0x18002c2f0`
- `0x18002c9d0`
- `0x180030f50`

## callees

- `0x1800033b4`
- `0x180014d04`
- `0x180022ad8`
- `0x18002fc68`
- `0x1800305b8`
- `0x180050010`

## import_xrefs

- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002fce8`
- `msvcp_win!?_Xbad_function_call@std@@YAXXZ` at `0x18002fce8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002fd00`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002fd00`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002fcb0`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18002fcb0`

## string_xrefs

- `0x18002fcbe`: `shellcommon\shell\retaildemo\include\RetailDemoUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall RetailDemoUtil::ExecuteAsDemoUser(__int64 a1, unsigned __int64 *a2)
{
  char *v3; // rbx
  HANDLE v4; // rcx
  const char *v5; // r9
  char v6; // bl
  __int64 v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  HANDLE hToken; // [rsp+60h] [rbp+30h] BYREF
  void *v11; // [rsp+68h] [rbp+38h] BYREF

  RetailDemoUtil::GetDemoUserToken(&v11, a2);
  hToken = v11;
  v11 = 0;
  v3 = (char *)operator new(1u);
  v4 = hToken;
  *v3 = 0;
  if ( !ImpersonateLoggedOnUser(v4) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x27,
      (unsigned int)"shellcommon\\shell\\retaildemo\\include\\RetailDemoUtil.h",
      v5);
  *v3 = 1;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  v6 = *v3;
  v7 = *(_QWORD *)(a1 + 56);
  if ( !v7 )
  {
    std::_Xbad_function_call();
    __debugbreak();
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  if ( v6 )
    RevertToSelf();
  return wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
}

```

## disassembly

```asm
0x18002fc68  push    rbp
0x18002fc6a  push    rbx
0x18002fc6b  push    rdi
0x18002fc6c  mov     rbp, rsp
0x18002fc6f  sub     rsp, 30h
0x18002fc73  mov     rdi, rcx
0x18002fc76  lea     rcx, [rbp+arg_18]
0x18002fc7a  call    ?GetDemoUserToken@RetailDemoUtil@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@XZ; RetailDemoUtil::GetDemoUserToken(void)
0x18002fc7f  nop
0x18002fc80  mov     rax, [rbp+arg_18]
0x18002fc84  mov     [rbp+hToken], rax
0x18002fc88  mov     [rbp+arg_18], 0
0x18002fc90  lea     rax, [rbp+hToken]
0x18002fc94  mov     [rbp+arg_8], rax
0x18002fc98  mov     ecx, 1; Size
0x18002fc9d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fca2  mov     rbx, rax
0x18002fca5  mov     [rbp+var_10], rax
0x18002fca9  mov     rcx, [rbp+hToken]; hToken
0x18002fcad  mov     byte ptr [rax], 0
0x18002fcb0  call    cs:__imp_ImpersonateLoggedOnUser
0x18002fcb6  mov     rcx, [rbp+18h]; this
0x18002fcba  test    eax, eax
0x18002fcbc  jnz     short loc_18002FCCE
0x18002fcbe  lea     r8, aShellcommonShe_1; "shellcommon\\shell\\retaildemo\\include"...
0x18002fcc5  lea     edx, [rax+27h]; void *
0x18002fcc8  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002fcce  mov     byte ptr [rbx], 1
0x18002fcd1  lea     rcx, [rbp+hToken]
0x18002fcd5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002fcda  mov     bl, [rbx]
0x18002fcdc  mov     byte ptr [rbp+arg_8], bl
0x18002fcdf  mov     rcx, [rdi+38h]
0x18002fce3  test    rcx, rcx
0x18002fce6  jnz     short loc_18002FCEF
0x18002fce8  call    cs:__imp_?_Xbad_function_call@std@@YAXXZ; std::_Xbad_function_call(void)
0x18002fcee  int     3; Trap to Debugger
0x18002fcef  mov     rax, [rcx]
0x18002fcf2  mov     rax, [rax+10h]
0x18002fcf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fcfb  nop
0x18002fcfc  test    bl, bl
0x18002fcfe  jz      short loc_18002FD07
0x18002fd00  call    cs:__imp_RevertToSelf
0x18002fd06  nop
0x18002fd07  lea     rcx, [rbp+arg_18]
0x18002fd0b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002fd10  add     rsp, 30h
0x18002fd14  pop     rdi
0x18002fd15  pop     rbx
0x18002fd16  pop     rbp
0x18002fd17  retn
```
