# sqlite3_blob_open

- ea: `0x140087590`
- end: `0x140087b5c`
- name: `sqlite3_blob_open`
- size: `1484`
- prototype: ``
- caller_count: `0`
- callee_count: `26`
- tags: ``

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x14001cf78`
- `0x14001f748`
- `0x1400203ec`
- `0x1400206dc`
- `0x140053e3c`
- `0x140053fec`
- `0x1400560c4`
- `0x140056170`
- `0x1400626b8`
- `0x140062bfc`
- `0x140063280`
- `0x14006561c`
- `0x140065690`
- `0x14006c9dc`
- `0x1400702ec`
- `0x14007399c`
- `0x140073a2c`
- `0x140073ca8`
- `0x140073e08`
- `0x14007ab68`
- `0x14007b980`
- `0x14007e880`
- `0x140087590`
- `0x1400a8010`

## string_xrefs

- `0x140087aa2`: `cannot open virtual table: %s`
- `0x140087a90`: `cannot open view: %s`
- `0x140087a99`: `cannot open table without rowid: %s`
- `0x1400879e9`: `cannot open %s column for writing`

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
  __int64 v11; // rsi
  __int64 v12; // rcx
  unsigned int v13; // r14d
  __int64 v14; // r13
  __int64 Table; // rax
  __int64 v16; // rdi
  __int64 v17; // rdx
  __int64 v18; // r8
  int v19; // ecx
  __int64 v20; // r15
  int v21; // r11d
  __int64 v22; // r12
  const char *v23; // r10
  __int64 v24; // rdx
  unsigned int i; // r8d
  const char *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  int v29; // r8d
  __int64 v30; // rax
  __int64 v31; // r15
  int v32; // r12d
  _DWORD *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // rax
  __int64 v36; // r14
  unsigned int v37; // eax
  unsigned int v38; // edi
  __int64 v39; // rax
  __int64 v40; // rcx
  unsigned int v42; // [rsp+30h] [rbp-D0h]
  __int16 v43; // [rsp+34h] [rbp-CCh]
  BOOL v44; // [rsp+38h] [rbp-C8h]
  int v45; // [rsp+3Ch] [rbp-C4h]
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  const char *v47; // [rsp+48h] [rbp-B8h]
  _QWORD *v48; // [rsp+50h] [rbp-B0h]
  __int64 v49; // [rsp+58h] [rbp-A8h]
  __int64 v50; // [rsp+60h] [rbp-A0h]
  __int64 *v51; // [rsp+68h] [rbp-98h]
  char v52[8]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v53; // [rsp+78h] [rbp-88h]
  int v54; // [rsp+A4h] [rbp-5Ch]
  int v55; // [rsp+A8h] [rbp-58h]
  __int16 v56; // [rsp+198h] [rbp+98h]

  v7 = a7;
  v8 = a3;
  v49 = a3;
  v9 = a2;
  v50 = a2;
  v51 = a7;
  v47 = a4;
  v11 = 0;
  memset_0(v52, 0, 0x1A0u);
  if ( !a7 )
  {
    v12 = 100915;
    return sqlite3MisuseError(v12);
  }
  *a7 = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) || !v8 )
  {
    v12 = 100921;
    return sqlite3MisuseError(v12);
  }
  v13 = 0;
  v45 = 0;
  v44 = a6 != 0;
  v42 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1400C8530)();
  v14 = sqlite3DbMallocZero(a1, 56);
  sqlite3ParseObjectInit(v52, a1);
  if ( !v14 )
    goto LABEL_67;
  while ( 1 )
  {
    if ( v11 )
      sqlite3DbFreeNN(a1);
    v11 = 0;
    v46 = 0;
    if ( !*(_BYTE *)(a1 + 111) )
      btreeEnterAll(a1);
    Table = sqlite3LocateTable(v52, 0, v8, v9);
    v16 = Table;
    if ( !Table )
      goto LABEL_79;
    if ( *(_BYTE *)(Table + 63) == 1 )
    {
      sqlite3ErrorMsg(v52, "cannot open virtual table: %s", v8);
      goto LABEL_79;
    }
    if ( *(char *)(Table + 48) < 0 )
    {
      sqlite3ErrorMsg(v52, "cannot open table without rowid: %s", v8);
      goto LABEL_79;
    }
    if ( *(_BYTE *)(Table + 63) == 2 )
    {
      sqlite3ErrorMsg(v52, "cannot open view: %s", v8);
LABEL_79:
      v39 = v53;
      if ( !v53 )
      {
LABEL_82:
        v38 = 1;
LABEL_83:
        if ( !*(_BYTE *)(a1 + 111) )
          btreeLeaveAll(a1);
        goto LABEL_87;
      }
      v53 = 0;
LABEL_81:
      v11 = v39;
      goto LABEL_82;
    }
    *(_QWORD *)(v14 + 48) = Table;
    v48 = (_QWORD *)(Table + 96);
    v17 = *(_QWORD *)(Table + 96);
    if ( v17 )
    {
      v18 = *(_QWORD *)(a1 + 32);
      v19 = 0;
      if ( *(_QWORD *)(v18 + 24) != v17 )
      {
        do
          ++v19;
        while ( *(_QWORD *)(32LL * v19 + v18 + 24) != v17 );
      }
    }
    else
    {
      v19 = -32768;
    }
    v20 = 0;
    v43 = 0;
    *(_QWORD *)(v14 + 40) = *(_QWORD *)(32LL * v19 + *(_QWORD *)(a1 + 32));
    v21 = *(__int16 *)(Table + 54);
    if ( v21 <= 0 )
    {
LABEL_25:
      if ( (_DWORD)v20 != v21 )
        goto LABEL_26;
      v39 = sqlite3MPrintf(a1, "no such column: \"%s\"", v47);
      goto LABEL_81;
    }
    v22 = *(_QWORD *)(Table + 8);
    while ( (unsigned int)sqlite3StrICmp(*(_QWORD *)(v22 + 24 * v20), v47) )
    {
      v20 = (unsigned int)(v20 + 1);
      v43 = v20;
      if ( (int)v20 >= v21 )
        goto LABEL_25;
    }
LABEL_26:
    if ( a6 )
    {
      v23 = 0;
      if ( (*(_DWORD *)(a1 + 48) & 0x4000LL) != 0 )
      {
        v24 = *(_QWORD *)(v16 + 72);
        if ( v24 )
        {
          do
          {
            for ( i = 0; (signed int)i < *(_DWORD *)(v24 + 40); v23 = v26 )
            {
              v26 = "foreign key";
              if ( *(_DWORD *)(v24 + 16 * (i + 4LL)) != (_DWORD)v20 )
                v26 = v23;
              ++i;
            }
            v24 = *(_QWORD *)(v24 + 8);
          }
          while ( v24 );
          v13 = v42;
          v43 = v20;
        }
      }
      v27 = *(_QWORD *)(v16 + 16);
      if ( v27 )
      {
        do
        {
          if ( *(_WORD *)(v27 + 94) )
          {
            v28 = 0;
            do
            {
              v29 = *(__int16 *)(*(_QWORD *)(v27 + 8) + 2 * v28);
              if ( v29 == (_DWORD)v20 || (_WORD)v29 == 0xFFFE )
                v23 = "indexed";
              v28 = (unsigned int)(v28 + 1);
            }
            while ( (int)v28 < *(unsigned __int16 *)(v27 + 94) );
          }
          v27 = *(_QWORD *)(v27 + 40);
        }
        while ( v27 );
        v13 = v42;
      }
      if ( v23 )
      {
        v11 = sqlite3MPrintf(a1, "cannot open %s column for writing", v23);
        v38 = 1;
        goto LABEL_83;
      }
    }
    v30 = sqlite3VdbeCreate(v52);
    *(_QWORD *)(v14 + 24) = v30;
    v31 = v30;
    if ( v30 )
    {
      v32 = -32768;
      v33 = (_DWORD *)*v48;
      if ( *v48 )
      {
        v34 = *(_QWORD *)(a1 + 32);
        v32 = 0;
        if ( *(_DWORD **)(v34 + 24) != v33 )
        {
          do
            ++v32;
          while ( *(_DWORD **)(32LL * v32 + v34 + 24) != v33 );
        }
      }
      sqlite3VdbeAddOp4Int(v30, 2, v32, v44, *v33, v33[1]);
      v35 = *(int *)(v31 + 144);
      if ( (int)v35 > 0 )
        *(_WORD *)(*(_QWORD *)(v31 + 136) + 24 * v35 - 22) = 1;
      v36 = sqlite3VdbeAddOpList(v31, 6, qword_1400B5C90);
      sqlite3VdbeUsesBtree(v31, (unsigned int)v32);
      if ( !*(_BYTE *)(a1 + 103) )
      {
        *(_DWORD *)(v36 + 4) = v32;
        *(_DWORD *)(v36 + 8) = *(_DWORD *)(v16 + 40);
        *(_DWORD *)(v36 + 12) = v44;
        sqlite3VdbeChangeP4(v31, 2, *(_QWORD *)v16, 0);
        if ( !*(_BYTE *)(a1 + 103) )
        {
          if ( a6 )
            *(_BYTE *)(v36 + 24) = 113;
          *(_DWORD *)(v36 + 32) = *(_DWORD *)(v16 + 40);
          *(_DWORD *)(v36 + 36) = v32;
          *(_BYTE *)(v36 + 25) = -3;
          *(_DWORD *)(v36 + 40) = *(__int16 *)(v16 + 54) + 1;
          *(_DWORD *)(v36 + 80) = *(__int16 *)(v16 + 54);
          v56 = 0;
          v55 = 1;
          v54 = 1;
          sqlite3VdbeMakeReady(v31, v52);
        }
      }
      v13 = v42;
    }
    *(_WORD *)(v14 + 8) = v43;
    *(_QWORD *)(v14 + 32) = a1;
    if ( !*(_BYTE *)(a1 + 111) )
      btreeLeaveAll(a1);
    if ( *(_BYTE *)(a1 + 103) )
      goto LABEL_65;
    v37 = blobSeekToRow(v14, a5, &v46);
    v13 = v37;
    v42 = v37;
    if ( ++v45 >= 50 || v37 != 17 )
      break;
    sqlite3ParseObjectReset(v52);
    sqlite3ParseObjectInit(v52, a1);
    v11 = v46;
    v8 = v49;
    v9 = v50;
  }
  v11 = v46;
LABEL_65:
  if ( v13 )
    goto LABEL_86;
  v7 = v51;
LABEL_67:
  if ( !*(_BYTE *)(a1 + 103) )
  {
    *v7 = v14;
    goto LABEL_69;
  }
  if ( v14 )
  {
LABEL_86:
    v38 = v42;
LABEL_87:
    v40 = *(_QWORD *)(v14 + 24);
    if ( v40 )
      sqlite3VdbeFinalize(v40);
    sqlite3DbFreeNN(a1);
  }
  else
  {
LABEL_69:
    v38 = v42;
  }
  sqlite3ErrorWithMsg(a1, v38, (unsigned __int64)"%s" & -(__int64)(v11 != 0));
  if ( v11 )
    sqlite3DbFreeNN(a1);
  sqlite3ParseObjectReset(v52);
  if ( *(_BYTE *)(a1 + 103) || v38 )
    v38 = apiHandleError(a1, v38);
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1400C8540)();
  return v38;
}

```

## disassembly

```asm
0x140087590  push    rbp
0x140087592  push    rbx
0x140087593  push    rsi
0x140087594  push    rdi
0x140087595  push    r12
0x140087597  push    r13
0x140087599  push    r14
0x14008759b  push    r15
0x14008759d  lea     rbp, [rsp-128h]
0x1400875a5  sub     rsp, 228h
0x1400875ac  mov     rax, cs:__security_cookie
0x1400875b3  xor     rax, rsp
0x1400875b6  mov     [rbp+160h+var_50], rax
0x1400875bd  mov     rdi, [rbp+160h+arg_30]
0x1400875c4  mov     r15, r8
0x1400875c7  mov     [rsp+260h+var_208], r8
0x1400875cc  mov     r12, rdx
0x1400875cf  mov     [rsp+260h+var_200], rdx
0x1400875d4  mov     rbx, rcx
0x1400875d7  xor     r13d, r13d
0x1400875da  mov     [rsp+260h+var_1F8], rdi
0x1400875df  xor     edx, edx; Val
0x1400875e1  mov     [rsp+260h+var_218], r9
0x1400875e6  mov     r8d, 1A0h; Size
0x1400875ec  lea     rcx, [rsp+260h+var_1F0]; void *
0x1400875f1  mov     esi, r13d
0x1400875f4  call    memset_0
0x1400875f9  test    rdi, rdi
0x1400875fc  jnz     short loc_140087608
0x1400875fe  mov     ecx, 18A33h
0x140087603  jmp     loc_140087B34
0x140087608  mov     rcx, rbx
0x14008760b  mov     [rdi], r13
0x14008760e  call    sqlite3SafetyCheckOk
0x140087613  test    eax, eax
0x140087615  jz      loc_140087B2F
0x14008761b  test    r15, r15
0x14008761e  jz      loc_140087B2F
0x140087624  cmp     [rbp+160h+arg_28], r13d
0x14008762b  mov     eax, r13d
0x14008762e  mov     rcx, [rbx+18h]
0x140087632  mov     r14d, r13d
0x140087635  setnz   al
0x140087638  mov     [rsp+260h+var_224], r13d
0x14008763d  mov     [rsp+260h+var_228], eax
0x140087641  mov     [rsp+260h+var_230], r13d
0x140087646  test    rcx, rcx
0x140087649  jz      short loc_140087657
0x14008764b  mov     rax, qword ptr cs:xmmword_1400C8530
0x140087652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140087657  mov     edx, 38h ; '8'
0x14008765c  mov     rcx, rbx
0x14008765f  call    sqlite3DbMallocZero
0x140087664  mov     rdx, rbx
0x140087667  lea     rcx, [rsp+260h+var_1F0]
0x14008766c  mov     r13, rax
0x14008766f  call    sqlite3ParseObjectInit
0x140087674  test    r13, r13
0x140087677  jz      loc_140087A18
0x14008767d  test    rsi, rsi
0x140087680  jz      short loc_14008768D
0x140087682  mov     rdx, rsi
0x140087685  mov     rcx, rbx
0x140087688  call    sqlite3DbFreeNN
0x14008768d  xor     esi, esi
0x14008768f  mov     [rsp+260h+var_220], rsi
0x140087694  cmp     [rbx+6Fh], sil
0x140087698  jnz     short loc_1400876A2
0x14008769a  mov     rcx, rbx
0x14008769d  call    btreeEnterAll
0x1400876a2  mov     r9, r12
0x1400876a5  lea     rcx, [rsp+260h+var_1F0]
0x1400876aa  mov     r8, r15
0x1400876ad  xor     edx, edx
0x1400876af  call    sqlite3LocateTable
0x1400876b4  mov     rdi, rax
0x1400876b7  mov     r12d, 1
0x1400876bd  test    rax, rax
0x1400876c0  jz      loc_140087AB6
0x1400876c6  cmp     [rax+3Fh], r12b
0x1400876ca  jz      loc_140087AA2
0x1400876d0  test    byte ptr [rax+30h], 80h
0x1400876d4  jnz     loc_140087A99
0x1400876da  cmp     byte ptr [rax+3Fh], 2
0x1400876de  jz      loc_140087A90
0x1400876e4  mov     [r13+30h], rax
0x1400876e8  add     rax, 60h ; '`'
0x1400876ec  mov     [rsp+260h+var_210], rax
0x1400876f1  mov     rdx, [rax]
0x1400876f4  test    rdx, rdx
0x1400876f7  jz      short loc_140087718
0x1400876f9  mov     r8, [rbx+20h]
0x1400876fd  xor     ecx, ecx
0x1400876ff  cmp     [r8+18h], rdx
0x140087703  jz      short loc_14008771D
0x140087705  add     ecx, r12d
0x140087708  movsxd  rax, ecx
0x14008770b  shl     rax, 5
0x14008770f  cmp     [rax+r8+18h], rdx
0x140087714  jnz     short loc_140087705
0x140087716  jmp     short loc_14008771D
0x140087718  mov     ecx, 0FFFF8000h
0x14008771d  mov     rax, [rbx+20h]
0x140087721  xor     r15d, r15d
0x140087724  movsxd  rcx, ecx
0x140087727  shl     rcx, 5
0x14008772b  mov     [rsp+260h+var_22C], r15d
0x140087730  mov     rcx, [rcx+rax]
0x140087734  mov     [r13+28h], rcx
0x140087738  movsx   r11d, word ptr [rdi+36h]
0x14008773d  test    r11d, r11d
0x140087740  jle     short loc_14008776F
0x140087742  mov     r12, [rdi+8]
0x140087746  mov     rdx, [rsp+260h+var_218]
0x14008774b  lea     rcx, [r15+r15*2]
0x14008774f  mov     rcx, [r12+rcx*8]
0x140087753  call    sqlite3StrICmp
0x140087758  test    eax, eax
0x14008775a  jz      short loc_140087778
0x14008775c  inc     r15d
0x14008775f  mov     [rsp+260h+var_22C], r15d
0x140087764  cmp     r15d, r11d
0x140087767  jl      short loc_140087746
0x140087769  mov     r12d, 1
0x14008776f  cmp     r15d, r11d
0x140087772  jz      loc_140087A7A
0x140087778  cmp     [rbp+160h+arg_28], esi
0x14008777e  jz      loc_140087829
0x140087784  mov     eax, [rbx+30h]
0x140087787  xor     r10d, r10d
0x14008778a  bt      rax, 0Eh
0x14008778f  jnb     short loc_1400877DA
0x140087791  mov     rdx, [rdi+48h]
0x140087795  test    rdx, rdx
0x140087798  jz      short loc_1400877DA
0x14008779a  xor     r8d, r8d
0x14008779d  cmp     [rdx+28h], esi
0x1400877a0  jle     short loc_1400877C7
0x1400877a2  mov     ecx, r8d
0x1400877a5  lea     rax, aForeignKey; "foreign key"
0x1400877ac  add     rcx, 4
0x1400877b0  add     rcx, rcx
0x1400877b3  cmp     [rdx+rcx*8], r15d
0x1400877b7  cmovnz  rax, r10
0x1400877bb  inc     r8d
0x1400877be  mov     r10, rax
0x1400877c1  cmp     r8d, [rdx+28h]
0x1400877c5  jl      short loc_1400877A2
0x1400877c7  mov     rdx, [rdx+8]
0x1400877cb  test    rdx, rdx
0x1400877ce  jnz     short loc_14008779A
0x1400877d0  mov     r14d, [rsp+260h+var_230]
0x1400877d5  mov     [rsp+260h+var_22C], r15d
0x1400877da  mov     rcx, [rdi+10h]
0x1400877de  test    rcx, rcx
0x1400877e1  jz      short loc_140087820
0x1400877e3  movzx   r9d, word ptr [rcx+5Eh]
0x1400877e8  test    r9d, r9d
0x1400877eb  jz      short loc_140087812
0x1400877ed  mov     r11, [rcx+8]
0x1400877f1  xor     edx, edx
0x1400877f3  movsx   r8d, word ptr [r11+rdx*2]
0x1400877f8  cmp     r8d, r15d
0x1400877fb  jz      short loc_140087804
0x1400877fd  cmp     r8w, 0FFFEh
0x140087802  jnz     short loc_14008780B
0x140087804  lea     r10, aIndexed; "indexed"
0x14008780b  inc     edx
0x14008780d  cmp     edx, r9d
0x140087810  jl      short loc_1400877F3
0x140087812  mov     rcx, [rcx+28h]
0x140087816  test    rcx, rcx
0x140087819  jnz     short loc_1400877E3
0x14008781b  mov     r14d, [rsp+260h+var_230]
0x140087820  test    r10, r10
0x140087823  jnz     loc_1400879E6
0x140087829  lea     rcx, [rsp+260h+var_1F0]
0x14008782e  call    sqlite3VdbeCreate
0x140087833  mov     [r13+18h], rax
0x140087837  mov     r15, rax
0x14008783a  test    rax, rax
0x14008783d  jz      loc_140087963
0x140087843  mov     rcx, [rsp+260h+var_210]
0x140087848  mov     r12d, 0FFFF8000h
0x14008784e  mov     r14d, 1
0x140087854  mov     rcx, [rcx]
0x140087857  test    rcx, rcx
0x14008785a  jz      short loc_14008787A
0x14008785c  mov     rdx, [rbx+20h]
0x140087860  xor     r12d, r12d
0x140087863  cmp     [rdx+18h], rcx
0x140087867  jz      short loc_14008787A
0x140087869  add     r12d, r14d
0x14008786c  movsxd  rax, r12d
0x14008786f  shl     rax, 5
0x140087873  cmp     [rax+rdx+18h], rcx
0x140087878  jnz     short loc_140087869
0x14008787a  mov     eax, [rcx+4]
0x14008787d  mov     r8d, r12d
0x140087880  mov     r9d, [rsp+260h+var_228]
0x140087885  mov     edx, 2
0x14008788a  mov     [rsp+260h+var_238], eax
0x14008788e  mov     eax, [rcx]
0x140087890  mov     rcx, r15
0x140087893  mov     [rsp+260h+var_240], eax
0x140087897  call    sqlite3VdbeAddOp4Int
0x14008789c  movsxd  rax, dword ptr [r15+90h]
0x1400878a3  test    eax, eax
0x1400878a5  jle     short loc_1400878B8
0x1400878a7  lea     rcx, [rax+rax*2]
0x1400878ab  mov     rax, [r15+88h]
0x1400878b2  mov     [rax+rcx*8-16h], r14w
0x1400878b8  lea     r8, qword_1400B5C90
0x1400878bf  mov     edx, 6
0x1400878c4  mov     rcx, r15
0x1400878c7  call    sqlite3VdbeAddOpList
0x1400878cc  mov     edx, r12d
0x1400878cf  mov     rcx, r15
0x1400878d2  mov     r14, rax
0x1400878d5  call    sqlite3VdbeUsesBtree
0x1400878da  cmp     [rbx+67h], sil
0x1400878de  jnz     short loc_14008795E
0x1400878e0  mov     eax, [rsp+260h+var_228]
0x1400878e4  xor     r9d, r9d
0x1400878e7  mov     [r14+4], r12d
0x1400878eb  mov     ecx, [rdi+28h]
0x1400878ee  mov     [r14+8], ecx
0x1400878f2  mov     rcx, r15
0x1400878f5  mov     [r14+0Ch], eax
0x1400878f9  lea     edx, [r9+2]
0x1400878fd  mov     r8, [rdi]
0x140087900  call    sqlite3VdbeChangeP4
0x140087905  cmp     [rbx+67h], sil
0x140087909  jnz     short loc_14008795E
0x14008790b  cmp     [rbp+160h+arg_28], esi
0x140087911  jz      short loc_140087918
0x140087913  mov     byte ptr [r14+18h], 71h ; 'q'
0x140087918  mov     eax, [rdi+28h]
0x14008791b  lea     rdx, [rsp+260h+var_1F0]
0x140087920  mov     [r14+20h], eax
0x140087924  mov     rcx, r15
0x140087927  mov     [r14+24h], r12d
0x14008792b  mov     byte ptr [r14+19h], 0FDh
0x140087930  movsx   eax, word ptr [rdi+36h]
0x140087934  inc     eax
0x140087936  mov     [r14+28h], eax
0x14008793a  movsx   eax, word ptr [rdi+36h]
0x14008793e  mov     [r14+50h], eax
0x140087942  xor     eax, eax
0x140087944  mov     [rbp+160h+var_C8], ax
0x14008794b  mov     [rbp+160h+var_1B8], 1
0x140087952  mov     [rbp+160h+var_1BC], 1
0x140087959  call    sqlite3VdbeMakeReady
0x14008795e  mov     r14d, [rsp+260h+var_230]
0x140087963  mov     eax, [rsp+260h+var_22C]
0x140087967  mov     [r13+8], ax
0x14008796c  mov     [r13+20h], rbx
0x140087970  cmp     [rbx+6Fh], sil
0x140087974  jnz     short loc_14008797E
0x140087976  mov     rcx, rbx
0x140087979  call    btreeLeaveAll
0x14008797e  cmp     [rbx+67h], sil
0x140087982  jnz     loc_140087A0A
0x140087988  mov     rdx, [rbp+160h+arg_20]
0x14008798f  lea     r8, [rsp+260h+var_220]
0x140087994  mov     rcx, r13
0x140087997  call    blobSeekToRow
0x14008799c  mov     r12d, [rsp+260h+var_224]
0x1400879a1  mov     r14d, eax
0x1400879a4  inc     r12d
0x1400879a7  mov     [rsp+260h+var_230], eax
0x1400879ab  mov     [rsp+260h+var_224], r12d
0x1400879b0  cmp     r12d, 32h ; '2'
0x1400879b4  jge     short loc_140087A05
0x1400879b6  cmp     eax, 11h
0x1400879b9  jnz     short loc_140087A05
0x1400879bb  lea     rcx, [rsp+260h+var_1F0]
0x1400879c0  call    sqlite3ParseObjectReset
0x1400879c5  mov     rdx, rbx
0x1400879c8  lea     rcx, [rsp+260h+var_1F0]
0x1400879cd  call    sqlite3ParseObjectInit
0x1400879d2  mov     rsi, [rsp+260h+var_220]
0x1400879d7  mov     r15, [rsp+260h+var_208]
0x1400879dc  mov     r12, [rsp+260h+var_200]
0x1400879e1  jmp     loc_14008767D
0x1400879e6  mov     r8, r10
0x1400879e9  lea     rdx, aCannotOpenSCol; "cannot open %s column for writing"
0x1400879f0  mov     rcx, rbx
0x1400879f3  call    sqlite3MPrintf
0x1400879f8  mov     rsi, rax
0x1400879fb  mov     edi, 1
0x140087a00  jmp     loc_140087ACF
0x140087a05  mov     rsi, [rsp+260h+var_220]
0x140087a0a  test    r14d, r14d
0x140087a0d  jnz     loc_140087AE8
0x140087a13  mov     rdi, [rsp+260h+var_1F8]
0x140087a18  cmp     byte ptr [rbx+67h], 0
0x140087a1c  jnz     loc_140087ADF
0x140087a22  mov     [rdi], r13
0x140087a25  mov     edi, [rsp+260h+var_230]
  ... truncated ...
```
