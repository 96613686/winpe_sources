# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x140004ab8`
- end: `0x140004ad7`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400047c8`
- `0x14000492c`
- `0x1400074d4`
- `0x140007504`

## callees

- `0x1400076d0`

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
0x140004ab8  push    rbx
0x140004aba  sub     rsp, 20h
0x140004abe  mov     rbx, rcx
0x140004ac1  add     rcx, 8
0x140004ac5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140004aca  mov     rcx, rbx
0x140004acd  add     rsp, 20h
0x140004ad1  pop     rbx
0x140004ad2  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
