# _CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor$5

- ea: `0x18001a620`
- end: `0x18001a62c`
- name: `_CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor$5`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bc80`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::ReadProviderRegistration_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  return CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>((__int64 (__fastcall ****)(_QWORD, __int64))(a2 + 128));
}

```

## disassembly

```asm
0x18001a620  lea     rcx, [rdx+80h]
0x18001a627  jmp     ??1?$CAutoPointer@VCCertChainList@@U?$AutoPointerTraits@VCCertChainList@@@@@@QEAA@XZ; CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>::~CAutoPointer<CCertChainList,AutoPointerTraits<CCertChainList>>(void)
```
