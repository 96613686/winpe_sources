# sqlite3CodeDropTable

- ea: `0x18006e0a0`
- end: `0x18006e2c1`
- name: `sqlite3CodeDropTable`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x180072d54`

## callees

- `0x1800427c4`
- `0x180069d64`
- `0x18006db58`
- `0x18006e0a0`
- `0x180071ca0`
- `0x1800730f0`
- `0x18007d478`
- `0x1800817f4`
- `0x18008f71c`
- `0x1800923d8`
- `0x1800927e0`

## string_xrefs

- `0x18006e14e`: `DELETE FROM %Q.sqlite_master WHERE tbl_name=%Q and type!='trigger'`
- `0x18006e138`: `DELETE FROM %Q.sqlite_sequence WHERE name=%Q`

## pseudocode

```c
__int64 __fastcall sqlite3CodeDropTable(_QWORD *a1, _QWORD *a2, unsigned int a3, int a4)
{
  __int64 v4; // r13
  __int64 v9; // r14
  __int64 v10; // rbp
  __int64 Vdbe; // r12
  __int64 i; // rbx
  unsigned int v13; // ebp
  unsigned int j; // ecx
  unsigned int v15; // ebx
  __int64 k; // rax
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // rdx
  unsigned int v20; // ebp
  __int64 v21; // rbx
  unsigned int v22; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rbx
  unsigned int v25; // eax
  __int64 result; // rax
  __int64 v27; // rbx
  _QWORD *m; // rbx
  __int64 v29; // rcx

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
      goto LABEL_26;
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
      v17 = a2[12];
      v18 = 4294934528LL;
      if ( v17 )
      {
        v18 = 0;
        v19 = *(_QWORD *)(*a1 + 32LL);
        if ( *(_QWORD *)(v19 + 24) != v17 )
        {
          do
            v18 = (unsigned int)(v18 + 1);
          while ( *(_QWORD *)(32LL * (int)v18 + v19 + 24) != v17 );
        }
      }
      destroyRootPage(a1, v15, v18);
    }
  }
  if ( *((_BYTE *)a2 + 63) != 1 )
  {
    v20 = a3;
    goto LABEL_30;
  }
LABEL_26:
  v20 = a3;
  v21 = *a2;
  v22 = sqlite3VdbeAddOp3(Vdbe, 172, a3, 0, 0);
  sqlite3VdbeChangeP4(Vdbe, v22, v21, 0);
  v23 = a1;
  if ( a1[22] )
    v23 = (_QWORD *)a1[22];
  *((_BYTE *)v23 + 33) = 1;
LABEL_30:
  v24 = *a2;
  v25 = sqlite3VdbeAddOp3(Vdbe, 151, v20, 0, 0);
  sqlite3VdbeChangeP4(Vdbe, v25, v24, 0);
  sqlite3ChangeCookie(a1, v20);
  result = *(_QWORD *)(v4 + 32);
  v27 = *(_QWORD *)(result + v9 + 24);
  if ( (*(_BYTE *)(v27 + 114) & 2) != 0 )
  {
    for ( m = *(_QWORD **)(v27 + 16); m; m = (_QWORD *)*m )
    {
      if ( *(_BYTE *)(m[2] + 63LL) == 2 )
        sqlite3DeleteColumnNames(v4);
    }
    v29 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + v9 + 24);
    result = 65533;
    *(_WORD *)(v29 + 114) &= ~2u;
  }
  return result;
}

```

## disassembly

```asm
0x18006e0a0  mov     [rsp+arg_10], r8d
0x18006e0a5  push    rbx
0x18006e0a6  push    rbp
0x18006e0a7  push    rsi
0x18006e0a8  push    rdi
0x18006e0a9  push    r12
0x18006e0ab  push    r13
0x18006e0ad  push    r14
0x18006e0af  push    r15
0x18006e0b1  sub     rsp, 38h
0x18006e0b5  mov     r13, [rcx]
0x18006e0b8  mov     r15d, r9d
0x18006e0bb  movsxd  rbx, r8d
0x18006e0be  mov     rdi, rdx
0x18006e0c1  mov     r14, rbx
0x18006e0c4  mov     rsi, rcx
0x18006e0c7  shl     r14, 5
0x18006e0cb  mov     rbp, [r13+20h]
0x18006e0cf  call    sqlite3GetVdbe
0x18006e0d4  mov     r8d, ebx
0x18006e0d7  mov     edx, 1
0x18006e0dc  mov     rcx, rsi
0x18006e0df  mov     r12, rax
0x18006e0e2  call    sqlite3BeginWriteOperation
0x18006e0e7  cmp     byte ptr [rdi+3Fh], 1
0x18006e0eb  jnz     short loc_18006E108
0x18006e0ed  xor     r9d, r9d
0x18006e0f0  mov     [rsp+78h+var_58], 0
0x18006e0f8  xor     r8d, r8d
0x18006e0fb  mov     edx, 0AAh
0x18006e100  mov     rcx, r12
0x18006e103  call    sqlite3VdbeAddOp3
0x18006e108  mov     rdx, rdi
0x18006e10b  mov     rcx, rsi
0x18006e10e  call    sqlite3TriggerList
0x18006e113  mov     rbx, rax
0x18006e116  test    rax, rax
0x18006e119  jz      short loc_18006E12F
0x18006e11b  mov     rdx, rbx
0x18006e11e  mov     rcx, rsi
0x18006e121  call    sqlite3DropTriggerPtr
0x18006e126  mov     rbx, [rbx+40h]
0x18006e12a  test    rbx, rbx
0x18006e12d  jnz     short loc_18006E11B
0x18006e12f  test    byte ptr [rdi+30h], 8
0x18006e133  jz      short loc_18006E14B
0x18006e135  mov     r9, [rdi]
0x18006e138  lea     rdx, aDeleteFromQSql_0; "DELETE FROM %Q.sqlite_sequence WHERE na"...
0x18006e13f  mov     r8, [r14+rbp]
0x18006e143  mov     rcx, rsi
0x18006e146  call    sqlite3NestedParse
0x18006e14b  mov     r9, [rdi]
0x18006e14e  lea     rdx, aDeleteFromQSql_1; "DELETE FROM %Q.sqlite_master WHERE tbl_"...
0x18006e155  mov     r8, [r14+rbp]
0x18006e159  mov     rcx, rsi
0x18006e15c  call    sqlite3NestedParse
0x18006e161  test    r15d, r15d
0x18006e164  jnz     short loc_18006E1DE
0x18006e166  cmp     byte ptr [rdi+3Fh], 1
0x18006e16a  jz      short loc_18006E1E4
0x18006e16c  mov     ebp, [rdi+28h]
0x18006e16f  xor     ecx, ecx
0x18006e171  test    ecx, ecx
0x18006e173  jz      short loc_18006E17B
0x18006e175  xor     ebx, ebx
0x18006e177  cmp     ebp, ecx
0x18006e179  jnb     short loc_18006E17D
0x18006e17b  mov     ebx, ebp
0x18006e17d  mov     rax, [rdi+10h]
0x18006e181  jmp     short loc_18006E197
0x18006e183  test    ecx, ecx
0x18006e185  jz      short loc_18006E18C
0x18006e187  cmp     [rax+58h], ecx
0x18006e18a  jnb     short loc_18006E193
0x18006e18c  cmp     [rax+58h], ebx
0x18006e18f  cmova   ebx, [rax+58h]
0x18006e193  mov     rax, [rax+28h]
0x18006e197  test    rax, rax
0x18006e19a  jnz     short loc_18006E183
0x18006e19c  test    ebx, ebx
0x18006e19e  jz      short loc_18006E1DE
0x18006e1a0  mov     rcx, [rdi+60h]
0x18006e1a4  mov     r8d, 0FFFF8000h
0x18006e1aa  test    rcx, rcx
0x18006e1ad  jz      short loc_18006E1D0
0x18006e1af  mov     rax, [rsi]
0x18006e1b2  xor     r8d, r8d
0x18006e1b5  mov     rdx, [rax+20h]
0x18006e1b9  cmp     [rdx+18h], rcx
0x18006e1bd  jz      short loc_18006E1D0
0x18006e1bf  inc     r8d
0x18006e1c2  movsxd  rax, r8d
0x18006e1c5  shl     rax, 5
0x18006e1c9  cmp     [rax+rdx+18h], rcx
0x18006e1ce  jnz     short loc_18006E1BF
0x18006e1d0  mov     edx, ebx
0x18006e1d2  mov     rcx, rsi
0x18006e1d5  call    destroyRootPage
0x18006e1da  mov     ecx, ebx
0x18006e1dc  jmp     short loc_18006E171
0x18006e1de  cmp     byte ptr [rdi+3Fh], 1
0x18006e1e2  jnz     short loc_18006E230
0x18006e1e4  mov     ebp, [rsp+78h+arg_10]
0x18006e1eb  xor     r9d, r9d
0x18006e1ee  mov     rbx, [rdi]
0x18006e1f1  mov     r8d, ebp
0x18006e1f4  mov     edx, 0ACh
0x18006e1f9  mov     [rsp+78h+var_58], 0
0x18006e201  mov     rcx, r12
0x18006e204  call    sqlite3VdbeAddOp3
0x18006e209  xor     r9d, r9d
0x18006e20c  mov     r8, rbx
0x18006e20f  mov     edx, eax
0x18006e211  mov     rcx, r12
0x18006e214  call    sqlite3VdbeChangeP4
0x18006e219  mov     rax, [rsi+0B0h]
0x18006e220  mov     rcx, rsi
0x18006e223  test    rax, rax
0x18006e226  cmovnz  rcx, rax
0x18006e22a  mov     byte ptr [rcx+21h], 1
0x18006e22e  jmp     short loc_18006E237
0x18006e230  mov     ebp, [rsp+78h+arg_10]
0x18006e237  mov     rbx, [rdi]
0x18006e23a  xor     r9d, r9d
0x18006e23d  mov     r8d, ebp
0x18006e240  mov     [rsp+78h+var_58], 0
0x18006e248  mov     edx, 97h
0x18006e24d  mov     rcx, r12
0x18006e250  call    sqlite3VdbeAddOp3
0x18006e255  xor     r9d, r9d
0x18006e258  mov     r8, rbx
0x18006e25b  mov     edx, eax
0x18006e25d  mov     rcx, r12
0x18006e260  call    sqlite3VdbeChangeP4
0x18006e265  mov     edx, ebp
0x18006e267  mov     rcx, rsi
0x18006e26a  call    sqlite3ChangeCookie
0x18006e26f  mov     rax, [r13+20h]
0x18006e273  mov     rbx, [rax+r14+18h]
0x18006e278  test    byte ptr [rbx+72h], 2
0x18006e27c  jz      short loc_18006E2B0
0x18006e27e  mov     rbx, [rbx+10h]
0x18006e282  jmp     short loc_18006E299
0x18006e284  mov     rdx, [rbx+10h]
0x18006e288  cmp     byte ptr [rdx+3Fh], 2
0x18006e28c  jnz     short loc_18006E296
0x18006e28e  mov     rcx, r13
0x18006e291  call    sqlite3DeleteColumnNames
0x18006e296  mov     rbx, [rbx]
0x18006e299  test    rbx, rbx
0x18006e29c  jnz     short loc_18006E284
0x18006e29e  mov     rax, [r13+20h]
0x18006e2a2  mov     rcx, [rax+r14+18h]
0x18006e2a7  mov     eax, 0FFFDh
0x18006e2ac  and     [rcx+72h], ax
0x18006e2b0  add     rsp, 38h
0x18006e2b4  pop     r15
0x18006e2b6  pop     r14
0x18006e2b8  pop     r13
0x18006e2ba  pop     r12
0x18006e2bc  pop     rdi
0x18006e2bd  pop     rsi
0x18006e2be  pop     rbp
0x18006e2bf  pop     rbx
0x18006e2c0  retn
```
