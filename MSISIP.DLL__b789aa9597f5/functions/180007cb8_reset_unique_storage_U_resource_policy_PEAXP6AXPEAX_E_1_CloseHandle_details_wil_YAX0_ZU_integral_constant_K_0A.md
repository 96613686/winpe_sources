# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180007cb8`
- end: `0x180007d04`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180007640`
- `0x1800077a8`
- `0x180007ad0`
- `0x180007b28`

## callees

- `0x180007cb8`
- `0x180009738`
- `0x18000ac30`
- `0x18000aec0`

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
0x180007cb8  mov     [rsp+arg_8], rbx
0x180007cbd  mov     [rsp+arg_10], rsi
0x180007cc2  push    rdi
0x180007cc3  sub     rsp, 20h
0x180007cc7  mov     rdi, [rcx]
0x180007cca  mov     rsi, rdx
0x180007ccd  mov     rbx, rcx
0x180007cd0  test    rdi, rdi
0x180007cd3  jz      short loc_180007CF1
0x180007cd5  lea     rcx, [rsp+28h+arg_0]; this
0x180007cda  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180007cdf  mov     rcx, rdi; this
0x180007ce2  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180007ce7  lea     rcx, [rsp+28h+arg_0]; this
0x180007cec  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180007cf1  mov     [rbx], rsi
0x180007cf4  mov     rbx, [rsp+28h+arg_8]
0x180007cf9  mov     rsi, [rsp+28h+arg_10]
0x180007cfe  add     rsp, 20h
0x180007d02  pop     rdi
0x180007d03  retn
```
