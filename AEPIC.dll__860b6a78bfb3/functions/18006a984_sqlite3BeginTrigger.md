# sqlite3BeginTrigger

- ea: `0x18006a984`
- end: `0x18006ae44`
- name: `sqlite3BeginTrigger`
- size: `1216`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x1800be9b8`

## callees

- `0x180006938`
- `0x18004bfb0`
- `0x18006a3e8`
- `0x18006a984`
- `0x18006e6fc`
- `0x18006f6f4`
- `0x180071b80`
- `0x180071d64`
- `0x180071f14`
- `0x180072c0c`
- `0x180073d2c`
- `0x180076be0`
- `0x180076c90`
- `0x180079248`
- `0x1800792cc`
- `0x18007d388`
- `0x180080b40`
- `0x1800884cc`
- `0x180089c24`
- `0x18008c384`
- `0x18008c7a0`
- `0x18008dedc`
- `0x1800aa010`

## string_xrefs

- `0x18006ad19`: `sqlite_temp_master`
- `0x18006a9eb`: `temporary trigger may not have qualified name`
- `0x18006aae0`: `cannot create triggers on virtual tables`
- `0x18006ac21`: `cannot create trigger on system table`
- `0x18006abe8`: `trigger %T already exists`
- `0x18006ac7e`: `cannot create INSTEAD OF trigger on table: %S`
- `0x18006ac5c`: `cannot create %s trigger on view: %S`

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
        v20 = sqlite3NameFromToken(v10, a2);
        v34 = v20;
        if ( !v20 || (unsigned int)sqlite3CheckObjectName(a1, v20, "trigger", *v18) )
          goto LABEL_24;
        if ( *((_BYTE *)a1 + 300) < 2u
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
        if ( *((_BYTE *)a1 + 300) >= 2u )
          goto LABEL_54;
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
LABEL_54:
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
              if ( *((_BYTE *)a1 + 300) < 2u )
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
              a1[45] = v14;
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
  result = sqlite3ExprDelete(v10, a8);
  if ( !a1[45] )
    return sqlite3DeleteTrigger(v10, v14);
  return result;
}

```

## disassembly

```asm
0x18006a984  mov     [rsp+arg_8], rbx
0x18006a989  mov     [rsp+arg_18], r9d
0x18006a98e  push    rbp
0x18006a98f  push    rsi
0x18006a990  push    rdi
0x18006a991  push    r12
0x18006a993  push    r13
0x18006a995  push    r14
0x18006a997  push    r15
0x18006a999  sub     rsp, 0A0h
0x18006a9a0  mov     rdi, [rcx]
0x18006a9a3  xor     r13d, r13d
0x18006a9a6  mov     r14, r8
0x18006a9a9  mov     [rsp+0D8h+arg_0], r13
0x18006a9b1  mov     r12, rdx
0x18006a9b4  mov     [rsp+0D8h+var_A8], r13
0x18006a9b9  mov     rbx, rcx
0x18006a9bc  xor     edx, edx; Val
0x18006a9be  lea     r8d, [r13+60h]; Size
0x18006a9c2  mov     r15d, r13d
0x18006a9c5  lea     rcx, [rsp+0D8h+var_98]; void *
0x18006a9ca  call    memset_0
0x18006a9cf  lea     eax, [r13+1]
0x18006a9d3  mov     rsi, [rsp+0D8h+arg_30]
0x18006a9db  cmp     [rsp+0D8h+arg_40], r13d
0x18006a9e3  jz      short loc_18006AA03
0x18006a9e5  cmp     [r14+8], r13d
0x18006a9e9  jbe     short loc_18006A9FF
0x18006a9eb  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x18006a9f2  mov     rcx, rbx
0x18006a9f5  call    sqlite3ErrorMsg
0x18006a9fa  jmp     loc_18006AB02
0x18006a9ff  mov     ebp, eax
0x18006aa01  jmp     short loc_18006AA2A
0x18006aa03  lea     r9, [rsp+0D8h+var_A8]
0x18006aa08  mov     r8, r14
0x18006aa0b  mov     rdx, r12
0x18006aa0e  mov     rcx, rbx
0x18006aa11  call    sqlite3TwoPartName
0x18006aa16  mov     ebp, eax
0x18006aa18  test    eax, eax
0x18006aa1a  js      loc_18006AB02
0x18006aa20  mov     r12, [rsp+0D8h+var_A8]
0x18006aa25  mov     eax, 1
0x18006aa2a  test    rsi, rsi
0x18006aa2d  jz      loc_18006AB02
0x18006aa33  cmp     [rdi+67h], r13b
0x18006aa37  jnz     loc_18006AB02
0x18006aa3d  cmp     [rdi+0C5h], r13b
0x18006aa44  jz      short loc_18006AA5A
0x18006aa46  cmp     ebp, eax
0x18006aa48  jz      short loc_18006AA5A
0x18006aa4a  mov     rdx, [rsi+10h]
0x18006aa4e  mov     rcx, rdi
0x18006aa51  call    sqlite3DbFree
0x18006aa56  mov     [rsi+10h], r13
0x18006aa5a  mov     rdx, rsi
0x18006aa5d  mov     rcx, rbx
0x18006aa60  call    sqlite3SrcListLookup
0x18006aa65  mov     rcx, rax
0x18006aa68  cmp     [rdi+0C5h], r13b
0x18006aa6f  jnz     short loc_18006AA90
0x18006aa71  cmp     [r14+8], r13d
0x18006aa75  jnz     short loc_18006AA90
0x18006aa77  test    rax, rax
0x18006aa7a  jz      short loc_18006AA90
0x18006aa7c  mov     rax, [rdi+20h]
0x18006aa80  mov     rax, [rax+38h]
0x18006aa84  cmp     [rcx+60h], rax
0x18006aa88  mov     eax, 1
0x18006aa8d  cmovz   ebp, eax
0x18006aa90  cmp     [rdi+67h], r13b
0x18006aa94  jnz     short loc_18006AB02
0x18006aa96  lea     r9, aTrigger; "trigger"
0x18006aa9d  mov     [rsp+0D8h+var_B8], r12
0x18006aaa2  mov     r8d, ebp
0x18006aaa5  lea     rcx, [rsp+0D8h+var_98]
0x18006aaaa  mov     rdx, rbx
0x18006aaad  call    sqlite3FixInit
0x18006aab2  mov     rdx, rsi
0x18006aab5  lea     rcx, [rsp+0D8h+var_98]
0x18006aaba  call    sqlite3FixSrcList
0x18006aabf  test    eax, eax
0x18006aac1  jnz     short loc_18006AB02
0x18006aac3  mov     rdx, rsi
0x18006aac6  mov     rcx, rbx
0x18006aac9  call    sqlite3SrcListLookup
0x18006aace  mov     r14, rax
0x18006aad1  test    rax, rax
0x18006aad4  jz      short loc_18006AAEF
0x18006aad6  cmp     byte ptr [rax+3Fh], 1
0x18006aada  jnz     loc_18006AB6D
0x18006aae0  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x18006aae7  mov     rcx, rbx
0x18006aaea  call    sqlite3ErrorMsg
0x18006aaef  mov     eax, 1
0x18006aaf4  cmp     [rdi+0C4h], al
0x18006aafa  jnz     short loc_18006AB02
0x18006aafc  or      [rdi+0C8h], eax
0x18006ab02  mov     rdx, [rsp+0D8h+arg_0]
0x18006ab0a  mov     rcx, rdi
0x18006ab0d  call    sqlite3DbFree
0x18006ab12  mov     rdx, rsi
0x18006ab15  mov     rcx, rdi
0x18006ab18  call    sqlite3SrcListDelete
0x18006ab1d  mov     rdx, [rsp+0D8h+arg_28]
0x18006ab25  mov     rcx, rdi
0x18006ab28  call    sqlite3IdListDelete
0x18006ab2d  mov     rdx, [rsp+0D8h+arg_38]
0x18006ab35  mov     rcx, rdi
0x18006ab38  call    sqlite3ExprDelete
0x18006ab3d  cmp     qword ptr [rbx+168h], 0
0x18006ab45  jnz     short loc_18006AB52
0x18006ab47  mov     rdx, r15
0x18006ab4a  mov     rcx, rdi
0x18006ab4d  call    sqlite3DeleteTrigger
0x18006ab52  mov     rbx, [rsp+0D8h+arg_8]
0x18006ab5a  add     rsp, 0A0h
0x18006ab61  pop     r15
0x18006ab63  pop     r14
0x18006ab65  pop     r13
0x18006ab67  pop     r12
0x18006ab69  pop     rdi
0x18006ab6a  pop     rsi
0x18006ab6b  pop     rbp
0x18006ab6c  retn
0x18006ab6d  mov     rdx, r12
0x18006ab70  mov     rcx, rdi
0x18006ab73  call    sqlite3NameFromToken
0x18006ab78  mov     [rsp+0D8h+arg_0], rax
0x18006ab80  test    rax, rax
0x18006ab83  jz      loc_18006AB02
0x18006ab89  mov     r9, [r14]
0x18006ab8c  lea     r8, aTrigger; "trigger"
0x18006ab93  mov     rdx, rax
0x18006ab96  mov     rcx, rbx
0x18006ab99  call    sqlite3CheckObjectName
0x18006ab9e  test    eax, eax
0x18006aba0  jnz     loc_18006AB02
0x18006aba6  cmp     byte ptr [rbx+12Ch], 2
0x18006abad  jnb     short loc_18006AC05
0x18006abaf  mov     rax, [rdi+20h]
0x18006abb3  xor     r8d, r8d
0x18006abb6  mov     rdx, [rsp+0D8h+arg_0]
0x18006abbe  mov     ecx, ebp
0x18006abc0  shl     rcx, 5
0x18006abc4  mov     rcx, [rcx+rax+18h]
0x18006abc9  add     rcx, 38h ; '8'
0x18006abcd  call    findElementWithHash
0x18006abd2  cmp     [rax+10h], r13
0x18006abd6  jz      short loc_18006AC05
0x18006abd8  mov     rcx, rbx
0x18006abdb  cmp     [rsp+0D8h+arg_48], r13d
0x18006abe3  jnz     short loc_18006ABF9
0x18006abe5  mov     r8, r12
0x18006abe8  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x18006abef  call    sqlite3ErrorMsg
0x18006abf4  jmp     loc_18006AB02
0x18006abf9  mov     edx, ebp
0x18006abfb  call    sqlite3CodeVerifySchema
0x18006ac00  jmp     loc_18006AB02
0x18006ac05  mov     rcx, [r14]
0x18006ac08  lea     rdx, aSqlite_0; "sqlite_"
0x18006ac0f  mov     r13d, 7
0x18006ac15  mov     r8d, r13d
0x18006ac18  call    sqlite3_strnicmp
0x18006ac1d  test    eax, eax
0x18006ac1f  jnz     short loc_18006AC2D
0x18006ac21  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x18006ac28  jmp     loc_18006A9F2
0x18006ac2d  cmp     byte ptr [r14+3Fh], 2
0x18006ac32  jnz     short loc_18006AC6D
0x18006ac34  mov     eax, [rsp+0D8h+arg_18]
0x18006ac3b  cmp     eax, 41h ; 'A'
0x18006ac3e  jz      short loc_18006AC8F
0x18006ac40  cmp     eax, 21h ; '!'
0x18006ac43  lea     rcx, aAfter; "AFTER"
0x18006ac4a  lea     r8, aBefore; "BEFORE"
0x18006ac51  cmovnz  r8, rcx
0x18006ac55  lea     r9, [rsi+8]
0x18006ac59  mov     rcx, rbx
0x18006ac5c  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x18006ac63  call    sqlite3ErrorMsg
0x18006ac68  jmp     loc_18006AAEF
0x18006ac6d  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x18006ac75  jnz     short loc_18006AC8F
0x18006ac77  lea     r8, [rsi+8]
0x18006ac7b  mov     rcx, rbx
0x18006ac7e  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x18006ac85  call    sqlite3ErrorMsg
0x18006ac8a  jmp     loc_18006AAEF
0x18006ac8f  cmp     byte ptr [rbx+12Ch], 2
0x18006ac96  jnb     loc_18006AD47
0x18006ac9c  mov     rdx, [r14+60h]
0x18006aca0  mov     rcx, rdi
0x18006aca3  call    sqlite3SchemaToIndex
0x18006aca8  mov     rdx, [rdi+20h]
0x18006acac  mov     r8d, [rsp+0D8h+arg_40]
0x18006acb4  movsxd  r12, eax
0x18006acb7  mov     rcx, r12
0x18006acba  shl     rcx, 5
0x18006acbe  mov     rax, [rcx+rdx]
0x18006acc2  mov     [rsp+0D8h+var_A8], rax
0x18006acc7  test    r8d, r8d
0x18006acca  jz      short loc_18006ACD2
0x18006accc  mov     rcx, [rdx+20h]
0x18006acd0  jmp     short loc_18006ACD5
0x18006acd2  mov     rcx, rax
0x18006acd5  cmp     r12d, 1
0x18006acd9  jz      short loc_18006ACE0
0x18006acdb  test    r8d, r8d
0x18006acde  jz      short loc_18006ACE6
0x18006ace0  mov     r13d, 5
0x18006ace6  mov     r9, [r14]
0x18006ace9  mov     edx, r13d
0x18006acec  mov     r8, [rsp+0D8h+arg_0]
0x18006acf4  mov     [rsp+0D8h+var_B8], rcx
0x18006acf9  mov     rcx, rbx
0x18006acfc  call    sqlite3AuthCheck
0x18006ad01  test    eax, eax
0x18006ad03  jnz     loc_18006AB02
0x18006ad09  mov     r13d, 1
0x18006ad0f  lea     rax, aSqliteMaster; "sqlite_master"
0x18006ad16  cmp     r12d, r13d
0x18006ad19  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x18006ad20  mov     rcx, rbx
0x18006ad23  cmovnz  r8, rax
0x18006ad27  mov     rax, [rsp+0D8h+var_A8]
0x18006ad2c  xor     r9d, r9d
0x18006ad2f  mov     [rsp+0D8h+var_B8], rax
0x18006ad34  lea     edx, [r13+11h]
0x18006ad38  call    sqlite3AuthCheck
0x18006ad3d  test    eax, eax
0x18006ad3f  jnz     loc_18006AB02
0x18006ad45  jmp     short loc_18006AD4D
0x18006ad47  mov     r13d, 1
0x18006ad4d  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x18006ad55  mov     r12d, 21h ; '!'
0x18006ad5b  mov     edx, 48h ; 'H'
0x18006ad60  mov     rcx, rdi
0x18006ad63  cmovnz  r12d, [rsp+0D8h+arg_18]
0x18006ad6c  call    sqlite3DbMallocZero
0x18006ad71  mov     r15, rax
0x18006ad74  test    rax, rax
0x18006ad77  jz      loc_18006AB02
0x18006ad7d  mov     rax, [rsp+0D8h+arg_0]
0x18006ad85  mov     rcx, rdi
0x18006ad88  mov     [r15], rax
0x18006ad8b  mov     rdx, [rsi+18h]
0x18006ad8f  mov     [rsp+0D8h+arg_0], 0
0x18006ad9b  call    sqlite3DbStrDup
0x18006ada0  mov     [r15+8], rax
0x18006ada4  mov     rcx, [rdi+20h]
0x18006ada8  mov     edx, ebp
0x18006adaa  shl     rdx, 5
0x18006adae  cmp     r12d, 21h ; '!'
0x18006adb2  mov     rdx, [rdx+rcx+18h]
0x18006adb7  mov     [r15+28h], rdx
0x18006adbb  mov     rcx, [r14+60h]
0x18006adbf  mov     [r15+30h], rcx
0x18006adc3  mov     cl, [rsp+0D8h+arg_20]
0x18006adca  mov     [r15+10h], cl
0x18006adce  setnz   cl
0x18006add1  add     cl, r13b
0x18006add4  mov     [r15+11h], cl
0x18006add8  cmp     byte ptr [rbx+12Ch], 2
0x18006addf  jb      short loc_18006AE06
0x18006ade1  mov     r8, [rsi+18h]
0x18006ade5  mov     rdx, rax
0x18006ade8  mov     r9, [rsp+0D8h+arg_38]
0x18006adf0  mov     rcx, rbx
0x18006adf3  call    sqlite3RenameTokenRemap
0x18006adf8  mov     [rsp+0D8h+arg_38], 0
0x18006ae04  jmp     short loc_18006AE1C
0x18006ae06  mov     rdx, [rsp+0D8h+arg_38]
0x18006ae0e  mov     r8d, r13d
0x18006ae11  mov     rcx, rdi
0x18006ae14  call    sqlite3ExprDup
0x18006ae19  mov     r9, rax
0x18006ae1c  mov     rax, [rsp+0D8h+arg_28]
0x18006ae24  mov     [r15+18h], r9
0x18006ae28  mov     [r15+20h], rax
0x18006ae2c  mov     [rbx+168h], r15
0x18006ae33  mov     [rsp+0D8h+arg_28], 0
0x18006ae3f  jmp     loc_18006AB02
```
