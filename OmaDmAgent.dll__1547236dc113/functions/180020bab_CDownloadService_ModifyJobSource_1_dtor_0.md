# _CDownloadService::ModifyJobSource_::_1_::dtor$0

- ea: `0x180020bab`
- end: `0x180020bb7`
- name: `_CDownloadService::ModifyJobSource_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001afb4`

## pseudocode

```c
__int64 __fastcall CDownloadService::ModifyJobSource_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)(a2 + 40));
}

```

## disassembly

```asm
0x180020bab  lea     rcx, [rdx+28h]
0x180020bb2  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
```
