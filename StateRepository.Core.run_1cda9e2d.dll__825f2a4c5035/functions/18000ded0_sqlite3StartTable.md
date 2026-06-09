# sqlite3StartTable

- ea: `0x18000ded0`
- end: `0x18000e3a6`
- name: `sqlite3StartTable`
- size: `1238`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x18000d480`
- `0x180031b38`
- `0x1800896b8`

## callees

- `0x180005c54`
- `0x18000a9e0`
- `0x18000ded0`
- `0x18000f720`
- `0x18000fd7c`
- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x1800139a4`
- `0x180013a00`
- `0x180014434`
- `0x1800150f4`
- `0x1800157d4`
- `0x180016574`
- `0x180036688`
- `0x1800398f0`
- `0x18003fe98`
- `0x18004d11c`
- `0x180053eb0`
- `0x180060ce8`
- `0x1800842a4`
- `0x1800859c4`
- `0x180086e98`

## string_xrefs

- `0x18000deed`: `sqlite_temp_master`
- `0x18000df6c`: `temporary table name must be unqualified`
- `0x18000e0f7`: `%s %T already exists`
- `0x18000e167`: `there is already an index named %s`

## pseudocode

```c
__int64 __fastcall sqlite3StartTable(__int64 *a1, _OWORD *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  __int64 v7; // rsi
  const char *v8; // r13
  _OWORD *v11; // r14
  unsigned int v13; // ebp
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
  __int64 v28; // r14
  int v29; // eax
  int v30; // r15d
  int v31; // r12d
  int v32; // ecx
  unsigned int v33; // ebx
  int v34; // ebx
  int v35; // ecx
  __int64 v36; // [rsp+40h] [rbp-48h]
  __int64 v37; // [rsp+48h] [rbp-40h]
  _OWORD *v38; // [rsp+90h] [rbp+8h] BYREF
  int v39; // [rsp+A8h] [rbp+20h]

  v39 = a4;
  v7 = *a1;
  v8 = "sqlite_temp_master";
  v38 = 0;
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
    result = sqlite3TwoPartName(a1, a2, a3, &v38);
    v13 = result;
    if ( (int)result < 0 )
      return result;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && (_DWORD)result != 1 )
        return sqlite3ErrorMsg(a1, "temporary table name must be unqualified");
      v13 = 1;
    }
    v11 = v38;
    result = sqlite3NameFromToken(v7, v38);
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
      v20 = v39;
    v36 = 32LL * v13;
    LODWORD(v38) = v20;
    v22 = *(_QWORD *)(v36 + v21);
    if ( v20 != 1 )
      v8 = "sqlite_master";
    v37 = v22;
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v8, 0, v22) )
      goto LABEL_32;
    v23 = a6;
    if ( !a6 )
    {
      if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, byte_18009EA54[2 * a5 + (int)v38], (_DWORD)v16, 0, v37) )
        goto LABEL_32;
    }
    if ( !*v17 )
    {
      v38 = *(_OWORD **)(v36 + *(_QWORD *)(v7 + 32));
      if ( (unsigned int)sqlite3ReadSchema(a1) )
      {
LABEL_32:
        *((_BYTE *)a1 + 29) = 1;
        return sqlite3DbFree(v7, v16);
      }
      Table = sqlite3FindTable(v7, v16, v38);
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
      if ( sqlite3FindIndex(v7, v16, v38) )
      {
        sqlite3ErrorMsg(a1, "there is already an index named %s", v16);
        goto LABEL_32;
      }
    }
    v25 = sqlite3DbMallocZero(v7, 104);
    v26 = v25;
    if ( !v25 )
    {
      ++*((_DWORD *)a1 + 13);
      *((_DWORD *)a1 + 6) = 7;
      goto LABEL_32;
    }
    *(_QWORD *)v25 = v16;
    *(_WORD *)(v25 + 52) = -1;
    result = *(_QWORD *)(v7 + 32);
    v27 = *(_QWORD *)(result + v36 + 24);
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
        v29 = *((_DWORD *)a1 + 15) + 1;
        LODWORD(v38) = v29;
        *((_DWORD *)a1 + 34) = v29;
        v30 = v29 + 1;
        v31 = v29 + 2;
        *((_DWORD *)a1 + 35) = v29 + 1;
        *((_DWORD *)a1 + 15) = v29 + 2;
        sqlite3VdbeAddOp3(v28, 99, v13, v29 + 2, 2);
        sqlite3VdbeUsesBtree(v28, v13);
        v33 = sqlite3VdbeAddOp3(v32, 16, v31, 0, 0);
        sqlite3VdbeAddOp3(v28, 100, v13, 2, (*(_BYTE *)(v7 + 48) & 2) != 0 ? 1 : 4);
        sqlite3VdbeAddOp3(v28, 100, v13, 5, *(unsigned __int8 *)(v7 + 100));
        *(_DWORD *)(sqlite3VdbeGetOp(v28, v33) + 8) = *(_DWORD *)(v28 + 144);
        if ( a5 || v23 )
          sqlite3VdbeAddOp3(v28, 71, 0, v30, 0);
        else
          *((_DWORD *)a1 + 52) = sqlite3VdbeAddOp3(v28, 147, v13, v30, 1);
        sqlite3OpenSchemaTable(a1, v13);
        v34 = (int)v38;
        sqlite3VdbeAddOp3(v28, 127, 0, (_DWORD)v38, 0);
        sqlite3VdbeAddOp4(v28, 77, 6, v31, 0, (__int64)&unk_1800A6A78, -1);
        sqlite3VdbeAddOp3(v28, 128, 0, v31, v34);
        sqlite3VdbeChangeP5(v28, 8);
        return sqlite3VdbeAddOp3(v35, 122, 0, 0, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ded0  mov     rax, rsp
0x18000ded3  mov     [rax+10h], rbx
0x18000ded7  mov     [rax+20h], r9d
0x18000dedb  push    rbp
0x18000dedc  push    rsi
0x18000dedd  push    rdi
0x18000dede  push    r12
0x18000dee0  push    r13
0x18000dee2  push    r14
0x18000dee4  push    r15
0x18000dee6  sub     rsp, 50h
0x18000deea  mov     rsi, [rcx]
0x18000deed  lea     r13, aSqliteTempMast; "sqlite_temp_master"
0x18000def4  xor     r12d, r12d
0x18000def7  mov     r15d, r9d
0x18000defa  mov     [rax+8], r12
0x18000defe  mov     rbx, r8
0x18000df01  mov     r14, rdx
0x18000df04  lea     rax, aSqliteMaster; "sqlite_master"
0x18000df0b  mov     rdi, rcx
0x18000df0e  cmp     [rsi+0C5h], r12b
0x18000df15  jz      short loc_18000DF45
0x18000df17  cmp     dword ptr [rsi+0C0h], 1
0x18000df1e  jnz     short loc_18000DF45
0x18000df20  movzx   ebp, byte ptr [rsi+0C4h]
0x18000df27  mov     rdx, r13
0x18000df2a  cmp     ebp, 1
0x18000df2d  mov     rcx, rsi
0x18000df30  cmovnz  rdx, rax
0x18000df34  call    sqlite3DbStrDup
0x18000df39  mov     rbx, rax
0x18000df3c  lea     r15, [rdi+134h]
0x18000df43  jmp     short loc_18000DFB6
0x18000df45  lea     r9, [rsp+88h+arg_0]
0x18000df4d  call    sqlite3TwoPartName
0x18000df52  mov     ebp, eax
0x18000df54  test    eax, eax
0x18000df56  js      loc_18000E123
0x18000df5c  test    r15d, r15d
0x18000df5f  jz      short loc_18000DF85
0x18000df61  cmp     [rbx+8], r12d
0x18000df65  jbe     short loc_18000DF80
0x18000df67  cmp     eax, 1
0x18000df6a  jz      short loc_18000DF80
0x18000df6c  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x18000df73  mov     rcx, rdi
0x18000df76  call    sqlite3ErrorMsg
0x18000df7b  jmp     loc_18000E123
0x18000df80  mov     ebp, 1
0x18000df85  mov     r14, [rsp+88h+arg_0]
0x18000df8d  mov     rcx, rsi
0x18000df90  mov     rdx, r14
0x18000df93  call    sqlite3NameFromToken
0x18000df98  lea     r15, [rdi+134h]
0x18000df9f  mov     rbx, rax
0x18000dfa2  cmp     byte ptr [r15], 2
0x18000dfa6  jb      short loc_18000DFB6
0x18000dfa8  mov     r8, r14
0x18000dfab  mov     rdx, rax
0x18000dfae  mov     rcx, rdi
0x18000dfb1  call    sqlite3RenameTokenMap
0x18000dfb6  movups  xmm0, xmmword ptr [r14]
0x18000dfba  movdqu  xmmword ptr [rdi+110h], xmm0
0x18000dfc2  test    rbx, rbx
0x18000dfc5  jz      loc_18000E123
0x18000dfcb  cmp     [rsp+88h+arg_20], 0
0x18000dfd3  lea     rax, aTable; "table"
0x18000dfda  lea     r12, aView_0; "view"
0x18000dfe1  mov     r9, rbx
0x18000dfe4  mov     r8, r12
0x18000dfe7  mov     rdx, rbx
0x18000dfea  cmovz   r8, rax
0x18000dfee  mov     rcx, rdi
0x18000dff1  call    sqlite3CheckObjectName
0x18000dff6  test    eax, eax
0x18000dff8  jnz     loc_18000E114
0x18000dffe  lea     edx, [rax+1]
0x18000e001  mov     ecx, ebp
0x18000e003  cmp     [rsi+0C4h], dl
0x18000e009  mov     rax, [rsi+20h]
0x18000e00d  cmovnz  edx, [rsp+88h+arg_18]
0x18000e015  shl     rcx, 5
0x18000e019  mov     [rsp+88h+var_48], rcx
0x18000e01e  cmp     edx, 1
0x18000e021  mov     dword ptr [rsp+88h+arg_0], edx
0x18000e028  mov     rax, [rcx+rax]
0x18000e02c  lea     rcx, aSqliteMaster; "sqlite_master"
0x18000e033  cmovnz  r13, rcx
0x18000e037  mov     [rsp+88h+var_40], rax
0x18000e03c  xor     r9d, r9d
0x18000e03f  mov     [rsp+88h+var_68], rax
0x18000e044  mov     r8, r13
0x18000e047  mov     rcx, rdi
0x18000e04a  lea     edx, [r9+12h]
0x18000e04e  call    sqlite3AuthCheck
0x18000e053  test    eax, eax
0x18000e055  jnz     loc_18000E114
0x18000e05b  mov     r13d, [rsp+88h+arg_28]
0x18000e063  test    r13d, r13d
0x18000e066  jnz     short loc_18000E0A3
0x18000e068  mov     eax, dword ptr [rsp+88h+arg_0]
0x18000e06f  xor     r9d, r9d
0x18000e072  mov     ecx, [rsp+88h+arg_20]
0x18000e079  mov     r8, rbx
0x18000e07c  lea     eax, [rax+rcx*2]
0x18000e07f  movsxd  rcx, eax
0x18000e082  lea     rax, byte_18009EA54
0x18000e089  movzx   edx, byte ptr [rcx+rax]
0x18000e08d  mov     rcx, rdi
0x18000e090  mov     rax, [rsp+88h+var_40]
0x18000e095  mov     [rsp+88h+var_68], rax
0x18000e09a  call    sqlite3AuthCheck
0x18000e09f  test    eax, eax
0x18000e0a1  jnz     short loc_18000E114
0x18000e0a3  cmp     byte ptr [r15], 0
0x18000e0a7  mov     r15, [rsp+88h+var_48]
0x18000e0ac  jnz     loc_18000E178
0x18000e0b2  mov     rax, [rsi+20h]
0x18000e0b6  mov     rcx, rdi
0x18000e0b9  mov     rax, [r15+rax]
0x18000e0bd  mov     [rsp+88h+arg_0], rax
0x18000e0c5  call    sqlite3ReadSchema
0x18000e0ca  test    eax, eax
0x18000e0cc  jnz     short loc_18000E114
0x18000e0ce  mov     r8, [rsp+88h+arg_0]
0x18000e0d6  mov     rdx, rbx
0x18000e0d9  mov     rcx, rsi
0x18000e0dc  call    sqlite3FindTable
0x18000e0e1  test    rax, rax
0x18000e0e4  jz      short loc_18000E14C
0x18000e0e6  cmp     [rsp+88h+arg_30], 0
0x18000e0ee  mov     rcx, rdi
0x18000e0f1  jnz     short loc_18000E13B
0x18000e0f3  cmp     byte ptr [rax+3Fh], 2
0x18000e0f7  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x18000e0fe  lea     rax, aTable; "table"
0x18000e105  mov     r9, r14
0x18000e108  cmovnz  r12, rax
0x18000e10c  mov     r8, r12
0x18000e10f  call    sqlite3ErrorMsg
0x18000e114  mov     rdx, rbx
0x18000e117  mov     byte ptr [rdi+1Dh], 1
0x18000e11b  mov     rcx, rsi
0x18000e11e  call    sqlite3DbFree
0x18000e123  mov     rbx, [rsp+88h+arg_8]
0x18000e12b  add     rsp, 50h
0x18000e12f  pop     r15
0x18000e131  pop     r14
0x18000e133  pop     r13
0x18000e135  pop     r12
0x18000e137  pop     rdi
0x18000e138  pop     rsi
0x18000e139  pop     rbp
0x18000e13a  retn
0x18000e13b  mov     edx, ebp
0x18000e13d  call    sqlite3CodeVerifySchema
0x18000e142  mov     rcx, rdi
0x18000e145  call    sqlite3ForceNotReadOnly
0x18000e14a  jmp     short loc_18000E114
0x18000e14c  mov     r8, [rsp+88h+arg_0]
0x18000e154  mov     rdx, rbx
0x18000e157  mov     rcx, rsi
0x18000e15a  call    sqlite3FindIndex
0x18000e15f  test    rax, rax
0x18000e162  jz      short loc_18000E178
0x18000e164  mov     r8, rbx
0x18000e167  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x18000e16e  mov     rcx, rdi
0x18000e171  call    sqlite3ErrorMsg
0x18000e176  jmp     short loc_18000E114
0x18000e178  mov     edx, 68h ; 'h'
0x18000e17d  mov     rcx, rsi
0x18000e180  call    sqlite3DbMallocZero
0x18000e185  mov     rdx, rax
0x18000e188  test    rax, rax
0x18000e18b  jnz     short loc_18000E19C
0x18000e18d  inc     dword ptr [rdi+34h]
0x18000e190  mov     dword ptr [rdi+18h], 7
0x18000e197  jmp     loc_18000E114
0x18000e19c  mov     [rax], rbx
0x18000e19f  xor     ebx, ebx
0x18000e1a1  mov     word ptr [rax+34h], 0FFFFh
0x18000e1a7  mov     rax, [rsi+20h]
0x18000e1ab  mov     rcx, [rax+r15+18h]
0x18000e1b0  mov     r15d, 1
0x18000e1b6  mov     [rdx+2Ch], r15d
0x18000e1ba  mov     [rdx+60h], rcx
0x18000e1be  mov     word ptr [rdx+3Ah], 0C8h
0x18000e1c4  mov     [rdi+160h], rdx
0x18000e1cb  cmp     [rsi+0C5h], bl
0x18000e1d1  jnz     loc_18000E123
0x18000e1d7  mov     rcx, rdi
0x18000e1da  call    sqlite3GetVdbe
0x18000e1df  mov     r14, rax
0x18000e1e2  test    rax, rax
0x18000e1e5  jz      loc_18000E123
0x18000e1eb  mov     r8d, ebp
0x18000e1ee  mov     edx, r15d
0x18000e1f1  mov     rcx, rdi
0x18000e1f4  call    sqlite3BeginWriteOperation
0x18000e1f9  test    r13d, r13d
0x18000e1fc  jz      short loc_18000E215
0x18000e1fe  xor     r9d, r9d
0x18000e201  mov     dword ptr [rsp+88h+var_68], ebx
0x18000e205  xor     r8d, r8d
0x18000e208  mov     edx, 0AAh
0x18000e20d  mov     rcx, r14
0x18000e210  call    sqlite3VdbeAddOp3
0x18000e215  mov     eax, [rdi+3Ch]
0x18000e218  mov     r8d, ebp
0x18000e21b  inc     eax
0x18000e21d  mov     dword ptr [rsp+88h+var_68], 2
0x18000e225  mov     edx, 63h ; 'c'
0x18000e22a  mov     dword ptr [rsp+88h+arg_0], eax
0x18000e231  mov     rcx, r14
0x18000e234  mov     [rdi+88h], eax
0x18000e23a  lea     r15d, [rax+1]
0x18000e23e  lea     r12d, [r15+1]
0x18000e242  mov     [rdi+8Ch], r15d
0x18000e249  mov     r9d, r12d
0x18000e24c  mov     [rdi+3Ch], r12d
0x18000e250  call    sqlite3VdbeAddOp3
0x18000e255  mov     edx, ebp
0x18000e257  mov     rcx, r14
0x18000e25a  call    sqlite3VdbeUsesBtree
0x18000e25f  xor     r9d, r9d
0x18000e262  mov     dword ptr [rsp+88h+var_68], ebx
0x18000e266  mov     r8d, r12d
0x18000e269  lea     edx, [r9+10h]
0x18000e26d  call    sqlite3VdbeAddOp3
0x18000e272  mov     cl, [rsi+30h]
0x18000e275  mov     r9d, 2
0x18000e27b  and     cl, 2
0x18000e27e  mov     r8d, ebp
0x18000e281  neg     cl
0x18000e283  mov     ebx, eax
0x18000e285  mov     rcx, r14
0x18000e288  sbb     edx, edx
0x18000e28a  and     edx, 0FFFFFFFDh
0x18000e28d  add     edx, 4
0x18000e290  mov     dword ptr [rsp+88h+var_68], edx
0x18000e294  lea     edx, [r9+62h]
0x18000e298  call    sqlite3VdbeAddOp3
0x18000e29d  movzx   eax, byte ptr [rsi+64h]
0x18000e2a1  mov     r9d, 5
0x18000e2a7  mov     r8d, ebp
0x18000e2aa  mov     dword ptr [rsp+88h+var_68], eax
0x18000e2ae  mov     rcx, r14
0x18000e2b1  lea     edx, [r9+5Fh]
0x18000e2b5  call    sqlite3VdbeAddOp3
0x18000e2ba  mov     edx, ebx
0x18000e2bc  mov     rcx, r14
0x18000e2bf  call    sqlite3VdbeGetOp
0x18000e2c4  mov     ecx, [r14+90h]
0x18000e2cb  xor     esi, esi
0x18000e2cd  mov     [rax+8], ecx
0x18000e2d0  cmp     [rsp+88h+arg_20], esi
0x18000e2d7  jnz     short loc_18000E301
0x18000e2d9  test    r13d, r13d
0x18000e2dc  jnz     short loc_18000E301
0x18000e2de  mov     r9d, r15d
0x18000e2e1  mov     dword ptr [rsp+88h+var_68], 1
0x18000e2e9  mov     r8d, ebp
0x18000e2ec  mov     edx, 93h
0x18000e2f1  mov     rcx, r14
0x18000e2f4  call    sqlite3VdbeAddOp3
0x18000e2f9  mov     [rdi+0D0h], eax
0x18000e2ff  jmp     short loc_18000E317
0x18000e301  xor     r8d, r8d
0x18000e304  mov     dword ptr [rsp+88h+var_68], esi
0x18000e308  mov     r9d, r15d
0x18000e30b  mov     rcx, r14
0x18000e30e  lea     edx, [r8+47h]
0x18000e312  call    sqlite3VdbeAddOp3
0x18000e317  mov     edx, ebp
0x18000e319  mov     rcx, rdi
0x18000e31c  call    sqlite3OpenSchemaTable
0x18000e321  mov     ebx, dword ptr [rsp+88h+arg_0]
0x18000e328  xor     r8d, r8d
0x18000e32b  mov     r9d, ebx
0x18000e32e  mov     dword ptr [rsp+88h+var_68], esi
0x18000e332  mov     rcx, r14
0x18000e335  lea     edx, [r8+7Fh]
0x18000e339  call    sqlite3VdbeAddOp3
0x18000e33e  mov     edx, 4Dh ; 'M'
0x18000e343  mov     [rsp+88h+var_58], 0FFFFFFFFh
0x18000e34b  lea     rax, unk_1800A6A78
0x18000e352  mov     r9d, r12d
0x18000e355  mov     [rsp+88h+var_60], rax
0x18000e35a  mov     rcx, r14
0x18000e35d  mov     dword ptr [rsp+88h+var_68], esi
0x18000e361  lea     r8d, [rdx-47h]
0x18000e365  call    sqlite3VdbeAddOp4
0x18000e36a  mov     r9d, r12d
0x18000e36d  mov     dword ptr [rsp+88h+var_68], ebx
0x18000e371  xor     r8d, r8d
0x18000e374  mov     edx, 80h
0x18000e379  mov     rcx, r14
0x18000e37c  call    sqlite3VdbeAddOp3
0x18000e381  mov     edx, 8
  ... truncated ...
```
