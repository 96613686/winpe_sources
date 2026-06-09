# sqlite3BeginTrigger

- ea: `0x18008fcd0`
- end: `0x1800901b6`
- name: `sqlite3BeginTrigger`
- size: `1254`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `reparse_path`

## callers

- `0x18000213c`

## callees

- `0x180009760`
- `0x180009ef0`
- `0x18000a754`
- `0x18000e818`
- `0x180011bcc`
- `0x18001b16c`
- `0x18001bb70`
- `0x18001f0f0`
- `0x18001f19c`
- `0x18001f418`
- `0x18001f530`
- `0x18003d380`
- `0x18003d760`
- `0x180041d10`
- `0x18004b010`
- `0x18005166c`
- `0x1800516e4`
- `0x1800589fc`
- `0x18005d2d4`
- `0x18005df58`
- `0x180061d60`
- `0x180062a94`
- `0x180078968`
- `0x18008fcd0`

## string_xrefs

- `0x18009008b`: `sqlite_temp_master`
- `0x18008fd37`: `temporary trigger may not have qualified name`
- `0x18008fe2c`: `cannot create triggers on virtual tables`
- `0x18008fed3`: `cannot create triggers on shadow tables`
- `0x18008ff5a`: `trigger %T already exists`
- `0x18008ff93`: `cannot create trigger on system table`
- `0x18008ffce`: `cannot create %s trigger on view: %S`
- `0x18008fff0`: `cannot create INSTEAD OF trigger on table: %S`

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
  unsigned int v15; // ebp
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
          goto LABEL_59;
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
LABEL_59:
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
                sqlite3RenameTokenRemap(a1, v30);
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
  result = sqlite3IdListDelete(v10, a6);
  if ( a8 )
    result = sqlite3ExprDeleteNN(v10);
  if ( !a1[46] )
    return sqlite3DeleteTrigger(v10, v14);
  return result;
}

```

## disassembly

```asm
0x18008fcd0  mov     [rsp+arg_8], rbx
0x18008fcd5  mov     [rsp+arg_18], r9d
0x18008fcda  push    rbp
0x18008fcdb  push    rsi
0x18008fcdc  push    rdi
0x18008fcdd  push    r12
0x18008fcdf  push    r13
0x18008fce1  push    r14
0x18008fce3  push    r15
0x18008fce5  sub     rsp, 0A0h
0x18008fcec  mov     rdi, [rcx]
0x18008fcef  xor     r13d, r13d
0x18008fcf2  mov     r14, r8
0x18008fcf5  mov     [rsp+0D8h+arg_0], r13
0x18008fcfd  mov     r12, rdx
0x18008fd00  mov     [rsp+0D8h+var_A8], r13
0x18008fd05  mov     rbx, rcx
0x18008fd08  xor     edx, edx; Val
0x18008fd0a  lea     r8d, [r13+60h]; Size
0x18008fd0e  mov     r15d, r13d
0x18008fd11  lea     rcx, [rsp+0D8h+var_98]; void *
0x18008fd16  call    memset_0
0x18008fd1b  lea     eax, [r13+1]
0x18008fd1f  mov     rsi, [rsp+0D8h+arg_30]
0x18008fd27  cmp     [rsp+0D8h+arg_40], r13d
0x18008fd2f  jz      short loc_18008FD4F
0x18008fd31  cmp     [r14+8], r13d
0x18008fd35  jbe     short loc_18008FD4B
0x18008fd37  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x18008fd3e  mov     rcx, rbx
0x18008fd41  call    sqlite3ErrorMsg
0x18008fd46  jmp     loc_18008FE4E
0x18008fd4b  mov     ebp, eax
0x18008fd4d  jmp     short loc_18008FD76
0x18008fd4f  lea     r9, [rsp+0D8h+var_A8]
0x18008fd54  mov     r8, r14
0x18008fd57  mov     rdx, r12
0x18008fd5a  mov     rcx, rbx
0x18008fd5d  call    sqlite3TwoPartName
0x18008fd62  mov     ebp, eax
0x18008fd64  test    eax, eax
0x18008fd66  js      loc_18008FE4E
0x18008fd6c  mov     r12, [rsp+0D8h+var_A8]
0x18008fd71  mov     eax, 1
0x18008fd76  test    rsi, rsi
0x18008fd79  jz      loc_18008FE4E
0x18008fd7f  cmp     [rdi+67h], r13b
0x18008fd83  jnz     loc_18008FE4E
0x18008fd89  cmp     [rdi+0C5h], r13b
0x18008fd90  jz      short loc_18008FDA6
0x18008fd92  cmp     ebp, eax
0x18008fd94  jz      short loc_18008FDA6
0x18008fd96  mov     rdx, [rsi+10h]
0x18008fd9a  mov     rcx, rdi
0x18008fd9d  call    sqlite3DbFree
0x18008fda2  mov     [rsi+10h], r13
0x18008fda6  mov     rdx, rsi
0x18008fda9  mov     rcx, rbx
0x18008fdac  call    sqlite3SrcListLookup
0x18008fdb1  mov     rcx, rax
0x18008fdb4  cmp     [rdi+0C5h], r13b
0x18008fdbb  jnz     short loc_18008FDDC
0x18008fdbd  cmp     [r14+8], r13d
0x18008fdc1  jnz     short loc_18008FDDC
0x18008fdc3  test    rax, rax
0x18008fdc6  jz      short loc_18008FDDC
0x18008fdc8  mov     rax, [rdi+20h]
0x18008fdcc  mov     rax, [rax+38h]
0x18008fdd0  cmp     [rcx+60h], rax
0x18008fdd4  mov     eax, 1
0x18008fdd9  cmovz   ebp, eax
0x18008fddc  cmp     [rdi+67h], r13b
0x18008fde0  jnz     short loc_18008FE4E
0x18008fde2  lea     r9, aTrigger; "trigger"
0x18008fde9  mov     [rsp+0D8h+var_B8], r12
0x18008fdee  mov     r8d, ebp
0x18008fdf1  lea     rcx, [rsp+0D8h+var_98]
0x18008fdf6  mov     rdx, rbx
0x18008fdf9  call    sqlite3FixInit
0x18008fdfe  mov     rdx, rsi
0x18008fe01  lea     rcx, [rsp+0D8h+var_98]
0x18008fe06  call    sqlite3FixSrcList
0x18008fe0b  test    eax, eax
0x18008fe0d  jnz     short loc_18008FE4E
0x18008fe0f  mov     rdx, rsi
0x18008fe12  mov     rcx, rbx
0x18008fe15  call    sqlite3SrcListLookup
0x18008fe1a  mov     r14, rax
0x18008fe1d  test    rax, rax
0x18008fe20  jz      short loc_18008FE3B
0x18008fe22  cmp     byte ptr [rax+3Fh], 1
0x18008fe26  jnz     loc_18008FEBE
0x18008fe2c  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x18008fe33  mov     rcx, rbx
0x18008fe36  call    sqlite3ErrorMsg
0x18008fe3b  mov     eax, 1
0x18008fe40  cmp     [rdi+0C4h], al
0x18008fe46  jnz     short loc_18008FE4E
0x18008fe48  or      [rdi+0C8h], eax
0x18008fe4e  mov     rdx, [rsp+0D8h+arg_0]
0x18008fe56  mov     rcx, rdi
0x18008fe59  call    sqlite3DbFree
0x18008fe5e  mov     rdx, rsi
0x18008fe61  mov     rcx, rdi
0x18008fe64  call    sqlite3SrcListDelete
0x18008fe69  mov     rdx, [rsp+0D8h+arg_28]
0x18008fe71  mov     rcx, rdi
0x18008fe74  call    sqlite3IdListDelete
0x18008fe79  mov     rdx, [rsp+0D8h+arg_38]
0x18008fe81  test    rdx, rdx
0x18008fe84  jz      short loc_18008FE8E
0x18008fe86  mov     rcx, rdi
0x18008fe89  call    sqlite3ExprDeleteNN
0x18008fe8e  cmp     qword ptr [rbx+170h], 0
0x18008fe96  jnz     short loc_18008FEA3
0x18008fe98  mov     rdx, r15
0x18008fe9b  mov     rcx, rdi
0x18008fe9e  call    sqlite3DeleteTrigger
0x18008fea3  mov     rbx, [rsp+0D8h+arg_8]
0x18008feab  add     rsp, 0A0h
0x18008feb2  pop     r15
0x18008feb4  pop     r14
0x18008feb6  pop     r13
0x18008feb8  pop     r12
0x18008feba  pop     rdi
0x18008febb  pop     rsi
0x18008febc  pop     rbp
0x18008febd  retn
0x18008febe  test    dword ptr [rax+30h], 1000h
0x18008fec5  jz      short loc_18008FEDF
0x18008fec7  mov     rcx, rdi
0x18008feca  call    sqlite3ReadOnlyShadowTables
0x18008fecf  test    eax, eax
0x18008fed1  jz      short loc_18008FEDF
0x18008fed3  lea     rdx, aCannotCreateTr_1; "cannot create triggers on shadow tables"
0x18008feda  jmp     loc_18008FE33
0x18008fedf  mov     rdx, r12
0x18008fee2  mov     rcx, rdi
0x18008fee5  call    sqlite3NameFromToken
0x18008feea  mov     [rsp+0D8h+arg_0], rax
0x18008fef2  test    rax, rax
0x18008fef5  jz      loc_18008FE4E
0x18008fefb  mov     r9, [r14]
0x18008fefe  lea     r8, aTrigger; "trigger"
0x18008ff05  mov     rdx, rax
0x18008ff08  mov     rcx, rbx
0x18008ff0b  call    sqlite3CheckObjectName
0x18008ff10  test    eax, eax
0x18008ff12  jnz     loc_18008FE4E
0x18008ff18  cmp     byte ptr [rbx+134h], 2
0x18008ff1f  jnb     short loc_18008FF77
0x18008ff21  mov     rax, [rdi+20h]
0x18008ff25  xor     r8d, r8d
0x18008ff28  mov     rdx, [rsp+0D8h+arg_0]
0x18008ff30  mov     ecx, ebp
0x18008ff32  shl     rcx, 5
0x18008ff36  mov     rcx, [rcx+rax+18h]
0x18008ff3b  add     rcx, 38h ; '8'
0x18008ff3f  call    findElementWithHash
0x18008ff44  cmp     [rax+10h], r13
0x18008ff48  jz      short loc_18008FF77
0x18008ff4a  mov     rcx, rbx
0x18008ff4d  cmp     [rsp+0D8h+arg_48], r13d
0x18008ff55  jnz     short loc_18008FF6B
0x18008ff57  mov     r8, r12
0x18008ff5a  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x18008ff61  call    sqlite3ErrorMsg
0x18008ff66  jmp     loc_18008FE4E
0x18008ff6b  mov     edx, ebp
0x18008ff6d  call    sqlite3CodeVerifySchema
0x18008ff72  jmp     loc_18008FE4E
0x18008ff77  mov     rcx, [r14]
0x18008ff7a  lea     rdx, aSqlite_0; "sqlite_"
0x18008ff81  mov     r13d, 7
0x18008ff87  mov     r8d, r13d
0x18008ff8a  call    sqlite3_strnicmp
0x18008ff8f  test    eax, eax
0x18008ff91  jnz     short loc_18008FF9F
0x18008ff93  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x18008ff9a  jmp     loc_18008FD3E
0x18008ff9f  cmp     byte ptr [r14+3Fh], 2
0x18008ffa4  jnz     short loc_18008FFDF
0x18008ffa6  mov     eax, [rsp+0D8h+arg_18]
0x18008ffad  cmp     eax, 41h ; 'A'
0x18008ffb0  jz      short loc_180090001
0x18008ffb2  cmp     eax, 21h ; '!'
0x18008ffb5  lea     rcx, aAfter; "AFTER"
0x18008ffbc  lea     r8, aBefore; "BEFORE"
0x18008ffc3  cmovnz  r8, rcx
0x18008ffc7  lea     r9, [rsi+8]
0x18008ffcb  mov     rcx, rbx
0x18008ffce  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x18008ffd5  call    sqlite3ErrorMsg
0x18008ffda  jmp     loc_18008FE3B
0x18008ffdf  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x18008ffe7  jnz     short loc_180090001
0x18008ffe9  lea     r8, [rsi+8]
0x18008ffed  mov     rcx, rbx
0x18008fff0  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x18008fff7  call    sqlite3ErrorMsg
0x18008fffc  jmp     loc_18008FE3B
0x180090001  cmp     byte ptr [rbx+134h], 2
0x180090008  jnb     loc_1800900B9
0x18009000e  mov     rdx, [r14+60h]
0x180090012  mov     rcx, rdi
0x180090015  call    sqlite3SchemaToIndex
0x18009001a  mov     rdx, [rdi+20h]
0x18009001e  mov     r8d, [rsp+0D8h+arg_40]
0x180090026  movsxd  r12, eax
0x180090029  mov     rcx, r12
0x18009002c  shl     rcx, 5
0x180090030  mov     rax, [rcx+rdx]
0x180090034  mov     [rsp+0D8h+var_A8], rax
0x180090039  test    r8d, r8d
0x18009003c  jz      short loc_180090044
0x18009003e  mov     rcx, [rdx+20h]
0x180090042  jmp     short loc_180090047
0x180090044  mov     rcx, rax
0x180090047  cmp     r12d, 1
0x18009004b  jz      short loc_180090052
0x18009004d  test    r8d, r8d
0x180090050  jz      short loc_180090058
0x180090052  mov     r13d, 5
0x180090058  mov     r9, [r14]
0x18009005b  mov     edx, r13d
0x18009005e  mov     r8, [rsp+0D8h+arg_0]
0x180090066  mov     [rsp+0D8h+var_B8], rcx
0x18009006b  mov     rcx, rbx
0x18009006e  call    sqlite3AuthCheck
0x180090073  test    eax, eax
0x180090075  jnz     loc_18008FE4E
0x18009007b  mov     r13d, 1
0x180090081  lea     rax, aSqliteMaster; "sqlite_master"
0x180090088  cmp     r12d, r13d
0x18009008b  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180090092  mov     rcx, rbx
0x180090095  cmovnz  r8, rax
0x180090099  mov     rax, [rsp+0D8h+var_A8]
0x18009009e  xor     r9d, r9d
0x1800900a1  mov     [rsp+0D8h+var_B8], rax
0x1800900a6  lea     edx, [r13+11h]
0x1800900aa  call    sqlite3AuthCheck
0x1800900af  test    eax, eax
0x1800900b1  jnz     loc_18008FE4E
0x1800900b7  jmp     short loc_1800900BF
0x1800900b9  mov     r13d, 1
0x1800900bf  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x1800900c7  mov     r12d, 21h ; '!'
0x1800900cd  mov     edx, 48h ; 'H'
0x1800900d2  mov     rcx, rdi
0x1800900d5  cmovnz  r12d, [rsp+0D8h+arg_18]
0x1800900de  call    sqlite3DbMallocZero
0x1800900e3  mov     r15, rax
0x1800900e6  test    rax, rax
0x1800900e9  jz      loc_18008FE4E
0x1800900ef  mov     rax, [rsp+0D8h+arg_0]
0x1800900f7  mov     rcx, rdi
0x1800900fa  mov     [r15], rax
0x1800900fd  mov     rdx, [rsi+18h]
0x180090101  mov     [rsp+0D8h+arg_0], 0
0x18009010d  call    sqlite3DbStrDup
0x180090112  mov     [r15+8], rax
0x180090116  mov     rcx, [rdi+20h]
0x18009011a  mov     edx, ebp
0x18009011c  shl     rdx, 5
0x180090120  cmp     r12d, 21h ; '!'
0x180090124  mov     rdx, [rdx+rcx+18h]
0x180090129  mov     [r15+28h], rdx
0x18009012d  mov     rcx, [r14+60h]
0x180090131  mov     [r15+30h], rcx
0x180090135  mov     cl, [rsp+0D8h+arg_20]
0x18009013c  mov     [r15+10h], cl
0x180090140  setnz   cl
0x180090143  add     cl, r13b
0x180090146  mov     [r15+11h], cl
0x18009014a  cmp     byte ptr [rbx+134h], 2
0x180090151  jb      short loc_180090178
0x180090153  mov     r8, [rsi+18h]
0x180090157  mov     rdx, rax
0x18009015a  mov     r9, [rsp+0D8h+arg_38]
0x180090162  mov     rcx, rbx
0x180090165  call    sqlite3RenameTokenRemap
0x18009016a  mov     [rsp+0D8h+arg_38], 0
0x180090176  jmp     short loc_18009018E
0x180090178  mov     rdx, [rsp+0D8h+arg_38]
0x180090180  mov     r8d, r13d
0x180090183  mov     rcx, rdi
0x180090186  call    sqlite3ExprDup
0x18009018b  mov     r9, rax
0x18009018e  mov     rax, [rsp+0D8h+arg_28]
0x180090196  mov     [r15+18h], r9
0x18009019a  mov     [r15+20h], rax
0x18009019e  mov     [rbx+170h], r15
0x1800901a5  mov     [rsp+0D8h+arg_28], 0
0x1800901b1  jmp     loc_18008FE4E
```
