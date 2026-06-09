# _com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>(void)

- ea: `0x18001aff8`
- end: `0x18001affd`
- name: `??1?$_com_ptr_t@V?$_com_IIID@UIUnknown@@$1?_GUID_00000000_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ`
- size: `5`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020b87`

## callees

- `0x18001afb4`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall _com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>(
        __int64 *a1)
{
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(a1);
}

```

## disassembly

```asm
0x18001aff8  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
```
