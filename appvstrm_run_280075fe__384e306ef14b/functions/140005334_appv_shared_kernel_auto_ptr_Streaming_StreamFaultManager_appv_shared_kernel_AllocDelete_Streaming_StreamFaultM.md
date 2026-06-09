# appv::shared::kernel::auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>::~auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>(void)

- ea: `0x140005334`
- end: `0x14000539e`
- name: `??1?$auto_ptr@VStreamFaultManager@Streaming@@U?$AllocDelete@VStreamFaultManager@Streaming@@@kernel@shared@appv@@@kernel@shared@appv@@QEAA@XZ`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140005498`
- `0x14000571c`

## callees

- `0x140003aa8`
- `0x1400048a8`
- `0x140005334`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000537a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000537a`

## pseudocode

```c
void __fastcall appv::shared::kernel::auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>::~auto_ptr<Streaming::StreamFaultManager,appv::shared::kernel::AllocDelete<Streaming::StreamFaultManager>>(
        void **a1)
{
  void *v1; // rdi

  v1 = *a1;
  if ( *a1 )
  {
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool((__int64)v1);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool((__int64)v1 + 216);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>((__int64)v1 + 216);
    appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>((__int64)v1);
    ExFreePoolWithTag(v1, 0);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140005334  mov     [rsp+arg_0], rbx
0x140005339  mov     [rsp+arg_8], rsi
0x14000533e  push    rdi
0x14000533f  sub     rsp, 20h
0x140005343  mov     rdi, [rcx]
0x140005346  mov     rsi, rcx
0x140005349  test    rdi, rdi
0x14000534c  jz      short loc_14000538D
0x14000534e  mov     rcx, rdi
0x140005351  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x140005356  lea     rbx, [rdi+0D8h]
0x14000535d  mov     rcx, rbx
0x140005360  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x140005365  mov     rcx, rbx
0x140005368  call    ??1?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>(void)
0x14000536d  mov     rcx, rdi
0x140005370  call    ??1?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>(void)
0x140005375  xor     edx, edx; Tag
0x140005377  mov     rcx, rdi; P
0x14000537a  call    cs:__imp_ExFreePoolWithTag
0x140005381  nop     dword ptr [rax+rax+00h]
0x140005386  mov     qword ptr [rsi], 0
0x14000538d  mov     rbx, [rsp+28h+arg_0]
0x140005392  mov     rsi, [rsp+28h+arg_8]
0x140005397  add     rsp, 20h
0x14000539b  pop     rdi
0x14000539c  retn
```
