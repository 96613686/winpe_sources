# ATL::CComPtr<IMMDeviceEnumerator>::~CComPtr<IMMDeviceEnumerator>(void)

- ea: `0x18000eb5c`
- end: `0x18000eb61`
- name: `??1?$CComPtr@UIMMDeviceEnumerator@@@ATL@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `14`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020870`
- `0x180020890`
- `0x1800208b0`
- `0x1800208d0`
- `0x1800208f0`
- `0x180020910`
- `0x180020930`
- `0x180020950`
- `0x180020970`
- `0x180020990`
- `0x1800209b0`
- `0x1800209d0`
- `0x1800209f0`
- `0x180020a10`

## callees

- `0x18000eb68`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall ATL::CComPtr<IMMDeviceEnumerator>::~CComPtr<IMMDeviceEnumerator>(__int64 a1)
{
  return ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(a1);
}

```

## disassembly

```asm
0x18000eb5c  jmp     ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
```
