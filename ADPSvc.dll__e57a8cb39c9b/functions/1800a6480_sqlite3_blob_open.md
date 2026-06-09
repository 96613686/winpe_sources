# sqlite3_blob_open

- ea: `0x1800a6480`
- end: `0x1800a6a13`
- name: `sqlite3_blob_open`
- size: `1427`
- prototype: ``
- caller_count: `0`
- callee_count: `24`
- tags: ``

## callees

- `0x180002250`
- `0x180002cf8`
- `0x1800374f8`
- `0x180039e48`
- `0x18003aafc`
- `0x18003adec`
- `0x1800716fc`
- `0x1800718ac`
- `0x180073aec`
- `0x180073b98`
- `0x180080620`
- `0x180080b64`
- `0x180083a34`
- `0x180083aa8`
- `0x18008ed60`
- `0x1800924d4`
- `0x180092564`
- `0x1800927e0`
- `0x180092940`
- `0x1800999a4`
- `0x18009a7c0`
- `0x18009d734`
- `0x1800a6480`
- `0x1800ca010`

## string_xrefs

- `0x1800a6965`: `cannot open virtual table: %s`
- `0x1800a695c`: `cannot open table without rowid: %s`
- `0x1800a6953`: `cannot open view: %s`
- `0x1800a68ac`: `cannot open %s column for writing`

## pseudocode

```c
__int64 __fastcall sqlite3_blob_open(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4,
        __int64 a5,
        int a6,
        __int64 *a7)
{
  __int64 *v7; // rdi
  __int64 v8; // r15
  __int64 v9; // r12
  unsigned int v11; // r14d
  __int64 v12; // rsi
  __int64 v13; // r13
  __int64 Table; // rax
  __int64 v15; // rdi
  __int64 v16; // rdx
  __int64 v17; // r8
  int v18; // ecx
  __int64 v19; // r15
  int v20; // r11d
  __int64 v21; // r12
  const char *v22; // r10
  __int64 v23; // rdx
  unsigned int i; // r8d
  const char *v25; // rax
  __int64 j; // rcx
  __int64 v27; // rdx
  int v28; // r8d
  __int64 v29; // rax
  __int64 v30; // r15
  int v31; // r12d
  _DWORD *v32; // rcx
  __int64 v33; // rdx
  __int64 v34; // rax
  __int64 v35; // r14
  __int64 v36; // rcx
  unsigned int v37; // eax
  unsigned int v38; // edi
  __int64 v39; // rax
  unsigned int v41; // [rsp+30h] [rbp-D0h]
  __int16 v42; // [rsp+34h] [rbp-CCh]
  BOOL v43; // [rsp+38h] [rbp-C8h]
  int v44; // [rsp+3Ch] [rbp-C4h]
  __int64 v45; // [rsp+40h] [rbp-C0h] BYREF
  const char *v46; // [rsp+48h] [rbp-B8h]
  _QWORD *v47; // [rsp+50h] [rbp-B0h]
  __int64 v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  __int64 *v50; // [rsp+68h] [rbp-98h]
  char v51[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h]
  int v53; // [rsp+A4h] [rbp-5Ch]
  int v54; // [rsp+A8h] [rbp-58h]
  __int16 v55; // [rsp+1A0h] [rbp+A0h]

  v7 = a7;
  v8 = a3;
  v48 = a3;
  v9 = a2;
  v49 = a2;
  v50 = a7;
  v44 = 0;
  v41 = 0;
  v46 = a4;
  v11 = 0;
  v12 = 0;
  memset_0(v51, 0, 0x1A8u);
  *a7 = 0;
  v43 = a6 != 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_18010EED0)();
  v13 = sqlite3DbMallocZero(a1, 56);
  sqlite3ParseObjectInit(v51, a1);
  if ( !v13 )
    goto LABEL_63;
  while ( 1 )
  {
    if ( v12 )
      sqlite3DbFreeNN(a1);
    v12 = 0;
    v45 = 0;
    if ( !*(_BYTE *)(a1 + 111) )
      btreeEnterAll(a1);
    Table = sqlite3LocateTable(v51, 0, v8, v9);
    v15 = Table;
    if ( !Table )
      goto LABEL_75;
    if ( *(_BYTE *)(Table + 63) == 1 )
    {
      sqlite3ErrorMsg(v51, "cannot open virtual table: %s", v8);
      goto LABEL_75;
    }
    if ( *(char *)(Table + 48) < 0 )
    {
      sqlite3ErrorMsg(v51, "cannot open table without rowid: %s", v8);
      goto LABEL_75;
    }
    if ( *(_BYTE *)(Table + 63) == 2 )
    {
      sqlite3ErrorMsg(v51, "cannot open view: %s", v8);
LABEL_75:
      v39 = v52;
      if ( !v52 )
      {
LABEL_78:
        v38 = 1;
LABEL_79:
        if ( !*(_BYTE *)(a1 + 111) )
          btreeLeaveAll(a1);
        goto LABEL_83;
      }
      v52 = 0;
LABEL_77:
      v12 = v39;
      goto LABEL_78;
    }
    *(_QWORD *)(v13 + 48) = Table;
    v47 = (_QWORD *)(Table + 96);
    v16 = *(_QWORD *)(Table + 96);
    if ( v16 )
    {
      v17 = *(_QWORD *)(a1 + 32);
      v18 = 0;
      if ( *(_QWORD *)(v17 + 24) != v16 )
      {
        do
          ++v18;
        while ( *(_QWORD *)(32LL * v18 + v17 + 24) != v16 );
      }
    }
    else
    {
      v18 = -32768;
    }
    v19 = 0;
    v42 = 0;
    *(_QWORD *)(v13 + 40) = *(_QWORD *)(32LL * v18 + *(_QWORD *)(a1 + 32));
    v20 = *(__int16 *)(Table + 54);
    if ( v20 <= 0 )
    {
LABEL_21:
      if ( (_DWORD)v19 != v20 )
        goto LABEL_22;
      v39 = sqlite3MPrintf(a1, "no such column: \"%s\"", v46);
      goto LABEL_77;
    }
    v21 = *(_QWORD *)(Table + 8);
    while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v21 + 24 * v19), v46) )
    {
      v19 = (unsigned int)(v19 + 1);
      v42 = v19;
      if ( (int)v19 >= v20 )
        goto LABEL_21;
    }
LABEL_22:
    if ( a6 )
    {
      v22 = 0;
      if ( (*(_DWORD *)(a1 + 48) & 0x4000LL) != 0 )
      {
        v23 = *(_QWORD *)(v15 + 72);
        if ( v23 )
        {
          do
          {
            for ( i = 0; (signed int)i < *(_DWORD *)(v23 + 40); v22 = v25 )
            {
              v25 = "foreign key";
              if ( *(_DWORD *)(v23 + 16 * (i + 4LL)) != (_DWORD)v19 )
                v25 = v22;
              ++i;
            }
            v23 = *(_QWORD *)(v23 + 8);
          }
          while ( v23 );
          v42 = v19;
        }
      }
      for ( j = *(_QWORD *)(v15 + 16); j; j = *(_QWORD *)(j + 40) )
      {
        if ( *(_WORD *)(j + 94) )
        {
          v27 = 0;
          do
          {
            v28 = *(__int16 *)(*(_QWORD *)(j + 8) + 2 * v27);
            if ( v28 == (_DWORD)v19 || (_WORD)v28 == 0xFFFE )
              v22 = "indexed";
            v27 = (unsigned int)(v27 + 1);
          }
          while ( (int)v27 < *(unsigned __int16 *)(j + 94) );
        }
      }
      if ( v22 )
      {
        v12 = sqlite3MPrintf(a1, "cannot open %s column for writing", v22);
        v38 = 1;
        goto LABEL_79;
      }
    }
    v29 = sqlite3VdbeCreate(v51);
    *(_QWORD *)(v13 + 24) = v29;
    v30 = v29;
    if ( v29 )
    {
      v31 = -32768;
      v32 = (_DWORD *)*v47;
      if ( *v47 )
      {
        v33 = *(_QWORD *)(a1 + 32);
        v31 = 0;
        if ( *(_DWORD **)(v33 + 24) != v32 )
        {
          do
            ++v31;
          while ( *(_DWORD **)(32LL * v31 + v33 + 24) != v32 );
        }
      }
      sqlite3VdbeAddOp4Int(v29, 2, v31, v43, *v32, v32[1]);
      v34 = *(int *)(v30 + 144);
      if ( (int)v34 > 0 )
        *(_WORD *)(*(_QWORD *)(v30 + 136) + 24 * v34 - 22) = 1;
      v35 = sqlite3VdbeAddOpList(v30, 6, qword_1800FAF00);
      sqlite3VdbeUsesBtree(v30, (unsigned int)v31);
      if ( *(_BYTE *)(a1 + 103)
        || (*(_DWORD *)(v35 + 4) = v31,
            *(_DWORD *)(v35 + 8) = *(_DWORD *)(v15 + 40),
            *(_DWORD *)(v35 + 12) = v43,
            sqlite3VdbeChangeP4(v36, 2, *(_QWORD *)v15, 0),
            *(_BYTE *)(a1 + 103)) )
      {
        v11 = v41;
      }
      else
      {
        if ( a6 )
          *(_BYTE *)(v35 + 24) = 113;
        *(_DWORD *)(v35 + 32) = *(_DWORD *)(v15 + 40);
        *(_DWORD *)(v35 + 36) = v31;
        *(_BYTE *)(v35 + 25) = -3;
        *(_DWORD *)(v35 + 40) = *(__int16 *)(v15 + 54) + 1;
        *(_DWORD *)(v35 + 80) = *(__int16 *)(v15 + 54);
        v55 = 0;
        v54 = 1;
        v53 = 1;
        sqlite3VdbeMakeReady(v30, v51);
        v11 = v41;
      }
    }
    *(_WORD *)(v13 + 8) = v42;
    *(_QWORD *)(v13 + 32) = a1;
    if ( !*(_BYTE *)(a1 + 111) )
      btreeLeaveAll(a1);
    if ( *(_BYTE *)(a1 + 103) )
      goto LABEL_61;
    v37 = blobSeekToRow(v13, a5, &v45);
    v11 = v37;
    v41 = v37;
    if ( ++v44 >= 50 || v37 != 17 )
      break;
    sqlite3ParseObjectReset(v51);
    sqlite3ParseObjectInit(v51, a1);
    v12 = v45;
    v8 = v48;
    v9 = v49;
  }
  v12 = v45;
LABEL_61:
  if ( v11 )
    goto LABEL_82;
  v7 = v50;
LABEL_63:
  if ( !*(_BYTE *)(a1 + 103) )
  {
    *v7 = v13;
    goto LABEL_65;
  }
  if ( v13 )
  {
LABEL_82:
    v38 = v41;
LABEL_83:
    if ( *(_QWORD *)(v13 + 24) )
      sqlite3VdbeFinalize();
    sqlite3DbFreeNN(a1);
  }
  else
  {
LABEL_65:
    v38 = v41;
  }
  sqlite3ErrorWithMsg(a1, v38, (unsigned __int64)"%s" & -(__int64)(v12 != 0), v12);
  if ( v12 )
    sqlite3DbFreeNN(a1);
  sqlite3ParseObjectReset(v51);
  if ( *(_BYTE *)(a1 + 103) || v38 )
    v38 = apiHandleError(a1, v38);
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_18010EEE0)();
  return v38;
}

```

## disassembly

```asm
0x1800a6480  push    rbp
0x1800a6482  push    rbx
0x1800a6483  push    rsi
0x1800a6484  push    rdi
0x1800a6485  push    r12
0x1800a6487  push    r13
0x1800a6489  push    r14
0x1800a648b  push    r15
0x1800a648d  lea     rbp, [rsp-138h]
0x1800a6495  sub     rsp, 238h
0x1800a649c  mov     rax, cs:__security_cookie
0x1800a64a3  xor     rax, rsp
0x1800a64a6  mov     [rbp+170h+var_50], rax
0x1800a64ad  mov     rdi, [rbp+170h+arg_30]
0x1800a64b4  xor     r13d, r13d
0x1800a64b7  mov     r15, r8
0x1800a64ba  mov     [rsp+270h+var_218], r8
0x1800a64bf  mov     r12, rdx
0x1800a64c2  mov     [rsp+270h+var_210], rdx
0x1800a64c7  mov     rbx, rcx
0x1800a64ca  mov     [rsp+270h+var_208], rdi
0x1800a64cf  xor     edx, edx; Val
0x1800a64d1  mov     [rsp+270h+var_234], r13d
0x1800a64d6  mov     r8d, 1A8h; Size
0x1800a64dc  mov     [rsp+270h+var_240], r13d
0x1800a64e1  lea     rcx, [rsp+270h+var_200]; void *
0x1800a64e6  mov     [rsp+270h+var_228], r9
0x1800a64eb  mov     r14d, r13d
0x1800a64ee  mov     esi, r13d
0x1800a64f1  call    memset_0
0x1800a64f6  cmp     [rbp+170h+arg_28], r13d
0x1800a64fd  mov     eax, r13d
0x1800a6500  mov     [rdi], r13
0x1800a6503  mov     rcx, [rbx+18h]
0x1800a6507  setnz   al
0x1800a650a  mov     [rsp+270h+var_238], eax
0x1800a650e  test    rcx, rcx
0x1800a6511  jz      short loc_1800A651F
0x1800a6513  mov     rax, qword ptr cs:xmmword_18010EED0
0x1800a651a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a651f  mov     edx, 38h ; '8'
0x1800a6524  mov     rcx, rbx
0x1800a6527  call    sqlite3DbMallocZero
0x1800a652c  mov     rdx, rbx
0x1800a652f  lea     rcx, [rsp+270h+var_200]
0x1800a6534  mov     r13, rax
0x1800a6537  call    sqlite3ParseObjectInit
0x1800a653c  test    r13, r13
0x1800a653f  jz      loc_1800A68DB
0x1800a6545  test    rsi, rsi
0x1800a6548  jz      short loc_1800A6555
0x1800a654a  mov     rdx, rsi
0x1800a654d  mov     rcx, rbx
0x1800a6550  call    sqlite3DbFreeNN
0x1800a6555  xor     esi, esi
0x1800a6557  mov     [rsp+270h+var_230], rsi
0x1800a655c  cmp     [rbx+6Fh], sil
0x1800a6560  jnz     short loc_1800A656A
0x1800a6562  mov     rcx, rbx
0x1800a6565  call    btreeEnterAll
0x1800a656a  mov     r9, r12
0x1800a656d  lea     rcx, [rsp+270h+var_200]
0x1800a6572  mov     r8, r15
0x1800a6575  xor     edx, edx
0x1800a6577  call    sqlite3LocateTable
0x1800a657c  mov     rdi, rax
0x1800a657f  mov     r12d, 1
0x1800a6585  test    rax, rax
0x1800a6588  jz      loc_1800A6979
0x1800a658e  cmp     [rax+3Fh], r12b
0x1800a6592  jz      loc_1800A6965
0x1800a6598  test    byte ptr [rax+30h], 80h
0x1800a659c  jnz     loc_1800A695C
0x1800a65a2  cmp     byte ptr [rax+3Fh], 2
0x1800a65a6  jz      loc_1800A6953
0x1800a65ac  mov     [r13+30h], rax
0x1800a65b0  add     rax, 60h ; '`'
0x1800a65b4  mov     [rsp+270h+var_220], rax
0x1800a65b9  mov     rdx, [rax]
0x1800a65bc  test    rdx, rdx
0x1800a65bf  jz      short loc_1800A65E0
0x1800a65c1  mov     r8, [rbx+20h]
0x1800a65c5  xor     ecx, ecx
0x1800a65c7  cmp     [r8+18h], rdx
0x1800a65cb  jz      short loc_1800A65E5
0x1800a65cd  add     ecx, r12d
0x1800a65d0  movsxd  rax, ecx
0x1800a65d3  shl     rax, 5
0x1800a65d7  cmp     [rax+r8+18h], rdx
0x1800a65dc  jnz     short loc_1800A65CD
0x1800a65de  jmp     short loc_1800A65E5
0x1800a65e0  mov     ecx, 0FFFF8000h
0x1800a65e5  mov     rax, [rbx+20h]
0x1800a65e9  xor     r15d, r15d
0x1800a65ec  movsxd  rcx, ecx
0x1800a65ef  shl     rcx, 5
0x1800a65f3  mov     [rsp+270h+var_23C], r15d
0x1800a65f8  mov     rcx, [rcx+rax]
0x1800a65fc  mov     [r13+28h], rcx
0x1800a6600  movsx   r11d, word ptr [rdi+36h]
0x1800a6605  test    r11d, r11d
0x1800a6608  jle     short loc_1800A6637
0x1800a660a  mov     r12, [rdi+8]
0x1800a660e  mov     rdx, [rsp+270h+var_228]
0x1800a6613  lea     rcx, [r15+r15*2]
0x1800a6617  mov     rcx, [r12+rcx*8]
0x1800a661b  call    sqlite3StrICmp
0x1800a6620  test    eax, eax
0x1800a6622  jz      short loc_1800A6640
0x1800a6624  inc     r15d
0x1800a6627  mov     [rsp+270h+var_23C], r15d
0x1800a662c  cmp     r15d, r11d
0x1800a662f  jl      short loc_1800A660E
0x1800a6631  mov     r12d, 1
0x1800a6637  cmp     r15d, r11d
0x1800a663a  jz      loc_1800A693D
0x1800a6640  cmp     [rbp+170h+arg_28], esi
0x1800a6646  jz      loc_1800A66E4
0x1800a664c  mov     eax, [rbx+30h]
0x1800a664f  xor     r10d, r10d
0x1800a6652  bt      rax, 0Eh
0x1800a6657  jnb     short loc_1800A669D
0x1800a6659  mov     rdx, [rdi+48h]
0x1800a665d  test    rdx, rdx
0x1800a6660  jz      short loc_1800A669D
0x1800a6662  xor     r8d, r8d
0x1800a6665  cmp     [rdx+28h], esi
0x1800a6668  jle     short loc_1800A668F
0x1800a666a  mov     ecx, r8d
0x1800a666d  lea     rax, aForeignKey; "foreign key"
0x1800a6674  add     rcx, 4
0x1800a6678  add     rcx, rcx
0x1800a667b  cmp     [rdx+rcx*8], r15d
0x1800a667f  cmovnz  rax, r10
0x1800a6683  inc     r8d
0x1800a6686  mov     r10, rax
0x1800a6689  cmp     r8d, [rdx+28h]
0x1800a668d  jl      short loc_1800A666A
0x1800a668f  mov     rdx, [rdx+8]
0x1800a6693  test    rdx, rdx
0x1800a6696  jnz     short loc_1800A6662
0x1800a6698  mov     [rsp+270h+var_23C], r15d
0x1800a669d  mov     rcx, [rdi+10h]
0x1800a66a1  jmp     short loc_1800A66D6
0x1800a66a3  movzx   r9d, word ptr [rcx+5Eh]
0x1800a66a8  test    r9d, r9d
0x1800a66ab  jz      short loc_1800A66D2
0x1800a66ad  mov     r11, [rcx+8]
0x1800a66b1  xor     edx, edx
0x1800a66b3  movsx   r8d, word ptr [r11+rdx*2]
0x1800a66b8  cmp     r8d, r15d
0x1800a66bb  jz      short loc_1800A66C4
0x1800a66bd  cmp     r8w, 0FFFEh
0x1800a66c2  jnz     short loc_1800A66CB
0x1800a66c4  lea     r10, aIndexed; "indexed"
0x1800a66cb  inc     edx
0x1800a66cd  cmp     edx, r9d
0x1800a66d0  jl      short loc_1800A66B3
0x1800a66d2  mov     rcx, [rcx+28h]
0x1800a66d6  test    rcx, rcx
0x1800a66d9  jnz     short loc_1800A66A3
0x1800a66db  test    r10, r10
0x1800a66de  jnz     loc_1800A68A9
0x1800a66e4  lea     rcx, [rsp+270h+var_200]
0x1800a66e9  call    sqlite3VdbeCreate
0x1800a66ee  mov     [r13+18h], rax
0x1800a66f2  mov     r15, rax
0x1800a66f5  test    rax, rax
0x1800a66f8  jz      loc_1800A6827
0x1800a66fe  mov     rcx, [rsp+270h+var_220]
0x1800a6703  mov     r12d, 0FFFF8000h
0x1800a6709  mov     r14d, 1
0x1800a670f  mov     rcx, [rcx]
0x1800a6712  test    rcx, rcx
0x1800a6715  jz      short loc_1800A6735
0x1800a6717  mov     rdx, [rbx+20h]
0x1800a671b  xor     r12d, r12d
0x1800a671e  cmp     [rdx+18h], rcx
0x1800a6722  jz      short loc_1800A6735
0x1800a6724  add     r12d, r14d
0x1800a6727  movsxd  rax, r12d
0x1800a672a  shl     rax, 5
0x1800a672e  cmp     [rax+rdx+18h], rcx
0x1800a6733  jnz     short loc_1800A6724
0x1800a6735  mov     eax, [rcx+4]
0x1800a6738  mov     r8d, r12d
0x1800a673b  mov     r9d, [rsp+270h+var_238]
0x1800a6740  mov     edx, 2
0x1800a6745  mov     [rsp+270h+var_248], eax
0x1800a6749  mov     eax, [rcx]
0x1800a674b  mov     rcx, r15
0x1800a674e  mov     [rsp+270h+var_250], eax
0x1800a6752  call    sqlite3VdbeAddOp4Int
0x1800a6757  movsxd  rax, dword ptr [r15+90h]
0x1800a675e  test    eax, eax
0x1800a6760  jle     short loc_1800A6773
0x1800a6762  lea     rcx, [rax+rax*2]
0x1800a6766  mov     rax, [r15+88h]
0x1800a676d  mov     [rax+rcx*8-16h], r14w
0x1800a6773  lea     r8, qword_1800FAF00
0x1800a677a  mov     edx, 6
0x1800a677f  mov     rcx, r15
0x1800a6782  call    sqlite3VdbeAddOpList
0x1800a6787  mov     edx, r12d
0x1800a678a  mov     rcx, r15
0x1800a678d  mov     r14, rax
0x1800a6790  call    sqlite3VdbeUsesBtree
0x1800a6795  cmp     [rbx+67h], sil
0x1800a6799  jnz     loc_1800A6822
0x1800a679f  mov     [r14+4], r12d
0x1800a67a3  xor     r9d, r9d
0x1800a67a6  mov     eax, [rdi+28h]
0x1800a67a9  mov     [r14+8], eax
0x1800a67ad  mov     eax, [rsp+270h+var_238]
0x1800a67b1  mov     [r14+0Ch], eax
0x1800a67b5  lea     edx, [r9+2]
0x1800a67b9  mov     r8, [rdi]
0x1800a67bc  call    sqlite3VdbeChangeP4
0x1800a67c1  cmp     [rbx+67h], sil
0x1800a67c5  jnz     short loc_1800A6822
0x1800a67c7  cmp     [rbp+170h+arg_28], esi
0x1800a67cd  jz      short loc_1800A67D4
0x1800a67cf  mov     byte ptr [r14+18h], 71h ; 'q'
0x1800a67d4  mov     eax, [rdi+28h]
0x1800a67d7  lea     rdx, [rsp+270h+var_200]
0x1800a67dc  mov     [r14+20h], eax
0x1800a67e0  mov     rcx, r15
0x1800a67e3  mov     [r14+24h], r12d
0x1800a67e7  mov     r12d, 1
0x1800a67ed  mov     byte ptr [r14+19h], 0FDh
0x1800a67f2  movsx   eax, word ptr [rdi+36h]
0x1800a67f6  add     eax, r12d
0x1800a67f9  mov     [r14+28h], eax
0x1800a67fd  movsx   eax, word ptr [rdi+36h]
0x1800a6801  mov     [r14+50h], eax
0x1800a6805  xor     eax, eax
0x1800a6807  mov     [rbp+170h+var_D0], ax
0x1800a680e  mov     [rbp+170h+var_1C8], r12d
0x1800a6812  mov     [rbp+170h+var_1CC], r12d
0x1800a6816  call    sqlite3VdbeMakeReady
0x1800a681b  mov     r14d, [rsp+270h+var_240]
0x1800a6820  jmp     short loc_1800A682D
0x1800a6822  mov     r14d, [rsp+270h+var_240]
0x1800a6827  mov     r12d, 1
0x1800a682d  mov     eax, [rsp+270h+var_23C]
0x1800a6831  mov     [r13+8], ax
0x1800a6836  mov     [r13+20h], rbx
0x1800a683a  cmp     [rbx+6Fh], sil
0x1800a683e  jnz     short loc_1800A6848
0x1800a6840  mov     rcx, rbx
0x1800a6843  call    btreeLeaveAll
0x1800a6848  cmp     [rbx+67h], sil
0x1800a684c  jnz     short loc_1800A68CD
0x1800a684e  mov     rdx, [rbp+170h+arg_20]
0x1800a6855  lea     r8, [rsp+270h+var_230]
0x1800a685a  mov     rcx, r13
0x1800a685d  call    blobSeekToRow
0x1800a6862  mov     edi, [rsp+270h+var_234]
0x1800a6866  mov     r14d, eax
0x1800a6869  add     edi, r12d
0x1800a686c  mov     [rsp+270h+var_240], eax
0x1800a6870  mov     [rsp+270h+var_234], edi
0x1800a6874  cmp     edi, 32h ; '2'
0x1800a6877  jge     short loc_1800A68C8
0x1800a6879  cmp     eax, 11h
0x1800a687c  jnz     short loc_1800A68C8
0x1800a687e  lea     rcx, [rsp+270h+var_200]
0x1800a6883  call    sqlite3ParseObjectReset
0x1800a6888  mov     rdx, rbx
0x1800a688b  lea     rcx, [rsp+270h+var_200]
0x1800a6890  call    sqlite3ParseObjectInit
0x1800a6895  mov     rsi, [rsp+270h+var_230]
0x1800a689a  mov     r15, [rsp+270h+var_218]
0x1800a689f  mov     r12, [rsp+270h+var_210]
0x1800a68a4  jmp     loc_1800A6545
0x1800a68a9  mov     r8, r10
0x1800a68ac  lea     rdx, aCannotOpenSCol; "cannot open %s column for writing"
0x1800a68b3  mov     rcx, rbx
0x1800a68b6  call    sqlite3MPrintf
0x1800a68bb  mov     rsi, rax
0x1800a68be  mov     edi, 1
0x1800a68c3  jmp     loc_1800A6992
0x1800a68c8  mov     rsi, [rsp+270h+var_230]
0x1800a68cd  test    r14d, r14d
0x1800a68d0  jnz     loc_1800A69AB
0x1800a68d6  mov     rdi, [rsp+270h+var_208]
0x1800a68db  cmp     byte ptr [rbx+67h], 0
0x1800a68df  jnz     loc_1800A69A2
0x1800a68e5  mov     [rdi], r13
0x1800a68e8  mov     edi, [rsp+270h+var_240]
0x1800a68ec  mov     rax, rsi
0x1800a68ef  mov     r9, rsi
0x1800a68f2  neg     rax
0x1800a68f5  mov     edx, edi
0x1800a68f7  lea     rax, aS_7; "%s"
0x1800a68fe  mov     rcx, rbx
0x1800a6901  sbb     r8, r8
0x1800a6904  and     r8, rax
0x1800a6907  call    sqlite3ErrorWithMsg
0x1800a690c  test    rsi, rsi
  ... truncated ...
```
