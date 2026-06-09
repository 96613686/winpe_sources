# sqlite3_blob_open

- ea: `0x180092ec0`
- end: `0x1800933ce`
- name: `sqlite3_blob_open`
- size: `1294`
- prototype: ``
- caller_count: `0`
- callee_count: `29`
- tags: ``

## callees

- `0x18000b5a8`
- `0x180014464`
- `0x18001ad50`
- `0x18001ef48`
- `0x180027eb0`
- `0x18002b8ec`
- `0x18002e290`
- `0x180034900`
- `0x180037880`
- `0x180038974`
- `0x18003a860`
- `0x18003ad5c`
- `0x18003bf64`
- `0x18003c8d4`
- `0x18003cde4`
- `0x180042500`
- `0x180042b88`
- `0x180042bb0`
- `0x180042bcc`
- `0x180042c38`
- `0x180042cd4`
- `0x1800449f0`
- `0x180045374`
- `0x180055f3c`
- `0x18007edf0`
- `0x1800881a8`
- `0x18008cbcc`
- `0x18008d540`
- `0x180092ec0`

## string_xrefs

- `0x1800932e4`: `cannot open virtual table: %s`
- `0x1800932db`: `cannot open table without rowid: %s`
- `0x1800932d2`: `cannot open view: %s`
- `0x180093281`: `cannot open %s column for writing`

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
  int v18; // r15d
  __int64 v19; // r8
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
  int v51; // [rsp+A4h] [rbp-5Ch]
  int v52; // [rsp+A8h] [rbp-58h]
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
    v12 = 102421;
    return sqlite3ReportError(21, v12, "misuse");
  }
  *a7 = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) || !v7 || !a4 )
  {
    v12 = 102427;
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
      goto LABEL_48;
    sqlite3DbFree(a1, v11);
    v11 = 0;
    v43 = 0;
    sqlite3BtreeEnterAll(a1);
    Table = sqlite3LocateTable(v49, 0, v7, v8);
    v16 = Table;
    if ( !Table )
      goto LABEL_56;
    if ( *(_BYTE *)(Table + 63) == 1 )
    {
      sqlite3ErrorMsg(v49, "cannot open virtual table: %s", v7);
LABEL_56:
      if ( v50 )
      {
        sqlite3DbFree(a1, 0);
        v11 = v50;
        v50 = 0;
      }
      goto LABEL_58;
    }
    if ( *(char *)(Table + 48) < 0 )
    {
      sqlite3ErrorMsg(v49, "cannot open table without rowid: %s", v7);
      goto LABEL_56;
    }
    if ( *(_BYTE *)(Table + 63) == 2 )
    {
      sqlite3ErrorMsg(v49, "cannot open view: %s", v7);
      goto LABEL_56;
    }
    *(_QWORD *)(v14 + 48) = Table;
    v41 = (_QWORD *)(Table + 96);
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
        v36 = sqlite3MPrintf(a1, "no such column: \"%s\"", v45);
        goto LABEL_52;
      }
    }
    else
    {
      v19 = *(_QWORD *)(v16 + 8);
      while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v19 + 24 * v17), v45) )
      {
        v19 = *(_QWORD *)(v16 + 8);
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
    v27 = sqlite3VdbeCreate(v49);
    v44 = v27;
    v28 = v27;
    *(_QWORD *)(v14 + 24) = v27;
    if ( v27 )
    {
      v42 = sqlite3SchemaToIndex(a1, *v41);
      sqlite3VdbeAddOp4Int(v28, 2, v42, v39, *v29, v29[1]);
      sqlite3VdbeChangeP5(v28, 1);
      v31 = sqlite3VdbeAddOpList(v30, 6, qword_1800BA8D0);
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
      goto LABEL_48;
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
LABEL_48:
  if ( !v13 && !*(_BYTE *)(a1 + 103) )
  {
    *v48 = v14;
    goto LABEL_63;
  }
  if ( v14 )
  {
LABEL_60:
    if ( *(_QWORD *)(v14 + 24) )
      sqlite3VdbeFinalize();
  }
  sqlite3DbFree(a1, v14);
LABEL_63:
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
0x180092ec0  push    rbp
0x180092ec2  push    rbx
0x180092ec3  push    rsi
0x180092ec4  push    rdi
0x180092ec5  push    r12
0x180092ec7  push    r13
0x180092ec9  push    r14
0x180092ecb  push    r15
0x180092ecd  lea     rbp, [rsp-138h]
0x180092ed5  sub     rsp, 238h
0x180092edc  mov     rax, cs:__security_cookie
0x180092ee3  xor     rax, rsp
0x180092ee6  mov     [rbp+170h+var_50], rax
0x180092eed  mov     rbx, [rbp+170h+arg_30]
0x180092ef4  mov     r15, r8
0x180092ef7  mov     [rsp+270h+var_218], r8
0x180092efc  mov     r12, rdx
0x180092eff  mov     [rsp+270h+var_210], rdx
0x180092f04  mov     rdi, rcx
0x180092f07  xor     edx, edx; Val
0x180092f09  mov     [rsp+270h+var_208], rbx
0x180092f0e  mov     r8d, 1A8h; Size
0x180092f14  mov     [rsp+270h+var_220], r9
0x180092f19  lea     rcx, [rsp+270h+var_200]; void *
0x180092f1e  mov     rsi, r9
0x180092f21  xor     r14d, r14d
0x180092f24  call    memset_0
0x180092f29  test    rbx, rbx
0x180092f2c  jnz     short loc_180092F38
0x180092f2e  mov     edx, 19015h
0x180092f33  jmp     loc_18009339A
0x180092f38  mov     rcx, rdi
0x180092f3b  mov     [rbx], r14
0x180092f3e  call    sqlite3SafetyCheckOk
0x180092f43  test    eax, eax
0x180092f45  jz      loc_180093395
0x180092f4b  test    r15, r15
0x180092f4e  jz      loc_180093395
0x180092f54  test    rsi, rsi
0x180092f57  jz      loc_180093395
0x180092f5d  mov     rcx, [rdi+18h]
0x180092f61  xor     eax, eax
0x180092f63  xor     r13d, r13d
0x180092f66  mov     [rsp+270h+var_23C], r14d
0x180092f6b  cmp     [rbp+170h+arg_28], eax
0x180092f71  setnz   al
0x180092f74  mov     [rsp+270h+var_240], eax
0x180092f78  call    sqlite3_mutex_enter
0x180092f7d  lea     edx, [r13+38h]
0x180092f81  mov     rcx, rdi
0x180092f84  call    sqlite3DbMallocZero
0x180092f89  mov     rsi, rax
0x180092f8c  mov     rdx, rdi
0x180092f8f  lea     rcx, [rsp+270h+var_200]
0x180092f94  call    sqlite3ParseObjectInit
0x180092f99  test    rsi, rsi
0x180092f9c  jz      loc_18009328F
0x180092fa2  mov     rdx, r14
0x180092fa5  mov     rcx, rdi
0x180092fa8  call    sqlite3DbFree
0x180092fad  xor     r14d, r14d
0x180092fb0  mov     rcx, rdi
0x180092fb3  mov     [rsp+270h+var_230], r14
0x180092fb8  call    sqlite3BtreeEnterAll
0x180092fbd  mov     r9, r12
0x180092fc0  lea     rcx, [rsp+270h+var_200]
0x180092fc5  mov     r8, r15
0x180092fc8  xor     edx, edx
0x180092fca  call    sqlite3LocateTable
0x180092fcf  mov     rbx, rax
0x180092fd2  test    rax, rax
0x180092fd5  jz      loc_1800932F8
0x180092fdb  cmp     byte ptr [rax+3Fh], 1
0x180092fdf  jz      loc_1800932E4
0x180092fe5  test    byte ptr [rax+30h], 80h
0x180092fe9  jnz     loc_1800932DB
0x180092fef  cmp     byte ptr [rax+3Fh], 2
0x180092ff3  jz      loc_1800932D2
0x180092ff9  mov     [rsi+30h], rax
0x180092ffd  mov     rcx, rdi
0x180093000  add     rax, 60h ; '`'
0x180093004  mov     [rsp+270h+var_238], rax
0x180093009  mov     rdx, [rax]
0x18009300c  call    sqlite3SchemaToIndex
0x180093011  movsxd  rcx, eax
0x180093014  xor     r12d, r12d
0x180093017  mov     rax, [rdi+20h]
0x18009301b  shl     rcx, 5
0x18009301f  mov     rcx, [rcx+rax]
0x180093023  mov     [rsi+28h], rcx
0x180093027  movsx   r15d, word ptr [rbx+36h]
0x18009302c  test    r15d, r15d
0x18009302f  jle     short loc_180093057
0x180093031  mov     r8, [rbx+8]
0x180093035  mov     rdx, [rsp+270h+var_220]
0x18009303a  lea     rcx, [r12+r12*2]
0x18009303e  mov     rcx, [r8+rcx*8]
0x180093042  call    sqlite3StrICmp
0x180093047  test    eax, eax
0x180093049  jz      short loc_180093060
0x18009304b  mov     r8, [rbx+8]
0x18009304f  inc     r12d
0x180093052  cmp     r12d, r15d
0x180093055  jl      short loc_180093035
0x180093057  cmp     r12d, r15d
0x18009305a  jz      loc_1800932AF
0x180093060  cmp     [rbp+170h+arg_28], r14d
0x180093067  jz      loc_1800930FE
0x18009306d  mov     eax, [rdi+30h]
0x180093070  xor     r15d, r15d
0x180093073  bt      rax, 0Eh
0x180093078  jnb     short loc_1800930B7
0x18009307a  mov     rdx, [rbx+48h]
0x18009307e  jmp     short loc_1800930B2
0x180093080  xor     r8d, r8d
0x180093083  cmp     [rdx+28h], r8d
0x180093087  jle     short loc_1800930AE
0x180093089  mov     ecx, r8d
0x18009308c  lea     rax, aForeignKey; "foreign key"
0x180093093  add     rcx, 4
0x180093097  add     rcx, rcx
0x18009309a  cmp     [rdx+rcx*8], r12d
0x18009309e  cmovnz  rax, r15
0x1800930a2  inc     r8d
0x1800930a5  mov     r15, rax
0x1800930a8  cmp     r8d, [rdx+28h]
0x1800930ac  jl      short loc_180093089
0x1800930ae  mov     rdx, [rdx+8]
0x1800930b2  test    rdx, rdx
0x1800930b5  jnz     short loc_180093080
0x1800930b7  mov     rcx, [rbx+10h]
0x1800930bb  jmp     short loc_1800930F0
0x1800930bd  movzx   r9d, word ptr [rcx+5Eh]
0x1800930c2  test    r9d, r9d
0x1800930c5  jz      short loc_1800930EC
0x1800930c7  mov     r10, [rcx+8]
0x1800930cb  xor     edx, edx
0x1800930cd  movsx   r8d, word ptr [r10+rdx*2]
0x1800930d2  cmp     r8d, r12d
0x1800930d5  jz      short loc_1800930DE
0x1800930d7  cmp     r8w, 0FFFEh
0x1800930dc  jnz     short loc_1800930E5
0x1800930de  lea     r15, aIndexed; "indexed"
0x1800930e5  inc     edx
0x1800930e7  cmp     edx, r9d
0x1800930ea  jl      short loc_1800930CD
0x1800930ec  mov     rcx, [rcx+28h]
0x1800930f0  test    rcx, rcx
0x1800930f3  jnz     short loc_1800930BD
0x1800930f5  test    r15, r15
0x1800930f8  jnz     loc_180093274
0x1800930fe  lea     rcx, [rsp+270h+var_200]
0x180093103  call    sqlite3VdbeCreate
0x180093108  mov     [rsp+270h+var_228], rax
0x18009310d  mov     r15, rax
0x180093110  mov     [rsi+18h], rax
0x180093114  test    rax, rax
0x180093117  jz      loc_180093214
0x18009311d  mov     rdx, [rsp+270h+var_238]
0x180093122  mov     rcx, rdi
0x180093125  mov     rdx, [rdx]
0x180093128  call    sqlite3SchemaToIndex
0x18009312d  mov     ecx, [rdx+4]
0x180093130  mov     r8d, eax
0x180093133  mov     r9d, [rsp+270h+var_240]
0x180093138  mov     [rsp+270h+var_248], ecx
0x18009313c  mov     ecx, [rdx]
0x18009313e  mov     edx, 2
0x180093143  mov     [rsp+270h+var_250], ecx
0x180093147  mov     rcx, r15
0x18009314a  mov     dword ptr [rsp+270h+var_238], eax
0x18009314e  call    sqlite3VdbeAddOp4Int
0x180093153  mov     edx, 1
0x180093158  mov     rcx, r15
0x18009315b  call    sqlite3VdbeChangeP5
0x180093160  lea     r8, qword_1800BA8D0
0x180093167  mov     edx, 6
0x18009316c  call    sqlite3VdbeAddOpList
0x180093171  mov     r10, [rsp+270h+var_228]
0x180093176  mov     r15, rax
0x180093179  mov     edx, dword ptr [rsp+270h+var_238]
0x18009317d  mov     rcx, r10
0x180093180  call    sqlite3VdbeUsesBtree
0x180093185  cmp     [rdi+67h], r14b
0x180093189  jnz     loc_180093214
0x18009318f  mov     eax, [rsp+270h+var_240]
0x180093193  xor     r9d, r9d
0x180093196  mov     [r15+4], edx
0x18009319a  mov     ecx, [rbx+28h]
0x18009319d  mov     [r15+8], ecx
0x1800931a1  mov     rcx, r10
0x1800931a4  mov     [r15+0Ch], eax
0x1800931a8  lea     edx, [r9+2]
0x1800931ac  mov     r8, [rbx]
0x1800931af  call    sqlite3VdbeChangeP4
0x1800931b4  mov     r10, [rsp+270h+var_228]
0x1800931b9  mov     edx, dword ptr [rsp+270h+var_238]
0x1800931bd  cmp     [rdi+67h], r14b
0x1800931c1  jnz     short loc_180093214
0x1800931c3  cmp     [rbp+170h+arg_28], r14d
0x1800931ca  jz      short loc_1800931D1
0x1800931cc  mov     byte ptr [r15+18h], 71h ; 'q'
0x1800931d1  mov     eax, [rbx+28h]
0x1800931d4  mov     ecx, 1
0x1800931d9  mov     [r15+20h], eax
0x1800931dd  mov     [r15+24h], edx
0x1800931e1  lea     rdx, [rsp+270h+var_200]
0x1800931e6  mov     byte ptr [r15+19h], 0FDh
0x1800931eb  movsx   eax, word ptr [rbx+36h]
0x1800931ef  add     eax, ecx
0x1800931f1  mov     [r15+28h], eax
0x1800931f5  movsx   eax, word ptr [rbx+36h]
0x1800931f9  mov     [r15+50h], eax
0x1800931fd  xor     eax, eax
0x1800931ff  mov     [rbp+170h+var_1C8], ecx
0x180093202  mov     [rbp+170h+var_1CC], ecx
0x180093205  mov     rcx, r10
0x180093208  mov     [rbp+170h+var_D0], ax
0x18009320f  call    sqlite3VdbeMakeReady
0x180093214  mov     rcx, rdi
0x180093217  mov     [rsi+8], r12w
0x18009321c  mov     [rsi+20h], rdi
0x180093220  call    sqlite3BtreeLeaveAll
0x180093225  cmp     [rdi+67h], r14b
0x180093229  jnz     short loc_18009328F
0x18009322b  mov     rdx, [rbp+170h+arg_20]
0x180093232  lea     r8, [rsp+270h+var_230]
0x180093237  mov     rcx, rsi
0x18009323a  call    blobSeekToRow
0x18009323f  mov     ebx, [rsp+270h+var_23C]
0x180093243  mov     r13d, eax
0x180093246  inc     ebx
0x180093248  mov     [rsp+270h+var_23C], ebx
0x18009324c  cmp     ebx, 32h ; '2'
0x18009324f  jge     short loc_18009328A
0x180093251  cmp     eax, 11h
0x180093254  jnz     short loc_18009328A
0x180093256  lea     rcx, [rsp+270h+var_200]
0x18009325b  call    sqlite3ParseObjectReset
0x180093260  mov     r14, [rsp+270h+var_230]
0x180093265  mov     r15, [rsp+270h+var_218]
0x18009326a  mov     r12, [rsp+270h+var_210]
0x18009326f  jmp     loc_180092F8C
0x180093274  xor     edx, edx
0x180093276  mov     rcx, rdi
0x180093279  call    sqlite3DbFree
0x18009327e  mov     r8, r15
0x180093281  lea     rdx, aCannotOpenSCol; "cannot open %s column for writing"
0x180093288  jmp     short loc_1800932C5
0x18009328a  mov     r14, [rsp+270h+var_230]
0x18009328f  test    r13d, r13d
0x180093292  jnz     loc_180093327
0x180093298  cmp     [rdi+67h], r13b
0x18009329c  jnz     loc_180093327
0x1800932a2  mov     rax, [rsp+270h+var_208]
0x1800932a7  mov     [rax], rsi
0x1800932aa  jmp     loc_180093345
0x1800932af  xor     edx, edx
0x1800932b1  mov     rcx, rdi
0x1800932b4  call    sqlite3DbFree
0x1800932b9  mov     r8, [rsp+270h+var_220]
0x1800932be  lea     rdx, aNoSuchColumnS_0; "no such column: \"%s\""
0x1800932c5  mov     rcx, rdi
0x1800932c8  call    sqlite3MPrintf
0x1800932cd  mov     r14, rax
0x1800932d0  jmp     short loc_180093317
0x1800932d2  lea     rdx, aCannotOpenView; "cannot open view: %s"
0x1800932d9  jmp     short loc_1800932EB
0x1800932db  lea     rdx, aCannotOpenTabl; "cannot open table without rowid: %s"
0x1800932e2  jmp     short loc_1800932EB
0x1800932e4  lea     rdx, aCannotOpenVirt; "cannot open virtual table: %s"
0x1800932eb  mov     r8, r15
0x1800932ee  lea     rcx, [rsp+270h+var_200]
0x1800932f3  call    sqlite3ErrorMsg
0x1800932f8  cmp     [rsp+270h+var_1F8], r14
0x1800932fd  jz      short loc_180093317
0x1800932ff  xor     edx, edx
0x180093301  mov     rcx, rdi
0x180093304  call    sqlite3DbFree
0x180093309  mov     r14, [rsp+270h+var_1F8]
0x18009330e  mov     [rsp+270h+var_1F8], 0
0x180093317  mov     rcx, rdi
0x18009331a  mov     r13d, 1
0x180093320  call    sqlite3BtreeLeaveAll
0x180093325  jmp     short loc_18009332C
0x180093327  test    rsi, rsi
0x18009332a  jz      short loc_18009333A
0x18009332c  mov     rcx, [rsi+18h]
0x180093330  test    rcx, rcx
0x180093333  jz      short loc_18009333A
0x180093335  call    sqlite3VdbeFinalize
0x18009333a  mov     rdx, rsi
0x18009333d  mov     rcx, rdi
0x180093340  call    sqlite3DbFree
0x180093345  mov     rax, r14
0x180093348  mov     r9, r14
0x18009334b  neg     rax
0x18009334e  mov     edx, r13d
0x180093351  lea     rax, aS_10; "%s"
0x180093358  mov     rcx, rdi
  ... truncated ...
```
