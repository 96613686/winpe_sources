# ATL::CComPtr<IAppHostProperty>::~CComPtr<IAppHostProperty>(void)

- ea: `0x180002198`
- end: `0x18000219d`
- name: `??1?$CComPtr@UIAppHostProperty@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001357e`
- `0x1800135c6`
- `0x1800135fc`
- `0x18001360e`
- `0x1800137d3`
- `0x1800137e5`
- `0x180013851`
- `0x180013879`
- `0x18001388b`
- `0x1800138d7`
- `0x1800139a9`
- `0x180013adb`
- `0x180013aff`
- `0x180013b23`
- `0x180013b47`
- `0x180013c3f`
- `0x180013ca7`
- `0x180013cdd`
- `0x180013d28`

## callees

- `0x1800021a4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IAppHostProperty>::~CComPtr<IAppHostProperty>(__int64 *a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x180002198  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
