# ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(void)

- ea: `0x180004530`
- end: `0x180004535`
- name: `??1?$CComPtr@UIEnhancedStorageSilo@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b750`
- `0x18000b770`
- `0x18000b7c0`
- `0x18000b860`
- `0x18000b8c8`
- `0x18000b8fe`
- `0x18000b910`
- `0x18000b922`
- `0x18000b9d6`
- `0x18000bd7a`

## callees

- `0x18000453c`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IEnhancedStorageSilo>::~CComPtr<IEnhancedStorageSilo>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x180004530  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
