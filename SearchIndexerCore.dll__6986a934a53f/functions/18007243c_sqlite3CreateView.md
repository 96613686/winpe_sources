# sqlite3CreateView

- ea: `0x18007243c`
- end: `0x180072653`
- name: `sqlite3CreateView`
- size: `535`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x18000213c`

## callees

- `0x180011bcc`
- `0x180018fd0`
- `0x18001b818`
- `0x18001bc40`
- `0x18001ebb8`
- `0x18001f418`
- `0x180054824`
- `0x18005d2d4`
- `0x180060434`
- `0x180061d60`
- `0x1800635fc`
- `0x18007243c`
- `0x180078968`
- `0x180097d24`

## pseudocode

```c
__int64 __fastcall sqlite3CreateView(
        __int64 a1,
        _DWORD *a2,
        _OWORD *a3,
        __int64 a4,
        _DWORD *a5,
        __int64 a6,
        int a7,
        int a8)
{
  __int64 v12; // rsi
  __int64 v13; // rdi
  __int64 v15; // r14
  int v16; // eax
  __int64 v17; // rax
  _DWORD *v18; // rdx
  int v19; // edx
  int v20; // edx
  __int64 v21; // r8
  __int64 i; // rcx
  __int64 v23; // rax
  __int128 v24; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v25[8]; // [rsp+50h] [rbp-49h] BYREF
  _BYTE v26[88]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v27; // [rsp+E0h] [rbp+47h] BYREF

  v24 = 0;
  memset_0(v25, 0, 0x60u);
  v12 = *(_QWORD *)a1;
  v27 = 0;
  if ( *(__int16 *)(a1 + 304) > 0 )
  {
    sqlite3ErrorMsg(a1, "parameters are not allowed in views");
LABEL_3:
    v13 = a6;
    goto LABEL_4;
  }
  sqlite3StartTable((__int64 *)a1, a3, a4, a7, 1, 0, a8);
  v15 = *(_QWORD *)(a1 + 352);
  if ( !v15 || *(_DWORD *)(a1 + 48) )
    goto LABEL_3;
  *(_DWORD *)(v15 + 48) |= 0x200u;
  sqlite3TwoPartName(a1, a3, a4, &v27);
  v16 = sqlite3SchemaToIndex(v12, *(_QWORD *)(v15 + 96));
  sqlite3FixInit((unsigned int)v25, a1, v16, (unsigned int)"view", v27);
  v13 = a6;
  if ( !(unsigned int)sqlite3WalkSelect(v26, a6) )
  {
    *(_DWORD *)(v13 + 4) |= 0x200000u;
    if ( *(_BYTE *)(a1 + 308) < 2u )
    {
      v17 = sqlite3SelectDup(v12, v13, 1);
    }
    else
    {
      v17 = v13;
      v13 = 0;
    }
    v18 = a5;
    *(_QWORD *)(v15 + 64) = v17;
    *(_QWORD *)(v15 + 32) = sqlite3ExprListDup(v12, v18, 1);
    *(_BYTE *)(v15 + 63) = 2;
    if ( !*(_BYTE *)(v12 + 103) )
    {
      v24 = *(_OWORD *)(a1 + 288);
      v19 = v24;
      if ( *(_BYTE *)v24 != 59 )
      {
        v19 = DWORD2(v24) + v24;
        *(_QWORD *)&v24 = DWORD2(v24) + (_QWORD)v24;
      }
      v20 = v19 - *a2;
      v21 = *(_QWORD *)a2;
      DWORD2(v24) = 0;
      for ( i = *(unsigned __int8 *)(v20 + v21 - 1);
            (*((_BYTE *)&qword_1800B4FF0 + i) & 1) != 0;
            i = *(unsigned __int8 *)(v23 + v21 - 2) )
      {
        v23 = v20--;
      }
      DWORD2(v24) = 1;
      *(_QWORD *)&v24 = v21 + v20 - 1;
      sqlite3EndTable((_QWORD *)a1, 0, &v24, 0, 0);
    }
  }
LABEL_4:
  sqlite3SelectDelete((_QWORD *)v12, (__int64 *)v13);
  if ( *(_BYTE *)(a1 + 308) >= 2u )
    sqlite3RenameExprlistUnmap(a1, a5);
  return sqlite3ExprListDeleteGeneric((_QWORD *)v12, a5);
}

```

## disassembly

```asm
0x18007243c  mov     [rsp-8+arg_8], rbx
0x180072441  mov     [rsp-8+arg_10], rsi
0x180072446  push    rbp
0x180072447  push    rdi
0x180072448  push    r12
0x18007244a  push    r13
0x18007244c  push    r14
0x18007244e  lea     rbp, [rsp-17h]
0x180072453  sub     rsp, 0B0h
0x18007245a  mov     r13, rdx
0x18007245d  mov     r12, r8
0x180072460  xor     edx, edx; Val
0x180072462  mov     rbx, rcx
0x180072465  xorps   xmm0, xmm0
0x180072468  lea     rcx, [rbp+37h+var_80]; void *
0x18007246c  mov     rdi, r9
0x18007246f  movups  [rbp+37h+var_90], xmm0
0x180072473  lea     r8d, [rdx+60h]; Size
0x180072477  call    memset_0
0x18007247c  mov     rsi, [rbx]
0x18007247f  xor     ecx, ecx
0x180072481  mov     [rbp+37h+arg_0], rcx
0x180072485  cmp     [rbx+130h], cx
0x18007248c  jle     short loc_1800724E9
0x18007248e  lea     rdx, aParametersAreN; "parameters are not allowed in views"
0x180072495  mov     rcx, rbx
0x180072498  call    sqlite3ErrorMsg
0x18007249d  mov     rdi, [rbp+37h+arg_28]
0x1800724a1  mov     rdx, rdi
0x1800724a4  mov     rcx, rsi
0x1800724a7  call    sqlite3SelectDelete
0x1800724ac  cmp     byte ptr [rbx+134h], 2
0x1800724b3  jb      short loc_1800724C1
0x1800724b5  mov     rdx, [rbp+37h+arg_20]
0x1800724b9  mov     rcx, rbx
0x1800724bc  call    sqlite3RenameExprlistUnmap
0x1800724c1  mov     rdx, [rbp+37h+arg_20]
0x1800724c5  mov     rcx, rsi
0x1800724c8  call    sqlite3ExprListDeleteGeneric
0x1800724cd  lea     r11, [rsp+0D0h+var_20]
0x1800724d5  mov     rbx, [r11+38h]
0x1800724d9  mov     rsi, [r11+40h]
0x1800724dd  mov     rsp, r11
0x1800724e0  pop     r14
0x1800724e2  pop     r13
0x1800724e4  pop     r12
0x1800724e6  pop     rdi
0x1800724e7  pop     rbp
0x1800724e8  retn
0x1800724e9  mov     eax, [rbp+37h+arg_38]
0x1800724ec  mov     r8, rdi
0x1800724ef  mov     r9d, [rbp+37h+arg_30]
0x1800724f3  mov     rdx, r12
0x1800724f6  mov     [rsp+0D0h+var_A0], eax
0x1800724fa  mov     [rsp+0D0h+var_A8], ecx
0x1800724fe  mov     rcx, rbx
0x180072501  mov     dword ptr [rsp+0D0h+var_B0], 1
0x180072509  call    sqlite3StartTable
0x18007250e  mov     r14, [rbx+160h]
0x180072515  test    r14, r14
0x180072518  jz      short loc_18007249D
0x18007251a  cmp     dword ptr [rbx+30h], 0
0x18007251e  jnz     loc_18007249D
0x180072524  bts     dword ptr [r14+30h], 9
0x18007252a  lea     r9, [rbp+37h+arg_0]
0x18007252e  mov     r8, rdi
0x180072531  mov     rdx, r12
0x180072534  mov     rcx, rbx
0x180072537  call    sqlite3TwoPartName
0x18007253c  mov     rdx, [r14+60h]
0x180072540  mov     rcx, rsi
0x180072543  call    sqlite3SchemaToIndex
0x180072548  mov     rcx, [rbp+37h+arg_0]
0x18007254c  lea     r9, aView_0; "view"
0x180072553  mov     [rsp+0D0h+var_B0], rcx
0x180072558  mov     r8d, eax
0x18007255b  lea     rcx, [rbp+37h+var_80]
0x18007255f  mov     rdx, rbx
0x180072562  call    sqlite3FixInit
0x180072567  mov     rdi, [rbp+37h+arg_28]
0x18007256b  lea     rcx, [rbp+37h+var_78]
0x18007256f  mov     rdx, rdi
0x180072572  call    sqlite3WalkSelect
0x180072577  xor     r12d, r12d
0x18007257a  test    eax, eax
0x18007257c  jnz     loc_1800724A1
0x180072582  bts     dword ptr [rdi+4], 15h
0x180072587  cmp     byte ptr [rbx+134h], 2
0x18007258e  jb      short loc_180072598
0x180072590  mov     rax, rdi
0x180072593  mov     edi, r12d
0x180072596  jmp     short loc_1800725A9
0x180072598  mov     r8d, 1
0x18007259e  mov     rdx, rdi
0x1800725a1  mov     rcx, rsi
0x1800725a4  call    sqlite3SelectDup
0x1800725a9  mov     rdx, [rbp+37h+arg_20]
0x1800725ad  mov     r8d, 1
0x1800725b3  mov     rcx, rsi
0x1800725b6  mov     [r14+40h], rax
0x1800725ba  call    sqlite3ExprListDup
0x1800725bf  mov     [r14+20h], rax
0x1800725c3  mov     byte ptr [r14+3Fh], 2
0x1800725c8  cmp     [rsi+67h], r12b
0x1800725cc  jnz     loc_1800724A1
0x1800725d2  movups  xmm0, xmmword ptr [rbx+120h]
0x1800725d9  movq    rdx, xmm0
0x1800725de  movups  [rbp+37h+var_90], xmm0
0x1800725e2  cmp     byte ptr [rdx], 3Bh ; ';'
0x1800725e5  jz      short loc_1800725F1
0x1800725e7  mov     eax, dword ptr [rbp+37h+var_90+8]
0x1800725ea  add     rdx, rax
0x1800725ed  mov     qword ptr [rbp+37h+var_90], rdx
0x1800725f1  sub     edx, [r13+0]
0x1800725f5  lea     r10, qword_1800B4FF0
0x1800725fc  mov     r8, [r13+0]
0x180072600  mov     r9d, 1
0x180072606  movsxd  rax, edx
0x180072609  mov     dword ptr [rbp+37h+var_90+8], r12d
0x18007260d  movzx   ecx, byte ptr [rax+r8-1]
0x180072613  jmp     short loc_180072621
0x180072615  movsxd  rax, edx
0x180072618  sub     edx, r9d
0x18007261b  movzx   ecx, byte ptr [rax+r8-2]
0x180072621  test    [rcx+r10], r9b
0x180072625  jnz     short loc_180072615
0x180072627  lea     eax, [rdx-1]
0x18007262a  mov     dword ptr [rbp+37h+var_90+8], r9d
0x18007262e  movsxd  rcx, eax
0x180072631  xor     r9d, r9d
0x180072634  add     rcx, r8
0x180072637  mov     [rsp+0D0h+var_B0], r12
0x18007263c  mov     qword ptr [rbp+37h+var_90], rcx
0x180072640  lea     r8, [rbp+37h+var_90]
0x180072644  mov     rcx, rbx
0x180072647  xor     edx, edx
0x180072649  call    sqlite3EndTable
0x18007264e  jmp     loc_1800724A1
```
