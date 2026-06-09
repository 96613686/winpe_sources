# sqlite3_blob_open

- ea: `0x18008c9b0`
- end: `0x18008cecd`
- name: `sqlite3_blob_open`
- size: `1309`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: ``

## callees

- `0x180005c54`
- `0x180009f00`
- `0x18000a430`
- `0x18000a9e0`
- `0x18000b220`
- `0x18000f720`
- `0x180010b10`
- `0x180011950`
- `0x180013c28`
- `0x1800143f0`
- `0x1800256c4`
- `0x180027aa0`
- `0x180034e60`
- `0x18003abcc`
- `0x18003f6dc`
- `0x180047bbc`
- `0x180047c2c`
- `0x18004d11c`
- `0x18005ba3c`
- `0x18005cf6c`
- `0x18005e288`
- `0x18005fa24`
- `0x180060134`
- `0x180060ce8`
- `0x180068880`
- `0x18006910e`
- `0x18006a2a0`
- `0x180085fe8`
- `0x18008c9b0`

## string_xrefs

- `0x18008cde3`: `cannot open virtual table: %s`
- `0x18008cdda`: `cannot open table without rowid: %s`
- `0x18008cdd1`: `cannot open table with generated columns: %s`
- `0x18008cdc8`: `cannot open view: %s`
- `0x18008cd77`: `cannot open %s column for writing`

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
  unsigned int v37; // ebx
  BOOL v39; // [rsp+30h] [rbp-D0h]
  int v40; // [rsp+34h] [rbp-CCh]
  _QWORD *v41; // [rsp+38h] [rbp-C8h]
  unsigned int v42; // [rsp+38h] [rbp-C8h]
  __int64 v43; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v44; // [rsp+48h] [rbp-B8h]
  __int64 v45; // [rsp+50h] [rbp-B0h]
  __int64 v46; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h]
  __int64 *v48; // [rsp+68h] [rbp-98h]
  char v49[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v50; // [rsp+78h] [rbp-88h]
  int v51; // [rsp+A8h] [rbp-58h]
  int v52; // [rsp+ACh] [rbp-54h]
  __int16 v53; // [rsp+1A0h] [rbp+A0h]

  v7 = a3;
  v46 = a3;
  v8 = a2;
  v47 = a2;
  v48 = a7;
  v45 = a4;
  v11 = 0;
  memset_0(v49, 0, 0x1A8u);
  if ( !a7 )
  {
    v12 = 102762;
    return sqlite3ReportError(21, v12, "misuse");
  }
  *a7 = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) || !v7 || !a4 )
  {
    v12 = 102768;
    return sqlite3ReportError(21, v12, "misuse");
  }
  v13 = 0;
  v40 = 0;
  v39 = a6 != 0;
  sqlite3_mutex_enter(*(_QWORD *)(a1 + 24));
  v14 = sqlite3DbMallocZero(a1, 56);
  while ( 1 )
  {
    sqlite3ParseObjectInit(v49, a1);
    if ( !v14 )
      goto LABEL_49;
    sqlite3DbFree(a1, v11);
    v11 = 0;
    v43 = 0;
    sqlite3BtreeEnterAll(a1);
    Table = sqlite3LocateTable(v49, 0, v7, v8);
    v16 = Table;
    if ( !Table )
      goto LABEL_58;
    if ( *(_BYTE *)(Table + 63) == 1 )
    {
      sqlite3ErrorMsg(v49, "cannot open virtual table: %s", v7);
LABEL_58:
      if ( v50 )
      {
        sqlite3DbFree(a1, 0);
        v11 = v50;
        v50 = 0;
      }
      goto LABEL_60;
    }
    if ( *(char *)(Table + 48) < 0 )
    {
      sqlite3ErrorMsg(v49, "cannot open table without rowid: %s", v7);
      goto LABEL_58;
    }
    if ( (*(_BYTE *)(Table + 48) & 0x60) != 0 )
    {
      sqlite3ErrorMsg(v49, "cannot open table with generated columns: %s", v7);
      goto LABEL_58;
    }
    if ( *(_BYTE *)(Table + 63) == 2 )
    {
      sqlite3ErrorMsg(v49, "cannot open view: %s", v7);
      goto LABEL_58;
    }
    *(_QWORD *)(v14 + 48) = Table;
    v41 = (_QWORD *)(Table + 96);
    v17 = 0;
    *(_QWORD *)(v14 + 40) = *(_QWORD *)(32LL * (int)sqlite3SchemaToIndex(a1, *(_QWORD *)(Table + 96))
                                      + *(_QWORD *)(a1 + 32));
    v18 = *(__int16 *)(v16 + 54);
    if ( v18 <= 0 )
    {
LABEL_17:
      if ( (_DWORD)v17 == v18 )
      {
        sqlite3DbFree(a1, 0);
        v36 = sqlite3MPrintf(a1, "no such column: \"%s\"", v45);
        goto LABEL_53;
      }
    }
    else
    {
      v19 = *(_QWORD *)(v16 + 8);
      while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v19 + 24 * v17), v45) )
      {
        v17 = (unsigned int)(v17 + 1);
        if ( (int)v17 >= v18 )
          goto LABEL_17;
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
LABEL_53:
        v11 = v36;
LABEL_60:
        v13 = 1;
        sqlite3BtreeLeaveAll(a1);
        goto LABEL_62;
      }
    }
    v27 = sqlite3VdbeCreate(v49);
    v44 = v27;
    v28 = v27;
    *(_QWORD *)(v14 + 24) = v27;
    if ( v27 )
    {
      v42 = sqlite3SchemaToIndex(a1, *v41);
      sqlite3VdbeAddOp4Int(v28, 2, v42, v39, *v29, v29[1]);
      sqlite3VdbeChangeP5(v28, 1);
      v31 = sqlite3VdbeAddOpList(v30, 6, qword_1800AA770);
      sqlite3VdbeUsesBtree(v44, v42);
      if ( !*(_BYTE *)(a1 + 103) )
      {
        *(_DWORD *)(v31 + 4) = v32;
        *(_DWORD *)(v31 + 8) = *(_DWORD *)(v16 + 40);
        *(_DWORD *)(v31 + 12) = v39;
        sqlite3VdbeChangeP4(v33, 2, *(_QWORD *)v16);
        v34 = v44;
        if ( !*(_BYTE *)(a1 + 103) )
        {
          if ( a6 )
            *(_BYTE *)(v31 + 24) = 113;
          *(_DWORD *)(v31 + 32) = *(_DWORD *)(v16 + 40);
          *(_DWORD *)(v31 + 36) = v42;
          *(_BYTE *)(v31 + 25) = -3;
          *(_DWORD *)(v31 + 40) = *(__int16 *)(v16 + 54) + 1;
          *(_DWORD *)(v31 + 80) = *(__int16 *)(v16 + 54);
          v52 = 1;
          v51 = 1;
          v53 = 0;
          sqlite3VdbeMakeReady(v34, v49);
        }
      }
    }
    *(_WORD *)(v14 + 8) = v17;
    *(_QWORD *)(v14 + 32) = a1;
    sqlite3BtreeLeaveAll(a1);
    if ( *(_BYTE *)(a1 + 103) )
      goto LABEL_49;
    v35 = blobSeekToRow(v14, a5, &v43);
    v13 = v35;
    if ( ++v40 >= 50 || v35 != 17 )
      break;
    sqlite3ParseObjectReset(v49);
    v11 = v43;
    v7 = v46;
    v8 = v47;
  }
  v11 = v43;
LABEL_49:
  if ( !v13 && !*(_BYTE *)(a1 + 103) )
  {
    *v48 = v14;
    goto LABEL_65;
  }
  if ( v14 )
  {
LABEL_62:
    if ( *(_QWORD *)(v14 + 24) )
      sqlite3VdbeFinalize();
  }
  sqlite3DbFree(a1, v14);
LABEL_65:
  sqlite3ErrorWithMsg(a1, v13, (unsigned __int64)"%s" & -(__int64)(v11 != 0), v11);
  sqlite3DbFree(a1, v11);
  sqlite3ParseObjectReset(v49);
  v37 = sqlite3ApiExit(a1, v13);
  sqlite3_mutex_leave(*(_QWORD *)(a1 + 24));
  return v37;
}

```

## disassembly

```asm
0x18008c9b0  push    rbp
0x18008c9b2  push    rbx
0x18008c9b3  push    rsi
0x18008c9b4  push    rdi
0x18008c9b5  push    r12
0x18008c9b7  push    r13
0x18008c9b9  push    r14
0x18008c9bb  push    r15
0x18008c9bd  lea     rbp, [rsp-138h]
0x18008c9c5  sub     rsp, 238h
0x18008c9cc  mov     rax, cs:__security_cookie
0x18008c9d3  xor     rax, rsp
0x18008c9d6  mov     [rbp+170h+var_50], rax
0x18008c9dd  mov     rbx, [rbp+170h+arg_30]
0x18008c9e4  mov     r15, r8
0x18008c9e7  mov     [rsp+270h+var_218], r8
0x18008c9ec  mov     r12, rdx
0x18008c9ef  mov     [rsp+270h+var_210], rdx
0x18008c9f4  mov     rdi, rcx
0x18008c9f7  xor     edx, edx; Val
0x18008c9f9  mov     [rsp+270h+var_208], rbx
0x18008c9fe  mov     r8d, 1A8h; Size
0x18008ca04  mov     [rsp+270h+var_220], r9
0x18008ca09  lea     rcx, [rsp+270h+var_200]; void *
0x18008ca0e  mov     rsi, r9
0x18008ca11  xor     r14d, r14d
0x18008ca14  call    memset_0
0x18008ca19  test    rbx, rbx
0x18008ca1c  jnz     short loc_18008CA28
0x18008ca1e  mov     edx, 1916Ah
0x18008ca23  jmp     loc_18008CE99
0x18008ca28  mov     rcx, rdi
0x18008ca2b  mov     [rbx], r14
0x18008ca2e  call    sqlite3SafetyCheckOk
0x18008ca33  test    eax, eax
0x18008ca35  jz      loc_18008CE94
0x18008ca3b  test    r15, r15
0x18008ca3e  jz      loc_18008CE94
0x18008ca44  test    rsi, rsi
0x18008ca47  jz      loc_18008CE94
0x18008ca4d  mov     rcx, [rdi+18h]
0x18008ca51  xor     eax, eax
0x18008ca53  xor     r13d, r13d
0x18008ca56  mov     [rsp+270h+var_23C], r14d
0x18008ca5b  cmp     [rbp+170h+arg_28], eax
0x18008ca61  setnz   al
0x18008ca64  mov     [rsp+270h+var_240], eax
0x18008ca68  call    sqlite3_mutex_enter
0x18008ca6d  lea     edx, [r13+38h]
0x18008ca71  mov     rcx, rdi
0x18008ca74  call    sqlite3DbMallocZero
0x18008ca79  mov     rsi, rax
0x18008ca7c  mov     rdx, rdi
0x18008ca7f  lea     rcx, [rsp+270h+var_200]
0x18008ca84  call    sqlite3ParseObjectInit
0x18008ca89  test    rsi, rsi
0x18008ca8c  jz      loc_18008CD85
0x18008ca92  mov     rdx, r14
0x18008ca95  mov     rcx, rdi
0x18008ca98  call    sqlite3DbFree
0x18008ca9d  xor     r14d, r14d
0x18008caa0  mov     rcx, rdi
0x18008caa3  mov     [rsp+270h+var_230], r14
0x18008caa8  call    sqlite3BtreeEnterAll
0x18008caad  mov     r9, r12
0x18008cab0  lea     rcx, [rsp+270h+var_200]
0x18008cab5  mov     r8, r15
0x18008cab8  xor     edx, edx
0x18008caba  call    sqlite3LocateTable
0x18008cabf  mov     rbx, rax
0x18008cac2  test    rax, rax
0x18008cac5  jz      loc_18008CDF7
0x18008cacb  cmp     byte ptr [rax+3Fh], 1
0x18008cacf  jz      loc_18008CDE3
0x18008cad5  test    byte ptr [rax+30h], 80h
0x18008cad9  jnz     loc_18008CDDA
0x18008cadf  test    byte ptr [rax+30h], 60h
0x18008cae3  jnz     loc_18008CDD1
0x18008cae9  cmp     byte ptr [rax+3Fh], 2
0x18008caed  jz      loc_18008CDC8
0x18008caf3  mov     [rsi+30h], rax
0x18008caf7  mov     rcx, rdi
0x18008cafa  add     rax, 60h ; '`'
0x18008cafe  mov     [rsp+270h+var_238], rax
0x18008cb03  mov     rdx, [rax]
0x18008cb06  call    sqlite3SchemaToIndex
0x18008cb0b  movsxd  rcx, eax
0x18008cb0e  xor     r12d, r12d
0x18008cb11  mov     rax, [rdi+20h]
0x18008cb15  shl     rcx, 5
0x18008cb19  mov     rcx, [rcx+rax]
0x18008cb1d  mov     [rsi+28h], rcx
0x18008cb21  movsx   r11d, word ptr [rbx+36h]
0x18008cb26  test    r11d, r11d
0x18008cb29  jle     short loc_18008CB4D
0x18008cb2b  mov     r15, [rbx+8]
0x18008cb2f  mov     rdx, [rsp+270h+var_220]
0x18008cb34  lea     rcx, [r12+r12*2]
0x18008cb38  mov     rcx, [r15+rcx*8]
0x18008cb3c  call    sqlite3StrICmp
0x18008cb41  test    eax, eax
0x18008cb43  jz      short loc_18008CB56
0x18008cb45  inc     r12d
0x18008cb48  cmp     r12d, r11d
0x18008cb4b  jl      short loc_18008CB2F
0x18008cb4d  cmp     r12d, r11d
0x18008cb50  jz      loc_18008CDA5
0x18008cb56  cmp     [rbp+170h+arg_28], r14d
0x18008cb5d  jz      loc_18008CBF4
0x18008cb63  mov     eax, [rdi+30h]
0x18008cb66  xor     r15d, r15d
0x18008cb69  bt      rax, 0Eh
0x18008cb6e  jnb     short loc_18008CBAD
0x18008cb70  mov     rdx, [rbx+48h]
0x18008cb74  jmp     short loc_18008CBA8
0x18008cb76  xor     r8d, r8d
0x18008cb79  cmp     [rdx+28h], r8d
0x18008cb7d  jle     short loc_18008CBA4
0x18008cb7f  mov     ecx, r8d
0x18008cb82  lea     rax, aForeignKey; "foreign key"
0x18008cb89  add     rcx, 4
0x18008cb8d  add     rcx, rcx
0x18008cb90  cmp     [rdx+rcx*8], r12d
0x18008cb94  cmovnz  rax, r15
0x18008cb98  inc     r8d
0x18008cb9b  mov     r15, rax
0x18008cb9e  cmp     r8d, [rdx+28h]
0x18008cba2  jl      short loc_18008CB7F
0x18008cba4  mov     rdx, [rdx+8]
0x18008cba8  test    rdx, rdx
0x18008cbab  jnz     short loc_18008CB76
0x18008cbad  mov     rcx, [rbx+10h]
0x18008cbb1  jmp     short loc_18008CBE6
0x18008cbb3  movzx   r9d, word ptr [rcx+5Eh]
0x18008cbb8  test    r9d, r9d
0x18008cbbb  jz      short loc_18008CBE2
0x18008cbbd  mov     r10, [rcx+8]
0x18008cbc1  xor     edx, edx
0x18008cbc3  movsx   r8d, word ptr [r10+rdx*2]
0x18008cbc8  cmp     r8d, r12d
0x18008cbcb  jz      short loc_18008CBD4
0x18008cbcd  cmp     r8w, 0FFFEh
0x18008cbd2  jnz     short loc_18008CBDB
0x18008cbd4  lea     r15, aIndexed; "indexed"
0x18008cbdb  inc     edx
0x18008cbdd  cmp     edx, r9d
0x18008cbe0  jl      short loc_18008CBC3
0x18008cbe2  mov     rcx, [rcx+28h]
0x18008cbe6  test    rcx, rcx
0x18008cbe9  jnz     short loc_18008CBB3
0x18008cbeb  test    r15, r15
0x18008cbee  jnz     loc_18008CD6A
0x18008cbf4  lea     rcx, [rsp+270h+var_200]
0x18008cbf9  call    sqlite3VdbeCreate
0x18008cbfe  mov     [rsp+270h+var_228], rax
0x18008cc03  mov     r15, rax
0x18008cc06  mov     [rsi+18h], rax
0x18008cc0a  test    rax, rax
0x18008cc0d  jz      loc_18008CD0A
0x18008cc13  mov     rdx, [rsp+270h+var_238]
0x18008cc18  mov     rcx, rdi
0x18008cc1b  mov     rdx, [rdx]
0x18008cc1e  call    sqlite3SchemaToIndex
0x18008cc23  mov     ecx, [rdx+4]
0x18008cc26  mov     r8d, eax
0x18008cc29  mov     r9d, [rsp+270h+var_240]
0x18008cc2e  mov     [rsp+270h+var_248], ecx
0x18008cc32  mov     ecx, [rdx]
0x18008cc34  mov     edx, 2
0x18008cc39  mov     [rsp+270h+var_250], ecx
0x18008cc3d  mov     rcx, r15
0x18008cc40  mov     dword ptr [rsp+270h+var_238], eax
0x18008cc44  call    sqlite3VdbeAddOp4Int
0x18008cc49  mov     edx, 1
0x18008cc4e  mov     rcx, r15
0x18008cc51  call    sqlite3VdbeChangeP5
0x18008cc56  lea     r8, qword_1800AA770
0x18008cc5d  mov     edx, 6
0x18008cc62  call    sqlite3VdbeAddOpList
0x18008cc67  mov     r10, [rsp+270h+var_228]
0x18008cc6c  mov     r15, rax
0x18008cc6f  mov     edx, dword ptr [rsp+270h+var_238]
0x18008cc73  mov     rcx, r10
0x18008cc76  call    sqlite3VdbeUsesBtree
0x18008cc7b  cmp     [rdi+67h], r14b
0x18008cc7f  jnz     loc_18008CD0A
0x18008cc85  mov     eax, [rsp+270h+var_240]
0x18008cc89  xor     r9d, r9d
0x18008cc8c  mov     [r15+4], edx
0x18008cc90  mov     ecx, [rbx+28h]
0x18008cc93  mov     [r15+8], ecx
0x18008cc97  mov     rcx, r10
0x18008cc9a  mov     [r15+0Ch], eax
0x18008cc9e  lea     edx, [r9+2]
0x18008cca2  mov     r8, [rbx]
0x18008cca5  call    sqlite3VdbeChangeP4
0x18008ccaa  mov     r10, [rsp+270h+var_228]
0x18008ccaf  mov     edx, dword ptr [rsp+270h+var_238]
0x18008ccb3  cmp     [rdi+67h], r14b
0x18008ccb7  jnz     short loc_18008CD0A
0x18008ccb9  cmp     [rbp+170h+arg_28], r14d
0x18008ccc0  jz      short loc_18008CCC7
0x18008ccc2  mov     byte ptr [r15+18h], 71h ; 'q'
0x18008ccc7  mov     eax, [rbx+28h]
0x18008ccca  mov     ecx, 1
0x18008cccf  mov     [r15+20h], eax
0x18008ccd3  mov     [r15+24h], edx
0x18008ccd7  lea     rdx, [rsp+270h+var_200]
0x18008ccdc  mov     byte ptr [r15+19h], 0FDh
0x18008cce1  movsx   eax, word ptr [rbx+36h]
0x18008cce5  add     eax, ecx
0x18008cce7  mov     [r15+28h], eax
0x18008cceb  movsx   eax, word ptr [rbx+36h]
0x18008ccef  mov     [r15+50h], eax
0x18008ccf3  xor     eax, eax
0x18008ccf5  mov     [rbp+170h+var_1C4], ecx
0x18008ccf8  mov     [rbp+170h+var_1C8], ecx
0x18008ccfb  mov     rcx, r10
0x18008ccfe  mov     [rbp+170h+var_D0], ax
0x18008cd05  call    sqlite3VdbeMakeReady
0x18008cd0a  mov     rcx, rdi
0x18008cd0d  mov     [rsi+8], r12w
0x18008cd12  mov     [rsi+20h], rdi
0x18008cd16  call    sqlite3BtreeLeaveAll
0x18008cd1b  cmp     [rdi+67h], r14b
0x18008cd1f  jnz     short loc_18008CD85
0x18008cd21  mov     rdx, [rbp+170h+arg_20]
0x18008cd28  lea     r8, [rsp+270h+var_230]
0x18008cd2d  mov     rcx, rsi
0x18008cd30  call    blobSeekToRow
0x18008cd35  mov     ebx, [rsp+270h+var_23C]
0x18008cd39  mov     r13d, eax
0x18008cd3c  inc     ebx
0x18008cd3e  mov     [rsp+270h+var_23C], ebx
0x18008cd42  cmp     ebx, 32h ; '2'
0x18008cd45  jge     short loc_18008CD80
0x18008cd47  cmp     eax, 11h
0x18008cd4a  jnz     short loc_18008CD80
0x18008cd4c  lea     rcx, [rsp+270h+var_200]
0x18008cd51  call    sqlite3ParseObjectReset
0x18008cd56  mov     r14, [rsp+270h+var_230]
0x18008cd5b  mov     r15, [rsp+270h+var_218]
0x18008cd60  mov     r12, [rsp+270h+var_210]
0x18008cd65  jmp     loc_18008CA7C
0x18008cd6a  xor     edx, edx
0x18008cd6c  mov     rcx, rdi
0x18008cd6f  call    sqlite3DbFree
0x18008cd74  mov     r8, r15
0x18008cd77  lea     rdx, aCannotOpenSCol; "cannot open %s column for writing"
0x18008cd7e  jmp     short loc_18008CDBB
0x18008cd80  mov     r14, [rsp+270h+var_230]
0x18008cd85  test    r13d, r13d
0x18008cd88  jnz     loc_18008CE26
0x18008cd8e  cmp     [rdi+67h], r13b
0x18008cd92  jnz     loc_18008CE26
0x18008cd98  mov     rax, [rsp+270h+var_208]
0x18008cd9d  mov     [rax], rsi
0x18008cda0  jmp     loc_18008CE44
0x18008cda5  xor     edx, edx
0x18008cda7  mov     rcx, rdi
0x18008cdaa  call    sqlite3DbFree
0x18008cdaf  mov     r8, [rsp+270h+var_220]
0x18008cdb4  lea     rdx, aNoSuchColumnS_0; "no such column: \"%s\""
0x18008cdbb  mov     rcx, rdi
0x18008cdbe  call    sqlite3MPrintf
0x18008cdc3  mov     r14, rax
0x18008cdc6  jmp     short loc_18008CE16
0x18008cdc8  lea     rdx, aCannotOpenView; "cannot open view: %s"
0x18008cdcf  jmp     short loc_18008CDEA
0x18008cdd1  lea     rdx, aCannotOpenTabl; "cannot open table with generated column"...
0x18008cdd8  jmp     short loc_18008CDEA
0x18008cdda  lea     rdx, aCannotOpenTabl_0; "cannot open table without rowid: %s"
0x18008cde1  jmp     short loc_18008CDEA
0x18008cde3  lea     rdx, aCannotOpenVirt; "cannot open virtual table: %s"
0x18008cdea  mov     r8, r15
0x18008cded  lea     rcx, [rsp+270h+var_200]
0x18008cdf2  call    sqlite3ErrorMsg
0x18008cdf7  cmp     [rsp+270h+var_1F8], r14
0x18008cdfc  jz      short loc_18008CE16
0x18008cdfe  xor     edx, edx
0x18008ce00  mov     rcx, rdi
0x18008ce03  call    sqlite3DbFree
0x18008ce08  mov     r14, [rsp+270h+var_1F8]
0x18008ce0d  mov     [rsp+270h+var_1F8], 0
0x18008ce16  mov     rcx, rdi
0x18008ce19  mov     r13d, 1
0x18008ce1f  call    sqlite3BtreeLeaveAll
0x18008ce24  jmp     short loc_18008CE2B
0x18008ce26  test    rsi, rsi
0x18008ce29  jz      short loc_18008CE39
0x18008ce2b  mov     rcx, [rsi+18h]
0x18008ce2f  test    rcx, rcx
0x18008ce32  jz      short loc_18008CE39
0x18008ce34  call    sqlite3VdbeFinalize
0x18008ce39  mov     rdx, rsi
0x18008ce3c  mov     rcx, rdi
0x18008ce3f  call    sqlite3DbFree
0x18008ce44  mov     rax, r14
0x18008ce47  mov     r9, r14
0x18008ce4a  neg     rax
  ... truncated ...
```
