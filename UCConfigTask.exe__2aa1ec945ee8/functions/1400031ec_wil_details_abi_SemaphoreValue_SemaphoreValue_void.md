# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1400031ec`
- end: `0x14000320b`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(wil::details **this, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140002ddc`
- `0x140002e0c`
- `0x140004e38`
- `0x140004f68`

## callees

- `0x140003078`

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
0x1400031ec  push    rbx
0x1400031ee  sub     rsp, 20h
0x1400031f2  mov     rbx, rcx
0x1400031f5  add     rcx, 8
0x1400031f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400031fe  mov     rcx, rbx
0x140003201  add     rsp, 20h
0x140003205  pop     rbx
0x140003206  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
