# sqlite3BeginTrigger

- ea: `0x1801c7708`
- end: `0x1801c7be9`
- name: `sqlite3BeginTrigger`
- size: `1249`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path`

## callers

- `0x18021d7f0`

## callees

- `0x1800bc094`
- `0x1801a6b9c`
- `0x1801c716c`
- `0x1801c7708`
- `0x1801cb4d4`
- `0x1801cc4f8`
- `0x1801ce9a0`
- `0x1801ceb84`
- `0x1801ced34`
- `0x1801cfa2c`
- `0x1801d0c94`
- `0x1801d3c20`
- `0x1801d3d00`
- `0x1801d6340`
- `0x1801d63c4`
- `0x1801da504`
- `0x1801de0f4`
- `0x1801e5300`
- `0x1801e5e94`
- `0x1801e7704`
- `0x1801e9ec8`
- `0x1801ea2e4`
- `0x1801eba6c`
- `0x180208540`

## string_xrefs

- `0x1801c7abe`: `sqlite_temp_master`
- `0x1801c7a01`: `cannot create %s trigger on view: %S`
- `0x1801c7a23`: `cannot create INSTEAD OF trigger on table: %S`
- `0x1801c7906`: `cannot create triggers on shadow tables`
- `0x1801c798d`: `trigger %T already exists`
- `0x1801c79c6`: `cannot create trigger on system table`
- `0x1801c776f`: `temporary trigger may not have qualified name`
- `0x1801c7864`: `cannot create triggers on virtual tables`

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
  __int64 v10; // rdi
  __int64 v14; // r15
  unsigned int v15; // esi
  __int64 v16; // rax
  __int64 v17; // rax
  _QWORD *v18; // r14
  __int64 result; // rax
  __int64 v20; // rax
  int v21; // r13d
  const char *v22; // r8
  int v23; // eax
  __int64 v24; // rdx
  int v25; // r12d
  __int64 v26; // rax
  __int64 v27; // rcx
  const char *v28; // r8
  int v29; // r12d
  __int64 v30; // rax
  __int64 v31; // r9
  __int64 v32; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v33[152]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v34; // [rsp+E0h] [rbp+8h]

  v10 = *a1;
  v34 = 0;
  v32 = 0;
  v14 = 0;
  memset_0(v33, 0, 0x60u);
  if ( a9 )
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      sqlite3ErrorMsg(a1, "temporary trigger may not have qualified name");
      goto LABEL_24;
    }
    v15 = 1;
  }
  else
  {
    v15 = sqlite3TwoPartName(a1, a2, a3, &v32);
    if ( (v15 & 0x80000000) != 0 )
      goto LABEL_24;
    a2 = v32;
  }
  if ( a7 && !*(_BYTE *)(v10 + 103) )
  {
    if ( *(_BYTE *)(v10 + 197) && v15 != 1 )
    {
      sqlite3DbFree(v10, *(_QWORD *)(a7 + 16));
      *(_QWORD *)(a7 + 16) = 0;
    }
    v16 = sqlite3SrcListLookup(a1, a7);
    if ( !*(_BYTE *)(v10 + 197)
      && !*(_DWORD *)(a3 + 8)
      && v16
      && *(_QWORD *)(v16 + 96) == *(_QWORD *)(*(_QWORD *)(v10 + 32) + 56LL) )
    {
      v15 = 1;
    }
    if ( !*(_BYTE *)(v10 + 103) )
    {
      sqlite3FixInit((unsigned int)v33, (_DWORD)a1, v15, (unsigned int)"trigger", a2);
      if ( !(unsigned int)sqlite3FixSrcList(v33, a7) )
      {
        v17 = sqlite3SrcListLookup(a1, a7);
        v18 = (_QWORD *)v17;
        if ( !v17 )
          goto LABEL_22;
        if ( *(_BYTE *)(v17 + 63) == 1 )
        {
          sqlite3ErrorMsg(a1, "cannot create triggers on virtual tables");
          goto LABEL_22;
        }
        if ( (*(_DWORD *)(v17 + 48) & 0x1000) != 0 && (unsigned int)sqlite3ReadOnlyShadowTables(v10) )
        {
          sqlite3ErrorMsg(a1, "cannot create triggers on shadow tables");
          goto LABEL_22;
        }
        v20 = sqlite3NameFromToken(v10, a2);
        v34 = v20;
        if ( !v20 || (unsigned int)sqlite3CheckObjectName(a1, v20, "trigger", *v18) )
          goto LABEL_24;
        if ( *((_BYTE *)a1 + 308) < 2u
          && *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v15 + *(_QWORD *)(v10 + 32) + 24) + 56LL, v34, 0) + 16) )
        {
          if ( a10 )
            sqlite3CodeVerifySchema(a1, v15);
          else
            sqlite3ErrorMsg(a1, "trigger %T already exists", a2);
          goto LABEL_24;
        }
        v21 = 7;
        if ( !(unsigned int)sqlite3_strnicmp(*v18, "sqlite_", 7) )
        {
          sqlite3ErrorMsg(a1, "cannot create trigger on system table");
          goto LABEL_24;
        }
        if ( *((_BYTE *)v18 + 63) == 2 )
        {
          if ( a4 != 65 )
          {
            v22 = "BEFORE";
            if ( a4 != 33 )
              v22 = "AFTER";
            sqlite3ErrorMsg(a1, "cannot create %s trigger on view: %S", v22, (const wchar_t *)(a7 + 8));
            goto LABEL_22;
          }
        }
        else if ( a4 == 65 )
        {
          sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
LABEL_22:
          if ( *(_BYTE *)(v10 + 196) == 1 )
            *(_DWORD *)(v10 + 200) |= 1u;
          goto LABEL_24;
        }
        if ( *((_BYTE *)a1 + 308) >= 2u )
          goto LABEL_57;
        v23 = sqlite3SchemaToIndex(v10, v18[12]);
        v24 = *(_QWORD *)(v10 + 32);
        v25 = v23;
        v26 = *(_QWORD *)(32LL * v23 + v24);
        v32 = v26;
        if ( a9 )
          v27 = *(_QWORD *)(v24 + 32);
        else
          v27 = v26;
        if ( v25 == 1 || a9 )
          v21 = 5;
        if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v21, v34, *v18, v27) )
        {
          v28 = "sqlite_temp_master";
          if ( v25 != 1 )
            v28 = "sqlite_master";
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v28, 0, v32) )
          {
LABEL_57:
            v29 = 33;
            if ( a4 != 65 )
              v29 = a4;
            v14 = sqlite3DbMallocZero(v10, 72);
            if ( v14 )
            {
              *(_QWORD *)v14 = v34;
              v34 = 0;
              v30 = sqlite3DbStrDup(v10, *(_QWORD *)(a7 + 24));
              *(_QWORD *)(v14 + 8) = v30;
              *(_QWORD *)(v14 + 40) = *(_QWORD *)(32LL * v15 + *(_QWORD *)(v10 + 32) + 24);
              *(_QWORD *)(v14 + 48) = v18[12];
              *(_BYTE *)(v14 + 16) = a5;
              *(_BYTE *)(v14 + 17) = (v29 != 33) + 1;
              if ( *((_BYTE *)a1 + 308) < 2u )
              {
                v31 = sqlite3ExprDup(v10, a8, 1);
              }
              else
              {
                sqlite3RenameTokenRemap(a1, v30, *(_QWORD *)(a7 + 24), a8);
                a8 = 0;
              }
              *(_QWORD *)(v14 + 24) = v31;
              *(_QWORD *)(v14 + 32) = a6;
              a1[46] = v14;
              a6 = 0;
            }
          }
        }
      }
    }
  }
LABEL_24:
  sqlite3DbFree(v10, v34);
  sqlite3SrcListDelete(v10, a7);
  sqlite3IdListDelete(v10, a6);
  result = sqlite3ExprDeleteGeneric(v10, a8);
  if ( !a1[46] )
    return sqlite3DeleteTrigger(v10, v14);
  return result;
}

```

## disassembly

```asm
0x1801c7708  mov     [rsp+arg_8], rbx
0x1801c770d  mov     [rsp+arg_18], r9d
0x1801c7712  push    rbp
0x1801c7713  push    rsi
0x1801c7714  push    rdi
0x1801c7715  push    r12
0x1801c7717  push    r13
0x1801c7719  push    r14
0x1801c771b  push    r15
0x1801c771d  sub     rsp, 0A0h
0x1801c7724  mov     rdi, [rcx]
0x1801c7727  xor     r13d, r13d
0x1801c772a  mov     r14, r8
0x1801c772d  mov     [rsp+0D8h+arg_0], r13
0x1801c7735  mov     r12, rdx
0x1801c7738  mov     [rsp+0D8h+var_A8], r13
0x1801c773d  mov     rbx, rcx
0x1801c7740  xor     edx, edx; Val
0x1801c7742  lea     r8d, [r13+60h]; Size
0x1801c7746  mov     r15d, r13d
0x1801c7749  lea     rcx, [rsp+0D8h+var_98]; void *
0x1801c774e  call    memset_0
0x1801c7753  lea     eax, [r13+1]
0x1801c7757  mov     rbp, [rsp+0D8h+arg_30]
0x1801c775f  cmp     [rsp+0D8h+arg_40], r13d
0x1801c7767  jz      short loc_1801C7787
0x1801c7769  cmp     [r14+8], r13d
0x1801c776d  jbe     short loc_1801C7783
0x1801c776f  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x1801c7776  mov     rcx, rbx
0x1801c7779  call    sqlite3ErrorMsg
0x1801c777e  jmp     loc_1801C7886
0x1801c7783  mov     esi, eax
0x1801c7785  jmp     short loc_1801C77AE
0x1801c7787  lea     r9, [rsp+0D8h+var_A8]
0x1801c778c  mov     r8, r14
0x1801c778f  mov     rdx, r12
0x1801c7792  mov     rcx, rbx
0x1801c7795  call    sqlite3TwoPartName
0x1801c779a  mov     esi, eax
0x1801c779c  test    eax, eax
0x1801c779e  js      loc_1801C7886
0x1801c77a4  mov     r12, [rsp+0D8h+var_A8]
0x1801c77a9  mov     eax, 1
0x1801c77ae  test    rbp, rbp
0x1801c77b1  jz      loc_1801C7886
0x1801c77b7  cmp     [rdi+67h], r13b
0x1801c77bb  jnz     loc_1801C7886
0x1801c77c1  cmp     [rdi+0C5h], r13b
0x1801c77c8  jz      short loc_1801C77DE
0x1801c77ca  cmp     esi, eax
0x1801c77cc  jz      short loc_1801C77DE
0x1801c77ce  mov     rdx, [rbp+10h]
0x1801c77d2  mov     rcx, rdi
0x1801c77d5  call    sqlite3DbFree
0x1801c77da  mov     [rbp+10h], r13
0x1801c77de  mov     rdx, rbp
0x1801c77e1  mov     rcx, rbx
0x1801c77e4  call    sqlite3SrcListLookup
0x1801c77e9  mov     rcx, rax
0x1801c77ec  cmp     [rdi+0C5h], r13b
0x1801c77f3  jnz     short loc_1801C7814
0x1801c77f5  cmp     [r14+8], r13d
0x1801c77f9  jnz     short loc_1801C7814
0x1801c77fb  test    rax, rax
0x1801c77fe  jz      short loc_1801C7814
0x1801c7800  mov     rax, [rdi+20h]
0x1801c7804  mov     rax, [rax+38h]
0x1801c7808  cmp     [rcx+60h], rax
0x1801c780c  mov     eax, 1
0x1801c7811  cmovz   esi, eax
0x1801c7814  cmp     [rdi+67h], r13b
0x1801c7818  jnz     short loc_1801C7886
0x1801c781a  lea     r9, aTrigger; "trigger"
0x1801c7821  mov     [rsp+0D8h+var_B8], r12
0x1801c7826  mov     r8d, esi
0x1801c7829  lea     rcx, [rsp+0D8h+var_98]
0x1801c782e  mov     rdx, rbx
0x1801c7831  call    sqlite3FixInit
0x1801c7836  mov     rdx, rbp
0x1801c7839  lea     rcx, [rsp+0D8h+var_98]
0x1801c783e  call    sqlite3FixSrcList
0x1801c7843  test    eax, eax
0x1801c7845  jnz     short loc_1801C7886
0x1801c7847  mov     rdx, rbp
0x1801c784a  mov     rcx, rbx
0x1801c784d  call    sqlite3SrcListLookup
0x1801c7852  mov     r14, rax
0x1801c7855  test    rax, rax
0x1801c7858  jz      short loc_1801C7873
0x1801c785a  cmp     byte ptr [rax+3Fh], 1
0x1801c785e  jnz     loc_1801C78F1
0x1801c7864  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x1801c786b  mov     rcx, rbx
0x1801c786e  call    sqlite3ErrorMsg
0x1801c7873  mov     eax, 1
0x1801c7878  cmp     [rdi+0C4h], al
0x1801c787e  jnz     short loc_1801C7886
0x1801c7880  or      [rdi+0C8h], eax
0x1801c7886  mov     rdx, [rsp+0D8h+arg_0]
0x1801c788e  mov     rcx, rdi
0x1801c7891  call    sqlite3DbFree
0x1801c7896  mov     rdx, rbp
0x1801c7899  mov     rcx, rdi
0x1801c789c  call    sqlite3SrcListDelete
0x1801c78a1  mov     rdx, [rsp+0D8h+arg_28]
0x1801c78a9  mov     rcx, rdi
0x1801c78ac  call    sqlite3IdListDelete
0x1801c78b1  mov     rdx, [rsp+0D8h+arg_38]
0x1801c78b9  mov     rcx, rdi
0x1801c78bc  call    sqlite3ExprDeleteGeneric
0x1801c78c1  cmp     qword ptr [rbx+170h], 0
0x1801c78c9  jnz     short loc_1801C78D6
0x1801c78cb  mov     rdx, r15
0x1801c78ce  mov     rcx, rdi
0x1801c78d1  call    sqlite3DeleteTrigger
0x1801c78d6  mov     rbx, [rsp+0D8h+arg_8]
0x1801c78de  add     rsp, 0A0h
0x1801c78e5  pop     r15
0x1801c78e7  pop     r14
0x1801c78e9  pop     r13
0x1801c78eb  pop     r12
0x1801c78ed  pop     rdi
0x1801c78ee  pop     rsi
0x1801c78ef  pop     rbp
0x1801c78f0  retn
0x1801c78f1  test    dword ptr [rax+30h], 1000h
0x1801c78f8  jz      short loc_1801C7912
0x1801c78fa  mov     rcx, rdi
0x1801c78fd  call    sqlite3ReadOnlyShadowTables
0x1801c7902  test    eax, eax
0x1801c7904  jz      short loc_1801C7912
0x1801c7906  lea     rdx, aCannotCreateTr_1; "cannot create triggers on shadow tables"
0x1801c790d  jmp     loc_1801C786B
0x1801c7912  mov     rdx, r12
0x1801c7915  mov     rcx, rdi
0x1801c7918  call    sqlite3NameFromToken
0x1801c791d  mov     [rsp+0D8h+arg_0], rax
0x1801c7925  test    rax, rax
0x1801c7928  jz      loc_1801C7886
0x1801c792e  mov     r9, [r14]
0x1801c7931  lea     r8, aTrigger; "trigger"
0x1801c7938  mov     rdx, rax
0x1801c793b  mov     rcx, rbx
0x1801c793e  call    sqlite3CheckObjectName
0x1801c7943  test    eax, eax
0x1801c7945  jnz     loc_1801C7886
0x1801c794b  cmp     byte ptr [rbx+134h], 2
0x1801c7952  jnb     short loc_1801C79AA
0x1801c7954  mov     rax, [rdi+20h]
0x1801c7958  xor     r8d, r8d
0x1801c795b  mov     rdx, [rsp+0D8h+arg_0]
0x1801c7963  mov     ecx, esi
0x1801c7965  shl     rcx, 5
0x1801c7969  mov     rcx, [rcx+rax+18h]
0x1801c796e  add     rcx, 38h ; '8'
0x1801c7972  call    findElementWithHash
0x1801c7977  cmp     [rax+10h], r13
0x1801c797b  jz      short loc_1801C79AA
0x1801c797d  mov     rcx, rbx
0x1801c7980  cmp     [rsp+0D8h+arg_48], r13d
0x1801c7988  jnz     short loc_1801C799E
0x1801c798a  mov     r8, r12
0x1801c798d  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x1801c7994  call    sqlite3ErrorMsg
0x1801c7999  jmp     loc_1801C7886
0x1801c799e  mov     edx, esi
0x1801c79a0  call    sqlite3CodeVerifySchema
0x1801c79a5  jmp     loc_1801C7886
0x1801c79aa  mov     rcx, [r14]
0x1801c79ad  lea     rdx, aSqlite_0; "sqlite_"
0x1801c79b4  mov     r13d, 7
0x1801c79ba  mov     r8d, r13d
0x1801c79bd  call    sqlite3_strnicmp
0x1801c79c2  test    eax, eax
0x1801c79c4  jnz     short loc_1801C79D2
0x1801c79c6  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x1801c79cd  jmp     loc_1801C7776
0x1801c79d2  cmp     byte ptr [r14+3Fh], 2
0x1801c79d7  jnz     short loc_1801C7A12
0x1801c79d9  mov     eax, [rsp+0D8h+arg_18]
0x1801c79e0  cmp     eax, 41h ; 'A'
0x1801c79e3  jz      short loc_1801C7A34
0x1801c79e5  cmp     eax, 21h ; '!'
0x1801c79e8  lea     rcx, aAfter; "AFTER"
0x1801c79ef  lea     r8, aBefore; "BEFORE"
0x1801c79f6  cmovnz  r8, rcx
0x1801c79fa  lea     r9, [rbp+8]
0x1801c79fe  mov     rcx, rbx
0x1801c7a01  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x1801c7a08  call    sqlite3ErrorMsg
0x1801c7a0d  jmp     loc_1801C7873
0x1801c7a12  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x1801c7a1a  jnz     short loc_1801C7A34
0x1801c7a1c  lea     r8, [rbp+8]
0x1801c7a20  mov     rcx, rbx
0x1801c7a23  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x1801c7a2a  call    sqlite3ErrorMsg
0x1801c7a2f  jmp     loc_1801C7873
0x1801c7a34  cmp     byte ptr [rbx+134h], 2
0x1801c7a3b  jnb     loc_1801C7AEC
0x1801c7a41  mov     rdx, [r14+60h]
0x1801c7a45  mov     rcx, rdi
0x1801c7a48  call    sqlite3SchemaToIndex
0x1801c7a4d  mov     rdx, [rdi+20h]
0x1801c7a51  mov     r8d, [rsp+0D8h+arg_40]
0x1801c7a59  movsxd  r12, eax
0x1801c7a5c  mov     rcx, r12
0x1801c7a5f  shl     rcx, 5
0x1801c7a63  mov     rax, [rcx+rdx]
0x1801c7a67  mov     [rsp+0D8h+var_A8], rax
0x1801c7a6c  test    r8d, r8d
0x1801c7a6f  jz      short loc_1801C7A77
0x1801c7a71  mov     rcx, [rdx+20h]
0x1801c7a75  jmp     short loc_1801C7A7A
0x1801c7a77  mov     rcx, rax
0x1801c7a7a  cmp     r12d, 1
0x1801c7a7e  jz      short loc_1801C7A85
0x1801c7a80  test    r8d, r8d
0x1801c7a83  jz      short loc_1801C7A8B
0x1801c7a85  mov     r13d, 5
0x1801c7a8b  mov     r9, [r14]
0x1801c7a8e  mov     edx, r13d
0x1801c7a91  mov     r8, [rsp+0D8h+arg_0]
0x1801c7a99  mov     [rsp+0D8h+var_B8], rcx
0x1801c7a9e  mov     rcx, rbx
0x1801c7aa1  call    sqlite3AuthCheck
0x1801c7aa6  test    eax, eax
0x1801c7aa8  jnz     loc_1801C7886
0x1801c7aae  mov     r13d, 1
0x1801c7ab4  lea     rax, aSqliteMaster; "sqlite_master"
0x1801c7abb  cmp     r12d, r13d
0x1801c7abe  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1801c7ac5  mov     rcx, rbx
0x1801c7ac8  cmovnz  r8, rax
0x1801c7acc  mov     rax, [rsp+0D8h+var_A8]
0x1801c7ad1  xor     r9d, r9d
0x1801c7ad4  mov     [rsp+0D8h+var_B8], rax
0x1801c7ad9  lea     edx, [r13+11h]
0x1801c7add  call    sqlite3AuthCheck
0x1801c7ae2  test    eax, eax
0x1801c7ae4  jnz     loc_1801C7886
0x1801c7aea  jmp     short loc_1801C7AF2
0x1801c7aec  mov     r13d, 1
0x1801c7af2  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x1801c7afa  mov     r12d, 21h ; '!'
0x1801c7b00  mov     edx, 48h ; 'H'
0x1801c7b05  mov     rcx, rdi
0x1801c7b08  cmovnz  r12d, [rsp+0D8h+arg_18]
0x1801c7b11  call    sqlite3DbMallocZero
0x1801c7b16  mov     r15, rax
0x1801c7b19  test    rax, rax
0x1801c7b1c  jz      loc_1801C7886
0x1801c7b22  mov     rax, [rsp+0D8h+arg_0]
0x1801c7b2a  mov     rcx, rdi
0x1801c7b2d  mov     [r15], rax
0x1801c7b30  mov     rdx, [rbp+18h]
0x1801c7b34  mov     [rsp+0D8h+arg_0], 0
0x1801c7b40  call    sqlite3DbStrDup
0x1801c7b45  mov     [r15+8], rax
0x1801c7b49  mov     rcx, [rdi+20h]
0x1801c7b4d  mov     edx, esi
0x1801c7b4f  shl     rdx, 5
0x1801c7b53  cmp     r12d, 21h ; '!'
0x1801c7b57  mov     rdx, [rdx+rcx+18h]
0x1801c7b5c  mov     [r15+28h], rdx
0x1801c7b60  mov     rcx, [r14+60h]
0x1801c7b64  mov     [r15+30h], rcx
0x1801c7b68  mov     cl, [rsp+0D8h+arg_20]
0x1801c7b6f  mov     [r15+10h], cl
0x1801c7b73  setnz   cl
0x1801c7b76  add     cl, r13b
0x1801c7b79  mov     [r15+11h], cl
0x1801c7b7d  cmp     byte ptr [rbx+134h], 2
0x1801c7b84  jb      short loc_1801C7BAB
0x1801c7b86  mov     r8, [rbp+18h]
0x1801c7b8a  mov     rdx, rax
0x1801c7b8d  mov     r9, [rsp+0D8h+arg_38]
0x1801c7b95  mov     rcx, rbx
0x1801c7b98  call    sqlite3RenameTokenRemap
0x1801c7b9d  mov     [rsp+0D8h+arg_38], 0
0x1801c7ba9  jmp     short loc_1801C7BC1
0x1801c7bab  mov     rdx, [rsp+0D8h+arg_38]
0x1801c7bb3  mov     r8d, r13d
0x1801c7bb6  mov     rcx, rdi
0x1801c7bb9  call    sqlite3ExprDup
0x1801c7bbe  mov     r9, rax
0x1801c7bc1  mov     rax, [rsp+0D8h+arg_28]
0x1801c7bc9  mov     [r15+18h], r9
0x1801c7bcd  mov     [r15+20h], rax
0x1801c7bd1  mov     [rbx+170h], r15
0x1801c7bd8  mov     [rsp+0D8h+arg_28], 0
0x1801c7be4  jmp     loc_1801C7886
```
