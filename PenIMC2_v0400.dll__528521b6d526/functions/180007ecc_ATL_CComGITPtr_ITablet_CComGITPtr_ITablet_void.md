# ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>(void)

- ea: `0x180007ecc`
- end: `0x180007ed1`
- name: `??1?$CComGITPtr@UITablet@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e61a`
- `0x18000e968`
- `0x18000ea1c`
- `0x18000ea8a`
- `0x18000ed44`
- `0x18000eddb`
- `0x18000f0a7`
- `0x18000f107`

## callees

- `0x180007e24`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComGITPtr<ITablet>::~CComGITPtr<ITablet>(_DWORD *a1)
{
  return ATL::CComGITPtr<ITabletContextP>::Revoke(a1);
}

```

## disassembly

```asm
0x180007ecc  jmp     ?Revoke@?$CComGITPtr@UITabletContextP@@@ATL@@QEAAJXZ; ATL::CComGITPtr<ITabletContextP>::Revoke(void)
```
