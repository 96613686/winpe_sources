# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::WorkingThread(void *)

- ea: `0x14000efc0`
- end: `0x14000efcf`
- name: `?WorkingThread@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@SAXPEAX@Z`
- size: `15`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x14000e7f8`

## pseudocode

```c
void __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::WorkingThread(
        __int64 StartContext)
{
  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::Run(StartContext);
}

```

## disassembly

```asm
0x14000efc0  sub     rsp, 28h
0x14000efc4  call    ?Run@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@AEAAJXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::Run(void)
0x14000efc9  add     rsp, 28h
0x14000efcd  retn
```
