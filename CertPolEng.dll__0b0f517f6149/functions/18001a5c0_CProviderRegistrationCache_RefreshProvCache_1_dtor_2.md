# _CProviderRegistrationCache::RefreshProvCache_::_1_::dtor$2

- ea: `0x18001a5c0`
- end: `0x18001a5cc`
- name: `_CProviderRegistrationCache::RefreshProvCache_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008930`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::RefreshProvCache_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CAutoRtlLock::~CAutoRtlLock((PRTL_RESOURCE *)(a2 + 144));
}

```

## disassembly

```asm
0x18001a5c0  lea     rcx, [rdx+90h]; this
0x18001a5c7  jmp     ??1CAutoRtlLock@@QEAA@XZ; CAutoRtlLock::~CAutoRtlLock(void)
```
