# _CProviderRegistrationCache::GetTrustAnchors_::_1_::dtor$0

- ea: `0x18001aa74`
- end: `0x18001aa80`
- name: `_CProviderRegistrationCache::GetTrustAnchors_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180013be8`

## pseudocode

```c
void __fastcall CProviderRegistrationCache::GetTrustAnchors_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>::~CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>((_QWORD *)(a2 + 312));
}

```

## disassembly

```asm
0x18001aa74  lea     rcx, [rdx+138h]
0x18001aa7b  jmp     ??1?$CAutoPointer@V?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@U?$AutoPointerTraits@V?$CPtrArrayTemplate@VCCertChainList@@U?$AutoPtrTraits@VCCertChainList@@@@@@@@@@QEAA@XZ; CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>::~CAutoPointer<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>,AutoPointerTraits<CPtrArrayTemplate<CCertChainList,AutoPtrTraits<CCertChainList>>>>(void)
```
