# _CProviderRegistrationCache::SelectCert_::_1_::dtor$0

- ea: `0x18001a4a0`
- end: `0x18001a4ac`
- name: `_CProviderRegistrationCache::SelectCert_::_1_::dtor$0`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bc80`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::SelectCert_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 144));
}

```

## disassembly

```asm
0x18001a4a0  lea     rcx, [rdx+90h]
0x18001a4a7  jmp     ??1?$CAutoPointer@VCCertChainList@@U?$AutoPointerTraits@VCCertChainList@@@@@@QEAA@XZ; CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>(void)
```
