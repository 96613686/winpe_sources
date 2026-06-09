# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180006544`
- end: `0x180006591`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800031e4`
- `0x180004af4`
- `0x180006300`

## callees

- `0x180002e60`
- `0x180003140`
- `0x180003440`
- `0x180006544`

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
0x180006544  mov     [rsp+arg_8], rbx
0x180006549  mov     [rsp+arg_10], rsi
0x18000654e  push    rdi
0x18000654f  sub     rsp, 20h
0x180006553  mov     rdi, [rcx]
0x180006556  mov     rsi, rdx
0x180006559  mov     rbx, rcx
0x18000655c  test    rdi, rdi
0x18000655f  jz      short loc_18000657D
0x180006561  lea     rcx, [rsp+28h+arg_0]; this
0x180006566  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000656b  mov     rcx, rdi; this
0x18000656e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180006573  lea     rcx, [rsp+28h+arg_0]; this
0x180006578  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000657d  mov     [rbx], rsi
0x180006580  mov     rbx, [rsp+28h+arg_8]
0x180006585  mov     rsi, [rsp+28h+arg_10]
0x18000658a  add     rsp, 20h
0x18000658e  pop     rdi
0x18000658f  retn
```
