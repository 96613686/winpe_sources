# Streaming::StreamingTargetFileCache::Clear(Streaming::StrmInstanceContext *)

- ea: `0x140011bf8`
- end: `0x140011caa`
- name: `?Clear@StreamingTargetFileCache@Streaming@@QEAAXPEAUStrmInstanceContext@2@@Z`
- size: `178`
- prototype: `void __fastcall(Streaming::StreamingTargetFileCache *__hidden this, struct Streaming::StrmInstanceContext *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140005d68`

## callees

- `0x1400041cc`
- `0x140004c40`
- `0x140011bf8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c90`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140011c90`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c84`
- `ntoskrnl!ExReleaseResourceLite` at `0x140011c84`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140011c2c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140011c2c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011c14`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140011c14`

## pseudocode

```c
void __fastcall Streaming::StreamingTargetFileCache::Clear(PERESOURCE *this, struct Streaming::StrmInstanceContext *a2)
{
  bool v2; // di
  struct _ERESOURCE *v5; // rcx
  PERESOURCE v6; // [rsp+40h] [rbp+8h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  if ( this[1] )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(this[1], 1u) == 1;
  }
  while ( *((_DWORD *)this + 4) )
  {
    Streaming::FlushRequestManager::Process(*((_QWORD *)a2 + 36), this[6]);
    v6 = this[6];
    appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
      (_DWORD *)this + 4,
      &v7,
      (__int64)&v6);
  }
  if ( v2 )
  {
    v5 = this[1];
    if ( v5 )
    {
      ExReleaseResourceLite(v5);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x140011bf8  mov     [rsp+arg_8], rbx
0x140011bfd  push    rbp
0x140011bfe  push    rsi
0x140011bff  push    rdi
0x140011c00  sub     rsp, 20h
0x140011c04  xor     dil, dil
0x140011c07  mov     rbp, rdx
0x140011c0a  cmp     qword ptr [rcx+8], 0
0x140011c0f  mov     rbx, rcx
0x140011c12  jz      short loc_140011C42
0x140011c14  call    cs:__imp_KeEnterCriticalRegion
0x140011c1b  nop     dword ptr [rax+rax+00h]
0x140011c20  mov     rcx, [rbx+8]; Resource
0x140011c24  mov     esi, 1
0x140011c29  mov     dl, sil; Wait
0x140011c2c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140011c33  nop     dword ptr [rax+rax+00h]
0x140011c38  cmp     al, sil
0x140011c3b  movzx   edi, dil
0x140011c3f  cmovz   edi, esi
0x140011c42  cmp     dword ptr [rbx+10h], 0
0x140011c46  jz      short loc_140011C76
0x140011c48  mov     rdx, [rbx+30h]
0x140011c4c  mov     rcx, [rbp+120h]
0x140011c53  call    ?Process@FlushRequestManager@Streaming@@QEAAJAEAV?$shared_ptr@VStreamingTargetFileObject@Streaming@@@kernel_std@@@Z; Streaming::FlushRequestManager::Process(kernel_std::shared_ptr<Streaming::StreamingTargetFileObject> &)
0x140011c58  mov     rax, [rbx+30h]
0x140011c5c  lea     r8, [rsp+38h+arg_0]
0x140011c61  lea     rdx, [rsp+38h+arg_10]
0x140011c66  mov     [rsp+38h+arg_0], rax
0x140011c6b  lea     rcx, [rbx+10h]
0x140011c6f  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)
0x140011c74  jmp     short loc_140011C42
0x140011c76  test    dil, dil
0x140011c79  jz      short loc_140011C9C
0x140011c7b  mov     rcx, [rbx+8]; Resource
0x140011c7f  test    rcx, rcx
0x140011c82  jz      short loc_140011C9C
0x140011c84  call    cs:__imp_ExReleaseResourceLite
0x140011c8b  nop     dword ptr [rax+rax+00h]
0x140011c90  call    cs:__imp_KeLeaveCriticalRegion
0x140011c97  nop     dword ptr [rax+rax+00h]
0x140011c9c  mov     rbx, [rsp+38h+arg_8]
0x140011ca1  add     rsp, 20h
0x140011ca5  pop     rdi
0x140011ca6  pop     rsi
0x140011ca7  pop     rbp
0x140011ca8  retn
```
