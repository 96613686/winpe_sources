# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::WorkingThread(void *)

- ea: `0x1400079a0`
- end: `0x1400079af`
- name: `?WorkingThread@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z`
- size: `15`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140006fe0`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::WorkingThread(
        __int64 StartContext)
{
  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::Run(StartContext);
}

```

## disassembly

```asm
0x1400079a0  sub     rsp, 28h
0x1400079a4  call    ?Run@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::Run(void)
0x1400079a9  add     rsp, 28h
0x1400079ad  retn
```
