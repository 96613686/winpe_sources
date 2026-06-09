# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18000ae98`
- end: `0x18000aeb7`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000983c`
- `0x180009990`
- `0x18000ac54`
- `0x18000ac84`

## callees

- `0x180007ab4`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details **this, void *a2)
{
  void *v3; // rdx

  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this + 1,
    a2);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    this,
    v3);
}

```

## disassembly

```asm
0x18000ae98  push    rbx
0x18000ae9a  sub     rsp, 20h
0x18000ae9e  mov     rbx, rcx
0x18000aea1  add     rcx, 8
0x18000aea5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aeaa  mov     rcx, rbx
0x18000aead  add     rsp, 20h
0x18000aeb1  pop     rbx
0x18000aeb2  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
