# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000aa8c`
- end: `0x18000aad8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005cc8`
- `0x180007534`
- `0x180008e38`
- `0x1800096b0`
- `0x18000a834`

## callees

- `0x180005318`
- `0x180005a38`
- `0x180005f14`
- `0x18000aa8c`

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
0x18000aa8c  mov     [rsp+arg_8], rbx
0x18000aa91  mov     [rsp+arg_10], rsi
0x18000aa96  push    rdi
0x18000aa97  sub     rsp, 20h
0x18000aa9b  mov     rdi, [rcx]
0x18000aa9e  mov     rsi, rdx
0x18000aaa1  mov     rbx, rcx
0x18000aaa4  test    rdi, rdi
0x18000aaa7  jz      short loc_18000AAC5
0x18000aaa9  lea     rcx, [rsp+28h+arg_0]; this
0x18000aaae  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000aab3  mov     rcx, rdi; this
0x18000aab6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000aabb  lea     rcx, [rsp+28h+arg_0]; this
0x18000aac0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000aac5  mov     [rbx], rsi
0x18000aac8  mov     rbx, [rsp+28h+arg_8]
0x18000aacd  mov     rsi, [rsp+28h+arg_10]
0x18000aad2  add     rsp, 20h
0x18000aad6  pop     rdi
0x18000aad7  retn
```
