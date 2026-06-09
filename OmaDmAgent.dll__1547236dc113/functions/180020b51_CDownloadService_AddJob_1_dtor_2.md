# _CDownloadService::AddJob_::_1_::dtor$2

- ea: `0x180020b51`
- end: `0x180020b5d`
- name: `_CDownloadService::AddJob_::_1_::dtor$2`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18001afb4`

## pseudocode

```c
__int64 __fastcall CDownloadService::AddJob_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  return ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>((__int64 *)(a2 + 96));
}

```

## disassembly

```asm
0x180020b51  lea     rcx, [rdx+60h]
0x180020b58  jmp     ??1?$CComPtr@UIBackgroundCopyCallback@@@ATL@@QEAA@XZ; ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(void)
```
