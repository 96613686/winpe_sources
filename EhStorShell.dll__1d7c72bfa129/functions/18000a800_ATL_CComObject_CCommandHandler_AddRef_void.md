# ATL::CComObject<CCommandHandler>::AddRef(void)

- ea: `0x18000a800`
- end: `0x18000a809`
- name: `?AddRef@?$CComObject@VCCommandHandler@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000a810`
- `0x18000a820`
- `0x18000a830`

## callees

- `0x1800031e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCommandHandler>::AddRef(__int64 a1)
{
  return ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(a1 + 32);
}

```

## disassembly

```asm
0x18000a800  add     rcx, 20h ; ' '
0x18000a804  jmp     ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
```
