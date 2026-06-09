# appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::remove_directory(appv::shared::vfs::prefix_tree_table &)

- ea: `0x140012130`
- end: `0x14001240b`
- name: `?remove_directory@?$prefix_tree@VPrefixTreeContext@@VPrefixTreeAllocator@@@vfs@shared@appv@@CAXAEAUprefix_tree_table@234@@Z`
- size: `731`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x140011998`

## callees

- `0x140011a64`
- `0x140012130`

## import_xrefs

- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400121c0`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14001220c`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14001226a`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x1400121c0`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14001220c`
- `ntoskrnl!RtlIsGenericTableEmptyAvl` at `0x14001226a`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001216c`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400121d5`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400123b2`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x14001216c`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400121d5`
- `ntoskrnl!RtlEnumerateGenericTableAvl` at `0x1400123b2`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400122f3`
- `ntoskrnl!RtlLookupElementGenericTableAvl` at `0x1400122f3`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001215a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140012321`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140012364`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400123a1`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14001215a`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140012321`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x140012364`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x1400123a1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400121a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012247`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400122a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001233c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001237f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400121a4`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012247`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400122a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001233c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001237f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400123e9`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012193`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012236`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012294`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400123d8`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012193`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012236`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x140012294`
- `ntoskrnl!ExFreeToPagedLookasideList` at `0x1400123d8`

## pseudocode

```c
void __fastcall appv::shared::vfs::prefix_tree<PrefixTreeContext,PrefixTreeAllocator>::remove_directory(PVOID *a1)
{
  PRTL_AVL_TABLE *v2; // rdi
  PRTL_AVL_TABLE *i; // rbx
  struct _RTL_AVL_TABLE *v4; // rcx
  PVOID v5; // rax
  struct _RTL_AVL_TABLE *v6; // rcx
  struct _RTL_AVL_TABLE *v7; // rcx
  struct _RTL_AVL_TABLE *v8; // rcx
  PRTL_AVL_TABLE *v9; // r15
  struct _RTL_AVL_TABLE *v10; // rcx
  _QWORD *v11; // rax
  _QWORD *v12; // r8
  void *v13; // rsi
  char *v14; // rdx
  PRTL_AVL_TABLE v15; // rsi
  struct _RTL_AVL_TABLE *v16; // rcx
  PVOID v17; // rax
  struct _RTL_AVL_TABLE *v18; // rcx

  v2 = (PRTL_AVL_TABLE *)a1;
  for ( i = 0; ; i = v2 - 16 )
  {
    while ( 1 )
    {
      v4 = v2[1];
      if ( v4 )
      {
        while ( 1 )
        {
          v5 = RtlEnumerateGenericTableAvl(v4, 1u);
          v6 = v2[1];
          if ( !v5 )
            break;
          RtlDeleteElementGenericTableAvl(v6, v5);
          v4 = v2[1];
        }
        if ( PrefixTreeAllocator::LookasideInited )
          ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, v2[1]);
        else
          ExFreePoolWithTag(v6, 0x30704656u);
        v2[1] = 0;
      }
      if ( !*v2 || RtlIsGenericTableEmptyAvl(*v2) )
        break;
      i = (PRTL_AVL_TABLE *)RtlEnumerateGenericTableAvl(*v2, 1u);
      v2 = i + 16;
    }
    if ( v2 == (PRTL_AVL_TABLE *)a1 )
      break;
    v7 = i[16];
    v2 = (PRTL_AVL_TABLE *)i[18];
    if ( v7 && RtlIsGenericTableEmptyAvl(v7) )
    {
      if ( PrefixTreeAllocator::LookasideInited )
        ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, i[16]);
      else
        ExFreePoolWithTag(i[16], 0x30704656u);
      i[16] = 0;
    }
    v8 = i[17];
    if ( v8 && RtlIsGenericTableEmptyAvl(v8) )
    {
      if ( PrefixTreeAllocator::LookasideInited )
        ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, i[17]);
      else
        ExFreePoolWithTag(i[17], 0x30704656u);
      i[17] = 0;
    }
    if ( *((_BYTE *)i + 152) )
    {
      PrefixTreeContext::~PrefixTreeContext((PrefixTreeContext *)(i + 20));
      *((_BYTE *)i + 152) = 0;
    }
    v9 = (PRTL_AVL_TABLE *)i[18];
    v10 = v9[1];
    if ( v10 )
    {
      if ( *((_WORD *)i + 44) )
      {
        v11 = RtlLookupElementGenericTableAvl(v10, i + 11);
        if ( v11 )
        {
          v12 = (_QWORD *)v11[1];
          v13 = 0;
          if ( v12 && v12 != v11 + 2 )
            v13 = (void *)v11[1];
          if ( RtlDeleteElementGenericTableAvl(v9[1], v11) && v13 )
            ExFreePoolWithTag(v13, 0x30704656u);
        }
      }
    }
    v14 = (char *)i[1];
    v15 = 0;
    if ( v14 && v14 != (char *)(i + 2) )
      v15 = i[1];
    if ( RtlDeleteElementGenericTableAvl(*v9, i) )
    {
      if ( v15 )
        ExFreePoolWithTag(v15, 0x30704656u);
    }
  }
  v16 = (struct _RTL_AVL_TABLE *)*a1;
  if ( *a1 )
  {
    while ( 1 )
    {
      v17 = RtlEnumerateGenericTableAvl(v16, 1u);
      v18 = (struct _RTL_AVL_TABLE *)*a1;
      if ( !v17 )
        break;
      RtlDeleteElementGenericTableAvl(v18, v17);
      v16 = (struct _RTL_AVL_TABLE *)*a1;
    }
    if ( PrefixTreeAllocator::LookasideInited )
      ExFreeToPagedLookasideList(&PrefixTreeAllocator::PrefixTableLookasideList, *a1);
    else
      ExFreePoolWithTag(v18, 0x30704656u);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x140012130  push    rbx
0x140012132  push    rsi
0x140012133  push    rdi
0x140012134  push    r12
0x140012136  push    r14
0x140012138  push    r15
0x14001213a  sub     rsp, 28h
0x14001213e  mov     r14, rcx
0x140012141  mov     rdi, rcx
0x140012144  xor     ebx, ebx
0x140012146  mov     r12d, 30704656h
0x14001214c  mov     rcx, [rdi+8]
0x140012150  test    rcx, rcx
0x140012153  jz      short loc_1400121B8
0x140012155  jmp     short loc_14001216A
0x140012157  mov     rdx, rax; Buffer
0x14001215a  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140012161  nop     dword ptr [rax+rax+00h]
0x140012166  mov     rcx, [rdi+8]; Table
0x14001216a  mov     dl, 1; Restart
0x14001216c  call    cs:__imp_RtlEnumerateGenericTableAvl
0x140012173  nop     dword ptr [rax+rax+00h]
0x140012178  mov     rcx, [rdi+8]; P
0x14001217c  test    rax, rax
0x14001217f  jnz     short loc_140012157
0x140012181  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, al; bool PrefixTreeAllocator::LookasideInited
0x140012187  jz      short loc_1400121A1
0x140012189  mov     rdx, rcx; Entry
0x14001218c  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012193  call    cs:__imp_ExFreeToPagedLookasideList
0x14001219a  nop     dword ptr [rax+rax+00h]
0x14001219f  jmp     short loc_1400121B0
0x1400121a1  mov     edx, r12d; Tag
0x1400121a4  call    cs:__imp_ExFreePoolWithTag
0x1400121ab  nop     dword ptr [rax+rax+00h]
0x1400121b0  mov     qword ptr [rdi+8], 0
0x1400121b8  mov     rcx, [rdi]; Table
0x1400121bb  test    rcx, rcx
0x1400121be  jz      short loc_1400121F0
0x1400121c0  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x1400121c7  nop     dword ptr [rax+rax+00h]
0x1400121cc  test    al, al
0x1400121ce  jnz     short loc_1400121F0
0x1400121d0  mov     rcx, [rdi]; Table
0x1400121d3  mov     dl, 1; Restart
0x1400121d5  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400121dc  nop     dword ptr [rax+rax+00h]
0x1400121e1  mov     rbx, rax
0x1400121e4  lea     rdi, [rax+80h]
0x1400121eb  jmp     loc_14001214C
0x1400121f0  cmp     rdi, r14
0x1400121f3  jz      loc_140012394
0x1400121f9  mov     rcx, [rbx+80h]; Table
0x140012200  mov     rdi, [rbx+90h]
0x140012207  test    rcx, rcx
0x14001220a  jz      short loc_14001225E
0x14001220c  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140012213  nop     dword ptr [rax+rax+00h]
0x140012218  test    al, al
0x14001221a  jz      short loc_14001225E
0x14001221c  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140012223  mov     rcx, [rbx+80h]; P
0x14001222a  jz      short loc_140012244
0x14001222c  mov     rdx, rcx; Entry
0x14001222f  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012236  call    cs:__imp_ExFreeToPagedLookasideList
0x14001223d  nop     dword ptr [rax+rax+00h]
0x140012242  jmp     short loc_140012253
0x140012244  mov     edx, r12d; Tag
0x140012247  call    cs:__imp_ExFreePoolWithTag
0x14001224e  nop     dword ptr [rax+rax+00h]
0x140012253  mov     qword ptr [rbx+80h], 0
0x14001225e  mov     rcx, [rbx+88h]; Table
0x140012265  test    rcx, rcx
0x140012268  jz      short loc_1400122BC
0x14001226a  call    cs:__imp_RtlIsGenericTableEmptyAvl
0x140012271  nop     dword ptr [rax+rax+00h]
0x140012276  test    al, al
0x140012278  jz      short loc_1400122BC
0x14001227a  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, 0; bool PrefixTreeAllocator::LookasideInited
0x140012281  mov     rcx, [rbx+88h]; P
0x140012288  jz      short loc_1400122A2
0x14001228a  mov     rdx, rcx; Entry
0x14001228d  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x140012294  call    cs:__imp_ExFreeToPagedLookasideList
0x14001229b  nop     dword ptr [rax+rax+00h]
0x1400122a0  jmp     short loc_1400122B1
0x1400122a2  mov     edx, r12d; Tag
0x1400122a5  call    cs:__imp_ExFreePoolWithTag
0x1400122ac  nop     dword ptr [rax+rax+00h]
0x1400122b1  mov     qword ptr [rbx+88h], 0
0x1400122bc  cmp     byte ptr [rbx+98h], 0
0x1400122c3  jz      short loc_1400122D8
0x1400122c5  lea     rcx, [rbx+0A0h]; this
0x1400122cc  call    ??1PrefixTreeContext@@QEAA@XZ; PrefixTreeContext::~PrefixTreeContext(void)
0x1400122d1  mov     byte ptr [rbx+98h], 0
0x1400122d8  mov     r15, [rbx+90h]
0x1400122df  mov     rcx, [r15+8]; Table
0x1400122e3  test    rcx, rcx
0x1400122e6  jz      short loc_140012348
0x1400122e8  lea     rdx, [rbx+58h]; Buffer
0x1400122ec  xor     eax, eax
0x1400122ee  cmp     ax, [rdx]
0x1400122f1  jz      short loc_140012348
0x1400122f3  call    cs:__imp_RtlLookupElementGenericTableAvl
0x1400122fa  nop     dword ptr [rax+rax+00h]
0x1400122ff  test    rax, rax
0x140012302  jz      short loc_140012348
0x140012304  mov     r8, [rax+8]
0x140012308  xor     esi, esi
0x14001230a  mov     rcx, [r15+8]; Table
0x14001230e  test    r8, r8
0x140012311  jz      short loc_14001231E
0x140012313  lea     rdx, [rax+10h]
0x140012317  cmp     r8, rdx
0x14001231a  cmovnz  rsi, r8
0x14001231e  mov     rdx, rax; Buffer
0x140012321  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x140012328  nop     dword ptr [rax+rax+00h]
0x14001232d  test    al, al
0x14001232f  jz      short loc_140012348
0x140012331  test    rsi, rsi
0x140012334  jz      short loc_140012348
0x140012336  mov     edx, r12d; Tag
0x140012339  mov     rcx, rsi; P
0x14001233c  call    cs:__imp_ExFreePoolWithTag
0x140012343  nop     dword ptr [rax+rax+00h]
0x140012348  mov     rdx, [rbx+8]
0x14001234c  xor     esi, esi
0x14001234e  mov     rcx, [r15]; Table
0x140012351  test    rdx, rdx
0x140012354  jz      short loc_140012361
0x140012356  lea     rax, [rbx+10h]
0x14001235a  cmp     rdx, rax
0x14001235d  cmovnz  rsi, rdx
0x140012361  mov     rdx, rbx; Buffer
0x140012364  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x14001236b  nop     dword ptr [rax+rax+00h]
0x140012370  test    al, al
0x140012372  jz      short loc_14001238B
0x140012374  test    rsi, rsi
0x140012377  jz      short loc_14001238B
0x140012379  mov     edx, r12d; Tag
0x14001237c  mov     rcx, rsi; P
0x14001237f  call    cs:__imp_ExFreePoolWithTag
0x140012386  nop     dword ptr [rax+rax+00h]
0x14001238b  lea     rbx, [rdi-80h]
0x14001238f  jmp     loc_14001214C
0x140012394  mov     rcx, [r14]
0x140012397  test    rcx, rcx
0x14001239a  jz      short loc_1400123FC
0x14001239c  jmp     short loc_1400123B0
0x14001239e  mov     rdx, rax; Buffer
0x1400123a1  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x1400123a8  nop     dword ptr [rax+rax+00h]
0x1400123ad  mov     rcx, [r14]; Table
0x1400123b0  mov     dl, 1; Restart
0x1400123b2  call    cs:__imp_RtlEnumerateGenericTableAvl
0x1400123b9  nop     dword ptr [rax+rax+00h]
0x1400123be  mov     rcx, [r14]; P
0x1400123c1  test    rax, rax
0x1400123c4  jnz     short loc_14001239E
0x1400123c6  cmp     cs:?LookasideInited@PrefixTreeAllocator@@0_NA, al; bool PrefixTreeAllocator::LookasideInited
0x1400123cc  jz      short loc_1400123E6
0x1400123ce  mov     rdx, rcx; Entry
0x1400123d1  lea     rcx, ?PrefixTableLookasideList@PrefixTreeAllocator@@0U_PAGED_LOOKASIDE_LIST@@A; Lookaside
0x1400123d8  call    cs:__imp_ExFreeToPagedLookasideList
0x1400123df  nop     dword ptr [rax+rax+00h]
0x1400123e4  jmp     short loc_1400123F5
0x1400123e6  mov     edx, r12d; Tag
0x1400123e9  call    cs:__imp_ExFreePoolWithTag
0x1400123f0  nop     dword ptr [rax+rax+00h]
0x1400123f5  mov     qword ptr [r14], 0
0x1400123fc  add     rsp, 28h
0x140012400  pop     r15
0x140012402  pop     r14
0x140012404  pop     r12
0x140012406  pop     rdi
0x140012407  pop     rsi
0x140012408  pop     rbx
0x140012409  retn
```
