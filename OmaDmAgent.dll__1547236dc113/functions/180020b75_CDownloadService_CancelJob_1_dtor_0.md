# _CDownloadService::CancelJob_::_1_::dtor$0

- ea: `0x180020b75`
- end: `0x180020b81`
- name: `_CDownloadService::CancelJob_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001afb4`

## pseudocode

```c
__int64 __fastcall CDownloadService::CancelJob_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)(a2 + 184));
}

```

## disassembly

```asm
0x180020b75  lea     rcx, [rdx+0B8h]
0x180020b7c  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
```
