# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x140008934`
- end: `0x140008953`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140008668`
- `0x1400087cc`
- `0x14000ab58`
- `0x14000ab88`

## callees

- `0x140007f1c`

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
0x140008934  push    rbx
0x140008936  sub     rsp, 20h
0x14000893a  mov     rbx, rcx
0x14000893d  add     rcx, 8
0x140008941  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140008946  mov     rcx, rbx
0x140008949  add     rsp, 20h
0x14000894d  pop     rbx
0x14000894e  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
