# _CProviderRegistrationCache::GetTrustAnchors_::_1_::dtor$4

- ea: `0x18001aaaa`
- end: `0x18001aab6`
- name: `_CProviderRegistrationCache::GetTrustAnchors_::_1_::dtor$4`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bc80`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetTrustAnchors_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  return CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 168));
}

```

## disassembly

```asm
0x18001aaaa  lea     rcx, [rdx+0A8h]
0x18001aab1  jmp     ??1?$CAutoPointer@VCCertChainList@@U?$AutoPointerTraits@VCCertChainList@@@@@@QEAA@XZ; CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>(void)
```
