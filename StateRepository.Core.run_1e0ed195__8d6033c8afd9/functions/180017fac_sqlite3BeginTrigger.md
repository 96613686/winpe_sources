# sqlite3BeginTrigger

- ea: `0x180017fac`
- end: `0x1800184c4`
- name: `sqlite3BeginTrigger`
- size: `1304`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x180031b38`

## callees

- `0x18000a9e0`
- `0x18000c960`
- `0x18000ca30`
- `0x18000cbb8`
- `0x18000f720`
- `0x18000fd7c`
- `0x1800150f4`
- `0x180016250`
- `0x180016574`
- `0x180017fac`
- `0x1800184cc`
- `0x180019d20`
- `0x180019da4`
- `0x1800398f0`
- `0x18003e1e0`
- `0x18003f6dc`
- `0x18003fe98`
- `0x180046630`
- `0x180053eb0`
- `0x180060ce8`
- `0x180068404`
- `0x18006910e`
- `0x1800864b0`

## string_xrefs

- `0x1800182b7`: `cannot create trigger on system table`
- `0x1800183a1`: `sqlite_temp_master`
- `0x180018015`: `temporary trigger may not have qualified name`
- `0x180018108`: `cannot create triggers on virtual tables`
- `0x1800181af`: `cannot create triggers on shadow tables`
- `0x180018236`: `trigger %T already exists`
- `0x1800182ed`: `cannot create %s trigger on view: %S`
- `0x18001830b`: `cannot create INSTEAD OF trigger on table: %S`

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
  __int64 v11; // r12
  int v15; // r13d
  unsigned int v16; // ebp
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // r14
  __int64 result; // rax
  __int64 v21; // rax
  _BYTE *v22; // r8
  const char *v23; // r9
  int v24; // edx
  const char *v25; // r8
  int v26; // eax
  int v27; // r10d
  int v28; // r11d
  __int64 v29; // rdx
  int v30; // r15d
  __int64 v31; // r13
  __int64 v32; // rcx
  const char *v33; // r8
  int v34; // r15d
  __int64 v35; // rax
  __int64 v36; // r9
  __int64 v37; // [rsp+30h] [rbp-A8h] BYREF
  _BYTE v38[152]; // [rsp+40h] [rbp-98h] BYREF
  __int64 v39; // [rsp+E0h] [rbp+8h]

  v10 = *a1;
  v11 = 0;
  v39 = 0;
  v37 = 0;
  v15 = a4;
  memset_0(v38, 0, 0x60u);
  if ( a9 )
  {
    if ( *(_DWORD *)(a3 + 8) )
    {
      sqlite3ErrorMsg(a1, "temporary trigger may not have qualified name");
      goto LABEL_25;
    }
    v16 = 1;
  }
  else
  {
    v16 = sqlite3TwoPartName(a1, a2, a3, &v37);
    if ( (v16 & 0x80000000) != 0 )
      goto LABEL_25;
    a2 = v37;
  }
  if ( a7 && !*(_BYTE *)(v10 + 103) )
  {
    if ( *(_BYTE *)(v10 + 197) && v16 != 1 )
    {
      sqlite3DbFree(v10, *(_QWORD *)(a7 + 80));
      *(_QWORD *)(a7 + 80) = 0;
    }
    v17 = sqlite3SrcListLookup(a1, a7);
    if ( !*(_BYTE *)(v10 + 197)
      && !*(_DWORD *)(a3 + 8)
      && v17
      && *(_QWORD *)(v17 + 96) == *(_QWORD *)(*(_QWORD *)(v10 + 32) + 56LL) )
    {
      v16 = 1;
    }
    if ( !*(_BYTE *)(v10 + 103) )
    {
      sqlite3FixInit((unsigned int)v38, (_DWORD)a1, v16, (unsigned int)"trigger", a2);
      if ( !(unsigned int)sqlite3FixSrcList(v38, a7) )
      {
        v18 = sqlite3SrcListLookup(a1, a7);
        v19 = v18;
        if ( !v18 )
          goto LABEL_23;
        if ( *(_BYTE *)(v18 + 63) == 1 )
        {
          sqlite3ErrorMsg(a1, "cannot create triggers on virtual tables");
          goto LABEL_23;
        }
        if ( (*(_DWORD *)(v18 + 48) & 0x1000) != 0 && (unsigned int)sqlite3ReadOnlyShadowTables(v10) )
        {
          sqlite3ErrorMsg(a1, "cannot create triggers on shadow tables");
          goto LABEL_23;
        }
        v21 = sqlite3NameFromToken(v10, a2);
        v39 = v21;
        if ( !v21 || (unsigned int)sqlite3CheckObjectName(a1, v21, "trigger", *(_QWORD *)v19) )
          goto LABEL_25;
        if ( *((_BYTE *)a1 + 308) < 2u
          && *(_QWORD *)(findElementWithHash(*(_QWORD *)(32LL * v16 + *(_QWORD *)(v10 + 32) + 24) + 56LL, v39, 0) + 16) )
        {
          if ( a10 )
            sqlite3CodeVerifySchema(a1, v16);
          else
            sqlite3ErrorMsg(a1, "trigger %T already exists", a2);
          goto LABEL_25;
        }
        if ( *(_QWORD *)v19 )
        {
          v22 = *(_BYTE **)v19;
          v23 = "sqlite_";
          v24 = 7;
          while ( 1 )
          {
            --v24;
            if ( !*v22
              || *((_BYTE *)qword_18009E760 + (unsigned __int8)*v22) != *((_BYTE *)qword_18009E760
                                                                        + *(unsigned __int8 *)v23) )
            {
              break;
            }
            ++v22;
            ++v23;
            if ( v24 <= 0 )
            {
              --v24;
              break;
            }
          }
          if ( v24 < 0
            || *((unsigned __int8 *)qword_18009E760 + (unsigned __int8)*v22) == *((unsigned __int8 *)qword_18009E760
                                                                                + *(unsigned __int8 *)v23) )
          {
            sqlite3ErrorMsg(a1, "cannot create trigger on system table");
            goto LABEL_25;
          }
        }
        if ( *(_BYTE *)(v19 + 63) == 2 )
        {
          if ( v15 != 66 )
          {
            v25 = "BEFORE";
            if ( v15 != 33 )
              v25 = "AFTER";
            sqlite3ErrorMsg(a1, "cannot create %s trigger on view: %S", v25, (const wchar_t *)(a7 + 8));
            goto LABEL_23;
          }
        }
        else if ( v15 == 66 )
        {
          sqlite3ErrorMsg(a1, "cannot create INSTEAD OF trigger on table: %S", (const wchar_t *)(a7 + 8));
LABEL_23:
          if ( *(_BYTE *)(v10 + 196) == 1 )
            *(_DWORD *)(v10 + 200) |= 1u;
          goto LABEL_25;
        }
        if ( *((_BYTE *)a1 + 308) >= 2u )
          goto LABEL_68;
        v26 = sqlite3SchemaToIndex(v10, *(_QWORD *)(v19 + 96));
        v29 = *(_QWORD *)(v10 + 32);
        v30 = v26;
        v31 = *(_QWORD *)(32LL * v26 + v29);
        if ( a9 )
          v32 = *(_QWORD *)(v29 + 32);
        else
          v32 = *(_QWORD *)(32LL * v26 + v29);
        if ( v26 == v28 || a9 )
          v27 = 5;
        if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, v27, v39, *(_QWORD *)v19, v32) )
        {
          v33 = "sqlite_temp_master";
          if ( v30 != 1 )
            v33 = "sqlite_master";
          if ( !(unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v33, 0, v31) )
          {
            v15 = a4;
LABEL_68:
            v34 = 33;
            if ( v15 != 66 )
              v34 = v15;
            v11 = sqlite3DbMallocZero(v10, 72);
            if ( v11 )
            {
              *(_QWORD *)v11 = v39;
              v39 = 0;
              v35 = sqlite3DbStrDup(v10, *(_QWORD *)(a7 + 8));
              *(_QWORD *)(v11 + 8) = v35;
              *(_QWORD *)(v11 + 40) = *(_QWORD *)(32LL * v16 + *(_QWORD *)(v10 + 32) + 24);
              *(_QWORD *)(v11 + 48) = *(_QWORD *)(v19 + 96);
              *(_BYTE *)(v11 + 16) = a5;
              *(_BYTE *)(v11 + 17) = (v34 != 33) + 1;
              if ( *((_BYTE *)a1 + 308) < 2u )
              {
                v36 = sqlite3ExprDup(v10, a8, 1);
              }
              else
              {
                sqlite3RenameTokenRemap(a1, v35, *(_QWORD *)(a7 + 8), a8);
                a8 = 0;
              }
              *(_QWORD *)(v11 + 24) = v36;
              *(_QWORD *)(v11 + 32) = a6;
              a1[46] = v11;
              a6 = 0;
            }
          }
        }
      }
    }
  }
LABEL_25:
  sqlite3DbFree(v10, v39);
  sqlite3SrcListDelete(v10, a7);
  result = sqlite3IdListDelete(v10, a6);
  if ( a8 )
    result = sqlite3ExprDeleteNN(v10);
  if ( !a1[46] )
    return sqlite3DeleteTrigger(v10, v11);
  return result;
}

```

## disassembly

```asm
0x180017fac  mov     [rsp+arg_8], rbx
0x180017fb1  mov     [rsp+arg_18], r9d
0x180017fb6  push    rbp
0x180017fb7  push    rsi
0x180017fb8  push    rdi
0x180017fb9  push    r12
0x180017fbb  push    r13
0x180017fbd  push    r14
0x180017fbf  push    r15
0x180017fc1  sub     rsp, 0A0h
0x180017fc8  mov     rdi, [rcx]
0x180017fcb  xor     r12d, r12d
0x180017fce  mov     r14, r8
0x180017fd1  mov     [rsp+0D8h+arg_0], r12
0x180017fd9  mov     r15, rdx
0x180017fdc  mov     [rsp+0D8h+var_A8], r12
0x180017fe1  mov     rbx, rcx
0x180017fe4  xor     edx, edx; Val
0x180017fe6  lea     r8d, [r12+60h]; Size
0x180017feb  mov     r13d, r9d
0x180017fee  lea     rcx, [rsp+0D8h+var_98]; void *
0x180017ff3  call    memset_0
0x180017ff8  lea     eax, [r12+1]
0x180017ffd  mov     rsi, [rsp+0D8h+arg_30]
0x180018005  cmp     [rsp+0D8h+arg_40], r12d
0x18001800d  jz      short loc_18001802D
0x18001800f  cmp     [r14+8], r12d
0x180018013  jbe     short loc_180018029
0x180018015  lea     rdx, aTemporaryTrigg; "temporary trigger may not have qualifie"...
0x18001801c  mov     rcx, rbx
0x18001801f  call    sqlite3ErrorMsg
0x180018024  jmp     loc_18001812A
0x180018029  mov     ebp, eax
0x18001802b  jmp     short loc_180018054
0x18001802d  lea     r9, [rsp+0D8h+var_A8]
0x180018032  mov     r8, r14
0x180018035  mov     rdx, r15
0x180018038  mov     rcx, rbx
0x18001803b  call    sqlite3TwoPartName
0x180018040  mov     ebp, eax
0x180018042  test    eax, eax
0x180018044  js      loc_18001812A
0x18001804a  mov     r15, [rsp+0D8h+var_A8]
0x18001804f  mov     eax, 1
0x180018054  test    rsi, rsi
0x180018057  jz      loc_18001812A
0x18001805d  cmp     [rdi+67h], r12b
0x180018061  jnz     loc_18001812A
0x180018067  cmp     [rdi+0C5h], r12b
0x18001806e  jz      short loc_180018084
0x180018070  cmp     ebp, eax
0x180018072  jz      short loc_180018084
0x180018074  mov     rdx, [rsi+50h]
0x180018078  mov     rcx, rdi
0x18001807b  call    sqlite3DbFree
0x180018080  mov     [rsi+50h], r12
0x180018084  mov     rdx, rsi
0x180018087  mov     rcx, rbx
0x18001808a  call    sqlite3SrcListLookup
0x18001808f  xor     edx, edx
0x180018091  mov     rcx, rax
0x180018094  cmp     [rdi+0C5h], dl
0x18001809a  jnz     short loc_1800180B9
0x18001809c  cmp     [r14+8], edx
0x1800180a0  jnz     short loc_1800180B9
0x1800180a2  test    rax, rax
0x1800180a5  jz      short loc_1800180B9
0x1800180a7  mov     rax, [rdi+20h]
0x1800180ab  mov     rax, [rax+38h]
0x1800180af  cmp     [rcx+60h], rax
0x1800180b3  lea     ecx, [rdx+1]
0x1800180b6  cmovz   ebp, ecx
0x1800180b9  cmp     [rdi+67h], dl
0x1800180bc  jnz     short loc_18001812A
0x1800180be  lea     r9, aTrigger; "trigger"
0x1800180c5  mov     [rsp+0D8h+var_B8], r15
0x1800180ca  mov     r8d, ebp
0x1800180cd  lea     rcx, [rsp+0D8h+var_98]
0x1800180d2  mov     rdx, rbx
0x1800180d5  call    sqlite3FixInit
0x1800180da  mov     rdx, rsi
0x1800180dd  lea     rcx, [rsp+0D8h+var_98]
0x1800180e2  call    sqlite3FixSrcList
0x1800180e7  test    eax, eax
0x1800180e9  jnz     short loc_18001812A
0x1800180eb  mov     rdx, rsi
0x1800180ee  mov     rcx, rbx
0x1800180f1  call    sqlite3SrcListLookup
0x1800180f6  mov     r14, rax
0x1800180f9  test    rax, rax
0x1800180fc  jz      short loc_180018117
0x1800180fe  cmp     byte ptr [rax+3Fh], 1
0x180018102  jnz     loc_18001819A
0x180018108  lea     rdx, aCannotCreateTr; "cannot create triggers on virtual table"...
0x18001810f  mov     rcx, rbx
0x180018112  call    sqlite3ErrorMsg
0x180018117  mov     eax, 1
0x18001811c  cmp     [rdi+0C4h], al
0x180018122  jnz     short loc_18001812A
0x180018124  or      [rdi+0C8h], eax
0x18001812a  mov     rdx, [rsp+0D8h+arg_0]
0x180018132  mov     rcx, rdi
0x180018135  call    sqlite3DbFree
0x18001813a  mov     rdx, rsi
0x18001813d  mov     rcx, rdi
0x180018140  call    sqlite3SrcListDelete
0x180018145  mov     rdx, [rsp+0D8h+arg_28]
0x18001814d  mov     rcx, rdi
0x180018150  call    sqlite3IdListDelete
0x180018155  mov     rdx, [rsp+0D8h+arg_38]
0x18001815d  test    rdx, rdx
0x180018160  jz      short loc_18001816A
0x180018162  mov     rcx, rdi
0x180018165  call    sqlite3ExprDeleteNN
0x18001816a  cmp     qword ptr [rbx+170h], 0
0x180018172  jnz     short loc_18001817F
0x180018174  mov     rdx, r12
0x180018177  mov     rcx, rdi
0x18001817a  call    sqlite3DeleteTrigger
0x18001817f  mov     rbx, [rsp+0D8h+arg_8]
0x180018187  add     rsp, 0A0h
0x18001818e  pop     r15
0x180018190  pop     r14
0x180018192  pop     r13
0x180018194  pop     r12
0x180018196  pop     rdi
0x180018197  pop     rsi
0x180018198  pop     rbp
0x180018199  retn
0x18001819a  test    dword ptr [rax+30h], 1000h
0x1800181a1  jz      short loc_1800181BB
0x1800181a3  mov     rcx, rdi
0x1800181a6  call    sqlite3ReadOnlyShadowTables
0x1800181ab  test    eax, eax
0x1800181ad  jz      short loc_1800181BB
0x1800181af  lea     rdx, aCannotCreateTr_1; "cannot create triggers on shadow tables"
0x1800181b6  jmp     loc_18001810F
0x1800181bb  mov     rdx, r15
0x1800181be  mov     rcx, rdi
0x1800181c1  call    sqlite3NameFromToken
0x1800181c6  mov     [rsp+0D8h+arg_0], rax
0x1800181ce  test    rax, rax
0x1800181d1  jz      loc_18001812A
0x1800181d7  mov     r9, [r14]
0x1800181da  lea     r8, aTrigger; "trigger"
0x1800181e1  mov     rdx, rax
0x1800181e4  mov     rcx, rbx
0x1800181e7  call    sqlite3CheckObjectName
0x1800181ec  test    eax, eax
0x1800181ee  jnz     loc_18001812A
0x1800181f4  cmp     byte ptr [rbx+134h], 2
0x1800181fb  jnb     short loc_180018253
0x1800181fd  mov     rax, [rdi+20h]
0x180018201  xor     r8d, r8d
0x180018204  mov     rdx, [rsp+0D8h+arg_0]
0x18001820c  mov     ecx, ebp
0x18001820e  shl     rcx, 5
0x180018212  mov     rcx, [rcx+rax+18h]
0x180018217  add     rcx, 38h ; '8'
0x18001821b  call    findElementWithHash
0x180018220  cmp     [rax+10h], r12
0x180018224  jz      short loc_180018253
0x180018226  mov     rcx, rbx
0x180018229  cmp     [rsp+0D8h+arg_48], r12d
0x180018231  jnz     short loc_180018247
0x180018233  mov     r8, r15
0x180018236  lea     rdx, aTriggerTAlread; "trigger %T already exists"
0x18001823d  call    sqlite3ErrorMsg
0x180018242  jmp     loc_18001812A
0x180018247  mov     edx, ebp
0x180018249  call    sqlite3CodeVerifySchema
0x18001824e  jmp     loc_18001812A
0x180018253  mov     r10d, 7
0x180018259  lea     r11d, [r10-6]
0x18001825d  cmp     [r14], r12
0x180018260  jz      short loc_1800182C3
0x180018262  mov     r8, [r14]
0x180018265  lea     r9, aSqlite_0; "sqlite_"
0x18001826c  mov     edx, r10d
0x18001826f  lea     r15, qword_18009E760
0x180018276  sub     edx, r11d
0x180018279  cmp     [r8], r12b
0x18001827c  jz      short loc_18001829D
0x18001827e  movzx   eax, byte ptr [r9]
0x180018282  movzx   ecx, byte ptr [r8]
0x180018286  mov     al, [rax+r15]
0x18001828a  cmp     [rcx+r15], al
0x18001828e  jnz     short loc_18001829D
0x180018290  add     r8, r11
0x180018293  add     r9, r11
0x180018296  test    edx, edx
0x180018298  jg      short loc_180018276
0x18001829a  sub     edx, r11d
0x18001829d  test    edx, edx
0x18001829f  js      short loc_1800182B7
0x1800182a1  movzx   eax, byte ptr [r9]
0x1800182a5  movzx   ecx, byte ptr [rax+r15]
0x1800182aa  movzx   eax, byte ptr [r8]
0x1800182ae  movzx   eax, byte ptr [rax+r15]
0x1800182b3  cmp     eax, ecx
0x1800182b5  jnz     short loc_1800182C3
0x1800182b7  lea     rdx, aCannotCreateTr_0; "cannot create trigger on system table"
0x1800182be  jmp     loc_18001801C
0x1800182c3  cmp     byte ptr [r14+3Fh], 2
0x1800182c8  jnz     short loc_1800182FE
0x1800182ca  cmp     r13d, 42h ; 'B'
0x1800182ce  jz      short loc_18001831C
0x1800182d0  cmp     r13d, 21h ; '!'
0x1800182d4  lea     rax, aAfter; "AFTER"
0x1800182db  lea     r8, aBefore; "BEFORE"
0x1800182e2  mov     rcx, rbx
0x1800182e5  cmovnz  r8, rax
0x1800182e9  lea     r9, [rsi+8]
0x1800182ed  lea     rdx, aCannotCreateST; "cannot create %s trigger on view: %S"
0x1800182f4  call    sqlite3ErrorMsg
0x1800182f9  jmp     loc_180018117
0x1800182fe  cmp     r13d, 42h ; 'B'
0x180018302  jnz     short loc_18001831C
0x180018304  lea     r8, [rsi+8]
0x180018308  mov     rcx, rbx
0x18001830b  lea     rdx, aCannotCreateIn; "cannot create INSTEAD OF trigger on tab"...
0x180018312  call    sqlite3ErrorMsg
0x180018317  jmp     loc_180018117
0x18001831c  cmp     byte ptr [rbx+134h], 2
0x180018323  jnb     loc_1800183CA
0x180018329  mov     rdx, [r14+60h]
0x18001832d  mov     rcx, rdi
0x180018330  call    sqlite3SchemaToIndex
0x180018335  mov     rdx, [rdi+20h]
0x180018339  movsxd  r15, eax
0x18001833c  mov     eax, [rsp+0D8h+arg_40]
0x180018343  mov     rcx, r15
0x180018346  shl     rcx, 5
0x18001834a  mov     r13, [rcx+rdx]
0x18001834e  test    eax, eax
0x180018350  jz      short loc_180018358
0x180018352  mov     rcx, [rdx+20h]
0x180018356  jmp     short loc_18001835B
0x180018358  mov     rcx, r13
0x18001835b  cmp     r15d, r11d
0x18001835e  jz      short loc_180018364
0x180018360  test    eax, eax
0x180018362  jz      short loc_18001836A
0x180018364  mov     r10d, 5
0x18001836a  mov     r9, [r14]
0x18001836d  mov     edx, r10d
0x180018370  mov     r8, [rsp+0D8h+arg_0]
0x180018378  mov     [rsp+0D8h+var_B8], rcx
0x18001837d  mov     rcx, rbx
0x180018380  call    sqlite3AuthCheck
0x180018385  test    eax, eax
0x180018387  jnz     loc_18001812A
0x18001838d  mov     ecx, 1
0x180018392  mov     [rsp+0D8h+var_B8], r13
0x180018397  cmp     r15d, ecx
0x18001839a  lea     rax, aSqliteMaster; "sqlite_master"
0x1800183a1  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1800183a8  cmovnz  r8, rax
0x1800183ac  xor     r9d, r9d
0x1800183af  lea     edx, [rcx+11h]
0x1800183b2  mov     rcx, rbx
0x1800183b5  call    sqlite3AuthCheck
0x1800183ba  test    eax, eax
0x1800183bc  jnz     loc_18001812A
0x1800183c2  mov     r13d, [rsp+0D8h+arg_18]
0x1800183ca  cmp     r13d, 42h ; 'B'
0x1800183ce  mov     r15d, 21h ; '!'
0x1800183d4  mov     edx, 48h ; 'H'
0x1800183d9  mov     rcx, rdi
0x1800183dc  cmovnz  r15d, r13d
0x1800183e0  call    sqlite3DbMallocZero
0x1800183e5  mov     r12, rax
0x1800183e8  test    rax, rax
0x1800183eb  jz      loc_18001812A
0x1800183f1  mov     rax, [rsp+0D8h+arg_0]
0x1800183f9  mov     rcx, rdi
0x1800183fc  mov     [r12], rax
0x180018400  mov     rdx, [rsi+8]
0x180018404  mov     [rsp+0D8h+arg_0], 0
0x180018410  call    sqlite3DbStrDup
0x180018415  mov     [r12+8], rax
0x18001841a  mov     rcx, [rdi+20h]
0x18001841e  mov     edx, ebp
0x180018420  shl     rdx, 5
0x180018424  cmp     r15d, 21h ; '!'
0x180018428  mov     rdx, [rdx+rcx+18h]
0x18001842d  mov     [r12+28h], rdx
0x180018432  mov     edx, 1
0x180018437  mov     rcx, [r14+60h]
0x18001843b  mov     [r12+30h], rcx
0x180018440  mov     cl, [rsp+0D8h+arg_20]
0x180018447  mov     [r12+10h], cl
0x18001844c  setnz   cl
0x18001844f  add     cl, dl
0x180018451  mov     [r12+11h], cl
0x180018456  cmp     byte ptr [rbx+134h], 2
0x18001845d  jb      short loc_180018484
0x18001845f  mov     r8, [rsi+8]
0x180018463  mov     rdx, rax
0x180018466  mov     r9, [rsp+0D8h+arg_38]
  ... truncated ...
```
