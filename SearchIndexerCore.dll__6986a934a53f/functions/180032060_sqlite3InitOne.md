# sqlite3InitOne

- ea: `0x180032060`
- end: `0x180032469`
- name: `sqlite3InitOne`
- size: `1033`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800286a4`
- `0x180031fd0`

## callees

- `0x18001f740`
- `0x180020610`
- `0x180031e2c`
- `0x180031f40`
- `0x180031fb0`
- `0x180032060`
- `0x180032470`
- `0x1800324d0`
- `0x1800325b0`
- `0x180032e28`
- `0x18003352c`
- `0x18003f8d0`
- `0x18003fb44`
- `0x180040e00`
- `0x180041d10`
- `0x180044158`
- `0x180059d90`
- `0x18005a044`
- `0x18006dc30`
- `0x1800766c8`
- `0x1800789c0`

## string_xrefs

- `0x1800320a8`: `sqlite_temp_master`
- `0x1800320ff`: `CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)`

## pseudocode

```c
__int64 __fastcall sqlite3InitOne(__int64 a1, int a2, __int64 a3, int a4)
{
  int v4; // ebx
  __int64 v5; // r13
  const char *v8; // rax
  unsigned int v9; // ebx
  unsigned int v10; // r14d
  __int64 v11; // rax
  __int64 v12; // r12
  __int64 v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // rcx
  unsigned int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // rax
  int v22; // ebx
  int v23; // edx
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rax
  __int64 v27; // r8
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rdi
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v34; // rdx
  const char *v35; // r8
  __int64 v36; // rax
  int v37; // [rsp+30h] [rbp-79h]
  __int128 v38; // [rsp+38h] [rbp-71h] BYREF
  int v39; // [rsp+48h] [rbp-61h]
  _QWORD v40[2]; // [rsp+50h] [rbp-59h] BYREF
  int v41; // [rsp+60h] [rbp-49h]
  unsigned int v42; // [rsp+64h] [rbp-45h]
  int v43; // [rsp+68h] [rbp-41h]
  int v44; // [rsp+6Ch] [rbp-3Dh]
  __int64 v45; // [rsp+70h] [rbp-39h]
  const char *v46; // [rsp+78h] [rbp-31h]
  _QWORD v47[6]; // [rsp+80h] [rbp-29h] BYREF

  v4 = *(_DWORD *)(a1 + 44);
  v5 = a2;
  v47[0] = "table";
  v43 = a4;
  v45 = 0;
  v8 = "sqlite_temp_master";
  v47[5] = 0;
  v9 = v4 | 0xFFFFFFBF;
  v42 = 0;
  *(_BYTE *)(a1 + 197) = 1;
  v44 = 0;
  if ( a2 != 1 )
    v8 = "sqlite_master";
  v40[0] = a1;
  v46 = v8;
  v47[1] = v8;
  v47[2] = v8;
  v41 = a2;
  v47[3] = "1";
  v47[4] = "CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)";
  v40[1] = a3;
  sqlite3InitCallback(v40, 5, v47);
  *(_DWORD *)(a1 + 44) &= v9;
  v10 = v42;
  if ( !v42 )
  {
    v11 = *(_QWORD *)(a1 + 32);
    v12 = 32 * v5;
    v13 = 32 * v5 + v11;
    v14 = *(_QWORD *)(v13 + 8);
    if ( !v14 )
    {
      v10 = 0;
      *(_WORD *)(*(_QWORD *)(v11 + 56) + 114LL) |= 1u;
      goto LABEL_33;
    }
    v37 = 0;
    sqlite3BtreeEnter(v14);
    if ( (unsigned int)sqlite3BtreeTxnState(*(_QWORD *)(v13 + 8), v15, v16) )
    {
      v10 = 1;
    }
    else
    {
      if ( *(_BYTE *)(v17 + 17) || !*(_BYTE *)(v17 + 16) )
      {
        v18 = btreeBeginTrans(v17, 0, 0);
        v10 = v18;
        if ( v18 )
        {
          v36 = sqlite3ErrStr(v18, v19, v20);
          sqlite3SetString(a3, a1, v36);
          goto LABEL_32;
        }
      }
      v10 = 1;
      v37 = 1;
    }
    v21 = 0;
    do
    {
      v22 = v21 + 1;
      sqlite3BtreeGetMeta(*(_QWORD *)(v13 + 8), (unsigned int)(v21 + 1), (char *)&v38 + 4 * v21);
      v21 = (unsigned int)v22;
    }
    while ( v22 < 5 );
    if ( (*(_DWORD *)(a1 + 48) & 0x2000000) != 0 )
    {
      v23 = 0;
      v38 = 0;
    }
    else
    {
      v23 = v39;
    }
    **(_DWORD **)(v13 + 24) = v38;
    if ( v23 )
    {
      if ( (_DWORD)v5 || (*(_BYTE *)(a1 + 44) & 0x40) != 0 )
      {
        if ( (v23 & 3) != *(_BYTE *)(a1 + 100) )
        {
          v35 = "attached databases must use the same text encoding as main database";
LABEL_48:
          sqlite3SetString(a3, a1, v35);
          goto LABEL_30;
        }
      }
      else
      {
        v34 = v23 & 3;
        if ( !(_BYTE)v34 )
          v34 = 1;
        if ( *(int *)(a1 + 216) > 0 && (_BYTE)v34 != *(_BYTE *)(a1 + 100) && (*(_BYTE *)(a1 + 44) & 4) == 0 )
        {
          v10 = 6;
LABEL_30:
          if ( v37 )
            sqlite3BtreeCommit(*(_QWORD *)(v13 + 8));
LABEL_32:
          sqlite3BtreeLeave(*(_QWORD *)(v13 + 8));
          if ( !v10 )
            goto LABEL_33;
          goto LABEL_57;
        }
        sqlite3SetTextEncoding(a1, v34);
      }
    }
    *(_BYTE *)(*(_QWORD *)(v13 + 24) + 113LL) = *(_BYTE *)(a1 + 100);
    if ( !*(_DWORD *)(*(_QWORD *)(v13 + 24) + 116LL) )
    {
      v24 = sqlite3AbsInt32(DWORD2(v38));
      if ( !v24 )
        v24 = -2000;
      *(_DWORD *)(v25 + 116) = v24;
      sqlite3BtreeSetCacheSize(*(_QWORD *)(v13 + 8), *(unsigned int *)(*(_QWORD *)(v13 + 24) + 116LL));
    }
    *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) = BYTE4(v38);
    v26 = *(_QWORD *)(v13 + 24);
    if ( !*(_BYTE *)(v26 + 112) )
      *(_BYTE *)(v26 + 112) = 1;
    if ( *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) <= 4u )
    {
      if ( !(_DWORD)v5 && SDWORD1(v38) >= 4 )
        *(_QWORD *)(a1 + 48) &= ~2uLL;
      v27 = *(_QWORD *)(a1 + 32);
      LODWORD(v45) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 64LL);
      v28 = sqlite3MPrintf(a1, "SELECT*FROM\"%w\".%s ORDER BY rowid", *(_QWORD *)(v27 + 32 * v5), v46);
      v29 = *(_QWORD *)(a1 + 512);
      *(_QWORD *)(a1 + 512) = 0;
      v30 = v28;
      v31 = sqlite3_exec(a1, v28, (unsigned int)sqlite3InitCallback, (unsigned int)v40, 0);
      *(_QWORD *)(a1 + 512) = v29;
      v10 = v31;
      if ( !v31 )
        v10 = v42;
      sqlite3DbFree(a1, v30);
      if ( !v10 )
        sqlite3AnalysisLoad(a1, (unsigned int)v5);
      if ( *(_BYTE *)(a1 + 103) )
      {
        v10 = 7;
        sqlite3ResetAllSchemasOfConnection(a1);
        v13 = v12 + *(_QWORD *)(a1 + 32);
      }
      else if ( !v10 || (*(_DWORD *)(a1 + 48) & 0x8000000) != 0 && v10 != 7 )
      {
        v10 = 0;
        v32 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + v12 + 24);
        *(_WORD *)(v32 + 114) |= 1u;
      }
      goto LABEL_30;
    }
    v35 = "unsupported file format";
    goto LABEL_48;
  }
LABEL_57:
  if ( v10 == 7 || v10 == 3082 )
    sqlite3OomFault(a1);
  sqlite3ResetOneSchema(a1);
LABEL_33:
  *(_BYTE *)(a1 + 197) = 0;
  return v10;
}

```

## disassembly

```asm
0x180032060  push    rbp
0x180032062  push    rbx
0x180032063  push    rsi
0x180032064  push    rdi
0x180032065  push    r12
0x180032067  push    r13
0x180032069  push    r14
0x18003206b  push    r15
0x18003206d  lea     rbp, [rsp-1Fh]
0x180032072  sub     rsp, 0C8h
0x180032079  mov     rax, cs:__security_cookie
0x180032080  xor     rax, rsp
0x180032083  mov     [rbp+57h+var_50], rax
0x180032087  mov     ebx, [rcx+2Ch]
0x18003208a  lea     rax, aTable; "table"
0x180032091  movsxd  r13, edx
0x180032094  mov     rdi, r8
0x180032097  xor     edx, edx
0x180032099  mov     [rbp+57h+var_80], rax
0x18003209d  mov     rsi, rcx
0x1800320a0  mov     [rbp+57h+var_98], r9d
0x1800320a4  mov     [rbp+57h+var_90], rdx
0x1800320a8  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x1800320af  mov     [rbp+57h+var_58], rdx
0x1800320b3  or      ebx, 0FFFFFFBFh
0x1800320b6  lea     r8d, [rdx+1]
0x1800320ba  mov     [rbp+57h+var_9C], edx
0x1800320bd  mov     [rcx+0C5h], r8b
0x1800320c4  cmp     r13d, r8d
0x1800320c7  lea     rcx, aSqliteMaster; "sqlite_master"
0x1800320ce  mov     [rbp+57h+var_94], edx
0x1800320d1  cmovnz  rax, rcx
0x1800320d5  mov     [rbp+57h+var_B0], rsi
0x1800320d9  mov     [rbp+57h+var_88], rax
0x1800320dd  lea     r8, [rbp+57h+var_80]
0x1800320e1  mov     [rbp+57h+var_78], rax
0x1800320e5  lea     rcx, [rbp+57h+var_B0]
0x1800320e9  mov     [rbp+57h+var_70], rax
0x1800320ed  xor     r9d, r9d
0x1800320f0  lea     rax, a1; "1"
0x1800320f7  mov     [rbp+57h+var_A0], r13d
0x1800320fb  mov     [rbp+57h+var_68], rax
0x1800320ff  lea     rax, aCreateTableXTy; "CREATE TABLE x(type text,name text,tbl_"...
0x180032106  mov     [rbp+57h+var_60], rax
0x18003210a  lea     edx, [r9+5]
0x18003210e  mov     [rbp+57h+var_A8], rdi
0x180032112  call    sqlite3InitCallback
0x180032117  and     [rsi+2Ch], ebx
0x18003211a  xor     ebx, ebx
0x18003211c  mov     r14d, [rbp+57h+var_9C]
0x180032120  test    r14d, r14d
0x180032123  jnz     loc_180032442
0x180032129  mov     rax, [rsi+20h]
0x18003212d  mov     r12, r13
0x180032130  shl     r12, 5
0x180032134  lea     r15, [r12+rax]
0x180032138  mov     rcx, [r15+8]
0x18003213c  test    rcx, rcx
0x18003213f  jz      loc_180032320
0x180032145  mov     [rbp+57h+var_D0], ebx
0x180032148  call    sqlite3BtreeEnter
0x18003214d  mov     rcx, [r15+8]
0x180032151  call    sqlite3BtreeTxnState
0x180032156  test    eax, eax
0x180032158  jnz     loc_1800323C5
0x18003215e  cmp     [rcx+11h], bl
0x180032161  jnz     short loc_180032168
0x180032163  cmp     [rcx+10h], bl
0x180032166  jnz     short loc_18003217D
0x180032168  xor     r8d, r8d
0x18003216b  xor     edx, edx
0x18003216d  call    btreeBeginTrans
0x180032172  mov     r14d, eax
0x180032175  test    eax, eax
0x180032177  jnz     loc_1800323D0
0x18003217d  mov     r14d, 1
0x180032183  mov     [rbp+57h+var_D0], r14d
0x180032187  mov     eax, ebx
0x180032189  mov     rcx, [r15+8]
0x18003218d  lea     ebx, [rax+1]
0x180032190  lea     r8, [rbp+57h+var_C8]
0x180032194  mov     edx, ebx
0x180032196  lea     r8, [r8+rax*4]
0x18003219a  call    sqlite3BtreeGetMeta
0x18003219f  mov     eax, ebx
0x1800321a1  cmp     ebx, 5
0x1800321a4  jl      short loc_180032189
0x1800321a6  mov     eax, [rsi+30h]
0x1800321a9  bt      rax, 19h
0x1800321ae  jb      loc_1800323EA
0x1800321b4  mov     edx, [rbp+57h+var_B8]
0x1800321b7  mov     rcx, [r15+18h]
0x1800321bb  xor     ebx, ebx
0x1800321bd  mov     eax, dword ptr [rbp+57h+var_C8]
0x1800321c0  mov     [rcx], eax
0x1800321c2  test    edx, edx
0x1800321c4  jnz     loc_180032332
0x1800321ca  mov     rcx, [r15+18h]
0x1800321ce  mov     al, [rsi+64h]
0x1800321d1  mov     [rcx+71h], al
0x1800321d4  mov     r8, [r15+18h]
0x1800321d8  cmp     [r8+74h], ebx
0x1800321dc  jnz     short loc_180032204
0x1800321de  mov     ecx, dword ptr [rbp+57h+var_C8+8]
0x1800321e1  call    sqlite3AbsInt32
0x1800321e6  test    eax, eax
0x1800321e8  mov     ecx, 0FFFFF830h
0x1800321ed  cmovz   eax, ecx
0x1800321f0  mov     [r8+74h], eax
0x1800321f4  mov     rdx, [r15+18h]
0x1800321f8  mov     rcx, [r15+8]
0x1800321fc  mov     edx, [rdx+74h]
0x1800321ff  call    sqlite3BtreeSetCacheSize
0x180032204  mov     al, byte ptr [rbp+57h+var_C8+4]
0x180032207  mov     rcx, [r15+18h]
0x18003220b  mov     [rcx+70h], al
0x18003220e  mov     rax, [r15+18h]
0x180032212  cmp     [rax+70h], bl
0x180032215  jz      loc_180032416
0x18003221b  mov     rax, [r15+18h]
0x18003221f  cmp     byte ptr [rax+70h], 4
0x180032223  ja      loc_18003241F
0x180032229  test    r13d, r13d
0x18003222c  jz      loc_180032371
0x180032232  mov     rax, [r15+8]
0x180032236  lea     rdx, aSelectFromWSOr; "SELECT*FROM\"%w\".%s ORDER BY rowid"
0x18003223d  mov     r8, [rsi+20h]
0x180032241  mov     r9, [rbp+57h+var_88]
0x180032245  mov     rcx, [rax+8]
0x180032249  mov     eax, [rcx+40h]
0x18003224c  mov     rcx, rsi
0x18003224f  mov     dword ptr [rbp+57h+var_90], eax
0x180032252  mov     r8, [r8+r12]
0x180032256  call    sqlite3MPrintf
0x18003225b  mov     rbx, [rsi+200h]
0x180032262  lea     r9, [rbp+57h+var_B0]
0x180032266  xor     edx, edx
0x180032268  lea     r8, sqlite3InitCallback
0x18003226f  mov     [rsi+200h], rdx
0x180032276  mov     rcx, rsi
0x180032279  mov     [rsp+100h+var_E0], rdx
0x18003227e  mov     rdi, rax
0x180032281  mov     rdx, rax
0x180032284  call    sqlite3_exec
0x180032289  mov     [rsi+200h], rbx
0x180032290  mov     r14d, eax
0x180032293  xor     ebx, ebx
0x180032295  mov     rdx, rdi
0x180032298  test    eax, eax
0x18003229a  mov     rcx, rsi
0x18003229d  cmovz   r14d, [rbp+57h+var_9C]
0x1800322a2  call    sqlite3DbFree
0x1800322a7  test    r14d, r14d
0x1800322aa  jz      loc_180032361
0x1800322b0  cmp     [rsi+67h], bl
0x1800322b3  jnz     loc_180032428
0x1800322b9  test    r14d, r14d
0x1800322bc  jnz     loc_180032385
0x1800322c2  mov     rax, [rsi+20h]
0x1800322c6  mov     ecx, 1
0x1800322cb  mov     r14d, ebx
0x1800322ce  mov     rdx, [rax+r12+18h]
0x1800322d3  or      [rdx+72h], cx
0x1800322d7  cmp     [rbp+57h+var_D0], ebx
0x1800322da  jz      short loc_1800322E5
0x1800322dc  mov     rcx, [r15+8]
0x1800322e0  call    sqlite3BtreeCommit
0x1800322e5  mov     rcx, [r15+8]
0x1800322e9  call    sqlite3BtreeLeave
0x1800322ee  test    r14d, r14d
0x1800322f1  jnz     loc_180032442
0x1800322f7  mov     [rsi+0C5h], bl
0x1800322fd  mov     eax, r14d
0x180032300  mov     rcx, [rbp+57h+var_50]
0x180032304  xor     rcx, rsp; StackCookie
0x180032307  call    __security_check_cookie
0x18003230c  add     rsp, 0C8h
0x180032313  pop     r15
0x180032315  pop     r14
0x180032317  pop     r13
0x180032319  pop     r12
0x18003231b  pop     rdi
0x18003231c  pop     rsi
0x18003231d  pop     rbx
0x18003231e  pop     rbp
0x18003231f  retn
0x180032320  mov     rax, [rax+38h]
0x180032324  mov     ecx, 1
0x180032329  mov     r14d, ebx
0x18003232c  or      [rax+72h], cx
0x180032330  jmp     short loc_1800322F7
0x180032332  test    r13d, r13d
0x180032335  jnz     short loc_1800323A2
0x180032337  test    byte ptr [rsi+2Ch], 40h
0x18003233b  jnz     short loc_1800323A2
0x18003233d  mov     al, dl
0x18003233f  and     al, 3
0x180032341  movzx   edx, al
0x180032344  cmovz   edx, r14d
0x180032348  cmp     [rsi+0D8h], ebx
0x18003234e  jg      loc_1800323F8
0x180032354  mov     rcx, rsi
0x180032357  call    sqlite3SetTextEncoding
0x18003235c  jmp     loc_1800321CA
0x180032361  mov     edx, r13d
0x180032364  mov     rcx, rsi
0x180032367  call    sqlite3AnalysisLoad
0x18003236c  jmp     loc_1800322B0
0x180032371  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x180032375  jl      loc_180032232
0x18003237b  and     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFDh
0x180032380  jmp     loc_180032232
0x180032385  mov     eax, [rsi+30h]
0x180032388  bt      rax, 1Bh
0x18003238d  jnb     loc_1800322D7
0x180032393  cmp     r14d, 7
0x180032397  jz      loc_1800322D7
0x18003239d  jmp     loc_1800322C2
0x1800323a2  and     edx, 3
0x1800323a5  cmp     dl, [rsi+64h]
0x1800323a8  jz      loc_1800321CA
0x1800323ae  lea     r8, aAttachedDataba; "attached databases must use the same te"...
0x1800323b5  mov     rdx, rsi
0x1800323b8  mov     rcx, rdi
0x1800323bb  call    sqlite3SetString
0x1800323c0  jmp     loc_1800322D7
0x1800323c5  mov     r14d, 1
0x1800323cb  jmp     loc_180032187
0x1800323d0  mov     ecx, eax
0x1800323d2  call    sqlite3ErrStr
0x1800323d7  mov     r8, rax
0x1800323da  mov     rdx, rsi
0x1800323dd  mov     rcx, rdi
0x1800323e0  call    sqlite3SetString
0x1800323e5  jmp     loc_1800322E5
0x1800323ea  xorps   xmm0, xmm0
0x1800323ed  xor     edx, edx
0x1800323ef  movups  [rbp+57h+var_C8], xmm0
0x1800323f3  jmp     loc_1800321B7
0x1800323f8  cmp     dl, [rsi+64h]
0x1800323fb  jz      loc_180032354
0x180032401  test    byte ptr [rsi+2Ch], 4
0x180032405  jnz     loc_180032354
0x18003240b  mov     r14d, 6
0x180032411  jmp     loc_1800322D7
0x180032416  mov     [rax+70h], r14b
0x18003241a  jmp     loc_18003221B
0x18003241f  lea     r8, aUnsupportedFil; "unsupported file format"
0x180032426  jmp     short loc_1800323B5
0x180032428  mov     rcx, rsi
0x18003242b  mov     r14d, 7
0x180032431  call    sqlite3ResetAllSchemasOfConnection
0x180032436  mov     r15, [rsi+20h]
0x18003243a  add     r15, r12
0x18003243d  jmp     loc_1800322D7
0x180032442  cmp     r14d, 7
0x180032446  jz      short loc_180032451
0x180032448  cmp     r14d, 0C0Ah
0x18003244f  jnz     short loc_180032459
0x180032451  mov     rcx, rsi
0x180032454  call    sqlite3OomFault
0x180032459  mov     edx, r13d
0x18003245c  mov     rcx, rsi
0x18003245f  call    sqlite3ResetOneSchema
0x180032464  jmp     loc_1800322F7
```
