# updateFromSelect

- ea: `0x18006a580`
- end: `0x18006a7b1`
- name: `updateFromSelect`
- size: `561`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18000a954`
- `0x1800a14d0`

## callees

- `0x180001980`
- `0x180005650`
- `0x180014270`
- `0x180015118`
- `0x180015540`
- `0x18001b16c`
- `0x18001b818`
- `0x18006a580`
- `0x18006a7b8`
- `0x18007e6dc`

## pseudocode

```c
__int64 __fastcall updateFromSelect(_QWORD *a1, int a2, __int64 a3, int *a4, __int64 a5, __int64 a6)
{
  __int64 v8; // rdi
  int *v9; // r15
  __int64 appended; // r12
  int v11; // r13d
  __int64 v12; // rcx
  int v13; // ebx
  __int64 v14; // rax
  bool v15; // zf
  char v16; // r15
  unsigned int i; // ebx
  __int64 v18; // rax
  char v19; // bl
  __int64 v20; // rax
  int v21; // edi
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 *v24; // rdi
  __int128 v26[7]; // [rsp+50h] [rbp-31h] BYREF
  _QWORD *v27; // [rsp+D0h] [rbp+4Fh]
  int v29; // [rsp+E0h] [rbp+5Fh]
  __int64 v31; // [rsp+F0h] [rbp+6Fh]

  v27 = (_QWORD *)*a1;
  v8 = *(_QWORD *)(a5 + 40);
  v9 = a4;
  memset(v26, 0, 37);
  appended = 0;
  v31 = sqlite3SrcListDup(v27, a5, 0);
  v11 = v31;
  v29 = sqlite3ExprDup(v27, a6, 0);
  if ( v31 )
  {
    v12 = *(_QWORD *)(v31 + 40);
    *(_DWORD *)(v31 + 76) = -1;
    --*(_DWORD *)(v12 + 44);
    *(_QWORD *)(v31 + 40) = 0;
  }
  if ( a3 )
  {
    v13 = 0;
    if ( *(_WORD *)(a3 + 94) )
    {
      do
      {
        v14 = exprRowColumn(a1, (unsigned int)*(__int16 *)(*(_QWORD *)(a3 + 8) + 2LL * v13));
        appended = sqlite3ExprListAppend(a1, appended, v14);
        ++v13;
      }
      while ( v13 < *(unsigned __int16 *)(a3 + 94) );
    }
    v15 = *(_BYTE *)(v8 + 63) == 1;
    goto LABEL_12;
  }
  v16 = *(_BYTE *)(v8 + 63);
  if ( v16 != 2 )
  {
    v20 = sqlite3PExpr(a1, 75, 0, 0);
    appended = sqlite3ExprListAppendNew(*a1, v20);
    v15 = v16 == 1;
    v9 = a4;
LABEL_12:
    v19 = !v15 + 14;
    goto LABEL_13;
  }
  for ( i = 0; (int)i < *(__int16 *)(v8 + 54); ++i )
  {
    v18 = exprRowColumn(a1, i);
    appended = sqlite3ExprListAppend(a1, appended, v18);
  }
  v9 = a4;
  v19 = 14;
LABEL_13:
  if ( v9 )
  {
    v21 = 0;
    if ( *v9 > 0 )
    {
      do
      {
        v22 = sqlite3ExprDup(v27, *(_QWORD *)&v9[8 * v21++ + 2], 0);
        appended = sqlite3ExprListAppend(a1, appended, v22);
      }
      while ( v21 < *v9 );
      v11 = v31;
    }
  }
  v23 = sqlite3SelectNew((_DWORD)a1, appended, v11, v29, 0, 0, 0, 276955136, 0);
  v24 = (__int64 *)v23;
  if ( v23 )
    *(_DWORD *)(v23 + 4) |= 0x8000000u;
  DWORD1(v26[0]) = a2;
  LOBYTE(v26[0]) = v19;
  *((_QWORD *)&v26[1] + 1) = 0;
  *(_QWORD *)((char *)v26 + 12) = 0;
  if ( a3 )
    DWORD2(v26[0]) = *(unsigned __int16 *)(a3 + 94);
  else
    DWORD2(v26[0]) = -1;
  sqlite3Select((__int64)a1, v23, v26);
  return sqlite3SelectDelete(v27, v24);
}

```

## disassembly

```asm
0x18006a580  mov     [rsp-8+arg_18], r9
0x18006a585  mov     [rsp-8+arg_8], edx
0x18006a589  push    rbp
0x18006a58a  push    rbx
0x18006a58b  push    rsi
0x18006a58c  push    rdi
0x18006a58d  push    r12
0x18006a58f  push    r13
0x18006a591  push    r14
0x18006a593  push    r15
0x18006a595  lea     rbp, [rsp-7]
0x18006a59a  sub     rsp, 88h
0x18006a5a1  mov     rbx, [rcx]
0x18006a5a4  xorps   xmm0, xmm0
0x18006a5a7  mov     rdx, [rbp+3Fh+arg_20]
0x18006a5ab  mov     r14, r8
0x18006a5ae  mov     rsi, rcx
0x18006a5b1  mov     [rbp+3Fh+arg_0], rbx
0x18006a5b5  xor     eax, eax
0x18006a5b7  xor     r8d, r8d
0x18006a5ba  movups  [rbp+3Fh+var_60], xmm0
0x18006a5be  mov     rdi, [rdx+28h]
0x18006a5c2  mov     rcx, rbx
0x18006a5c5  mov     r15, r9
0x18006a5c8  mov     qword ptr [rbp+3Fh+var_60+0Dh], rax
0x18006a5cc  movups  [rbp+3Fh+var_70], xmm0
0x18006a5d0  xor     r12d, r12d
0x18006a5d3  call    sqlite3SrcListDup
0x18006a5d8  mov     rdx, [rbp+3Fh+arg_28]
0x18006a5dc  xor     r8d, r8d
0x18006a5df  mov     rcx, rbx
0x18006a5e2  mov     [rbp+3Fh+arg_20], rax
0x18006a5e6  mov     r13, rax
0x18006a5e9  call    sqlite3ExprDup
0x18006a5ee  mov     [rbp+3Fh+arg_10], rax
0x18006a5f2  test    r13, r13
0x18006a5f5  jz      short loc_18006A60A
0x18006a5f7  mov     rcx, [r13+28h]
0x18006a5fb  mov     dword ptr [r13+4Ch], 0FFFFFFFFh
0x18006a603  dec     dword ptr [rcx+2Ch]
0x18006a606  mov     [r13+28h], r12
0x18006a60a  test    r14, r14
0x18006a60d  jz      short loc_18006A651
0x18006a60f  xor     ebx, ebx
0x18006a611  xor     eax, eax
0x18006a613  cmp     ax, [r14+5Eh]
0x18006a618  jnb     short loc_18006A649
0x18006a61a  mov     rax, [r14+8]
0x18006a61e  movsxd  rcx, ebx
0x18006a621  movsx   edx, word ptr [rax+rcx*2]
0x18006a625  mov     rcx, rsi
0x18006a628  call    exprRowColumn
0x18006a62d  mov     r8, rax
0x18006a630  mov     rdx, r12
0x18006a633  mov     rcx, rsi
0x18006a636  call    sqlite3ExprListAppend
0x18006a63b  mov     r12, rax
0x18006a63e  inc     ebx
0x18006a640  movzx   eax, word ptr [r14+5Eh]
0x18006a645  cmp     ebx, eax
0x18006a647  jl      short loc_18006A61A
0x18006a649  xor     ebx, ebx
0x18006a64b  cmp     byte ptr [rdi+3Fh], 1
0x18006a64f  jmp     short loc_18006A6BF
0x18006a651  mov     r15b, [rdi+3Fh]
0x18006a655  cmp     r15b, 2
0x18006a659  jnz     short loc_18006A695
0x18006a65b  xor     ebx, ebx
0x18006a65d  xor     eax, eax
0x18006a65f  cmp     ax, [rdi+36h]
0x18006a663  jge     short loc_18006A68A
0x18006a665  mov     edx, ebx
0x18006a667  mov     rcx, rsi
0x18006a66a  call    exprRowColumn
0x18006a66f  mov     r8, rax
0x18006a672  mov     rdx, r12
0x18006a675  mov     rcx, rsi
0x18006a678  call    sqlite3ExprListAppend
0x18006a67d  mov     r12, rax
0x18006a680  inc     ebx
0x18006a682  movsx   eax, word ptr [rdi+36h]
0x18006a686  cmp     ebx, eax
0x18006a688  jl      short loc_18006A665
0x18006a68a  mov     r15, [rbp+3Fh+arg_18]
0x18006a68e  mov     ebx, 0Eh
0x18006a693  jmp     short loc_18006A6C5
0x18006a695  xor     r9d, r9d
0x18006a698  xor     r8d, r8d
0x18006a69b  mov     rcx, rsi
0x18006a69e  lea     edx, [r9+4Bh]
0x18006a6a2  call    sqlite3PExpr
0x18006a6a7  mov     rcx, [rsi]
0x18006a6aa  mov     rdx, rax
0x18006a6ad  call    sqlite3ExprListAppendNew
0x18006a6b2  xor     ebx, ebx
0x18006a6b4  mov     r12, rax
0x18006a6b7  cmp     r15b, 1
0x18006a6bb  mov     r15, [rbp+3Fh+arg_18]
0x18006a6bf  setnz   bl
0x18006a6c2  add     ebx, 0Eh
0x18006a6c5  test    r15, r15
0x18006a6c8  jz      short loc_18006A708
0x18006a6ca  xor     edi, edi
0x18006a6cc  cmp     [r15], edi
0x18006a6cf  jle     short loc_18006A708
0x18006a6d1  mov     r13, [rbp+3Fh+arg_0]
0x18006a6d5  movsxd  rdx, edi
0x18006a6d8  xor     r8d, r8d
0x18006a6db  shl     rdx, 5
0x18006a6df  mov     rcx, r13
0x18006a6e2  mov     rdx, [rdx+r15+8]
0x18006a6e7  call    sqlite3ExprDup
0x18006a6ec  mov     r8, rax
0x18006a6ef  mov     rdx, r12
0x18006a6f2  mov     rcx, rsi
0x18006a6f5  call    sqlite3ExprListAppend
0x18006a6fa  inc     edi
0x18006a6fc  mov     r12, rax
0x18006a6ff  cmp     edi, [r15]
0x18006a702  jl      short loc_18006A6D5
0x18006a704  mov     r13, [rbp+3Fh+arg_20]
0x18006a708  mov     r9, [rbp+3Fh+arg_10]
0x18006a70c  mov     r8, r13
0x18006a70f  mov     [rsp+0C0h+var_80], 0
0x18006a718  mov     rdx, r12
0x18006a71b  mov     [rsp+0C0h+var_88], 10820000h
0x18006a723  mov     rcx, rsi
0x18006a726  mov     [rsp+0C0h+var_90], 0
0x18006a72f  mov     [rsp+0C0h+var_98], 0
0x18006a738  mov     [rsp+0C0h+var_A0], 0
0x18006a741  call    sqlite3SelectNew
0x18006a746  mov     rdi, rax
0x18006a749  test    rax, rax
0x18006a74c  jz      short loc_18006A753
0x18006a74e  bts     dword ptr [rax+4], 1Bh
0x18006a753  mov     eax, [rbp+3Fh+arg_8]
0x18006a756  mov     dword ptr [rbp+3Fh+var_70+4], eax
0x18006a759  mov     byte ptr [rbp+3Fh+var_70], bl
0x18006a75c  mov     qword ptr [rbp+3Fh+var_60+8], 0
0x18006a764  mov     qword ptr [rbp+3Fh+var_70+0Ch], 0
0x18006a76c  test    r14, r14
0x18006a76f  jz      short loc_18006A77B
0x18006a771  movzx   eax, word ptr [r14+5Eh]
0x18006a776  mov     dword ptr [rbp+3Fh+var_70+8], eax
0x18006a779  jmp     short loc_18006A782
0x18006a77b  mov     dword ptr [rbp+3Fh+var_70+8], 0FFFFFFFFh
0x18006a782  lea     r8, [rbp+3Fh+var_70]
0x18006a786  mov     rdx, rdi
0x18006a789  mov     rcx, rsi
0x18006a78c  call    sqlite3Select
0x18006a791  mov     rcx, [rbp+3Fh+arg_0]
0x18006a795  mov     rdx, rdi
0x18006a798  call    sqlite3SelectDelete
0x18006a79d  add     rsp, 88h
0x18006a7a4  pop     r15
0x18006a7a6  pop     r14
0x18006a7a8  pop     r13
0x18006a7aa  pop     r12
0x18006a7ac  pop     rdi
0x18006a7ad  pop     rsi
0x18006a7ae  pop     rbx
0x18006a7af  pop     rbp
0x18006a7b0  retn
```
