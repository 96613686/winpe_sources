# _CProviderRegistrationCache::SelectCert_::_1_::dtor$2

- ea: `0x18001a4e0`
- end: `0x18001a4ec`
- name: `_CProviderRegistrationCache::SelectCert_::_1_::dtor$2`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008930`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::SelectCert_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  CAutoRtlLock::~CAutoRtlLock((PRTL_RESOURCE *)(a2 + 96));
}

```

## disassembly

```asm
0x18001a4e0  lea     rcx, [rdx+60h]; this
0x18001a4e7  jmp     ??1CAutoRtlLock@@QEAA@XZ; CAutoRtlLock::~CAutoRtlLock(void)
```
