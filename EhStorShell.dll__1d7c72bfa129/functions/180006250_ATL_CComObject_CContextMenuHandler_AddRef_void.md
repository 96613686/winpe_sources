# ATL::CComObject<CContextMenuHandler>::AddRef(void)

- ea: `0x180006250`
- end: `0x180006259`
- name: `?AddRef@?$CComObject@VCContextMenuHandler@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180007e90`

## callees

- `0x1800031e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CContextMenuHandler>::AddRef(__int64 a1)
{
  return ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(a1 + 16);
}

```

## disassembly

```asm
0x180006250  add     rcx, 10h
0x180006254  jmp     ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
```
