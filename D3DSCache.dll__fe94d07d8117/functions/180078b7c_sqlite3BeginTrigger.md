# sqlite3BeginTrigger

- ea: `0x180078b7c`
- end: `0x18007905d`
- name: `sqlite3BeginTrigger`
- size: `1249`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path`

## callers

- `0x18001bc30`

## callees

- `0x180014464`
- `0x180015e80`
- `0x1800283fc`
- `0x18002b840`
- `0x18002b8ec`
- `0x1800367a0`
- `0x180037954`
- `0x180038ba0`
- `0x18003ceec`
- `0x18003e5b4`
- `0x18003f960`
- `0x18003ff28`
- `0x18004002c`
- `0x180042130`
- `0x180042bb0`
- `0x180042c38`
- `0x180045374`
- `0x180078b7c`
- `0x18007e48c`
- `0x180081b28`
- `0x180081bac`
- `0x180083d6c`
- `0x180088ee0`
- `0x1800899a0`

## string_xrefs

- `0x180078f32`: `sqlite_temp_master`
- `0x180078be3`: `temporary trigger may not have qualified name`
- `0x180078cd8`: `cannot create triggers on virtual tables`
- `0x180078d7a`: `cannot create triggers on shadow tables`
- `0x180078e01`: `trigger %T already exists`
- `0x180078e3a`: `cannot create trigger on system table`
- `0x180078e75`: `cannot create %s trigger on view: %S`
- `0x180078e97`: `cannot create INSTEAD OF trigger on table: %S`

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
0x180078b7c  mov     [rsp+arg_8], rbx
0x180078b81  mov     [rsp+arg_18], r9d
0x180078b86  push    rbp
0x180078b87  push    rsi
0x180078b88  push    rdi
0x180078b89  push    r12
0x180078b8b  push    r13
0x180078b8d  push    r14
0x180078b8f  push    r15
0x180078b91  sub     rsp, 0A0h
0x180078b98  mov     rdi, [rcx]
0x180078b9b  xor     r13d, r13d
0x180078b9e  mov     r14, r8
0x180078ba1  mov     [rsp+0D8h+arg_0], r13
0x180078ba9  mov     r12, rdx
0x180078bac  mov     [rsp+0D8h+var_A8], r13
0x180078bb1  mov     rbx, rcx
0x180078bb4  xor     edx, edx; Val
0x180078bb6  lea     r8d, [r13+60h]; Size
0x180078bba  mov     r15d, r13d
0x180078bbd  lea     rcx, [rsp+0D8h+var_98]; void *
0x180078bc2  call    memset_0
0x180078bc7  lea     eax, [r13+1]
0x180078bcb  mov     rbp, [rsp+0D8h+arg_30]
0x180078bd3  cmp     [rsp+0D8h+arg_40], r13d
0x180078bdb  jz      short loc_180078BFB
0x180078bdd  cmp     [r14+8], r13d
0x180078be1  jbe     short loc_180078BF7
0x180078be3  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x180078bea  mov     rcx, rbx
0x180078bed  call    sqlite3ErrorMsg
0x180078bf2  jmp     loc_180078CFA
0x180078bf7  mov     esi, eax
0x180078bf9  jmp     short loc_180078C22
0x180078bfb  lea     r9, [rsp+0D8h+var_A8]
0x180078c00  mov     r8, r14
0x180078c03  mov     rdx, r12
0x180078c06  mov     rcx, rbx
0x180078c09  call    sqlite3TwoPartName
0x180078c0e  mov     esi, eax
0x180078c10  test    eax, eax
0x180078c12  js      loc_180078CFA
0x180078c18  mov     r12, [rsp+0D8h+var_A8]
0x180078c1d  mov     eax, 1
0x180078c22  test    rbp, rbp
0x180078c25  jz      loc_180078CFA
0x180078c2b  cmp     [rdi+67h], r13b
0x180078c2f  jnz     loc_180078CFA
0x180078c35  cmp     [rdi+0C5h], r13b
0x180078c3c  jz      short loc_180078C52
0x180078c3e  cmp     esi, eax
0x180078c40  jz      short loc_180078C52
0x180078c42  mov     rdx, [rbp+10h]
0x180078c46  mov     rcx, rdi
0x180078c49  call    sqlite3DbFree
0x180078c4e  mov     [rbp+10h], r13
0x180078c52  mov     rdx, rbp
0x180078c55  mov     rcx, rbx
0x180078c58  call    sqlite3SrcListLookup
0x180078c5d  mov     rcx, rax
0x180078c60  cmp     [rdi+0C5h], r13b
0x180078c67  jnz     short loc_180078C88
0x180078c69  cmp     [r14+8], r13d
0x180078c6d  jnz     short loc_180078C88
0x180078c6f  test    rax, rax
0x180078c72  jz      short loc_180078C88
0x180078c74  mov     rax, [rdi+20h]
0x180078c78  mov     rax, [rax+38h]
0x180078c7c  cmp     [rcx+60h], rax
0x180078c80  mov     eax, 1
0x180078c85  cmovz   esi, eax
0x180078c88  cmp     [rdi+67h], r13b
0x180078c8c  jnz     short loc_180078CFA
0x180078c8e  lea     r9, aTrigger; "trigger"
0x180078c95  mov     [rsp+0D8h+var_B8], r12
0x180078c9a  mov     r8d, esi
0x180078c9d  lea     rcx, [rsp+0D8h+var_98]
0x180078ca2  mov     rdx, rbx
0x180078ca5  call    sqlite3FixInit
0x180078caa  mov     rdx, rbp
0x180078cad  lea     rcx, [rsp+0D8h+var_98]
0x180078cb2  call    sqlite3FixSrcList
0x180078cb7  test    eax, eax
0x180078cb9  jnz     short loc_180078CFA
0x180078cbb  mov     rdx, rbp
0x180078cbe  mov     rcx, rbx
0x180078cc1  call    sqlite3SrcListLookup
0x180078cc6  mov     r14, rax
0x180078cc9  test    rax, rax
0x180078ccc  jz      short loc_180078CE7
0x180078cce  cmp     byte ptr [rax+3Fh], 1
0x180078cd2  jnz     loc_180078D65
0x180078cd8  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x180078cdf  mov     rcx, rbx
0x180078ce2  call    sqlite3ErrorMsg
0x180078ce7  mov     eax, 1
0x180078cec  cmp     [rdi+0C4h], al
0x180078cf2  jnz     short loc_180078CFA
0x180078cf4  or      [rdi+0C8h], eax
0x180078cfa  mov     rdx, [rsp+0D8h+arg_0]
0x180078d02  mov     rcx, rdi
0x180078d05  call    sqlite3DbFree
0x180078d0a  mov     rdx, rbp
0x180078d0d  mov     rcx, rdi
0x180078d10  call    sqlite3SrcListDelete
0x180078d15  mov     rdx, [rsp+0D8h+arg_28]
0x180078d1d  mov     rcx, rdi
0x180078d20  call    sqlite3IdListDelete
0x180078d25  mov     rdx, [rsp+0D8h+arg_38]
0x180078d2d  mov     rcx, rdi
0x180078d30  call    sqlite3ExprDeleteGeneric
0x180078d35  cmp     qword ptr [rbx+170h], 0
0x180078d3d  jnz     short loc_180078D4A
0x180078d3f  mov     rdx, r15
0x180078d42  mov     rcx, rdi
0x180078d45  call    sqlite3DeleteTrigger
0x180078d4a  mov     rbx, [rsp+0D8h+arg_8]
0x180078d52  add     rsp, 0A0h
0x180078d59  pop     r15
0x180078d5b  pop     r14
0x180078d5d  pop     r13
0x180078d5f  pop     r12
0x180078d61  pop     rdi
0x180078d62  pop     rsi
0x180078d63  pop     rbp
0x180078d64  retn
0x180078d65  test    dword ptr [rax+30h], 1000h
0x180078d6c  jz      short loc_180078D86
0x180078d6e  mov     rcx, rdi
0x180078d71  call    sqlite3ReadOnlyShadowTables
0x180078d76  test    eax, eax
0x180078d78  jz      short loc_180078D86
0x180078d7a  lea     rdx, aCannotCreateTr_1; "cannot create triggers on shadow tables"
0x180078d81  jmp     loc_180078CDF
0x180078d86  mov     rdx, r12
0x180078d89  mov     rcx, rdi
0x180078d8c  call    sqlite3NameFromToken
0x180078d91  mov     [rsp+0D8h+arg_0], rax
0x180078d99  test    rax, rax
0x180078d9c  jz      loc_180078CFA
0x180078da2  mov     r9, [r14]
0x180078da5  lea     r8, aTrigger; "trigger"
0x180078dac  mov     rdx, rax
0x180078daf  mov     rcx, rbx
0x180078db2  call    sqlite3CheckObjectName
0x180078db7  test    eax, eax
0x180078db9  jnz     loc_180078CFA
0x180078dbf  cmp     byte ptr [rbx+134h], 2
0x180078dc6  jnb     short loc_180078E1E
0x180078dc8  mov     rax, [rdi+20h]
0x180078dcc  xor     r8d, r8d
0x180078dcf  mov     rdx, [rsp+0D8h+arg_0]
0x180078dd7  mov     ecx, esi
0x180078dd9  shl     rcx, 5
0x180078ddd  mov     rcx, [rcx+rax+18h]
0x180078de2  add     rcx, 38h ; '8'
0x180078de6  call    findElementWithHash
0x180078deb  cmp     [rax+10h], r13
0x180078def  jz      short loc_180078E1E
0x180078df1  mov     rcx, rbx
0x180078df4  cmp     [rsp+0D8h+arg_48], r13d
0x180078dfc  jnz     short loc_180078E12
0x180078dfe  mov     r8, r12
0x180078e01  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x180078e08  call    sqlite3ErrorMsg
0x180078e0d  jmp     loc_180078CFA
0x180078e12  mov     edx, esi
0x180078e14  call    sqlite3CodeVerifySchema
0x180078e19  jmp     loc_180078CFA
0x180078e1e  mov     rcx, [r14]
0x180078e21  lea     rdx, aSqlite_0; "sqlite_"
0x180078e28  mov     r13d, 7
0x180078e2e  mov     r8d, r13d
0x180078e31  call    sqlite3_strnicmp
0x180078e36  test    eax, eax
0x180078e38  jnz     short loc_180078E46
0x180078e3a  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x180078e41  jmp     loc_180078BEA
0x180078e46  cmp     byte ptr [r14+3Fh], 2
0x180078e4b  jnz     short loc_180078E86
0x180078e4d  mov     eax, [rsp+0D8h+arg_18]
0x180078e54  cmp     eax, 41h ; 'A'
0x180078e57  jz      short loc_180078EA8
0x180078e59  cmp     eax, 21h ; '!'
0x180078e5c  lea     rcx, aAfter; "AFTER"
0x180078e63  lea     r8, aBefore; "BEFORE"
0x180078e6a  cmovnz  r8, rcx
0x180078e6e  lea     r9, [rbp+8]
0x180078e72  mov     rcx, rbx
0x180078e75  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x180078e7c  call    sqlite3ErrorMsg
0x180078e81  jmp     loc_180078CE7
0x180078e86  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180078e8e  jnz     short loc_180078EA8
0x180078e90  lea     r8, [rbp+8]
0x180078e94  mov     rcx, rbx
0x180078e97  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x180078e9e  call    sqlite3ErrorMsg
0x180078ea3  jmp     loc_180078CE7
0x180078ea8  cmp     byte ptr [rbx+134h], 2
0x180078eaf  jnb     loc_180078F60
0x180078eb5  mov     rdx, [r14+60h]
0x180078eb9  mov     rcx, rdi
0x180078ebc  call    sqlite3SchemaToIndex
0x180078ec1  mov     rdx, [rdi+20h]
0x180078ec5  mov     r8d, [rsp+0D8h+arg_40]
0x180078ecd  movsxd  r12, eax
0x180078ed0  mov     rcx, r12
0x180078ed3  shl     rcx, 5
0x180078ed7  mov     rax, [rcx+rdx]
0x180078edb  mov     [rsp+0D8h+var_A8], rax
0x180078ee0  test    r8d, r8d
0x180078ee3  jz      short loc_180078EEB
0x180078ee5  mov     rcx, [rdx+20h]
0x180078ee9  jmp     short loc_180078EEE
0x180078eeb  mov     rcx, rax
0x180078eee  cmp     r12d, 1
0x180078ef2  jz      short loc_180078EF9
0x180078ef4  test    r8d, r8d
0x180078ef7  jz      short loc_180078EFF
0x180078ef9  mov     r13d, 5
0x180078eff  mov     r9, [r14]
0x180078f02  mov     edx, r13d
0x180078f05  mov     r8, [rsp+0D8h+arg_0]
0x180078f0d  mov     [rsp+0D8h+var_B8], rcx
0x180078f12  mov     rcx, rbx
0x180078f15  call    sqlite3AuthCheck
0x180078f1a  test    eax, eax
0x180078f1c  jnz     loc_180078CFA
0x180078f22  mov     r13d, 1
0x180078f28  lea     rax, aSqliteMaster; "sqlite_master"
0x180078f2f  cmp     r12d, r13d
0x180078f32  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180078f39  mov     rcx, rbx
0x180078f3c  cmovnz  r8, rax
0x180078f40  mov     rax, [rsp+0D8h+var_A8]
0x180078f45  xor     r9d, r9d
0x180078f48  mov     [rsp+0D8h+var_B8], rax
0x180078f4d  lea     edx, [r13+11h]
0x180078f51  call    sqlite3AuthCheck
0x180078f56  test    eax, eax
0x180078f58  jnz     loc_180078CFA
0x180078f5e  jmp     short loc_180078F66
0x180078f60  mov     r13d, 1
0x180078f66  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180078f6e  mov     r12d, 21h ; '!'
0x180078f74  mov     edx, 48h ; 'H'
0x180078f79  mov     rcx, rdi
0x180078f7c  cmovnz  r12d, [rsp+0D8h+arg_18]
0x180078f85  call    sqlite3DbMallocZero
0x180078f8a  mov     r15, rax
0x180078f8d  test    rax, rax
0x180078f90  jz      loc_180078CFA
0x180078f96  mov     rax, [rsp+0D8h+arg_0]
0x180078f9e  mov     rcx, rdi
0x180078fa1  mov     [r15], rax
0x180078fa4  mov     rdx, [rbp+18h]
0x180078fa8  mov     [rsp+0D8h+arg_0], 0
0x180078fb4  call    sqlite3DbStrDup
0x180078fb9  mov     [r15+8], rax
0x180078fbd  mov     rcx, [rdi+20h]
0x180078fc1  mov     edx, esi
0x180078fc3  shl     rdx, 5
0x180078fc7  cmp     r12d, 21h ; '!'
0x180078fcb  mov     rdx, [rdx+rcx+18h]
0x180078fd0  mov     [r15+28h], rdx
0x180078fd4  mov     rcx, [r14+60h]
0x180078fd8  mov     [r15+30h], rcx
0x180078fdc  mov     cl, [rsp+0D8h+arg_20]
0x180078fe3  mov     [r15+10h], cl
0x180078fe7  setnz   cl
0x180078fea  add     cl, r13b
0x180078fed  mov     [r15+11h], cl
0x180078ff1  cmp     byte ptr [rbx+134h], 2
0x180078ff8  jb      short loc_18007901F
0x180078ffa  mov     r8, [rbp+18h]
0x180078ffe  mov     rdx, rax
0x180079001  mov     r9, [rsp+0D8h+arg_38]
0x180079009  mov     rcx, rbx
0x18007900c  call    sqlite3RenameTokenRemap
0x180079011  mov     [rsp+0D8h+arg_38], 0
0x18007901d  jmp     short loc_180079035
0x18007901f  mov     rdx, [rsp+0D8h+arg_38]
0x180079027  mov     r8d, r13d
0x18007902a  mov     rcx, rdi
0x18007902d  call    sqlite3ExprDup
0x180079032  mov     r9, rax
0x180079035  mov     rax, [rsp+0D8h+arg_28]
0x18007903d  mov     [r15+18h], r9
0x180079041  mov     [r15+20h], rax
0x180079045  mov     [rbx+170h], r15
0x18007904c  mov     [rsp+0D8h+arg_28], 0
0x180079058  jmp     loc_180078CFA
```
