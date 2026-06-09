# sqlite3BeginTrigger

- ea: `0x1800846c4`
- end: `0x180084c0e`
- name: `sqlite3BeginTrigger`
- size: `1354`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path`

## callers

- `0x1800dea88`

## callees

- `0x180003fb8`
- `0x1800602d8`
- `0x180061f04`
- `0x180084260`
- `0x1800846c4`
- `0x180088a4c`
- `0x180089bdc`
- `0x18008c5ac`
- `0x18008c75c`
- `0x18008c8e8`
- `0x18008d6cc`
- `0x18008e99c`
- `0x180091c1c`
- `0x1800943c4`
- `0x180094448`
- `0x18009876c`
- `0x18009c604`
- `0x1800a4150`
- `0x1800a8fd4`
- `0x1800a9438`
- `0x1800aa940`
- `0x1800c88e0`

## string_xrefs

- `0x180084a76`: `sqlite_temp_master`
- `0x180084728`: `temporary trigger may not have qualified name`
- `0x18008488e`: `cannot create triggers on shadow tables`
- `0x180084849`: `cannot create triggers on virtual tables`
- `0x180084966`: `cannot create trigger on system table`
- `0x18008490e`: `trigger %T already exists`
- `0x1800849c9`: `cannot create INSTEAD OF trigger on table: %S`
- `0x1800849a7`: `cannot create %s trigger on view: %S`

## pseudocode

```c
__int64 __fastcall sqlite3BeginTrigger(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        int a9,
        int a10)
{
  __int64 v10; // rbx
  __int64 *v11; // r14
  __int64 v15; // rsi
  __int64 v16; // rbp
  unsigned int v17; // r14d
  __int64 v18; // rax
  __int64 v19; // r15
  __int64 v20; // rax
  __int64 v21; // rax
  const char *v22; // r8
  __int64 v23; // rcx
  int v24; // r12d
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // rax
  int v28; // edx
  const char *v29; // r8
  int v30; // eax
  __int64 *v31; // rax
  __int64 *v32; // r12
  __int64 v33; // rax
  __int64 v34; // r8
  __int64 v35; // rcx
  __int64 *i; // rax
  __int64 result; // rax
  __int64 v38; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+38h] [rbp-A0h]
  _BYTE v40[152]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v42; // [rsp+118h] [rbp+40h]
  int v43; // [rsp+120h] [rbp+48h]

  v10 = *a1;
  v11 = 0;
  v38 = 0;
  memset_0(v40, 0, 0x60u);
  if ( a9 )
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      sqlite3ErrorMsg(a1, "temporary trigger may not have qualified name");
      v15 = a8;
      v16 = a6;
      goto LABEL_81;
    }
    v17 = 1;
  }
  else
  {
    v17 = sqlite3TwoPartName(a1, a2, a3, &v38);
    if ( (v17 & 0x80000000) != 0 )
    {
LABEL_79:
      v15 = a8;
      v16 = a6;
      goto LABEL_80;
    }
    a2 = v38;
  }
  if ( !a7 || *(_BYTE *)(v10 + 103) )
    goto LABEL_79;
  if ( *(_BYTE *)(v10 + 197) && v17 != 1 )
  {
    if ( *(_QWORD *)(a7 + 16) )
      sqlite3DbFreeNN(v10);
    *(_QWORD *)(a7 + 16) = 0;
  }
  v18 = sqlite3SrcListLookup(a1, a7);
  if ( !*(_BYTE *)(v10 + 197)
    && !*(_DWORD *)(a3 + 8)
    && v18
    && *(_QWORD *)(v18 + 96) == *(_QWORD *)(*(_QWORD *)(v10 + 32) + 56LL) )
  {
    v17 = 1;
  }
  if ( *(_BYTE *)(v10 + 103) )
    goto LABEL_79;
  sqlite3FixInit((unsigned int)v40, (_DWORD)a1, v17, (unsigned int)"trigger", a2);
  if ( (unsigned int)sqlite3FixSrcList(v40, a7) )
    goto LABEL_79;
  v16 = a6;
  v15 = a8;
  v19 = 0;
  v20 = sqlite3SrcListLookup(a1, a7);
  v42 = v20;
  if ( !v20 )
    goto LABEL_24;
  if ( *(_BYTE *)(v20 + 63) == 1 )
  {
    sqlite3ErrorMsg(a1, "cannot create triggers on virtual tables");
    goto LABEL_24;
  }
  if ( (*(_DWORD *)(v20 + 48) & 0x1000) != 0 && (unsigned int)sqlite3ReadOnlyShadowTables(v10) )
  {
    sqlite3ErrorMsg(a1, "cannot create triggers on shadow tables");
    goto LABEL_24;
  }
  v21 = sqlite3NameFromToken(v10, a2);
  v19 = v21;
  if ( !v21 )
  {
LABEL_80:
    v11 = 0;
    goto LABEL_81;
  }
  if ( (unsigned int)sqlite3CheckObjectName(a1, v21, "trigger", *(_QWORD *)v42) )
    goto LABEL_37;
  if ( *((_BYTE *)a1 + 308) < 2u
    && *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v17 + *(_QWORD *)(v10 + 32) + 24) + 56LL, v19, 0) + 16) )
  {
    if ( a10 )
      sqlite3CodeVerifySchema(a1, v17);
    else
      sqlite3ErrorMsg(a1, "trigger %T already exists", a2);
    goto LABEL_37;
  }
  v38 = *(_QWORD *)v42;
  if ( !(unsigned int)sqlite3_strnicmp(v38, "sqlite_", 7) )
  {
    sqlite3ErrorMsg(a1, "cannot create trigger on system table");
    goto LABEL_37;
  }
  if ( *(_BYTE *)(v42 + 63) != 2 )
  {
    if ( a4 == 65 )
    {
      sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
      goto LABEL_24;
    }
    goto LABEL_49;
  }
  if ( a4 == 65 )
  {
LABEL_49:
    if ( *((_BYTE *)a1 + 308) >= 2u )
      goto LABEL_63;
    v23 = *(_QWORD *)(v42 + 96);
    v24 = -32768;
    if ( v23 )
    {
      v25 = *(_QWORD *)(v10 + 32);
      v24 = 0;
      if ( *(_QWORD *)(v25 + 24) != v23 )
      {
        do
          ++v24;
        while ( *(_QWORD *)(32LL * v24 + v25 + 24) != v23 );
      }
    }
    v26 = *(_QWORD *)(v10 + 32);
    v27 = *(_QWORD *)(32LL * v24 + v26);
    v39 = v27;
    if ( a9 )
      v27 = *(_QWORD *)(v26 + 32);
    v28 = v24 == 1 || a9 ? 5 : 7;
    if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v28, v19, v38, v27) )
    {
      v29 = "sqlite_temp_master";
      if ( v24 != 1 )
        v29 = "sqlite_master";
      if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v29, 0, v39) )
      {
LABEL_63:
        v30 = 33;
        if ( a4 != 65 )
          v30 = a4;
        v43 = v30;
        v31 = (__int64 *)sqlite3DbMallocZero(v10, 72);
        v32 = v31;
        if ( v31 )
        {
          *v31 = v19;
          v33 = sqlite3DbStrDup(v10, *(_QWORD *)(a7 + 24));
          v32[1] = v33;
          v34 = v33;
          v32[5] = *(_QWORD *)(32LL * v17 + *(_QWORD *)(v10 + 32) + 24);
          v32[6] = *(_QWORD *)(v42 + 96);
          *((_BYTE *)v32 + 16) = a5;
          *((_BYTE *)v32 + 17) = (v43 != 33) + 1;
          if ( *((_BYTE *)a1 + 308) < 2u )
          {
            if ( v15 )
              v35 = exprDup(v10, v15, 1);
            else
              v35 = 0;
          }
          else
          {
            v35 = v15;
            for ( i = (__int64 *)a1[52]; i; i = (__int64 *)i[3] )
            {
              if ( *i == *(_QWORD *)(a7 + 24) )
              {
                *i = v34;
                break;
              }
            }
            v15 = 0;
          }
          v32[3] = v35;
          v11 = v32;
          v32[4] = a6;
          v16 = 0;
          a1[46] = (__int64)v32;
          goto LABEL_81;
        }
        v11 = 0;
LABEL_38:
        sqlite3DbFreeNN(v10);
        goto LABEL_81;
      }
    }
LABEL_37:
    v11 = 0;
    goto LABEL_38;
  }
  v22 = "BEFORE";
  if ( a4 != 33 )
    v22 = "AFTER";
  sqlite3ErrorMsg(a1, "cannot create %s trigger on view: %S", v22, (const wchar_t *)(a7 + 8));
LABEL_24:
  if ( *(_BYTE *)(v10 + 196) == 1 )
    *(_DWORD *)(v10 + 200) |= 1u;
  v11 = 0;
  if ( v19 )
    goto LABEL_38;
LABEL_81:
  sqlite3SrcListDelete(v10, a7);
  result = sqlite3IdListDelete(v10, v16);
  if ( v15 )
    result = sqlite3ExprDeleteNN(v10, v15);
  if ( !a1[46] )
    return sqlite3DeleteTrigger(v10, v11);
  return result;
}

```

## disassembly

```asm
0x1800846c4  mov     [rsp+arg_8], rbx
0x1800846c9  mov     [rsp+arg_18], r9d
0x1800846ce  push    rbp
0x1800846cf  push    rsi
0x1800846d0  push    rdi
0x1800846d1  push    r12
0x1800846d3  push    r13
0x1800846d5  push    r14
0x1800846d7  push    r15
0x1800846d9  sub     rsp, 0A0h
0x1800846e0  mov     rbx, [rcx]
0x1800846e3  xor     r14d, r14d
0x1800846e6  mov     rsi, r8
0x1800846e9  mov     [rsp+0D8h+arg_0], r14
0x1800846f1  mov     r12, rdx
0x1800846f4  mov     [rsp+0D8h+var_A8], r14
0x1800846f9  mov     rdi, rcx
0x1800846fc  xor     edx, edx; Val
0x1800846fe  lea     r8d, [r14+60h]; Size
0x180084702  lea     rcx, [rsp+0D8h+var_98]; void *
0x180084707  call    memset_0
0x18008470c  lea     ebp, [r14+1]
0x180084710  mov     r13, [rsp+0D8h+arg_30]
0x180084718  cmp     [rsp+0D8h+arg_40], r14d
0x180084720  jz      short loc_180084751
0x180084722  cmp     [rsi+8], r14d
0x180084726  jbe     short loc_18008474C
0x180084728  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x18008472f  mov     rcx, rdi
0x180084732  call    sqlite3ErrorMsg
0x180084737  mov     rsi, [rsp+0D8h+arg_38]
0x18008473f  mov     rbp, [rsp+0D8h+arg_28]
0x180084747  jmp     loc_180084BB8
0x18008474c  mov     r14d, ebp
0x18008474f  jmp     short loc_180084774
0x180084751  lea     r9, [rsp+0D8h+var_A8]
0x180084756  mov     r8, rsi
0x180084759  mov     rdx, r12
0x18008475c  mov     rcx, rdi
0x18008475f  call    sqlite3TwoPartName
0x180084764  mov     r14d, eax
0x180084767  test    eax, eax
0x180084769  js      loc_180084BA0
0x18008476f  mov     r12, [rsp+0D8h+var_A8]
0x180084774  test    r13, r13
0x180084777  jz      loc_180084BA0
0x18008477d  cmp     byte ptr [rbx+67h], 0
0x180084781  jnz     loc_180084BA0
0x180084787  cmp     byte ptr [rbx+0C5h], 0
0x18008478e  jz      short loc_1800847AE
0x180084790  cmp     r14d, ebp
0x180084793  jz      short loc_1800847AE
0x180084795  mov     rdx, [r13+10h]
0x180084799  test    rdx, rdx
0x18008479c  jz      short loc_1800847A6
0x18008479e  mov     rcx, rbx
0x1800847a1  call    sqlite3DbFreeNN
0x1800847a6  mov     qword ptr [r13+10h], 0
0x1800847ae  mov     rdx, r13
0x1800847b1  mov     rcx, rdi
0x1800847b4  call    sqlite3SrcListLookup
0x1800847b9  cmp     byte ptr [rbx+0C5h], 0
0x1800847c0  jnz     short loc_1800847DD
0x1800847c2  cmp     dword ptr [rsi+8], 0
0x1800847c6  jnz     short loc_1800847DD
0x1800847c8  test    rax, rax
0x1800847cb  jz      short loc_1800847DD
0x1800847cd  mov     rcx, [rbx+20h]
0x1800847d1  mov     rcx, [rcx+38h]
0x1800847d5  cmp     [rax+60h], rcx
0x1800847d9  cmovz   r14d, ebp
0x1800847dd  cmp     byte ptr [rbx+67h], 0
0x1800847e1  jnz     loc_180084BA0
0x1800847e7  lea     r9, aTrigger; "trigger"
0x1800847ee  mov     [rsp+0D8h+var_B8], r12
0x1800847f3  mov     r8d, r14d
0x1800847f6  lea     rcx, [rsp+0D8h+var_98]
0x1800847fb  mov     rdx, rdi
0x1800847fe  call    sqlite3FixInit
0x180084803  mov     rdx, r13
0x180084806  lea     rcx, [rsp+0D8h+var_98]
0x18008480b  call    sqlite3FixSrcList
0x180084810  test    eax, eax
0x180084812  jnz     loc_180084BA0
0x180084818  mov     rbp, [rsp+0D8h+arg_28]
0x180084820  mov     rdx, r13
0x180084823  mov     rsi, [rsp+0D8h+arg_38]
0x18008482b  mov     rcx, rdi
0x18008482e  xor     r15d, r15d
0x180084831  call    sqlite3SrcListLookup
0x180084836  mov     [rsp+0D8h+arg_38], rax
0x18008483e  test    rax, rax
0x180084841  jz      short loc_180084858
0x180084843  cmp     byte ptr [rax+3Fh], 1
0x180084847  jnz     short loc_180084879
0x180084849  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x180084850  mov     rcx, rdi
0x180084853  call    sqlite3ErrorMsg
0x180084858  cmp     byte ptr [rbx+0C4h], 1
0x18008485f  jnz     short loc_180084868
0x180084861  or      dword ptr [rbx+0C8h], 1
0x180084868  xor     r14d, r14d
0x18008486b  test    r15, r15
0x18008486e  jz      loc_180084BB8
0x180084874  jmp     loc_180084922
0x180084879  test    dword ptr [rax+30h], 1000h
0x180084880  jz      short loc_180084897
0x180084882  mov     rcx, rbx
0x180084885  call    sqlite3ReadOnlyShadowTables
0x18008488a  test    eax, eax
0x18008488c  jz      short loc_180084897
0x18008488e  lea     rdx, aCannotCreateTr_1; "cannot create triggers on shadow tables"
0x180084895  jmp     short loc_180084850
0x180084897  mov     rdx, r12
0x18008489a  mov     rcx, rbx
0x18008489d  call    sqlite3NameFromToken
0x1800848a2  mov     r15, rax
0x1800848a5  test    rax, rax
0x1800848a8  jz      loc_180084BB0
0x1800848ae  mov     rcx, [rsp+0D8h+arg_38]
0x1800848b6  lea     r8, aTrigger; "trigger"
0x1800848bd  mov     rdx, rax
0x1800848c0  mov     r9, [rcx]
0x1800848c3  mov     rcx, rdi
0x1800848c6  call    sqlite3CheckObjectName
0x1800848cb  test    eax, eax
0x1800848cd  jnz     short loc_18008491A
0x1800848cf  cmp     byte ptr [rdi+134h], 2
0x1800848d6  jnb     short loc_18008493C
0x1800848d8  mov     rax, [rbx+20h]
0x1800848dc  xor     r8d, r8d
0x1800848df  mov     ecx, r14d
0x1800848e2  mov     rdx, r15
0x1800848e5  shl     rcx, 5
0x1800848e9  mov     rcx, [rcx+rax+18h]
0x1800848ee  add     rcx, 38h ; '8'
0x1800848f2  call    findElementWithHash
0x1800848f7  cmp     qword ptr [rax+10h], 0
0x1800848fc  jz      short loc_18008493C
0x1800848fe  cmp     [rsp+0D8h+arg_48], 0
0x180084906  mov     rcx, rdi
0x180084909  jnz     short loc_180084932
0x18008490b  mov     r8, r12
0x18008490e  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x180084915  call    sqlite3ErrorMsg
0x18008491a  mov     r14, [rsp+0D8h+arg_0]
0x180084922  mov     rdx, r15
0x180084925  mov     rcx, rbx
0x180084928  call    sqlite3DbFreeNN
0x18008492d  jmp     loc_180084BB8
0x180084932  mov     edx, r14d
0x180084935  call    sqlite3CodeVerifySchema
0x18008493a  jmp     short loc_18008491A
0x18008493c  mov     r12, [rsp+0D8h+arg_38]
0x180084944  lea     rdx, aSqlite_0; "sqlite_"
0x18008494b  mov     r8d, 7
0x180084951  mov     rax, [r12]
0x180084955  mov     rcx, rax
0x180084958  mov     [rsp+0D8h+var_A8], rax
0x18008495d  call    sqlite3_strnicmp
0x180084962  test    eax, eax
0x180084964  jnz     short loc_180084977
0x180084966  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x18008496d  mov     rcx, rdi
0x180084970  call    sqlite3ErrorMsg
0x180084975  jmp     short loc_18008491A
0x180084977  cmp     byte ptr [r12+3Fh], 2
0x18008497d  jnz     short loc_1800849B8
0x18008497f  mov     eax, [rsp+0D8h+arg_18]
0x180084986  cmp     eax, 41h ; 'A'
0x180084989  jz      short loc_1800849DA
0x18008498b  cmp     eax, 21h ; '!'
0x18008498e  lea     rcx, aAfter; "AFTER"
0x180084995  lea     r8, aBefore; "BEFORE"
0x18008499c  cmovnz  r8, rcx
0x1800849a0  lea     r9, [r13+8]
0x1800849a4  mov     rcx, rdi
0x1800849a7  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x1800849ae  call    sqlite3ErrorMsg
0x1800849b3  jmp     loc_180084858
0x1800849b8  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x1800849c0  jnz     short loc_1800849DA
0x1800849c2  lea     r8, [r13+8]
0x1800849c6  mov     rcx, rdi
0x1800849c9  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x1800849d0  call    sqlite3ErrorMsg
0x1800849d5  jmp     loc_180084858
0x1800849da  cmp     byte ptr [rdi+134h], 2
0x1800849e1  jnb     loc_180084AA2
0x1800849e7  mov     rcx, [r12+60h]
0x1800849ec  mov     r12d, 0FFFF8000h
0x1800849f2  test    rcx, rcx
0x1800849f5  jz      short loc_180084A15
0x1800849f7  mov     rdx, [rbx+20h]
0x1800849fb  xor     r12d, r12d
0x1800849fe  cmp     [rdx+18h], rcx
0x180084a02  jz      short loc_180084A15
0x180084a04  inc     r12d
0x180084a07  movsxd  rax, r12d
0x180084a0a  shl     rax, 5
0x180084a0e  cmp     [rax+rdx+18h], rcx
0x180084a13  jnz     short loc_180084A04
0x180084a15  mov     rcx, [rbx+20h]
0x180084a19  mov     edx, [rsp+0D8h+arg_40]
0x180084a20  movsxd  rax, r12d
0x180084a23  shl     rax, 5
0x180084a27  mov     rax, [rax+rcx]
0x180084a2b  mov     [rsp+0D8h+var_A0], rax
0x180084a30  test    edx, edx
0x180084a32  jz      short loc_180084A38
0x180084a34  mov     rax, [rcx+20h]
0x180084a38  cmp     r12d, 1
0x180084a3c  jz      short loc_180084A42
0x180084a3e  test    edx, edx
0x180084a40  jz      short loc_180084A49
0x180084a42  mov     edx, 5
0x180084a47  jmp     short loc_180084A4E
0x180084a49  mov     edx, 7
0x180084a4e  mov     r9, [rsp+0D8h+var_A8]
0x180084a53  mov     r8, r15
0x180084a56  mov     rcx, rdi
0x180084a59  mov     [rsp+0D8h+var_B8], rax
0x180084a5e  call    sqlite3AuthCheck
0x180084a63  test    eax, eax
0x180084a65  jnz     loc_18008491A
0x180084a6b  lea     rax, aSqliteMaster; "sqlite_master"
0x180084a72  cmp     r12d, 1
0x180084a76  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180084a7d  mov     rcx, rdi
0x180084a80  cmovnz  r8, rax
0x180084a84  mov     rax, [rsp+0D8h+var_A0]
0x180084a89  xor     r9d, r9d
0x180084a8c  mov     [rsp+0D8h+var_B8], rax
0x180084a91  lea     edx, [r9+12h]
0x180084a95  call    sqlite3AuthCheck
0x180084a9a  test    eax, eax
0x180084a9c  jnz     loc_18008491A
0x180084aa2  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180084aaa  mov     eax, 21h ; '!'
0x180084aaf  mov     edx, 48h ; 'H'
0x180084ab4  mov     rcx, rbx
0x180084ab7  cmovnz  eax, [rsp+0D8h+arg_18]
0x180084abf  mov     [rsp+0D8h+arg_40], eax
0x180084ac6  call    sqlite3DbMallocZero
0x180084acb  mov     r12, rax
0x180084ace  test    rax, rax
0x180084ad1  jz      loc_180084B98
0x180084ad7  mov     [rax], r15
0x180084ada  mov     rcx, rbx
0x180084add  mov     rdx, [r13+18h]
0x180084ae1  call    sqlite3DbStrDup
0x180084ae6  mov     [r12+8], rax
0x180084aeb  mov     r8, rax
0x180084aee  mov     rcx, [rbx+20h]
0x180084af2  mov     edx, r14d
0x180084af5  shl     rdx, 5
0x180084af9  cmp     [rsp+0D8h+arg_40], 21h ; '!'
0x180084b01  mov     rdx, [rdx+rcx+18h]
0x180084b06  mov     rcx, [rsp+0D8h+arg_38]
0x180084b0e  mov     [r12+28h], rdx
0x180084b13  mov     rcx, [rcx+60h]
0x180084b17  mov     [r12+30h], rcx
0x180084b1c  mov     cl, [rsp+0D8h+arg_20]
0x180084b23  mov     [r12+10h], cl
0x180084b28  setnz   cl
0x180084b2b  inc     cl
0x180084b2d  mov     [r12+11h], cl
0x180084b32  cmp     byte ptr [rdi+134h], 2
0x180084b39  jb      short loc_180084B62
0x180084b3b  mov     rdx, [r13+18h]
0x180084b3f  mov     rcx, rsi
0x180084b42  mov     rax, [rdi+1A0h]
0x180084b49  jmp     short loc_180084B54
0x180084b4b  cmp     [rax], rdx
0x180084b4e  jz      short loc_180084B5B
0x180084b50  mov     rax, [rax+18h]
0x180084b54  test    rax, rax
0x180084b57  jnz     short loc_180084B4B
0x180084b59  jmp     short loc_180084B5E
0x180084b5b  mov     [rax], r8
0x180084b5e  xor     esi, esi
0x180084b60  jmp     short loc_180084B80
0x180084b62  test    rsi, rsi
0x180084b65  jz      short loc_180084B7E
0x180084b67  xor     r9d, r9d
0x180084b6a  mov     rdx, rsi
0x180084b6d  mov     rcx, rbx
0x180084b70  lea     r8d, [r9+1]
0x180084b74  call    exprDup
0x180084b79  mov     rcx, rax
0x180084b7c  jmp     short loc_180084B80
0x180084b7e  xor     ecx, ecx
0x180084b80  mov     [r12+18h], rcx
0x180084b85  mov     r14, r12
0x180084b88  mov     [r12+20h], rbp
0x180084b8d  xor     ebp, ebp
0x180084b8f  mov     [rdi+170h], r12
0x180084b96  jmp     short loc_180084BB8
0x180084b98  mov     r14, rax
0x180084b9b  jmp     loc_180084922
  ... truncated ...
```
