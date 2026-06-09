# Streaming::MDLCache::~MDLCache(void)

- ea: `0x1400133f4`
- end: `0x14001353a`
- name: `??1MDLCache@Streaming@@QEAA@XZ`
- size: `326`
- prototype: `void __fastcall(PPAGED_LOOKASIDE_LIST Lookaside)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140013540`
- `0x1400135b4`

## callees

- `0x140003b50`
- `0x1400133f4`

## import_xrefs

- `ntoskrnl!ExDeletePagedLookasideList` at `0x140013446`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140013497`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400134e4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140013446`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x140013497`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400134e4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140013419`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001346a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400134bb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140013508`
- `ntoskrnl!ExDeleteResourceLite` at `0x140013419`
- `ntoskrnl!ExDeleteResourceLite` at `0x14001346a`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400134bb`
- `ntoskrnl!ExDeleteResourceLite` at `0x140013508`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013433`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013484`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400134d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013522`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013433`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013484`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400134d5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013522`

## pseudocode

```c
void __fastcall Streaming::MDLCache::~MDLCache(PPAGED_LOOKASIDE_LIST Lookaside)
{
  struct _ERESOURCE *Region; // rcx
  void *v3; // rcx
  struct _ERESOURCE *v4; // rcx
  void *v5; // rcx
  struct _ERESOURCE *v6; // rcx
  void *v7; // rcx
  struct _ERESOURCE *v8; // rcx
  void *v9; // rcx

  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)&Lookaside[6].L.Depth);
  Region = (struct _ERESOURCE *)Lookaside[6].L.ListHead.Region;
  if ( Region )
  {
    ExDeleteResourceLite(Region);
    v3 = (void *)Lookaside[6].L.ListHead.Region;
    if ( v3 )
      ExFreePoolWithTag(v3, 0);
  }
  ExDeletePagedLookasideList(Lookaside + 4);
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)&Lookaside[5].L.AllocateMisses);
  v4 = *(struct _ERESOURCE **)&Lookaside[5].L.Depth;
  if ( v4 )
  {
    ExDeleteResourceLite(v4);
    v5 = *(void **)&Lookaside[5].L.Depth;
    if ( v5 )
      ExFreePoolWithTag(v5, 0);
  }
  ExDeletePagedLookasideList(Lookaside + 2);
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)&Lookaside[3].L.AllocateMisses);
  v6 = *(struct _ERESOURCE **)&Lookaside[3].L.Depth;
  if ( v6 )
  {
    ExDeleteResourceLite(v6);
    v7 = *(void **)&Lookaside[3].L.Depth;
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
  }
  ExDeletePagedLookasideList(Lookaside);
  appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>((__int64)&Lookaside[1].L.AllocateMisses);
  v8 = *(struct _ERESOURCE **)&Lookaside[1].L.Depth;
  if ( v8 )
  {
    ExDeleteResourceLite(v8);
    v9 = *(void **)&Lookaside[1].L.Depth;
    if ( v9 )
      ExFreePoolWithTag(v9, 0);
  }
}

```

## disassembly

```asm
0x1400133f4  mov     [rsp+arg_0], rbx
0x1400133f9  push    rdi
0x1400133fa  sub     rsp, 20h
0x1400133fe  mov     rbx, rcx
0x140013401  add     rcx, 310h
0x140013408  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x14001340d  mov     rcx, [rbx+308h]; Resource
0x140013414  test    rcx, rcx
0x140013417  jz      short loc_14001343F
0x140013419  call    cs:__imp_ExDeleteResourceLite
0x140013420  nop     dword ptr [rax+rax+00h]
0x140013425  mov     rcx, [rbx+308h]; P
0x14001342c  test    rcx, rcx
0x14001342f  jz      short loc_14001343F
0x140013431  xor     edx, edx; Tag
0x140013433  call    cs:__imp_ExFreePoolWithTag
0x14001343a  nop     dword ptr [rax+rax+00h]
0x14001343f  lea     rcx, [rbx+200h]; Lookaside
0x140013446  call    cs:__imp_ExDeletePagedLookasideList
0x14001344d  nop     dword ptr [rax+rax+00h]
0x140013452  lea     rcx, [rbx+298h]
0x140013459  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x14001345e  mov     rcx, [rbx+290h]; Resource
0x140013465  test    rcx, rcx
0x140013468  jz      short loc_140013490
0x14001346a  call    cs:__imp_ExDeleteResourceLite
0x140013471  nop     dword ptr [rax+rax+00h]
0x140013476  mov     rcx, [rbx+290h]; P
0x14001347d  test    rcx, rcx
0x140013480  jz      short loc_140013490
0x140013482  xor     edx, edx; Tag
0x140013484  call    cs:__imp_ExFreePoolWithTag
0x14001348b  nop     dword ptr [rax+rax+00h]
0x140013490  lea     rcx, [rbx+100h]; Lookaside
0x140013497  call    cs:__imp_ExDeletePagedLookasideList
0x14001349e  nop     dword ptr [rax+rax+00h]
0x1400134a3  lea     rcx, [rbx+198h]
0x1400134aa  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x1400134af  mov     rcx, [rbx+190h]; Resource
0x1400134b6  test    rcx, rcx
0x1400134b9  jz      short loc_1400134E1
0x1400134bb  call    cs:__imp_ExDeleteResourceLite
0x1400134c2  nop     dword ptr [rax+rax+00h]
0x1400134c7  mov     rcx, [rbx+190h]; P
0x1400134ce  test    rcx, rcx
0x1400134d1  jz      short loc_1400134E1
0x1400134d3  xor     edx, edx; Tag
0x1400134d5  call    cs:__imp_ExFreePoolWithTag
0x1400134dc  nop     dword ptr [rax+rax+00h]
0x1400134e1  mov     rcx, rbx; Lookaside
0x1400134e4  call    cs:__imp_ExDeletePagedLookasideList
0x1400134eb  nop     dword ptr [rax+rax+00h]
0x1400134f0  lea     rcx, [rbx+98h]
0x1400134f7  call    ??1?$doubly_linked_list@V?$shared_ptr@VStreamFaultWriter@Streaming@@@kernel_std@@VStreamFaultWriterTagInfo@Streaming@@@kernel@shared@appv@@QEAA@XZ; appv::shared::kernel::doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>::~doubly_linked_list<kernel_std::shared_ptr<Streaming::StreamFaultWriter>,Streaming::StreamFaultWriterTagInfo>(void)
0x1400134fc  mov     rcx, [rbx+90h]; Resource
0x140013503  test    rcx, rcx
0x140013506  jz      short loc_14001352E
0x140013508  call    cs:__imp_ExDeleteResourceLite
0x14001350f  nop     dword ptr [rax+rax+00h]
0x140013514  mov     rcx, [rbx+90h]; P
0x14001351b  test    rcx, rcx
0x14001351e  jz      short loc_14001352E
0x140013520  xor     edx, edx; Tag
0x140013522  call    cs:__imp_ExFreePoolWithTag
0x140013529  nop     dword ptr [rax+rax+00h]
0x14001352e  mov     rbx, [rsp+28h+arg_0]
0x140013533  add     rsp, 20h
0x140013537  pop     rdi
0x140013538  retn
```
