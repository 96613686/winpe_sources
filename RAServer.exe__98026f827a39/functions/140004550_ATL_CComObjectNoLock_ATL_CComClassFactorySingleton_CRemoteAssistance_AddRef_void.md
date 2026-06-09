# ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::AddRef(void)

- ea: `0x140004550`
- end: `0x140004559`
- name: `?AddRef@?$CComObjectNoLock@V?$CComClassFactorySingleton@VCRemoteAssistance@@@ATL@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `unsigned int __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000a258`

## pseudocode

```c
unsigned int __fastcall ATL::CComObjectNoLock<ATL::CComClassFactorySingleton<CRemoteAssistance>>::AddRef(__int64 a1)
{
  return ATL::SafeIncrementReferenceMultiThread((volatile int *)(a1 + 8));
}

```

## disassembly

```asm
0x140004550  add     rcx, 8; volatile int *
0x140004554  jmp     ?SafeIncrementReferenceMultiThread@ATL@@YAKPECJ@Z; ATL::SafeIncrementReferenceMultiThread(long volatile *)
```
