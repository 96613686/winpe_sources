# updateFromSelect

- ea: `0x180092f78`
- end: `0x1800931ab`
- name: `updateFromSelect`
- size: `563`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x1800167c0`
- `0x18005e35c`

## callees

- `0x18000c850`
- `0x18000f820`
- `0x180010950`
- `0x18003465c`
- `0x180037194`
- `0x18003e1e0`
- `0x18003fc90`
- `0x18006eb80`
- `0x180092f78`

## pseudocode

```c
__int64 __fastcall updateFromSelect(__int64 *a1, int a2, __int64 a3, int *a4, __int64 a5, __int64 a6)
{
  __int64 v8; // rdi
  int *v9; // r15
  __int64 v10; // r12
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
  __int64 v24; // rdi
  __int128 v26[7]; // [rsp+50h] [rbp-31h] BYREF
  __int64 v27; // [rsp+D0h] [rbp+4Fh]
  int v29; // [rsp+E0h] [rbp+5Fh]
  __int64 v31; // [rsp+F0h] [rbp+6Fh]

  v27 = *a1;
  v8 = *(_QWORD *)(a5 + 24);
  v9 = a4;
  memset(v26, 0, 37);
  v10 = 0;
  v31 = sqlite3SrcListDup(v27, a5, 0);
  v11 = v31;
  v29 = sqlite3ExprDup(v27, a6, 0);
  if ( v31 )
  {
    v12 = *(_QWORD *)(v31 + 24);
    *(_DWORD *)(v31 + 40) = -1;
    --*(_DWORD *)(v12 + 44);
    *(_QWORD *)(v31 + 24) = 0;
  }
  if ( a3 )
  {
    v13 = 0;
    if ( *(_WORD *)(a3 + 94) )
    {
      do
      {
        v14 = exprRowColumn(a1, (unsigned int)*(__int16 *)(*(_QWORD *)(a3 + 8) + 2LL * v13));
        v10 = sqlite3ExprListAppend(a1, v10, v14);
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
    v20 = sqlite3PExpr(a1, 76, 0);
    v10 = sqlite3ExprListAppend(a1, 0, v20);
    v15 = v16 == 1;
    v9 = a4;
LABEL_12:
    v19 = !v15 + 14;
    goto LABEL_13;
  }
  for ( i = 0; (int)i < *(__int16 *)(v8 + 54); ++i )
  {
    v18 = exprRowColumn(a1, i);
    v10 = sqlite3ExprListAppend(a1, v10, v18);
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
        v10 = sqlite3ExprListAppend(a1, v10, v22);
      }
      while ( v21 < *v9 );
      v11 = v31;
    }
  }
  v23 = sqlite3SelectNew((_DWORD)a1, v10, v11, v29, 0, 0, 0, 276955136, 0);
  v24 = v23;
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
  sqlite3Select(a1, v23, v26);
  return sqlite3SelectDelete(v27, v24);
}

```

## disassembly

```asm
0x180092f78  mov     [rsp-8+arg_18], r9
0x180092f7d  mov     [rsp-8+arg_8], edx
0x180092f81  push    rbp
0x180092f82  push    rbx
0x180092f83  push    rsi
0x180092f84  push    rdi
0x180092f85  push    r12
0x180092f87  push    r13
0x180092f89  push    r14
0x180092f8b  push    r15
0x180092f8d  lea     rbp, [rsp-7]
0x180092f92  sub     rsp, 88h
0x180092f99  mov     rbx, [rcx]
0x180092f9c  xorps   xmm0, xmm0
0x180092f9f  mov     rdx, [rbp+3Fh+arg_20]
0x180092fa3  mov     r14, r8
0x180092fa6  mov     rsi, rcx
0x180092fa9  mov     [rbp+3Fh+arg_0], rbx
0x180092fad  xor     eax, eax
0x180092faf  xor     r8d, r8d
0x180092fb2  movups  [rbp+3Fh+var_60], xmm0
0x180092fb6  mov     rdi, [rdx+18h]
0x180092fba  mov     rcx, rbx
0x180092fbd  mov     r15, r9
0x180092fc0  mov     qword ptr [rbp+3Fh+var_60+0Dh], rax
0x180092fc4  movups  [rbp+3Fh+var_70], xmm0
0x180092fc8  xor     r12d, r12d
0x180092fcb  call    sqlite3SrcListDup
0x180092fd0  mov     rdx, [rbp+3Fh+arg_28]
0x180092fd4  xor     r8d, r8d
0x180092fd7  mov     rcx, rbx
0x180092fda  mov     [rbp+3Fh+arg_20], rax
0x180092fde  mov     r13, rax
0x180092fe1  call    sqlite3ExprDup
0x180092fe6  mov     [rbp+3Fh+arg_10], rax
0x180092fea  test    r13, r13
0x180092fed  jz      short loc_180093002
0x180092fef  mov     rcx, [r13+18h]
0x180092ff3  mov     dword ptr [r13+28h], 0FFFFFFFFh
0x180092ffb  dec     dword ptr [rcx+2Ch]
0x180092ffe  mov     [r13+18h], r12
0x180093002  test    r14, r14
0x180093005  jz      short loc_180093049
0x180093007  xor     ebx, ebx
0x180093009  xor     eax, eax
0x18009300b  cmp     ax, [r14+5Eh]
0x180093010  jnb     short loc_180093041
0x180093012  mov     rax, [r14+8]
0x180093016  movsxd  rcx, ebx
0x180093019  movsx   edx, word ptr [rax+rcx*2]
0x18009301d  mov     rcx, rsi
0x180093020  call    exprRowColumn
0x180093025  mov     r8, rax
0x180093028  mov     rdx, r12
0x18009302b  mov     rcx, rsi
0x18009302e  call    sqlite3ExprListAppend
0x180093033  mov     r12, rax
0x180093036  inc     ebx
0x180093038  movzx   eax, word ptr [r14+5Eh]
0x18009303d  cmp     ebx, eax
0x18009303f  jl      short loc_180093012
0x180093041  xor     ebx, ebx
0x180093043  cmp     byte ptr [rdi+3Fh], 1
0x180093047  jmp     short loc_1800930B9
0x180093049  mov     r15b, [rdi+3Fh]
0x18009304d  cmp     r15b, 2
0x180093051  jnz     short loc_18009308D
0x180093053  xor     ebx, ebx
0x180093055  xor     eax, eax
0x180093057  cmp     ax, [rdi+36h]
0x18009305b  jge     short loc_180093082
0x18009305d  mov     edx, ebx
0x18009305f  mov     rcx, rsi
0x180093062  call    exprRowColumn
0x180093067  mov     r8, rax
0x18009306a  mov     rdx, r12
0x18009306d  mov     rcx, rsi
0x180093070  call    sqlite3ExprListAppend
0x180093075  mov     r12, rax
0x180093078  inc     ebx
0x18009307a  movsx   eax, word ptr [rdi+36h]
0x18009307e  cmp     ebx, eax
0x180093080  jl      short loc_18009305D
0x180093082  mov     r15, [rbp+3Fh+arg_18]
0x180093086  mov     ebx, 0Eh
0x18009308b  jmp     short loc_1800930BF
0x18009308d  xor     r9d, r9d
0x180093090  xor     r8d, r8d
0x180093093  mov     rcx, rsi
0x180093096  lea     edx, [r9+4Ch]
0x18009309a  call    sqlite3PExpr
0x18009309f  mov     r8, rax
0x1800930a2  xor     edx, edx
0x1800930a4  mov     rcx, rsi
0x1800930a7  call    sqlite3ExprListAppend
0x1800930ac  xor     ebx, ebx
0x1800930ae  mov     r12, rax
0x1800930b1  cmp     r15b, 1
0x1800930b5  mov     r15, [rbp+3Fh+arg_18]
0x1800930b9  setnz   bl
0x1800930bc  add     ebx, 0Eh
0x1800930bf  test    r15, r15
0x1800930c2  jz      short loc_180093102
0x1800930c4  xor     edi, edi
0x1800930c6  cmp     [r15], edi
0x1800930c9  jle     short loc_180093102
0x1800930cb  mov     r13, [rbp+3Fh+arg_0]
0x1800930cf  movsxd  rdx, edi
0x1800930d2  xor     r8d, r8d
0x1800930d5  shl     rdx, 5
0x1800930d9  mov     rcx, r13
0x1800930dc  mov     rdx, [rdx+r15+8]
0x1800930e1  call    sqlite3ExprDup
0x1800930e6  mov     r8, rax
0x1800930e9  mov     rdx, r12
0x1800930ec  mov     rcx, rsi
0x1800930ef  call    sqlite3ExprListAppend
0x1800930f4  inc     edi
0x1800930f6  mov     r12, rax
0x1800930f9  cmp     edi, [r15]
0x1800930fc  jl      short loc_1800930CF
0x1800930fe  mov     r13, [rbp+3Fh+arg_20]
0x180093102  mov     r9, [rbp+3Fh+arg_10]
0x180093106  mov     r8, r13
0x180093109  mov     [rsp+0C0h+var_80], 0
0x180093112  mov     rdx, r12
0x180093115  mov     [rsp+0C0h+var_88], 10820000h
0x18009311d  mov     rcx, rsi
0x180093120  mov     [rsp+0C0h+var_90], 0
0x180093129  mov     [rsp+0C0h+var_98], 0
0x180093132  mov     [rsp+0C0h+var_A0], 0
0x18009313b  call    sqlite3SelectNew
0x180093140  mov     rdi, rax
0x180093143  test    rax, rax
0x180093146  jz      short loc_18009314D
0x180093148  bts     dword ptr [rax+4], 1Bh
0x18009314d  mov     eax, [rbp+3Fh+arg_8]
0x180093150  mov     dword ptr [rbp+3Fh+var_70+4], eax
0x180093153  mov     byte ptr [rbp+3Fh+var_70], bl
0x180093156  mov     qword ptr [rbp+3Fh+var_60+8], 0
0x18009315e  mov     qword ptr [rbp+3Fh+var_70+0Ch], 0
0x180093166  test    r14, r14
0x180093169  jz      short loc_180093175
0x18009316b  movzx   eax, word ptr [r14+5Eh]
0x180093170  mov     dword ptr [rbp+3Fh+var_70+8], eax
0x180093173  jmp     short loc_18009317C
0x180093175  mov     dword ptr [rbp+3Fh+var_70+8], 0FFFFFFFFh
0x18009317c  lea     r8, [rbp+3Fh+var_70]
0x180093180  mov     rdx, rdi
0x180093183  mov     rcx, rsi
0x180093186  call    sqlite3Select
0x18009318b  mov     rcx, [rbp+3Fh+arg_0]
0x18009318f  mov     rdx, rdi
0x180093192  call    sqlite3SelectDelete
0x180093197  add     rsp, 88h
0x18009319e  pop     r15
0x1800931a0  pop     r14
0x1800931a2  pop     r13
0x1800931a4  pop     r12
0x1800931a6  pop     rdi
0x1800931a7  pop     rsi
0x1800931a8  pop     rbx
0x1800931a9  pop     rbp
0x1800931aa  retn
```
