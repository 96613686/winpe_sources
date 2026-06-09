# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140006f5c`
- end: `0x140006faa`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007db0`
- `0x14000b3ac`
- `0x14000ce24`

## callees

- `0x14000222c`
- `0x140006f5c`
- `0x14000ab14`
- `0x14000ad60`

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
0x140006f5c  mov     [rsp+arg_8], rbx
0x140006f61  mov     [rsp+arg_10], rsi
0x140006f66  push    rdi
0x140006f67  sub     rsp, 20h
0x140006f6b  mov     rdi, [rcx]
0x140006f6e  mov     rsi, rdx
0x140006f71  mov     rbx, rcx
0x140006f74  test    rdi, rdi
0x140006f77  jnz     short loc_140006F8C
0x140006f79  mov     [rbx], rsi
0x140006f7c  mov     rbx, [rsp+28h+arg_8]
0x140006f81  mov     rsi, [rsp+28h+arg_10]
0x140006f86  add     rsp, 20h
0x140006f8a  pop     rdi
0x140006f8b  retn
0x140006f8c  lea     rcx, [rsp+28h+arg_0]; this
0x140006f91  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140006f96  mov     rcx, rdi; this
0x140006f99  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x140006f9e  lea     rcx, [rsp+28h+arg_0]; this
0x140006fa3  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140006fa8  jmp     short loc_140006F79
```
