# kernel_std::detail::sp_counted_impl_p<Streaming::PackageWriter>::dispose(void)

- ea: `0x140007ae0`
- end: `0x140007b37`
- name: `?dispose@?$sp_counted_impl_p@VPackageWriter@Streaming@@@detail@kernel_std@@UEAAXXZ`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000528c`
- `0x1400073b8`
- `0x140007ae0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007b1f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007b1f`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Streaming::PackageWriter>::dispose(__int64 a1)
{
  void *v1; // rdi

  v1 = *(void **)(a1 + 16);
  if ( v1 )
  {
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(*(_QWORD *)(a1 + 16));
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool((__int64)v1 + 216);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)v1 + 216);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)v1);
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x140007ae0  mov     [rsp+arg_0], rbx
0x140007ae5  push    rdi
0x140007ae6  sub     rsp, 20h
0x140007aea  mov     rdi, [rcx+10h]
0x140007aee  test    rdi, rdi
0x140007af1  jz      short loc_140007B2B
0x140007af3  mov     rcx, rdi
0x140007af6  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x140007afb  lea     rbx, [rdi+0D8h]
0x140007b02  mov     rcx, rbx
0x140007b05  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x140007b0a  mov     rcx, rbx
0x140007b0d  call    ??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x140007b12  mov     rcx, rdi
0x140007b15  call    ??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x140007b1a  xor     edx, edx; Tag
0x140007b1c  mov     rcx, rdi; P
0x140007b1f  call    cs:__imp_ExFreePoolWithTag
0x140007b26  nop     dword ptr [rax+rax+00h]
0x140007b2b  mov     rbx, [rsp+28h+arg_0]
0x140007b30  add     rsp, 20h
0x140007b34  pop     rdi
0x140007b35  retn
```
