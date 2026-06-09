# _CDownloadService::Complete_::_1_::dtor$0

- ea: `0x180020b3f`
- end: `0x180020b4b`
- name: `_CDownloadService::Complete_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001afb4`

## pseudocode

```c
__int64 __fastcall CDownloadService::Complete_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)(a2 + 128));
}

```

## disassembly

```asm
0x180020b3f  lea     rcx, [rdx+80h]
0x180020b46  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
```
