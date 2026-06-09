# sqlite3BeginTrigger

- ea: `0x14004c220`
- end: `0x14004c74c`
- name: `sqlite3BeginTrigger`
- size: `1324`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `reparse_path`

## callers

- `0x1400a40bc`

## callees

- `0x1400026c0`
- `0x14002aa98`
- `0x14002c1b8`
- `0x14004bdbc`
- `0x14004c220`
- `0x140050574`
- `0x1400516cc`
- `0x140053e3c`
- `0x140053fec`
- `0x140054178`
- `0x140054f4c`
- `0x1400560c4`
- `0x14005904c`
- `0x14005b728`
- `0x14005b7ac`
- `0x14005fa40`
- `0x14006345c`
- `0x14006f6b0`
- `0x14006fb14`
- `0x140070fd0`
- `0x14008eb20`

## string_xrefs

- `0x14004c5b4`: `sqlite_temp_master`
- `0x14004c284`: `temporary trigger may not have qualified name`
- `0x14004c44c`: `trigger %T already exists`
- `0x14004c3a5`: `cannot create triggers on virtual tables`
- `0x14004c4a4`: `cannot create trigger on system table`
- `0x14004c4e5`: `cannot create %s trigger on view: %S`
- `0x14004c507`: `cannot create INSTEAD OF trigger on table: %S`

## pseudocode

```c
__int64 __fastcall sqlite3BeginTrigger(
        __int64 a1,
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
  _BYTE *v35; // rcx
  __int64 *i; // rax
  __int64 result; // rax
  __int64 v38; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v39; // [rsp+38h] [rbp-A0h]
  _BYTE v40[152]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v42; // [rsp+118h] [rbp+40h]
  int v43; // [rsp+120h] [rbp+48h]

  v10 = *(_QWORD *)a1;
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
  sqlite3FixInit((unsigned int)v40, a1, v17, (unsigned int)"trigger", a2);
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
  if ( *(_BYTE *)(a1 + 300) < 2u
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
    if ( *(_BYTE *)(a1 + 300) >= 2u )
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
    if ( !(unsigned int)sqlite3AuthCheck(a1, v28, v19, v38, v27) )
    {
      v29 = "sqlite_temp_master";
      if ( v24 != 1 )
        v29 = "sqlite_master";
      if ( !(unsigned int)sqlite3AuthCheck(a1, 18, (_DWORD)v29, 0, v39) )
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
          if ( *(_BYTE *)(a1 + 300) < 2u )
          {
            if ( v15 )
              v35 = exprDup(v10, v15, 1u, 0);
            else
              v35 = 0;
          }
          else
          {
            v35 = (_BYTE *)v15;
            for ( i = *(__int64 **)(a1 + 408); i; i = (__int64 *)i[3] )
            {
              if ( *i == *(_QWORD *)(a7 + 24) )
              {
                *i = v34;
                break;
              }
            }
            v15 = 0;
          }
          v32[3] = (__int64)v35;
          v11 = v32;
          v32[4] = a6;
          v16 = 0;
          *(_QWORD *)(a1 + 360) = v32;
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
    result = sqlite3ExprDeleteNN(v10);
  if ( !*(_QWORD *)(a1 + 360) )
    return sqlite3DeleteTrigger(v10, v11);
  return result;
}

```

## disassembly

```asm
0x14004c220  mov     [rsp+arg_8], rbx
0x14004c225  mov     [rsp+arg_18], r9d
0x14004c22a  push    rbp
0x14004c22b  push    rsi
0x14004c22c  push    rdi
0x14004c22d  push    r12
0x14004c22f  push    r13
0x14004c231  push    r14
0x14004c233  push    r15
0x14004c235  sub     rsp, 0A0h
0x14004c23c  mov     rbx, [rcx]
0x14004c23f  xor     r14d, r14d
0x14004c242  mov     rsi, r8
0x14004c245  mov     [rsp+0D8h+arg_0], r14
0x14004c24d  mov     r12, rdx
0x14004c250  mov     [rsp+0D8h+var_A8], r14
0x14004c255  mov     rdi, rcx
0x14004c258  xor     edx, edx; Val
0x14004c25a  lea     r8d, [r14+60h]; Size
0x14004c25e  lea     rcx, [rsp+0D8h+var_98]; void *
0x14004c263  call    memset_0
0x14004c268  lea     ebp, [r14+1]
0x14004c26c  mov     r13, [rsp+0D8h+arg_30]
0x14004c274  cmp     [rsp+0D8h+arg_40], r14d
0x14004c27c  jz      short loc_14004C2AD
0x14004c27e  cmp     [rsi+8], r14d
0x14004c282  jbe     short loc_14004C2A8
0x14004c284  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x14004c28b  mov     rcx, rdi
0x14004c28e  call    sqlite3ErrorMsg
0x14004c293  mov     rsi, [rsp+0D8h+arg_38]
0x14004c29b  mov     rbp, [rsp+0D8h+arg_28]
0x14004c2a3  jmp     loc_14004C6F6
0x14004c2a8  mov     r14d, ebp
0x14004c2ab  jmp     short loc_14004C2D0
0x14004c2ad  lea     r9, [rsp+0D8h+var_A8]
0x14004c2b2  mov     r8, rsi
0x14004c2b5  mov     rdx, r12
0x14004c2b8  mov     rcx, rdi
0x14004c2bb  call    sqlite3TwoPartName
0x14004c2c0  mov     r14d, eax
0x14004c2c3  test    eax, eax
0x14004c2c5  js      loc_14004C6DE
0x14004c2cb  mov     r12, [rsp+0D8h+var_A8]
0x14004c2d0  test    r13, r13
0x14004c2d3  jz      loc_14004C6DE
0x14004c2d9  cmp     byte ptr [rbx+67h], 0
0x14004c2dd  jnz     loc_14004C6DE
0x14004c2e3  cmp     byte ptr [rbx+0C5h], 0
0x14004c2ea  jz      short loc_14004C30A
0x14004c2ec  cmp     r14d, ebp
0x14004c2ef  jz      short loc_14004C30A
0x14004c2f1  mov     rdx, [r13+10h]
0x14004c2f5  test    rdx, rdx
0x14004c2f8  jz      short loc_14004C302
0x14004c2fa  mov     rcx, rbx
0x14004c2fd  call    sqlite3DbFreeNN
0x14004c302  mov     qword ptr [r13+10h], 0
0x14004c30a  mov     rdx, r13
0x14004c30d  mov     rcx, rdi
0x14004c310  call    sqlite3SrcListLookup
0x14004c315  cmp     byte ptr [rbx+0C5h], 0
0x14004c31c  jnz     short loc_14004C339
0x14004c31e  cmp     dword ptr [rsi+8], 0
0x14004c322  jnz     short loc_14004C339
0x14004c324  test    rax, rax
0x14004c327  jz      short loc_14004C339
0x14004c329  mov     rcx, [rbx+20h]
0x14004c32d  mov     rcx, [rcx+38h]
0x14004c331  cmp     [rax+60h], rcx
0x14004c335  cmovz   r14d, ebp
0x14004c339  cmp     byte ptr [rbx+67h], 0
0x14004c33d  jnz     loc_14004C6DE
0x14004c343  lea     r9, aTrigger; "trigger"
0x14004c34a  mov     [rsp+0D8h+var_B8], r12
0x14004c34f  mov     r8d, r14d
0x14004c352  lea     rcx, [rsp+0D8h+var_98]
0x14004c357  mov     rdx, rdi
0x14004c35a  call    sqlite3FixInit
0x14004c35f  mov     rdx, r13
0x14004c362  lea     rcx, [rsp+0D8h+var_98]
0x14004c367  call    sqlite3FixSrcList
0x14004c36c  test    eax, eax
0x14004c36e  jnz     loc_14004C6DE
0x14004c374  mov     rbp, [rsp+0D8h+arg_28]
0x14004c37c  mov     rdx, r13
0x14004c37f  mov     rsi, [rsp+0D8h+arg_38]
0x14004c387  mov     rcx, rdi
0x14004c38a  xor     r15d, r15d
0x14004c38d  call    sqlite3SrcListLookup
0x14004c392  mov     [rsp+0D8h+arg_38], rax
0x14004c39a  test    rax, rax
0x14004c39d  jz      short loc_14004C3B4
0x14004c39f  cmp     byte ptr [rax+3Fh], 1
0x14004c3a3  jnz     short loc_14004C3D5
0x14004c3a5  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x14004c3ac  mov     rcx, rdi
0x14004c3af  call    sqlite3ErrorMsg
0x14004c3b4  cmp     byte ptr [rbx+0C4h], 1
0x14004c3bb  jnz     short loc_14004C3C4
0x14004c3bd  or      dword ptr [rbx+0C8h], 1
0x14004c3c4  xor     r14d, r14d
0x14004c3c7  test    r15, r15
0x14004c3ca  jz      loc_14004C6F6
0x14004c3d0  jmp     loc_14004C460
0x14004c3d5  mov     rdx, r12
0x14004c3d8  mov     rcx, rbx
0x14004c3db  call    sqlite3NameFromToken
0x14004c3e0  mov     r15, rax
0x14004c3e3  test    rax, rax
0x14004c3e6  jz      loc_14004C6EE
0x14004c3ec  mov     rcx, [rsp+0D8h+arg_38]
0x14004c3f4  lea     r8, aTrigger; "trigger"
0x14004c3fb  mov     rdx, rax
0x14004c3fe  mov     r9, [rcx]
0x14004c401  mov     rcx, rdi
0x14004c404  call    sqlite3CheckObjectName
0x14004c409  test    eax, eax
0x14004c40b  jnz     short loc_14004C458
0x14004c40d  cmp     byte ptr [rdi+12Ch], 2
0x14004c414  jnb     short loc_14004C47A
0x14004c416  mov     rax, [rbx+20h]
0x14004c41a  xor     r8d, r8d
0x14004c41d  mov     ecx, r14d
0x14004c420  mov     rdx, r15
0x14004c423  shl     rcx, 5
0x14004c427  mov     rcx, [rcx+rax+18h]
0x14004c42c  add     rcx, 38h ; '8'
0x14004c430  call    findElementWithHash
0x14004c435  cmp     qword ptr [rax+10h], 0
0x14004c43a  jz      short loc_14004C47A
0x14004c43c  cmp     [rsp+0D8h+arg_48], 0
0x14004c444  mov     rcx, rdi
0x14004c447  jnz     short loc_14004C470
0x14004c449  mov     r8, r12
0x14004c44c  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x14004c453  call    sqlite3ErrorMsg
0x14004c458  mov     r14, [rsp+0D8h+arg_0]
0x14004c460  mov     rdx, r15
0x14004c463  mov     rcx, rbx
0x14004c466  call    sqlite3DbFreeNN
0x14004c46b  jmp     loc_14004C6F6
0x14004c470  mov     edx, r14d
0x14004c473  call    sqlite3CodeVerifySchema
0x14004c478  jmp     short loc_14004C458
0x14004c47a  mov     r12, [rsp+0D8h+arg_38]
0x14004c482  lea     rdx, aSqlite_0; "sqlite_"
0x14004c489  mov     r8d, 7
0x14004c48f  mov     rax, [r12]
0x14004c493  mov     rcx, rax
0x14004c496  mov     [rsp+0D8h+var_A8], rax
0x14004c49b  call    sqlite3_strnicmp
0x14004c4a0  test    eax, eax
0x14004c4a2  jnz     short loc_14004C4B5
0x14004c4a4  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x14004c4ab  mov     rcx, rdi
0x14004c4ae  call    sqlite3ErrorMsg
0x14004c4b3  jmp     short loc_14004C458
0x14004c4b5  cmp     byte ptr [r12+3Fh], 2
0x14004c4bb  jnz     short loc_14004C4F6
0x14004c4bd  mov     eax, [rsp+0D8h+arg_18]
0x14004c4c4  cmp     eax, 41h ; 'A'
0x14004c4c7  jz      short loc_14004C518
0x14004c4c9  cmp     eax, 21h ; '!'
0x14004c4cc  lea     rcx, aAfter; "AFTER"
0x14004c4d3  lea     r8, aBefore; "BEFORE"
0x14004c4da  cmovnz  r8, rcx
0x14004c4de  lea     r9, [r13+8]
0x14004c4e2  mov     rcx, rdi
0x14004c4e5  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x14004c4ec  call    sqlite3ErrorMsg
0x14004c4f1  jmp     loc_14004C3B4
0x14004c4f6  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x14004c4fe  jnz     short loc_14004C518
0x14004c500  lea     r8, [r13+8]
0x14004c504  mov     rcx, rdi
0x14004c507  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x14004c50e  call    sqlite3ErrorMsg
0x14004c513  jmp     loc_14004C3B4
0x14004c518  cmp     byte ptr [rdi+12Ch], 2
0x14004c51f  jnb     loc_14004C5E0
0x14004c525  mov     rcx, [r12+60h]
0x14004c52a  mov     r12d, 0FFFF8000h
0x14004c530  test    rcx, rcx
0x14004c533  jz      short loc_14004C553
0x14004c535  mov     rdx, [rbx+20h]
0x14004c539  xor     r12d, r12d
0x14004c53c  cmp     [rdx+18h], rcx
0x14004c540  jz      short loc_14004C553
0x14004c542  inc     r12d
0x14004c545  movsxd  rax, r12d
0x14004c548  shl     rax, 5
0x14004c54c  cmp     [rax+rdx+18h], rcx
0x14004c551  jnz     short loc_14004C542
0x14004c553  mov     rcx, [rbx+20h]
0x14004c557  mov     edx, [rsp+0D8h+arg_40]
0x14004c55e  movsxd  rax, r12d
0x14004c561  shl     rax, 5
0x14004c565  mov     rax, [rax+rcx]
0x14004c569  mov     [rsp+0D8h+var_A0], rax
0x14004c56e  test    edx, edx
0x14004c570  jz      short loc_14004C576
0x14004c572  mov     rax, [rcx+20h]
0x14004c576  cmp     r12d, 1
0x14004c57a  jz      short loc_14004C580
0x14004c57c  test    edx, edx
0x14004c57e  jz      short loc_14004C587
0x14004c580  mov     edx, 5
0x14004c585  jmp     short loc_14004C58C
0x14004c587  mov     edx, 7
0x14004c58c  mov     r9, [rsp+0D8h+var_A8]
0x14004c591  mov     r8, r15
0x14004c594  mov     rcx, rdi
0x14004c597  mov     [rsp+0D8h+var_B8], rax
0x14004c59c  call    sqlite3AuthCheck
0x14004c5a1  test    eax, eax
0x14004c5a3  jnz     loc_14004C458
0x14004c5a9  lea     rax, aSqliteMaster; "sqlite_master"
0x14004c5b0  cmp     r12d, 1
0x14004c5b4  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x14004c5bb  mov     rcx, rdi
0x14004c5be  cmovnz  r8, rax
0x14004c5c2  mov     rax, [rsp+0D8h+var_A0]
0x14004c5c7  xor     r9d, r9d
0x14004c5ca  mov     [rsp+0D8h+var_B8], rax
0x14004c5cf  lea     edx, [r9+12h]
0x14004c5d3  call    sqlite3AuthCheck
0x14004c5d8  test    eax, eax
0x14004c5da  jnz     loc_14004C458
0x14004c5e0  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x14004c5e8  mov     eax, 21h ; '!'
0x14004c5ed  mov     edx, 48h ; 'H'
0x14004c5f2  mov     rcx, rbx
0x14004c5f5  cmovnz  eax, [rsp+0D8h+arg_18]
0x14004c5fd  mov     [rsp+0D8h+arg_40], eax
0x14004c604  call    sqlite3DbMallocZero
0x14004c609  mov     r12, rax
0x14004c60c  test    rax, rax
0x14004c60f  jz      loc_14004C6D6
0x14004c615  mov     [rax], r15
0x14004c618  mov     rcx, rbx
0x14004c61b  mov     rdx, [r13+18h]
0x14004c61f  call    sqlite3DbStrDup
0x14004c624  mov     [r12+8], rax
0x14004c629  mov     r8, rax
0x14004c62c  mov     rcx, [rbx+20h]
0x14004c630  mov     edx, r14d
0x14004c633  shl     rdx, 5
0x14004c637  cmp     [rsp+0D8h+arg_40], 21h ; '!'
0x14004c63f  mov     rdx, [rdx+rcx+18h]
0x14004c644  mov     rcx, [rsp+0D8h+arg_38]
0x14004c64c  mov     [r12+28h], rdx
0x14004c651  mov     rcx, [rcx+60h]
0x14004c655  mov     [r12+30h], rcx
0x14004c65a  mov     cl, [rsp+0D8h+arg_20]
0x14004c661  mov     [r12+10h], cl
0x14004c666  setnz   cl
0x14004c669  inc     cl
0x14004c66b  mov     [r12+11h], cl
0x14004c670  cmp     byte ptr [rdi+12Ch], 2
0x14004c677  jb      short loc_14004C6A0
0x14004c679  mov     rdx, [r13+18h]
0x14004c67d  mov     rcx, rsi
0x14004c680  mov     rax, [rdi+198h]
0x14004c687  jmp     short loc_14004C692
0x14004c689  cmp     [rax], rdx
0x14004c68c  jz      short loc_14004C699
0x14004c68e  mov     rax, [rax+18h]
0x14004c692  test    rax, rax
0x14004c695  jnz     short loc_14004C689
0x14004c697  jmp     short loc_14004C69C
0x14004c699  mov     [rax], r8
0x14004c69c  xor     esi, esi
0x14004c69e  jmp     short loc_14004C6BE
0x14004c6a0  test    rsi, rsi
0x14004c6a3  jz      short loc_14004C6BC
0x14004c6a5  xor     r9d, r9d
0x14004c6a8  mov     rdx, rsi
0x14004c6ab  mov     rcx, rbx
0x14004c6ae  lea     r8d, [r9+1]
0x14004c6b2  call    exprDup
0x14004c6b7  mov     rcx, rax
0x14004c6ba  jmp     short loc_14004C6BE
0x14004c6bc  xor     ecx, ecx
0x14004c6be  mov     [r12+18h], rcx
0x14004c6c3  mov     r14, r12
0x14004c6c6  mov     [r12+20h], rbp
0x14004c6cb  xor     ebp, ebp
0x14004c6cd  mov     [rdi+168h], r12
0x14004c6d4  jmp     short loc_14004C6F6
0x14004c6d6  mov     r14, rax
0x14004c6d9  jmp     loc_14004C460
0x14004c6de  mov     rsi, [rsp+0D8h+arg_38]
0x14004c6e6  mov     rbp, [rsp+0D8h+arg_28]
0x14004c6ee  mov     r14, [rsp+0D8h+arg_0]
0x14004c6f6  mov     rdx, r13
0x14004c6f9  mov     rcx, rbx
0x14004c6fc  call    sqlite3SrcListDelete
0x14004c701  mov     rdx, rbp
0x14004c704  mov     rcx, rbx
  ... truncated ...
```
