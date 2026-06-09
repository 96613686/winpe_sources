# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140007884`
- end: `0x1400078d0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140005508`
- `0x140006acc`
- `0x140007818`
- `0x14000d6f0`

## callees

- `0x1400051ec`
- `0x140005460`
- `0x1400056b8`
- `0x140007884`

## pseudocode

```c
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        wil::details **a1,
        wil::details *a2)
{
  wil::details *v2; // rdi
  void *v5; // rdx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    wil::details::CloseHandle(v2, v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x140007884  mov     [rsp+arg_8], rbx
0x140007889  mov     [rsp+arg_10], rsi
0x14000788e  push    rdi
0x14000788f  sub     rsp, 20h
0x140007893  mov     rdi, [rcx]
0x140007896  mov     rsi, rdx
0x140007899  mov     rbx, rcx
0x14000789c  test    rdi, rdi
0x14000789f  jz      short loc_1400078BD
0x1400078a1  lea     rcx, [rsp+28h+arg_0]; this
0x1400078a6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400078ab  mov     rcx, rdi; this
0x1400078ae  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400078b3  lea     rcx, [rsp+28h+arg_0]; this
0x1400078b8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400078bd  mov     [rbx], rsi
0x1400078c0  mov     rbx, [rsp+28h+arg_8]
0x1400078c5  mov     rsi, [rsp+28h+arg_10]
0x1400078ca  add     rsp, 20h
0x1400078ce  pop     rdi
0x1400078cf  retn
```
