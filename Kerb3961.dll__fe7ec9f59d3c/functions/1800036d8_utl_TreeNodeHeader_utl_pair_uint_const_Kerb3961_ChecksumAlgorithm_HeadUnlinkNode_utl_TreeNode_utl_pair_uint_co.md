# utl::_TreeNodeHeader<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(utl::_TreeNode<utl::pair<uint const,Kerb3961::ChecksumAlgorithm *>> *)

- ea: `0x1800036d8`
- end: `0x180003b6e`
- name: `?_HeadUnlinkNode@?$_TreeNodeHeader@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@utl@@QEAAXPEAU?$_TreeNode@U?$pair@$$CBIPEAUChecksumAlgorithm@Kerb3961@@@utl@@@2@@Z`
- size: `1174`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003410`
- `0x180003cc4`

## callees

- `0x1800036d8`

## pseudocode

```c
__int64 __fastcall utl::_TreeNodeHeader<utl::pair<unsigned int const,Kerb3961::ChecksumAlgorithm *>>::_HeadUnlinkNode(
        _QWORD *a1,
        __int64 *a2)
{
  __int64 v2; // rdi
  void **v3; // r10
  _QWORD *v5; // r8
  unsigned __int64 v7; // rdx
  __int64 v8; // r14
  __int64 result; // rax
  int v10; // ecx
  _BYTE **v11; // r10
  bool v12; // bl
  _QWORD *v13; // rax
  unsigned __int64 v14; // rbx
  bool v15; // di
  _QWORD *v16; // r15
  _BYTE **v17; // r10
  bool v18; // di
  _BYTE *v19; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  __int64 v22; // r10
  void **v23; // r11
  _QWORD *v24; // rcx
  __int64 v25; // rax
  _QWORD *v26; // rax
  void **v27; // rax
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rcx
  unsigned __int64 *v30; // rdx
  _QWORD *v31; // r8
  __int64 v32; // rax
  unsigned __int64 *v33; // r15
  __int64 v34; // rax
  bool v35; // zf
  unsigned __int64 v36; // rdx
  unsigned __int64 v37; // rcx
  unsigned __int64 *v38; // r9
  _QWORD *v39; // r8
  __int64 v40; // rax
  __int64 v41; // rcx
  _QWORD *v42; // r9
  unsigned __int64 v43; // rdx
  _QWORD *v44; // r10
  _QWORD *v45; // rax
  _QWORD *v46; // r8

  v2 = *a2;
  v3 = (void **)a2[1];
  v5 = (_QWORD *)(*a2 & 0xFFFFFFFFFFFFFFFEuLL);
  v7 = a2[2];
  v8 = 1;
  result = v3 != &utl::_TreeSentinel;
  v10 = result + (v7 != (_QWORD)&utl::_TreeSentinel);
  if ( v10 )
  {
    if ( v10 == 1 )
    {
      v22 = -(__int64)(&utl::_TreeSentinel != (void **)v7) & 8;
      v23 = *(void ***)((char *)a2 + v22 + 8);
      if ( *(__int64 **)((char *)a1 + v22 + 8) == a2 )
      {
        if ( v23 == &utl::_TreeSentinel )
        {
          v24 = v5;
          if ( *(__int64 **)((char *)v5 + v22 + 8) == a2 && (__int64 *)*v5 != a2 )
          {
            v24 = (_QWORD *)(*v5 & 0xFFFFFFFFFFFFFFFEuLL);
            if ( *(_QWORD **)((char *)v24 + v22 + 8) == v5 && (_QWORD *)*v24 != v5 )
            {
              do
              {
                v26 = v24;
                v24 = (_QWORD *)(*v24 & 0xFFFFFFFFFFFFFFFEuLL);
              }
              while ( *(_QWORD **)((char *)v24 + v22 + 8) == v26 );
            }
          }
        }
        else
        {
          v24 = *(_QWORD **)((char *)a2 + v22 + 8);
          if ( a2 == (__int64 *)v23 )
            __int2c();
          v25 = 0;
          if ( (void **)v7 == &utl::_TreeSentinel )
            v25 = 1;
          if ( v23[v25 + 1] != &utl::_TreeSentinel )
          {
            do
              v24 = (_QWORD *)v24[v25 + 1];
            while ( (void **)v24[v25 + 1] != &utl::_TreeSentinel );
          }
        }
        *(_QWORD *)((char *)a1 + v22 + 8) = v24;
      }
      if ( (__int64 *)(*v5 & 0xFFFFFFFFFFFFFFFEuLL) == a2 )
      {
        *v5 = v23;
      }
      else
      {
        if ( (__int64 *)v5[2] == a2 )
          v8 = 2;
        v5[v8] = v23;
      }
      result = *a2;
      *v23 = (void *)*a2;
    }
    else if ( *(void ***)(v7 + 8) == &utl::_TreeSentinel )
    {
      v11 = (_BYTE **)(v7 + 16);
      v12 = (*(_BYTE *)v7 & 1) != 0 && (**v11 & 1) != 0;
      *(_QWORD *)v7 = v2;
      v13 = (_QWORD *)a2[1];
      *(_QWORD *)(v7 + 8) = v13;
      *v13 &= 1uLL;
      *v13 |= v7;
      *(_QWORD *)*v11 = v7 | 1;
      result = *v5 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( (__int64 *)result == a2 )
      {
        *v5 = v7;
      }
      else
      {
        result = 8;
        if ( (__int64 *)v5[2] == a2 )
          result = 16;
        *(_QWORD *)((char *)v5 + result) = v7;
      }
      if ( v12 )
      {
        v14 = v7;
        v15 = 1;
        goto LABEL_78;
      }
    }
    else
    {
      do
      {
        v16 = (_QWORD *)(v7 + 8);
        v14 = v7;
        v7 = *(_QWORD *)(v7 + 8);
      }
      while ( *(void ***)(v7 + 8) != &utl::_TreeSentinel );
      v17 = (_BYTE **)(v7 + 16);
      v18 = (*(_BYTE *)v7 & 1) != 0 && (**v17 & 1) != 0;
      v19 = *v17;
      *v16 = *v17;
      *(_QWORD *)v19 = v14 | 1;
      *(_QWORD *)v7 = *a2;
      v20 = (_QWORD *)a2[1];
      *(_QWORD *)(v7 + 8) = v20;
      *v20 &= 1uLL;
      *v20 |= v7;
      v21 = (_QWORD *)a2[2];
      *v17 = v21;
      *v21 &= 1uLL;
      *v21 |= v7;
      result = *v5 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( (__int64 *)result == a2 )
      {
        *v5 = v7;
      }
      else
      {
        result = 8;
        if ( (__int64 *)v5[2] == a2 )
          result = 16;
        *(_QWORD *)((char *)v5 + result) = v7;
      }
      if ( v18 )
      {
        v15 = 0;
        goto LABEL_78;
      }
    }
  }
  else if ( a1 == v5 )
  {
    *a1 = a1;
    a1[1] = a1;
    a1[2] = a1;
  }
  else
  {
    if ( (__int64 *)a1[1] == a2 )
    {
      if ( v3 == &utl::_TreeSentinel )
      {
        v3 = (void **)v5;
        if ( (__int64 *)v5[1] == a2 && (__int64 *)*v5 != a2 )
        {
          v3 = (void **)(*v5 & 0xFFFFFFFFFFFFFFFEuLL);
          if ( v3[1] == v5 && *v3 != v5 )
          {
            do
            {
              v27 = v3;
              v3 = (void **)((unsigned __int64)*v3 & 0xFFFFFFFFFFFFFFFEuLL);
            }
            while ( v3[1] == v27 );
          }
        }
      }
      else
      {
        if ( a2 == (__int64 *)v3 )
          __int2c();
        while ( v3[2] != &utl::_TreeSentinel )
          v3 = (void **)v3[2];
      }
      a1[1] = v3;
    }
    else if ( (__int64 *)a1[2] == a2 )
    {
      if ( (void **)v7 == &utl::_TreeSentinel )
      {
        v7 = (unsigned __int64)v5;
        if ( (__int64 *)v5[2] == a2 && (__int64 *)*v5 != a2 )
        {
          v7 = *v5 & 0xFFFFFFFFFFFFFFFEuLL;
          if ( *(_QWORD **)(v7 + 0x10) == v5 && *(_QWORD **)v7 != v5 )
          {
            do
            {
              v28 = v7;
              v7 = *(_QWORD *)v7 & 0xFFFFFFFFFFFFFFFEuLL;
            }
            while ( *(_QWORD *)(v7 + 16) == v28 );
          }
        }
      }
      else
      {
        if ( a2 == (__int64 *)v7 )
          __int2c();
        while ( *(void ***)(v7 + 8) != &utl::_TreeSentinel )
          v7 = *(_QWORD *)(v7 + 8);
      }
      a1[2] = v7;
    }
    v15 = v5[2] == (_QWORD)a2;
    result = v15;
    v5[v15 + 1] = &utl::_TreeSentinel;
    if ( (*(_BYTE *)a2 & 1) != 0 )
    {
      v14 = (unsigned __int64)v5;
      while ( 1 )
      {
LABEL_78:
        if ( (**(_BYTE **)(v14 + 8 * !v15 + 8) & 1) == 0 )
        {
          v29 = *(_QWORD *)v14 & 0xFFFFFFFFFFFFFFFEuLL;
          v30 = *(unsigned __int64 **)(v14 + 8 * !v15 + 8);
          v31 = (_QWORD *)v30[v15 + 1];
          *v30 = v29 | 1;
          if ( (*(_QWORD *)v29 & 0xFFFFFFFFFFFFFFFEuLL) == v14 )
          {
            *(_QWORD *)v29 = v30;
          }
          else
          {
            v32 = 8;
            if ( *(_QWORD *)(v29 + 16) == v14 )
              v32 = 16;
            *(_QWORD *)(v32 + v29) = v30;
          }
          *(_QWORD *)v14 = v30;
          *v31 &= 1uLL;
          *v31 |= v14;
          *(_QWORD *)(v14 + 8 * !v15 + 8) = v31;
          v30[v15 + 1] = v14;
        }
        v33 = *(unsigned __int64 **)(v14 + 8 * !v15 + 8);
        if ( (*(_BYTE *)v33[!v15 + 1] & 1) == 0 )
        {
          v45 = (_QWORD *)v33[!v15 + 1];
          *v45 |= 1uLL;
          v41 = *(_QWORD *)v14;
          v42 = (_QWORD *)(*(_QWORD *)v14 & 0xFFFFFFFFFFFFFFFEuLL);
          v43 = *(_QWORD *)(v14 + 8 * !v15 + 8);
          v44 = (_QWORD *)(v43 + 8LL * v15);
          goto LABEL_95;
        }
        if ( (*(_BYTE *)v33[v15 + 1] & 1) == 0 )
          break;
        *v33 &= ~1uLL;
        v34 = *(_QWORD *)v14;
        if ( (*(_QWORD *)v14 & 1) == 0 )
        {
          result = v34 | 1;
          *(_QWORD *)v14 = result;
          return result;
        }
        result = v34 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( a1 == (_QWORD *)result )
          return result;
        v35 = *(_QWORD *)(result + 16) == v14;
        v14 = result;
        v15 = v35;
      }
      v36 = *v33 & 0xFFFFFFFFFFFFFFFEuLL;
      v37 = v33[v15 + 1];
      v38 = (unsigned __int64 *)(v37 + 8LL * !v15);
      v39 = (_QWORD *)v38[1];
      *(_QWORD *)v37 = v36 | 1;
      v40 = 8;
      if ( *(unsigned __int64 **)(v36 + 16) == v33 )
        v40 = 16;
      *(_QWORD *)(v40 + v36) = v37;
      *v33 = v37 | 1;
      *v39 &= 1uLL;
      *v39 |= (unsigned __int64)v33;
      v33[v15 + 1] = (unsigned __int64)v39;
      v38[1] = (unsigned __int64)v33;
      v41 = *(_QWORD *)v14;
      v42 = (_QWORD *)(*(_QWORD *)v14 & 0xFFFFFFFFFFFFFFFEuLL);
      v43 = *(_QWORD *)(v14 + 8 * !v15 + 8);
      v44 = (_QWORD *)(v43 + 8LL * v15);
LABEL_95:
      v46 = (_QWORD *)v44[1];
      *(_QWORD *)v43 = v41;
      if ( (*v42 & 0xFFFFFFFFFFFFFFFEuLL) == v14 )
      {
        *v42 = v43;
      }
      else
      {
        if ( v42[2] == v14 )
          v8 = 2;
        v42[v8] = v43;
      }
      *(_QWORD *)v14 = v43 | 1;
      *v46 &= 1uLL;
      *v46 |= v14;
      result = !v15;
      *(_QWORD *)(v14 + 8 * result + 8) = v46;
      v44[1] = v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800036d8  push    rbx
0x1800036da  push    rbp
0x1800036db  push    rsi
0x1800036dc  push    rdi
0x1800036dd  push    r12
0x1800036df  push    r13
0x1800036e1  push    r14
0x1800036e3  push    r15
0x1800036e5  mov     rdi, [rdx]
0x1800036e8  lea     rbp, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x1800036ef  mov     r10, [rdx+8]
0x1800036f3  mov     r12, 0FFFFFFFFFFFFFFFEh
0x1800036fa  mov     rsi, rcx
0x1800036fd  mov     r8, rdi
0x180003700  xor     ecx, ecx
0x180003702  and     r8, r12
0x180003705  mov     r9, rdx
0x180003708  mov     rdx, [rdx+10h]
0x18000370c  cmp     rdx, rbp
0x18000370f  lea     r14d, [r12+0Ah]
0x180003714  lea     r13d, [r12+12h]
0x180003719  setnz   cl
0x18000371c  xor     eax, eax
0x18000371e  cmp     r10, rbp
0x180003721  setnz   al
0x180003724  add     ecx, eax
0x180003726  jz      loc_1800038DB
0x18000372c  cmp     ecx, 1
0x18000372f  jz      loc_180003836
0x180003735  cmp     [rdx+8], rbp
0x180003739  jnz     short loc_1800037A7
0x18000373b  lea     r11d, [r12+3]
0x180003740  lea     r10, [rdx+10h]
0x180003744  test    [rdx], r11b
0x180003747  jz      short loc_180003756
0x180003749  mov     rax, [r10]
0x18000374c  test    [rax], r11b
0x18000374f  jz      short loc_180003756
0x180003751  mov     bl, r11b
0x180003754  jmp     short loc_180003758
0x180003756  xor     bl, bl
0x180003758  mov     [rdx], rdi
0x18000375b  mov     rcx, rdx
0x18000375e  mov     rax, [r9+8]
0x180003762  or      rcx, r11
0x180003765  mov     [rdx+8], rax
0x180003769  and     [rax], r11
0x18000376c  or      [rax], rdx
0x18000376f  mov     rax, [r10]
0x180003772  mov     [rax], rcx
0x180003775  mov     rax, [r8]
0x180003778  and     rax, r12
0x18000377b  cmp     rax, r9
0x18000377e  jnz     short loc_180003785
0x180003780  mov     [r8], rdx
0x180003783  jmp     short loc_180003794
0x180003785  cmp     [r8+10h], r9
0x180003789  mov     rax, r14
0x18000378c  cmovz   rax, r13
0x180003790  mov     [rax+r8], rdx
0x180003794  test    bl, bl
0x180003796  jz      loc_180003B61
0x18000379c  mov     rbx, rdx
0x18000379f  mov     dil, r11b
0x1800037a2  jmp     loc_1800039B9
0x1800037a7  lea     r15, [rdx+8]
0x1800037ab  mov     rbx, rdx
0x1800037ae  mov     rdx, [r15]
0x1800037b1  cmp     [rdx+8], rbp
0x1800037b5  jnz     short loc_1800037A7
0x1800037b7  mov     r11d, 1
0x1800037bd  lea     r10, [rdx+10h]
0x1800037c1  test    [rdx], r11b
0x1800037c4  jz      short loc_1800037D3
0x1800037c6  mov     rax, [r10]
0x1800037c9  test    [rax], r11b
0x1800037cc  jz      short loc_1800037D3
0x1800037ce  mov     dil, r11b
0x1800037d1  jmp     short loc_1800037D6
0x1800037d3  xor     dil, dil
0x1800037d6  mov     rcx, [r10]
0x1800037d9  mov     rax, rbx
0x1800037dc  mov     [r15], rcx
0x1800037df  or      rax, r11
0x1800037e2  mov     [rcx], rax
0x1800037e5  mov     rax, [r9]
0x1800037e8  mov     [rdx], rax
0x1800037eb  mov     rax, [r9+8]
0x1800037ef  mov     [rdx+8], rax
0x1800037f3  and     [rax], r11
0x1800037f6  or      [rax], rdx
0x1800037f9  mov     rax, [r9+10h]
0x1800037fd  mov     [r10], rax
0x180003800  and     [rax], r11
0x180003803  or      [rax], rdx
0x180003806  mov     rax, [r8]
0x180003809  and     rax, r12
0x18000380c  cmp     rax, r9
0x18000380f  jnz     short loc_180003816
0x180003811  mov     [r8], rdx
0x180003814  jmp     short loc_180003825
0x180003816  cmp     [r8+10h], r9
0x18000381a  mov     rax, r14
0x18000381d  cmovz   rax, r13
0x180003821  mov     [rax+r8], rdx
0x180003825  test    dil, dil
0x180003828  jz      loc_180003B61
0x18000382e  xor     dil, dil
0x180003831  jmp     loc_1800039B9
0x180003836  mov     rax, rdx
0x180003839  sub     rax, rbp
0x18000383c  neg     rax
0x18000383f  sbb     r10, r10
0x180003842  and     r10, r14
0x180003845  mov     r11, [r10+r9+8]
0x18000384a  cmp     [r10+rsi+8], r9
0x18000384f  jnz     short loc_1800038B4
0x180003851  cmp     r11, rbp
0x180003854  jz      short loc_18000387E
0x180003856  mov     rcx, r11
0x180003859  cmp     r9, r11
0x18000385c  jnz     short loc_180003860
0x18000385e  int     2Ch; Windows NT - assertion failure
0x180003860  xor     eax, eax
0x180003862  cmp     rdx, rbp
0x180003865  cmovz   rax, r14
0x180003869  cmp     [rax+r11+8], rbp
0x18000386e  jz      short loc_1800038AF
0x180003870  mov     rcx, [rcx+rax+8]
0x180003875  cmp     [rcx+rax+8], rbp
0x18000387a  jnz     short loc_180003870
0x18000387c  jmp     short loc_1800038AF
0x18000387e  mov     rcx, r8
0x180003881  cmp     [r10+r8+8], r9
0x180003886  jnz     short loc_1800038AF
0x180003888  cmp     [r8], r9
0x18000388b  jz      short loc_1800038AF
0x18000388d  mov     rcx, [r8]
0x180003890  and     rcx, r12
0x180003893  cmp     [r10+rcx+8], r8
0x180003898  jnz     short loc_1800038AF
0x18000389a  cmp     [rcx], r8
0x18000389d  jz      short loc_1800038AF
0x18000389f  mov     rax, rcx
0x1800038a2  mov     rcx, [rcx]
0x1800038a5  and     rcx, r12
0x1800038a8  cmp     [r10+rcx+8], rax
0x1800038ad  jz      short loc_18000389F
0x1800038af  mov     [r10+rsi+8], rcx
0x1800038b4  mov     rax, [r8]
0x1800038b7  and     rax, r12
0x1800038ba  cmp     rax, r9
0x1800038bd  jnz     short loc_1800038C4
0x1800038bf  mov     [r8], r11
0x1800038c2  jmp     short loc_1800038D0
0x1800038c4  cmp     [r8+10h], r9
0x1800038c8  cmovz   r14, r13
0x1800038cc  mov     [r14+r8], r11
0x1800038d0  mov     rax, [r9]
0x1800038d3  mov     [r11], rax
0x1800038d6  jmp     loc_180003B61
0x1800038db  cmp     rsi, r8
0x1800038de  jnz     short loc_1800038F0
0x1800038e0  mov     [rsi], rsi
0x1800038e3  mov     [rsi+8], rsi
0x1800038e7  mov     [rsi+10h], rsi
0x1800038eb  jmp     loc_180003B61
0x1800038f0  cmp     [rsi+8], r9
0x1800038f4  jnz     short loc_180003944
0x1800038f6  cmp     r10, rbp
0x1800038f9  jz      short loc_180003910
0x1800038fb  cmp     r9, r10
0x1800038fe  jnz     short loc_180003908
0x180003900  int     2Ch; Windows NT - assertion failure
0x180003902  jmp     short loc_180003908
0x180003904  mov     r10, [r10+10h]
0x180003908  cmp     [r10+10h], rbp
0x18000390c  jnz     short loc_180003904
0x18000390e  jmp     short loc_18000393E
0x180003910  mov     r10, r8
0x180003913  cmp     [r8+8], r9
0x180003917  jnz     short loc_18000393E
0x180003919  cmp     [r8], r9
0x18000391c  jz      short loc_18000393E
0x18000391e  mov     r10, [r8]
0x180003921  and     r10, r12
0x180003924  cmp     [r10+8], r8
0x180003928  jnz     short loc_18000393E
0x18000392a  cmp     [r10], r8
0x18000392d  jz      short loc_18000393E
0x18000392f  mov     rax, r10
0x180003932  mov     r10, [r10]
0x180003935  and     r10, r12
0x180003938  cmp     [r10+8], rax
0x18000393c  jz      short loc_18000392F
0x18000393e  mov     [rsi+8], r10
0x180003942  jmp     short loc_180003996
0x180003944  cmp     [rsi+10h], r9
0x180003948  jnz     short loc_180003996
0x18000394a  cmp     rdx, rbp
0x18000394d  jz      short loc_180003964
0x18000394f  cmp     r9, rdx
0x180003952  jnz     short loc_18000395C
0x180003954  int     2Ch; Windows NT - assertion failure
0x180003956  jmp     short loc_18000395C
0x180003958  mov     rdx, [rdx+8]
0x18000395c  cmp     [rdx+8], rbp
0x180003960  jnz     short loc_180003958
0x180003962  jmp     short loc_180003992
0x180003964  mov     rdx, r8
0x180003967  cmp     [r8+10h], r9
0x18000396b  jnz     short loc_180003992
0x18000396d  cmp     [r8], r9
0x180003970  jz      short loc_180003992
0x180003972  mov     rdx, [r8]
0x180003975  and     rdx, r12
0x180003978  cmp     [rdx+10h], r8
0x18000397c  jnz     short loc_180003992
0x18000397e  cmp     [rdx], r8
0x180003981  jz      short loc_180003992
0x180003983  mov     rax, rdx
0x180003986  mov     rdx, [rdx]
0x180003989  and     rdx, r12
0x18000398c  cmp     [rdx+10h], rax
0x180003990  jz      short loc_180003983
0x180003992  mov     [rsi+10h], rdx
0x180003996  cmp     [r8+10h], r9
0x18000399a  mov     r11d, 1
0x1800039a0  setz    dil
0x1800039a4  movzx   eax, dil
0x1800039a8  mov     [r8+rax*8+8], rbp
0x1800039ad  test    [r9], r11b
0x1800039b0  jz      loc_180003B61
0x1800039b6  mov     rbx, r8
0x1800039b9  movzx   eax, dil
0x1800039bd  xor     rax, r11
0x1800039c0  mov     rax, [rbx+rax*8+8]
0x1800039c5  test    [rax], r11b
0x1800039c8  jnz     short loc_180003A27
0x1800039ca  mov     rcx, [rbx]
0x1800039cd  and     rcx, r12
0x1800039d0  movzx   eax, dil
0x1800039d4  xor     rax, r11
0x1800039d7  movzx   r9d, dil
0x1800039db  mov     rdx, [rbx+rax*8+8]
0x1800039e0  mov     rax, rcx
0x1800039e3  or      rax, r11
0x1800039e6  mov     r8, [rdx+r9*8+8]
0x1800039eb  mov     [rdx], rax
0x1800039ee  mov     rax, [rcx]
0x1800039f1  and     rax, r12
0x1800039f4  cmp     rax, rbx
0x1800039f7  jnz     short loc_1800039FE
0x1800039f9  mov     [rcx], rdx
0x1800039fc  jmp     short loc_180003A0D
0x1800039fe  cmp     [rcx+10h], rbx
0x180003a02  mov     rax, r14
0x180003a05  cmovz   rax, r13
0x180003a09  mov     [rax+rcx], rdx
0x180003a0d  mov     [rbx], rdx
0x180003a10  and     [r8], r11
0x180003a13  or      [r8], rbx
0x180003a16  movzx   eax, dil
0x180003a1a  xor     rax, r11
0x180003a1d  mov     [rbx+rax*8+8], r8
0x180003a22  mov     [rdx+r9*8+8], rbx
0x180003a27  movzx   eax, dil
0x180003a2b  xor     rax, r11
0x180003a2e  mov     r15, [rbx+rax*8+8]
0x180003a33  movzx   eax, dil
0x180003a37  xor     rax, r11
0x180003a3a  mov     rax, [r15+rax*8+8]
0x180003a3f  test    [rax], r11b
0x180003a42  jz      loc_180003AF6
0x180003a48  movzx   ebp, dil
0x180003a4c  mov     rax, [r15+rbp*8+8]
0x180003a51  test    [rax], r11b
0x180003a54  jz      short loc_180003A88
0x180003a56  and     [r15], r12
0x180003a59  mov     rax, [rbx]
0x180003a5c  test    r11b, al
0x180003a5f  jz      short loc_180003A7D
0x180003a61  and     rax, r12
0x180003a64  cmp     rsi, rax
0x180003a67  jz      loc_180003B61
0x180003a6d  cmp     [rax+10h], rbx
0x180003a71  mov     rbx, rax
0x180003a74  setz    dil
0x180003a78  jmp     loc_1800039B9
0x180003a7d  or      rax, r11
0x180003a80  mov     [rbx], rax
0x180003a83  jmp     loc_180003B61
0x180003a88  mov     rdx, [r15]
0x180003a8b  mov     al, dil
0x180003a8e  xor     al, r11b
0x180003a91  and     rdx, r12
0x180003a94  movzx   r10d, al
0x180003a98  mov     eax, r10d
0x180003a9b  xor     rax, r11
0x180003a9e  mov     rcx, [r15+rax*8+8]
  ... truncated ...
```
