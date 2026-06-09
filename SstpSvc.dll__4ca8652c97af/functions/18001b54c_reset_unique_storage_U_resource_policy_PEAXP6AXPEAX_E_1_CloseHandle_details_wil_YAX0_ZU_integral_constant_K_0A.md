# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18001b54c`
- end: `0x18001b598`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017810`
- `0x180017978`
- `0x180017cac`
- `0x18001b354`

## callees

- `0x18001724c`
- `0x180017714`
- `0x180017ae0`
- `0x18001b54c`

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
0x18001b54c  mov     [rsp+arg_8], rbx
0x18001b551  mov     [rsp+arg_10], rsi
0x18001b556  push    rdi
0x18001b557  sub     rsp, 20h
0x18001b55b  mov     rdi, [rcx]
0x18001b55e  mov     rsi, rdx
0x18001b561  mov     rbx, rcx
0x18001b564  test    rdi, rdi
0x18001b567  jz      short loc_18001B585
0x18001b569  lea     rcx, [rsp+28h+arg_0]; this
0x18001b56e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18001b573  mov     rcx, rdi; this
0x18001b576  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18001b57b  lea     rcx, [rsp+28h+arg_0]; this
0x18001b580  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001b585  mov     [rbx], rsi
0x18001b588  mov     rbx, [rsp+28h+arg_8]
0x18001b58d  mov     rsi, [rsp+28h+arg_10]
0x18001b592  add     rsp, 20h
0x18001b596  pop     rdi
0x18001b597  retn
```
