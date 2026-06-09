# ll_open_persisted_policy_key(ulong)

- ea: `0x180232d3c`
- end: `0x180232e32`
- name: `?ll_open_persisted_policy_key@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@K@Z`
- size: `246`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1802321cc`

## callees

- `0x1800663fc`
- `0x18007cbc8`
- `0x180232d3c`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180232d95`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x180232d95`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180232d69`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x180232d69`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180232dd9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180232de3`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180232dd9`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x180232de3`
- `api-ms-win-service-core-l1-1-5!GetSharedServiceRegistryStateKey` at `0x180232dc7`
- `api-ms-win-service-core-l1-1-5!GetSharedServiceRegistryStateKey` at `0x180232dc7`

## string_xrefs

- `0x180232d60`: `ServicesActive`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall ll_open_persisted_policy_key(_QWORD *a1, unsigned int a2)
{
  SC_HANDLE v4; // rax
  const char *v5; // r9
  SC_HANDLE v6; // rdi
  SC_HANDLE v7; // rax
  const char *v8; // r9
  SC_HANDLE v9; // rbx
  unsigned int SharedServiceRegistryStateKey; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v6 = v4;
  if ( !v4 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x15,
      (unsigned int)"onecore\\vm\\dv\\net\\l1vhlwf\\api\\nivpersistence.cpp",
      v5);
  v7 = OpenServiceW(v4, L"l1vhlwf", 1u);
  v9 = v7;
  if ( !v7 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecore\\vm\\dv\\net\\l1vhlwf\\api\\nivpersistence.cpp",
      v8);
  *a1 = 0;
  SharedServiceRegistryStateKey = GetSharedServiceRegistryStateKey(v7, 0, a2, a1);
  if ( SharedServiceRegistryStateKey )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x21,
      (unsigned int)"onecore\\vm\\dv\\net\\l1vhlwf\\api\\nivpersistence.cpp",
      (const char *)SharedServiceRegistryStateKey,
      1u);
  CloseServiceHandle(v9);
  CloseServiceHandle(v6);
  return a1;
}

```

## disassembly

```asm
0x180232d3c  mov     [rsp+arg_8], rbx
0x180232d41  mov     [rsp+arg_0], rcx
0x180232d46  push    rbp
0x180232d47  push    rsi
0x180232d48  push    rdi
0x180232d49  sub     rsp, 30h
0x180232d4d  mov     ebp, edx
0x180232d4f  mov     rsi, rcx
0x180232d52  mov     [rsp+48h+var_28], 0
0x180232d5a  mov     r8d, 1; dwDesiredAccess
0x180232d60  lea     rdx, DatabaseName; "ServicesActive"
0x180232d67  xor     ecx, ecx; lpMachineName
0x180232d69  call    cs:__imp_OpenSCManagerW
0x180232d6f  mov     rdi, rax
0x180232d72  mov     [rsp+48h+arg_10], rax
0x180232d77  mov     rcx, [rsp+48h]; this
0x180232d7c  test    rax, rax
0x180232d7f  jz      loc_180232E0E
0x180232d85  mov     r8d, 1; dwDesiredAccess
0x180232d8b  lea     rdx, aL1vhlwf; "l1vhlwf"
0x180232d92  mov     rcx, rax; hSCManager
0x180232d95  call    cs:__imp_OpenServiceW
0x180232d9b  mov     rbx, rax
0x180232d9e  mov     [rsp+48h+arg_18], rax
0x180232da3  mov     rcx, [rsp+48h]; this
0x180232da8  test    rax, rax
0x180232dab  jz      short loc_180232E20
0x180232dad  mov     [rsp+48h+var_28], 1; unsigned int
0x180232db5  mov     qword ptr [rsi], 0
0x180232dbc  mov     r9, rsi
0x180232dbf  mov     r8d, ebp
0x180232dc2  xor     edx, edx
0x180232dc4  mov     rcx, rax
0x180232dc7  call    cs:__imp_GetSharedServiceRegistryStateKey
0x180232dcd  mov     rcx, [rsp+48h]; this
0x180232dd2  test    eax, eax
0x180232dd4  jnz     short loc_180232DF9
0x180232dd6  mov     rcx, rbx; hSCObject
0x180232dd9  call    cs:__imp_CloseServiceHandle
0x180232ddf  nop
0x180232de0  mov     rcx, rdi; hSCObject
0x180232de3  call    cs:__imp_CloseServiceHandle
0x180232de9  mov     rax, rsi
0x180232dec  mov     rbx, [rsp+48h+arg_8]
0x180232df1  add     rsp, 30h
0x180232df5  pop     rdi
0x180232df6  pop     rsi
0x180232df7  pop     rbp
0x180232df8  retn
0x180232df9  mov     r9d, eax; char *
0x180232dfc  lea     r8, aOnecoreVmDvNet_41; "onecore\\vm\\dv\\net\\l1vhlwf\\api\\niv"...
0x180232e03  mov     edx, 21h ; '!'; void *
0x180232e08  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180232e0e  lea     r8, aOnecoreVmDvNet_41; "onecore\\vm\\dv\\net\\l1vhlwf\\api\\niv"...
0x180232e15  mov     edx, 15h; void *
0x180232e1a  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180232e20  lea     r8, aOnecoreVmDvNet_41; "onecore\\vm\\dv\\net\\l1vhlwf\\api\\niv"...
0x180232e27  mov     edx, 19h; void *
0x180232e2c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
