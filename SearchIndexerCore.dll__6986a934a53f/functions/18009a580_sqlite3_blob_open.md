# sqlite3_blob_open

- ea: `0x18009a580`
- end: `0x18009aa8a`
- name: `sqlite3_blob_open`
- size: `1290`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: ``

## callees

- `0x180008be8`
- `0x180009ac0`
- `0x18000a038`
- `0x18000a710`
- `0x18000caf0`
- `0x180011bcc`
- `0x180016010`
- `0x180016c60`
- `0x18001f418`
- `0x18001fe1c`
- `0x1800208bc`
- `0x180020928`
- `0x180021284`
- `0x180024640`
- `0x18002619c`
- `0x180027290`
- `0x180032b14`
- `0x180038d00`
- `0x18003d380`
- `0x18003f840`
- `0x180040e00`
- `0x180041d10`
- `0x1800587c8`
- `0x180061de4`
- `0x180078968`
- `0x1800789c0`
- `0x18007a8f0`
- `0x180093b3c`
- `0x18009a580`

## string_xrefs

- `0x18009a9a0`: `cannot open virtual table: %s`
- `0x18009a997`: `cannot open table without rowid: %s`
- `0x18009a98e`: `cannot open view: %s`
- `0x18009a93d`: `cannot open %s column for writing`

## pseudocode

```c
__int64 __fastcall sqlite3_blob_open(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, __int64 *a7)
{
  __int64 v7; // r15
  __int64 v8; // r12
  __int64 v11; // r14
  __int64 v12; // rdx
  unsigned int v13; // r13d
  __int64 v14; // rsi
  __int64 Table; // rax
  __int64 v16; // rbx
  __int64 v17; // r12
  int v18; // r11d
  __int64 v19; // r15
  const char *v20; // r15
  __int64 i; // rdx
  unsigned int j; // r8d
  const char *v23; // rax
  __int64 k; // rcx
  __int64 v25; // rdx
  int v26; // r8d
  __int64 v27; // rax
  __int64 v28; // r15
  _DWORD *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // r15
  int v32; // edx
  __int64 v33; // r10
  __int64 v34; // r10
  unsigned int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // ebx
  BOOL v40; // [rsp+30h] [rbp-D0h]
  int v41; // [rsp+34h] [rbp-CCh]
  _QWORD *v42; // [rsp+38h] [rbp-C8h]
  unsigned int v43; // [rsp+38h] [rbp-C8h]
  __int64 v44; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v45; // [rsp+48h] [rbp-B8h]
  __int64 v46; // [rsp+50h] [rbp-B0h]
  __int64 v47; // [rsp+58h] [rbp-A8h]
  __int64 v48; // [rsp+60h] [rbp-A0h]
  __int64 *v49; // [rsp+68h] [rbp-98h]
  char v50[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v51; // [rsp+78h] [rbp-88h]
  int v52; // [rsp+A4h] [rbp-5Ch]
  int v53; // [rsp+A8h] [rbp-58h]
  __int16 v54; // [rsp+1A0h] [rbp+A0h]

  v7 = a3;
  v47 = a3;
  v8 = a2;
  v48 = a2;
  v49 = a7;
  v46 = a4;
  v11 = 0;
  memset_0(v50, 0, 0x1A8u);
  if ( !a7 )
  {
    v12 = 102702;
    return sqlite3ReportError(21, v12, "misuse");
  }
  *a7 = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) || !v7 || !a4 )
  {
    v12 = 102708;
    return sqlite3ReportError(21, v12, "misuse");
  }
  v13 = 0;
  v41 = 0;
  v40 = a6 != 0;
  sqlite3_mutex_enter(*(_QWORD *)(a1 + 24));
  v14 = sqlite3DbMallocZero(a1, 56);
  while ( 1 )
  {
    sqlite3ParseObjectInit(v50, a1);
    if ( !v14 )
      goto LABEL_48;
    sqlite3DbFree(a1, v11);
    v11 = 0;
    v44 = 0;
    sqlite3BtreeEnterAll(a1);
    Table = sqlite3LocateTable(v50, 0, v7, v8);
    v16 = Table;
    if ( !Table )
      goto LABEL_56;
    if ( *(_BYTE *)(Table + 63) == 1 )
    {
      sqlite3ErrorMsg(v50, "cannot open virtual table: %s", v7);
LABEL_56:
      if ( v51 )
      {
        sqlite3DbFree(a1, 0);
        v11 = v51;
        v51 = 0;
      }
      goto LABEL_58;
    }
    if ( *(char *)(Table + 48) < 0 )
    {
      sqlite3ErrorMsg(v50, "cannot open table without rowid: %s", v7);
      goto LABEL_56;
    }
    if ( *(_BYTE *)(Table + 63) == 2 )
    {
      sqlite3ErrorMsg(v50, "cannot open view: %s", v7);
      goto LABEL_56;
    }
    *(_QWORD *)(v14 + 48) = Table;
    v42 = (_QWORD *)(Table + 96);
    v17 = 0;
    *(_QWORD *)(v14 + 40) = *(_QWORD *)(32LL * (int)sqlite3SchemaToIndex(a1, *(_QWORD *)(Table + 96))
                                      + *(_QWORD *)(a1 + 32));
    v18 = *(__int16 *)(v16 + 54);
    if ( v18 <= 0 )
    {
LABEL_16:
      if ( (_DWORD)v17 == v18 )
      {
        sqlite3DbFree(a1, 0);
        v36 = sqlite3MPrintf(a1, "no such column: \"%s\"", v46);
        goto LABEL_52;
      }
    }
    else
    {
      v19 = *(_QWORD *)(v16 + 8);
      while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v19 + 24 * v17), v46) )
      {
        v17 = (unsigned int)(v17 + 1);
        if ( (int)v17 >= v18 )
          goto LABEL_16;
      }
    }
    if ( a6 )
    {
      v20 = 0;
      if ( (*(_DWORD *)(a1 + 48) & 0x4000LL) != 0 )
      {
        for ( i = *(_QWORD *)(v16 + 72); i; i = *(_QWORD *)(i + 8) )
        {
          for ( j = 0; (signed int)j < *(_DWORD *)(i + 40); v20 = v23 )
          {
            v23 = "foreign key";
            if ( *(_DWORD *)(i + 16 * (j + 4LL)) != (_DWORD)v17 )
              v23 = v20;
            ++j;
          }
        }
      }
      for ( k = *(_QWORD *)(v16 + 16); k; k = *(_QWORD *)(k + 40) )
      {
        if ( *(_WORD *)(k + 94) )
        {
          v25 = 0;
          do
          {
            v26 = *(__int16 *)(*(_QWORD *)(k + 8) + 2 * v25);
            if ( v26 == (_DWORD)v17 || (_WORD)v26 == 0xFFFE )
              v20 = "indexed";
            v25 = (unsigned int)(v25 + 1);
          }
          while ( (int)v25 < *(unsigned __int16 *)(k + 94) );
        }
      }
      if ( v20 )
      {
        sqlite3DbFree(a1, 0);
        v36 = sqlite3MPrintf(a1, "cannot open %s column for writing", v20);
LABEL_52:
        v11 = v36;
LABEL_58:
        v13 = 1;
        sqlite3BtreeLeaveAll(a1);
        goto LABEL_60;
      }
    }
    v27 = sqlite3VdbeCreate(v50);
    v45 = v27;
    v28 = v27;
    *(_QWORD *)(v14 + 24) = v27;
    if ( v27 )
    {
      v43 = sqlite3SchemaToIndex(a1, *v42);
      sqlite3VdbeAddOp4Int(v28, 2, v43, v40, *v29, v29[1]);
      sqlite3VdbeChangeP5(v28, 1);
      v31 = sqlite3VdbeAddOpList(v30, 6, qword_1800C1490);
      sqlite3VdbeUsesBtree(v45, v43);
      if ( !*(_BYTE *)(a1 + 103) )
      {
        *(_DWORD *)(v31 + 4) = v32;
        *(_DWORD *)(v31 + 8) = *(_DWORD *)(v16 + 40);
        *(_DWORD *)(v31 + 12) = v40;
        sqlite3VdbeChangeP4(v33, 2, *(_QWORD *)v16, 0);
        v34 = v45;
        if ( !*(_BYTE *)(a1 + 103) )
        {
          if ( a6 )
            *(_BYTE *)(v31 + 24) = 113;
          *(_DWORD *)(v31 + 32) = *(_DWORD *)(v16 + 40);
          *(_DWORD *)(v31 + 36) = v43;
          *(_BYTE *)(v31 + 25) = -3;
          *(_DWORD *)(v31 + 40) = *(__int16 *)(v16 + 54) + 1;
          *(_DWORD *)(v31 + 80) = *(__int16 *)(v16 + 54);
          v53 = 1;
          v52 = 1;
          v54 = 0;
          sqlite3VdbeMakeReady(v34, v50);
        }
      }
    }
    *(_WORD *)(v14 + 8) = v17;
    *(_QWORD *)(v14 + 32) = a1;
    sqlite3BtreeLeaveAll(a1);
    if ( *(_BYTE *)(a1 + 103) )
      goto LABEL_48;
    v35 = blobSeekToRow(v14, a5, &v44);
    v13 = v35;
    if ( ++v41 >= 50 || v35 != 17 )
      break;
    sqlite3ParseObjectReset(v50);
    v11 = v44;
    v7 = v47;
    v8 = v48;
  }
  v11 = v44;
LABEL_48:
  if ( !v13 && !*(_BYTE *)(a1 + 103) )
  {
    *v49 = v14;
    goto LABEL_63;
  }
  if ( v14 )
  {
LABEL_60:
    v37 = *(_QWORD *)(v14 + 24);
    if ( v37 )
      sqlite3VdbeFinalize(v37);
  }
  sqlite3DbFree(a1, v14);
LABEL_63:
  sqlite3ErrorWithMsg(a1, v13, (const char *)((unsigned __int64)"%s" & -(__int64)(v11 != 0)), v11);
  sqlite3DbFree(a1, v11);
  sqlite3ParseObjectReset(v50);
  v38 = sqlite3ApiExit(a1, v13);
  sqlite3_mutex_leave(*(_QWORD *)(a1 + 24));
  return v38;
}

```

## disassembly

```asm
0x18009a580  push    rbp
0x18009a582  push    rbx
0x18009a583  push    rsi
0x18009a584  push    rdi
0x18009a585  push    r12
0x18009a587  push    r13
0x18009a589  push    r14
0x18009a58b  push    r15
0x18009a58d  lea     rbp, [rsp-138h]
0x18009a595  sub     rsp, 238h
0x18009a59c  mov     rax, cs:__security_cookie
0x18009a5a3  xor     rax, rsp
0x18009a5a6  mov     [rbp+170h+var_50], rax
0x18009a5ad  mov     rbx, [rbp+170h+arg_30]
0x18009a5b4  mov     r15, r8
0x18009a5b7  mov     [rsp+270h+var_218], r8
0x18009a5bc  mov     r12, rdx
0x18009a5bf  mov     [rsp+270h+var_210], rdx
0x18009a5c4  mov     rdi, rcx
0x18009a5c7  xor     edx, edx; Val
0x18009a5c9  mov     [rsp+270h+var_208], rbx
0x18009a5ce  mov     r8d, 1A8h; Size
0x18009a5d4  mov     [rsp+270h+var_220], r9
0x18009a5d9  lea     rcx, [rsp+270h+var_200]; void *
0x18009a5de  mov     rsi, r9
0x18009a5e1  xor     r14d, r14d
0x18009a5e4  call    memset_0
0x18009a5e9  test    rbx, rbx
0x18009a5ec  jnz     short loc_18009A5F8
0x18009a5ee  mov     edx, 1912Eh
0x18009a5f3  jmp     loc_18009AA56
0x18009a5f8  mov     rcx, rdi
0x18009a5fb  mov     [rbx], r14
0x18009a5fe  call    sqlite3SafetyCheckOk
0x18009a603  test    eax, eax
0x18009a605  jz      loc_18009AA51
0x18009a60b  test    r15, r15
0x18009a60e  jz      loc_18009AA51
0x18009a614  test    rsi, rsi
0x18009a617  jz      loc_18009AA51
0x18009a61d  mov     rcx, [rdi+18h]
0x18009a621  xor     eax, eax
0x18009a623  xor     r13d, r13d
0x18009a626  mov     [rsp+270h+var_23C], r14d
0x18009a62b  cmp     [rbp+170h+arg_28], eax
0x18009a631  setnz   al
0x18009a634  mov     [rsp+270h+var_240], eax
0x18009a638  call    sqlite3_mutex_enter
0x18009a63d  lea     edx, [r13+38h]
0x18009a641  mov     rcx, rdi
0x18009a644  call    sqlite3DbMallocZero
0x18009a649  mov     rsi, rax
0x18009a64c  mov     rdx, rdi
0x18009a64f  lea     rcx, [rsp+270h+var_200]
0x18009a654  call    sqlite3ParseObjectInit
0x18009a659  test    rsi, rsi
0x18009a65c  jz      loc_18009A94B
0x18009a662  mov     rdx, r14
0x18009a665  mov     rcx, rdi
0x18009a668  call    sqlite3DbFree
0x18009a66d  xor     r14d, r14d
0x18009a670  mov     rcx, rdi
0x18009a673  mov     [rsp+270h+var_230], r14
0x18009a678  call    sqlite3BtreeEnterAll
0x18009a67d  mov     r9, r12
0x18009a680  lea     rcx, [rsp+270h+var_200]
0x18009a685  mov     r8, r15
0x18009a688  xor     edx, edx
0x18009a68a  call    sqlite3LocateTable
0x18009a68f  mov     rbx, rax
0x18009a692  test    rax, rax
0x18009a695  jz      loc_18009A9B4
0x18009a69b  cmp     byte ptr [rax+3Fh], 1
0x18009a69f  jz      loc_18009A9A0
0x18009a6a5  test    byte ptr [rax+30h], 80h
0x18009a6a9  jnz     loc_18009A997
0x18009a6af  cmp     byte ptr [rax+3Fh], 2
0x18009a6b3  jz      loc_18009A98E
0x18009a6b9  mov     [rsi+30h], rax
0x18009a6bd  mov     rcx, rdi
0x18009a6c0  add     rax, 60h ; '`'
0x18009a6c4  mov     [rsp+270h+var_238], rax
0x18009a6c9  mov     rdx, [rax]
0x18009a6cc  call    sqlite3SchemaToIndex
0x18009a6d1  movsxd  rcx, eax
0x18009a6d4  xor     r12d, r12d
0x18009a6d7  mov     rax, [rdi+20h]
0x18009a6db  shl     rcx, 5
0x18009a6df  mov     rcx, [rcx+rax]
0x18009a6e3  mov     [rsi+28h], rcx
0x18009a6e7  movsx   r11d, word ptr [rbx+36h]
0x18009a6ec  test    r11d, r11d
0x18009a6ef  jle     short loc_18009A713
0x18009a6f1  mov     r15, [rbx+8]
0x18009a6f5  mov     rdx, [rsp+270h+var_220]
0x18009a6fa  lea     rcx, [r12+r12*2]
0x18009a6fe  mov     rcx, [r15+rcx*8]
0x18009a702  call    sqlite3StrICmp
0x18009a707  test    eax, eax
0x18009a709  jz      short loc_18009A71C
0x18009a70b  inc     r12d
0x18009a70e  cmp     r12d, r11d
0x18009a711  jl      short loc_18009A6F5
0x18009a713  cmp     r12d, r11d
0x18009a716  jz      loc_18009A96B
0x18009a71c  cmp     [rbp+170h+arg_28], r14d
0x18009a723  jz      loc_18009A7BA
0x18009a729  mov     eax, [rdi+30h]
0x18009a72c  xor     r15d, r15d
0x18009a72f  bt      rax, 0Eh
0x18009a734  jnb     short loc_18009A773
0x18009a736  mov     rdx, [rbx+48h]
0x18009a73a  jmp     short loc_18009A76E
0x18009a73c  xor     r8d, r8d
0x18009a73f  cmp     [rdx+28h], r8d
0x18009a743  jle     short loc_18009A76A
0x18009a745  mov     ecx, r8d
0x18009a748  lea     rax, aForeignKey; "foreign key"
0x18009a74f  add     rcx, 4
0x18009a753  add     rcx, rcx
0x18009a756  cmp     [rdx+rcx*8], r12d
0x18009a75a  cmovnz  rax, r15
0x18009a75e  inc     r8d
0x18009a761  mov     r15, rax
0x18009a764  cmp     r8d, [rdx+28h]
0x18009a768  jl      short loc_18009A745
0x18009a76a  mov     rdx, [rdx+8]
0x18009a76e  test    rdx, rdx
0x18009a771  jnz     short loc_18009A73C
0x18009a773  mov     rcx, [rbx+10h]
0x18009a777  jmp     short loc_18009A7AC
0x18009a779  movzx   r9d, word ptr [rcx+5Eh]
0x18009a77e  test    r9d, r9d
0x18009a781  jz      short loc_18009A7A8
0x18009a783  mov     r10, [rcx+8]
0x18009a787  xor     edx, edx
0x18009a789  movsx   r8d, word ptr [r10+rdx*2]
0x18009a78e  cmp     r8d, r12d
0x18009a791  jz      short loc_18009A79A
0x18009a793  cmp     r8w, 0FFFEh
0x18009a798  jnz     short loc_18009A7A1
0x18009a79a  lea     r15, aIndexed; "indexed"
0x18009a7a1  inc     edx
0x18009a7a3  cmp     edx, r9d
0x18009a7a6  jl      short loc_18009A789
0x18009a7a8  mov     rcx, [rcx+28h]
0x18009a7ac  test    rcx, rcx
0x18009a7af  jnz     short loc_18009A779
0x18009a7b1  test    r15, r15
0x18009a7b4  jnz     loc_18009A930
0x18009a7ba  lea     rcx, [rsp+270h+var_200]
0x18009a7bf  call    sqlite3VdbeCreate
0x18009a7c4  mov     [rsp+270h+var_228], rax
0x18009a7c9  mov     r15, rax
0x18009a7cc  mov     [rsi+18h], rax
0x18009a7d0  test    rax, rax
0x18009a7d3  jz      loc_18009A8D0
0x18009a7d9  mov     rdx, [rsp+270h+var_238]
0x18009a7de  mov     rcx, rdi
0x18009a7e1  mov     rdx, [rdx]
0x18009a7e4  call    sqlite3SchemaToIndex
0x18009a7e9  mov     ecx, [rdx+4]
0x18009a7ec  mov     r8d, eax
0x18009a7ef  mov     r9d, [rsp+270h+var_240]
0x18009a7f4  mov     [rsp+270h+var_248], ecx
0x18009a7f8  mov     ecx, [rdx]
0x18009a7fa  mov     edx, 2
0x18009a7ff  mov     [rsp+270h+var_250], ecx
0x18009a803  mov     rcx, r15
0x18009a806  mov     dword ptr [rsp+270h+var_238], eax
0x18009a80a  call    sqlite3VdbeAddOp4Int
0x18009a80f  mov     edx, 1
0x18009a814  mov     rcx, r15
0x18009a817  call    sqlite3VdbeChangeP5
0x18009a81c  lea     r8, qword_1800C1490
0x18009a823  mov     edx, 6
0x18009a828  call    sqlite3VdbeAddOpList
0x18009a82d  mov     r10, [rsp+270h+var_228]
0x18009a832  mov     r15, rax
0x18009a835  mov     edx, dword ptr [rsp+270h+var_238]
0x18009a839  mov     rcx, r10
0x18009a83c  call    sqlite3VdbeUsesBtree
0x18009a841  cmp     [rdi+67h], r14b
0x18009a845  jnz     loc_18009A8D0
0x18009a84b  mov     eax, [rsp+270h+var_240]
0x18009a84f  xor     r9d, r9d
0x18009a852  mov     [r15+4], edx
0x18009a856  mov     ecx, [rbx+28h]
0x18009a859  mov     [r15+8], ecx
0x18009a85d  mov     rcx, r10
0x18009a860  mov     [r15+0Ch], eax
0x18009a864  lea     edx, [r9+2]
0x18009a868  mov     r8, [rbx]
0x18009a86b  call    sqlite3VdbeChangeP4
0x18009a870  mov     r10, [rsp+270h+var_228]
0x18009a875  mov     edx, dword ptr [rsp+270h+var_238]
0x18009a879  cmp     [rdi+67h], r14b
0x18009a87d  jnz     short loc_18009A8D0
0x18009a87f  cmp     [rbp+170h+arg_28], r14d
0x18009a886  jz      short loc_18009A88D
0x18009a888  mov     byte ptr [r15+18h], 71h ; 'q'
0x18009a88d  mov     eax, [rbx+28h]
0x18009a890  mov     ecx, 1
0x18009a895  mov     [r15+20h], eax
0x18009a899  mov     [r15+24h], edx
0x18009a89d  lea     rdx, [rsp+270h+var_200]
0x18009a8a2  mov     byte ptr [r15+19h], 0FDh
0x18009a8a7  movsx   eax, word ptr [rbx+36h]
0x18009a8ab  add     eax, ecx
0x18009a8ad  mov     [r15+28h], eax
0x18009a8b1  movsx   eax, word ptr [rbx+36h]
0x18009a8b5  mov     [r15+50h], eax
0x18009a8b9  xor     eax, eax
0x18009a8bb  mov     [rbp+170h+var_1C8], ecx
0x18009a8be  mov     [rbp+170h+var_1CC], ecx
0x18009a8c1  mov     rcx, r10
0x18009a8c4  mov     [rbp+170h+var_D0], ax
0x18009a8cb  call    sqlite3VdbeMakeReady
0x18009a8d0  mov     rcx, rdi
0x18009a8d3  mov     [rsi+8], r12w
0x18009a8d8  mov     [rsi+20h], rdi
0x18009a8dc  call    sqlite3BtreeLeaveAll
0x18009a8e1  cmp     [rdi+67h], r14b
0x18009a8e5  jnz     short loc_18009A94B
0x18009a8e7  mov     rdx, [rbp+170h+arg_20]
0x18009a8ee  lea     r8, [rsp+270h+var_230]
0x18009a8f3  mov     rcx, rsi
0x18009a8f6  call    blobSeekToRow
0x18009a8fb  mov     ebx, [rsp+270h+var_23C]
0x18009a8ff  mov     r13d, eax
0x18009a902  inc     ebx
0x18009a904  mov     [rsp+270h+var_23C], ebx
0x18009a908  cmp     ebx, 32h ; '2'
0x18009a90b  jge     short loc_18009A946
0x18009a90d  cmp     eax, 11h
0x18009a910  jnz     short loc_18009A946
0x18009a912  lea     rcx, [rsp+270h+var_200]
0x18009a917  call    sqlite3ParseObjectReset
0x18009a91c  mov     r14, [rsp+270h+var_230]
0x18009a921  mov     r15, [rsp+270h+var_218]
0x18009a926  mov     r12, [rsp+270h+var_210]
0x18009a92b  jmp     loc_18009A64C
0x18009a930  xor     edx, edx
0x18009a932  mov     rcx, rdi
0x18009a935  call    sqlite3DbFree
0x18009a93a  mov     r8, r15
0x18009a93d  lea     rdx, aCannotOpenSCol; "cannot open %s column for writing"
0x18009a944  jmp     short loc_18009A981
0x18009a946  mov     r14, [rsp+270h+var_230]
0x18009a94b  test    r13d, r13d
0x18009a94e  jnz     loc_18009A9E3
0x18009a954  cmp     [rdi+67h], r13b
0x18009a958  jnz     loc_18009A9E3
0x18009a95e  mov     rax, [rsp+270h+var_208]
0x18009a963  mov     [rax], rsi
0x18009a966  jmp     loc_18009AA01
0x18009a96b  xor     edx, edx
0x18009a96d  mov     rcx, rdi
0x18009a970  call    sqlite3DbFree
0x18009a975  mov     r8, [rsp+270h+var_220]
0x18009a97a  lea     rdx, aNoSuchColumnS_0; "no such column: \"%s\""
0x18009a981  mov     rcx, rdi
0x18009a984  call    sqlite3MPrintf
0x18009a989  mov     r14, rax
0x18009a98c  jmp     short loc_18009A9D3
0x18009a98e  lea     rdx, aCannotOpenView; "cannot open view: %s"
0x18009a995  jmp     short loc_18009A9A7
0x18009a997  lea     rdx, aCannotOpenTabl; "cannot open table without rowid: %s"
0x18009a99e  jmp     short loc_18009A9A7
0x18009a9a0  lea     rdx, aCannotOpenVirt; "cannot open virtual table: %s"
0x18009a9a7  mov     r8, r15
0x18009a9aa  lea     rcx, [rsp+270h+var_200]
0x18009a9af  call    sqlite3ErrorMsg
0x18009a9b4  cmp     [rsp+270h+var_1F8], r14
0x18009a9b9  jz      short loc_18009A9D3
0x18009a9bb  xor     edx, edx
0x18009a9bd  mov     rcx, rdi
0x18009a9c0  call    sqlite3DbFree
0x18009a9c5  mov     r14, [rsp+270h+var_1F8]
0x18009a9ca  mov     [rsp+270h+var_1F8], 0
0x18009a9d3  mov     rcx, rdi
0x18009a9d6  mov     r13d, 1
0x18009a9dc  call    sqlite3BtreeLeaveAll
0x18009a9e1  jmp     short loc_18009A9E8
0x18009a9e3  test    rsi, rsi
0x18009a9e6  jz      short loc_18009A9F6
0x18009a9e8  mov     rcx, [rsi+18h]
0x18009a9ec  test    rcx, rcx
0x18009a9ef  jz      short loc_18009A9F6
0x18009a9f1  call    sqlite3VdbeFinalize
0x18009a9f6  mov     rdx, rsi
0x18009a9f9  mov     rcx, rdi
0x18009a9fc  call    sqlite3DbFree
0x18009aa01  mov     rax, r14
0x18009aa04  mov     r9, r14
0x18009aa07  neg     rax
0x18009aa0a  mov     edx, r13d
0x18009aa0d  lea     rax, aS_7; "%s"
0x18009aa14  mov     rcx, rdi
0x18009aa17  sbb     r8, r8
  ... truncated ...
```
