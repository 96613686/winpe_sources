# CQuery::CopyParameters(_DEV_OBJECT_TYPE,ulong,ulong,ushort const * *,ulong,_DEVPROPCOMPKEY const *,ulong,_DEVPROP_FILTER_EXPRESSION const *,ulong,_DEV_QUERY_PARAMETER const *,ushort const *)

- ea: `0x180003454`
- end: `0x180003836`
- name: `?CopyParameters@CQuery@@IEAAJW4_DEV_OBJECT_TYPE@@KKPEAPEBGKPEBU_DEVPROPCOMPKEY@@KPEBU_DEVPROP_FILTER_EXPRESSION@@KPEBU_DEV_QUERY_PARAMETER@@PEBG@Z`
- size: `994`
- prototype: `__int64 __fastcall(__int64, int, int, unsigned int, __int64, unsigned int, char *Src, unsigned int, char *, unsigned int, unsigned int *, _WORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000383c`

## callees

- `0x180003454`
- `0x180003e50`
- `0x18000a192`
- `0x18000a19e`

## import_xrefs

- `msvcrt!malloc` at `0x18000348f`
- `msvcrt!malloc` at `0x1800034d9`
- `msvcrt!malloc` at `0x180003537`
- `msvcrt!malloc` at `0x18000358c`
- `msvcrt!malloc` at `0x1800035eb`
- `msvcrt!malloc` at `0x180003656`
- `msvcrt!malloc` at `0x1800036a1`
- `msvcrt!malloc` at `0x18000370a`
- `msvcrt!malloc` at `0x180003764`
- `msvcrt!malloc` at `0x1800037be`
- `msvcrt!malloc` at `0x18000348f`
- `msvcrt!malloc` at `0x1800034d9`
- `msvcrt!malloc` at `0x180003537`
- `msvcrt!malloc` at `0x18000358c`
- `msvcrt!malloc` at `0x1800035eb`
- `msvcrt!malloc` at `0x180003656`
- `msvcrt!malloc` at `0x1800036a1`
- `msvcrt!malloc` at `0x18000370a`
- `msvcrt!malloc` at `0x180003764`
- `msvcrt!malloc` at `0x1800037be`

## pseudocode

```c
__int64 __fastcall CQuery::CopyParameters(
        __int64 a1,
        int a2,
        int a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        char *Src,
        unsigned int a8,
        char *a9,
        unsigned int a10,
        unsigned int *a11,
        _WORD *a12)
{
  __int64 v13; // r15
  void *v15; // rax
  __int64 v16; // r8
  unsigned int v17; // ebp
  __int64 v18; // rcx
  void *v19; // rcx
  _WORD *v20; // rdx
  __int64 v21; // r8
  void *v22; // rax
  unsigned int i; // ebp
  __int64 v24; // rsi
  __int64 v25; // rax
  __int64 v26; // rcx
  void *v27; // rcx
  _WORD *v28; // rdx
  __int64 v29; // r8
  void *v30; // rax
  unsigned int v31; // edx
  __int64 v32; // rax
  __int64 v33; // rcx
  unsigned int j; // r14d
  __int64 v35; // rsi
  __int64 v36; // rbx
  __int64 v37; // rax
  void *v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rcx
  void *v41; // rcx
  _WORD *v42; // rdx
  __int64 v43; // r8
  void *v44; // rax
  unsigned int k; // edx
  __int64 v46; // rax
  unsigned int m; // esi
  void *v48; // rcx
  unsigned int v49; // ebx
  __int64 v50; // rcx
  void *v51; // rax

  v13 = -1;
  *(_DWORD *)(a1 + 16) = a2;
  *(_DWORD *)(a1 + 72) = a3 | 1;
  if ( a4 )
  {
    v15 = malloc(8LL * a4);
    *(_QWORD *)(a1 + 40) = v15;
    if ( !v15 )
      goto LABEL_53;
    memset_0(v15, 0, 8LL * a4);
    v17 = 0;
    if ( a4 )
    {
      do
      {
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(*(_QWORD *)(a5 + 8LL * v17) + 2 * v18) );
        *(_QWORD *)(*(_QWORD *)(a1 + 40) + 8LL * v17) = malloc(2 * v18 + 2);
        v19 = *(void **)(*(_QWORD *)(a1 + 40) + 8LL * v17);
        if ( !v19 )
          goto LABEL_53;
        v20 = *(_WORD **)(a5 + 8LL * v17);
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        memcpy_0(v19, v20, 2 * v21 + 2);
      }
      while ( ++v17 < a4 );
    }
    *(_DWORD *)(a1 + 32) = a4;
  }
  if ( a6 )
  {
    v22 = malloc(32LL * a6);
    *(_QWORD *)(a1 + 80) = v22;
    if ( !v22 )
      goto LABEL_53;
    memcpy_0(v22, Src, 32LL * a6);
    for ( i = 0; i < a6; ++i )
    {
      v24 = 32LL * i;
      v25 = *(_QWORD *)&Src[v24 + 24];
      if ( v25 )
      {
        v26 = -1;
        do
          ++v26;
        while ( *(_WORD *)(v25 + 2 * v26) );
        *(_QWORD *)(v24 + *(_QWORD *)(a1 + 80) + 24) = malloc(2 * v26 + 2);
        v27 = *(void **)(v24 + *(_QWORD *)(a1 + 80) + 24);
        if ( !v27 )
          goto LABEL_53;
        v28 = *(_WORD **)&Src[v24 + 24];
        v29 = -1;
        do
          ++v29;
        while ( v28[v29] );
        memcpy_0(v27, v28, 2 * v29 + 2);
      }
    }
    *(_DWORD *)(a1 + 76) = a6;
  }
  if ( a8 )
  {
    v30 = malloc(56LL * a8);
    *(_QWORD *)(a1 + 96) = v30;
    if ( !v30 )
      goto LABEL_53;
    memcpy_0(v30, a9, 56LL * a8);
    v31 = 0;
    do
    {
      v32 = v31++;
      v33 = 56 * v32;
      *(_QWORD *)(v33 + *(_QWORD *)(a1 + 96) + 48) = 0;
      *(_QWORD *)(*(_QWORD *)(a1 + 96) + v33 + 32) = 0;
    }
    while ( v31 < a8 );
    for ( j = 0; j < a8; ++j )
    {
      v35 = 56LL * j;
      if ( *(_QWORD *)&a9[v35 + 48] )
      {
        v36 = *(_QWORD *)(a1 + 96);
        *(_QWORD *)(v36 + v35 + 48) = malloc(*(unsigned int *)(v36 + v35 + 44));
        v37 = *(_QWORD *)(a1 + 96);
        v38 = *(void **)(v37 + v35 + 48);
        if ( !v38 )
          goto LABEL_53;
        memcpy_0(v38, *(const void **)&a9[v35 + 48], *(unsigned int *)(v37 + v35 + 44));
      }
      v39 = *(_QWORD *)&a9[v35 + 32];
      if ( v39 )
      {
        v40 = -1;
        do
          ++v40;
        while ( *(_WORD *)(v39 + 2 * v40) );
        *(_QWORD *)(*(_QWORD *)(a1 + 96) + v35 + 32) = malloc(2 * v40 + 2);
        v41 = *(void **)(*(_QWORD *)(a1 + 96) + v35 + 32);
        if ( !v41 )
          goto LABEL_53;
        v42 = *(_WORD **)&a9[v35 + 32];
        v43 = -1;
        do
          ++v43;
        while ( v42[v43] );
        memcpy_0(v41, v42, 2 * v43 + 2);
      }
    }
    *(_DWORD *)(a1 + 88) = a8;
  }
  if ( !a10 )
    goto LABEL_49;
  v44 = malloc(40LL * a10);
  *(_QWORD *)(a1 + 112) = v44;
  if ( !v44 )
  {
LABEL_53:
    v49 = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v16, 2147942414LL, a1);
    return v49;
  }
  memcpy_0(v44, a11, 40LL * a10);
  for ( k = 0; k < a10; ++k )
  {
    v46 = k;
    *(_QWORD *)(*(_QWORD *)(a1 + 112) + 40 * v46 + 32) = 0;
  }
  for ( m = 0; m < a10; ++m )
  {
    if ( *(_QWORD *)&a11[10 * m + 8] )
    {
      *(_QWORD *)(*(_QWORD *)(a1 + 112) + 40LL * m + 32) = malloc(a11[10 * m + 6]);
      v48 = *(void **)(*(_QWORD *)(a1 + 112) + 40LL * m + 32);
      if ( !v48 )
        goto LABEL_53;
      memcpy_0(v48, *(const void **)&a11[10 * m + 8], a11[10 * m + 6]);
    }
    *(_DWORD *)(a1 + 104) = a10;
  }
LABEL_49:
  v49 = 0;
  if ( !a12 )
    return v49;
  v50 = -1;
  do
    ++v50;
  while ( a12[v50] );
  v51 = malloc(2 * v50 + 2);
  *(_QWORD *)(a1 + 24) = v51;
  if ( !v51 )
    goto LABEL_53;
  do
    ++v13;
  while ( a12[v13] );
  memcpy_0(v51, a12, 2 * v13 + 2);
  return v49;
}

```

## disassembly

```asm
0x180003454  push    rbx
0x180003456  push    rbp
0x180003457  push    rsi
0x180003458  push    rdi
0x180003459  push    r12
0x18000345b  push    r13
0x18000345d  push    r14
0x18000345f  push    r15
0x180003461  sub     rsp, 38h
0x180003465  or      r8d, 1
0x180003469  mov     esi, r9d
0x18000346c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003470  mov     [rcx+10h], edx
0x180003473  xor     r13d, r13d
0x180003476  mov     [rcx+48h], r8d
0x18000347a  mov     rdi, rcx
0x18000347d  test    r9d, r9d
0x180003480  jz      loc_18000351F
0x180003486  mov     ebx, esi
0x180003488  shl     rbx, 3
0x18000348c  mov     rcx, rbx; Size
0x18000348f  call    cs:__imp_malloc
0x180003495  mov     [rdi+28h], rax
0x180003499  test    rax, rax
0x18000349c  jz      loc_1800037CD
0x1800034a2  mov     r14, [rsp+78h+arg_20]
0x1800034aa  mov     r8, rbx; Size
0x1800034ad  xor     edx, edx; Val
0x1800034af  mov     rcx, rax; void *
0x1800034b2  call    memset_0
0x1800034b7  mov     ebp, r13d
0x1800034ba  test    esi, esi
0x1800034bc  jz      short loc_18000351C
0x1800034be  mov     ebx, ebp
0x1800034c0  mov     rcx, r15
0x1800034c3  mov     rax, [r14+rbx*8]
0x1800034c7  inc     rcx
0x1800034ca  cmp     [rax+rcx*2], r13w
0x1800034cf  jnz     short loc_1800034C7
0x1800034d1  lea     rcx, ds:2[rcx*2]; Size
0x1800034d9  call    cs:__imp_malloc
0x1800034df  mov     rcx, [rdi+28h]
0x1800034e3  mov     [rcx+rbx*8], rax
0x1800034e7  mov     rax, [rdi+28h]
0x1800034eb  mov     rcx, [rax+rbx*8]; void *
0x1800034ef  test    rcx, rcx
0x1800034f2  jz      loc_1800037CD
0x1800034f8  mov     rdx, [r14+rbx*8]; Src
0x1800034fc  mov     r8, r15
0x1800034ff  inc     r8
0x180003502  cmp     [rdx+r8*2], r13w
0x180003507  jnz     short loc_1800034FF
0x180003509  lea     r8, ds:2[r8*2]; Size
0x180003511  call    memcpy_0
0x180003516  inc     ebp
0x180003518  cmp     ebp, esi
0x18000351a  jb      short loc_1800034BE
0x18000351c  mov     [rdi+20h], esi
0x18000351f  mov     ebx, [rsp+78h+arg_28]
0x180003526  test    ebx, ebx
0x180003528  jz      loc_1800035D5
0x18000352e  mov     esi, ebx
0x180003530  shl     rsi, 5
0x180003534  mov     rcx, rsi; Size
0x180003537  call    cs:__imp_malloc
0x18000353d  mov     [rdi+50h], rax
0x180003541  test    rax, rax
0x180003544  jz      loc_1800037CD
0x18000354a  mov     r14, [rsp+78h+Src]
0x180003552  mov     r8, rsi; Size
0x180003555  mov     rdx, r14; Src
0x180003558  mov     rcx, rax; void *
0x18000355b  call    memcpy_0
0x180003560  mov     ebp, r13d
0x180003563  test    ebx, ebx
0x180003565  jz      short loc_1800035D2
0x180003567  mov     esi, ebp
0x180003569  shl     rsi, 5
0x18000356d  mov     rax, [rsi+r14+18h]
0x180003572  test    rax, rax
0x180003575  jz      short loc_1800035CC
0x180003577  mov     rcx, r15
0x18000357a  inc     rcx
0x18000357d  cmp     [rax+rcx*2], r13w
0x180003582  jnz     short loc_18000357A
0x180003584  lea     rcx, ds:2[rcx*2]; Size
0x18000358c  call    cs:__imp_malloc
0x180003592  mov     rcx, [rdi+50h]
0x180003596  mov     [rsi+rcx+18h], rax
0x18000359b  mov     rax, [rdi+50h]
0x18000359f  mov     rcx, [rsi+rax+18h]; void *
0x1800035a4  test    rcx, rcx
0x1800035a7  jz      loc_1800037CD
0x1800035ad  mov     rdx, [rsi+r14+18h]; Src
0x1800035b2  mov     r8, r15
0x1800035b5  inc     r8
0x1800035b8  cmp     [rdx+r8*2], r13w
0x1800035bd  jnz     short loc_1800035B5
0x1800035bf  lea     r8, ds:2[r8*2]; Size
0x1800035c7  call    memcpy_0
0x1800035cc  inc     ebp
0x1800035ce  cmp     ebp, ebx
0x1800035d0  jb      short loc_180003567
0x1800035d2  mov     [rdi+4Ch], ebx
0x1800035d5  mov     ebp, [rsp+78h+arg_38]
0x1800035dc  test    ebp, ebp
0x1800035de  jz      loc_1800036F0
0x1800035e4  imul    rbx, rbp, 38h ; '8'
0x1800035e8  mov     rcx, rbx; Size
0x1800035eb  call    cs:__imp_malloc
0x1800035f1  mov     [rdi+60h], rax
0x1800035f5  test    rax, rax
0x1800035f8  jz      loc_1800037CD
0x1800035fe  mov     r12, [rsp+78h+arg_40]
0x180003606  mov     r8, rbx; Size
0x180003609  mov     rdx, r12; Src
0x18000360c  mov     rcx, rax; void *
0x18000360f  call    memcpy_0
0x180003614  mov     edx, r13d
0x180003617  test    ebp, ebp
0x180003619  jz      loc_1800036ED
0x18000361f  mov     eax, edx
0x180003621  inc     edx
0x180003623  imul    rcx, rax, 38h ; '8'
0x180003627  mov     rax, [rdi+60h]
0x18000362b  mov     [rcx+rax+30h], r13
0x180003630  mov     rax, [rdi+60h]
0x180003634  mov     [rax+rcx+20h], r13
0x180003639  cmp     edx, ebp
0x18000363b  jb      short loc_18000361F
0x18000363d  mov     r14d, r13d
0x180003640  mov     eax, r14d
0x180003643  imul    rsi, rax, 38h ; '8'
0x180003647  cmp     [r12+rsi+30h], r13
0x18000364c  jz      short loc_180003682
0x18000364e  mov     rbx, [rdi+60h]
0x180003652  mov     ecx, [rbx+rsi+2Ch]; Size
0x180003656  call    cs:__imp_malloc
0x18000365c  mov     [rbx+rsi+30h], rax
0x180003661  mov     rax, [rdi+60h]
0x180003665  mov     rcx, [rax+rsi+30h]; void *
0x18000366a  test    rcx, rcx
0x18000366d  jz      loc_1800037CD
0x180003673  mov     r8d, [rax+rsi+2Ch]; Size
0x180003678  mov     rdx, [r12+rsi+30h]; Src
0x18000367d  call    memcpy_0
0x180003682  mov     rax, [r12+rsi+20h]
0x180003687  test    rax, rax
0x18000368a  jz      short loc_1800036E1
0x18000368c  mov     rcx, r15
0x18000368f  inc     rcx
0x180003692  cmp     [rax+rcx*2], r13w
0x180003697  jnz     short loc_18000368F
0x180003699  lea     rcx, ds:2[rcx*2]; Size
0x1800036a1  call    cs:__imp_malloc
0x1800036a7  mov     rcx, [rdi+60h]
0x1800036ab  mov     [rcx+rsi+20h], rax
0x1800036b0  mov     rax, [rdi+60h]
0x1800036b4  mov     rcx, [rax+rsi+20h]; void *
0x1800036b9  test    rcx, rcx
0x1800036bc  jz      loc_1800037CD
0x1800036c2  mov     rdx, [r12+rsi+20h]; Src
0x1800036c7  mov     r8, r15
0x1800036ca  inc     r8
0x1800036cd  cmp     [rdx+r8*2], r13w
0x1800036d2  jnz     short loc_1800036CA
0x1800036d4  lea     r8, ds:2[r8*2]; Size
0x1800036dc  call    memcpy_0
0x1800036e1  inc     r14d
0x1800036e4  cmp     r14d, ebp
0x1800036e7  jb      loc_180003640
0x1800036ed  mov     [rdi+58h], ebp
0x1800036f0  mov     ebx, [rsp+78h+arg_48]
0x1800036f7  test    ebx, ebx
0x1800036f9  jz      loc_180003799
0x1800036ff  lea     rsi, [rbx+rbx*4]
0x180003703  shl     rsi, 3
0x180003707  mov     rcx, rsi; Size
0x18000370a  call    cs:__imp_malloc
0x180003710  mov     [rdi+70h], rax
0x180003714  test    rax, rax
0x180003717  jz      loc_1800037CD
0x18000371d  mov     r14, [rsp+78h+arg_50]
0x180003725  mov     r8, rsi; Size
0x180003728  mov     rdx, r14; Src
0x18000372b  mov     rcx, rax; void *
0x18000372e  call    memcpy_0
0x180003733  mov     edx, r13d
0x180003736  test    ebx, ebx
0x180003738  jz      short loc_180003799
0x18000373a  mov     eax, edx
0x18000373c  inc     edx
0x18000373e  lea     rcx, [rax+rax*4]
0x180003742  mov     rax, [rdi+70h]
0x180003746  mov     [rax+rcx*8+20h], r13
0x18000374b  cmp     edx, ebx
0x18000374d  jb      short loc_18000373A
0x18000374f  mov     esi, r13d
0x180003752  mov     eax, esi
0x180003754  lea     rbp, [rax+rax*4]
0x180003758  cmp     [r14+rbp*8+20h], r13
0x18000375d  jz      short loc_180003790
0x18000375f  mov     ecx, [r14+rbp*8+18h]; Size
0x180003764  call    cs:__imp_malloc
0x18000376a  mov     rcx, [rdi+70h]
0x18000376e  mov     [rcx+rbp*8+20h], rax
0x180003773  mov     rax, [rdi+70h]
0x180003777  mov     rcx, [rax+rbp*8+20h]; void *
0x18000377c  test    rcx, rcx
0x18000377f  jz      short loc_1800037CD
0x180003781  mov     r8d, [r14+rbp*8+18h]; Size
0x180003786  mov     rdx, [r14+rbp*8+20h]; Src
0x18000378b  call    memcpy_0
0x180003790  inc     esi
0x180003792  mov     [rdi+68h], ebx
0x180003795  cmp     esi, ebx
0x180003797  jb      short loc_180003752
0x180003799  mov     rsi, [rsp+78h+arg_58]
0x1800037a1  mov     ebx, r13d
0x1800037a4  test    rsi, rsi
0x1800037a7  jz      short loc_180003823
0x1800037a9  mov     rcx, r15
0x1800037ac  inc     rcx
0x1800037af  cmp     [rsi+rcx*2], r13w
0x1800037b4  jnz     short loc_1800037AC
0x1800037b6  lea     rcx, ds:2[rcx*2]; Size
0x1800037be  call    cs:__imp_malloc
0x1800037c4  mov     [rdi+18h], rax
0x1800037c8  test    rax, rax
0x1800037cb  jnz     short loc_180003806
0x1800037cd  mov     ebx, 8007000Eh
0x1800037d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037d9  lea     rax, WPP_GLOBAL_Control
0x1800037e0  cmp     rcx, rax
0x1800037e3  jz      short loc_180003823
0x1800037e5  cmp     byte ptr [rcx+19h], 2
0x1800037e9  jb      short loc_180003823
0x1800037eb  mov     rcx, [rcx+10h]
0x1800037ef  mov     edx, 0Ch
0x1800037f4  mov     r9d, 8007000Eh
0x1800037fa  mov     [rsp+78h+var_58], rdi
0x1800037ff  call    WPP_SF_Dq
0x180003804  jmp     short loc_180003823
0x180003806  inc     r15
0x180003809  cmp     [rsi+r15*2], r13w
0x18000380e  jnz     short loc_180003806
0x180003810  lea     r8, ds:2[r15*2]; Size
0x180003818  mov     rdx, rsi; Src
0x18000381b  mov     rcx, rax; void *
0x18000381e  call    memcpy_0
0x180003823  mov     eax, ebx
0x180003825  add     rsp, 38h
0x180003829  pop     r15
0x18000382b  pop     r14
0x18000382d  pop     r13
0x18000382f  pop     r12
0x180003831  pop     rdi
0x180003832  pop     rsi
0x180003833  pop     rbp
0x180003834  pop     rbx
0x180003835  retn
```
