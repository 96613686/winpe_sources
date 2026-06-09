# _dynamic_initializer_for__g_comObjectActivationCEditionUpgradeManager__

- ea: `0x180001680`
- end: `0x18000169d`
- name: `_dynamic_initializer_for__g_comObjectActivationCEditionUpgradeManager__`
- size: `29`
- prototype: `PVOID()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000168b`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18000168b`

## pseudocode

```c
PVOID dynamic_initializer_for__g_comObjectActivationCEditionUpgradeManager__()
{
  PVOID result; // rax

  result = EncodePointer(CComInternalCreatorBaseT<CComClassFactoryT<CEditionUpgradeManager,CComInternalCreatorInitializerT,0>,0>::CreateInstance);
  qword_18002F798 = (__int64)result;
  return result;
}

```

## disassembly

```asm
0x180001680  sub     rsp, 28h
0x180001684  lea     rcx, ?CreateInstance@?$CComInternalCreatorBaseT@V?$CComClassFactoryT@VCEditionUpgradeManager@@VCComInternalCreatorInitializerT@@$0A@@@$0A@@@SAJAEBU_GUID@@PEAPEAX@Z; Ptr
0x18000168b  call    cs:__imp_EncodePointer
0x180001691  mov     cs:qword_18002F798, rax
0x180001698  add     rsp, 28h
0x18000169c  retn
```
