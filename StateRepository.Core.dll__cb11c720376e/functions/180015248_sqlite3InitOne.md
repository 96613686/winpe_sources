# sqlite3InitOne

- ea: `0x180015248`
- end: `0x1800155db`
- name: `sqlite3InitOne`
- size: `915`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x1800151b4`
- `0x18002a050`

## callees

- `0x1800073ec`
- `0x18000a9e0`
- `0x180015248`
- `0x180022288`
- `0x180023b30`
- `0x180024440`
- `0x1800256c4`
- `0x1800293e0`
- `0x1800306b0`
- `0x180046938`
- `0x18004d39c`
- `0x180057d8c`
- `0x180058e24`
- `0x18005952c`
- `0x18005a498`
- `0x18005b4bc`
- `0x18005d458`
- `0x180063a1c`
- `0x180064ef0`
- `0x180068880`
- `0x180087708`

## string_xrefs

- `0x180015290`: `sqlite_temp_master`
- `0x1800152e7`: `CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)`

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
  __int64 v19; // rax
  __int64 v20; // rax
  int v21; // ebx
  int v22; // edx
  __int64 v23; // rdx
  int v24; // eax
  __int64 v25; // r8
  __int64 v26; // rax
  const char *v27; // r8
  __int64 v28; // r8
  __int64 v29; // rax
  __int64 v30; // rbx
  __int64 v31; // rdi
  unsigned int v32; // eax
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // rdx
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
      goto LABEL_57;
    }
    v37 = 0;
    sqlite3BtreeEnter(v14);
    if ( (unsigned int)sqlite3BtreeTxnState(*(_QWORD *)(v13 + 8), v15, v16) )
    {
      v10 = 1;
    }
    else
    {
      v18 = sqlite3BtreeBeginTrans(v17, 0, 0);
      v10 = v18;
      if ( v18 )
      {
        v19 = sqlite3ErrStr(v18);
        sqlite3SetString(a3, a1, v19);
        goto LABEL_52;
      }
      v10 = 1;
      v37 = 1;
    }
    v20 = 0;
    do
    {
      v21 = v20 + 1;
      sqlite3BtreeGetMeta(*(_QWORD *)(v13 + 8), (unsigned int)(v20 + 1), (char *)&v38 + 4 * v20);
      v20 = (unsigned int)v21;
    }
    while ( v21 < 5 );
    if ( (*(_DWORD *)(a1 + 48) & 0x2000000) != 0 )
    {
      v22 = 0;
      v38 = 0;
    }
    else
    {
      v22 = v39;
    }
    **(_DWORD **)(v13 + 24) = v38;
    if ( v22 )
    {
      if ( (_DWORD)v5 || (*(_BYTE *)(a1 + 44) & 0x40) != 0 )
      {
        if ( (v22 & 3) != *(_BYTE *)(a1 + 100) )
        {
          v27 = "attached databases must use the same text encoding as main database";
LABEL_36:
          sqlite3SetString(a3, a1, v27);
LABEL_50:
          if ( v37 )
            sqlite3BtreeCommit(*(_QWORD *)(v13 + 8));
LABEL_52:
          sqlite3BtreeLeave(*(_QWORD *)(v13 + 8));
          if ( !v10 )
            goto LABEL_57;
          goto LABEL_53;
        }
      }
      else
      {
        v23 = v22 & 3;
        if ( !(_BYTE)v23 )
          v23 = 1;
        if ( *(int *)(a1 + 216) > 0 && (_BYTE)v23 != *(_BYTE *)(a1 + 100) && (*(_BYTE *)(a1 + 44) & 4) == 0 )
        {
          v10 = 6;
          goto LABEL_50;
        }
        sqlite3SetTextEncoding(a1, v23);
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
      v28 = *(_QWORD *)(a1 + 32);
      LODWORD(v45) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 64LL);
      v29 = sqlite3MPrintf(a1, "SELECT*FROM\"%w\".%s ORDER BY rowid", *(_QWORD *)(v28 + 32 * v5), v46);
      v30 = *(_QWORD *)(a1 + 512);
      *(_QWORD *)(a1 + 512) = 0;
      v31 = v29;
      v32 = sqlite3_exec(a1, v29, (unsigned int)sqlite3InitCallback, (unsigned int)v40, 0);
      *(_QWORD *)(a1 + 512) = v30;
      v10 = v32;
      if ( !v32 )
        v10 = v42;
      sqlite3DbFree(a1, v31);
      if ( !v10 )
        sqlite3AnalysisLoad(a1, (unsigned int)v5, v33, v34);
      if ( *(_BYTE *)(a1 + 103) )
      {
        v10 = 7;
        sqlite3ResetAllSchemasOfConnection(a1);
        v13 = v12 + *(_QWORD *)(a1 + 32);
      }
      else if ( !v10 || (*(_DWORD *)(a1 + 48) & 0x8000000) != 0 && v10 != 7 )
      {
        v10 = 0;
        v35 = *(_QWORD *)(*(_QWORD *)(a1 + 32) + v12 + 24);
        *(_WORD *)(v35 + 114) |= 1u;
      }
      goto LABEL_50;
    }
    v27 = "unsupported file format";
    goto LABEL_36;
  }
LABEL_53:
  if ( v10 == 7 || v10 == 3082 )
    sqlite3OomFault(a1);
  sqlite3ResetOneSchema(a1);
LABEL_57:
  *(_BYTE *)(a1 + 197) = 0;
  return v10;
}

```

## disassembly

```asm
0x180015248  push    rbp
0x18001524a  push    rbx
0x18001524b  push    rsi
0x18001524c  push    rdi
0x18001524d  push    r12
0x18001524f  push    r13
0x180015251  push    r14
0x180015253  push    r15
0x180015255  lea     rbp, [rsp-1Fh]
0x18001525a  sub     rsp, 0C8h
0x180015261  mov     rax, cs:__security_cookie
0x180015268  xor     rax, rsp
0x18001526b  mov     [rbp+57h+var_50], rax
0x18001526f  mov     ebx, [rcx+2Ch]
0x180015272  lea     rax, aTable; "table"
0x180015279  movsxd  r13, edx
0x18001527c  mov     rdi, r8
0x18001527f  xor     edx, edx
0x180015281  mov     [rbp+57h+var_80], rax
0x180015285  mov     rsi, rcx
0x180015288  mov     [rbp+57h+var_98], r9d
0x18001528c  mov     [rbp+57h+var_90], rdx
0x180015290  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x180015297  mov     [rbp+57h+var_58], rdx
0x18001529b  or      ebx, 0FFFFFFBFh
0x18001529e  lea     r8d, [rdx+1]
0x1800152a2  mov     [rbp+57h+var_9C], edx
0x1800152a5  mov     [rcx+0C5h], r8b
0x1800152ac  cmp     r13d, r8d
0x1800152af  lea     rcx, aSqliteMaster; "sqlite_master"
0x1800152b6  mov     [rbp+57h+var_94], edx
0x1800152b9  cmovnz  rax, rcx
0x1800152bd  mov     [rbp+57h+var_B0], rsi
0x1800152c1  mov     [rbp+57h+var_88], rax
0x1800152c5  lea     r8, [rbp+57h+var_80]
0x1800152c9  mov     [rbp+57h+var_78], rax
0x1800152cd  lea     rcx, [rbp+57h+var_B0]
0x1800152d1  mov     [rbp+57h+var_70], rax
0x1800152d5  xor     r9d, r9d
0x1800152d8  lea     rax, a1; "1"
0x1800152df  mov     [rbp+57h+var_A0], r13d
0x1800152e3  mov     [rbp+57h+var_68], rax
0x1800152e7  lea     rax, aCreateTableXTy; "CREATE TABLE x(type text,name text,tbl_"...
0x1800152ee  mov     [rbp+57h+var_60], rax
0x1800152f2  lea     edx, [r9+5]
0x1800152f6  mov     [rbp+57h+var_A8], rdi
0x1800152fa  call    sqlite3InitCallback
0x1800152ff  and     [rsi+2Ch], ebx
0x180015302  xor     ebx, ebx
0x180015304  mov     r14d, [rbp+57h+var_9C]
0x180015308  test    r14d, r14d
0x18001530b  jnz     loc_180015590
0x180015311  mov     rax, [rsi+20h]
0x180015315  mov     r12, r13
0x180015318  shl     r12, 5
0x18001531c  lea     r15, [r12+rax]
0x180015320  mov     rcx, [r15+8]
0x180015324  test    rcx, rcx
0x180015327  jnz     short loc_18001533C
0x180015329  mov     rax, [rax+38h]
0x18001532d  lea     ecx, [rbx+1]
0x180015330  mov     r14d, ebx
0x180015333  or      [rax+72h], cx
0x180015337  jmp     loc_1800155B2
0x18001533c  mov     [rbp+57h+var_D0], ebx
0x18001533f  call    sqlite3BtreeEnter
0x180015344  mov     rcx, [r15+8]
0x180015348  call    sqlite3BtreeTxnState
0x18001534d  test    eax, eax
0x18001534f  jnz     short loc_180015388
0x180015351  xor     r8d, r8d
0x180015354  xor     edx, edx
0x180015356  call    sqlite3BtreeBeginTrans
0x18001535b  mov     r14d, eax
0x18001535e  test    eax, eax
0x180015360  jz      short loc_18001537C
0x180015362  mov     ecx, eax
0x180015364  call    sqlite3ErrStr
0x180015369  mov     r8, rax
0x18001536c  mov     rdx, rsi
0x18001536f  mov     rcx, rdi
0x180015372  call    sqlite3SetString
0x180015377  jmp     loc_180015582
0x18001537c  mov     r14d, 1
0x180015382  mov     [rbp+57h+var_D0], r14d
0x180015386  jmp     short loc_18001538E
0x180015388  mov     r14d, 1
0x18001538e  mov     eax, ebx
0x180015390  mov     rcx, [r15+8]
0x180015394  lea     ebx, [rax+1]
0x180015397  lea     r8, [rbp+57h+var_C8]
0x18001539b  mov     edx, ebx
0x18001539d  lea     r8, [r8+rax*4]
0x1800153a1  call    sqlite3BtreeGetMeta
0x1800153a6  mov     eax, ebx
0x1800153a8  cmp     ebx, 5
0x1800153ab  jl      short loc_180015390
0x1800153ad  mov     eax, [rsi+30h]
0x1800153b0  bt      rax, 19h
0x1800153b5  jnb     short loc_1800153C2
0x1800153b7  xorps   xmm0, xmm0
0x1800153ba  xor     edx, edx
0x1800153bc  movups  [rbp+57h+var_C8], xmm0
0x1800153c0  jmp     short loc_1800153C5
0x1800153c2  mov     edx, [rbp+57h+var_B8]
0x1800153c5  mov     rcx, [r15+18h]
0x1800153c9  xor     ebx, ebx
0x1800153cb  mov     eax, dword ptr [rbp+57h+var_C8]
0x1800153ce  mov     [rcx], eax
0x1800153d0  test    edx, edx
0x1800153d2  jz      short loc_180015416
0x1800153d4  test    r13d, r13d
0x1800153d7  jnz     loc_18001547A
0x1800153dd  test    byte ptr [rsi+2Ch], 40h
0x1800153e1  jnz     loc_18001547A
0x1800153e7  mov     al, dl
0x1800153e9  and     al, 3
0x1800153eb  movzx   edx, al
0x1800153ee  cmovz   edx, r14d
0x1800153f2  cmp     [rsi+0D8h], ebx
0x1800153f8  jle     short loc_18001540E
0x1800153fa  cmp     dl, [rsi+64h]
0x1800153fd  jz      short loc_18001540E
0x1800153ff  test    byte ptr [rsi+2Ch], 4
0x180015403  jnz     short loc_18001540E
0x180015405  lea     r14d, [rbx+6]
0x180015409  jmp     loc_180015574
0x18001540e  mov     rcx, rsi
0x180015411  call    sqlite3SetTextEncoding
0x180015416  mov     rcx, [r15+18h]
0x18001541a  mov     al, [rsi+64h]
0x18001541d  mov     [rcx+71h], al
0x180015420  mov     r8, [r15+18h]
0x180015424  cmp     [r8+74h], ebx
0x180015428  jnz     short loc_180015450
0x18001542a  mov     ecx, dword ptr [rbp+57h+var_C8+8]
0x18001542d  call    sqlite3AbsInt32
0x180015432  test    eax, eax
0x180015434  mov     ecx, 0FFFFF830h
0x180015439  cmovz   eax, ecx
0x18001543c  mov     [r8+74h], eax
0x180015440  mov     rdx, [r15+18h]
0x180015444  mov     rcx, [r15+8]
0x180015448  mov     edx, [rdx+74h]
0x18001544b  call    sqlite3BtreeSetCacheSize
0x180015450  mov     al, byte ptr [rbp+57h+var_C8+4]
0x180015453  mov     rcx, [r15+18h]
0x180015457  mov     [rcx+70h], al
0x18001545a  mov     rax, [r15+18h]
0x18001545e  cmp     [rax+70h], bl
0x180015461  jnz     short loc_180015467
0x180015463  mov     [rax+70h], r14b
0x180015467  mov     rax, [r15+18h]
0x18001546b  cmp     byte ptr [rax+70h], 4
0x18001546f  jbe     short loc_180015499
0x180015471  lea     r8, aUnsupportedFil; "unsupported file format"
0x180015478  jmp     short loc_180015489
0x18001547a  and     edx, 3
0x18001547d  cmp     dl, [rsi+64h]
0x180015480  jz      short loc_180015416
0x180015482  lea     r8, aAttachedDataba; "attached databases must use the same te"...
0x180015489  mov     rdx, rsi
0x18001548c  mov     rcx, rdi
0x18001548f  call    sqlite3SetString
0x180015494  jmp     loc_180015574
0x180015499  test    r13d, r13d
0x18001549c  jnz     short loc_1800154A9
0x18001549e  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x1800154a2  jl      short loc_1800154A9
0x1800154a4  and     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFDh
0x1800154a9  mov     rax, [r15+8]
0x1800154ad  lea     rdx, aSelectFromWSOr; "SELECT*FROM\"%w\".%s ORDER BY rowid"
0x1800154b4  mov     r8, [rsi+20h]
0x1800154b8  mov     r9, [rbp+57h+var_88]
0x1800154bc  mov     rcx, [rax+8]
0x1800154c0  mov     eax, [rcx+40h]
0x1800154c3  mov     rcx, rsi
0x1800154c6  mov     dword ptr [rbp+57h+var_90], eax
0x1800154c9  mov     r8, [r8+r12]
0x1800154cd  call    sqlite3MPrintf
0x1800154d2  mov     rbx, [rsi+200h]
0x1800154d9  lea     r9, [rbp+57h+var_B0]
0x1800154dd  xor     edx, edx
0x1800154df  lea     r8, sqlite3InitCallback
0x1800154e6  mov     [rsi+200h], rdx
0x1800154ed  mov     rcx, rsi
0x1800154f0  mov     [rsp+100h+var_E0], rdx
0x1800154f5  mov     rdi, rax
0x1800154f8  mov     rdx, rax
0x1800154fb  call    sqlite3_exec
0x180015500  mov     [rsi+200h], rbx
0x180015507  mov     r14d, eax
0x18001550a  xor     ebx, ebx
0x18001550c  mov     rdx, rdi
0x18001550f  test    eax, eax
0x180015511  mov     rcx, rsi
0x180015514  cmovz   r14d, [rbp+57h+var_9C]
0x180015519  call    sqlite3DbFree
0x18001551e  test    r14d, r14d
0x180015521  jnz     short loc_18001552E
0x180015523  mov     edx, r13d
0x180015526  mov     rcx, rsi
0x180015529  call    sqlite3AnalysisLoad
0x18001552e  cmp     [rsi+67h], bl
0x180015531  jz      short loc_18001554A
0x180015533  mov     rcx, rsi
0x180015536  mov     r14d, 7
0x18001553c  call    sqlite3ResetAllSchemasOfConnection
0x180015541  mov     r15, [rsi+20h]
0x180015545  add     r15, r12
0x180015548  jmp     short loc_180015574
0x18001554a  test    r14d, r14d
0x18001554d  jz      short loc_18001555F
0x18001554f  mov     eax, [rsi+30h]
0x180015552  bt      rax, 1Bh
0x180015557  jnb     short loc_180015574
0x180015559  cmp     r14d, 7
0x18001555d  jz      short loc_180015574
0x18001555f  mov     rax, [rsi+20h]
0x180015563  mov     ecx, 1
0x180015568  mov     r14d, ebx
0x18001556b  mov     rdx, [rax+r12+18h]
0x180015570  or      [rdx+72h], cx
0x180015574  cmp     [rbp+57h+var_D0], ebx
0x180015577  jz      short loc_180015582
0x180015579  mov     rcx, [r15+8]
0x18001557d  call    sqlite3BtreeCommit
0x180015582  mov     rcx, [r15+8]
0x180015586  call    sqlite3BtreeLeave
0x18001558b  test    r14d, r14d
0x18001558e  jz      short loc_1800155B2
0x180015590  cmp     r14d, 7
0x180015594  jz      short loc_18001559F
0x180015596  cmp     r14d, 0C0Ah
0x18001559d  jnz     short loc_1800155A7
0x18001559f  mov     rcx, rsi
0x1800155a2  call    sqlite3OomFault
0x1800155a7  mov     edx, r13d
0x1800155aa  mov     rcx, rsi
0x1800155ad  call    sqlite3ResetOneSchema
0x1800155b2  mov     [rsi+0C5h], bl
0x1800155b8  mov     eax, r14d
0x1800155bb  mov     rcx, [rbp+57h+var_50]
0x1800155bf  xor     rcx, rsp; StackCookie
0x1800155c2  call    __security_check_cookie
0x1800155c7  add     rsp, 0C8h
0x1800155ce  pop     r15
0x1800155d0  pop     r14
0x1800155d2  pop     r13
0x1800155d4  pop     r12
0x1800155d6  pop     rdi
0x1800155d7  pop     rsi
0x1800155d8  pop     rbx
0x1800155d9  pop     rbp
0x1800155da  retn
```
