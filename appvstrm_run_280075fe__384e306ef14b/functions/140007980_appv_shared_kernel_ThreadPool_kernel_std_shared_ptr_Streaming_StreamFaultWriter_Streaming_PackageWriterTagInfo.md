# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::WorkingThread(void *)

- ea: `0x140007980`
- end: `0x14000798f`
- name: `?WorkingThread@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z`
- size: `15`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140006c08`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::WorkingThread(
        __int64 StartContext)
{
  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::Run(StartContext);
}

```

## disassembly

```asm
0x140007980  sub     rsp, 28h
0x140007984  call    ?Run@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VPackageWriterTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::PackageWriterTagInfo>::Run(void)
0x140007989  add     rsp, 28h
0x14000798d  retn
```
