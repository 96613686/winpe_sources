# sqlite3FinishTrigger

- ea: `0x18007922c`
- end: `0x18007950e`
- name: `sqlite3FinishTrigger`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: ``

## callers

- `0x1800c3bd8`

## callees

- `0x180002cf8`
- `0x180047054`
- `0x180069d64`
- `0x18006db58`
- `0x1800716fc`
- `0x180071aac`
- `0x18007281c`
- `0x18007289c`
- `0x180073aec`
- `0x18007922c`
- `0x180079514`
- `0x180079610`
- `0x18007d478`
- `0x18007d618`
- `0x180080b64`
- `0x1800817f4`
- `0x180081a3c`
- `0x1800892a0`
- `0x18008dd8c`
- `0x180092638`
- `0x18009ee3c`

## string_xrefs

- `0x18007940e`: `INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')`
- `0x1800794a6`: `trigger "%s" may not write to shadow table "%s"`

## pseudocode

```c
__int64 __fastcall sqlite3FinishTrigger(__int64 *a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rdi
  __int64 v5; // rsi
  __int64 v8; // rcx
  int v9; // r15d
  __int64 v10; // rbp
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // r8
  __int64 v16; // rdx
  _BYTE *v17; // r14
  __int64 i; // rbp
  __int64 v19; // rdx
  __int64 Vdbe; // rbp
  __int64 v21; // r12
  __int64 v22; // rax
  _QWORD *v23; // rbx
  __int64 v24; // rcx
  __int64 v25; // rdx
  __int128 v27; // [rsp+30h] [rbp-B8h] BYREF
  _BYTE v28[8]; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v29[160]; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+F0h] [rbp+8h]

  v3 = a1[46];
  v5 = *a1;
  memset_0(v28, 0, 0x60u);
  v27 = 0;
  a1[46] = 0;
  if ( !*((_DWORD *)a1 + 12) && v3 )
  {
    v8 = *(_QWORD *)(v3 + 40);
    v9 = -32768;
    v10 = *(_QWORD *)v3;
    v30 = *(_QWORD *)v3;
    if ( v8 )
    {
      v11 = *(_QWORD *)(v5 + 32);
      v9 = 0;
      if ( *(_QWORD *)(v11 + 24) != v8 )
      {
        do
          ++v9;
        while ( *(_QWORD *)(32LL * v9 + v11 + 24) != v8 );
      }
    }
    *(_QWORD *)(v3 + 56) = a2;
    while ( a2 )
    {
      *(_QWORD *)(a2 + 8) = v3;
      a2 = *(_QWORD *)(a2 + 80);
    }
    v12 = *(_QWORD *)v3;
    *(_QWORD *)&v27 = v12;
    if ( v12 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_BYTE *)(v12 + v14) );
      v13 = v14 & 0x3FFFFFFF;
    }
    else
    {
      v13 = 0;
    }
    DWORD2(v27) = v13;
    sqlite3FixInit((unsigned int)v28, (_DWORD)a1, v9, (unsigned int)"trigger", (__int64)&v27);
    if ( !(unsigned int)sqlite3FixTriggerStep(v28, *(_QWORD *)(v3 + 56)) )
    {
      v16 = *(_QWORD *)(v3 + 24);
      if ( !v16 || !(unsigned int)sqlite3WalkExprNN(v29, v16, v15) )
      {
        if ( *((_BYTE *)a1 + 308) >= 2u )
        {
          a1[46] = v3;
          v3 = 0;
          v17 = (_BYTE *)(v5 + 197);
          goto LABEL_30;
        }
        v17 = (_BYTE *)(v5 + 197);
        if ( *(_BYTE *)(v5 + 197) )
        {
LABEL_31:
          v23 = (_QWORD *)v3;
          v3 = sqlite3HashInsert(*(_QWORD *)(32LL * v9 + *(_QWORD *)(v5 + 32) + 24) + 56LL, v10, v3);
          if ( v3 )
          {
            sqlite3OomFault(v5);
          }
          else
          {
            v24 = v23[6];
            if ( v23[5] == v24 )
            {
              v25 = *(_QWORD *)(findElementWithHash(v24 + 8, v23[1], 0) + 16);
              v23[8] = *(_QWORD *)(v25 + 88);
              *(_QWORD *)(v25 + 88) = v23;
            }
          }
          goto LABEL_36;
        }
        if ( (unsigned int)sqlite3ReadOnlyShadowTables(v5) )
        {
          for ( i = *(_QWORD *)(v3 + 56); i; i = *(_QWORD *)(i + 80) )
          {
            v19 = *(_QWORD *)(i + 24);
            if ( v19 && (unsigned int)sqlite3ShadowTableName(v5, v19) )
            {
              sqlite3ErrorMsg(
                a1,
                "trigger \"%s\" may not write to shadow table \"%s\"",
                *(const char **)v3,
                *(const char **)(i + 24));
              goto LABEL_36;
            }
          }
        }
        Vdbe = sqlite3GetVdbe(a1);
        if ( Vdbe )
        {
          sqlite3BeginWriteOperation(a1, 0, (unsigned int)v9);
          v21 = sqlite3DbStrNDup(v5, *(_QWORD *)a3, *(unsigned int *)(a3 + 8));
          sqlite3NestedParse(
            a1,
            "INSERT INTO %Q.sqlite_master VALUES('trigger',%Q,%Q,0,'CREATE TRIGGER %q')",
            *(_QWORD *)(32LL * v9 + *(_QWORD *)(v5 + 32)),
            v30,
            *(_QWORD *)(v3 + 8),
            v21,
            (_QWORD)v27);
          if ( v21 )
            sqlite3DbFreeNN(v5);
          sqlite3ChangeCookie(a1, (unsigned int)v9);
          v22 = sqlite3MPrintf(v5, "type='trigger' AND name='%q'", v30);
          sqlite3VdbeAddParseSchemaOp(Vdbe, (unsigned int)v9, v22, 0);
          v10 = v30;
LABEL_30:
          if ( !*v17 )
            goto LABEL_36;
          goto LABEL_31;
        }
      }
    }
  }
LABEL_36:
  sqlite3DeleteTrigger(v5, v3);
  return sqlite3DeleteTriggerStep(v5, a2);
}

```

## disassembly

```asm
0x18007922c  push    rbx
0x18007922e  push    rbp
0x18007922f  push    rsi
0x180079230  push    rdi
0x180079231  push    r12
0x180079233  push    r13
0x180079235  push    r14
0x180079237  push    r15
0x180079239  sub     rsp, 0A8h
0x180079240  mov     rdi, [rcx+170h]
0x180079247  mov     r13, rdx
0x18007924a  mov     rsi, [rcx]
0x18007924d  xor     edx, edx; Val
0x18007924f  mov     r12, r8
0x180079252  mov     rbx, rcx
0x180079255  lea     rcx, [rsp+0E8h+var_A8]; void *
0x18007925a  lea     r8d, [rdx+60h]; Size
0x18007925e  call    memset_0
0x180079263  xor     r14d, r14d
0x180079266  xorps   xmm0, xmm0
0x180079269  movups  [rsp+0E8h+var_B8], xmm0
0x18007926e  mov     [rbx+170h], r14
0x180079275  cmp     [rbx+30h], r14d
0x180079279  jnz     loc_1800794E4
0x18007927f  test    rdi, rdi
0x180079282  jz      loc_1800794E4
0x180079288  mov     rcx, [rdi+28h]
0x18007928c  mov     r15d, 0FFFF8000h
0x180079292  mov     rbp, [rdi]
0x180079295  mov     [rsp+0E8h+arg_0], rbp
0x18007929d  test    rcx, rcx
0x1800792a0  jz      short loc_1800792C0
0x1800792a2  mov     rdx, [rsi+20h]
0x1800792a6  mov     r15d, r14d
0x1800792a9  cmp     [rdx+18h], rcx
0x1800792ad  jz      short loc_1800792C0
0x1800792af  inc     r15d
0x1800792b2  movsxd  rax, r15d
0x1800792b5  shl     rax, 5
0x1800792b9  cmp     [rax+rdx+18h], rcx
0x1800792be  jnz     short loc_1800792AF
0x1800792c0  mov     [rdi+38h], r13
0x1800792c4  jmp     short loc_1800792CE
0x1800792c6  mov     [r13+8], rdi
0x1800792ca  mov     r13, [r13+50h]
0x1800792ce  test    r13, r13
0x1800792d1  jnz     short loc_1800792C6
0x1800792d3  mov     rcx, [rdi]
0x1800792d6  mov     qword ptr [rsp+0E8h+var_B8], rcx
0x1800792db  test    rcx, rcx
0x1800792de  jnz     short loc_1800792E5
0x1800792e0  mov     eax, r14d
0x1800792e3  jmp     short loc_1800792F7
0x1800792e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800792e9  inc     rax
0x1800792ec  cmp     [rcx+rax], r14b
0x1800792f0  jnz     short loc_1800792E9
0x1800792f2  and     eax, 3FFFFFFFh
0x1800792f7  mov     dword ptr [rsp+0E8h+var_B8+8], eax
0x1800792fb  lea     r9, aTrigger; "trigger"
0x180079302  lea     rax, [rsp+0E8h+var_B8]
0x180079307  mov     r8d, r15d
0x18007930a  mov     rdx, rbx
0x18007930d  mov     [rsp+0E8h+var_C8], rax
0x180079312  lea     rcx, [rsp+0E8h+var_A8]
0x180079317  call    sqlite3FixInit
0x18007931c  mov     rdx, [rdi+38h]
0x180079320  lea     rcx, [rsp+0E8h+var_A8]
0x180079325  call    sqlite3FixTriggerStep
0x18007932a  test    eax, eax
0x18007932c  jnz     loc_1800794E4
0x180079332  mov     rdx, [rdi+18h]
0x180079336  test    rdx, rdx
0x180079339  jz      short loc_18007934D
0x18007933b  lea     rcx, [rsp+0E8h+var_A0]
0x180079340  call    sqlite3WalkExprNN
0x180079345  test    eax, eax
0x180079347  jnz     loc_1800794E4
0x18007934d  cmp     byte ptr [rbx+134h], 2
0x180079354  jb      short loc_18007936C
0x180079356  mov     [rbx+170h], rdi
0x18007935d  mov     rdi, r14
0x180079360  lea     r14, [rsi+0C5h]
0x180079367  jmp     loc_180079468
0x18007936c  lea     r14, [rsi+0C5h]
0x180079373  cmp     byte ptr [r14], 0
0x180079377  jnz     loc_18007946E
0x18007937d  mov     rcx, rsi
0x180079380  call    sqlite3ReadOnlyShadowTables
0x180079385  test    eax, eax
0x180079387  jz      short loc_1800793B1
0x180079389  mov     rbp, [rdi+38h]
0x18007938d  jmp     short loc_1800793AC
0x18007938f  mov     rdx, [rbp+18h]
0x180079393  test    rdx, rdx
0x180079396  jz      short loc_1800793A8
0x180079398  mov     rcx, rsi
0x18007939b  call    sqlite3ShadowTableName
0x1800793a0  test    eax, eax
0x1800793a2  jnz     loc_1800794A2
0x1800793a8  mov     rbp, [rbp+50h]
0x1800793ac  test    rbp, rbp
0x1800793af  jnz     short loc_18007938F
0x1800793b1  mov     rcx, rbx
0x1800793b4  call    sqlite3GetVdbe
0x1800793b9  mov     rbp, rax
0x1800793bc  test    rax, rax
0x1800793bf  jz      loc_1800794E4
0x1800793c5  mov     r8d, r15d
0x1800793c8  xor     edx, edx
0x1800793ca  mov     rcx, rbx
0x1800793cd  call    sqlite3BeginWriteOperation
0x1800793d2  mov     r8d, [r12+8]
0x1800793d7  mov     rcx, rsi
0x1800793da  mov     rdx, [r12]
0x1800793de  call    sqlite3DbStrNDup
0x1800793e3  mov     rcx, [rdi+8]
0x1800793e7  mov     r12, rax
0x1800793ea  mov     r8, [rsi+20h]
0x1800793ee  mov     r9, [rsp+0E8h+arg_0]
0x1800793f6  mov     [rsp+0E8h+var_C0], rax
0x1800793fb  mov     [rsp+0E8h+var_C8], rcx
0x180079400  mov     rcx, rbx
0x180079403  movsxd  rdx, r15d
0x180079406  shl     rdx, 5
0x18007940a  mov     r8, [rdx+r8]
0x18007940e  lea     rdx, aInsertIntoQSql_0; "INSERT INTO %Q.sqlite_master VALUES('tr"...
0x180079415  call    sqlite3NestedParse
0x18007941a  test    r12, r12
0x18007941d  jz      short loc_18007942A
0x18007941f  mov     rdx, r12
0x180079422  mov     rcx, rsi
0x180079425  call    sqlite3DbFreeNN
0x18007942a  mov     edx, r15d
0x18007942d  mov     rcx, rbx
0x180079430  call    sqlite3ChangeCookie
0x180079435  mov     r8, [rsp+0E8h+arg_0]
0x18007943d  lea     rdx, aTypeTriggerAnd; "type='trigger' AND name='%q'"
0x180079444  mov     rcx, rsi
0x180079447  xor     ebx, ebx
0x180079449  call    sqlite3MPrintf
0x18007944e  mov     r8, rax
0x180079451  movzx   r9d, bx
0x180079455  mov     edx, r15d
0x180079458  mov     rcx, rbp
0x18007945b  call    sqlite3VdbeAddParseSchemaOp
0x180079460  mov     rbp, [rsp+0E8h+arg_0]
0x180079468  cmp     byte ptr [r14], 0
0x18007946c  jz      short loc_1800794E4
0x18007946e  mov     rax, [rsi+20h]
0x180079472  mov     r8, rdi
0x180079475  movsxd  rcx, r15d
0x180079478  mov     rdx, rbp
0x18007947b  shl     rcx, 5
0x18007947f  mov     rbx, rdi
0x180079482  mov     rcx, [rcx+rax+18h]
0x180079487  add     rcx, 38h ; '8'
0x18007948b  call    sqlite3HashInsert
0x180079490  mov     rdi, rax
0x180079493  test    rax, rax
0x180079496  jz      short loc_1800794BA
0x180079498  mov     rcx, rsi
0x18007949b  call    sqlite3OomFault
0x1800794a0  jmp     short loc_1800794E4
0x1800794a2  mov     r9, [rbp+18h]
0x1800794a6  lea     rdx, aTriggerSMayNot; "trigger \"%s\" may not write to shadow "...
0x1800794ad  mov     r8, [rdi]
0x1800794b0  mov     rcx, rbx
0x1800794b3  call    sqlite3ErrorMsg
0x1800794b8  jmp     short loc_1800794E4
0x1800794ba  mov     rcx, [rbx+30h]
0x1800794be  cmp     [rbx+28h], rcx
0x1800794c2  jnz     short loc_1800794E4
0x1800794c4  mov     rdx, [rbx+8]
0x1800794c8  add     rcx, 8
0x1800794cc  xor     r8d, r8d
0x1800794cf  call    findElementWithHash
0x1800794d4  mov     rdx, [rax+10h]
0x1800794d8  mov     rax, [rdx+58h]
0x1800794dc  mov     [rbx+40h], rax
0x1800794e0  mov     [rdx+58h], rbx
0x1800794e4  mov     rdx, rdi
0x1800794e7  mov     rcx, rsi
0x1800794ea  call    sqlite3DeleteTrigger
0x1800794ef  mov     rdx, r13
0x1800794f2  mov     rcx, rsi
0x1800794f5  call    sqlite3DeleteTriggerStep
0x1800794fa  add     rsp, 0A8h
0x180079501  pop     r15
0x180079503  pop     r14
0x180079505  pop     r13
0x180079507  pop     r12
0x180079509  pop     rdi
0x18007950a  pop     rsi
0x18007950b  pop     rbp
0x18007950c  pop     rbx
0x18007950d  retn
```
