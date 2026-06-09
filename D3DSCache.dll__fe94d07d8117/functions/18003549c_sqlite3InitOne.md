# sqlite3InitOne

- ea: `0x18003549c`
- end: `0x18003582f`
- name: `sqlite3InitOne`
- size: `915`
- prototype: ``
- caller_count: `2`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x180021aa0`
- `0x18003540c`

## callees

- `0x180011a14`
- `0x180020410`
- `0x1800334f0`
- `0x18003549c`
- `0x1800363c8`
- `0x180036770`
- `0x18003b5b4`
- `0x18003c8d4`
- `0x18003f280`
- `0x180042bb0`
- `0x1800449f0`
- `0x18007650c`
- `0x180077c74`
- `0x180079994`
- `0x18007a268`
- `0x18007acd8`
- `0x18007ed94`
- `0x180089a6c`
- `0x180089aec`
- `0x18008add8`
- `0x18008ae20`

## string_xrefs

- `0x1800354e4`: `sqlite_temp_master`
- `0x18003553b`: `CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)`

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
  __int64 v15; // rcx
  unsigned int v16; // eax
  __int64 v17; // rax
  __int64 v18; // rax
  int v19; // ebx
  int v20; // edx
  char v21; // dl
  int v22; // eax
  __int64 v23; // r8
  __int64 v24; // rax
  const char *v25; // r8
  __int64 v26; // r8
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rdi
  unsigned int v30; // eax
  __int64 v31; // r8
  __int64 v32; // rdx
  int v34; // [rsp+30h] [rbp-79h]
  __int128 v35; // [rsp+38h] [rbp-71h] BYREF
  int v36; // [rsp+48h] [rbp-61h]
  _QWORD v37[2]; // [rsp+50h] [rbp-59h] BYREF
  int v38; // [rsp+60h] [rbp-49h]
  unsigned int v39; // [rsp+64h] [rbp-45h]
  int v40; // [rsp+68h] [rbp-41h]
  int v41; // [rsp+6Ch] [rbp-3Dh]
  __int64 v42; // [rsp+70h] [rbp-39h]
  const char *v43; // [rsp+78h] [rbp-31h]
  _QWORD v44[6]; // [rsp+80h] [rbp-29h] BYREF

  v4 = *(_DWORD *)(a1 + 44);
  v5 = a2;
  v44[0] = "table";
  v40 = a4;
  v42 = 0;
  v8 = "sqlite_temp_master";
  v44[5] = 0;
  v9 = v4 | 0xFFFFFFBF;
  v39 = 0;
  *(_BYTE *)(a1 + 197) = 1;
  v41 = 0;
  if ( a2 != 1 )
    v8 = "sqlite_master";
  v37[0] = a1;
  v43 = v8;
  v44[1] = v8;
  v44[2] = v8;
  v38 = a2;
  v44[3] = "1";
  v44[4] = "CREATE TABLE x(type text,name text,tbl_name text,rootpage int,sql text)";
  v37[1] = a3;
  sqlite3InitCallback(v37, 5, v44);
  *(_DWORD *)(a1 + 44) &= v9;
  v10 = v39;
  if ( !v39 )
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
    v34 = 0;
    sqlite3BtreeEnter(v14);
    if ( (unsigned int)sqlite3BtreeTxnState(*(_QWORD *)(v13 + 8)) )
    {
      v10 = 1;
    }
    else
    {
      v16 = sqlite3BtreeBeginTrans(v15, 0, 0);
      v10 = v16;
      if ( v16 )
      {
        v17 = sqlite3ErrStr(v16);
        sqlite3SetString(a3, a1, v17);
        goto LABEL_52;
      }
      v10 = 1;
      v34 = 1;
    }
    v18 = 0;
    do
    {
      v19 = v18 + 1;
      sqlite3BtreeGetMeta(*(_QWORD *)(v13 + 8), (unsigned int)(v18 + 1), (char *)&v35 + 4 * v18);
      v18 = (unsigned int)v19;
    }
    while ( v19 < 5 );
    if ( (*(_DWORD *)(a1 + 48) & 0x2000000) != 0 )
    {
      v20 = 0;
      v35 = 0;
    }
    else
    {
      v20 = v36;
    }
    **(_DWORD **)(v13 + 24) = v35;
    if ( v20 )
    {
      if ( (_DWORD)v5 || (*(_BYTE *)(a1 + 44) & 0x40) != 0 )
      {
        if ( (v20 & 3) != *(_BYTE *)(a1 + 100) )
        {
          v25 = "attached databases must use the same text encoding as main database";
LABEL_36:
          sqlite3SetString(a3, a1, v25);
LABEL_50:
          if ( v34 )
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
        v21 = v20 & 3;
        if ( !v21 )
          v21 = 1;
        if ( *(int *)(a1 + 216) > 0 && v21 != *(_BYTE *)(a1 + 100) && (*(_BYTE *)(a1 + 44) & 4) == 0 )
        {
          v10 = 6;
          goto LABEL_50;
        }
        sqlite3SetTextEncoding(a1);
      }
    }
    *(_BYTE *)(*(_QWORD *)(v13 + 24) + 113LL) = *(_BYTE *)(a1 + 100);
    if ( !*(_DWORD *)(*(_QWORD *)(v13 + 24) + 116LL) )
    {
      v22 = sqlite3AbsInt32(DWORD2(v35));
      if ( !v22 )
        v22 = -2000;
      *(_DWORD *)(v23 + 116) = v22;
      sqlite3BtreeSetCacheSize(*(_QWORD *)(v13 + 8), *(unsigned int *)(*(_QWORD *)(v13 + 24) + 116LL));
    }
    *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) = BYTE4(v35);
    v24 = *(_QWORD *)(v13 + 24);
    if ( !*(_BYTE *)(v24 + 112) )
      *(_BYTE *)(v24 + 112) = 1;
    if ( *(_BYTE *)(*(_QWORD *)(v13 + 24) + 112LL) <= 4u )
    {
      if ( !(_DWORD)v5 && SDWORD1(v35) >= 4 )
        *(_QWORD *)(a1 + 48) &= ~2uLL;
      v26 = *(_QWORD *)(a1 + 32);
      LODWORD(v42) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 8) + 8LL) + 64LL);
      v27 = sqlite3MPrintf(a1, "SELECT*FROM\"%w\".%s ORDER BY rowid", *(_QWORD *)(v26 + 32 * v5), v43);
      v28 = *(_QWORD *)(a1 + 512);
      *(_QWORD *)(a1 + 512) = 0;
      v29 = v27;
      v30 = sqlite3_exec(a1, v27, (unsigned int)sqlite3InitCallback, (unsigned int)v37, 0);
      *(_QWORD *)(a1 + 512) = v28;
      v10 = v30;
      if ( !v30 )
        v10 = v39;
      sqlite3DbFree(a1, v29);
      if ( !v10 )
        sqlite3AnalysisLoad(a1, (unsigned int)v5, v31);
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
      goto LABEL_50;
    }
    v25 = "unsupported file format";
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
0x18003549c  push    rbp
0x18003549e  push    rbx
0x18003549f  push    rsi
0x1800354a0  push    rdi
0x1800354a1  push    r12
0x1800354a3  push    r13
0x1800354a5  push    r14
0x1800354a7  push    r15
0x1800354a9  lea     rbp, [rsp-1Fh]
0x1800354ae  sub     rsp, 0C8h
0x1800354b5  mov     rax, cs:__security_cookie
0x1800354bc  xor     rax, rsp
0x1800354bf  mov     [rbp+57h+var_50], rax
0x1800354c3  mov     ebx, [rcx+2Ch]
0x1800354c6  lea     rax, aTable; "table"
0x1800354cd  movsxd  r13, edx
0x1800354d0  mov     rdi, r8
0x1800354d3  xor     edx, edx
0x1800354d5  mov     [rbp+57h+var_80], rax
0x1800354d9  mov     rsi, rcx
0x1800354dc  mov     [rbp+57h+var_98], r9d
0x1800354e0  mov     [rbp+57h+var_90], rdx
0x1800354e4  lea     rax, aSqliteTempMast; "sqlite_temp_master"
0x1800354eb  mov     [rbp+57h+var_58], rdx
0x1800354ef  or      ebx, 0FFFFFFBFh
0x1800354f2  lea     r8d, [rdx+1]
0x1800354f6  mov     [rbp+57h+var_9C], edx
0x1800354f9  mov     [rcx+0C5h], r8b
0x180035500  cmp     r13d, r8d
0x180035503  lea     rcx, aSqliteMaster; "sqlite_master"
0x18003550a  mov     [rbp+57h+var_94], edx
0x18003550d  cmovnz  rax, rcx
0x180035511  mov     [rbp+57h+var_B0], rsi
0x180035515  mov     [rbp+57h+var_88], rax
0x180035519  lea     r8, [rbp+57h+var_80]
0x18003551d  mov     [rbp+57h+var_78], rax
0x180035521  lea     rcx, [rbp+57h+var_B0]
0x180035525  mov     [rbp+57h+var_70], rax
0x180035529  xor     r9d, r9d
0x18003552c  lea     rax, a1; "1"
0x180035533  mov     [rbp+57h+var_A0], r13d
0x180035537  mov     [rbp+57h+var_68], rax
0x18003553b  lea     rax, aCreateTableXTy; "CREATE TABLE x(type text,name text,tbl_"...
0x180035542  mov     [rbp+57h+var_60], rax
0x180035546  lea     edx, [r9+5]
0x18003554a  mov     [rbp+57h+var_A8], rdi
0x18003554e  call    sqlite3InitCallback
0x180035553  and     [rsi+2Ch], ebx
0x180035556  xor     ebx, ebx
0x180035558  mov     r14d, [rbp+57h+var_9C]
0x18003555c  test    r14d, r14d
0x18003555f  jnz     loc_1800357E4
0x180035565  mov     rax, [rsi+20h]
0x180035569  mov     r12, r13
0x18003556c  shl     r12, 5
0x180035570  lea     r15, [r12+rax]
0x180035574  mov     rcx, [r15+8]
0x180035578  test    rcx, rcx
0x18003557b  jnz     short loc_180035590
0x18003557d  mov     rax, [rax+38h]
0x180035581  lea     ecx, [rbx+1]
0x180035584  mov     r14d, ebx
0x180035587  or      [rax+72h], cx
0x18003558b  jmp     loc_180035806
0x180035590  mov     [rbp+57h+var_D0], ebx
0x180035593  call    sqlite3BtreeEnter
0x180035598  mov     rcx, [r15+8]
0x18003559c  call    sqlite3BtreeTxnState
0x1800355a1  test    eax, eax
0x1800355a3  jnz     short loc_1800355DC
0x1800355a5  xor     r8d, r8d
0x1800355a8  xor     edx, edx
0x1800355aa  call    sqlite3BtreeBeginTrans
0x1800355af  mov     r14d, eax
0x1800355b2  test    eax, eax
0x1800355b4  jz      short loc_1800355D0
0x1800355b6  mov     ecx, eax
0x1800355b8  call    sqlite3ErrStr
0x1800355bd  mov     r8, rax
0x1800355c0  mov     rdx, rsi
0x1800355c3  mov     rcx, rdi
0x1800355c6  call    sqlite3SetString
0x1800355cb  jmp     loc_1800357D6
0x1800355d0  mov     r14d, 1
0x1800355d6  mov     [rbp+57h+var_D0], r14d
0x1800355da  jmp     short loc_1800355E2
0x1800355dc  mov     r14d, 1
0x1800355e2  mov     eax, ebx
0x1800355e4  mov     rcx, [r15+8]
0x1800355e8  lea     ebx, [rax+1]
0x1800355eb  lea     r8, [rbp+57h+var_C8]
0x1800355ef  mov     edx, ebx
0x1800355f1  lea     r8, [r8+rax*4]
0x1800355f5  call    sqlite3BtreeGetMeta
0x1800355fa  mov     eax, ebx
0x1800355fc  cmp     ebx, 5
0x1800355ff  jl      short loc_1800355E4
0x180035601  mov     eax, [rsi+30h]
0x180035604  bt      rax, 19h
0x180035609  jnb     short loc_180035616
0x18003560b  xorps   xmm0, xmm0
0x18003560e  xor     edx, edx
0x180035610  movups  [rbp+57h+var_C8], xmm0
0x180035614  jmp     short loc_180035619
0x180035616  mov     edx, [rbp+57h+var_B8]
0x180035619  mov     rcx, [r15+18h]
0x18003561d  xor     ebx, ebx
0x18003561f  mov     eax, dword ptr [rbp+57h+var_C8]
0x180035622  mov     [rcx], eax
0x180035624  test    edx, edx
0x180035626  jz      short loc_18003566A
0x180035628  test    r13d, r13d
0x18003562b  jnz     loc_1800356CE
0x180035631  test    byte ptr [rsi+2Ch], 40h
0x180035635  jnz     loc_1800356CE
0x18003563b  mov     al, dl
0x18003563d  and     al, 3
0x18003563f  movzx   edx, al
0x180035642  cmovz   edx, r14d
0x180035646  cmp     [rsi+0D8h], ebx
0x18003564c  jle     short loc_180035662
0x18003564e  cmp     dl, [rsi+64h]
0x180035651  jz      short loc_180035662
0x180035653  test    byte ptr [rsi+2Ch], 4
0x180035657  jnz     short loc_180035662
0x180035659  lea     r14d, [rbx+6]
0x18003565d  jmp     loc_1800357C8
0x180035662  mov     rcx, rsi
0x180035665  call    sqlite3SetTextEncoding
0x18003566a  mov     rcx, [r15+18h]
0x18003566e  mov     al, [rsi+64h]
0x180035671  mov     [rcx+71h], al
0x180035674  mov     r8, [r15+18h]
0x180035678  cmp     [r8+74h], ebx
0x18003567c  jnz     short loc_1800356A4
0x18003567e  mov     ecx, dword ptr [rbp+57h+var_C8+8]
0x180035681  call    sqlite3AbsInt32
0x180035686  test    eax, eax
0x180035688  mov     ecx, 0FFFFF830h
0x18003568d  cmovz   eax, ecx
0x180035690  mov     [r8+74h], eax
0x180035694  mov     rdx, [r15+18h]
0x180035698  mov     rcx, [r15+8]
0x18003569c  mov     edx, [rdx+74h]
0x18003569f  call    sqlite3BtreeSetCacheSize
0x1800356a4  mov     al, byte ptr [rbp+57h+var_C8+4]
0x1800356a7  mov     rcx, [r15+18h]
0x1800356ab  mov     [rcx+70h], al
0x1800356ae  mov     rax, [r15+18h]
0x1800356b2  cmp     [rax+70h], bl
0x1800356b5  jnz     short loc_1800356BB
0x1800356b7  mov     [rax+70h], r14b
0x1800356bb  mov     rax, [r15+18h]
0x1800356bf  cmp     byte ptr [rax+70h], 4
0x1800356c3  jbe     short loc_1800356ED
0x1800356c5  lea     r8, aUnsupportedFil; "unsupported file format"
0x1800356cc  jmp     short loc_1800356DD
0x1800356ce  and     edx, 3
0x1800356d1  cmp     dl, [rsi+64h]
0x1800356d4  jz      short loc_18003566A
0x1800356d6  lea     r8, aAttachedDataba; "attached databases must use the same te"...
0x1800356dd  mov     rdx, rsi
0x1800356e0  mov     rcx, rdi
0x1800356e3  call    sqlite3SetString
0x1800356e8  jmp     loc_1800357C8
0x1800356ed  test    r13d, r13d
0x1800356f0  jnz     short loc_1800356FD
0x1800356f2  cmp     dword ptr [rbp+57h+var_C8+4], 4
0x1800356f6  jl      short loc_1800356FD
0x1800356f8  and     qword ptr [rsi+30h], 0FFFFFFFFFFFFFFFDh
0x1800356fd  mov     rax, [r15+8]
0x180035701  lea     rdx, aSelectFromWSOr; "SELECT*FROM\"%w\".%s ORDER BY rowid"
0x180035708  mov     r8, [rsi+20h]
0x18003570c  mov     r9, [rbp+57h+var_88]
0x180035710  mov     rcx, [rax+8]
0x180035714  mov     eax, [rcx+40h]
0x180035717  mov     rcx, rsi
0x18003571a  mov     dword ptr [rbp+57h+var_90], eax
0x18003571d  mov     r8, [r8+r12]
0x180035721  call    sqlite3MPrintf
0x180035726  mov     rbx, [rsi+200h]
0x18003572d  lea     r9, [rbp+57h+var_B0]
0x180035731  xor     edx, edx
0x180035733  lea     r8, sqlite3InitCallback
0x18003573a  mov     [rsi+200h], rdx
0x180035741  mov     rcx, rsi
0x180035744  mov     [rsp+100h+var_E0], rdx
0x180035749  mov     rdi, rax
0x18003574c  mov     rdx, rax
0x18003574f  call    sqlite3_exec
0x180035754  mov     [rsi+200h], rbx
0x18003575b  mov     r14d, eax
0x18003575e  xor     ebx, ebx
0x180035760  mov     rdx, rdi
0x180035763  test    eax, eax
0x180035765  mov     rcx, rsi
0x180035768  cmovz   r14d, [rbp+57h+var_9C]
0x18003576d  call    sqlite3DbFree
0x180035772  test    r14d, r14d
0x180035775  jnz     short loc_180035782
0x180035777  mov     edx, r13d
0x18003577a  mov     rcx, rsi
0x18003577d  call    sqlite3AnalysisLoad
0x180035782  cmp     [rsi+67h], bl
0x180035785  jz      short loc_18003579E
0x180035787  mov     rcx, rsi
0x18003578a  mov     r14d, 7
0x180035790  call    sqlite3ResetAllSchemasOfConnection
0x180035795  mov     r15, [rsi+20h]
0x180035799  add     r15, r12
0x18003579c  jmp     short loc_1800357C8
0x18003579e  test    r14d, r14d
0x1800357a1  jz      short loc_1800357B3
0x1800357a3  mov     eax, [rsi+30h]
0x1800357a6  bt      rax, 1Bh
0x1800357ab  jnb     short loc_1800357C8
0x1800357ad  cmp     r14d, 7
0x1800357b1  jz      short loc_1800357C8
0x1800357b3  mov     rax, [rsi+20h]
0x1800357b7  mov     ecx, 1
0x1800357bc  mov     r14d, ebx
0x1800357bf  mov     rdx, [rax+r12+18h]
0x1800357c4  or      [rdx+72h], cx
0x1800357c8  cmp     [rbp+57h+var_D0], ebx
0x1800357cb  jz      short loc_1800357D6
0x1800357cd  mov     rcx, [r15+8]
0x1800357d1  call    sqlite3BtreeCommit
0x1800357d6  mov     rcx, [r15+8]
0x1800357da  call    sqlite3BtreeLeave
0x1800357df  test    r14d, r14d
0x1800357e2  jz      short loc_180035806
0x1800357e4  cmp     r14d, 7
0x1800357e8  jz      short loc_1800357F3
0x1800357ea  cmp     r14d, 0C0Ah
0x1800357f1  jnz     short loc_1800357FB
0x1800357f3  mov     rcx, rsi
0x1800357f6  call    sqlite3OomFault
0x1800357fb  mov     edx, r13d
0x1800357fe  mov     rcx, rsi
0x180035801  call    sqlite3ResetOneSchema
0x180035806  mov     [rsi+0C5h], bl
0x18003580c  mov     eax, r14d
0x18003580f  mov     rcx, [rbp+57h+var_50]
0x180035813  xor     rcx, rsp; StackCookie
0x180035816  call    __security_check_cookie
0x18003581b  add     rsp, 0C8h
0x180035822  pop     r15
0x180035824  pop     r14
0x180035826  pop     r13
0x180035828  pop     r12
0x18003582a  pop     rdi
0x18003582b  pop     rsi
0x18003582c  pop     rbx
0x18003582d  pop     rbp
0x18003582e  retn
```
