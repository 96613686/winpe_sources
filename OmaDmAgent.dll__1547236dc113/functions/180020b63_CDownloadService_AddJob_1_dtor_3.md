# _CDownloadService::AddJob_::_1_::dtor$3

- ea: `0x180020b63`
- end: `0x180020b6f`
- name: `_CDownloadService::AddJob_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001afb4`

## pseudocode

```c
__int64 __fastcall CDownloadService::AddJob_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)(a2 + 88));
}

```

## disassembly

```asm
0x180020b63  lea     rcx, [rdx+58h]
0x180020b6a  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
```
