# sqlite3StartTable

- ea: `0x180131620`
- end: `0x180131c83`
- name: `sqlite3StartTable`
- size: `1635`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `reparse_path`

## callers

- `0x180108540`
- `0x180174050`

## callees

- `0x1800b99d0`
- `0x1800d8770`
- `0x1800fdf90`
- `0x1800ff2c0`
- `0x180102f70`
- `0x180108840`
- `0x1801089d0`
- `0x18010b290`
- `0x1801127c0`
- `0x1801128f0`
- `0x180114d60`
- `0x18011eaa0`
- `0x18011f340`
- `0x180128f40`
- `0x180129aa0`
- `0x180131620`
- `0x1801341d0`
- `0x1801379a0`
- `0x180137a10`
- `0x180137a80`
- `0x180137af0`
- `0x180138140`
- `0x180142480`
- `0x18015dbf0`
- `0x1802421a0`
- `0x180242d80`

## string_xrefs

- `0x180131638`: `sqlite_temp_master`
- `0x1801316e6`: `temporary table name must be unqualified`
- `0x180131864`: `%s %T already exists`
- `0x1801318d7`: `there is already an index named %s`

## pseudocode

```c
char *__fastcall sqlite3StartTable(__int64 *a1, _OWORD *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  const char *v7; // r13
  __int64 v8; // r14
  _OWORD *v11; // rsi
  unsigned int v13; // ebp
  const char *v14; // r15
  size_t v15; // r12
  char *result; // rax
  const char *v17; // rbx
  _BYTE *v18; // r15
  const char *v19; // r12
  const char *v20; // r8
  __int64 v21; // rax
  int v22; // edx
  __int64 v23; // rax
  bool v24; // zf
  __int64 v25; // r15
  __int64 Table; // rax
  __int64 *v27; // rcx
  int v28; // eax
  __int64 v29; // rax
  __int64 v30; // rdx
  __int64 v31; // rcx
  char *v32; // rsi
  unsigned int v33; // r12d
  unsigned int v34; // r15d
  unsigned int v35; // ebx
  int v36; // ecx
  __int64 v37; // r10
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rdx
  _QWORD *v42; // r8
  __int64 v43; // rcx
  __int64 v44; // rax
  __int64 v45; // rdx
  __int64 v46; // rax
  int v48; // [rsp+30h] [rbp-68h]
  __int64 v49; // [rsp+30h] [rbp-68h]
  unsigned int v50; // [rsp+30h] [rbp-68h]
  __int64 v51; // [rsp+40h] [rbp-58h] BYREF
  __int64 v52; // [rsp+48h] [rbp-50h]

  v7 = "sqlite_temp_master";
  v8 = *a1;
  v11 = a2;
  if ( *(_BYTE *)(*a1 + 197) && *(_DWORD *)(v8 + 192) == 1 )
  {
    v13 = *(unsigned __int8 *)(v8 + 196);
    v14 = "sqlite_temp_master";
    if ( v13 != 1 )
      v14 = "sqlite_master";
    v15 = strlen(v14) + 1;
    result = (char *)sqlite3DbMallocRawNN(v8, v15);
    v17 = result;
    if ( result )
      result = (char *)memmove(result, v14, v15);
    v18 = (char *)a1 + 300;
  }
  else
  {
    result = (char *)sqlite3TwoPartName(a1, a2, a3, &v51);
    v13 = (unsigned int)result;
    if ( (int)result < 0 )
      return result;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && (_DWORD)result != 1 )
      {
        _mm_lfence();
        return (char *)sqlite3ErrorMsg(a1, "temporary table name must be unqualified");
      }
      v13 = 1;
    }
    v11 = (_OWORD *)v51;
    result = (char *)sqlite3NameFromToken(v8, v51);
    v18 = (char *)a1 + 300;
    v17 = result;
    if ( *((_BYTE *)a1 + 300) >= 2u )
    {
      _mm_lfence();
      result = (char *)sqlite3RenameTokenMap(a1, result, v11);
    }
  }
  *(_OWORD *)(a1 + 33) = *v11;
  if ( v17 )
  {
    v19 = "table";
    v20 = "table";
    if ( a5 )
      v20 = "view";
    if ( (unsigned int)sqlite3CheckObjectName(a1, v17, v20, v17) )
      goto LABEL_80;
    v21 = *(_QWORD *)(v8 + 32);
    v22 = 1;
    if ( *(_BYTE *)(v8 + 196) != 1 )
      v22 = a4;
    v51 = 32LL * v13;
    v48 = v22;
    v23 = *(_QWORD *)(v51 + v21);
    if ( v22 != 1 )
      v7 = "sqlite_master";
    v52 = v23;
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v7, 0, v23)
      || !a6
      && (unsigned int)sqlite3AuthCheck(
                         (_DWORD)a1,
                         *((unsigned __int8 *)&qword_18026F3F0 + 2 * a5 + v48),
                         (_DWORD)v17,
                         0,
                         v52) )
    {
      goto LABEL_80;
    }
    v24 = *v18 == 0;
    v25 = v51;
    if ( v24 )
    {
      v49 = *(_QWORD *)(v51 + *(_QWORD *)(v8 + 32));
      if ( (unsigned int)sqlite3ReadSchema(a1) )
      {
LABEL_80:
        *((_BYTE *)a1 + 29) = 1;
        return (char *)sqlite3DbFreeNN(v8);
      }
      Table = sqlite3FindTable(v8, v17, v49);
      if ( Table )
      {
        v27 = a1;
        if ( a7 )
        {
          if ( a1[21] )
            v27 = (__int64 *)a1[21];
          v28 = *((_DWORD *)v27 + 33);
          if ( !_bittest(&v28, v13) )
          {
            *((_DWORD *)v27 + 33) = v28 | (1 << v13);
            if ( v13 == 1 )
              sqlite3OpenTempDatabase(v27);
          }
          sqlite3ForceNotReadOnly(a1);
        }
        else
        {
          if ( *(_BYTE *)(Table + 63) == 2 )
            v19 = "view";
          sqlite3ErrorMsg(a1, "%s %T already exists", v19, v11);
        }
        goto LABEL_80;
      }
      if ( sqlite3FindIndex(v8, v17, v49) )
      {
        sqlite3ErrorMsg(a1, "there is already an index named %s", v17);
        goto LABEL_80;
      }
    }
    v29 = sqlite3DbMallocRawNN(v8, 104);
    v30 = v29;
    if ( !v29 )
    {
      ++*((_DWORD *)a1 + 12);
      *((_DWORD *)a1 + 6) = 7;
      goto LABEL_80;
    }
    *(_OWORD *)v29 = 0;
    *(_OWORD *)(v29 + 16) = 0;
    *(_OWORD *)(v29 + 32) = 0;
    *(_OWORD *)(v29 + 48) = 0;
    *(_OWORD *)(v29 + 64) = 0;
    *(_OWORD *)(v29 + 80) = 0;
    *(_QWORD *)(v29 + 96) = 0;
    *(_QWORD *)v29 = v17;
    *(_WORD *)(v29 + 52) = -1;
    result = *(char **)(v8 + 32);
    v31 = *(_QWORD *)&result[v25 + 24];
    *(_DWORD *)(v30 + 44) = 1;
    *(_QWORD *)(v30 + 96) = v31;
    *(_WORD *)(v30 + 58) = 200;
    a1[43] = v30;
    if ( !*(_BYTE *)(v8 + 197) )
    {
      v32 = (char *)a1[2];
      if ( v32 )
        goto LABEL_49;
      if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
        *((_BYTE *)a1 + 35) = 1;
      result = (char *)sqlite3VdbeCreate(a1);
      v32 = result;
      if ( result )
      {
LABEL_49:
        sqlite3BeginWriteOperation(a1, 1, v13);
        if ( a6 )
          sqlite3VdbeAddOp0(v32, 170);
        v50 = *((_DWORD *)a1 + 14) + 1;
        *((_DWORD *)a1 + 34) = v50;
        v33 = v50 + 1;
        v34 = v50 + 2;
        *((_DWORD *)a1 + 35) = v50 + 1;
        *((_DWORD *)a1 + 14) = v50 + 2;
        sqlite3VdbeAddOp3((_DWORD)v32, 99, v13, v50 + 2, 2);
        *((_DWORD *)v32 + 51) |= 1 << v13;
        v35 = sqlite3VdbeAddOp1(v32, 16, v50 + 2);
        v36 = 4;
        if ( (*(_BYTE *)(v8 + 48) & 2) != 0 )
          v36 = 1;
        sqlite3VdbeAddOp3((_DWORD)v32, 100, v13, 2, v36);
        sqlite3VdbeAddOp3((_DWORD)v32, 100, v13, 5, *(unsigned __int8 *)(v8 + 100));
        sqlite3VdbeJumpHere(v32, v35);
        if ( a5 || a6 )
          sqlite3VdbeAddOp2(v32, 71, 0, v33);
        else
          *((_DWORD *)a1 + 50) = sqlite3VdbeAddOp3((_DWORD)v32, 147, v13, v33, 1);
        v37 = a1[2];
        if ( !v37 )
        {
          if ( !a1[21] && (*(_BYTE *)(*a1 + 96) & 8) == 0 )
            *((_BYTE *)a1 + 35) = 1;
          v37 = sqlite3VdbeCreate(a1);
        }
        v38 = *(int *)(v37 + 144);
        if ( *(_DWORD *)(v37 + 148) > (int)v38 )
        {
          *(_DWORD *)(v37 + 144) = v38 + 1;
          v39 = 3 * v38;
          v40 = *(_QWORD *)(v37 + 136);
          *(_QWORD *)(v40 + 8 * v39) = 64881;
          *(_DWORD *)(v40 + 8 * v39 + 8) = 1;
          *(_DWORD *)(v40 + 8 * v39 + 12) = v13;
          *(_DWORD *)(v40 + 8 * v39 + 16) = 5;
        }
        else
        {
          addOp4IntSlow(v37, 113, 0, 1, v13, 5);
        }
        if ( !*((_DWORD *)a1 + 13) )
          *((_DWORD *)a1 + 13) = 1;
        sqlite3VdbeAddOp2(v32, 127, 0, v50);
        v41 = *((int *)v32 + 36);
        if ( *((_DWORD *)v32 + 37) > (int)v41 )
        {
          v43 = 3 * v41;
          *((_DWORD *)v32 + 36) = v41 + 1;
          v42 = v32 + 136;
          v44 = *((_QWORD *)v32 + 17);
          *(_DWORD *)(v44 + 8 * v43) = 77;
          *(_DWORD *)(v44 + 8 * v43 + 4) = 6;
          *(_DWORD *)(v44 + 8 * v43 + 8) = v34;
          *(_DWORD *)(v44 + 8 * v43 + 12) = 0;
          *(_QWORD *)(v44 + 8 * v43 + 16) = 0;
        }
        else
        {
          LODWORD(v41) = growOp3((_DWORD)v32, 77, 6, v34, 0);
          v42 = v32 + 136;
        }
        if ( !*(_BYTE *)(*(_QWORD *)v32 + 103LL) )
        {
          if ( (int)v41 < 0 )
          {
            _mm_lfence();
            LODWORD(v41) = *((_DWORD *)v32 + 36) - 1;
          }
          v24 = *(_BYTE *)(*v42 + 24LL * (int)v41 + 1) == 0;
          v45 = *v42 + 24LL * (int)v41;
          if ( v24 )
          {
            *(_BYTE *)(v45 + 1) = -1;
            *(_QWORD *)(v45 + 16) = &qword_18026E078;
          }
          else
          {
            vdbeChangeP4Full(v32, v45, &qword_18026E078, 0xFFFFFFFFLL);
          }
        }
        sqlite3VdbeAddOp3((_DWORD)v32, 128, 0, v34, v50);
        v46 = *((int *)v32 + 36);
        if ( (int)v46 > 0 )
          *(_WORD *)(*((_QWORD *)v32 + 17) + 24 * v46 - 22) = 8;
        return (char *)sqlite3VdbeAddOp0(v32, 122);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180131620  push    rbx
0x180131622  push    rbp
0x180131623  push    rsi
0x180131624  push    rdi
0x180131625  push    r12
0x180131627  push    r13
0x180131629  push    r14
0x18013162b  push    r15
0x18013162d  sub     rsp, 58h
0x180131631  mov     eax, [rsp+98h+arg_20]
0x180131638  lea     r13, aSqliteTempMast; "sqlite_temp_master"
0x18013163f  mov     r14, [rcx]
0x180131642  mov     r15d, r9d
0x180131645  mov     [rsp+98h+var_60], eax
0x180131649  mov     rbx, r8
0x18013164c  mov     dword ptr [rsp+98h+var_68], r9d
0x180131651  lea     rax, aSqliteMaster; "sqlite_master"
0x180131658  mov     rsi, rdx
0x18013165b  mov     rdi, rcx
0x18013165e  cmp     byte ptr [r14+0C5h], 0
0x180131666  mov     r12d, 1
0x18013166c  jz      short loc_1801316BF
0x18013166e  cmp     [r14+0C0h], r12d
0x180131675  jnz     short loc_1801316BF
0x180131677  movzx   ebp, byte ptr [r14+0C4h]
0x18013167f  mov     r15, r13
0x180131682  cmp     ebp, r12d
0x180131685  cmovnz  r15, rax
0x180131689  mov     rcx, r15; Str
0x18013168c  call    strlen
0x180131691  mov     rcx, r14
0x180131694  lea     r12, [rax+1]
0x180131698  mov     rdx, r12
0x18013169b  call    sqlite3DbMallocRawNN
0x1801316a0  mov     rbx, rax
0x1801316a3  test    rax, rax
0x1801316a6  jz      short loc_1801316B6
0x1801316a8  mov     r8, r12; Size
0x1801316ab  mov     rdx, r15; Src
0x1801316ae  mov     rcx, rax; void *
0x1801316b1  call    memmove
0x1801316b6  lea     r15, [rdi+12Ch]
0x1801316bd  jmp     short loc_18013172E
0x1801316bf  lea     r9, [rsp+98h+var_58]
0x1801316c4  call    sqlite3TwoPartName
0x1801316c9  mov     ebp, eax
0x1801316cb  test    eax, eax
0x1801316cd  js      loc_180131C72
0x1801316d3  test    r15d, r15d
0x1801316d6  jz      short loc_1801316FD
0x1801316d8  cmp     dword ptr [rbx+8], 0
0x1801316dc  jbe     short loc_1801316FA
0x1801316de  cmp     eax, r12d
0x1801316e1  jz      short loc_1801316FA
0x1801316e3  lfence
0x1801316e6  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x1801316ed  mov     rcx, rdi
0x1801316f0  call    sqlite3ErrorMsg
0x1801316f5  jmp     loc_180131C72
0x1801316fa  mov     ebp, r12d
0x1801316fd  mov     rsi, [rsp+98h+var_58]
0x180131702  mov     rcx, r14
0x180131705  mov     rdx, rsi
0x180131708  call    sqlite3NameFromToken
0x18013170d  lea     r15, [rdi+12Ch]
0x180131714  mov     rbx, rax
0x180131717  cmp     byte ptr [r15], 2
0x18013171b  jb      short loc_18013172E
0x18013171d  lfence
0x180131720  mov     r8, rsi
0x180131723  mov     rdx, rax
0x180131726  mov     rcx, rdi
0x180131729  call    sqlite3RenameTokenMap
0x18013172e  movups  xmm0, xmmword ptr [rsi]
0x180131731  movups  xmmword ptr [rdi+108h], xmm0
0x180131738  test    rbx, rbx
0x18013173b  jz      loc_180131C72
0x180131741  cmp     [rsp+98h+var_60], 0
0x180131746  lea     rax, aView_0; "view"
0x18013174d  lea     r12, aTable; "table"
0x180131754  mov     r9, rbx
0x180131757  mov     r8, r12
0x18013175a  mov     rdx, rbx
0x18013175d  cmovnz  r8, rax
0x180131761  mov     rcx, rdi
0x180131764  call    sqlite3CheckObjectName
0x180131769  test    eax, eax
0x18013176b  jnz     loc_180131C63
0x180131771  mov     rax, [r14+20h]
0x180131775  mov     edx, 1
0x18013177a  cmp     [r14+0C4h], dl
0x180131781  mov     ecx, ebp
0x180131783  cmovnz  edx, dword ptr [rsp+98h+var_68]
0x180131788  shl     rcx, 5
0x18013178c  mov     [rsp+98h+var_58], rcx
0x180131791  cmp     edx, 1
0x180131794  mov     dword ptr [rsp+98h+var_68], edx
0x180131798  mov     edx, 12h
0x18013179d  mov     rax, [rcx+rax]
0x1801317a1  lea     rcx, aSqliteMaster; "sqlite_master"
0x1801317a8  cmovnz  r13, rcx
0x1801317ac  mov     [rsp+98h+var_50], rax
0x1801317b1  mov     r8, r13
0x1801317b4  mov     [rsp+98h+var_78], rax
0x1801317b9  xor     r9d, r9d
0x1801317bc  mov     rcx, rdi
0x1801317bf  call    sqlite3AuthCheck
0x1801317c4  test    eax, eax
0x1801317c6  jnz     loc_180131C63
0x1801317cc  mov     r13d, [rsp+98h+arg_28]
0x1801317d4  test    r13d, r13d
0x1801317d7  jnz     short loc_180131812
0x1801317d9  mov     eax, dword ptr [rsp+98h+var_68]
0x1801317dd  xor     r9d, r9d
0x1801317e0  mov     ecx, [rsp+98h+var_60]
0x1801317e4  mov     r8, rbx
0x1801317e7  lea     eax, [rax+rcx*2]
0x1801317ea  movsxd  rcx, eax
0x1801317ed  lea     rax, qword_18026F3F0
0x1801317f4  movzx   edx, byte ptr [rcx+rax]
0x1801317f8  mov     rcx, rdi
0x1801317fb  mov     rax, [rsp+98h+var_50]
0x180131800  mov     [rsp+98h+var_78], rax
0x180131805  call    sqlite3AuthCheck
0x18013180a  test    eax, eax
0x18013180c  jnz     loc_180131C63
0x180131812  cmp     byte ptr [r15], 0
0x180131816  mov     r15, [rsp+98h+var_58]
0x18013181b  jnz     loc_1801318EB
0x180131821  mov     rax, [r14+20h]
0x180131825  mov     rcx, rdi
0x180131828  mov     rax, [r15+rax]
0x18013182c  mov     [rsp+98h+var_68], rax
0x180131831  call    sqlite3ReadSchema
0x180131836  test    eax, eax
0x180131838  jnz     loc_180131C63
0x18013183e  mov     r8, [rsp+98h+var_68]
0x180131843  mov     rdx, rbx
0x180131846  mov     rcx, r14
0x180131849  call    sqlite3FindTable
0x18013184e  test    rax, rax
0x180131851  jz      short loc_1801318BF
0x180131853  cmp     [rsp+98h+arg_30], 0
0x18013185b  mov     rcx, rdi
0x18013185e  jnz     short loc_180131886
0x180131860  cmp     byte ptr [rax+3Fh], 2
0x180131864  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x18013186b  lea     rax, aView_0; "view"
0x180131872  mov     r9, rsi
0x180131875  cmovz   r12, rax
0x180131879  mov     r8, r12
0x18013187c  call    sqlite3ErrorMsg
0x180131881  jmp     loc_180131C63
0x180131886  mov     rax, [rdi+0A8h]
0x18013188d  test    rax, rax
0x180131890  cmovnz  rcx, rax
0x180131894  mov     eax, [rcx+84h]
0x18013189a  bt      eax, ebp
0x18013189d  jb      short loc_1801318B2
0x18013189f  bts     eax, ebp
0x1801318a2  mov     [rcx+84h], eax
0x1801318a8  cmp     ebp, 1
0x1801318ab  jnz     short loc_1801318B2
0x1801318ad  call    sqlite3OpenTempDatabase
0x1801318b2  mov     rcx, rdi
0x1801318b5  call    sqlite3ForceNotReadOnly
0x1801318ba  jmp     loc_180131C63
0x1801318bf  mov     r8, [rsp+98h+var_68]
0x1801318c4  mov     rdx, rbx
0x1801318c7  mov     rcx, r14
0x1801318ca  call    sqlite3FindIndex
0x1801318cf  test    rax, rax
0x1801318d2  jz      short loc_1801318EB
0x1801318d4  mov     r8, rbx
0x1801318d7  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x1801318de  mov     rcx, rdi
0x1801318e1  call    sqlite3ErrorMsg
0x1801318e6  jmp     loc_180131C63
0x1801318eb  mov     edx, 68h ; 'h'
0x1801318f0  mov     rcx, r14
0x1801318f3  call    sqlite3DbMallocRawNN
0x1801318f8  mov     rdx, rax
0x1801318fb  test    rax, rax
0x1801318fe  jz      loc_180131C59
0x180131904  xorps   xmm0, xmm0
0x180131907  xor     eax, eax
0x180131909  movups  xmmword ptr [rdx], xmm0
0x18013190c  movups  xmmword ptr [rdx+10h], xmm0
0x180131910  movups  xmmword ptr [rdx+20h], xmm0
0x180131914  movups  xmmword ptr [rdx+30h], xmm0
0x180131918  movups  xmmword ptr [rdx+40h], xmm0
0x18013191c  movups  xmmword ptr [rdx+50h], xmm0
0x180131920  mov     [rdx+60h], rax
0x180131924  mov     [rdx], rbx
0x180131927  mov     word ptr [rdx+34h], 0FFFFh
0x18013192d  mov     rax, [r14+20h]
0x180131931  mov     rcx, [r15+rax+18h]
0x180131936  mov     r15d, 1
0x18013193c  mov     [rdx+2Ch], r15d
0x180131940  mov     [rdx+60h], rcx
0x180131944  mov     word ptr [rdx+3Ah], 0C8h
0x18013194a  mov     [rdi+158h], rdx
0x180131951  cmp     byte ptr [r14+0C5h], 0
0x180131959  jnz     loc_180131C72
0x18013195f  mov     rsi, [rdi+10h]
0x180131963  test    rsi, rsi
0x180131966  jnz     short loc_180131992
0x180131968  cmp     [rdi+0A8h], rsi
0x18013196f  jnz     short loc_18013197E
0x180131971  mov     rax, [rdi]
0x180131974  test    byte ptr [rax+60h], 8
0x180131978  jnz     short loc_18013197E
0x18013197a  mov     [rdi+23h], r15b
0x18013197e  mov     rcx, rdi
0x180131981  call    sqlite3VdbeCreate
0x180131986  mov     rsi, rax
0x180131989  test    rax, rax
0x18013198c  jz      loc_180131C72
0x180131992  mov     r8d, ebp
0x180131995  mov     edx, r15d
0x180131998  mov     rcx, rdi
0x18013199b  call    sqlite3BeginWriteOperation
0x1801319a0  test    r13d, r13d
0x1801319a3  jz      short loc_1801319B2
0x1801319a5  mov     edx, 0AAh
0x1801319aa  mov     rcx, rsi
0x1801319ad  call    sqlite3VdbeAddOp0
0x1801319b2  mov     eax, [rdi+38h]
0x1801319b5  mov     r8d, ebp
0x1801319b8  inc     eax
0x1801319ba  mov     dword ptr [rsp+98h+var_78], 2
0x1801319c2  mov     edx, 63h ; 'c'
0x1801319c7  mov     dword ptr [rsp+98h+var_68], eax
0x1801319cb  mov     rcx, rsi
0x1801319ce  mov     [rdi+88h], eax
0x1801319d4  lea     r12d, [rax+1]
0x1801319d8  lea     r15d, [r12+1]
0x1801319dd  mov     [rdi+8Ch], r12d
0x1801319e4  mov     r9d, r15d
0x1801319e7  mov     [rdi+38h], r15d
0x1801319eb  call    sqlite3VdbeAddOp3
0x1801319f0  mov     eax, [rsi+0CCh]
0x1801319f6  mov     r8d, r15d
0x1801319f9  bts     eax, ebp
0x1801319fc  mov     edx, 10h
0x180131a01  mov     rcx, rsi
0x180131a04  mov     [rsi+0CCh], eax
0x180131a0a  call    sqlite3VdbeAddOp1
0x180131a0f  test    byte ptr [r14+30h], 2
0x180131a14  mov     ebx, eax
0x180131a16  mov     eax, 1
0x180131a1b  mov     ecx, 4
0x180131a20  cmovnz  ecx, eax
0x180131a23  mov     r9d, 2
0x180131a29  mov     dword ptr [rsp+98h+var_78], ecx
0x180131a2d  mov     r8d, ebp
0x180131a30  mov     rcx, rsi
0x180131a33  mov     edx, 64h ; 'd'
0x180131a38  call    sqlite3VdbeAddOp3
0x180131a3d  movzx   ecx, byte ptr [r14+64h]
0x180131a42  mov     r9d, 5
0x180131a48  mov     dword ptr [rsp+98h+var_78], ecx
0x180131a4c  mov     r8d, ebp
0x180131a4f  mov     rcx, rsi
0x180131a52  mov     edx, 64h ; 'd'
0x180131a57  call    sqlite3VdbeAddOp3
0x180131a5c  mov     edx, ebx
0x180131a5e  mov     rcx, rsi
0x180131a61  call    sqlite3VdbeJumpHere
0x180131a66  cmp     [rsp+98h+var_60], 0
0x180131a6b  jnz     short loc_180131A96
0x180131a6d  test    r13d, r13d
0x180131a70  jnz     short loc_180131A96
0x180131a72  mov     ebx, 1
0x180131a77  mov     r9d, r12d
0x180131a7a  mov     r8d, ebp
0x180131a7d  mov     dword ptr [rsp+98h+var_78], ebx
0x180131a81  mov     edx, 93h
0x180131a86  mov     rcx, rsi
0x180131a89  call    sqlite3VdbeAddOp3
0x180131a8e  mov     [rdi+0C8h], eax
0x180131a94  jmp     short loc_180131AAE
0x180131a96  mov     r9d, r12d
0x180131a99  xor     r8d, r8d
0x180131a9c  mov     edx, 47h ; 'G'
0x180131aa1  mov     rcx, rsi
0x180131aa4  call    sqlite3VdbeAddOp2
0x180131aa9  mov     ebx, 1
0x180131aae  mov     r10, [rdi+10h]
0x180131ab2  test    r10, r10
0x180131ab5  jnz     short loc_180131AD8
0x180131ab7  cmp     [rdi+0A8h], r10
0x180131abe  jnz     short loc_180131ACD
0x180131ac0  mov     rax, [rdi]
0x180131ac3  test    byte ptr [rax+60h], 8
0x180131ac7  jnz     short loc_180131ACD
0x180131ac9  mov     byte ptr [rdi+23h], 1
0x180131acd  mov     rcx, rdi
0x180131ad0  call    sqlite3VdbeCreate
0x180131ad5  mov     r10, rax
  ... truncated ...
```
