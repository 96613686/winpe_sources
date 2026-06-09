# sqlite3BeginTrigger

- ea: `0x180086a90`
- end: `0x180086fbc`
- name: `sqlite3BeginTrigger`
- size: `1324`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x1800de91c`

## callees

- `0x180005914`
- `0x180065318`
- `0x180066a38`
- `0x18008662c`
- `0x180086a90`
- `0x18008ade4`
- `0x18008bf3c`
- `0x18008e6ac`
- `0x18008e85c`
- `0x18008e9e8`
- `0x18008f7bc`
- `0x180090934`
- `0x1800938bc`
- `0x180095f98`
- `0x18009601c`
- `0x18009a2b0`
- `0x18009dccc`
- `0x1800a9f20`
- `0x1800aa384`
- `0x1800ab840`
- `0x1800c9390`

## string_xrefs

- `0x180086e24`: `sqlite_temp_master`
- `0x180086af4`: `temporary trigger may not have qualified name`
- `0x180086cbc`: `trigger %T already exists`
- `0x180086c15`: `cannot create triggers on virtual tables`
- `0x180086d14`: `cannot create trigger on system table`
- `0x180086d55`: `cannot create %s trigger on view: %S`
- `0x180086d77`: `cannot create INSTEAD OF trigger on table: %S`

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
      goto LABEL_78;
    }
    v17 = 1;
  }
  else
  {
    v17 = sqlite3TwoPartName(a1, a2, a3, &v38);
    if ( (v17 & 0x80000000) != 0 )
    {
LABEL_76:
      v15 = a8;
      v16 = a6;
      goto LABEL_77;
    }
    a2 = v38;
  }
  if ( !a7 || *(_BYTE *)(v10 + 103) )
    goto LABEL_76;
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
    goto LABEL_76;
  sqlite3FixInit((unsigned int)v40, (_DWORD)a1, v17, (unsigned int)"trigger", a2);
  if ( (unsigned int)sqlite3FixSrcList(v40, a7) )
    goto LABEL_76;
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
  v21 = sqlite3NameFromToken(v10, a2);
  v19 = v21;
  if ( !v21 )
  {
LABEL_77:
    v11 = 0;
    goto LABEL_78;
  }
  if ( (unsigned int)sqlite3CheckObjectName(a1, v21, "trigger", *(_QWORD *)v42) )
    goto LABEL_34;
  if ( *((_BYTE *)a1 + 300) < 2u
    && *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v17 + *(_QWORD *)(v10 + 32) + 24) + 56LL, v19, 0) + 16) )
  {
    if ( a10 )
      sqlite3CodeVerifySchema(a1, v17);
    else
      sqlite3ErrorMsg(a1, "trigger %T already exists", a2);
    goto LABEL_34;
  }
  v38 = *(_QWORD *)v42;
  if ( !(unsigned int)sqlite3_strnicmp(v38, "sqlite_", 7) )
  {
    sqlite3ErrorMsg(a1, "cannot create trigger on system table");
    goto LABEL_34;
  }
  if ( *(_BYTE *)(v42 + 63) != 2 )
  {
    if ( a4 == 65 )
    {
      sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
      goto LABEL_24;
    }
    goto LABEL_46;
  }
  if ( a4 == 65 )
  {
LABEL_46:
    if ( *((_BYTE *)a1 + 300) >= 2u )
      goto LABEL_60;
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
LABEL_60:
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
          if ( *((_BYTE *)a1 + 300) < 2u )
          {
            if ( v15 )
              v35 = exprDup(v10, v15, 1);
            else
              v35 = 0;
          }
          else
          {
            v35 = v15;
            for ( i = (__int64 *)a1[51]; i; i = (__int64 *)i[3] )
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
          a1[45] = (__int64)v32;
          goto LABEL_78;
        }
        v11 = 0;
LABEL_35:
        sqlite3DbFreeNN(v10);
        goto LABEL_78;
      }
    }
LABEL_34:
    v11 = 0;
    goto LABEL_35;
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
    goto LABEL_35;
LABEL_78:
  sqlite3SrcListDelete(v10, a7);
  result = sqlite3IdListDelete(v10, v16);
  if ( v15 )
    result = sqlite3ExprDeleteNN(v10, v15);
  if ( !a1[45] )
    return sqlite3DeleteTrigger(v10, v11);
  return result;
}

```

## disassembly

```asm
0x180086a90  mov     [rsp+arg_8], rbx
0x180086a95  mov     [rsp+arg_18], r9d
0x180086a9a  push    rbp
0x180086a9b  push    rsi
0x180086a9c  push    rdi
0x180086a9d  push    r12
0x180086a9f  push    r13
0x180086aa1  push    r14
0x180086aa3  push    r15
0x180086aa5  sub     rsp, 0A0h
0x180086aac  mov     rbx, [rcx]
0x180086aaf  xor     r14d, r14d
0x180086ab2  mov     rsi, r8
0x180086ab5  mov     [rsp+0D8h+arg_0], r14
0x180086abd  mov     r12, rdx
0x180086ac0  mov     [rsp+0D8h+var_A8], r14
0x180086ac5  mov     rdi, rcx
0x180086ac8  xor     edx, edx; Val
0x180086aca  lea     r8d, [r14+60h]; Size
0x180086ace  lea     rcx, [rsp+0D8h+var_98]; void *
0x180086ad3  call    memset_0
0x180086ad8  lea     ebp, [r14+1]
0x180086adc  mov     r13, [rsp+0D8h+arg_30]
0x180086ae4  cmp     [rsp+0D8h+arg_40], r14d
0x180086aec  jz      short loc_180086B1D
0x180086aee  cmp     [rsi+8], r14d
0x180086af2  jbe     short loc_180086B18
0x180086af4  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x180086afb  mov     rcx, rdi
0x180086afe  call    sqlite3ErrorMsg
0x180086b03  mov     rsi, [rsp+0D8h+arg_38]
0x180086b0b  mov     rbp, [rsp+0D8h+arg_28]
0x180086b13  jmp     loc_180086F66
0x180086b18  mov     r14d, ebp
0x180086b1b  jmp     short loc_180086B40
0x180086b1d  lea     r9, [rsp+0D8h+var_A8]
0x180086b22  mov     r8, rsi
0x180086b25  mov     rdx, r12
0x180086b28  mov     rcx, rdi
0x180086b2b  call    sqlite3TwoPartName
0x180086b30  mov     r14d, eax
0x180086b33  test    eax, eax
0x180086b35  js      loc_180086F4E
0x180086b3b  mov     r12, [rsp+0D8h+var_A8]
0x180086b40  test    r13, r13
0x180086b43  jz      loc_180086F4E
0x180086b49  cmp     byte ptr [rbx+67h], 0
0x180086b4d  jnz     loc_180086F4E
0x180086b53  cmp     byte ptr [rbx+0C5h], 0
0x180086b5a  jz      short loc_180086B7A
0x180086b5c  cmp     r14d, ebp
0x180086b5f  jz      short loc_180086B7A
0x180086b61  mov     rdx, [r13+10h]
0x180086b65  test    rdx, rdx
0x180086b68  jz      short loc_180086B72
0x180086b6a  mov     rcx, rbx
0x180086b6d  call    sqlite3DbFreeNN
0x180086b72  mov     qword ptr [r13+10h], 0
0x180086b7a  mov     rdx, r13
0x180086b7d  mov     rcx, rdi
0x180086b80  call    sqlite3SrcListLookup
0x180086b85  cmp     byte ptr [rbx+0C5h], 0
0x180086b8c  jnz     short loc_180086BA9
0x180086b8e  cmp     dword ptr [rsi+8], 0
0x180086b92  jnz     short loc_180086BA9
0x180086b94  test    rax, rax
0x180086b97  jz      short loc_180086BA9
0x180086b99  mov     rcx, [rbx+20h]
0x180086b9d  mov     rcx, [rcx+38h]
0x180086ba1  cmp     [rax+60h], rcx
0x180086ba5  cmovz   r14d, ebp
0x180086ba9  cmp     byte ptr [rbx+67h], 0
0x180086bad  jnz     loc_180086F4E
0x180086bb3  lea     r9, aTrigger; "trigger"
0x180086bba  mov     [rsp+0D8h+var_B8], r12
0x180086bbf  mov     r8d, r14d
0x180086bc2  lea     rcx, [rsp+0D8h+var_98]
0x180086bc7  mov     rdx, rdi
0x180086bca  call    sqlite3FixInit
0x180086bcf  mov     rdx, r13
0x180086bd2  lea     rcx, [rsp+0D8h+var_98]
0x180086bd7  call    sqlite3FixSrcList
0x180086bdc  test    eax, eax
0x180086bde  jnz     loc_180086F4E
0x180086be4  mov     rbp, [rsp+0D8h+arg_28]
0x180086bec  mov     rdx, r13
0x180086bef  mov     rsi, [rsp+0D8h+arg_38]
0x180086bf7  mov     rcx, rdi
0x180086bfa  xor     r15d, r15d
0x180086bfd  call    sqlite3SrcListLookup
0x180086c02  mov     [rsp+0D8h+arg_38], rax
0x180086c0a  test    rax, rax
0x180086c0d  jz      short loc_180086C24
0x180086c0f  cmp     byte ptr [rax+3Fh], 1
0x180086c13  jnz     short loc_180086C45
0x180086c15  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x180086c1c  mov     rcx, rdi
0x180086c1f  call    sqlite3ErrorMsg
0x180086c24  cmp     byte ptr [rbx+0C4h], 1
0x180086c2b  jnz     short loc_180086C34
0x180086c2d  or      dword ptr [rbx+0C8h], 1
0x180086c34  xor     r14d, r14d
0x180086c37  test    r15, r15
0x180086c3a  jz      loc_180086F66
0x180086c40  jmp     loc_180086CD0
0x180086c45  mov     rdx, r12
0x180086c48  mov     rcx, rbx
0x180086c4b  call    sqlite3NameFromToken
0x180086c50  mov     r15, rax
0x180086c53  test    rax, rax
0x180086c56  jz      loc_180086F5E
0x180086c5c  mov     rcx, [rsp+0D8h+arg_38]
0x180086c64  lea     r8, aTrigger; "trigger"
0x180086c6b  mov     rdx, rax
0x180086c6e  mov     r9, [rcx]
0x180086c71  mov     rcx, rdi
0x180086c74  call    sqlite3CheckObjectName
0x180086c79  test    eax, eax
0x180086c7b  jnz     short loc_180086CC8
0x180086c7d  cmp     byte ptr [rdi+12Ch], 2
0x180086c84  jnb     short loc_180086CEA
0x180086c86  mov     rax, [rbx+20h]
0x180086c8a  xor     r8d, r8d
0x180086c8d  mov     ecx, r14d
0x180086c90  mov     rdx, r15
0x180086c93  shl     rcx, 5
0x180086c97  mov     rcx, [rcx+rax+18h]
0x180086c9c  add     rcx, 38h ; '8'
0x180086ca0  call    findElementWithHash
0x180086ca5  cmp     qword ptr [rax+10h], 0
0x180086caa  jz      short loc_180086CEA
0x180086cac  cmp     [rsp+0D8h+arg_48], 0
0x180086cb4  mov     rcx, rdi
0x180086cb7  jnz     short loc_180086CE0
0x180086cb9  mov     r8, r12
0x180086cbc  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x180086cc3  call    sqlite3ErrorMsg
0x180086cc8  mov     r14, [rsp+0D8h+arg_0]
0x180086cd0  mov     rdx, r15
0x180086cd3  mov     rcx, rbx
0x180086cd6  call    sqlite3DbFreeNN
0x180086cdb  jmp     loc_180086F66
0x180086ce0  mov     edx, r14d
0x180086ce3  call    sqlite3CodeVerifySchema
0x180086ce8  jmp     short loc_180086CC8
0x180086cea  mov     r12, [rsp+0D8h+arg_38]
0x180086cf2  lea     rdx, aSqlite_0; "sqlite_"
0x180086cf9  mov     r8d, 7
0x180086cff  mov     rax, [r12]
0x180086d03  mov     rcx, rax
0x180086d06  mov     [rsp+0D8h+var_A8], rax
0x180086d0b  call    sqlite3_strnicmp
0x180086d10  test    eax, eax
0x180086d12  jnz     short loc_180086D25
0x180086d14  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x180086d1b  mov     rcx, rdi
0x180086d1e  call    sqlite3ErrorMsg
0x180086d23  jmp     short loc_180086CC8
0x180086d25  cmp     byte ptr [r12+3Fh], 2
0x180086d2b  jnz     short loc_180086D66
0x180086d2d  mov     eax, [rsp+0D8h+arg_18]
0x180086d34  cmp     eax, 41h ; 'A'
0x180086d37  jz      short loc_180086D88
0x180086d39  cmp     eax, 21h ; '!'
0x180086d3c  lea     rcx, aAfter; "AFTER"
0x180086d43  lea     r8, aBefore; "BEFORE"
0x180086d4a  cmovnz  r8, rcx
0x180086d4e  lea     r9, [r13+8]
0x180086d52  mov     rcx, rdi
0x180086d55  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x180086d5c  call    sqlite3ErrorMsg
0x180086d61  jmp     loc_180086C24
0x180086d66  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180086d6e  jnz     short loc_180086D88
0x180086d70  lea     r8, [r13+8]
0x180086d74  mov     rcx, rdi
0x180086d77  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x180086d7e  call    sqlite3ErrorMsg
0x180086d83  jmp     loc_180086C24
0x180086d88  cmp     byte ptr [rdi+12Ch], 2
0x180086d8f  jnb     loc_180086E50
0x180086d95  mov     rcx, [r12+60h]
0x180086d9a  mov     r12d, 0FFFF8000h
0x180086da0  test    rcx, rcx
0x180086da3  jz      short loc_180086DC3
0x180086da5  mov     rdx, [rbx+20h]
0x180086da9  xor     r12d, r12d
0x180086dac  cmp     [rdx+18h], rcx
0x180086db0  jz      short loc_180086DC3
0x180086db2  inc     r12d
0x180086db5  movsxd  rax, r12d
0x180086db8  shl     rax, 5
0x180086dbc  cmp     [rax+rdx+18h], rcx
0x180086dc1  jnz     short loc_180086DB2
0x180086dc3  mov     rcx, [rbx+20h]
0x180086dc7  mov     edx, [rsp+0D8h+arg_40]
0x180086dce  movsxd  rax, r12d
0x180086dd1  shl     rax, 5
0x180086dd5  mov     rax, [rax+rcx]
0x180086dd9  mov     [rsp+0D8h+var_A0], rax
0x180086dde  test    edx, edx
0x180086de0  jz      short loc_180086DE6
0x180086de2  mov     rax, [rcx+20h]
0x180086de6  cmp     r12d, 1
0x180086dea  jz      short loc_180086DF0
0x180086dec  test    edx, edx
0x180086dee  jz      short loc_180086DF7
0x180086df0  mov     edx, 5
0x180086df5  jmp     short loc_180086DFC
0x180086df7  mov     edx, 7
0x180086dfc  mov     r9, [rsp+0D8h+var_A8]
0x180086e01  mov     r8, r15
0x180086e04  mov     rcx, rdi
0x180086e07  mov     [rsp+0D8h+var_B8], rax
0x180086e0c  call    sqlite3AuthCheck
0x180086e11  test    eax, eax
0x180086e13  jnz     loc_180086CC8
0x180086e19  lea     rax, aSqliteMaster; "sqlite_master"
0x180086e20  cmp     r12d, 1
0x180086e24  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180086e2b  mov     rcx, rdi
0x180086e2e  cmovnz  r8, rax
0x180086e32  mov     rax, [rsp+0D8h+var_A0]
0x180086e37  xor     r9d, r9d
0x180086e3a  mov     [rsp+0D8h+var_B8], rax
0x180086e3f  lea     edx, [r9+12h]
0x180086e43  call    sqlite3AuthCheck
0x180086e48  test    eax, eax
0x180086e4a  jnz     loc_180086CC8
0x180086e50  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180086e58  mov     eax, 21h ; '!'
0x180086e5d  mov     edx, 48h ; 'H'
0x180086e62  mov     rcx, rbx
0x180086e65  cmovnz  eax, [rsp+0D8h+arg_18]
0x180086e6d  mov     [rsp+0D8h+arg_40], eax
0x180086e74  call    sqlite3DbMallocZero
0x180086e79  mov     r12, rax
0x180086e7c  test    rax, rax
0x180086e7f  jz      loc_180086F46
0x180086e85  mov     [rax], r15
0x180086e88  mov     rcx, rbx
0x180086e8b  mov     rdx, [r13+18h]
0x180086e8f  call    sqlite3DbStrDup
0x180086e94  mov     [r12+8], rax
0x180086e99  mov     r8, rax
0x180086e9c  mov     rcx, [rbx+20h]
0x180086ea0  mov     edx, r14d
0x180086ea3  shl     rdx, 5
0x180086ea7  cmp     [rsp+0D8h+arg_40], 21h ; '!'
0x180086eaf  mov     rdx, [rdx+rcx+18h]
0x180086eb4  mov     rcx, [rsp+0D8h+arg_38]
0x180086ebc  mov     [r12+28h], rdx
0x180086ec1  mov     rcx, [rcx+60h]
0x180086ec5  mov     [r12+30h], rcx
0x180086eca  mov     cl, [rsp+0D8h+arg_20]
0x180086ed1  mov     [r12+10h], cl
0x180086ed6  setnz   cl
0x180086ed9  inc     cl
0x180086edb  mov     [r12+11h], cl
0x180086ee0  cmp     byte ptr [rdi+12Ch], 2
0x180086ee7  jb      short loc_180086F10
0x180086ee9  mov     rdx, [r13+18h]
0x180086eed  mov     rcx, rsi
0x180086ef0  mov     rax, [rdi+198h]
0x180086ef7  jmp     short loc_180086F02
0x180086ef9  cmp     [rax], rdx
0x180086efc  jz      short loc_180086F09
0x180086efe  mov     rax, [rax+18h]
0x180086f02  test    rax, rax
0x180086f05  jnz     short loc_180086EF9
0x180086f07  jmp     short loc_180086F0C
0x180086f09  mov     [rax], r8
0x180086f0c  xor     esi, esi
0x180086f0e  jmp     short loc_180086F2E
0x180086f10  test    rsi, rsi
0x180086f13  jz      short loc_180086F2C
0x180086f15  xor     r9d, r9d
0x180086f18  mov     rdx, rsi
0x180086f1b  mov     rcx, rbx
0x180086f1e  lea     r8d, [r9+1]
0x180086f22  call    exprDup
0x180086f27  mov     rcx, rax
0x180086f2a  jmp     short loc_180086F2E
0x180086f2c  xor     ecx, ecx
0x180086f2e  mov     [r12+18h], rcx
0x180086f33  mov     r14, r12
0x180086f36  mov     [r12+20h], rbp
0x180086f3b  xor     ebp, ebp
0x180086f3d  mov     [rdi+168h], r12
0x180086f44  jmp     short loc_180086F66
0x180086f46  mov     r14, rax
0x180086f49  jmp     loc_180086CD0
0x180086f4e  mov     rsi, [rsp+0D8h+arg_38]
0x180086f56  mov     rbp, [rsp+0D8h+arg_28]
0x180086f5e  mov     r14, [rsp+0D8h+arg_0]
0x180086f66  mov     rdx, r13
0x180086f69  mov     rcx, rbx
0x180086f6c  call    sqlite3SrcListDelete
0x180086f71  mov     rdx, rbp
0x180086f74  mov     rcx, rbx
  ... truncated ...
```
