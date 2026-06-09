# wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void_(__cdecl_)(SIPOLICY_EXT_REGISTRY__)_&CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset

- ea: `0x18000d688`
- end: `0x18000d6d4`
- name: `wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void_(__cdecl_)(SIPOLICY_EXT_REGISTRY__)_&CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a278`
- `0x18000b540`
- `0x18000b878`

## callees

- `0x180005034`
- `0x18000569c`
- `0x18000ad20`
- `0x18000d688`

## pseudocode

```c
void __fastcall wil::details::unique_storage_wil::details::resource_policy_SIPOLICY_EXT_REGISTRY___void____cdecl___SIPOLICY_EXT_REGISTRY_____CodeIntegrity::Management::FreeExtRegistry_wistd::integral_constant_unsigned___int64_0__SIPOLICY_EXT_REGISTRY___SIPOLICY_EXT_REGISTRY___0_std::nullptr_t___::reset(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CodeIntegrity::Management::FreeExtRegistry(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18000d688  mov     [rsp+arg_8], rbx
0x18000d68d  mov     [rsp+arg_10], rsi
0x18000d692  push    rdi
0x18000d693  sub     rsp, 20h
0x18000d697  mov     rdi, [rcx]
0x18000d69a  mov     rsi, rdx
0x18000d69d  mov     rbx, rcx
0x18000d6a0  test    rdi, rdi
0x18000d6a3  jz      short loc_18000D6C1
0x18000d6a5  lea     rcx, [rsp+28h+arg_0]; this
0x18000d6aa  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000d6af  mov     rcx, rdi; hMem
0x18000d6b2  call    CodeIntegrity__Management__FreeExtRegistry
0x18000d6b7  lea     rcx, [rsp+28h+arg_0]; this
0x18000d6bc  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000d6c1  mov     [rbx], rsi
0x18000d6c4  mov     rbx, [rsp+28h+arg_8]
0x18000d6c9  mov     rsi, [rsp+28h+arg_10]
0x18000d6ce  add     rsp, 20h
0x18000d6d2  pop     rdi
0x18000d6d3  retn
```
