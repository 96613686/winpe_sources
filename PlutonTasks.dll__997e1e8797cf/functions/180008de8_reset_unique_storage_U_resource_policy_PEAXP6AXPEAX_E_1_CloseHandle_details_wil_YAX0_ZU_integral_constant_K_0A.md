# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180008de8`
- end: `0x180008e34`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003d18`
- `0x180003e80`
- `0x18000441c`
- `0x180008b48`

## callees

- `0x180003364`
- `0x180003a38`
- `0x180004024`
- `0x180008de8`

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
0x180008de8  mov     [rsp+arg_8], rbx
0x180008ded  mov     [rsp+arg_10], rsi
0x180008df2  push    rdi
0x180008df3  sub     rsp, 20h
0x180008df7  mov     rdi, [rcx]
0x180008dfa  mov     rsi, rdx
0x180008dfd  mov     rbx, rcx
0x180008e00  test    rdi, rdi
0x180008e03  jz      short loc_180008E21
0x180008e05  lea     rcx, [rsp+28h+arg_0]; this
0x180008e0a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008e0f  mov     rcx, rdi; this
0x180008e12  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008e17  lea     rcx, [rsp+28h+arg_0]; this
0x180008e1c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008e21  mov     [rbx], rsi
0x180008e24  mov     rbx, [rsp+28h+arg_8]
0x180008e29  mov     rsi, [rsp+28h+arg_10]
0x180008e2e  add     rsp, 20h
0x180008e32  pop     rdi
0x180008e33  retn
```
