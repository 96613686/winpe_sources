# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000d5f8`
- end: `0x18000d644`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008f7c`
- `0x18000adbc`
- `0x18000d1c8`

## callees

- `0x1800089b0`
- `0x180008e20`
- `0x180009254`
- `0x18000d5f8`

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
0x18000d5f8  mov     [rsp+arg_8], rbx
0x18000d5fd  mov     [rsp+arg_10], rsi
0x18000d602  push    rdi
0x18000d603  sub     rsp, 20h
0x18000d607  mov     rdi, [rcx]
0x18000d60a  mov     rsi, rdx
0x18000d60d  mov     rbx, rcx
0x18000d610  test    rdi, rdi
0x18000d613  jz      short loc_18000D631
0x18000d615  lea     rcx, [rsp+28h+arg_0]; this
0x18000d61a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000d61f  mov     rcx, rdi; this
0x18000d622  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000d627  lea     rcx, [rsp+28h+arg_0]; this
0x18000d62c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000d631  mov     [rbx], rsi
0x18000d634  mov     rbx, [rsp+28h+arg_8]
0x18000d639  mov     rsi, [rsp+28h+arg_10]
0x18000d63e  add     rsp, 20h
0x18000d642  pop     rdi
0x18000d643  retn
```
