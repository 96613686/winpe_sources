# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140004b0c`
- end: `0x140004b58`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400029f4`
- `0x140003f8c`
- `0x140004aa0`

## callees

- `0x1400027a0`
- `0x1400029d4`
- `0x140002b90`
- `0x140004b0c`

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
0x140004b0c  mov     [rsp+arg_8], rbx
0x140004b11  mov     [rsp+arg_10], rsi
0x140004b16  push    rdi
0x140004b17  sub     rsp, 20h
0x140004b1b  mov     rdi, [rcx]
0x140004b1e  mov     rsi, rdx
0x140004b21  mov     rbx, rcx
0x140004b24  test    rdi, rdi
0x140004b27  jz      short loc_140004B45
0x140004b29  lea     rcx, [rsp+28h+arg_0]; this
0x140004b2e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140004b33  mov     rcx, rdi; this
0x140004b36  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140004b3b  lea     rcx, [rsp+28h+arg_0]; this
0x140004b40  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140004b45  mov     [rbx], rsi
0x140004b48  mov     rbx, [rsp+28h+arg_8]
0x140004b4d  mov     rsi, [rsp+28h+arg_10]
0x140004b52  add     rsp, 20h
0x140004b56  pop     rdi
0x140004b57  retn
```
