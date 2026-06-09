# sqlite3CodeDropTable

- ea: `0x180082718`
- end: `0x180082932`
- name: `sqlite3CodeDropTable`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x1800832c0`

## callees

- `0x180010810`
- `0x1800119e0`
- `0x180011d80`
- `0x1800157d4`
- `0x18003f6dc`
- `0x180056bc0`
- `0x18005ee1c`
- `0x18006dca4`
- `0x180082718`
- `0x1800835e4`
- `0x1800857c4`

## string_xrefs

- `0x1800827b0`: `DELETE FROM %Q.sqlite_sequence WHERE name=%Q`
- `0x1800827c6`: `DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'`

## pseudocode

```c
__int64 __fastcall sqlite3CodeDropTable(_QWORD *a1, __int64 *a2, unsigned int a3, int a4)
{
  __int64 v4; // r15
  __int64 v9; // r14
  __int64 v10; // rbp
  int Vdbe; // r13d
  __int64 i; // rdi
  unsigned int v13; // ebp
  unsigned int j; // ecx
  unsigned int v15; // edi
  __int64 k; // rax
  int v17; // eax
  unsigned int v18; // edi
  _QWORD *v19; // rcx
  __int64 result; // rax
  __int64 v21; // rbx
  _QWORD *m; // rbx
  __int64 v23; // rdx
  __int64 v24; // rcx

  v4 = *a1;
  v9 = 32LL * (int)a3;
  v10 = *(_QWORD *)(*a1 + 32LL);
  Vdbe = sqlite3GetVdbe(a1);
  sqlite3BeginWriteOperation(a1, 1, a3);
  if ( *((_BYTE *)a2 + 63) == 1 )
    sqlite3VdbeAddOp3(Vdbe, 170, 0, 0, 0);
  for ( i = sqlite3TriggerList(a1, a2); i; i = *(_QWORD *)(i + 64) )
    sqlite3DropTriggerPtr(a1, i);
  if ( (a2[6] & 8) != 0 )
    sqlite3NestedParse(a1, "DELETE FROM %Q.sqlite_sequence WHERE name=%Q", *(_QWORD *)(v9 + v10), *a2);
  sqlite3NestedParse(
    a1,
    "DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'",
    *(_QWORD *)(v9 + v10),
    *a2);
  if ( !a4 )
  {
    if ( *((_BYTE *)a2 + 63) == 1 )
      goto LABEL_23;
    v13 = *((_DWORD *)a2 + 10);
    for ( j = 0; ; j = v15 )
    {
      if ( !j || (v15 = 0, v13 < j) )
        v15 = v13;
      for ( k = a2[2]; k; k = *(_QWORD *)(k + 40) )
      {
        if ( (!j || *(_DWORD *)(k + 88) < j) && *(_DWORD *)(k + 88) > v15 )
          v15 = *(_DWORD *)(k + 88);
      }
      if ( !v15 )
        break;
      v17 = sqlite3SchemaToIndex(*a1, a2[12]);
      destroyRootPage(a1, v15, v17);
    }
  }
  if ( *((_BYTE *)a2 + 63) != 1 )
  {
    v18 = a3;
    goto LABEL_27;
  }
LABEL_23:
  v18 = a3;
  sqlite3VdbeAddOp4(Vdbe, 172, a3, 0, 0, *a2, 0);
  v19 = a1;
  if ( a1[22] )
    v19 = (_QWORD *)a1[22];
  *((_BYTE *)v19 + 33) = 1;
LABEL_27:
  sqlite3VdbeAddOp4(Vdbe, 151, v18, 0, 0, *a2, 0);
  sqlite3VdbeAddOp3(a1[2], 100, v18, 1, **(_DWORD **)(*(_QWORD *)(*a1 + 32LL) + v9 + 24) + 1);
  result = *(_QWORD *)(v4 + 32);
  v21 = *(_QWORD *)(result + v9 + 24);
  if ( (*(_BYTE *)(v21 + 114) & 2) != 0 )
  {
    for ( m = *(_QWORD **)(v21 + 16); m; m = (_QWORD *)*m )
    {
      v23 = m[2];
      if ( *(_BYTE *)(v23 + 63) == 2 )
        sqlite3DeleteColumnNames(v4, v23);
    }
    v24 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + v9 + 24);
    result = 65533;
    *(_WORD *)(v24 + 114) &= ~2u;
  }
  return result;
}

```

## disassembly

```asm
0x180082718  mov     [rsp+arg_10], r8d
0x18008271d  push    rbx
0x18008271e  push    rbp
0x18008271f  push    rsi
0x180082720  push    rdi
0x180082721  push    r12
0x180082723  push    r13
0x180082725  push    r14
0x180082727  push    r15
0x180082729  sub     rsp, 48h
0x18008272d  mov     r15, [rcx]
0x180082730  mov     r12d, r9d
0x180082733  movsxd  rdi, r8d
0x180082736  mov     rbx, rdx
0x180082739  mov     r14, rdi
0x18008273c  mov     rsi, rcx
0x18008273f  shl     r14, 5
0x180082743  mov     rbp, [r15+20h]
0x180082747  call    sqlite3GetVdbe
0x18008274c  mov     r8d, edi
0x18008274f  mov     edx, 1
0x180082754  mov     rcx, rsi
0x180082757  mov     r13, rax
0x18008275a  call    sqlite3BeginWriteOperation
0x18008275f  cmp     byte ptr [rbx+3Fh], 1
0x180082763  jnz     short loc_180082780
0x180082765  xor     r9d, r9d
0x180082768  mov     [rsp+88h+var_68], 0
0x180082770  xor     r8d, r8d
0x180082773  mov     edx, 0AAh
0x180082778  mov     rcx, r13
0x18008277b  call    sqlite3VdbeAddOp3
0x180082780  mov     rdx, rbx
0x180082783  mov     rcx, rsi
0x180082786  call    sqlite3TriggerList
0x18008278b  mov     rdi, rax
0x18008278e  test    rax, rax
0x180082791  jz      short loc_1800827A7
0x180082793  mov     rdx, rdi
0x180082796  mov     rcx, rsi
0x180082799  call    sqlite3DropTriggerPtr
0x18008279e  mov     rdi, [rdi+40h]
0x1800827a2  test    rdi, rdi
0x1800827a5  jnz     short loc_180082793
0x1800827a7  test    byte ptr [rbx+30h], 8
0x1800827ab  jz      short loc_1800827C3
0x1800827ad  mov     r9, [rbx]
0x1800827b0  lea     rdx, aDeleteFromQSql_0; "DELETE FROM %Q.sqlite_sequence WHERE na"...
0x1800827b7  mov     r8, [r14+rbp]
0x1800827bb  mov     rcx, rsi
0x1800827be  call    sqlite3NestedParse
0x1800827c3  mov     r9, [rbx]
0x1800827c6  lea     rdx, aDeleteFromQSql_1; "DELETE FROM %Q.sqlite_master WHERE tbl_"...
0x1800827cd  mov     r8, [r14+rbp]
0x1800827d1  mov     rcx, rsi
0x1800827d4  call    sqlite3NestedParse
0x1800827d9  test    r12d, r12d
0x1800827dc  jnz     short loc_180082835
0x1800827de  cmp     byte ptr [rbx+3Fh], 1
0x1800827e2  jz      short loc_18008283B
0x1800827e4  mov     ebp, [rbx+28h]
0x1800827e7  xor     ecx, ecx
0x1800827e9  test    ecx, ecx
0x1800827eb  jz      short loc_1800827F3
0x1800827ed  xor     edi, edi
0x1800827ef  cmp     ebp, ecx
0x1800827f1  jnb     short loc_1800827F5
0x1800827f3  mov     edi, ebp
0x1800827f5  mov     rax, [rbx+10h]
0x1800827f9  jmp     short loc_18008280F
0x1800827fb  test    ecx, ecx
0x1800827fd  jz      short loc_180082804
0x1800827ff  cmp     [rax+58h], ecx
0x180082802  jnb     short loc_18008280B
0x180082804  cmp     [rax+58h], edi
0x180082807  cmova   edi, [rax+58h]
0x18008280b  mov     rax, [rax+28h]
0x18008280f  test    rax, rax
0x180082812  jnz     short loc_1800827FB
0x180082814  test    edi, edi
0x180082816  jz      short loc_180082835
0x180082818  mov     rdx, [rbx+60h]
0x18008281c  mov     rcx, [rsi]
0x18008281f  call    sqlite3SchemaToIndex
0x180082824  mov     r8d, eax
0x180082827  mov     rcx, rsi
0x18008282a  mov     edx, edi
0x18008282c  call    destroyRootPage
0x180082831  mov     ecx, edi
0x180082833  jmp     short loc_1800827E9
0x180082835  cmp     byte ptr [rbx+3Fh], 1
0x180082839  jnz     short loc_180082884
0x18008283b  mov     rax, [rbx]
0x18008283e  xor     r9d, r9d
0x180082841  mov     edi, [rsp+88h+arg_10]
0x180082848  mov     edx, 0ACh
0x18008284d  mov     [rsp+88h+var_58], 0
0x180082855  mov     r8d, edi
0x180082858  mov     [rsp+88h+var_60], rax
0x18008285d  mov     rcx, r13
0x180082860  mov     [rsp+88h+var_68], 0
0x180082868  call    sqlite3VdbeAddOp4
0x18008286d  mov     rax, [rsi+0B0h]
0x180082874  mov     rcx, rsi
0x180082877  test    rax, rax
0x18008287a  cmovnz  rcx, rax
0x18008287e  mov     byte ptr [rcx+21h], 1
0x180082882  jmp     short loc_18008288B
0x180082884  mov     edi, [rsp+88h+arg_10]
0x18008288b  mov     rax, [rbx]
0x18008288e  xor     r9d, r9d
0x180082891  mov     [rsp+88h+var_58], 0
0x180082899  mov     r8d, edi
0x18008289c  mov     [rsp+88h+var_60], rax
0x1800828a1  mov     edx, 97h
0x1800828a6  mov     rcx, r13
0x1800828a9  mov     [rsp+88h+var_68], 0
0x1800828b1  call    sqlite3VdbeAddOp4
0x1800828b6  mov     rax, [rsi]
0x1800828b9  mov     r9d, 1
0x1800828bf  mov     r8d, edi
0x1800828c2  mov     rcx, [rax+20h]
0x1800828c6  lea     edx, [r9+63h]
0x1800828ca  mov     rax, [rcx+r14+18h]
0x1800828cf  mov     ecx, [rax]
0x1800828d1  inc     ecx
0x1800828d3  mov     [rsp+88h+var_68], ecx
0x1800828d7  mov     rcx, [rsi+10h]
0x1800828db  call    sqlite3VdbeAddOp3
0x1800828e0  mov     rax, [r15+20h]
0x1800828e4  mov     rbx, [rax+r14+18h]
0x1800828e9  test    byte ptr [rbx+72h], 2
0x1800828ed  jz      short loc_180082921
0x1800828ef  mov     rbx, [rbx+10h]
0x1800828f3  jmp     short loc_18008290A
0x1800828f5  mov     rdx, [rbx+10h]
0x1800828f9  cmp     byte ptr [rdx+3Fh], 2
0x1800828fd  jnz     short loc_180082907
0x1800828ff  mov     rcx, r15
0x180082902  call    sqlite3DeleteColumnNames
0x180082907  mov     rbx, [rbx]
0x18008290a  test    rbx, rbx
0x18008290d  jnz     short loc_1800828F5
0x18008290f  mov     rax, [r15+20h]
0x180082913  mov     rcx, [rax+r14+18h]
0x180082918  mov     eax, 0FFFDh
0x18008291d  and     [rcx+72h], ax
0x180082921  add     rsp, 48h
0x180082925  pop     r15
0x180082927  pop     r14
0x180082929  pop     r13
0x18008292b  pop     r12
0x18008292d  pop     rdi
0x18008292e  pop     rsi
0x18008292f  pop     rbp
0x180082930  pop     rbx
0x180082931  retn
```
