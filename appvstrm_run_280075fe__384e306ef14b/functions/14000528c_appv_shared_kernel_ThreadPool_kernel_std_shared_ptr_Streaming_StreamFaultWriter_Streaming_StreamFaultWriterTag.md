# appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)

- ea: `0x14000528c`
- end: `0x14000532c`
- name: `??1?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ`
- size: `160`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x14000600c`
- `0x140006158`
- `0x140007ae0`
- `0x140007b80`

## callees

- `0x1400039e4`
- `0x140003b50`
- `0x14000528c`
- `0x1400073b8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x1400052c6`
- `ntoskrnl!ZwClose` at `0x1400052c6`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400052fa`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400052fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005311`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400052ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140005311`

## pseudocode

```c
__int64 __fastcall appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(
        __int64 a1)
{
  void *v2; // rcx
  void *v3; // rcx
  struct _ERESOURCE *v4; // rcx
  void *v5; // rcx

  appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(a1);
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
0x14000528c  push    rbx
0x14000528e  sub     rsp, 20h
0x140005292  mov     rbx, rcx
0x140005295  call    ?StopThreadPool@?$ThreadPool@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAAXXZ; appv::shared::kernel::ThreadPool<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::StopThreadPool(void)
0x14000529a  mov     rcx, [rbx+80h]; P
0x1400052a1  test    rcx, rcx
0x1400052a4  jz      short loc_1400052E8
0x1400052a6  cmp     byte ptr [rbx+78h], 0
0x1400052aa  jz      short loc_1400052BA
0x1400052ac  xor     edx, edx; Tag
0x1400052ae  call    cs:__imp_ExFreePoolWithTag
0x1400052b5  nop     dword ptr [rax+rax+00h]
0x1400052ba  mov     rcx, [rbx+88h]; Handle
0x1400052c1  test    rcx, rcx
0x1400052c4  jz      short loc_1400052D2
0x1400052c6  call    cs:__imp_ZwClose
0x1400052cd  nop     dword ptr [rax+rax+00h]
0x1400052d2  mov     qword ptr [rbx+80h], 0
0x1400052dd  mov     qword ptr [rbx+88h], 0
0x1400052e8  lea     rcx, [rbx+38h]
0x1400052ec  call    ??1?$ThreadHandles@VStreamFaultTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::ThreadHandles<Streaming::StreamFaultTagInfo>::~ThreadHandles<Streaming::StreamFaultTagInfo>(void)
0x1400052f1  mov     rcx, [rbx+30h]; Resource
0x1400052f5  test    rcx, rcx
0x1400052f8  jz      short loc_14000531D
0x1400052fa  call    cs:__imp_ExDeleteResourceLite
0x140005301  nop     dword ptr [rax+rax+00h]
0x140005306  mov     rcx, [rbx+30h]; P
0x14000530a  test    rcx, rcx
0x14000530d  jz      short loc_14000531D
0x14000530f  xor     edx, edx; Tag
0x140005311  call    cs:__imp_ExFreePoolWithTag
0x140005318  nop     dword ptr [rax+rax+00h]
0x14000531d  mov     rcx, rbx
0x140005320  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x140005325  add     rsp, 20h
0x140005329  pop     rbx
0x14000532a  retn
```
