# CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::AddRef(void)

- ea: `0x180011d70`
- end: `0x180011d7d`
- name: `?AddRef@?$CUnknownImplT@V?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@UEAAKXZ`
- size: `13`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall CUnknownImplT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::AddRef(
        __int64 a1)
{
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)(a1 + 8));
}

```

## disassembly

```asm
0x180011d70  mov     eax, 1
0x180011d75  lock xadd [rcx+8], eax
0x180011d7a  inc     eax
0x180011d7c  retn
```
