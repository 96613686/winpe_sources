# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000713c`
- end: `0x180007188`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004d48`
- `0x180006684`
- `0x1800070d0`

## callees

- `0x180004a10`
- `0x180004cac`
- `0x180004ee4`
- `0x18000713c`

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
0x18000713c  mov     [rsp+arg_8], rbx
0x180007141  mov     [rsp+arg_10], rsi
0x180007146  push    rdi
0x180007147  sub     rsp, 20h
0x18000714b  mov     rdi, [rcx]
0x18000714e  mov     rsi, rdx
0x180007151  mov     rbx, rcx
0x180007154  test    rdi, rdi
0x180007157  jz      short loc_180007175
0x180007159  lea     rcx, [rsp+28h+arg_0]; this
0x18000715e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007163  mov     rcx, rdi; this
0x180007166  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000716b  lea     rcx, [rsp+28h+arg_0]; this
0x180007170  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007175  mov     [rbx], rsi
0x180007178  mov     rbx, [rsp+28h+arg_8]
0x18000717d  mov     rsi, [rsp+28h+arg_10]
0x180007182  add     rsp, 20h
0x180007186  pop     rdi
0x180007187  retn
```
