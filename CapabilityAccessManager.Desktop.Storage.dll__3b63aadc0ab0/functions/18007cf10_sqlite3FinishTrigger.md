# sqlite3FinishTrigger

- ea: `0x18007cf10`
- end: `0x18007d342`
- name: `sqlite3FinishTrigger`
- size: `1074`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: ``

## callers

- `0x1800d8b00`

## callees

- `0x180005980`
- `0x18003c1a0`
- `0x18004dba0`
- `0x1800669c0`
- `0x18006b630`
- `0x180071400`
- `0x180072a30`
- `0x180072be0`
- `0x1800743d0`
- `0x18007cf10`
- `0x18007d350`
- `0x1800838f0`
- `0x180088530`
- `0x180088ea0`
- `0x180089210`
- `0x180093600`
- `0x18009b840`
- `0x1800a3370`
- `0x1800a3b40`
- `0x1800b3d60`
- `0x1800e4dce`
- `0x1800e4dfe`

## string_xrefs

- `0x18007d1ef`: `trigger "%s" may not write to shadow table "%s"`
- `0x18007d20c`: `INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')`

## pseudocode

```c
__int64 __fastcall sqlite3FinishTrigger(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rsi
  __int64 v4; // rbx
  __int64 v5; // rdi
  __int64 v8; // rcx
  unsigned int v9; // r15d
  __int64 v10; // rdx
  const char *v11; // rcx
  int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // r13
  __int64 v15; // rcx
  _BYTE *v16; // r12
  const char *v17; // r14
  _QWORD *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // r13
  _QWORD *v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rdx
  __int64 v28; // [rsp+20h] [rbp-C8h]
  int v29; // [rsp+28h] [rbp-C0h]
  __int64 v30; // [rsp+30h] [rbp-B8h]
  __int64 v31; // [rsp+30h] [rbp-B8h]
  void *Src; // [rsp+38h] [rbp-B0h]
  const char *v33; // [rsp+40h] [rbp-A8h] BYREF
  int v34; // [rsp+48h] [rbp-A0h]
  __int64 *v35; // [rsp+50h] [rbp-98h] BYREF
  _QWORD v36[4]; // [rsp+58h] [rbp-90h] BYREF
  int v37; // [rsp+78h] [rbp-70h]
  __int16 v38; // [rsp+7Ch] [rbp-6Ch]
  __int64 **v39; // [rsp+80h] [rbp-68h]
  __int64 v40; // [rsp+88h] [rbp-60h]
  bool v41; // [rsp+90h] [rbp-58h]
  __int64 v42; // [rsp+98h] [rbp-50h]
  const char *v43; // [rsp+A0h] [rbp-48h]
  const char **v44; // [rsp+A8h] [rbp-40h]
  const char *v45; // [rsp+F0h] [rbp+8h]
  size_t Size; // [rsp+108h] [rbp+20h]

  v3 = a1[45];
  v4 = a3;
  v5 = *a1;
  a1[45] = 0;
  if ( *((_DWORD *)a1 + 12) || !v3 )
    goto LABEL_49;
  v8 = *(_QWORD *)(v3 + 40);
  v9 = -32768;
  v45 = *(const char **)v3;
  if ( v8 )
  {
    v10 = *(_QWORD *)(v5 + 32);
    v9 = 0;
    if ( *(_QWORD *)(v10 + 24) != v8 )
    {
      do
        ++v9;
      while ( *(_QWORD *)(32LL * (int)v9 + v10 + 24) != v8 );
    }
  }
  for ( *(_QWORD *)(v3 + 56) = a2; a2; a2 = *(_QWORD *)(a2 + 80) )
    *(_QWORD *)(a2 + 8) = v3;
  v11 = *(const char **)v3;
  v33 = v11;
  v12 = v11 ? strlen_0(v11) & 0x3FFFFFFF : 0;
  v13 = *a1;
  v34 = v12;
  v35 = a1;
  v14 = 32LL * (int)v9;
  v30 = v14;
  v42 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + v14);
  v15 = *(_QWORD *)(*(_QWORD *)(v13 + 32) + v14 + 24);
  v43 = "trigger";
  v41 = v9 == 1;
  v40 = v15;
  v44 = &v33;
  v36[0] = a1;
  v36[1] = fixExprCb;
  v36[2] = fixSelectCb;
  v36[3] = Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace;
  v39 = &v35;
  v37 = 0;
  v38 = 0;
  if ( (unsigned int)sqlite3FixTriggerStep(&v35, *(_QWORD *)(v3 + 56))
    || *(_QWORD *)(v3 + 24) && (unsigned int)sqlite3WalkExprNN(v36) )
  {
    goto LABEL_49;
  }
  if ( *((_BYTE *)a1 + 300) >= 2u )
  {
    a1[45] = v3;
    v3 = 0;
    v16 = (_BYTE *)(v5 + 197);
LABEL_16:
    v17 = v45;
    goto LABEL_17;
  }
  v16 = (_BYTE *)(v5 + 197);
  if ( *(_BYTE *)(v5 + 197) )
    goto LABEL_16;
  if ( !(unsigned int)sqlite3ReadOnlyShadowTables(v5) )
  {
LABEL_27:
    v21 = a1[2];
    if ( !v21 )
    {
      if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
        *((_BYTE *)a1 + 35) = 1;
      v21 = sqlite3VdbeCreate(a1);
      if ( !v21 )
        goto LABEL_49;
    }
    sqlite3BeginWriteOperation(a1, 0, v9);
    Src = *(void **)v4;
    if ( *(_QWORD *)v4 )
    {
      Size = *(unsigned int *)(v4 + 8);
      v22 = (_QWORD *)sqlite3DbMallocRawNN(v5, Size + 1);
      v23 = v22;
      if ( v22 )
      {
        memcpy_0(v22, Src, Size);
        *((_BYTE *)v23 + Size) = 0;
      }
    }
    else
    {
      v23 = 0;
    }
    sqlite3NestedParse(
      a1,
      "INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')",
      *(_QWORD *)(*(_QWORD *)(v5 + 32) + v30),
      v45,
      *(_QWORD *)(v3 + 8),
      v23);
    if ( v23 )
    {
      if ( (unsigned __int64)v23 < *(_QWORD *)(v5 + 496) )
      {
        if ( (unsigned __int64)v23 >= *(_QWORD *)(v5 + 480) )
        {
          *v23 = *(_QWORD *)(v5 + 472);
          *(_QWORD *)(v5 + 472) = v23;
          goto LABEL_46;
        }
        if ( (unsigned __int64)v23 >= *(_QWORD *)(v5 + 488) )
        {
          *v23 = *(_QWORD *)(v5 + 456);
          *(_QWORD *)(v5 + 456) = v23;
          goto LABEL_46;
        }
      }
      if ( *(_QWORD *)(v5 + 776) )
        measureAllocationSize(v5, v23);
      else
        sqlite3_free(v23);
    }
LABEL_46:
    sqlite3ChangeCookie(a1, v9);
    v17 = v45;
    v24 = sqlite3MPrintf(v5, "type='trigger' AND name='%q'", v45);
    sqlite3VdbeAddParseSchemaOp(v21, v9, v24, 0, v28, v29, v30);
    v14 = v31;
LABEL_17:
    if ( *v16 )
    {
      v18 = (_QWORD *)v3;
      v3 = sqlite3HashInsert(*(_QWORD *)(*(_QWORD *)(v5 + 32) + v14 + 24) + 56LL, v17, v3);
      if ( v3 )
      {
        sqlite3OomFault(v5);
      }
      else
      {
        v25 = v18[6];
        if ( v18[5] == v25 )
        {
          v26 = *(_QWORD *)(findElementWithHash(v25 + 8, v18[1], 0) + 16);
          v18[8] = *(_QWORD *)(v26 + 88);
          *(_QWORD *)(v26 + 88) = v18;
        }
      }
    }
    goto LABEL_49;
  }
  v19 = *(_QWORD *)(v3 + 56);
  if ( !v19 )
  {
LABEL_26:
    v4 = a3;
    goto LABEL_27;
  }
  while ( 1 )
  {
    v20 = *(_QWORD *)(v19 + 24);
    if ( v20 )
    {
      if ( (unsigned int)sqlite3ShadowTableName(v5, v20) )
        break;
    }
    v19 = *(_QWORD *)(v19 + 80);
    if ( !v19 )
      goto LABEL_26;
  }
  sqlite3ErrorMsg(
    a1,
    "trigger \"%s\" may not write to shadow table \"%s\"",
    *(const char **)v3,
    *(const char **)(v19 + 24));
LABEL_49:
  sqlite3DeleteTrigger(v5, v3);
  return sqlite3DeleteTriggerStep(v5, a2);
}

```

## disassembly

```asm
0x18007cf10  mov     rax, rsp
0x18007cf13  mov     [rax+18h], r8
0x18007cf17  push    rbx
0x18007cf18  push    rbp
0x18007cf19  push    rsi
0x18007cf1a  push    rdi
0x18007cf1b  push    r12
0x18007cf1d  push    r14
0x18007cf1f  sub     rsp, 0B8h
0x18007cf26  mov     rsi, [rcx+168h]
0x18007cf2d  xor     r12d, r12d
0x18007cf30  mov     rbx, r8
0x18007cf33  mov     rdi, [rcx]
0x18007cf36  mov     rbp, rdx
0x18007cf39  mov     r14, rcx
0x18007cf3c  mov     [rcx+168h], r12
0x18007cf43  cmp     [rcx+30h], r12d
0x18007cf47  jnz     loc_18007D31C
0x18007cf4d  test    rsi, rsi
0x18007cf50  jz      loc_18007D31C
0x18007cf56  mov     rcx, [rsi+28h]
0x18007cf5a  mov     [rax+10h], r13
0x18007cf5e  mov     [rax-38h], r15
0x18007cf62  mov     r15d, 0FFFF8000h
0x18007cf68  mov     rax, [rsi]
0x18007cf6b  mov     [rsp+0E8h+arg_0], rax
0x18007cf73  test    rcx, rcx
0x18007cf76  jz      short loc_18007CFA1
0x18007cf78  mov     rdx, [rdi+20h]
0x18007cf7c  mov     r15d, r12d
0x18007cf7f  cmp     [rdx+18h], rcx
0x18007cf83  jz      short loc_18007CFA1
0x18007cf85  nop     word ptr [rax+rax+00000000h]
0x18007cf90  inc     r15d
0x18007cf93  movsxd  rax, r15d
0x18007cf96  shl     rax, 5
0x18007cf9a  cmp     [rax+rdx+18h], rcx
0x18007cf9f  jnz     short loc_18007CF90
0x18007cfa1  mov     [rsi+38h], rbp
0x18007cfa5  test    rbp, rbp
0x18007cfa8  jz      short loc_18007CFBD
0x18007cfaa  nop     word ptr [rax+rax+00h]
0x18007cfb0  mov     [rbp+8], rsi
0x18007cfb4  mov     rbp, [rbp+50h]
0x18007cfb8  test    rbp, rbp
0x18007cfbb  jnz     short loc_18007CFB0
0x18007cfbd  mov     rcx, [rsi]; Str
0x18007cfc0  mov     [rsp+0E8h+var_A8], rcx
0x18007cfc5  test    rcx, rcx
0x18007cfc8  jnz     short loc_18007CFCF
0x18007cfca  mov     eax, r12d
0x18007cfcd  jmp     short loc_18007CFD9
0x18007cfcf  call    strlen_0
0x18007cfd4  and     eax, 3FFFFFFFh
0x18007cfd9  mov     rdx, [r14]
0x18007cfdc  mov     [rsp+0E8h+var_A0], eax
0x18007cfe0  mov     [rsp+0E8h+var_98], r14
0x18007cfe5  movsxd  r13, r15d
0x18007cfe8  mov     rax, [rdx+20h]
0x18007cfec  shl     r13, 5
0x18007cff0  cmp     r15d, 1
0x18007cff4  mov     [rsp+0E8h+var_B8], r13
0x18007cff9  mov     rcx, [rax+r13]
0x18007cffd  mov     [rsp+0E8h+var_50], rcx
0x18007d005  mov     rax, [rdx+20h]
0x18007d009  mov     rcx, [rax+r13+18h]
0x18007d00e  lea     rax, aTrigger; "trigger"
0x18007d015  mov     [rsp+0E8h+var_48], rax
0x18007d01d  setz    [rsp+0E8h+var_58]
0x18007d025  mov     [rsp+0E8h+var_60], rcx
0x18007d02d  lea     rax, [rsp+0E8h+var_A8]
0x18007d032  mov     [rsp+0E8h+var_40], rax
0x18007d03a  lea     rcx, [rsp+0E8h+var_98]
0x18007d03f  lea     rax, fixExprCb
0x18007d046  mov     [rsp+0E8h+var_90], r14
0x18007d04b  mov     [rsp+0E8h+var_88], rax
0x18007d050  lea     rax, fixSelectCb
0x18007d057  mov     [rsp+0E8h+var_80], rax
0x18007d05c  lea     rax, ?LoggerTrace@Database@Storage@Desktop@CapabilityAccess@Internal@Windows@@YAXPEAXPEBD@Z; Windows::Internal::CapabilityAccess::Desktop::Storage::Database::LoggerTrace(void *,char const *)
0x18007d063  mov     [rsp+0E8h+var_78], rax
0x18007d068  lea     rax, [rsp+0E8h+var_98]
0x18007d06d  mov     [rsp+0E8h+var_68], rax
0x18007d075  mov     [rsp+0E8h+var_70], r12d
0x18007d07a  mov     [rsp+0E8h+var_6C], r12w
0x18007d080  mov     rdx, [rsi+38h]
0x18007d084  call    sqlite3FixTriggerStep
0x18007d089  test    eax, eax
0x18007d08b  jnz     loc_18007D30C
0x18007d091  mov     rdx, [rsi+18h]
0x18007d095  test    rdx, rdx
0x18007d098  jz      short loc_18007D0AC
0x18007d09a  lea     rcx, [rsp+0E8h+var_90]
0x18007d09f  call    sqlite3WalkExprNN
0x18007d0a4  test    eax, eax
0x18007d0a6  jnz     loc_18007D30C
0x18007d0ac  cmp     byte ptr [r14+12Ch], 2
0x18007d0b4  jb      short loc_18007D10E
0x18007d0b6  mov     [r14+168h], rsi
0x18007d0bd  mov     rsi, r12
0x18007d0c0  lea     r12, [rdi+0C5h]
0x18007d0c7  mov     r14, [rsp+0E8h+arg_0]
0x18007d0cf  cmp     byte ptr [r12], 0
0x18007d0d4  jz      loc_18007D30C
0x18007d0da  mov     rax, [rdi+20h]
0x18007d0de  mov     r8, rsi
0x18007d0e1  mov     rdx, r14
0x18007d0e4  mov     rbx, rsi
0x18007d0e7  mov     rcx, [rax+r13+18h]
0x18007d0ec  add     rcx, 38h ; '8'
0x18007d0f0  call    sqlite3HashInsert
0x18007d0f5  mov     rsi, rax
0x18007d0f8  test    rax, rax
0x18007d0fb  jz      loc_18007D2E2
0x18007d101  mov     rcx, rdi
0x18007d104  call    sqlite3OomFault
0x18007d109  jmp     loc_18007D30C
0x18007d10e  lea     r12, [rdi+0C5h]
0x18007d115  cmp     byte ptr [r12], 0
0x18007d11a  jnz     short loc_18007D0C7
0x18007d11c  mov     rcx, rdi
0x18007d11f  call    sqlite3ReadOnlyShadowTables
0x18007d124  test    eax, eax
0x18007d126  jz      short loc_18007D15B
0x18007d128  mov     rbx, [rsi+38h]
0x18007d12c  test    rbx, rbx
0x18007d12f  jz      short loc_18007D153
0x18007d131  mov     rdx, [rbx+18h]
0x18007d135  test    rdx, rdx
0x18007d138  jz      short loc_18007D14A
0x18007d13a  mov     rcx, rdi
0x18007d13d  call    sqlite3ShadowTableName
0x18007d142  test    eax, eax
0x18007d144  jnz     loc_18007D1EB
0x18007d14a  mov     rbx, [rbx+50h]
0x18007d14e  test    rbx, rbx
0x18007d151  jnz     short loc_18007D131
0x18007d153  mov     rbx, [rsp+0E8h+arg_10]
0x18007d15b  mov     r13, [r14+10h]
0x18007d15f  test    r13, r13
0x18007d162  jnz     short loc_18007D18F
0x18007d164  cmp     [r14+0A8h], r13
0x18007d16b  jnz     short loc_18007D17B
0x18007d16d  mov     rax, [r14]
0x18007d170  test    byte ptr [rax+60h], 8
0x18007d174  jnz     short loc_18007D17B
0x18007d176  mov     byte ptr [r14+23h], 1
0x18007d17b  mov     rcx, r14
0x18007d17e  call    sqlite3VdbeCreate
0x18007d183  mov     r13, rax
0x18007d186  test    rax, rax
0x18007d189  jz      loc_18007D30C
0x18007d18f  mov     r8d, r15d
0x18007d192  xor     edx, edx
0x18007d194  mov     rcx, r14
0x18007d197  call    sqlite3BeginWriteOperation
0x18007d19c  mov     rax, [rbx]
0x18007d19f  mov     [rsp+0E8h+Src], rax
0x18007d1a4  test    rax, rax
0x18007d1a7  jz      short loc_18007D206
0x18007d1a9  mov     eax, [rbx+8]
0x18007d1ac  mov     rcx, rdi
0x18007d1af  mov     [rsp+0E8h+Size], rax
0x18007d1b7  lea     rdx, [rax+1]
0x18007d1bb  call    sqlite3DbMallocRawNN
0x18007d1c0  mov     rbx, rax
0x18007d1c3  test    rax, rax
0x18007d1c6  jz      short loc_18007D208
0x18007d1c8  mov     r8, [rsp+0E8h+Size]; Size
0x18007d1d0  mov     rcx, rax; void *
0x18007d1d3  mov     rdx, [rsp+0E8h+Src]; Src
0x18007d1d8  call    memcpy_0
0x18007d1dd  mov     rax, [rsp+0E8h+Size]
0x18007d1e5  mov     byte ptr [rax+rbx], 0
0x18007d1e9  jmp     short loc_18007D208
0x18007d1eb  mov     r9, [rbx+18h]
0x18007d1ef  lea     rdx, aTriggerSMayNot; "trigger \"%s\" may not write to shadow "...
0x18007d1f6  mov     r8, [rsi]
0x18007d1f9  mov     rcx, r14
0x18007d1fc  call    sqlite3ErrorMsg
0x18007d201  jmp     loc_18007D30C
0x18007d206  xor     ebx, ebx
0x18007d208  mov     rax, [rsi+8]
0x18007d20c  lea     rdx, aInsertIntoQSql_0; "INSERT INTO %Q.sqlite_master VALUES('tr"...
0x18007d213  mov     r8, [rdi+20h]
0x18007d217  mov     rcx, r14
0x18007d21a  mov     r9, [rsp+0E8h+arg_0]
0x18007d222  mov     [rsp+0E8h+var_C0], rbx
0x18007d227  mov     [rsp+0E8h+var_C8], rax
0x18007d22c  mov     rax, [rsp+0E8h+var_B8]
0x18007d231  mov     r8, [r8+rax]
0x18007d235  call    sqlite3NestedParse
0x18007d23a  test    rbx, rbx
0x18007d23d  jz      short loc_18007D29F
0x18007d23f  cmp     rbx, [rdi+1F0h]
0x18007d246  jnb     short loc_18007D280
0x18007d248  cmp     rbx, [rdi+1E0h]
0x18007d24f  jb      short loc_18007D264
0x18007d251  mov     rax, [rdi+1D8h]
0x18007d258  mov     [rbx], rax
0x18007d25b  mov     [rdi+1D8h], rbx
0x18007d262  jmp     short loc_18007D29F
0x18007d264  cmp     rbx, [rdi+1E8h]
0x18007d26b  jb      short loc_18007D280
0x18007d26d  mov     rax, [rdi+1C8h]
0x18007d274  mov     [rbx], rax
0x18007d277  mov     [rdi+1C8h], rbx
0x18007d27e  jmp     short loc_18007D29F
0x18007d280  cmp     qword ptr [rdi+308h], 0
0x18007d288  jz      short loc_18007D297
0x18007d28a  mov     rdx, rbx
0x18007d28d  mov     rcx, rdi
0x18007d290  call    measureAllocationSize
0x18007d295  jmp     short loc_18007D29F
0x18007d297  mov     rcx, rbx
0x18007d29a  call    sqlite3_free
0x18007d29f  mov     edx, r15d
0x18007d2a2  mov     rcx, r14
0x18007d2a5  call    sqlite3ChangeCookie
0x18007d2aa  mov     r14, [rsp+0E8h+arg_0]
0x18007d2b2  lea     rdx, aTypeTriggerAnd; "type='trigger' AND name='%q'"
0x18007d2b9  mov     r8, r14
0x18007d2bc  mov     rcx, rdi
0x18007d2bf  xor     ebx, ebx
0x18007d2c1  call    sqlite3MPrintf
0x18007d2c6  mov     r8, rax
0x18007d2c9  movzx   r9d, bx
0x18007d2cd  mov     edx, r15d
0x18007d2d0  mov     rcx, r13
0x18007d2d3  call    sqlite3VdbeAddParseSchemaOp
0x18007d2d8  mov     r13, [rsp+0E8h+var_B8]
0x18007d2dd  jmp     loc_18007D0CF
0x18007d2e2  mov     rcx, [rbx+30h]
0x18007d2e6  cmp     [rbx+28h], rcx
0x18007d2ea  jnz     short loc_18007D30C
0x18007d2ec  mov     rdx, [rbx+8]
0x18007d2f0  add     rcx, 8
0x18007d2f4  xor     r8d, r8d
0x18007d2f7  call    findElementWithHash
0x18007d2fc  mov     rdx, [rax+10h]
0x18007d300  mov     rax, [rdx+58h]
0x18007d304  mov     [rbx+40h], rax
0x18007d308  mov     [rdx+58h], rbx
0x18007d30c  mov     r13, [rsp+0E8h+arg_8]
0x18007d314  mov     r15, [rsp+0E8h+var_38]
0x18007d31c  mov     rdx, rsi
0x18007d31f  mov     rcx, rdi
0x18007d322  call    sqlite3DeleteTrigger
0x18007d327  mov     rdx, rbp
0x18007d32a  mov     rcx, rdi
0x18007d32d  call    sqlite3DeleteTriggerStep
0x18007d332  add     rsp, 0B8h
0x18007d339  pop     r14
0x18007d33b  pop     r12
0x18007d33d  pop     rdi
0x18007d33e  pop     rsi
0x18007d33f  pop     rbp
0x18007d340  pop     rbx
0x18007d341  retn
```
