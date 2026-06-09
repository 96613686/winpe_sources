# utl::_TreeNodeHeader<void *>::_HeadUnlinkNode(utl::_TreeNode<void *> *)

- ea: `0x1800171f4`
- end: `0x1800174b5`
- name: `?_HeadUnlinkNode@?$_TreeNodeHeader@PEAX@utl@@QEAAXPEAU?$_TreeNode@PEAX@2@@Z`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800157bc`

## callees

- `0x1800171f4`
- `0x1800175ac`
- `0x180017620`
- `0x18001764c`

## pseudocode

```c
__int64 __fastcall utl::_TreeNodeHeader<void *>::_HeadUnlinkNode(_QWORD *a1, __int64 *a2)
{
  __int64 v2; // r9
  __int64 v3; // r8
  _QWORD *v5; // r11
  unsigned __int64 v6; // r14
  __int64 result; // rax
  int v8; // ecx
  _QWORD *v9; // rax
  char v10; // r10
  unsigned __int64 v11; // rsi
  bool v12; // bp
  unsigned __int64 **v13; // r9
  unsigned __int64 *v14; // rdx
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  char v17; // r10
  _QWORD *v18; // rsi
  _QWORD *v19; // r11
  __int64 v20; // rax
  bool v21; // zf
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // r9
  unsigned __int64 *v24; // r11
  _QWORD *v25; // r10
  __int64 v26; // rax
  _QWORD *v27; // rax

  v2 = *a2;
  v3 = a2[2];
  v5 = a2;
  v6 = *a2 & 0xFFFFFFFFFFFFFFFEuLL;
  LOBYTE(a2) = v3 != (_QWORD)&utl::_TreeSentinel;
  result = v3 != (_QWORD)&utl::_TreeSentinel;
  v8 = result + (v5[1] != (_QWORD)&utl::_TreeSentinel);
  if ( v8 )
  {
    if ( v8 == 1 )
    {
      v18 = (_QWORD *)v5[(unsigned __int8)a2 + 1];
      if ( (_QWORD *)a1[(unsigned __int8)a2 + 1] == v5 )
        a1[(unsigned __int8)a2 + 1] = utl::_TreeNodeHeader<void *>::_Traverse(v5, a2);
      result = utl::_TreeNodeHeader<void *>::_ReplaceChild(v6, v5, v18);
      *v18 = *v19;
    }
    else if ( *(_UNKNOWN **)(v3 + 8) == &utl::_TreeSentinel )
    {
      *(_QWORD *)v3 = v2;
      v9 = (_QWORD *)v5[1];
      *(_QWORD *)(v3 + 8) = v9;
      *v9 &= 1uLL;
      *v9 |= v3;
      **(_QWORD **)(v3 + 16) = v3 | 1;
      result = utl::_TreeNodeHeader<void *>::_ReplaceChild(v6, v5, v3);
      if ( v10 )
      {
        v11 = v3;
        v12 = 1;
        goto LABEL_20;
      }
    }
    else
    {
      do
      {
        v13 = (unsigned __int64 **)(v3 + 8);
        v11 = v3;
        v3 = *(_QWORD *)(v3 + 8);
      }
      while ( *(_UNKNOWN **)(v3 + 8) != &utl::_TreeSentinel );
      v14 = *(unsigned __int64 **)(v3 + 16);
      *v13 = v14;
      *v14 = v11 | 1;
      *(_QWORD *)v3 = *v5;
      v15 = (_QWORD *)v5[1];
      *(_QWORD *)(v3 + 8) = v15;
      *v15 &= 1uLL;
      *v15 |= v3;
      v16 = (_QWORD *)v5[2];
      *(_QWORD *)(v3 + 16) = v16;
      *v16 &= 1uLL;
      *v16 |= v3;
      result = utl::_TreeNodeHeader<void *>::_ReplaceChild(v6, v5, v3);
      if ( v17 )
      {
        v12 = 0;
        goto LABEL_20;
      }
    }
  }
  else if ( a1 == (_QWORD *)v6 )
  {
    *a1 = a1;
    a1[1] = a1;
    a1[2] = a1;
  }
  else
  {
    if ( (_QWORD *)a1[1] == v5 )
    {
      a1[1] = utl::_TreeNodeHeader<void *>::_Traverse(v5, 0);
    }
    else if ( (_QWORD *)a1[2] == v5 )
    {
      LOBYTE(a2) = 1;
      a1[2] = utl::_TreeNodeHeader<void *>::_Traverse(v5, a2);
    }
    v12 = *(_QWORD *)(v6 + 16) == (_QWORD)v5;
    result = v12;
    *(_QWORD *)(v6 + 8LL * v12 + 8) = &utl::_TreeSentinel;
    if ( (*(_BYTE *)v5 & 1) != 0 )
    {
      v11 = v6;
      while ( 1 )
      {
LABEL_20:
        if ( (**(_BYTE **)(v11 + 8 * !v12 + 8) & 1) == 0 )
        {
          LOBYTE(v2) = 1;
          LOBYTE(a2) = v12;
          utl::_TreeNodeHeader<void *>::_NodeRotate(v11, a2, 0, v2);
        }
        a2 = *(__int64 **)(v11 + 8 * !v12 + 8);
        if ( (*(_BYTE *)a2[!v12 + 1] & 1) == 0 )
        {
          v27 = (_QWORD *)a2[!v12 + 1];
          *v27 |= 1uLL;
          goto LABEL_32;
        }
        if ( (*(_BYTE *)a2[v12 + 1] & 1) == 0 )
          break;
        *a2 &= ~1uLL;
        v20 = *(_QWORD *)v11;
        if ( (*(_QWORD *)v11 & 1) == 0 )
        {
          result = v20 | 1;
          *(_QWORD *)v11 = result;
          return result;
        }
        result = v20 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( a1 == (_QWORD *)result )
          return result;
        v21 = *(_QWORD *)(result + 16) == v11;
        v11 = result;
        v12 = v21;
      }
      v22 = *a2 & 0xFFFFFFFFFFFFFFFEuLL;
      v23 = a2[v12 + 1];
      v24 = (unsigned __int64 *)(v23 + 8LL * !v12);
      v25 = (_QWORD *)v24[1];
      *(_QWORD *)v23 = v22 | 1;
      v26 = 8;
      v3 = 16;
      if ( *(__int64 **)(v22 + 16) == a2 )
        v26 = 16;
      *(_QWORD *)(v26 + v22) = v23;
      v2 = v23 | 1;
      *a2 = v2;
      *v25 &= 1uLL;
      *v25 |= (unsigned __int64)a2;
      a2[v12 + 1] = (__int64)v25;
      v24[1] = (unsigned __int64)a2;
LABEL_32:
      LOBYTE(v3) = 1;
      LOBYTE(v2) = *(_BYTE *)v11 & 1;
      LOBYTE(a2) = v12;
      return utl::_TreeNodeHeader<void *>::_NodeRotate(v11, a2, v3, v2);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800171f4  push    rbx
0x1800171f6  push    rbp
0x1800171f7  push    rsi
0x1800171f8  push    rdi
0x1800171f9  push    r14
0x1800171fb  push    r15
0x1800171fd  sub     rsp, 28h
0x180017201  mov     r9, [rdx]
0x180017204  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18001720b  mov     r8, [rdx+10h]
0x18001720f  mov     rbx, rcx
0x180017212  mov     r11, rdx
0x180017215  mov     r14, r9
0x180017218  and     r14, 0FFFFFFFFFFFFFFFEh
0x18001721c  cmp     r8, r15
0x18001721f  setnz   dl
0x180017222  xor     ecx, ecx
0x180017224  cmp     [r11+8], r15
0x180017228  movzx   eax, dl
0x18001722b  setnz   cl
0x18001722e  add     ecx, eax
0x180017230  jz      loc_18001734E
0x180017236  cmp     ecx, 1
0x180017239  jz      loc_180017319
0x18001723f  cmp     [r8+8], r15
0x180017243  jnz     short loc_18001729F
0x180017245  mov     edi, 1
0x18001724a  lea     rdx, [r8+10h]
0x18001724e  test    [r8], dil
0x180017251  jz      short loc_180017260
0x180017253  mov     rax, [rdx]
0x180017256  test    [rax], dil
0x180017259  jz      short loc_180017260
0x18001725b  mov     r10b, dil
0x18001725e  jmp     short loc_180017263
0x180017260  xor     r10b, r10b
0x180017263  mov     [r8], r9
0x180017266  mov     rcx, r8
0x180017269  mov     rax, [r11+8]
0x18001726d  or      rcx, rdi
0x180017270  mov     [r8+8], rax
0x180017274  and     [rax], rdi
0x180017277  or      [rax], r8
0x18001727a  mov     rax, [rdx]
0x18001727d  mov     rdx, r11
0x180017280  mov     [rax], rcx
0x180017283  mov     rcx, r14
0x180017286  call    ?_ReplaceChild@?$_TreeNodeHeader@PEAX@utl@@AEAAXPEBU?$_TreeNode@PEAX@2@PEAU32@@Z; utl::_TreeNodeHeader<void *>::_ReplaceChild(utl::_TreeNode<void *> const *,utl::_TreeNode<void *> *)
0x18001728b  test    r10b, r10b
0x18001728e  jz      loc_1800174A8
0x180017294  mov     rsi, r8
0x180017297  mov     bpl, dil
0x18001729a  jmp     loc_1800173B0
0x18001729f  lea     r9, [r8+8]
0x1800172a3  mov     rsi, r8
0x1800172a6  mov     r8, [r9]
0x1800172a9  cmp     [r8+8], r15
0x1800172ad  jnz     short loc_18001729F
0x1800172af  mov     edi, 1
0x1800172b4  lea     rcx, [r8+10h]
0x1800172b8  test    [r8], dil
0x1800172bb  jz      short loc_1800172CA
0x1800172bd  mov     rax, [rcx]
0x1800172c0  test    [rax], dil
0x1800172c3  jz      short loc_1800172CA
0x1800172c5  mov     r10b, dil
0x1800172c8  jmp     short loc_1800172CD
0x1800172ca  xor     r10b, r10b
0x1800172cd  mov     rdx, [rcx]
0x1800172d0  mov     rax, rsi
0x1800172d3  mov     [r9], rdx
0x1800172d6  or      rax, rdi
0x1800172d9  mov     [rdx], rax
0x1800172dc  mov     rdx, r11
0x1800172df  mov     rax, [r11]
0x1800172e2  mov     [r8], rax
0x1800172e5  mov     rax, [r11+8]
0x1800172e9  mov     [r8+8], rax
0x1800172ed  and     [rax], rdi
0x1800172f0  or      [rax], r8
0x1800172f3  mov     rax, [r11+10h]
0x1800172f7  mov     [rcx], rax
0x1800172fa  mov     rcx, r14
0x1800172fd  and     [rax], rdi
0x180017300  or      [rax], r8
0x180017303  call    ?_ReplaceChild@?$_TreeNodeHeader@PEAX@utl@@AEAAXPEBU?$_TreeNode@PEAX@2@PEAU32@@Z; utl::_TreeNodeHeader<void *>::_ReplaceChild(utl::_TreeNode<void *> const *,utl::_TreeNode<void *> *)
0x180017308  test    r10b, r10b
0x18001730b  jz      loc_1800174A8
0x180017311  xor     bpl, bpl
0x180017314  jmp     loc_1800173B0
0x180017319  movzx   edi, dl
0x18001731c  mov     rsi, [r11+rdi*8+8]
0x180017321  cmp     [rbx+rdi*8+8], r11
0x180017326  jnz     short loc_180017335
0x180017328  mov     rcx, r11
0x18001732b  call    ?_Traverse@?$_TreeNodeHeader@PEAX@utl@@QEAAPEAU?$_TreeNode@PEAX@2@_N@Z; utl::_TreeNodeHeader<void *>::_Traverse(bool)
0x180017330  mov     [rbx+rdi*8+8], rax
0x180017335  mov     r8, rsi
0x180017338  mov     rdx, r11
0x18001733b  mov     rcx, r14
0x18001733e  call    ?_ReplaceChild@?$_TreeNodeHeader@PEAX@utl@@AEAAXPEBU?$_TreeNode@PEAX@2@PEAU32@@Z; utl::_TreeNodeHeader<void *>::_ReplaceChild(utl::_TreeNode<void *> const *,utl::_TreeNode<void *> *)
0x180017343  mov     rcx, [r11]
0x180017346  mov     [rsi], rcx
0x180017349  jmp     loc_1800174A8
0x18001734e  cmp     rbx, r14
0x180017351  jnz     short loc_180017363
0x180017353  mov     [rbx], rbx
0x180017356  mov     [rbx+8], rbx
0x18001735a  mov     [rbx+10h], rbx
0x18001735e  jmp     loc_1800174A8
0x180017363  mov     edi, 1
0x180017368  cmp     [rbx+8], r11
0x18001736c  jnz     short loc_18001737E
0x18001736e  xor     edx, edx
0x180017370  mov     rcx, r11
0x180017373  call    ?_Traverse@?$_TreeNodeHeader@PEAX@utl@@QEAAPEAU?$_TreeNode@PEAX@2@_N@Z; utl::_TreeNodeHeader<void *>::_Traverse(bool)
0x180017378  mov     [rbx+8], rax
0x18001737c  jmp     short loc_180017393
0x18001737e  cmp     [rbx+10h], r11
0x180017382  jnz     short loc_180017393
0x180017384  mov     dl, dil
0x180017387  mov     rcx, r11
0x18001738a  call    ?_Traverse@?$_TreeNodeHeader@PEAX@utl@@QEAAPEAU?$_TreeNode@PEAX@2@_N@Z; utl::_TreeNodeHeader<void *>::_Traverse(bool)
0x18001738f  mov     [rbx+10h], rax
0x180017393  cmp     [r14+10h], r11
0x180017397  setz    bpl
0x18001739b  movzx   eax, bpl
0x18001739f  mov     [r14+rax*8+8], r15
0x1800173a4  test    [r11], dil
0x1800173a7  jz      loc_1800174A8
0x1800173ad  mov     rsi, r14
0x1800173b0  movzx   eax, bpl
0x1800173b4  xor     rax, rdi
0x1800173b7  mov     rax, [rsi+rax*8+8]
0x1800173bc  test    [rax], dil
0x1800173bf  jnz     short loc_1800173D2
0x1800173c1  mov     r9b, dil
0x1800173c4  xor     r8d, r8d
0x1800173c7  mov     dl, bpl
0x1800173ca  mov     rcx, rsi
0x1800173cd  call    ?_NodeRotate@?$_TreeNodeHeader@PEAX@utl@@AEAAPEAU?$_TreeNode@PEAX@2@_N00@Z; utl::_TreeNodeHeader<void *>::_NodeRotate(bool,bool,bool)
0x1800173d2  movzx   eax, bpl
0x1800173d6  xor     rax, rdi
0x1800173d9  mov     rdx, [rsi+rax*8+8]
0x1800173de  movzx   eax, bpl
0x1800173e2  xor     rax, rdi
0x1800173e5  mov     rax, [rdx+rax*8+8]
0x1800173ea  test    [rax], dil
0x1800173ed  movzx   eax, bpl
0x1800173f1  jz      loc_180017489
0x1800173f7  mov     rcx, [rdx+rax*8+8]
0x1800173fc  test    [rcx], dil
0x1800173ff  jz      short loc_18001742F
0x180017401  and     qword ptr [rdx], 0FFFFFFFFFFFFFFFEh
0x180017405  mov     rax, [rsi]
0x180017408  test    dil, al
0x18001740b  jz      short loc_180017427
0x18001740d  and     rax, 0FFFFFFFFFFFFFFFEh
0x180017411  cmp     rbx, rax
0x180017414  jz      loc_1800174A8
0x18001741a  cmp     [rax+10h], rsi
0x18001741e  mov     rsi, rax
0x180017421  setz    bpl
0x180017425  jmp     short loc_1800173B0
0x180017427  or      rax, rdi
0x18001742a  mov     [rsi], rax
0x18001742d  jmp     short loc_1800174A8
0x18001742f  mov     rcx, [rdx]
0x180017432  mov     al, bpl
0x180017435  xor     al, dil
0x180017438  and     rcx, 0FFFFFFFFFFFFFFFEh
0x18001743c  movzx   ebx, al
0x18001743f  mov     eax, ebx
0x180017441  xor     rax, rdi
0x180017444  mov     r9, [rdx+rax*8+8]
0x180017449  mov     rax, rcx
0x18001744c  or      rax, rdi
0x18001744f  lea     r11, [r9+rbx*8]
0x180017453  mov     r10, [r11+8]
0x180017457  mov     [r9], rax
0x18001745a  mov     eax, 8
0x18001745f  cmp     [rcx+10h], rdx
0x180017463  lea     r8d, [rax+8]
0x180017467  cmovz   eax, r8d
0x18001746b  mov     [rax+rcx], r9
0x18001746f  or      r9, rdi
0x180017472  mov     [rdx], r9
0x180017475  and     [r10], rdi
0x180017478  or      [r10], rdx
0x18001747b  xor     rbx, rdi
0x18001747e  mov     [rdx+rbx*8+8], r10
0x180017483  mov     [r11+8], rdx
0x180017487  jmp     short loc_180017494
0x180017489  xor     rax, rdi
0x18001748c  mov     rax, [rdx+rax*8+8]
0x180017491  or      [rax], rdi
0x180017494  mov     r9b, [rsi]
0x180017497  mov     r8b, dil
0x18001749a  and     r9b, dil
0x18001749d  mov     dl, bpl
0x1800174a0  mov     rcx, rsi
0x1800174a3  call    ?_NodeRotate@?$_TreeNodeHeader@PEAX@utl@@AEAAPEAU?$_TreeNode@PEAX@2@_N00@Z; utl::_TreeNodeHeader<void *>::_NodeRotate(bool,bool,bool)
0x1800174a8  add     rsp, 28h
0x1800174ac  pop     r15
0x1800174ae  pop     r14
0x1800174b0  pop     rdi
0x1800174b1  pop     rsi
0x1800174b2  pop     rbp
0x1800174b3  pop     rbx
0x1800174b4  retn
```
