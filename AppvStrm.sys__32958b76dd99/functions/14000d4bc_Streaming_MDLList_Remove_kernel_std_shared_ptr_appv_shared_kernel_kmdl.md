# Streaming::MDLList::Remove(kernel_std::shared_ptr<appv::shared::kernel::kmdl> &)

- ea: `0x14000d4bc`
- end: `0x14000d59f`
- name: `?Remove@MDLList@Streaming@@QEAAJAEAV?$shared_ptr@Vkmdl@kernel@shared@appv@@@kernel_std@@@Z`
- size: `227`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, loader_planting`

## callers

- `0x14000d054`
- `0x14000d0c8`

## callees

- `0x140004c40`
- `0x14000d4bc`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d556`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d580`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d556`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d580`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d54a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d574`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d54a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d574`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d4f0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d4f0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d4d8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d4d8`

## pseudocode

```c
__int64 __fastcall Streaming::MDLList::Remove(__int64 a1, _QWORD *a2)
{
  bool v2; // di
  __int64 i; // rax
  struct _ERESOURCE *v6; // rcx
  struct _ERESOURCE *v8; // rcx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  __int64 v10; // [rsp+50h] [rbp+18h] BYREF

  v2 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 8), 1u) == 1;
  }
  for ( i = *(_QWORD *)(a1 + 48); i != a1 + 24; i = *(_QWORD *)(i + 24) )
  {
    if ( **(_QWORD **)i == *a2 )
    {
      v9 = i;
      appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
        (_DWORD *)(a1 + 16),
        &v10,
        (__int64)&v9);
      if ( v2 )
      {
        v6 = *(struct _ERESOURCE **)(a1 + 8);
        if ( v6 )
        {
          ExReleaseResourceLite(v6);
          KeLeaveCriticalRegion();
        }
      }
      return 0;
    }
  }
  if ( v2 )
  {
    v8 = *(struct _ERESOURCE **)(a1 + 8);
    if ( v8 )
    {
      ExReleaseResourceLite(v8);
      KeLeaveCriticalRegion();
    }
  }
  return 3221226021LL;
}

```

## disassembly

```asm
0x14000d4bc  mov     [rsp+arg_8], rbx
0x14000d4c1  push    rbp
0x14000d4c2  push    rsi
0x14000d4c3  push    rdi
0x14000d4c4  sub     rsp, 20h
0x14000d4c8  xor     dil, dil
0x14000d4cb  mov     rsi, rdx
0x14000d4ce  cmp     qword ptr [rcx+8], 0
0x14000d4d3  mov     rbx, rcx
0x14000d4d6  jz      short loc_14000D506
0x14000d4d8  call    cs:__imp_KeEnterCriticalRegion
0x14000d4df  nop     dword ptr [rax+rax+00h]
0x14000d4e4  mov     rcx, [rbx+8]; Resource
0x14000d4e8  mov     ebp, 1
0x14000d4ed  mov     dl, bpl; Wait
0x14000d4f0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000d4f7  nop     dword ptr [rax+rax+00h]
0x14000d4fc  cmp     al, bpl
0x14000d4ff  movzx   edi, dil
0x14000d503  cmovz   edi, ebp
0x14000d506  mov     rax, [rbx+30h]
0x14000d50a  lea     r8, [rbx+18h]
0x14000d50e  cmp     rax, r8
0x14000d511  jz      short loc_14000D566
0x14000d513  mov     rdx, [rax]
0x14000d516  mov     rcx, [rsi]
0x14000d519  cmp     [rdx], rcx
0x14000d51c  jz      short loc_14000D524
0x14000d51e  mov     rax, [rax+18h]
0x14000d522  jmp     short loc_14000D50E
0x14000d524  lea     r8, [rsp+38h+arg_0]
0x14000d529  mov     [rsp+38h+arg_0], rax
0x14000d52e  lea     rdx, [rsp+38h+arg_10]
0x14000d533  lea     rcx, [rbx+10h]
0x14000d537  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)
0x14000d53c  test    dil, dil
0x14000d53f  jz      short loc_14000D562
0x14000d541  mov     rcx, [rbx+8]; Resource
0x14000d545  test    rcx, rcx
0x14000d548  jz      short loc_14000D562
0x14000d54a  call    cs:__imp_ExReleaseResourceLite
0x14000d551  nop     dword ptr [rax+rax+00h]
0x14000d556  call    cs:__imp_KeLeaveCriticalRegion
0x14000d55d  nop     dword ptr [rax+rax+00h]
0x14000d562  xor     eax, eax
0x14000d564  jmp     short loc_14000D591
0x14000d566  test    dil, dil
0x14000d569  jz      short loc_14000D58C
0x14000d56b  mov     rcx, [rbx+8]; Resource
0x14000d56f  test    rcx, rcx
0x14000d572  jz      short loc_14000D58C
0x14000d574  call    cs:__imp_ExReleaseResourceLite
0x14000d57b  nop     dword ptr [rax+rax+00h]
0x14000d580  call    cs:__imp_KeLeaveCriticalRegion
0x14000d587  nop     dword ptr [rax+rax+00h]
0x14000d58c  mov     eax, 0C0000225h
0x14000d591  mov     rbx, [rsp+38h+arg_8]
0x14000d596  add     rsp, 20h
0x14000d59a  pop     rdi
0x14000d59b  pop     rsi
0x14000d59c  pop     rbp
0x14000d59d  retn
```
