# sqlite3BeginTrigger

- ea: `0x180069814`
- end: `0x180069d5e`
- name: `sqlite3BeginTrigger`
- size: `1354`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path`

## callers

- `0x1800c3bd8`

## callees

- `0x180002cf8`
- `0x180045428`
- `0x180047054`
- `0x1800693b0`
- `0x180069814`
- `0x18006db9c`
- `0x18006ed2c`
- `0x1800716fc`
- `0x1800718ac`
- `0x180071a38`
- `0x18007281c`
- `0x180073aec`
- `0x180076d6c`
- `0x180079514`
- `0x180079598`
- `0x18007d8bc`
- `0x180081754`
- `0x1800892a0`
- `0x18008e124`
- `0x18008e588`
- `0x18008fa90`
- `0x1800ada30`

## string_xrefs

- `0x180069bc6`: `sqlite_temp_master`
- `0x180069878`: `temporary trigger may not have qualified name`
- `0x1800699de`: `cannot create triggers on shadow tables`
- `0x180069a5e`: `trigger %T already exists`
- `0x180069999`: `cannot create triggers on virtual tables`
- `0x180069af7`: `cannot create %s trigger on view: %S`
- `0x180069ab6`: `cannot create trigger on system table`
- `0x180069b19`: `cannot create INSTEAD OF trigger on table: %S`

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
0x180069814  mov     [rsp+arg_8], rbx
0x180069819  mov     [rsp+arg_18], r9d
0x18006981e  push    rbp
0x18006981f  push    rsi
0x180069820  push    rdi
0x180069821  push    r12
0x180069823  push    r13
0x180069825  push    r14
0x180069827  push    r15
0x180069829  sub     rsp, 0A0h
0x180069830  mov     rbx, [rcx]
0x180069833  xor     r14d, r14d
0x180069836  mov     rsi, r8
0x180069839  mov     [rsp+0D8h+arg_0], r14
0x180069841  mov     r12, rdx
0x180069844  mov     [rsp+0D8h+var_A8], r14
0x180069849  mov     rdi, rcx
0x18006984c  xor     edx, edx; Val
0x18006984e  lea     r8d, [r14+60h]; Size
0x180069852  lea     rcx, [rsp+0D8h+var_98]; void *
0x180069857  call    memset_0
0x18006985c  lea     ebp, [r14+1]
0x180069860  mov     r13, [rsp+0D8h+arg_30]
0x180069868  cmp     [rsp+0D8h+arg_40], r14d
0x180069870  jz      short loc_1800698A1
0x180069872  cmp     [rsi+8], r14d
0x180069876  jbe     short loc_18006989C
0x180069878  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x18006987f  mov     rcx, rdi
0x180069882  call    sqlite3ErrorMsg
0x180069887  mov     rsi, [rsp+0D8h+arg_38]
0x18006988f  mov     rbp, [rsp+0D8h+arg_28]
0x180069897  jmp     loc_180069D08
0x18006989c  mov     r14d, ebp
0x18006989f  jmp     short loc_1800698C4
0x1800698a1  lea     r9, [rsp+0D8h+var_A8]
0x1800698a6  mov     r8, rsi
0x1800698a9  mov     rdx, r12
0x1800698ac  mov     rcx, rdi
0x1800698af  call    sqlite3TwoPartName
0x1800698b4  mov     r14d, eax
0x1800698b7  test    eax, eax
0x1800698b9  js      loc_180069CF0
0x1800698bf  mov     r12, [rsp+0D8h+var_A8]
0x1800698c4  test    r13, r13
0x1800698c7  jz      loc_180069CF0
0x1800698cd  cmp     byte ptr [rbx+67h], 0
0x1800698d1  jnz     loc_180069CF0
0x1800698d7  cmp     byte ptr [rbx+0C5h], 0
0x1800698de  jz      short loc_1800698FE
0x1800698e0  cmp     r14d, ebp
0x1800698e3  jz      short loc_1800698FE
0x1800698e5  mov     rdx, [r13+10h]
0x1800698e9  test    rdx, rdx
0x1800698ec  jz      short loc_1800698F6
0x1800698ee  mov     rcx, rbx
0x1800698f1  call    sqlite3DbFreeNN
0x1800698f6  mov     qword ptr [r13+10h], 0
0x1800698fe  mov     rdx, r13
0x180069901  mov     rcx, rdi
0x180069904  call    sqlite3SrcListLookup
0x180069909  cmp     byte ptr [rbx+0C5h], 0
0x180069910  jnz     short loc_18006992D
0x180069912  cmp     dword ptr [rsi+8], 0
0x180069916  jnz     short loc_18006992D
0x180069918  test    rax, rax
0x18006991b  jz      short loc_18006992D
0x18006991d  mov     rcx, [rbx+20h]
0x180069921  mov     rcx, [rcx+38h]
0x180069925  cmp     [rax+60h], rcx
0x180069929  cmovz   r14d, ebp
0x18006992d  cmp     byte ptr [rbx+67h], 0
0x180069931  jnz     loc_180069CF0
0x180069937  lea     r9, aTrigger; "trigger"
0x18006993e  mov     [rsp+0D8h+var_B8], r12
0x180069943  mov     r8d, r14d
0x180069946  lea     rcx, [rsp+0D8h+var_98]
0x18006994b  mov     rdx, rdi
0x18006994e  call    sqlite3FixInit
0x180069953  mov     rdx, r13
0x180069956  lea     rcx, [rsp+0D8h+var_98]
0x18006995b  call    sqlite3FixSrcList
0x180069960  test    eax, eax
0x180069962  jnz     loc_180069CF0
0x180069968  mov     rbp, [rsp+0D8h+arg_28]
0x180069970  mov     rdx, r13
0x180069973  mov     rsi, [rsp+0D8h+arg_38]
0x18006997b  mov     rcx, rdi
0x18006997e  xor     r15d, r15d
0x180069981  call    sqlite3SrcListLookup
0x180069986  mov     [rsp+0D8h+arg_38], rax
0x18006998e  test    rax, rax
0x180069991  jz      short loc_1800699A8
0x180069993  cmp     byte ptr [rax+3Fh], 1
0x180069997  jnz     short loc_1800699C9
0x180069999  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x1800699a0  mov     rcx, rdi
0x1800699a3  call    sqlite3ErrorMsg
0x1800699a8  cmp     byte ptr [rbx+0C4h], 1
0x1800699af  jnz     short loc_1800699B8
0x1800699b1  or      dword ptr [rbx+0C8h], 1
0x1800699b8  xor     r14d, r14d
0x1800699bb  test    r15, r15
0x1800699be  jz      loc_180069D08
0x1800699c4  jmp     loc_180069A72
0x1800699c9  test    dword ptr [rax+30h], 1000h
0x1800699d0  jz      short loc_1800699E7
0x1800699d2  mov     rcx, rbx
0x1800699d5  call    sqlite3ReadOnlyShadowTables
0x1800699da  test    eax, eax
0x1800699dc  jz      short loc_1800699E7
0x1800699de  lea     rdx, aCannotCreateTr_1; "cannot create triggers on shadow tables"
0x1800699e5  jmp     short loc_1800699A0
0x1800699e7  mov     rdx, r12
0x1800699ea  mov     rcx, rbx
0x1800699ed  call    sqlite3NameFromToken
0x1800699f2  mov     r15, rax
0x1800699f5  test    rax, rax
0x1800699f8  jz      loc_180069D00
0x1800699fe  mov     rcx, [rsp+0D8h+arg_38]
0x180069a06  lea     r8, aTrigger; "trigger"
0x180069a0d  mov     rdx, rax
0x180069a10  mov     r9, [rcx]
0x180069a13  mov     rcx, rdi
0x180069a16  call    sqlite3CheckObjectName
0x180069a1b  test    eax, eax
0x180069a1d  jnz     short loc_180069A6A
0x180069a1f  cmp     byte ptr [rdi+134h], 2
0x180069a26  jnb     short loc_180069A8C
0x180069a28  mov     rax, [rbx+20h]
0x180069a2c  xor     r8d, r8d
0x180069a2f  mov     ecx, r14d
0x180069a32  mov     rdx, r15
0x180069a35  shl     rcx, 5
0x180069a39  mov     rcx, [rcx+rax+18h]
0x180069a3e  add     rcx, 38h ; '8'
0x180069a42  call    findElementWithHash
0x180069a47  cmp     qword ptr [rax+10h], 0
0x180069a4c  jz      short loc_180069A8C
0x180069a4e  cmp     [rsp+0D8h+arg_48], 0
0x180069a56  mov     rcx, rdi
0x180069a59  jnz     short loc_180069A82
0x180069a5b  mov     r8, r12
0x180069a5e  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x180069a65  call    sqlite3ErrorMsg
0x180069a6a  mov     r14, [rsp+0D8h+arg_0]
0x180069a72  mov     rdx, r15
0x180069a75  mov     rcx, rbx
0x180069a78  call    sqlite3DbFreeNN
0x180069a7d  jmp     loc_180069D08
0x180069a82  mov     edx, r14d
0x180069a85  call    sqlite3CodeVerifySchema
0x180069a8a  jmp     short loc_180069A6A
0x180069a8c  mov     r12, [rsp+0D8h+arg_38]
0x180069a94  lea     rdx, aSqlite_0; "sqlite_"
0x180069a9b  mov     r8d, 7
0x180069aa1  mov     rax, [r12]
0x180069aa5  mov     rcx, rax
0x180069aa8  mov     [rsp+0D8h+var_A8], rax
0x180069aad  call    sqlite3_strnicmp
0x180069ab2  test    eax, eax
0x180069ab4  jnz     short loc_180069AC7
0x180069ab6  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x180069abd  mov     rcx, rdi
0x180069ac0  call    sqlite3ErrorMsg
0x180069ac5  jmp     short loc_180069A6A
0x180069ac7  cmp     byte ptr [r12+3Fh], 2
0x180069acd  jnz     short loc_180069B08
0x180069acf  mov     eax, [rsp+0D8h+arg_18]
0x180069ad6  cmp     eax, 41h ; 'A'
0x180069ad9  jz      short loc_180069B2A
0x180069adb  cmp     eax, 21h ; '!'
0x180069ade  lea     rcx, aAfter; "AFTER"
0x180069ae5  lea     r8, aBefore; "BEFORE"
0x180069aec  cmovnz  r8, rcx
0x180069af0  lea     r9, [r13+8]
0x180069af4  mov     rcx, rdi
0x180069af7  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x180069afe  call    sqlite3ErrorMsg
0x180069b03  jmp     loc_1800699A8
0x180069b08  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180069b10  jnz     short loc_180069B2A
0x180069b12  lea     r8, [r13+8]
0x180069b16  mov     rcx, rdi
0x180069b19  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x180069b20  call    sqlite3ErrorMsg
0x180069b25  jmp     loc_1800699A8
0x180069b2a  cmp     byte ptr [rdi+134h], 2
0x180069b31  jnb     loc_180069BF2
0x180069b37  mov     rcx, [r12+60h]
0x180069b3c  mov     r12d, 0FFFF8000h
0x180069b42  test    rcx, rcx
0x180069b45  jz      short loc_180069B65
0x180069b47  mov     rdx, [rbx+20h]
0x180069b4b  xor     r12d, r12d
0x180069b4e  cmp     [rdx+18h], rcx
0x180069b52  jz      short loc_180069B65
0x180069b54  inc     r12d
0x180069b57  movsxd  rax, r12d
0x180069b5a  shl     rax, 5
0x180069b5e  cmp     [rax+rdx+18h], rcx
0x180069b63  jnz     short loc_180069B54
0x180069b65  mov     rcx, [rbx+20h]
0x180069b69  mov     edx, [rsp+0D8h+arg_40]
0x180069b70  movsxd  rax, r12d
0x180069b73  shl     rax, 5
0x180069b77  mov     rax, [rax+rcx]
0x180069b7b  mov     [rsp+0D8h+var_A0], rax
0x180069b80  test    edx, edx
0x180069b82  jz      short loc_180069B88
0x180069b84  mov     rax, [rcx+20h]
0x180069b88  cmp     r12d, 1
0x180069b8c  jz      short loc_180069B92
0x180069b8e  test    edx, edx
0x180069b90  jz      short loc_180069B99
0x180069b92  mov     edx, 5
0x180069b97  jmp     short loc_180069B9E
0x180069b99  mov     edx, 7
0x180069b9e  mov     r9, [rsp+0D8h+var_A8]
0x180069ba3  mov     r8, r15
0x180069ba6  mov     rcx, rdi
0x180069ba9  mov     [rsp+0D8h+var_B8], rax
0x180069bae  call    sqlite3AuthCheck
0x180069bb3  test    eax, eax
0x180069bb5  jnz     loc_180069A6A
0x180069bbb  lea     rax, aSqliteMaster; "sqlite_master"
0x180069bc2  cmp     r12d, 1
0x180069bc6  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x180069bcd  mov     rcx, rdi
0x180069bd0  cmovnz  r8, rax
0x180069bd4  mov     rax, [rsp+0D8h+var_A0]
0x180069bd9  xor     r9d, r9d
0x180069bdc  mov     [rsp+0D8h+var_B8], rax
0x180069be1  lea     edx, [r9+12h]
0x180069be5  call    sqlite3AuthCheck
0x180069bea  test    eax, eax
0x180069bec  jnz     loc_180069A6A
0x180069bf2  cmp     [rsp+0D8h+arg_18], 41h ; 'A'
0x180069bfa  mov     eax, 21h ; '!'
0x180069bff  mov     edx, 48h ; 'H'
0x180069c04  mov     rcx, rbx
0x180069c07  cmovnz  eax, [rsp+0D8h+arg_18]
0x180069c0f  mov     [rsp+0D8h+arg_40], eax
0x180069c16  call    sqlite3DbMallocZero
0x180069c1b  mov     r12, rax
0x180069c1e  test    rax, rax
0x180069c21  jz      loc_180069CE8
0x180069c27  mov     [rax], r15
0x180069c2a  mov     rcx, rbx
0x180069c2d  mov     rdx, [r13+18h]
0x180069c31  call    sqlite3DbStrDup
0x180069c36  mov     [r12+8], rax
0x180069c3b  mov     r8, rax
0x180069c3e  mov     rcx, [rbx+20h]
0x180069c42  mov     edx, r14d
0x180069c45  shl     rdx, 5
0x180069c49  cmp     [rsp+0D8h+arg_40], 21h ; '!'
0x180069c51  mov     rdx, [rdx+rcx+18h]
0x180069c56  mov     rcx, [rsp+0D8h+arg_38]
0x180069c5e  mov     [r12+28h], rdx
0x180069c63  mov     rcx, [rcx+60h]
0x180069c67  mov     [r12+30h], rcx
0x180069c6c  mov     cl, [rsp+0D8h+arg_20]
0x180069c73  mov     [r12+10h], cl
0x180069c78  setnz   cl
0x180069c7b  inc     cl
0x180069c7d  mov     [r12+11h], cl
0x180069c82  cmp     byte ptr [rdi+134h], 2
0x180069c89  jb      short loc_180069CB2
0x180069c8b  mov     rdx, [r13+18h]
0x180069c8f  mov     rcx, rsi
0x180069c92  mov     rax, [rdi+1A0h]
0x180069c99  jmp     short loc_180069CA4
0x180069c9b  cmp     [rax], rdx
0x180069c9e  jz      short loc_180069CAB
0x180069ca0  mov     rax, [rax+18h]
0x180069ca4  test    rax, rax
0x180069ca7  jnz     short loc_180069C9B
0x180069ca9  jmp     short loc_180069CAE
0x180069cab  mov     [rax], r8
0x180069cae  xor     esi, esi
0x180069cb0  jmp     short loc_180069CD0
0x180069cb2  test    rsi, rsi
0x180069cb5  jz      short loc_180069CCE
0x180069cb7  xor     r9d, r9d
0x180069cba  mov     rdx, rsi
0x180069cbd  mov     rcx, rbx
0x180069cc0  lea     r8d, [r9+1]
0x180069cc4  call    exprDup
0x180069cc9  mov     rcx, rax
0x180069ccc  jmp     short loc_180069CD0
0x180069cce  xor     ecx, ecx
0x180069cd0  mov     [r12+18h], rcx
0x180069cd5  mov     r14, r12
0x180069cd8  mov     [r12+20h], rbp
0x180069cdd  xor     ebp, ebp
0x180069cdf  mov     [rdi+170h], r12
0x180069ce6  jmp     short loc_180069D08
0x180069ce8  mov     r14, rax
0x180069ceb  jmp     loc_180069A72
  ... truncated ...
```
