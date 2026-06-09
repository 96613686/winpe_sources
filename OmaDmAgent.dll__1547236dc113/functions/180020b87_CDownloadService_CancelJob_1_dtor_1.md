# _CDownloadService::CancelJob_::_1_::dtor$1

- ea: `0x180020b87`
- end: `0x180020b93`
- name: `_CDownloadService::CancelJob_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001aff8`

## pseudocode

```c
__int64 __fastcall CDownloadService::CancelJob_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return _com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>((__int64 *)(a2 + 176));
}

```

## disassembly

```asm
0x180020b87  lea     rcx, [rdx+0B0h]
0x180020b8e  jmp     ??1?$_com_ptr_t@V?$_com_IIID@UIUnknown@@$1?_GUID_00000000_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IUnknown,&__s_GUID const _GUID_00000000_0000_0000_c000_000000000046>>(void)
```
