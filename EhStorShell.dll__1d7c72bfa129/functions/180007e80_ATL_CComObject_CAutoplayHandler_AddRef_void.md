# ATL::CComObject<CAutoplayHandler>::AddRef(void)

- ea: `0x180007e80`
- end: `0x180007e89`
- name: `?AddRef@?$CComObject@VCAutoplayHandler@@@ATL@@UEAAKXZ`
- size: `9`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800031e0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CAutoplayHandler>::AddRef(__int64 a1)
{
  return ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(a1 + 8);
}

```

## disassembly

```asm
0x180007e80  add     rcx, 8
0x180007e84  jmp     ?InternalAddRef@?$CComObjectRootEx@VCComSingleThreadModel@ATL@@@ATL@@QEAAKXZ; ATL::CComObjectRootEx<ATL::CComSingleThreadModel>::InternalAddRef(void)
```
