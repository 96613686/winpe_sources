# DqbGetEvents

- ea: `0x180002160`
- end: `0x180002462`
- name: `DqbGetEvents`
- size: `770`
- prototype: `__int64 __fastcall(__int64, UUID *, unsigned int *, unsigned int *, unsigned __int8 **, _DWORD *, void **, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001bfc`
- `0x180002160`
- `0x18000a192`
- `0x18000a19e`

## import_xrefs

- `msvcrt!_aligned_malloc` at `0x180002283`
- `msvcrt!_aligned_malloc` at `0x180002307`
- `msvcrt!_aligned_malloc` at `0x18000237a`
- `msvcrt!_aligned_malloc` at `0x180002283`
- `msvcrt!_aligned_malloc` at `0x180002307`
- `msvcrt!_aligned_malloc` at `0x18000237a`
- `msvcrt!_aligned_free` at `0x1800023f8`
- `msvcrt!_aligned_free` at `0x18000242e`
- `msvcrt!_aligned_free` at `0x18000243f`
- `msvcrt!_aligned_free` at `0x1800023f8`
- `msvcrt!_aligned_free` at `0x18000242e`
- `msvcrt!_aligned_free` at `0x18000243f`
- `RPCRT4!UuidCompare` at `0x1800021f3`
- `RPCRT4!UuidCompare` at `0x1800021f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002216`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180002216`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021be`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800021be`

## pseudocode

```c
__int64 __fastcall DqbGetEvents(
        __int64 a1,
        UUID *a2,
        unsigned int *a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        _DWORD *a6,
        void **a7,
        unsigned int *a8,
        void **a9)
{
  struct _LIST_ENTRY *v9; // rdi
  int v10; // ebx
  struct _LIST_ENTRY *i; // r14
  UUID **Blink; // rax
  struct _LIST_ENTRY *v13; // rax
  __int64 v14; // rcx
  void *v15; // rax
  __int64 v16; // r8
  struct _LIST_ENTRY *v17; // rdx
  struct _LIST_ENTRY *v18; // rax
  struct _LIST_ENTRY *Flink; // rcx
  void *v20; // rax
  struct _LIST_ENTRY *v21; // rax
  unsigned int v22; // ebp
  struct _LIST_ENTRY *v23; // rcx
  struct _LIST_ENTRY *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // r8
  _WORD *v27; // rdx
  struct _LIST_ENTRY *v28; // rax
  unsigned int j; // edi
  void *v30; // rcx
  RPC_STATUS Status; // [rsp+20h] [rbp-68h] BYREF
  UUID *Uuid1; // [rsp+28h] [rbp-60h]
  unsigned __int8 **v34; // [rsp+30h] [rbp-58h]
  unsigned int *v35; // [rsp+38h] [rbp-50h]
  unsigned int *v36; // [rsp+40h] [rbp-48h]

  v9 = 0;
  v10 = -2147024809;
  v34 = a5;
  v35 = a4;
  v36 = a3;
  Uuid1 = a2;
  EnterCriticalSection(&g_csActiveQueriesList);
  for ( i = g_activeQueriesList.Flink; i != &g_activeQueriesList; i = i->Flink )
  {
    if ( LODWORD(i[-1].Flink) )
    {
      Blink = (UUID **)i[-1].Blink;
      Status = 0;
      if ( !UuidCompare(Uuid1, *Blink + 3, &Status) )
      {
        v9 = i - 1;
        v10 = 0;
        break;
      }
    }
  }
  LeaveCriticalSection(&g_csActiveQueriesList);
  if ( v10 >= 0 )
  {
    if ( a6 )
    {
      if ( LODWORD(v9->Flink) == 1 )
        *a6 = v9->Blink->Flink[1].Flink;
      else
        *a6 = 0;
    }
    if ( a7 )
    {
      *a7 = 0;
      v13 = v9->Blink->Flink[1].Blink;
      if ( v13 )
      {
        v14 = -1;
        do
          ++v14;
        while ( *((_WORD *)&v13->Flink + v14) );
        v15 = _aligned_malloc(2 * v14 + 2, 0x10u);
        *a7 = v15;
        if ( !v15 )
        {
          v10 = -2147024882;
          goto LABEL_36;
        }
        v16 = -1;
        v17 = v9->Blink->Flink[1].Blink;
        do
          ++v16;
        while ( *((_WORD *)&v17->Flink + v16) );
        memcpy_0(v15, v17, 2 * v16 + 2);
      }
    }
    if ( a8 )
    {
      if ( a9 )
      {
        *a8 = 0;
        *a9 = 0;
        v18 = v9->Blink;
        Flink = v18->Flink;
        if ( LODWORD(v18->Flink[2].Flink) )
        {
          if ( Flink[2].Blink )
          {
            v20 = _aligned_malloc(8LL * LODWORD(Flink[2].Flink), 0x10u);
            *a9 = v20;
            if ( !v20 )
            {
LABEL_26:
              v10 = -2147024882;
              goto LABEL_35;
            }
            *a8 = (unsigned int)v9->Blink->Flink[2].Flink;
            memset_0(*a9, 0, 8LL * LODWORD(v9->Blink->Flink[2].Flink));
            v21 = v9->Blink;
            v22 = 0;
            v23 = v21->Flink;
            if ( LODWORD(v21->Flink[2].Flink) )
            {
              do
              {
                v24 = v23[2].Blink;
                v25 = -1;
                do
                  ++v25;
                while ( *(_WORD *)(*((_QWORD *)&v24->Flink + v22) + 2 * v25) );
                *((_QWORD *)*a9 + v22) = _aligned_malloc(2 * v25 + 2, 0x10u);
                if ( !*((_QWORD *)*a9 + v22) )
                  goto LABEL_26;
                v26 = -1;
                v27 = (_WORD *)*((_QWORD *)&v9->Blink->Flink[2].Blink->Flink + v22);
                do
                  ++v26;
                while ( v27[v26] );
                memcpy_0(*((void **)*a9 + v22), v27, 2 * v26 + 2);
                v28 = v9->Blink;
                ++v22;
                v23 = v28->Flink;
              }
              while ( v22 < LODWORD(v28->Flink[2].Flink) );
            }
          }
        }
      }
    }
    v10 = EncodeEvents((struct _BrokeredQueryContext *)v9, v36, v35, v34);
    if ( v10 >= 0 )
      return (unsigned int)v10;
  }
LABEL_35:
  if ( a7 )
  {
LABEL_36:
    if ( *a7 )
    {
      _aligned_free(*a7);
      *a7 = 0;
    }
  }
  if ( a8 && *a8 && a9 && *a9 )
  {
    for ( j = 0; j < *a8; ++j )
    {
      v30 = (void *)*((_QWORD *)*a9 + j);
      if ( v30 )
        _aligned_free(v30);
    }
    _aligned_free(*a9);
    *a9 = 0;
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180002160  mov     [rsp+arg_0], rbx
0x180002165  push    rbp
0x180002166  push    rsi
0x180002167  push    rdi
0x180002168  push    r12
0x18000216a  push    r13
0x18000216c  push    r14
0x18000216e  push    r15
0x180002170  sub     rsp, 50h
0x180002174  mov     rax, [rsp+88h+arg_20]
0x18000217c  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002183  mov     r15, [rsp+88h+arg_28]
0x18000218b  xor     edi, edi
0x18000218d  mov     r12, [rsp+88h+arg_30]
0x180002195  mov     ebx, 80070057h
0x18000219a  mov     r13, [rsp+88h+arg_38]
0x1800021a2  mov     rsi, [rsp+88h+arg_40]
0x1800021aa  mov     [rsp+88h+var_58], rax
0x1800021af  mov     [rsp+88h+var_50], r9
0x1800021b4  mov     [rsp+88h+var_48], r8
0x1800021b9  mov     [rsp+88h+Uuid1], rdx
0x1800021be  call    cs:__imp_EnterCriticalSection
0x1800021c4  mov     r14, cs:?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x1800021cb  lea     rax, ?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x1800021d2  jmp     short loc_180002207
0x1800021d4  cmp     [r14-10h], edi
0x1800021d8  jz      short loc_180002204
0x1800021da  mov     rax, [r14-8]
0x1800021de  lea     r8, [rsp+88h+Status]; Status
0x1800021e3  mov     rcx, [rsp+88h+Uuid1]; Uuid1
0x1800021e8  mov     [rsp+88h+Status], edi
0x1800021ec  mov     rdx, [rax]
0x1800021ef  add     rdx, 30h ; '0'; Uuid2
0x1800021f3  call    cs:__imp_UuidCompare
0x1800021f9  test    eax, eax
0x1800021fb  jz      short loc_18000223D
0x1800021fd  lea     rax, ?g_activeQueriesList@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_activeQueriesList
0x180002204  mov     r14, [r14]
0x180002207  cmp     r14, rax
0x18000220a  jnz     short loc_1800021D4
0x18000220c  xor     r14d, r14d
0x18000220f  lea     rcx, ?g_csActiveQueriesList@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180002216  call    cs:__imp_LeaveCriticalSection
0x18000221c  test    ebx, ebx
0x18000221e  js      loc_1800023EA
0x180002224  test    r15, r15
0x180002227  jz      short loc_18000224C
0x180002229  cmp     dword ptr [rdi], 1
0x18000222c  jnz     short loc_180002249
0x18000222e  mov     rax, [rdi+8]
0x180002232  mov     rcx, [rax]
0x180002235  mov     eax, [rcx+10h]
0x180002238  mov     [r15], eax
0x18000223b  jmp     short loc_18000224C
0x18000223d  lea     rdi, [r14-10h]
0x180002241  xor     r14d, r14d
0x180002244  mov     ebx, r14d
0x180002247  jmp     short loc_18000220F
0x180002249  mov     [r15], r14d
0x18000224c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180002250  test    r12, r12
0x180002253  jz      short loc_1800022C7
0x180002255  mov     [r12], r14
0x180002259  mov     rax, [rdi+8]
0x18000225d  mov     rcx, [rax]
0x180002260  mov     rax, [rcx+18h]
0x180002264  test    rax, rax
0x180002267  jz      short loc_1800022C7
0x180002269  mov     rcx, r15
0x18000226c  inc     rcx
0x18000226f  cmp     [rax+rcx*2], r14w
0x180002274  jnz     short loc_18000226C
0x180002276  lea     rcx, ds:2[rcx*2]; Size
0x18000227e  mov     edx, 10h; Alignment
0x180002283  call    cs:__imp__aligned_malloc
0x180002289  mov     [r12], rax
0x18000228d  mov     r9, rax
0x180002290  test    rax, rax
0x180002293  jnz     short loc_18000229F
0x180002295  mov     ebx, 8007000Eh
0x18000229a  jmp     loc_1800023EF
0x18000229f  mov     rax, [rdi+8]
0x1800022a3  mov     r8, r15
0x1800022a6  mov     rcx, [rax]
0x1800022a9  mov     rdx, [rcx+18h]; Src
0x1800022ad  inc     r8
0x1800022b0  cmp     [rdx+r8*2], r14w
0x1800022b5  jnz     short loc_1800022AD
0x1800022b7  lea     r8, ds:2[r8*2]; Size
0x1800022bf  mov     rcx, r9; void *
0x1800022c2  call    memcpy_0
0x1800022c7  test    r13, r13
0x1800022ca  jz      loc_1800023CD
0x1800022d0  test    rsi, rsi
0x1800022d3  jz      loc_1800023CD
0x1800022d9  mov     [r13+0], r14d
0x1800022dd  mov     [rsi], r14
0x1800022e0  mov     rax, [rdi+8]
0x1800022e4  mov     rcx, [rax]
0x1800022e7  cmp     [rcx+20h], r14d
0x1800022eb  jz      loc_1800023CD
0x1800022f1  cmp     [rcx+28h], r14
0x1800022f5  jz      loc_1800023CD
0x1800022fb  mov     ecx, [rcx+20h]
0x1800022fe  mov     edx, 10h; Alignment
0x180002303  shl     rcx, 3; Size
0x180002307  call    cs:__imp__aligned_malloc
0x18000230d  mov     [rsi], rax
0x180002310  test    rax, rax
0x180002313  jnz     short loc_18000231F
0x180002315  mov     ebx, 8007000Eh
0x18000231a  jmp     loc_1800023EA
0x18000231f  mov     rax, [rdi+8]
0x180002323  xor     edx, edx; Val
0x180002325  mov     rcx, [rax]
0x180002328  mov     eax, [rcx+20h]
0x18000232b  mov     [r13+0], eax
0x18000232f  mov     rax, [rdi+8]
0x180002333  mov     rcx, [rax]
0x180002336  mov     r8d, [rcx+20h]
0x18000233a  mov     rcx, [rsi]; void *
0x18000233d  shl     r8, 3; Size
0x180002341  call    memset_0
0x180002346  mov     rax, [rdi+8]
0x18000234a  mov     ebp, r14d
0x18000234d  mov     rcx, [rax]
0x180002350  cmp     [rcx+20h], r14d
0x180002354  jbe     short loc_1800023CD
0x180002356  mov     rax, [rcx+28h]
0x18000235a  mov     rcx, r15
0x18000235d  mov     ebx, ebp
0x18000235f  mov     rdx, [rax+rbx*8]
0x180002363  inc     rcx
0x180002366  cmp     [rdx+rcx*2], r14w
0x18000236b  jnz     short loc_180002363
0x18000236d  lea     rcx, ds:2[rcx*2]; Size
0x180002375  mov     edx, 10h; Alignment
0x18000237a  call    cs:__imp__aligned_malloc
0x180002380  mov     rcx, [rsi]
0x180002383  mov     [rcx+rbx*8], rax
0x180002387  mov     rax, [rsi]
0x18000238a  mov     r9, [rax+rbx*8]
0x18000238e  test    r9, r9
0x180002391  jz      short loc_180002315
0x180002393  mov     rax, [rdi+8]
0x180002397  mov     r8, r15
0x18000239a  mov     rcx, [rax]
0x18000239d  mov     rax, [rcx+28h]
0x1800023a1  mov     rdx, [rax+rbx*8]; Src
0x1800023a5  inc     r8
0x1800023a8  cmp     [rdx+r8*2], r14w
0x1800023ad  jnz     short loc_1800023A5
0x1800023af  lea     r8, ds:2[r8*2]; Size
0x1800023b7  mov     rcx, r9; void *
0x1800023ba  call    memcpy_0
0x1800023bf  mov     rax, [rdi+8]
0x1800023c3  inc     ebp
0x1800023c5  mov     rcx, [rax]
0x1800023c8  cmp     ebp, [rcx+20h]
0x1800023cb  jb      short loc_180002356
0x1800023cd  mov     r9, [rsp+88h+var_58]; unsigned __int8 **
0x1800023d2  mov     rcx, rdi; struct _BrokeredQueryContext *
0x1800023d5  mov     r8, [rsp+88h+var_50]; unsigned int *
0x1800023da  mov     rdx, [rsp+88h+var_48]; unsigned int *
0x1800023df  call    ?EncodeEvents@@YAJPEAU_BrokeredQueryContext@@PEAK1PEAPEAE@Z; EncodeEvents(_BrokeredQueryContext *,ulong *,ulong *,uchar * *)
0x1800023e4  mov     ebx, eax
0x1800023e6  test    eax, eax
0x1800023e8  jns     short loc_180002448
0x1800023ea  test    r12, r12
0x1800023ed  jz      short loc_180002402
0x1800023ef  mov     rcx, [r12]; Block
0x1800023f3  test    rcx, rcx
0x1800023f6  jz      short loc_180002402
0x1800023f8  call    cs:__imp__aligned_free
0x1800023fe  mov     [r12], r14
0x180002402  test    r13, r13
0x180002405  jz      short loc_180002448
0x180002407  cmp     [r13+0], r14d
0x18000240b  jz      short loc_180002448
0x18000240d  test    rsi, rsi
0x180002410  jz      short loc_180002448
0x180002412  cmp     [rsi], r14
0x180002415  jz      short loc_180002448
0x180002417  mov     edi, r14d
0x18000241a  cmp     [r13+0], r14d
0x18000241e  jbe     short loc_18000243C
0x180002420  mov     rax, [rsi]
0x180002423  mov     ecx, edi
0x180002425  mov     rcx, [rax+rcx*8]; Block
0x180002429  test    rcx, rcx
0x18000242c  jz      short loc_180002434
0x18000242e  call    cs:__imp__aligned_free
0x180002434  inc     edi
0x180002436  cmp     edi, [r13+0]
0x18000243a  jb      short loc_180002420
0x18000243c  mov     rcx, [rsi]; Block
0x18000243f  call    cs:__imp__aligned_free
0x180002445  mov     [rsi], r14
0x180002448  mov     eax, ebx
0x18000244a  mov     rbx, [rsp+88h+arg_0]
0x180002452  add     rsp, 50h
0x180002456  pop     r15
0x180002458  pop     r14
0x18000245a  pop     r13
0x18000245c  pop     r12
0x18000245e  pop     rdi
0x18000245f  pop     rsi
0x180002460  pop     rbp
0x180002461  retn
```
