# _CProviderRegistrationCache::IntGetTrustAnchors_::_1_::dtor$1

- ea: `0x18001a560`
- end: `0x18001a56c`
- name: `_CProviderRegistrationCache::IntGetTrustAnchors_::_1_::dtor$1`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180008930`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::IntGetTrustAnchors_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CAutoRtlLock::~CAutoRtlLock((PRTL_RESOURCE *)(a2 + 192));
}

```

## disassembly

```asm
0x18001a560  lea     rcx, [rdx+0C0h]; this
0x18001a567  jmp     ??1CAutoRtlLock@@QEAA@XZ; CAutoRtlLock::~CAutoRtlLock(void)
```
