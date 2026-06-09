# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1400082f0`
- end: `0x14000833d`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140003874`
- `0x140005d34`
- `0x140007dd8`

## callees

- `0x140003218`
- `0x140003618`
- `0x140003ad0`
- `0x1400082f0`

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
0x1400082f0  mov     [rsp+arg_8], rbx
0x1400082f5  mov     [rsp+arg_10], rsi
0x1400082fa  push    rdi
0x1400082fb  sub     rsp, 20h
0x1400082ff  mov     rdi, [rcx]
0x140008302  mov     rsi, rdx
0x140008305  mov     rbx, rcx
0x140008308  test    rdi, rdi
0x14000830b  jz      short loc_140008329
0x14000830d  lea     rcx, [rsp+28h+arg_0]; this
0x140008312  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140008317  mov     rcx, rdi; this
0x14000831a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000831f  lea     rcx, [rsp+28h+arg_0]; this
0x140008324  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140008329  mov     [rbx], rsi
0x14000832c  mov     rbx, [rsp+28h+arg_8]
0x140008331  mov     rsi, [rsp+28h+arg_10]
0x140008336  add     rsp, 20h
0x14000833a  pop     rdi
0x14000833b  retn
```
