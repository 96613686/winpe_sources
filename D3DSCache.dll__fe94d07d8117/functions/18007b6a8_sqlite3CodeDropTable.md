# sqlite3CodeDropTable

- ea: `0x18007b6a8`
- end: `0x18007b8c2`
- name: `sqlite3CodeDropTable`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18007e8bc`

## callees

- `0x18000b4bc`
- `0x1800369e4`
- `0x18003be78`
- `0x18003cc7c`
- `0x18003d480`
- `0x18003e7c0`
- `0x18003f844`
- `0x180042c38`
- `0x18005cb74`
- `0x18007b6a8`
- `0x18007ebd8`

## string_xrefs

- `0x18007b740`: `DELETE FROM %Q.sqlite_sequence WHERE name=%Q`
- `0x18007b756`: `DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'`

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
  unsigned int v17; // eax
  unsigned int v18; // edi
  _QWORD *v19; // rcx
  __int64 result; // rax
  __int64 v21; // rbx
  _QWORD *m; // rbx
  __int64 v23; // rcx

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
      if ( *(_BYTE *)(m[2] + 63LL) == 2 )
        sqlite3DeleteColumnNames(v4);
    }
    v23 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + v9 + 24);
    result = 65533;
    *(_WORD *)(v23 + 114) &= ~2u;
  }
  return result;
}

```

## disassembly

```asm
0x18007b6a8  mov     [rsp+arg_10], r8d
0x18007b6ad  push    rbx
0x18007b6ae  push    rbp
0x18007b6af  push    rsi
0x18007b6b0  push    rdi
0x18007b6b1  push    r12
0x18007b6b3  push    r13
0x18007b6b5  push    r14
0x18007b6b7  push    r15
0x18007b6b9  sub     rsp, 48h
0x18007b6bd  mov     r15, [rcx]
0x18007b6c0  mov     r12d, r9d
0x18007b6c3  movsxd  rdi, r8d
0x18007b6c6  mov     rbx, rdx
0x18007b6c9  mov     r14, rdi
0x18007b6cc  mov     rsi, rcx
0x18007b6cf  shl     r14, 5
0x18007b6d3  mov     rbp, [r15+20h]
0x18007b6d7  call    sqlite3GetVdbe
0x18007b6dc  mov     r8d, edi
0x18007b6df  mov     edx, 1
0x18007b6e4  mov     rcx, rsi
0x18007b6e7  mov     r13, rax
0x18007b6ea  call    sqlite3BeginWriteOperation
0x18007b6ef  cmp     byte ptr [rbx+3Fh], 1
0x18007b6f3  jnz     short loc_18007B710
0x18007b6f5  xor     r9d, r9d
0x18007b6f8  mov     [rsp+88h+var_68], 0
0x18007b700  xor     r8d, r8d
0x18007b703  mov     edx, 0AAh
0x18007b708  mov     rcx, r13
0x18007b70b  call    sqlite3VdbeAddOp3
0x18007b710  mov     rdx, rbx
0x18007b713  mov     rcx, rsi
0x18007b716  call    sqlite3TriggerList
0x18007b71b  mov     rdi, rax
0x18007b71e  test    rax, rax
0x18007b721  jz      short loc_18007B737
0x18007b723  mov     rdx, rdi
0x18007b726  mov     rcx, rsi
0x18007b729  call    sqlite3DropTriggerPtr
0x18007b72e  mov     rdi, [rdi+40h]
0x18007b732  test    rdi, rdi
0x18007b735  jnz     short loc_18007B723
0x18007b737  test    byte ptr [rbx+30h], 8
0x18007b73b  jz      short loc_18007B753
0x18007b73d  mov     r9, [rbx]
0x18007b740  lea     rdx, aDeleteFromQSql_0; "DELETE FROM %Q.sqlite_sequence WHERE na"...
0x18007b747  mov     r8, [r14+rbp]
0x18007b74b  mov     rcx, rsi
0x18007b74e  call    sqlite3NestedParse
0x18007b753  mov     r9, [rbx]
0x18007b756  lea     rdx, aDeleteFromQSql_1; "DELETE FROM %Q.sqlite_master WHERE tbl_"...
0x18007b75d  mov     r8, [r14+rbp]
0x18007b761  mov     rcx, rsi
0x18007b764  call    sqlite3NestedParse
0x18007b769  test    r12d, r12d
0x18007b76c  jnz     short loc_18007B7C5
0x18007b76e  cmp     byte ptr [rbx+3Fh], 1
0x18007b772  jz      short loc_18007B7CB
0x18007b774  mov     ebp, [rbx+28h]
0x18007b777  xor     ecx, ecx
0x18007b779  test    ecx, ecx
0x18007b77b  jz      short loc_18007B783
0x18007b77d  xor     edi, edi
0x18007b77f  cmp     ebp, ecx
0x18007b781  jnb     short loc_18007B785
0x18007b783  mov     edi, ebp
0x18007b785  mov     rax, [rbx+10h]
0x18007b789  jmp     short loc_18007B79F
0x18007b78b  test    ecx, ecx
0x18007b78d  jz      short loc_18007B794
0x18007b78f  cmp     [rax+58h], ecx
0x18007b792  jnb     short loc_18007B79B
0x18007b794  cmp     [rax+58h], edi
0x18007b797  cmova   edi, [rax+58h]
0x18007b79b  mov     rax, [rax+28h]
0x18007b79f  test    rax, rax
0x18007b7a2  jnz     short loc_18007B78B
0x18007b7a4  test    edi, edi
0x18007b7a6  jz      short loc_18007B7C5
0x18007b7a8  mov     rdx, [rbx+60h]
0x18007b7ac  mov     rcx, [rsi]
0x18007b7af  call    sqlite3SchemaToIndex
0x18007b7b4  mov     r8d, eax
0x18007b7b7  mov     rcx, rsi
0x18007b7ba  mov     edx, edi
0x18007b7bc  call    destroyRootPage
0x18007b7c1  mov     ecx, edi
0x18007b7c3  jmp     short loc_18007B779
0x18007b7c5  cmp     byte ptr [rbx+3Fh], 1
0x18007b7c9  jnz     short loc_18007B814
0x18007b7cb  mov     rax, [rbx]
0x18007b7ce  xor     r9d, r9d
0x18007b7d1  mov     edi, [rsp+88h+arg_10]
0x18007b7d8  mov     edx, 0ACh
0x18007b7dd  mov     [rsp+88h+var_58], 0
0x18007b7e5  mov     r8d, edi
0x18007b7e8  mov     [rsp+88h+var_60], rax
0x18007b7ed  mov     rcx, r13
0x18007b7f0  mov     [rsp+88h+var_68], 0
0x18007b7f8  call    sqlite3VdbeAddOp4
0x18007b7fd  mov     rax, [rsi+0B0h]
0x18007b804  mov     rcx, rsi
0x18007b807  test    rax, rax
0x18007b80a  cmovnz  rcx, rax
0x18007b80e  mov     byte ptr [rcx+21h], 1
0x18007b812  jmp     short loc_18007B81B
0x18007b814  mov     edi, [rsp+88h+arg_10]
0x18007b81b  mov     rax, [rbx]
0x18007b81e  xor     r9d, r9d
0x18007b821  mov     [rsp+88h+var_58], 0
0x18007b829  mov     r8d, edi
0x18007b82c  mov     [rsp+88h+var_60], rax
0x18007b831  mov     edx, 97h
0x18007b836  mov     rcx, r13
0x18007b839  mov     [rsp+88h+var_68], 0
0x18007b841  call    sqlite3VdbeAddOp4
0x18007b846  mov     rax, [rsi]
0x18007b849  mov     r9d, 1
0x18007b84f  mov     r8d, edi
0x18007b852  mov     rcx, [rax+20h]
0x18007b856  lea     edx, [r9+63h]
0x18007b85a  mov     rax, [rcx+r14+18h]
0x18007b85f  mov     ecx, [rax]
0x18007b861  inc     ecx
0x18007b863  mov     [rsp+88h+var_68], ecx
0x18007b867  mov     rcx, [rsi+10h]
0x18007b86b  call    sqlite3VdbeAddOp3
0x18007b870  mov     rax, [r15+20h]
0x18007b874  mov     rbx, [rax+r14+18h]
0x18007b879  test    byte ptr [rbx+72h], 2
0x18007b87d  jz      short loc_18007B8B1
0x18007b87f  mov     rbx, [rbx+10h]
0x18007b883  jmp     short loc_18007B89A
0x18007b885  mov     rdx, [rbx+10h]
0x18007b889  cmp     byte ptr [rdx+3Fh], 2
0x18007b88d  jnz     short loc_18007B897
0x18007b88f  mov     rcx, r15
0x18007b892  call    sqlite3DeleteColumnNames
0x18007b897  mov     rbx, [rbx]
0x18007b89a  test    rbx, rbx
0x18007b89d  jnz     short loc_18007B885
0x18007b89f  mov     rax, [r15+20h]
0x18007b8a3  mov     rcx, [rax+r14+18h]
0x18007b8a8  mov     eax, 0FFFDh
0x18007b8ad  and     [rcx+72h], ax
0x18007b8b1  add     rsp, 48h
0x18007b8b5  pop     r15
0x18007b8b7  pop     r14
0x18007b8b9  pop     r13
0x18007b8bb  pop     r12
0x18007b8bd  pop     rdi
0x18007b8be  pop     rsi
0x18007b8bf  pop     rbp
0x18007b8c0  pop     rbx
0x18007b8c1  retn
```
