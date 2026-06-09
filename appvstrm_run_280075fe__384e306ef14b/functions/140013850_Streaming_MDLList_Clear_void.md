# Streaming::MDLList::Clear(void)

- ea: `0x140013850`
- end: `0x1400138f5`
- name: `?Clear@MDLList@Streaming@@QEAAXXZ`
- size: `165`
- prototype: `void __fastcall(Streaming::MDLList *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x140013ed0`

## callees

- `0x140004c40`
- `0x140013850`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400138db`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400138db`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400138cf`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400138cf`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140013881`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140013881`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013869`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140013869`

## pseudocode

```c
void __fastcall Streaming::MDLList::Clear(PERESOURCE *this)
{
  bool v1; // di
  Streaming::MDLList *i; // rax
  struct _ERESOURCE *v4; // rcx
  Streaming::MDLList *v5; // [rsp+40h] [rbp+8h] BYREF
  __int64 v6; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  if ( this[1] )
  {
    KeEnterCriticalRegion();
    v1 = ExAcquireResourceExclusiveLite(this[1], 1u) == 1;
  }
  for ( i = (Streaming::MDLList *)this[6];
        i != (Streaming::MDLList *)(this + 3);
        i = (Streaming::MDLList *)*appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(
                                     (_DWORD *)this + 4,
                                     &v6,
                                     (__int64)&v5) )
  {
    v5 = i;
  }
  if ( v1 )
  {
    v4 = this[1];
    if ( v4 )
    {
      ExReleaseResourceLite(v4);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x140013850  mov     [rsp+arg_10], rbx
0x140013855  push    rbp
0x140013856  push    rsi
0x140013857  push    rdi
0x140013858  sub     rsp, 20h
0x14001385c  xor     dil, dil
0x14001385f  mov     rbx, rcx
0x140013862  cmp     qword ptr [rcx+8], 0
0x140013867  jz      short loc_140013897
0x140013869  call    cs:__imp_KeEnterCriticalRegion
0x140013870  nop     dword ptr [rax+rax+00h]
0x140013875  mov     rcx, [rbx+8]; Resource
0x140013879  mov     esi, 1
0x14001387e  mov     dl, sil; Wait
0x140013881  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140013888  nop     dword ptr [rax+rax+00h]
0x14001388d  cmp     al, sil
0x140013890  movzx   edi, dil
0x140013894  cmovz   edi, esi
0x140013897  mov     rax, [rbx+30h]
0x14001389b  lea     rbp, [rbx+18h]
0x14001389f  cmp     rax, rbp
0x1400138a2  jz      short loc_1400138C1
0x1400138a4  lea     r8, [rsp+38h+arg_0]
0x1400138a9  mov     [rsp+38h+arg_0], rax
0x1400138ae  lea     rdx, [rsp+38h+arg_8]
0x1400138b3  lea     rcx, [rbx+10h]
0x1400138b7  call    ?erase@?$doubly_linked_list@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@VFlushRequestTagInfo@Streaming@@@kernel@shared@appv@@QEAA?AV?$bidirectional_list_iterator@V?$dl_node_t@V?$shared_ptr@VFlushRequest@FlushRequestManager@Streaming@@@kernel_std@@@kernel@shared@appv@@@234@V5234@@Z; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>,Streaming::FlushRequestTagInfo>::erase(appv::shared::kernel::bidirectional_list_iterator<appv::shared::kernel::dl_node_t<kernel_std::shared_ptr<Streaming::FlushRequestManager::FlushRequest>>>)
0x1400138bc  mov     rax, [rax]
0x1400138bf  jmp     short loc_14001389F
0x1400138c1  test    dil, dil
0x1400138c4  jz      short loc_1400138E7
0x1400138c6  mov     rcx, [rbx+8]; Resource
0x1400138ca  test    rcx, rcx
0x1400138cd  jz      short loc_1400138E7
0x1400138cf  call    cs:__imp_ExReleaseResourceLite
0x1400138d6  nop     dword ptr [rax+rax+00h]
0x1400138db  call    cs:__imp_KeLeaveCriticalRegion
0x1400138e2  nop     dword ptr [rax+rax+00h]
0x1400138e7  mov     rbx, [rsp+38h+arg_10]
0x1400138ec  add     rsp, 20h
0x1400138f0  pop     rdi
0x1400138f1  pop     rsi
0x1400138f2  pop     rbp
0x1400138f3  retn
```
