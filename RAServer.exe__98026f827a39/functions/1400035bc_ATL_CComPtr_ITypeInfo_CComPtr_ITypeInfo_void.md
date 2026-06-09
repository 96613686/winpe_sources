# ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(void)

- ea: `0x1400035bc`
- end: `0x1400035c1`
- name: `??1?$CComPtr@UITypeInfo@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015de0`
- `0x140015df2`
- `0x140015e04`
- `0x140015fb1`
- `0x140015fd5`
- `0x14001601d`

## callees

- `0x1400035c8`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<ITypeInfo>::~CComPtr<ITypeInfo>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x1400035bc  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
