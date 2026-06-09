# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::WorkingThread(void *)

- ea: `0x140004aa0`
- end: `0x140004aaf`
- name: `?WorkingThread@?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(__int64 StartContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400044a0`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::WorkingThread(
        __int64 StartContext)
{
  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::Run(StartContext);
}

```

## disassembly

```asm
0x140004aa0  sub     rsp, 28h
0x140004aa4  call    ?Run@?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::Run(void)
0x140004aa9  add     rsp, 28h
0x140004aad  retn
```
