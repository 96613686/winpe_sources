# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>(void)

- ea: `0x140003aa8`
- end: `0x140003b48`
- name: `??1?$ThreadPool@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ`
- size: `160`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x140003d40`
- `0x140004c00`
- `0x140005334`

## callees

- `0x1400039e4`
- `0x140003aa8`
- `0x140003b50`
- `0x1400048a8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140003ae2`
- `ntoskrnl!ZwClose` at `0x140003ae2`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003b16`
- `ntoskrnl!ExDeleteResourceLite` at `0x140003b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003aca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b2d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003aca`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003b2d`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  struct _ERESOURCE *v4; // rcx
  void *v5; // rcx

  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(a1);
  v2 = *(void **)(a1 + 128);
  if ( v2 )
  {
    if ( *(_BYTE *)(a1 + 120) )
      ExFreePoolWithTag(v2, 0);
    v3 = *(void **)(a1 + 136);
    if ( v3 )
      ZwClose(v3);
    *(_QWORD *)(a1 + 128) = 0;
    *(_QWORD *)(a1 + 136) = 0;
  }
  appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::~ThreadHandles<Streaming::StreamFaultTagInfo>(a1 + 56);
  v4 = *(struct _ERESOURCE **)(a1 + 48);
  if ( v4 )
  {
    ExDeleteResourceLite(v4);
    v5 = *(void **)(a1 + 48);
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
  }
  return appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(a1);
}

```

## disassembly

```asm
0x140003aa8  push    rbx
0x140003aaa  sub     rsp, 20h
0x140003aae  mov     rbx, rcx
0x140003ab1  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFault@Streaming@@@kernel_std@@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFault>,Streaming::StreamFaultTagInfo>::StopThreadPool(void)
0x140003ab6  mov     rcx, [rbx+80h]; P
0x140003abd  test    rcx, rcx
0x140003ac0  jz      short loc_140003B04
0x140003ac2  cmp     byte ptr [rbx+78h], 0
0x140003ac6  jz      short loc_140003AD6
0x140003ac8  xor     edx, edx; Tag
0x140003aca  call    cs:__imp_ExFreePoolWithTag
0x140003ad1  nop     dword ptr [rax+rax+00h]
0x140003ad6  mov     rcx, [rbx+88h]; Handle
0x140003add  test    rcx, rcx
0x140003ae0  jz      short loc_140003AEE
0x140003ae2  call    cs:__imp_ZwClose
0x140003ae9  nop     dword ptr [rax+rax+00h]
0x140003aee  mov     qword ptr [rbx+80h], 0
0x140003af9  mov     qword ptr [rbx+88h], 0
0x140003b04  lea     rcx, [rbx+38h]
0x140003b08  call    ??1?$ThreadHandles@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::~ThreadHandles<Streaming::StreamFaultTagInfo>(void)
0x140003b0d  mov     rcx, [rbx+30h]; Resource
0x140003b11  test    rcx, rcx
0x140003b14  jz      short loc_140003B39
0x140003b16  call    cs:__imp_ExDeleteResourceLite
0x140003b1d  nop     dword ptr [rax+rax+00h]
0x140003b22  mov     rcx, [rbx+30h]; P
0x140003b26  test    rcx, rcx
0x140003b29  jz      short loc_140003B39
0x140003b2b  xor     edx, edx; Tag
0x140003b2d  call    cs:__imp_ExFreePoolWithTag
0x140003b34  nop     dword ptr [rax+rax+00h]
0x140003b39  mov     rcx, rbx
0x140003b3c  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x140003b41  add     rsp, 20h
0x140003b45  pop     rbx
0x140003b46  retn
```
