# sqlite3StartTable

- ea: `0x1801ea3dc`
- end: `0x1801ea8d2`
- name: `sqlite3StartTable`
- size: `1270`
- prototype: ``
- caller_count: `3`
- callee_count: `24`
- tags: `reparse_path`

## callers

- `0x1801ce6f8`
- `0x1801f8f98`
- `0x18021d7f0`

## callees

- `0x1801c716c`
- `0x1801c7bf0`
- `0x1801cb4d4`
- `0x1801cc4f8`
- `0x1801ce9a0`
- `0x1801ceb84`
- `0x1801ced34`
- `0x1801d0c94`
- `0x1801d5a40`
- `0x1801d5ac8`
- `0x1801d71ec`
- `0x1801da0fc`
- `0x1801de0f4`
- `0x1801e5344`
- `0x1801e5e28`
- `0x1801ea3dc`
- `0x1801eb2f8`
- `0x1801eba6c`
- `0x1801ee298`
- `0x1801ee320`
- `0x1801ee3cc`
- `0x1801ee734`
- `0x1801f59fc`
- `0x1801f8d5c`

## string_xrefs

- `0x1801ea42a`: `sqlite_temp_master`
- `0x1801ea510`: `sqlite_temp_master`
- `0x1801ea473`: `temporary table name must be unqualified`
- `0x1801ea5e2`: `%s %T already exists`
- `0x1801ea646`: `there is already an index named %s`

## pseudocode

```c
__int64 __fastcall sqlite3StartTable(__int64 *a1, _OWORD *a2, __int64 a3, int a4, int a5, int a6, int a7)
{
  __int64 v7; // rsi
  _OWORD *v10; // r14
  unsigned int v12; // ebp
  const char *v13; // rdx
  __int64 result; // rax
  const char *v15; // rbx
  _BYTE *v16; // r15
  const char *v17; // r12
  const char *v18; // r8
  int v19; // ecx
  __int64 v20; // rax
  const char *v21; // r8
  __int64 v22; // r15
  __int64 Table; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r14
  int v27; // r15d
  int v28; // eax
  int v29; // r13d
  int v30; // r12d
  int v31; // ecx
  unsigned int v32; // ebx
  int Vdbe; // ebx
  int v34; // r9d
  int v35; // ebx
  int v36; // ecx
  __int64 v37; // [rsp+40h] [rbp-58h]
  _OWORD *v38; // [rsp+A0h] [rbp+8h] BYREF

  v7 = *a1;
  v38 = 0;
  v10 = a2;
  if ( *(_BYTE *)(v7 + 197) && *(_DWORD *)(v7 + 192) == 1 )
  {
    v12 = *(unsigned __int8 *)(v7 + 196);
    v13 = "sqlite_temp_master";
    if ( v12 != 1 )
      v13 = "sqlite_master";
    result = sqlite3DbStrDup(v7, v13);
    v15 = (const char *)result;
    v16 = (char *)a1 + 308;
  }
  else
  {
    result = sqlite3TwoPartName(a1, a2, a3, &v38);
    v12 = result;
    if ( (int)result < 0 )
      return result;
    if ( a4 )
    {
      if ( *(_DWORD *)(a3 + 8) && (_DWORD)result != 1 )
        return sqlite3ErrorMsg(a1, "temporary table name must be unqualified");
      v12 = 1;
    }
    v10 = v38;
    result = sqlite3NameFromToken(v7, v38);
    v16 = (char *)a1 + 308;
    v15 = (const char *)result;
    if ( *((_BYTE *)a1 + 308) >= 2u )
      result = sqlite3RenameTokenMap(a1, result, v10);
  }
  *((_OWORD *)a1 + 17) = *v10;
  if ( v15 )
  {
    v17 = "view";
    v18 = "view";
    if ( !a5 )
      v18 = "table";
    if ( (unsigned int)sqlite3CheckObjectName(a1, v15, v18, v15) )
      goto LABEL_32;
    v19 = 1;
    v20 = *(_QWORD *)(v7 + 32);
    v21 = "sqlite_temp_master";
    if ( *(_BYTE *)(v7 + 196) != 1 )
      v19 = a4;
    LODWORD(v38) = v19;
    if ( v19 != 1 )
      v21 = "sqlite_master";
    v37 = *(_QWORD *)(v20 + 32LL * v12);
    if ( (unsigned int)sqlite3AuthCheck((_DWORD)a1, 18, (_DWORD)v21, 0, v37)
      || !a6
      && (unsigned int)sqlite3AuthCheck(
                         (_DWORD)a1,
                         (unsigned __int8)byte_1802DD848[2 * a5 + (int)v38],
                         (_DWORD)v15,
                         0,
                         v37) )
    {
      goto LABEL_32;
    }
    if ( !*v16 )
    {
      v22 = *(_QWORD *)(*(_QWORD *)(v7 + 32) + 32LL * v12);
      if ( (unsigned int)sqlite3ReadSchema(a1) )
      {
LABEL_32:
        *((_BYTE *)a1 + 29) = 1;
        return sqlite3DbFree(v7, v15);
      }
      Table = sqlite3FindTable(v7, v15, v22);
      if ( Table )
      {
        if ( a7 )
        {
          sqlite3CodeVerifySchema(a1, v12);
          sqlite3ForceNotReadOnly(a1);
        }
        else
        {
          if ( *(_BYTE *)(Table + 63) != 2 )
            v17 = "table";
          sqlite3ErrorMsg(a1, "%s %T already exists", v17, v10);
        }
        goto LABEL_32;
      }
      if ( sqlite3FindIndex(v7, v15, v22) )
      {
        sqlite3ErrorMsg(a1, "there is already an index named %s", v15);
        goto LABEL_32;
      }
    }
    v24 = sqlite3DbMallocZero(v7, 104);
    v25 = v24;
    if ( !v24 )
    {
      ++*((_DWORD *)a1 + 12);
      *((_DWORD *)a1 + 6) = 7;
      goto LABEL_32;
    }
    *(_QWORD *)v24 = v15;
    *(_WORD *)(v24 + 52) = -1;
    result = *(_QWORD *)(v7 + 32);
    *(_QWORD *)(v25 + 96) = *(_QWORD *)(result + 32LL * v12 + 24);
    *(_DWORD *)(v25 + 44) = 1;
    *(_WORD *)(v25 + 58) = 200;
    a1[44] = v25;
    if ( !*(_BYTE *)(v7 + 197) )
    {
      result = sqlite3GetVdbe(a1);
      v26 = result;
      if ( result )
      {
        sqlite3BeginWriteOperation(a1, 1, v12);
        v27 = a6;
        if ( a6 )
          sqlite3VdbeAddOp3(v26, 170, 0, 0, 0);
        v28 = *((_DWORD *)a1 + 14) + 1;
        LODWORD(v38) = v28;
        *((_DWORD *)a1 + 34) = v28;
        v29 = v28 + 1;
        v30 = v28 + 2;
        *((_DWORD *)a1 + 35) = v28 + 1;
        *((_DWORD *)a1 + 14) = v28 + 2;
        sqlite3VdbeAddOp3(v26, 99, v12, v28 + 2, 2);
        sqlite3VdbeUsesBtree(v26, v12);
        v32 = sqlite3VdbeAddOp3(v31, 16, v30, 0, 0);
        sqlite3VdbeAddOp3(v26, 100, v12, 2, (*(_BYTE *)(v7 + 48) & 2) != 0 ? 1 : 4);
        sqlite3VdbeAddOp3(v26, 100, v12, 5, *(unsigned __int8 *)(v7 + 100));
        *(_DWORD *)(sqlite3VdbeGetOp(v26, v32) + 8) = *(_DWORD *)(v26 + 144);
        if ( a5 || v27 )
          sqlite3VdbeAddOp3(v26, 71, 0, v29, 0);
        else
          *((_DWORD *)a1 + 52) = sqlite3VdbeAddOp3(v26, 147, v12, v29, 1);
        Vdbe = sqlite3GetVdbe(a1);
        LOBYTE(v34) = 1;
        sqlite3TableLock((_DWORD)a1, v12, 1, v34, (__int64)"sqlite_master");
        sqlite3VdbeAddOp4Int(Vdbe, 113, 0, 1, v12, 5);
        if ( !*((_DWORD *)a1 + 13) )
          *((_DWORD *)a1 + 13) = 1;
        v35 = (int)v38;
        sqlite3VdbeAddOp3(v26, 127, 0, (_DWORD)v38, 0);
        sqlite3VdbeAddOp4(v26, 77, 6, v30, 0, (__int64)&dword_1802DCD34, -1);
        sqlite3VdbeAddOp3(v26, 128, 0, v30, v35);
        sqlite3VdbeChangeP5(v26, 8);
        return sqlite3VdbeAddOp3(v36, 122, 0, 0, 0);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1801ea3dc  mov     rax, rsp
0x1801ea3df  push    rbx
0x1801ea3e0  push    rbp
0x1801ea3e1  push    rsi
0x1801ea3e2  push    rdi
0x1801ea3e3  push    r12
0x1801ea3e5  push    r13
0x1801ea3e7  push    r14
0x1801ea3e9  push    r15
0x1801ea3eb  sub     rsp, 58h
0x1801ea3ef  mov     rsi, [rcx]
0x1801ea3f2  xor     r12d, r12d
0x1801ea3f5  mov     [rax+8], r12
0x1801ea3f9  mov     r13d, r9d
0x1801ea3fc  mov     rbx, r8
0x1801ea3ff  lea     rax, aSqliteMaster; "sqlite_master"
0x1801ea406  mov     r14, rdx
0x1801ea409  mov     rdi, rcx
0x1801ea40c  lea     r15d, [r12+1]
0x1801ea411  cmp     [rsi+0C5h], r12b
0x1801ea418  jz      short loc_1801EA44C
0x1801ea41a  cmp     [rsi+0C0h], r15d
0x1801ea421  jnz     short loc_1801EA44C
0x1801ea423  movzx   ebp, byte ptr [rsi+0C4h]
0x1801ea42a  lea     rdx, aSqliteTempMast; "sqlite_temp_master"
0x1801ea431  cmp     ebp, r15d
0x1801ea434  mov     rcx, rsi
0x1801ea437  cmovnz  rdx, rax
0x1801ea43b  call    sqlite3DbStrDup
0x1801ea440  mov     rbx, rax
0x1801ea443  lea     r15, [rdi+134h]
0x1801ea44a  jmp     short loc_1801EA4BB
0x1801ea44c  lea     r9, [rsp+98h+arg_0]
0x1801ea454  call    sqlite3TwoPartName
0x1801ea459  mov     ebp, eax
0x1801ea45b  test    eax, eax
0x1801ea45d  js      loc_1801EA60E
0x1801ea463  test    r13d, r13d
0x1801ea466  jz      short loc_1801EA48A
0x1801ea468  cmp     [rbx+8], r12d
0x1801ea46c  jbe     short loc_1801EA487
0x1801ea46e  cmp     eax, r15d
0x1801ea471  jz      short loc_1801EA487
0x1801ea473  lea     rdx, aTemporaryTable; "temporary table name must be unqualifie"...
0x1801ea47a  mov     rcx, rdi
0x1801ea47d  call    sqlite3ErrorMsg
0x1801ea482  jmp     loc_1801EA60E
0x1801ea487  mov     ebp, r15d
0x1801ea48a  mov     r14, [rsp+98h+arg_0]
0x1801ea492  mov     rcx, rsi
0x1801ea495  mov     rdx, r14
0x1801ea498  call    sqlite3NameFromToken
0x1801ea49d  lea     r15, [rdi+134h]
0x1801ea4a4  mov     rbx, rax
0x1801ea4a7  cmp     byte ptr [r15], 2
0x1801ea4ab  jb      short loc_1801EA4BB
0x1801ea4ad  mov     r8, r14
0x1801ea4b0  mov     rdx, rax
0x1801ea4b3  mov     rcx, rdi
0x1801ea4b6  call    sqlite3RenameTokenMap
0x1801ea4bb  movups  xmm0, xmmword ptr [r14]
0x1801ea4bf  movdqu  xmmword ptr [rdi+110h], xmm0
0x1801ea4c7  test    rbx, rbx
0x1801ea4ca  jz      loc_1801EA60E
0x1801ea4d0  cmp     [rsp+98h+arg_20], 0
0x1801ea4d8  lea     rax, aTable; "table"
0x1801ea4df  lea     r12, aView_0; "view"
0x1801ea4e6  mov     r9, rbx
0x1801ea4e9  mov     r8, r12
0x1801ea4ec  mov     rdx, rbx
0x1801ea4ef  cmovz   r8, rax
0x1801ea4f3  mov     rcx, rdi
0x1801ea4f6  call    sqlite3CheckObjectName
0x1801ea4fb  test    eax, eax
0x1801ea4fd  jnz     loc_1801EA5FF
0x1801ea503  lea     ecx, [rax+1]
0x1801ea506  mov     rax, [rsi+20h]
0x1801ea50a  cmp     [rsi+0C4h], cl
0x1801ea510  lea     r8, aSqliteTempMast; "sqlite_temp_master"
0x1801ea517  cmovnz  ecx, r13d
0x1801ea51b  mov     r13d, ebp
0x1801ea51e  mov     dword ptr [rsp+98h+arg_0], ecx
0x1801ea525  shl     r13, 5
0x1801ea529  cmp     ecx, 1
0x1801ea52c  lea     rcx, aSqliteMaster; "sqlite_master"
0x1801ea533  cmovnz  r8, rcx
0x1801ea537  xor     r9d, r9d
0x1801ea53a  mov     rdx, [rax+r13]
0x1801ea53e  mov     rcx, rdi
0x1801ea541  mov     [rsp+98h+var_58], rdx
0x1801ea546  mov     [rsp+98h+var_78], rdx
0x1801ea54b  lea     edx, [r9+12h]
0x1801ea54f  call    sqlite3AuthCheck
0x1801ea554  test    eax, eax
0x1801ea556  jnz     loc_1801EA5FF
0x1801ea55c  cmp     [rsp+98h+arg_28], eax
0x1801ea563  jnz     short loc_1801EA5A0
0x1801ea565  mov     eax, dword ptr [rsp+98h+arg_0]
0x1801ea56c  xor     r9d, r9d
0x1801ea56f  mov     ecx, [rsp+98h+arg_20]
0x1801ea576  mov     r8, rbx
0x1801ea579  lea     eax, [rax+rcx*2]
0x1801ea57c  movsxd  rcx, eax
0x1801ea57f  lea     rax, byte_1802DD848
0x1801ea586  movzx   edx, byte ptr [rcx+rax]
0x1801ea58a  mov     rcx, rdi
0x1801ea58d  mov     rax, [rsp+98h+var_58]
0x1801ea592  mov     [rsp+98h+var_78], rax
0x1801ea597  call    sqlite3AuthCheck
0x1801ea59c  test    eax, eax
0x1801ea59e  jnz     short loc_1801EA5FF
0x1801ea5a0  cmp     byte ptr [r15], 0
0x1801ea5a4  jnz     loc_1801EA657
0x1801ea5aa  mov     rax, [rsi+20h]
0x1801ea5ae  mov     rcx, rdi
0x1801ea5b1  mov     r15, [rax+r13]
0x1801ea5b5  call    sqlite3ReadSchema
0x1801ea5ba  test    eax, eax
0x1801ea5bc  jnz     short loc_1801EA5FF
0x1801ea5be  mov     r8, r15
0x1801ea5c1  mov     rdx, rbx
0x1801ea5c4  mov     rcx, rsi
0x1801ea5c7  call    sqlite3FindTable
0x1801ea5cc  test    rax, rax
0x1801ea5cf  jz      short loc_1801EA630
0x1801ea5d1  cmp     [rsp+98h+arg_30], 0
0x1801ea5d9  mov     rcx, rdi
0x1801ea5dc  jnz     short loc_1801EA61F
0x1801ea5de  cmp     byte ptr [rax+3Fh], 2
0x1801ea5e2  lea     rdx, aSTAlreadyExist; "%s %T already exists"
0x1801ea5e9  lea     rax, aTable; "table"
0x1801ea5f0  mov     r9, r14
0x1801ea5f3  cmovnz  r12, rax
0x1801ea5f7  mov     r8, r12
0x1801ea5fa  call    sqlite3ErrorMsg
0x1801ea5ff  mov     rdx, rbx
0x1801ea602  mov     byte ptr [rdi+1Dh], 1
0x1801ea606  mov     rcx, rsi
0x1801ea609  call    sqlite3DbFree
0x1801ea60e  add     rsp, 58h
0x1801ea612  pop     r15
0x1801ea614  pop     r14
0x1801ea616  pop     r13
0x1801ea618  pop     r12
0x1801ea61a  pop     rdi
0x1801ea61b  pop     rsi
0x1801ea61c  pop     rbp
0x1801ea61d  pop     rbx
0x1801ea61e  retn
0x1801ea61f  mov     edx, ebp
0x1801ea621  call    sqlite3CodeVerifySchema
0x1801ea626  mov     rcx, rdi
0x1801ea629  call    sqlite3ForceNotReadOnly
0x1801ea62e  jmp     short loc_1801EA5FF
0x1801ea630  mov     r8, r15
0x1801ea633  mov     rdx, rbx
0x1801ea636  mov     rcx, rsi
0x1801ea639  call    sqlite3FindIndex
0x1801ea63e  test    rax, rax
0x1801ea641  jz      short loc_1801EA657
0x1801ea643  mov     r8, rbx
0x1801ea646  lea     rdx, aThereIsAlready_1; "there is already an index named %s"
0x1801ea64d  mov     rcx, rdi
0x1801ea650  call    sqlite3ErrorMsg
0x1801ea655  jmp     short loc_1801EA5FF
0x1801ea657  mov     edx, 68h ; 'h'
0x1801ea65c  mov     rcx, rsi
0x1801ea65f  call    sqlite3DbMallocZero
0x1801ea664  mov     rdx, rax
0x1801ea667  test    rax, rax
0x1801ea66a  jnz     short loc_1801EA678
0x1801ea66c  inc     dword ptr [rdi+30h]
0x1801ea66f  mov     dword ptr [rdi+18h], 7
0x1801ea676  jmp     short loc_1801EA5FF
0x1801ea678  mov     [rax], rbx
0x1801ea67b  xor     ebx, ebx
0x1801ea67d  mov     word ptr [rax+34h], 0FFFFh
0x1801ea683  mov     rax, [rsi+20h]
0x1801ea687  mov     rcx, [rax+r13+18h]
0x1801ea68c  mov     [rdx+60h], rcx
0x1801ea690  mov     dword ptr [rdx+2Ch], 1
0x1801ea697  mov     word ptr [rdx+3Ah], 0C8h
0x1801ea69d  mov     [rdi+160h], rdx
0x1801ea6a4  cmp     [rsi+0C5h], bl
0x1801ea6aa  jnz     loc_1801EA60E
0x1801ea6b0  mov     rcx, rdi
0x1801ea6b3  call    sqlite3GetVdbe
0x1801ea6b8  mov     r14, rax
0x1801ea6bb  test    rax, rax
0x1801ea6be  jz      loc_1801EA60E
0x1801ea6c4  mov     r8d, ebp
0x1801ea6c7  lea     edx, [rbx+1]
0x1801ea6ca  mov     rcx, rdi
0x1801ea6cd  call    sqlite3BeginWriteOperation
0x1801ea6d2  mov     r15d, [rsp+98h+arg_28]
0x1801ea6da  test    r15d, r15d
0x1801ea6dd  jz      short loc_1801EA6F6
0x1801ea6df  xor     r9d, r9d
0x1801ea6e2  mov     dword ptr [rsp+98h+var_78], ebx
0x1801ea6e6  xor     r8d, r8d
0x1801ea6e9  mov     edx, 0AAh
0x1801ea6ee  mov     rcx, r14
0x1801ea6f1  call    sqlite3VdbeAddOp3
0x1801ea6f6  mov     eax, [rdi+38h]
0x1801ea6f9  mov     r8d, ebp
0x1801ea6fc  inc     eax
0x1801ea6fe  mov     dword ptr [rsp+98h+var_78], 2
0x1801ea706  mov     edx, 63h ; 'c'
0x1801ea70b  mov     dword ptr [rsp+98h+arg_0], eax
0x1801ea712  mov     rcx, r14
0x1801ea715  mov     [rdi+88h], eax
0x1801ea71b  lea     r13d, [rax+1]
0x1801ea71f  lea     r12d, [r13+1]
0x1801ea723  mov     [rdi+8Ch], r13d
0x1801ea72a  mov     r9d, r12d
0x1801ea72d  mov     [rdi+38h], r12d
0x1801ea731  call    sqlite3VdbeAddOp3
0x1801ea736  mov     edx, ebp
0x1801ea738  mov     rcx, r14
0x1801ea73b  call    sqlite3VdbeUsesBtree
0x1801ea740  xor     r9d, r9d
0x1801ea743  mov     dword ptr [rsp+98h+var_78], ebx
0x1801ea747  mov     r8d, r12d
0x1801ea74a  lea     edx, [r9+10h]
0x1801ea74e  call    sqlite3VdbeAddOp3
0x1801ea753  mov     cl, [rsi+30h]
0x1801ea756  mov     r9d, 2
0x1801ea75c  and     cl, 2
0x1801ea75f  mov     r8d, ebp
0x1801ea762  neg     cl
0x1801ea764  mov     ebx, eax
0x1801ea766  mov     rcx, r14
0x1801ea769  sbb     edx, edx
0x1801ea76b  and     edx, 0FFFFFFFDh
0x1801ea76e  add     edx, 4
0x1801ea771  mov     dword ptr [rsp+98h+var_78], edx
0x1801ea775  lea     edx, [r9+62h]
0x1801ea779  call    sqlite3VdbeAddOp3
0x1801ea77e  movzx   eax, byte ptr [rsi+64h]
0x1801ea782  mov     r9d, 5
0x1801ea788  mov     r8d, ebp
0x1801ea78b  mov     dword ptr [rsp+98h+var_78], eax
0x1801ea78f  mov     rcx, r14
0x1801ea792  lea     edx, [r9+5Fh]
0x1801ea796  call    sqlite3VdbeAddOp3
0x1801ea79b  mov     edx, ebx
0x1801ea79d  mov     rcx, r14
0x1801ea7a0  call    sqlite3VdbeGetOp
0x1801ea7a5  mov     ecx, [r14+90h]
0x1801ea7ac  xor     esi, esi
0x1801ea7ae  mov     [rax+8], ecx
0x1801ea7b1  cmp     [rsp+98h+arg_20], esi
0x1801ea7b8  jnz     short loc_1801EA7E3
0x1801ea7ba  test    r15d, r15d
0x1801ea7bd  jnz     short loc_1801EA7E3
0x1801ea7bf  lea     r15d, [rsi+1]
0x1801ea7c3  mov     r9d, r13d
0x1801ea7c6  mov     r8d, ebp
0x1801ea7c9  mov     dword ptr [rsp+98h+var_78], r15d
0x1801ea7ce  mov     edx, 93h
0x1801ea7d3  mov     rcx, r14
0x1801ea7d6  call    sqlite3VdbeAddOp3
0x1801ea7db  mov     [rdi+0D0h], eax
0x1801ea7e1  jmp     short loc_1801EA7FF
0x1801ea7e3  xor     r8d, r8d
0x1801ea7e6  mov     dword ptr [rsp+98h+var_78], esi
0x1801ea7ea  mov     r9d, r13d
0x1801ea7ed  mov     rcx, r14
0x1801ea7f0  lea     edx, [r8+47h]
0x1801ea7f4  call    sqlite3VdbeAddOp3
0x1801ea7f9  mov     r15d, 1
0x1801ea7ff  mov     rcx, rdi
0x1801ea802  call    sqlite3GetVdbe
0x1801ea807  mov     rbx, rax
0x1801ea80a  mov     r9b, r15b
0x1801ea80d  lea     rax, aSqliteMaster; "sqlite_master"
0x1801ea814  mov     r8d, r15d
0x1801ea817  mov     edx, ebp
0x1801ea819  mov     [rsp+98h+var_78], rax
0x1801ea81e  mov     rcx, rdi
0x1801ea821  call    sqlite3TableLock
0x1801ea826  xor     r8d, r8d
0x1801ea829  mov     dword ptr [rsp+98h+var_70], 5
0x1801ea831  mov     r9d, r15d
0x1801ea834  mov     dword ptr [rsp+98h+var_78], ebp
0x1801ea838  mov     rcx, rbx
0x1801ea83b  lea     edx, [r8+71h]
0x1801ea83f  call    sqlite3VdbeAddOp4Int
0x1801ea844  cmp     [rdi+34h], esi
0x1801ea847  jnz     short loc_1801EA84D
0x1801ea849  mov     [rdi+34h], r15d
0x1801ea84d  mov     ebx, dword ptr [rsp+98h+arg_0]
0x1801ea854  xor     r8d, r8d
0x1801ea857  mov     r9d, ebx
0x1801ea85a  mov     dword ptr [rsp+98h+var_78], esi
0x1801ea85e  mov     rcx, r14
0x1801ea861  lea     edx, [r8+7Fh]
0x1801ea865  call    sqlite3VdbeAddOp3
0x1801ea86a  mov     edx, 4Dh ; 'M'
0x1801ea86f  mov     [rsp+98h+var_68], 0FFFFFFFFh
  ... truncated ...
```
