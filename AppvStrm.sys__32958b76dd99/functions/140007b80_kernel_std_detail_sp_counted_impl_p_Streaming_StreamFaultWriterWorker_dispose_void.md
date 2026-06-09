# kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriterWorker>::dispose(void)

- ea: `0x140007b80`
- end: `0x140007bb7`
- name: `?dispose@?$sp_counted_impl_p@VStreamFaultWriterWorker@Streaming@@@detail@kernel_std@@UEAAXXZ`
- size: `55`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000528c`
- `0x1400073b8`
- `0x140007b80`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007ba4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ba4`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Streaming::StreamFaultWriterWorker>::dispose(__int64 a1)
{
  void *v1; // rbx

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(*(_QWORD *)(a1 + 16));
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)v1);
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x140007b80  push    rbx
0x140007b82  sub     rsp, 20h
0x140007b86  mov     rbx, [rcx+10h]
0x140007b8a  test    rbx, rbx
0x140007b8d  jz      short loc_140007BB0
0x140007b8f  mov     rcx, rbx
0x140007b92  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x140007b97  mov     rcx, rbx
0x140007b9a  call    ??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x140007b9f  xor     edx, edx; Tag
0x140007ba1  mov     rcx, rbx; P
0x140007ba4  call    cs:__imp_ExFreePoolWithTag
0x140007bab  nop     dword ptr [rax+rax+00h]
0x140007bb0  add     rsp, 20h
0x140007bb4  pop     rbx
0x140007bb5  retn
```
