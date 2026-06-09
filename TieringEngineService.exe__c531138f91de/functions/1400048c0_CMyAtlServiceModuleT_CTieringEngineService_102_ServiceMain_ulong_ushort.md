# CMyAtlServiceModuleT<CTieringEngineService,102>::_ServiceMain(ulong,ushort * *)

- ea: `0x1400048c0`
- end: `0x1400048c5`
- name: `?_ServiceMain@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@KAXKPEAPEAG@Z`
- size: `5`
- prototype: `void __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x140004440`

## pseudocode

```c
// attributes: thunk
void __fastcall CMyAtlServiceModuleT<CTieringEngineService,102>::_ServiceMain(__int64 a1, int a2)
{
  CMyAtlServiceModuleT<CTieringEngineService,102>::ServiceMain(a1, a2);
}

```

## disassembly

```asm
0x1400048c0  jmp     ?ServiceMain@?$CMyAtlServiceModuleT@VCTieringEngineService@@$0GG@@@QEAAXKPEAPEAG@Z; CMyAtlServiceModuleT<CTieringEngineService,102>::ServiceMain(ulong,ushort * *)
```
