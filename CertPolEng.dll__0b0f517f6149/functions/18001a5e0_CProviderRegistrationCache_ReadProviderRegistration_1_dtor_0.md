# _CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor$0

- ea: `0x18001a5e0`
- end: `0x18001a5ec`
- name: `_CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008930`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoRtlLock::~CAutoRtlLock((PRTL_RESOURCE *)(a2 + 168));
}

```

## disassembly

```asm
0x18001a5e0  lea     rcx, [rdx+0A8h]; this
0x18001a5e7  jmp     ??1CAutoRtlLock@@QEAA@XZ; CAutoRtlLock::~CAutoRtlLock(void)
```
