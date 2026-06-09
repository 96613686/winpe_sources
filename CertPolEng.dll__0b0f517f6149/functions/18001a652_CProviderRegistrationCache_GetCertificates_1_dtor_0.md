# _CProviderRegistrationCache::GetCertificates_::_1_::dtor$0

- ea: `0x18001a652`
- end: `0x18001a65e`
- name: `_CProviderRegistrationCache::GetCertificates_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bc80`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::GetCertificates_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 184));
}

```

## disassembly

```asm
0x18001a652  lea     rcx, [rdx+0B8h]
0x18001a659  jmp     ??1?$CAutoPointer@VCCertChainList@@U?$AutoPointerTraits@VCCertChainList@@@@@@QEAA@XZ; CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>(void)
```
