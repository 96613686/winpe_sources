# ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMigrationPlugin>>,ATL::CComCreator<ATL::CComAggObject<CMigrationPlugin>>>::CreateInstance(void *,_GUID const &,void * *)

- ea: `0x18000d970`
- end: `0x18000d97e`
- name: `?CreateInstance@?$CComCreator2@V?$CComCreator@V?$CComObject@VCMigrationPlugin@@@ATL@@@ATL@@V?$CComCreator@V?$CComAggObject@VCMigrationPlugin@@@ATL@@@2@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z`
- size: `14`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000d984`
- `0x18000dad4`

## pseudocode

```c
__int64 __fastcall ATL::CComCreator2<ATL::CComCreator<ATL::CComObject<CMigrationPlugin>>,ATL::CComCreator<ATL::CComAggObject<CMigrationPlugin>>>::CreateInstance(
        __int64 a1)
{
  if ( a1 )
    return ATL::CComCreator<ATL::CComAggObject<CMigrationPlugin>>::CreateInstance();
  else
    return ATL::CComCreator<ATL::CComObject<CMigrationPlugin>>::CreateInstance();
}

```

## disassembly

```asm
0x18000d970  test    rcx, rcx
0x18000d973  jz      ?CreateInstance@?$CComCreator@V?$CComObject@VCMigrationPlugin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComObject<CMigrationPlugin>>::CreateInstance(void *,_GUID const &,void * *)
0x18000d979  jmp     ?CreateInstance@?$CComCreator@V?$CComAggObject@VCMigrationPlugin@@@ATL@@@ATL@@SAJPEAXAEBU_GUID@@PEAPEAX@Z; ATL::CComCreator<ATL::CComAggObject<CMigrationPlugin>>::CreateInstance(void *,_GUID const &,void * *)
```
