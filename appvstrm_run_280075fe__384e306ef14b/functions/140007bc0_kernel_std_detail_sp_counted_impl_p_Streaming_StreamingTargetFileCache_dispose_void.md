# kernel_std::detail::sp_counted_impl_p<Streaming::StreamingTargetFileCache>::dispose(void)

- ea: `0x140007bc0`
- end: `0x140007c1c`
- name: `?dispose@?$sp_counted_impl_p@VStreamingTargetFileCache@Streaming@@@detail@kernel_std@@UEAAXXZ`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140003b50`
- `0x140007bc0`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140007be1`
- `ntoskrnl!ExDeleteResourceLite` at `0x140007be1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007bf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007bf8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007c09`

## pseudocode

```c
void __fastcall kernel_std::detail::sp_counted_impl_p<Streaming::StreamingTargetFileCache>::dispose(__int64 a1)
{
  _QWORD *v1; // rbx
  struct _ERESOURCE *v2; // rcx
  void *v3; // rcx

  v1 = *(_QWORD **)(a1 + 16);
  if ( v1 )
  {
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(v1 + 2);
    v2 = (struct _ERESOURCE *)v1[1];
    if ( v2 )
    {
      ExDeleteResourceLite(v2);
      v3 = (void *)v1[1];
      if ( v3 )
        ExFreePoolWithTag(v3, 0);
    }
    ExFreePoolWithTag(v1, 0);
  }
}

```

## disassembly

```asm
0x140007bc0  push    rbx
0x140007bc2  sub     rsp, 20h
0x140007bc6  mov     rbx, [rcx+10h]
0x140007bca  test    rbx, rbx
0x140007bcd  jz      short loc_140007C15
0x140007bcf  lea     rcx, [rbx+10h]
0x140007bd3  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x140007bd8  mov     rcx, [rbx+8]; Resource
0x140007bdc  test    rcx, rcx
0x140007bdf  jz      short loc_140007C04
0x140007be1  call    cs:__imp_ExDeleteResourceLite
0x140007be8  nop     dword ptr [rax+rax+00h]
0x140007bed  mov     rcx, [rbx+8]; P
0x140007bf1  test    rcx, rcx
0x140007bf4  jz      short loc_140007C04
0x140007bf6  xor     edx, edx; Tag
0x140007bf8  call    cs:__imp_ExFreePoolWithTag
0x140007bff  nop     dword ptr [rax+rax+00h]
0x140007c04  xor     edx, edx; Tag
0x140007c06  mov     rcx, rbx; P
0x140007c09  call    cs:__imp_ExFreePoolWithTag
0x140007c10  nop     dword ptr [rax+rax+00h]
0x140007c15  add     rsp, 20h
0x140007c19  pop     rbx
0x140007c1a  retn
```
