# sqlite3StartTable

- ea: `0x18008e690`
- end: `0x18008ebc3`
- name: `sqlite3StartTable`
- size: `1331`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x180071400`
- `0x18009d930`
- `0x1800c3bd8`

## callees

- `0x1800693b0`
- `0x180069d64`
- `0x18006db9c`
- `0x18006ed2c`
- `0x1800716fc`
- `0x1800718ac`
- `0x180071a38`
- `0x180073aec`
- `0x180078bec`
- `0x180078c74`
- `0x18007a3e4`
- `0x18007d478`
- `0x180081754`
- `0x1800892e4`
- `0x180089ed4`
- `0x18008e690`
- `0x18008f3d8`
- `0x18008fa90`
- `0x1800923d8`
- `0x1800924d4`
- `0x1800927e0`
- `0x18009a3b4`
- `0x18009d734`

## string_xrefs

- `0x18008e6ad`: `sqlite_temp_master`
- `0x18008e8bc`: `%s %T already exists`
- `0x18008e92d`: `there is already an index named %s`
- `0x18008e72f`: `temporary table name must be unqualified`

## pseudocode

```c
__int64 __fastcall sqlite3StartTable(__int64 *a1, _OWORD *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  __int64 v7; // rsi
  const char *v8; // r13
  _OWORD *v11; // rbp
  unsigned int v13; // r14d
  const char *v14; // rdx
  __int64 result; // rax
  const char *v16; // rbx
  _BYTE *v17; // r15
  const char *v18; // r12
  const char *v19; // r8
  int v20; // edx
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // r13d
  __int64 Table; // rax
  __int64 v25; // rax
  __int64 v26; // rdx
  __int64 v27; // rcx
  __int64 v28; // rbp
  int v29; // eax
  int v30; // r15d
  int v31; // r12d
  int v32; // ecx
  unsigned int v33; // ebx
  int Vdbe; // ebx
  int v35; // r9d
  int v36; // ebx
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // [rsp+30h] [rbp-48h]
  __int64 v40; // [rsp+38h] [rbp-40h]
  _OWORD *v41; // [rsp+80h] [rbp+8h] BYREF
  int v42; // [rsp+98h] [rbp+20h]

  v42 = a4;
  v7 = *a1;
  v8 = "sqlite_temp_master";
  v41 = 0;
  v11 = a2;
  if ( *(_BYTE *)(v7 + 197) && *(_DWORD *)(v7 + 192) == 1 )
  {
    v13 = *(unsigned __int8 *)(v7 + 196);
    v14 = "sqlite_temp_master";
    if ( v13 != 1 )
      v14 = "sqlite_master";
    result = sqlite3DbStrDup(v7, v14);
    v16 = (const char *)result;
    v17 = (char *)a1 + 308;
  }
  else
  {
    result = sqlite3TwoPartName(a1, a2, a3, &v41);
    v13 = result;
    if ( (int)result < 0 )
      return result;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && (_DWORD)result != 1 )
        return sqlite3ErrorMsg(a1, "temporary table name must be unqualified");
      v13 = 1;
    }
    v11 = v41;
    result = sqlite3NameFromToken(v7, v41);
    v17 = (char *)a1 + 308;
    v16 = (const char *)result;
    if ( *((_BYTE *)a1 + 308) >= 2u )
      result = sqlite3RenameTokenMap(a1, result, v11);
  }
  *((_OWORD *)a1 + 17) = *v11;
  if ( v16 )
  {
    v18 = "view";
    v19 = "view";
    if ( !a5 )
      v19 = "table";
    if ( (unsigned int)sqlite3CheckObjectName(a1, v16, v19, v16) )
      goto LABEL_32;
    v20 = 1;
    v21 = *(_QWORD *)(v7 + 32);
    if ( *(_BYTE *)(v7 + 196) != 1 )
      v20 = v42;
    v39 = 32LL * v13;
    LODWORD(v41) = v20;
    v22 = *(_QWORD *)(v39 + v21);
    if ( v20 != 1 )
      v8 = "sqlite_master";
    v40 = v22;
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v8, 0, v22) )
      goto LABEL_32;
    v23 = a6;
    if ( !a6 )
    {
      if ( (unsigned int)sqlite3AuthCheck(
                           (_DWORD)a1,
                           *((unsigned __int8 *)&dword_1800FBA54 + 2 * a5 + (int)v41),
                           (_DWORD)v16,
                           0,
                           v40) )
        goto LABEL_32;
    }
    if ( !*v17 )
    {
      v41 = *(_OWORD **)(v39 + *(_QWORD *)(v7 + 32));
      if ( (unsigned int)sqlite3ReadSchema(a1) )
      {
LABEL_32:
        *((_BYTE *)a1 + 29) = 1;
        return sqlite3DbFreeNN(v7);
      }
      Table = sqlite3FindTable(v7, v16, v41);
      if ( Table )
      {
        if ( a7 )
        {
          sqlite3CodeVerifySchema(a1, v13);
          sqlite3ForceNotReadOnly(a1);
        }
        else
        {
          if ( *(_BYTE *)(Table + 63) != 2 )
            v18 = "table";
          sqlite3ErrorMsg(a1, "%s %T already exists", v18, v11);
        }
        goto LABEL_32;
      }
      if ( sqlite3FindIndex(v7, v16, v41) )
      {
        sqlite3ErrorMsg(a1, "there is already an index named %s", v16);
        goto LABEL_32;
      }
    }
    v25 = sqlite3DbMallocZero(v7, 104);
    v26 = v25;
    if ( !v25 )
    {
      ++*((_DWORD *)a1 + 12);
      *((_DWORD *)a1 + 6) = 7;
      goto LABEL_32;
    }
    *(_QWORD *)v25 = v16;
    *(_WORD *)(v25 + 52) = -1;
    result = *(_QWORD *)(v7 + 32);
    v27 = *(_QWORD *)(result + v39 + 24);
    *(_DWORD *)(v26 + 44) = 1;
    *(_QWORD *)(v26 + 96) = v27;
    *(_WORD *)(v26 + 58) = 200;
    a1[44] = v26;
    if ( !*(_BYTE *)(v7 + 197) )
    {
      result = sqlite3GetVdbe(a1);
      v28 = result;
      if ( result )
      {
        sqlite3BeginWriteOperation(a1, 1, v13);
        if ( v23 )
          sqlite3VdbeAddOp3(v28, 170, 0, 0, 0);
        v29 = *((_DWORD *)a1 + 14) + 1;
        LODWORD(v41) = v29;
        *((_DWORD *)a1 + 34) = v29;
        v30 = v29 + 1;
        v31 = v29 + 2;
        *((_DWORD *)a1 + 35) = v29 + 1;
        *((_DWORD *)a1 + 14) = v29 + 2;
        sqlite3VdbeAddOp3(v28, 99, v13, v29 + 2, 2);
        sqlite3VdbeUsesBtree(v28, v13);
        v33 = sqlite3VdbeAddOp3(v32, 16, v31, 0, 0);
        sqlite3VdbeAddOp3(v28, 100, v13, 2, (*(_BYTE *)(v7 + 48) & 2) != 0 ? 1 : 4);
        sqlite3VdbeAddOp3(v28, 100, v13, 5, *(unsigned __int8 *)(v7 + 100));
        sqlite3VdbeJumpHere(v28, v33);
        if ( a5 || v23 )
          sqlite3VdbeAddOp3(v28, 71, 0, v30, 0);
        else
          *((_DWORD *)a1 + 52) = sqlite3VdbeAddOp3(v28, 147, v13, v30, 1);
        Vdbe = sqlite3GetVdbe(a1);
        LOBYTE(v35) = 1;
        sqlite3TableLock((_DWORD)a1, v13, 1, v35, (__int64)"sqlite_master");
        sqlite3VdbeAddOp4Int(Vdbe, 113, 0, 1, v13, 5);
        if ( !*((_DWORD *)a1 + 13) )
          *((_DWORD *)a1 + 13) = 1;
        v36 = (int)v41;
        sqlite3VdbeAddOp3(v28, 127, 0, (_DWORD)v41, 0);
        v37 = sqlite3VdbeAddOp3(v28, 77, 6, v31, 0);
        sqlite3VdbeChangeP4(v28, v37, &dword_1800FAA4C, 0xFFFFFFFFLL);
        sqlite3VdbeAddOp3(v28, 128, 0, v31, v36);
        v38 = *(int *)(v28 + 144);
        if ( (int)v38 > 0 )
          *(_WORD *)(*(_QWORD *)(v28 + 136) + 24 * v38 - 22) = 8;
        return sqlite3VdbeAddOp3(v28, 122, 0, 0, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18008e690  mov     rax, rsp
0x18008e693  mov     [rax+10h], rbx
0x18008e697  mov     [rax+20h], r9d
0x18008e69b  push    rbp
0x18008e69c  push    rsi
0x18008e69d  push    rdi
0x18008e69e  push    r12
0x18008e6a0  push    r13
0x18008e6a2  push    r14
0x18008e6a4  push    r15
0x18008e6a6  sub     rsp, 40h
0x18008e6aa  mov     rsi, [rcx]
0x18008e6ad  lea     r13, aSqliteTempMast; "sqlite_temp_master"
0x18008e6b4  xor     r12d, r12d
0x18008e6b7  mov     r15d, r9d
0x18008e6ba  mov     [rax+8], r12
0x18008e6be  mov     rbx, r8
0x18008e6c1  mov     rbp, rdx
0x18008e6c4  lea     rax, aSqliteMaster; "sqlite_master"
0x18008e6cb  mov     rdi, rcx
0x18008e6ce  cmp     [rsi+0C5h], r12b
0x18008e6d5  jz      short loc_18008E707
0x18008e6d7  cmp     dword ptr [rsi+0C0h], 1
0x18008e6de  jnz     short loc_18008E707
0x18008e6e0  movzx   r14d, byte ptr [rsi+0C4h]
0x18008e6e8  mov     rdx, r13
0x18008e6eb  cmp     r14d, 1
0x18008e6ef  mov     rcx, rsi
0x18008e6f2  cmovnz  rdx, rax
0x18008e6f6  call    sqlite3DbStrDup
0x18008e6fb  mov     rbx, rax
0x18008e6fe  lea     r15, [rdi+134h]
0x18008e705  jmp     short loc_18008E77A
0x18008e707  lea     r9, [rsp+78h+arg_0]
0x18008e70f  call    sqlite3TwoPartName
0x18008e714  mov     r14d, eax
0x18008e717  test    eax, eax
0x18008e719  js      loc_18008E8E8
0x18008e71f  test    r15d, r15d
0x18008e722  jz      short loc_18008E749
0x18008e724  cmp     [rbx+8], r12d
0x18008e728  jbe     short loc_18008E743
0x18008e72a  cmp     eax, 1
0x18008e72d  jz      short loc_18008E743
0x18008e72f  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x18008e736  mov     rcx, rdi
0x18008e739  call    sqlite3ErrorMsg
0x18008e73e  jmp     loc_18008E8E8
0x18008e743  mov     r14d, 1
0x18008e749  mov     rbp, [rsp+78h+arg_0]
0x18008e751  mov     rcx, rsi
0x18008e754  mov     rdx, rbp
0x18008e757  call    sqlite3NameFromToken
0x18008e75c  lea     r15, [rdi+134h]
0x18008e763  mov     rbx, rax
0x18008e766  cmp     byte ptr [r15], 2
0x18008e76a  jb      short loc_18008E77A
0x18008e76c  mov     r8, rbp
0x18008e76f  mov     rdx, rax
0x18008e772  mov     rcx, rdi
0x18008e775  call    sqlite3RenameTokenMap
0x18008e77a  movups  xmm0, xmmword ptr [rbp+0]
0x18008e77e  movdqu  xmmword ptr [rdi+110h], xmm0
0x18008e786  test    rbx, rbx
0x18008e789  jz      loc_18008E8E8
0x18008e78f  cmp     [rsp+78h+arg_20], 0
0x18008e797  lea     rax, aTable; "table"
0x18008e79e  lea     r12, aView_0; "view"
0x18008e7a5  mov     r9, rbx
0x18008e7a8  mov     r8, r12
0x18008e7ab  mov     rdx, rbx
0x18008e7ae  cmovz   r8, rax
0x18008e7b2  mov     rcx, rdi
0x18008e7b5  call    sqlite3CheckObjectName
0x18008e7ba  test    eax, eax
0x18008e7bc  jnz     loc_18008E8D9
0x18008e7c2  lea     edx, [rax+1]
0x18008e7c5  mov     ecx, r14d
0x18008e7c8  cmp     [rsi+0C4h], dl
0x18008e7ce  mov     rax, [rsi+20h]
0x18008e7d2  cmovnz  edx, [rsp+78h+arg_18]
0x18008e7da  shl     rcx, 5
0x18008e7de  mov     [rsp+78h+var_48], rcx
0x18008e7e3  cmp     edx, 1
0x18008e7e6  mov     dword ptr [rsp+78h+arg_0], edx
0x18008e7ed  mov     rax, [rcx+rax]
0x18008e7f1  lea     rcx, aSqliteMaster; "sqlite_master"
0x18008e7f8  cmovnz  r13, rcx
0x18008e7fc  mov     [rsp+78h+var_40], rax
0x18008e801  xor     r9d, r9d
0x18008e804  mov     [rsp+78h+var_58], rax
0x18008e809  mov     r8, r13
0x18008e80c  mov     rcx, rdi
0x18008e80f  lea     edx, [r9+12h]
0x18008e813  call    sqlite3AuthCheck
0x18008e818  test    eax, eax
0x18008e81a  jnz     loc_18008E8D9
0x18008e820  mov     r13d, [rsp+78h+arg_28]
0x18008e828  test    r13d, r13d
0x18008e82b  jnz     short loc_18008E868
0x18008e82d  mov     eax, dword ptr [rsp+78h+arg_0]
0x18008e834  xor     r9d, r9d
0x18008e837  mov     ecx, [rsp+78h+arg_20]
0x18008e83e  mov     r8, rbx
0x18008e841  lea     eax, [rax+rcx*2]
0x18008e844  movsxd  rcx, eax
0x18008e847  lea     rax, dword_1800FBA54
0x18008e84e  movzx   edx, byte ptr [rcx+rax]
0x18008e852  mov     rcx, rdi
0x18008e855  mov     rax, [rsp+78h+var_40]
0x18008e85a  mov     [rsp+78h+var_58], rax
0x18008e85f  call    sqlite3AuthCheck
0x18008e864  test    eax, eax
0x18008e866  jnz     short loc_18008E8D9
0x18008e868  cmp     byte ptr [r15], 0
0x18008e86c  mov     r15, [rsp+78h+var_48]
0x18008e871  jnz     loc_18008E93E
0x18008e877  mov     rax, [rsi+20h]
0x18008e87b  mov     rcx, rdi
0x18008e87e  mov     rax, [r15+rax]
0x18008e882  mov     [rsp+78h+arg_0], rax
0x18008e88a  call    sqlite3ReadSchema
0x18008e88f  test    eax, eax
0x18008e891  jnz     short loc_18008E8D9
0x18008e893  mov     r8, [rsp+78h+arg_0]
0x18008e89b  mov     rdx, rbx
0x18008e89e  mov     rcx, rsi
0x18008e8a1  call    sqlite3FindTable
0x18008e8a6  test    rax, rax
0x18008e8a9  jz      short loc_18008E912
0x18008e8ab  cmp     [rsp+78h+arg_30], 0
0x18008e8b3  mov     rcx, rdi
0x18008e8b6  jnz     short loc_18008E900
0x18008e8b8  cmp     byte ptr [rax+3Fh], 2
0x18008e8bc  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x18008e8c3  lea     rax, aTable; "table"
0x18008e8ca  mov     r9, rbp
0x18008e8cd  cmovnz  r12, rax
0x18008e8d1  mov     r8, r12
0x18008e8d4  call    sqlite3ErrorMsg
0x18008e8d9  mov     rdx, rbx
0x18008e8dc  mov     byte ptr [rdi+1Dh], 1
0x18008e8e0  mov     rcx, rsi
0x18008e8e3  call    sqlite3DbFreeNN
0x18008e8e8  mov     rbx, [rsp+78h+arg_8]
0x18008e8f0  add     rsp, 40h
0x18008e8f4  pop     r15
0x18008e8f6  pop     r14
0x18008e8f8  pop     r13
0x18008e8fa  pop     r12
0x18008e8fc  pop     rdi
0x18008e8fd  pop     rsi
0x18008e8fe  pop     rbp
0x18008e8ff  retn
0x18008e900  mov     edx, r14d
0x18008e903  call    sqlite3CodeVerifySchema
0x18008e908  mov     rcx, rdi
0x18008e90b  call    sqlite3ForceNotReadOnly
0x18008e910  jmp     short loc_18008E8D9
0x18008e912  mov     r8, [rsp+78h+arg_0]
0x18008e91a  mov     rdx, rbx
0x18008e91d  mov     rcx, rsi
0x18008e920  call    sqlite3FindIndex
0x18008e925  test    rax, rax
0x18008e928  jz      short loc_18008E93E
0x18008e92a  mov     r8, rbx
0x18008e92d  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x18008e934  mov     rcx, rdi
0x18008e937  call    sqlite3ErrorMsg
0x18008e93c  jmp     short loc_18008E8D9
0x18008e93e  mov     edx, 68h ; 'h'
0x18008e943  mov     rcx, rsi
0x18008e946  call    sqlite3DbMallocZero
0x18008e94b  mov     rdx, rax
0x18008e94e  test    rax, rax
0x18008e951  jnz     short loc_18008E962
0x18008e953  inc     dword ptr [rdi+30h]
0x18008e956  mov     dword ptr [rdi+18h], 7
0x18008e95d  jmp     loc_18008E8D9
0x18008e962  mov     [rax], rbx
0x18008e965  xor     ebx, ebx
0x18008e967  mov     word ptr [rax+34h], 0FFFFh
0x18008e96d  mov     rax, [rsi+20h]
0x18008e971  mov     rcx, [rax+r15+18h]
0x18008e976  mov     r15d, 1
0x18008e97c  mov     [rdx+2Ch], r15d
0x18008e980  mov     [rdx+60h], rcx
0x18008e984  mov     word ptr [rdx+3Ah], 0C8h
0x18008e98a  mov     [rdi+160h], rdx
0x18008e991  cmp     [rsi+0C5h], bl
0x18008e997  jnz     loc_18008E8E8
0x18008e99d  mov     rcx, rdi
0x18008e9a0  call    sqlite3GetVdbe
0x18008e9a5  mov     rbp, rax
0x18008e9a8  test    rax, rax
0x18008e9ab  jz      loc_18008E8E8
0x18008e9b1  mov     r8d, r14d
0x18008e9b4  mov     edx, r15d
0x18008e9b7  mov     rcx, rdi
0x18008e9ba  call    sqlite3BeginWriteOperation
0x18008e9bf  test    r13d, r13d
0x18008e9c2  jz      short loc_18008E9DB
0x18008e9c4  xor     r9d, r9d
0x18008e9c7  mov     dword ptr [rsp+78h+var_58], ebx
0x18008e9cb  xor     r8d, r8d
0x18008e9ce  mov     edx, 0AAh
0x18008e9d3  mov     rcx, rbp
0x18008e9d6  call    sqlite3VdbeAddOp3
0x18008e9db  mov     eax, [rdi+38h]
0x18008e9de  mov     r8d, r14d
0x18008e9e1  inc     eax
0x18008e9e3  mov     dword ptr [rsp+78h+var_58], 2
0x18008e9eb  mov     edx, 63h ; 'c'
0x18008e9f0  mov     dword ptr [rsp+78h+arg_0], eax
0x18008e9f7  mov     rcx, rbp
0x18008e9fa  mov     [rdi+88h], eax
0x18008ea00  lea     r15d, [rax+1]
0x18008ea04  lea     r12d, [r15+1]
0x18008ea08  mov     [rdi+8Ch], r15d
0x18008ea0f  mov     r9d, r12d
0x18008ea12  mov     [rdi+38h], r12d
0x18008ea16  call    sqlite3VdbeAddOp3
0x18008ea1b  mov     edx, r14d
0x18008ea1e  mov     rcx, rbp
0x18008ea21  call    sqlite3VdbeUsesBtree
0x18008ea26  xor     r9d, r9d
0x18008ea29  mov     dword ptr [rsp+78h+var_58], ebx
0x18008ea2d  mov     r8d, r12d
0x18008ea30  lea     edx, [r9+10h]
0x18008ea34  call    sqlite3VdbeAddOp3
0x18008ea39  mov     cl, [rsi+30h]
0x18008ea3c  mov     r9d, 2
0x18008ea42  and     cl, 2
0x18008ea45  mov     r8d, r14d
0x18008ea48  neg     cl
0x18008ea4a  mov     ebx, eax
0x18008ea4c  mov     rcx, rbp
0x18008ea4f  sbb     edx, edx
0x18008ea51  and     edx, 0FFFFFFFDh
0x18008ea54  add     edx, 4
0x18008ea57  mov     dword ptr [rsp+78h+var_58], edx
0x18008ea5b  lea     edx, [r9+62h]
0x18008ea5f  call    sqlite3VdbeAddOp3
0x18008ea64  movzx   eax, byte ptr [rsi+64h]
0x18008ea68  mov     r9d, 5
0x18008ea6e  mov     r8d, r14d
0x18008ea71  mov     dword ptr [rsp+78h+var_58], eax
0x18008ea75  mov     rcx, rbp
0x18008ea78  lea     edx, [r9+5Fh]
0x18008ea7c  call    sqlite3VdbeAddOp3
0x18008ea81  mov     edx, ebx
0x18008ea83  mov     rcx, rbp
0x18008ea86  call    sqlite3VdbeJumpHere
0x18008ea8b  xor     esi, esi
0x18008ea8d  cmp     [rsp+78h+arg_20], esi
0x18008ea94  jnz     short loc_18008EABE
0x18008ea96  test    r13d, r13d
0x18008ea99  jnz     short loc_18008EABE
0x18008ea9b  mov     r9d, r15d
0x18008ea9e  mov     dword ptr [rsp+78h+var_58], 1
0x18008eaa6  mov     r8d, r14d
0x18008eaa9  mov     edx, 93h
0x18008eaae  mov     rcx, rbp
0x18008eab1  call    sqlite3VdbeAddOp3
0x18008eab6  mov     [rdi+0D0h], eax
0x18008eabc  jmp     short loc_18008EAD4
0x18008eabe  xor     r8d, r8d
0x18008eac1  mov     dword ptr [rsp+78h+var_58], esi
0x18008eac5  mov     r9d, r15d
0x18008eac8  mov     rcx, rbp
0x18008eacb  lea     edx, [r8+47h]
0x18008eacf  call    sqlite3VdbeAddOp3
0x18008ead4  mov     rcx, rdi
0x18008ead7  call    sqlite3GetVdbe
0x18008eadc  mov     rbx, rax
0x18008eadf  mov     r15d, 1
0x18008eae5  lea     rax, aSqliteMaster; "sqlite_master"
0x18008eaec  mov     r9b, r15b
0x18008eaef  mov     r8d, r15d
0x18008eaf2  mov     [rsp+78h+var_58], rax
0x18008eaf7  mov     edx, r14d
0x18008eafa  mov     rcx, rdi
0x18008eafd  call    sqlite3TableLock
0x18008eb02  mov     r9d, r15d
0x18008eb05  mov     [rsp+78h+var_50], 5
0x18008eb0d  xor     r8d, r8d
0x18008eb10  mov     dword ptr [rsp+78h+var_58], r14d
0x18008eb15  lea     edx, [r15+70h]
0x18008eb19  mov     rcx, rbx
0x18008eb1c  call    sqlite3VdbeAddOp4Int
0x18008eb21  cmp     [rdi+34h], esi
0x18008eb24  jnz     short loc_18008EB2A
0x18008eb26  mov     [rdi+34h], r15d
0x18008eb2a  mov     ebx, dword ptr [rsp+78h+arg_0]
0x18008eb31  xor     r8d, r8d
0x18008eb34  mov     r9d, ebx
0x18008eb37  mov     dword ptr [rsp+78h+var_58], esi
0x18008eb3b  mov     rcx, rbp
0x18008eb3e  lea     edx, [r8+7Fh]
0x18008eb42  call    sqlite3VdbeAddOp3
  ... truncated ...
```
