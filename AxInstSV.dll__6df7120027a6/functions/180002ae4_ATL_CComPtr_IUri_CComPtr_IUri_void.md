# ATL::CComPtr<IUri>::~CComPtr<IUri>(void)

- ea: `0x180002ae4`
- end: `0x180002ae9`
- name: `??1?$CComPtr@UIUri@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800144d8`
- `0x18001456a`
- `0x180014669`
- `0x180014a97`

## callees

- `0x180002af0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IUri>::~CComPtr<IUri>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x180002ae4  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
