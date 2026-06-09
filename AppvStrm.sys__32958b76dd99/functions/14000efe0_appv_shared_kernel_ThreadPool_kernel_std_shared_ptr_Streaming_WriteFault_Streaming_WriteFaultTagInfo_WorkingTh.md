# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::WorkingThread(void *)

- ea: `0x14000efe0`
- end: `0x14000efef`
- name: `?WorkingThread@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z`
- size: `15`
- prototype: `void __fastcall(__int64 StartContext)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000ebd0`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::WorkingThread(
        __int64 StartContext)
{
  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Run(StartContext);
}

```

## disassembly

```asm
0x14000efe0  sub     rsp, 28h
0x14000efe4  call    ?Run@?$ThreadPool@V?$shared_ptr@VWriteFault@Streaming@@@kernel_std@@VWriteFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::WriteFault>,Streaming::WriteFaultTagInfo>::Run(void)
0x14000efe9  add     rsp, 28h
0x14000efed  retn
```
