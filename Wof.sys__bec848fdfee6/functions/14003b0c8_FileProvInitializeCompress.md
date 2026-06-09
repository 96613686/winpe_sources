# FileProvInitializeCompress

- ea: `0x14003b0c8`
- end: `0x14003b32a`
- name: `FileProvInitializeCompress`
- size: `610`
- prototype: `__int64 __fastcall(__int64, __int64, void *, void *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14003a528`

## callees

- `0x140007a30`
- `0x1400119c0`
- `0x14003b0c8`
- `0x14003b330`

## import_xrefs

- `ntoskrnl!KeQueryPriorityThread` at `0x14003b12b`
- `ntoskrnl!KeQueryPriorityThread` at `0x14003b12b`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b0e8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b185`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b0e8`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14003b185`
- `ntoskrnl!ObfReferenceObject` at `0x14003b151`
- `ntoskrnl!ObfReferenceObject` at `0x14003b167`
- `ntoskrnl!ObfReferenceObject` at `0x14003b151`
- `ntoskrnl!ObfReferenceObject` at `0x14003b167`
- `ntoskrnl!KeInitializeEvent` at `0x14003b257`
- `ntoskrnl!KeInitializeEvent` at `0x14003b257`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003b271`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003b271`

## pseudocode

```c
__int64 __fastcall FileProvInitializeCompress(__int64 a1, __int64 a2, void *a3, void *a4, __int64 *a5)
{
  _DWORD *v9; // rax
  _DWORD *v10; // rbx
  KPRIORITY PriorityThread; // eax
  __int64 v12; // rcx
  __int64 v13; // rax
  PVOID v14; // rax
  __int64 v15; // rbx
  __int64 *v16; // rax
  unsigned int v17; // ecx
  unsigned int v18; // r8d
  unsigned int v19; // r8d
  unsigned int v20; // eax
  PVOID PoolWithTag; // rax
  unsigned int i; // ebx
  __int64 v23; // r10
  __int64 result; // rax
  __int64 v25; // rcx

  v9 = ExAllocateFromNPagedLookasideList(&FileProvCompressContextLookaside);
  v10 = v9;
  *a5 = (__int64)v9;
  if ( !v9 )
    return 3221225626LL;
  memset(v9, 0, 0x130u);
  v10[4] = 4;
  PriorityThread = KeQueryPriorityThread(KeGetCurrentThread());
  v12 = *a5;
  *(_DWORD *)(v12 + 56) = PriorityThread;
  *(_DWORD *)(v12 + 52) = FileProvNumberProcessors;
  *(_QWORD *)(v12 + 64) = *(_QWORD *)(a2 + 24);
  ObfReferenceObject(a4);
  *(_QWORD *)(*a5 + 72) = a4;
  ObfReferenceObject(a3);
  v13 = *a5;
  *(_QWORD *)(v13 + 80) = a3;
  *(_QWORD *)(v13 + 88) = a1;
  v14 = ExAllocateFromNPagedLookasideList(&FileProvCompressWorkitemsLookaside);
  v15 = *a5;
  *(_QWORD *)(*a5 + 232) = v14;
  if ( !v14 )
    return 3221225626LL;
  memset(*(void **)(v15 + 232), 0, 136LL * (unsigned int)FileProvNumberProcessors);
  v16 = FileProvCompressionScheme(a1);
  *(_QWORD *)(v15 + 8) = v16;
  v17 = (*(unsigned int *)v16 + *(_QWORD *)(a1 + 8) - 1LL) / *(unsigned int *)v16 - 1;
  *(_DWORD *)(v15 + 20) = v17;
  if ( *(_DWORD *)(a1 + 12) )
    *(_DWORD *)(v15 + 16) = 8;
  v18 = *(_DWORD *)(v15 + 16);
  if ( v17 >= 0xFFDFEFFF / v18 )
    return 3221226535LL;
  v19 = (v17 * v18 + 4095) & 0xFFFFF000;
  *(_DWORD *)(v15 + 108) = v19;
  *(_DWORD *)(v15 + 104) = v19 + 0x200000;
  if ( *(__int64 *)(a1 + 8) < 0x200000 )
  {
    v20 = v19 + (-*(_DWORD *)v16 & (*(_DWORD *)v16 + *(_DWORD *)(a1 + 8) - 1));
    if ( v19 + 0x200000 > v20 )
      *(_DWORD *)(v15 + 104) = v20;
  }
  KeInitializeEvent((PRKEVENT)(v15 + 120), SynchronizationEvent, 0);
  PoolWithTag = ExAllocatePoolWithTag(PagedPool, *(unsigned int *)(*a5 + 104), 0x44527066u);
  *(_QWORD *)(*a5 + 96) = PoolWithTag;
  if ( !PoolWithTag )
    return 3221225626LL;
  for ( i = 0; ; ++i )
  {
    v23 = *a5;
    if ( i >= *(_DWORD *)(*a5 + 52) )
      break;
    result = FileProvInitializeCompressWorkItem(
               *(_QWORD *)(v23 + 8),
               *(unsigned int *)(a1 + 4),
               a2,
               *(_QWORD *)(v23 + 232) + 136LL * i);
    if ( (int)result < 0 )
      return result;
  }
  v25 = (unsigned int)(*(_DWORD *)(v23 + 16) * *(_DWORD *)(v23 + 20));
  *(_DWORD *)(v23 + 48) = v25;
  *(_QWORD *)(v23 + 24) = *(_QWORD *)(v23 + 96) + v25;
  *(_QWORD *)(v23 + 32) = 0;
  *(_QWORD *)(v23 + 40) = 0;
  *(_QWORD *)(v23 + 240) = *(_QWORD *)(v23 + 232) + 136LL * *(unsigned int *)(v23 + 248);
  return 0;
}

```

## disassembly

```asm
0x14003b0c8  push    rbx
0x14003b0ca  push    rbp
0x14003b0cb  push    rsi
0x14003b0cc  push    rdi
0x14003b0cd  push    r14
0x14003b0cf  push    r15
0x14003b0d1  sub     rsp, 28h
0x14003b0d5  mov     rsi, rcx
0x14003b0d8  mov     rbp, r9
0x14003b0db  lea     rcx, FileProvCompressContextLookaside; Lookaside
0x14003b0e2  mov     r14, r8
0x14003b0e5  mov     r15, rdx
0x14003b0e8  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b0ef  nop     dword ptr [rax+rax+00h]
0x14003b0f4  mov     rdi, [rsp+58h+arg_20]
0x14003b0fc  mov     rbx, rax
0x14003b0ff  mov     [rdi], rax
0x14003b102  test    rax, rax
0x14003b105  jz      loc_14003B310
0x14003b10b  xor     edx, edx; Val
0x14003b10d  mov     r8d, 130h; Size
0x14003b113  mov     rcx, rax; void *
0x14003b116  call    memset
0x14003b11b  mov     dword ptr [rbx+10h], 4
0x14003b122  mov     rcx, gs:188h; Thread
0x14003b12b  call    cs:__imp_KeQueryPriorityThread
0x14003b132  nop     dword ptr [rax+rax+00h]
0x14003b137  mov     rcx, [rdi]
0x14003b13a  mov     [rcx+38h], eax
0x14003b13d  mov     eax, cs:FileProvNumberProcessors
0x14003b143  mov     [rcx+34h], eax
0x14003b146  mov     rax, [r15+18h]
0x14003b14a  mov     [rcx+40h], rax
0x14003b14e  mov     rcx, rbp; Object
0x14003b151  call    cs:__imp_ObfReferenceObject
0x14003b158  nop     dword ptr [rax+rax+00h]
0x14003b15d  mov     rax, [rdi]
0x14003b160  mov     rcx, r14; Object
0x14003b163  mov     [rax+48h], rbp
0x14003b167  call    cs:__imp_ObfReferenceObject
0x14003b16e  nop     dword ptr [rax+rax+00h]
0x14003b173  mov     rax, [rdi]
0x14003b176  lea     rcx, FileProvCompressWorkitemsLookaside; Lookaside
0x14003b17d  mov     [rax+50h], r14
0x14003b181  mov     [rax+58h], rsi
0x14003b185  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14003b18c  nop     dword ptr [rax+rax+00h]
0x14003b191  mov     rbx, [rdi]
0x14003b194  mov     [rbx+0E8h], rax
0x14003b19b  test    rax, rax
0x14003b19e  jz      loc_14003B310
0x14003b1a4  mov     eax, cs:FileProvNumberProcessors
0x14003b1aa  xor     edx, edx; Val
0x14003b1ac  mov     rcx, [rbx+0E8h]; void *
0x14003b1b3  imul    r8, rax, 88h; Size
0x14003b1ba  call    memset
0x14003b1bf  mov     rcx, rsi
0x14003b1c2  call    FileProvCompressionScheme
0x14003b1c7  mov     [rbx+8], rax
0x14003b1cb  mov     r10, rax
0x14003b1ce  mov     r8d, [rax]
0x14003b1d1  mov     rax, [rsi+8]
0x14003b1d5  dec     rax
0x14003b1d8  add     rax, r8
0x14003b1db  cqo
0x14003b1dd  idiv    r8
0x14003b1e0  lea     ecx, [rax-1]
0x14003b1e3  mov     [rbx+14h], ecx
0x14003b1e6  cmp     dword ptr [rsi+0Ch], 0
0x14003b1ea  jnz     loc_14003B31E
0x14003b1f0  mov     r8d, [rbx+10h]
0x14003b1f4  xor     edx, edx
0x14003b1f6  mov     eax, 0FFDFEFFFh
0x14003b1fb  div     r8d
0x14003b1fe  cmp     ecx, eax
0x14003b200  jnb     loc_14003B317
0x14003b206  imul    r8d, ecx
0x14003b20a  add     r8d, 0FFFh
0x14003b211  and     r8d, 0FFFFF000h
0x14003b218  mov     [rbx+6Ch], r8d
0x14003b21c  lea     r9d, [r8+200000h]
0x14003b223  mov     [rbx+68h], r9d
0x14003b227  cmp     qword ptr [rsi+8], 200000h
0x14003b22f  jge     short loc_14003B24A
0x14003b231  mov     edx, [r10]
0x14003b234  mov     eax, [rsi+8]
0x14003b237  dec     eax
0x14003b239  add     eax, edx
0x14003b23b  neg     edx
0x14003b23d  and     eax, edx
0x14003b23f  add     eax, r8d
0x14003b242  cmp     r9d, eax
0x14003b245  jbe     short loc_14003B24A
0x14003b247  mov     [rbx+68h], eax
0x14003b24a  xor     r8d, r8d; State
0x14003b24d  lea     rcx, [rbx+78h]; Event
0x14003b251  lea     ebp, [r8+1]
0x14003b255  mov     edx, ebp; Type
0x14003b257  call    cs:__imp_KeInitializeEvent
0x14003b25e  nop     dword ptr [rax+rax+00h]
0x14003b263  mov     rax, [rdi]
0x14003b266  mov     r8d, 44527066h; Tag
0x14003b26c  mov     ecx, ebp; PoolType
0x14003b26e  mov     edx, [rax+68h]; NumberOfBytes
0x14003b271  call    cs:__imp_ExAllocatePoolWithTag
0x14003b278  nop     dword ptr [rax+rax+00h]
0x14003b27d  mov     rcx, [rdi]
0x14003b280  mov     [rcx+60h], rax
0x14003b284  test    rax, rax
0x14003b287  jz      loc_14003B310
0x14003b28d  xor     ebx, ebx
0x14003b28f  mov     r10, [rdi]
0x14003b292  cmp     ebx, [r10+34h]
0x14003b296  jnb     short loc_14003B2BF
0x14003b298  mov     edx, [rsi+4]
0x14003b29b  mov     r8, r15
0x14003b29e  mov     rcx, [r10+8]
0x14003b2a2  mov     eax, ebx
0x14003b2a4  imul    r9, rax, 88h
0x14003b2ab  add     r9, [r10+0E8h]
0x14003b2b2  call    FileProvInitializeCompressWorkItem
0x14003b2b7  test    eax, eax
0x14003b2b9  js      short loc_14003B302
0x14003b2bb  add     ebx, ebp
0x14003b2bd  jmp     short loc_14003B28F
0x14003b2bf  mov     ecx, [r10+14h]
0x14003b2c3  imul    ecx, [r10+10h]
0x14003b2c8  mov     [r10+30h], ecx
0x14003b2cc  add     rcx, [r10+60h]
0x14003b2d0  mov     [r10+18h], rcx
0x14003b2d4  mov     qword ptr [r10+20h], 0
0x14003b2dc  mov     qword ptr [r10+28h], 0
0x14003b2e4  mov     eax, [r10+0F8h]
0x14003b2eb  imul    rcx, rax, 88h
0x14003b2f2  add     rcx, [r10+0E8h]
0x14003b2f9  mov     [r10+0F0h], rcx
0x14003b300  xor     eax, eax
0x14003b302  add     rsp, 28h
0x14003b306  pop     r15
0x14003b308  pop     r14
0x14003b30a  pop     rdi
0x14003b30b  pop     rsi
0x14003b30c  pop     rbp
0x14003b30d  pop     rbx
0x14003b30e  retn
0x14003b310  mov     eax, 0C000009Ah
0x14003b315  jmp     short loc_14003B302
0x14003b317  mov     eax, 0C0000427h
0x14003b31c  jmp     short loc_14003B302
0x14003b31e  mov     dword ptr [rbx+10h], 8
0x14003b325  jmp     loc_14003B1F0
```
