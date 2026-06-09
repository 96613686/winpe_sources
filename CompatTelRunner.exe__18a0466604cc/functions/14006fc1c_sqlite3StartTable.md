# sqlite3StartTable

- ea: `0x14006fc1c`
- end: `0x14007014f`
- name: `sqlite3StartTable`
- size: `1331`
- prototype: ``
- caller_count: `3`
- callee_count: `23`
- tags: `reparse_path`

## callers

- `0x140053b3c`
- `0x14007ea80`
- `0x1400a40bc`

## callees

- `0x14004bdbc`
- `0x14004c754`
- `0x140050574`
- `0x1400516cc`
- `0x140053e3c`
- `0x140053fec`
- `0x140054178`
- `0x1400560c4`
- `0x14005ae08`
- `0x14005ae90`
- `0x14005c598`
- `0x14005f5fc`
- `0x14006345c`
- `0x14006aa04`
- `0x14006b59c`
- `0x14006fc1c`
- `0x140070918`
- `0x140070fd0`
- `0x1400738a0`
- `0x14007399c`
- `0x140073ca8`
- `0x14007b574`
- `0x14007e880`

## string_xrefs

- `0x14006fc39`: `sqlite_temp_master`
- `0x14006fe48`: `%s %T already exists`
- `0x14006fcbb`: `temporary table name must be unqualified`
- `0x14006feb9`: `there is already an index named %s`

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
    v17 = (char *)a1 + 300;
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
    v17 = (char *)a1 + 300;
    v16 = (const char *)result;
    if ( *((_BYTE *)a1 + 300) >= 2u )
      result = sqlite3RenameTokenMap(a1, result, v11);
  }
  *(_OWORD *)(a1 + 33) = *v11;
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
                           *((unsigned __int8 *)&qword_1400B2848 + 2 * a5 + (int)v41),
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
    a1[43] = v26;
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
        *((_DWORD *)a1 + 32) = v29;
        v30 = v29 + 1;
        v31 = v29 + 2;
        *((_DWORD *)a1 + 33) = v29 + 1;
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
          *((_DWORD *)a1 + 50) = sqlite3VdbeAddOp3(v28, 147, v13, v30, 1);
        Vdbe = sqlite3GetVdbe(a1);
        LOBYTE(v35) = 1;
        sqlite3TableLock((_DWORD)a1, v13, 1, v35, (__int64)"sqlite_master");
        sqlite3VdbeAddOp4Int(Vdbe, 113, 0, 1, v13, 5);
        if ( !*((_DWORD *)a1 + 13) )
          *((_DWORD *)a1 + 13) = 1;
        v36 = (int)v41;
        sqlite3VdbeAddOp3(v28, 127, 0, (_DWORD)v41, 0);
        v37 = sqlite3VdbeAddOp3(v28, 77, 6, v31, 0);
        sqlite3VdbeChangeP4(v28, v37, &dword_1400B18B4, 0xFFFFFFFFLL);
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
0x14006fc1c  mov     rax, rsp
0x14006fc1f  mov     [rax+10h], rbx
0x14006fc23  mov     [rax+20h], r9d
0x14006fc27  push    rbp
0x14006fc28  push    rsi
0x14006fc29  push    rdi
0x14006fc2a  push    r12
0x14006fc2c  push    r13
0x14006fc2e  push    r14
0x14006fc30  push    r15
0x14006fc32  sub     rsp, 40h
0x14006fc36  mov     rsi, [rcx]
0x14006fc39  lea     r13, aSqliteTempMast; "sqlite_temp_master"
0x14006fc40  xor     r12d, r12d
0x14006fc43  mov     r15d, r9d
0x14006fc46  mov     [rax+8], r12
0x14006fc4a  mov     rbx, r8
0x14006fc4d  mov     rbp, rdx
0x14006fc50  lea     rax, aSqliteMaster; "sqlite_master"
0x14006fc57  mov     rdi, rcx
0x14006fc5a  cmp     [rsi+0C5h], r12b
0x14006fc61  jz      short loc_14006FC93
0x14006fc63  cmp     dword ptr [rsi+0C0h], 1
0x14006fc6a  jnz     short loc_14006FC93
0x14006fc6c  movzx   r14d, byte ptr [rsi+0C4h]
0x14006fc74  mov     rdx, r13
0x14006fc77  cmp     r14d, 1
0x14006fc7b  mov     rcx, rsi
0x14006fc7e  cmovnz  rdx, rax
0x14006fc82  call    sqlite3DbStrDup
0x14006fc87  mov     rbx, rax
0x14006fc8a  lea     r15, [rdi+12Ch]
0x14006fc91  jmp     short loc_14006FD06
0x14006fc93  lea     r9, [rsp+78h+arg_0]
0x14006fc9b  call    sqlite3TwoPartName
0x14006fca0  mov     r14d, eax
0x14006fca3  test    eax, eax
0x14006fca5  js      loc_14006FE74
0x14006fcab  test    r15d, r15d
0x14006fcae  jz      short loc_14006FCD5
0x14006fcb0  cmp     [rbx+8], r12d
0x14006fcb4  jbe     short loc_14006FCCF
0x14006fcb6  cmp     eax, 1
0x14006fcb9  jz      short loc_14006FCCF
0x14006fcbb  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x14006fcc2  mov     rcx, rdi
0x14006fcc5  call    sqlite3ErrorMsg
0x14006fcca  jmp     loc_14006FE74
0x14006fccf  mov     r14d, 1
0x14006fcd5  mov     rbp, [rsp+78h+arg_0]
0x14006fcdd  mov     rcx, rsi
0x14006fce0  mov     rdx, rbp
0x14006fce3  call    sqlite3NameFromToken
0x14006fce8  lea     r15, [rdi+12Ch]
0x14006fcef  mov     rbx, rax
0x14006fcf2  cmp     byte ptr [r15], 2
0x14006fcf6  jb      short loc_14006FD06
0x14006fcf8  mov     r8, rbp
0x14006fcfb  mov     rdx, rax
0x14006fcfe  mov     rcx, rdi
0x14006fd01  call    sqlite3RenameTokenMap
0x14006fd06  movups  xmm0, xmmword ptr [rbp+0]
0x14006fd0a  movdqu  xmmword ptr [rdi+108h], xmm0
0x14006fd12  test    rbx, rbx
0x14006fd15  jz      loc_14006FE74
0x14006fd1b  cmp     [rsp+78h+arg_20], 0
0x14006fd23  lea     rax, aTable; "table"
0x14006fd2a  lea     r12, aView_0; "view"
0x14006fd31  mov     r9, rbx
0x14006fd34  mov     r8, r12
0x14006fd37  mov     rdx, rbx
0x14006fd3a  cmovz   r8, rax
0x14006fd3e  mov     rcx, rdi
0x14006fd41  call    sqlite3CheckObjectName
0x14006fd46  test    eax, eax
0x14006fd48  jnz     loc_14006FE65
0x14006fd4e  lea     edx, [rax+1]
0x14006fd51  mov     ecx, r14d
0x14006fd54  cmp     [rsi+0C4h], dl
0x14006fd5a  mov     rax, [rsi+20h]
0x14006fd5e  cmovnz  edx, [rsp+78h+arg_18]
0x14006fd66  shl     rcx, 5
0x14006fd6a  mov     [rsp+78h+var_48], rcx
0x14006fd6f  cmp     edx, 1
0x14006fd72  mov     dword ptr [rsp+78h+arg_0], edx
0x14006fd79  mov     rax, [rcx+rax]
0x14006fd7d  lea     rcx, aSqliteMaster; "sqlite_master"
0x14006fd84  cmovnz  r13, rcx
0x14006fd88  mov     [rsp+78h+var_40], rax
0x14006fd8d  xor     r9d, r9d
0x14006fd90  mov     [rsp+78h+var_58], rax
0x14006fd95  mov     r8, r13
0x14006fd98  mov     rcx, rdi
0x14006fd9b  lea     edx, [r9+12h]
0x14006fd9f  call    sqlite3AuthCheck
0x14006fda4  test    eax, eax
0x14006fda6  jnz     loc_14006FE65
0x14006fdac  mov     r13d, [rsp+78h+arg_28]
0x14006fdb4  test    r13d, r13d
0x14006fdb7  jnz     short loc_14006FDF4
0x14006fdb9  mov     eax, dword ptr [rsp+78h+arg_0]
0x14006fdc0  xor     r9d, r9d
0x14006fdc3  mov     ecx, [rsp+78h+arg_20]
0x14006fdca  mov     r8, rbx
0x14006fdcd  lea     eax, [rax+rcx*2]
0x14006fdd0  movsxd  rcx, eax
0x14006fdd3  lea     rax, qword_1400B2848
0x14006fdda  movzx   edx, byte ptr [rcx+rax]
0x14006fdde  mov     rcx, rdi
0x14006fde1  mov     rax, [rsp+78h+var_40]
0x14006fde6  mov     [rsp+78h+var_58], rax
0x14006fdeb  call    sqlite3AuthCheck
0x14006fdf0  test    eax, eax
0x14006fdf2  jnz     short loc_14006FE65
0x14006fdf4  cmp     byte ptr [r15], 0
0x14006fdf8  mov     r15, [rsp+78h+var_48]
0x14006fdfd  jnz     loc_14006FECA
0x14006fe03  mov     rax, [rsi+20h]
0x14006fe07  mov     rcx, rdi
0x14006fe0a  mov     rax, [r15+rax]
0x14006fe0e  mov     [rsp+78h+arg_0], rax
0x14006fe16  call    sqlite3ReadSchema
0x14006fe1b  test    eax, eax
0x14006fe1d  jnz     short loc_14006FE65
0x14006fe1f  mov     r8, [rsp+78h+arg_0]
0x14006fe27  mov     rdx, rbx
0x14006fe2a  mov     rcx, rsi
0x14006fe2d  call    sqlite3FindTable
0x14006fe32  test    rax, rax
0x14006fe35  jz      short loc_14006FE9E
0x14006fe37  cmp     [rsp+78h+arg_30], 0
0x14006fe3f  mov     rcx, rdi
0x14006fe42  jnz     short loc_14006FE8C
0x14006fe44  cmp     byte ptr [rax+3Fh], 2
0x14006fe48  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x14006fe4f  lea     rax, aTable; "table"
0x14006fe56  mov     r9, rbp
0x14006fe59  cmovnz  r12, rax
0x14006fe5d  mov     r8, r12
0x14006fe60  call    sqlite3ErrorMsg
0x14006fe65  mov     rdx, rbx
0x14006fe68  mov     byte ptr [rdi+1Dh], 1
0x14006fe6c  mov     rcx, rsi
0x14006fe6f  call    sqlite3DbFreeNN
0x14006fe74  mov     rbx, [rsp+78h+arg_8]
0x14006fe7c  add     rsp, 40h
0x14006fe80  pop     r15
0x14006fe82  pop     r14
0x14006fe84  pop     r13
0x14006fe86  pop     r12
0x14006fe88  pop     rdi
0x14006fe89  pop     rsi
0x14006fe8a  pop     rbp
0x14006fe8b  retn
0x14006fe8c  mov     edx, r14d
0x14006fe8f  call    sqlite3CodeVerifySchema
0x14006fe94  mov     rcx, rdi
0x14006fe97  call    sqlite3ForceNotReadOnly
0x14006fe9c  jmp     short loc_14006FE65
0x14006fe9e  mov     r8, [rsp+78h+arg_0]
0x14006fea6  mov     rdx, rbx
0x14006fea9  mov     rcx, rsi
0x14006feac  call    sqlite3FindIndex
0x14006feb1  test    rax, rax
0x14006feb4  jz      short loc_14006FECA
0x14006feb6  mov     r8, rbx
0x14006feb9  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x14006fec0  mov     rcx, rdi
0x14006fec3  call    sqlite3ErrorMsg
0x14006fec8  jmp     short loc_14006FE65
0x14006feca  mov     edx, 68h ; 'h'
0x14006fecf  mov     rcx, rsi
0x14006fed2  call    sqlite3DbMallocZero
0x14006fed7  mov     rdx, rax
0x14006feda  test    rax, rax
0x14006fedd  jnz     short loc_14006FEEE
0x14006fedf  inc     dword ptr [rdi+30h]
0x14006fee2  mov     dword ptr [rdi+18h], 7
0x14006fee9  jmp     loc_14006FE65
0x14006feee  mov     [rax], rbx
0x14006fef1  xor     ebx, ebx
0x14006fef3  mov     word ptr [rax+34h], 0FFFFh
0x14006fef9  mov     rax, [rsi+20h]
0x14006fefd  mov     rcx, [rax+r15+18h]
0x14006ff02  mov     r15d, 1
0x14006ff08  mov     [rdx+2Ch], r15d
0x14006ff0c  mov     [rdx+60h], rcx
0x14006ff10  mov     word ptr [rdx+3Ah], 0C8h
0x14006ff16  mov     [rdi+158h], rdx
0x14006ff1d  cmp     [rsi+0C5h], bl
0x14006ff23  jnz     loc_14006FE74
0x14006ff29  mov     rcx, rdi
0x14006ff2c  call    sqlite3GetVdbe
0x14006ff31  mov     rbp, rax
0x14006ff34  test    rax, rax
0x14006ff37  jz      loc_14006FE74
0x14006ff3d  mov     r8d, r14d
0x14006ff40  mov     edx, r15d
0x14006ff43  mov     rcx, rdi
0x14006ff46  call    sqlite3BeginWriteOperation
0x14006ff4b  test    r13d, r13d
0x14006ff4e  jz      short loc_14006FF67
0x14006ff50  xor     r9d, r9d
0x14006ff53  mov     dword ptr [rsp+78h+var_58], ebx
0x14006ff57  xor     r8d, r8d
0x14006ff5a  mov     edx, 0AAh
0x14006ff5f  mov     rcx, rbp
0x14006ff62  call    sqlite3VdbeAddOp3
0x14006ff67  mov     eax, [rdi+38h]
0x14006ff6a  mov     r8d, r14d
0x14006ff6d  inc     eax
0x14006ff6f  mov     dword ptr [rsp+78h+var_58], 2
0x14006ff77  mov     edx, 63h ; 'c'
0x14006ff7c  mov     dword ptr [rsp+78h+arg_0], eax
0x14006ff83  mov     rcx, rbp
0x14006ff86  mov     [rdi+80h], eax
0x14006ff8c  lea     r15d, [rax+1]
0x14006ff90  lea     r12d, [r15+1]
0x14006ff94  mov     [rdi+84h], r15d
0x14006ff9b  mov     r9d, r12d
0x14006ff9e  mov     [rdi+38h], r12d
0x14006ffa2  call    sqlite3VdbeAddOp3
0x14006ffa7  mov     edx, r14d
0x14006ffaa  mov     rcx, rbp
0x14006ffad  call    sqlite3VdbeUsesBtree
0x14006ffb2  xor     r9d, r9d
0x14006ffb5  mov     dword ptr [rsp+78h+var_58], ebx
0x14006ffb9  mov     r8d, r12d
0x14006ffbc  lea     edx, [r9+10h]
0x14006ffc0  call    sqlite3VdbeAddOp3
0x14006ffc5  mov     cl, [rsi+30h]
0x14006ffc8  mov     r9d, 2
0x14006ffce  and     cl, 2
0x14006ffd1  mov     r8d, r14d
0x14006ffd4  neg     cl
0x14006ffd6  mov     ebx, eax
0x14006ffd8  mov     rcx, rbp
0x14006ffdb  sbb     edx, edx
0x14006ffdd  and     edx, 0FFFFFFFDh
0x14006ffe0  add     edx, 4
0x14006ffe3  mov     dword ptr [rsp+78h+var_58], edx
0x14006ffe7  lea     edx, [r9+62h]
0x14006ffeb  call    sqlite3VdbeAddOp3
0x14006fff0  movzx   eax, byte ptr [rsi+64h]
0x14006fff4  mov     r9d, 5
0x14006fffa  mov     r8d, r14d
0x14006fffd  mov     dword ptr [rsp+78h+var_58], eax
0x140070001  mov     rcx, rbp
0x140070004  lea     edx, [r9+5Fh]
0x140070008  call    sqlite3VdbeAddOp3
0x14007000d  mov     edx, ebx
0x14007000f  mov     rcx, rbp
0x140070012  call    sqlite3VdbeJumpHere
0x140070017  xor     esi, esi
0x140070019  cmp     [rsp+78h+arg_20], esi
0x140070020  jnz     short loc_14007004A
0x140070022  test    r13d, r13d
0x140070025  jnz     short loc_14007004A
0x140070027  mov     r9d, r15d
0x14007002a  mov     dword ptr [rsp+78h+var_58], 1
0x140070032  mov     r8d, r14d
0x140070035  mov     edx, 93h
0x14007003a  mov     rcx, rbp
0x14007003d  call    sqlite3VdbeAddOp3
0x140070042  mov     [rdi+0C8h], eax
0x140070048  jmp     short loc_140070060
0x14007004a  xor     r8d, r8d
0x14007004d  mov     dword ptr [rsp+78h+var_58], esi
0x140070051  mov     r9d, r15d
0x140070054  mov     rcx, rbp
0x140070057  lea     edx, [r8+47h]
0x14007005b  call    sqlite3VdbeAddOp3
0x140070060  mov     rcx, rdi
0x140070063  call    sqlite3GetVdbe
0x140070068  mov     rbx, rax
0x14007006b  mov     r15d, 1
0x140070071  lea     rax, aSqliteMaster; "sqlite_master"
0x140070078  mov     r9b, r15b
0x14007007b  mov     r8d, r15d
0x14007007e  mov     [rsp+78h+var_58], rax
0x140070083  mov     edx, r14d
0x140070086  mov     rcx, rdi
0x140070089  call    sqlite3TableLock
0x14007008e  mov     r9d, r15d
0x140070091  mov     [rsp+78h+var_50], 5
0x140070099  xor     r8d, r8d
0x14007009c  mov     dword ptr [rsp+78h+var_58], r14d
0x1400700a1  lea     edx, [r15+70h]
0x1400700a5  mov     rcx, rbx
0x1400700a8  call    sqlite3VdbeAddOp4Int
0x1400700ad  cmp     [rdi+34h], esi
0x1400700b0  jnz     short loc_1400700B6
0x1400700b2  mov     [rdi+34h], r15d
0x1400700b6  mov     ebx, dword ptr [rsp+78h+arg_0]
0x1400700bd  xor     r8d, r8d
0x1400700c0  mov     r9d, ebx
0x1400700c3  mov     dword ptr [rsp+78h+var_58], esi
0x1400700c7  mov     rcx, rbp
0x1400700ca  lea     edx, [r8+7Fh]
0x1400700ce  call    sqlite3VdbeAddOp3
  ... truncated ...
```
