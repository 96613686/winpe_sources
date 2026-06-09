# ComputeSetDifferences

- ea: `0x18001e12c`
- end: `0x18001e3a1`
- name: `ComputeSetDifferences`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001eb14`

## callees

- `0x18001cb48`
- `0x18001cb7c`
- `0x18001d978`
- `0x18001e12c`

## pseudocode

```c
void __fastcall ComputeSetDifferences(_QWORD **a1, _QWORD **a2, __int64 a3, __int64 a4)
{
  _QWORD *v4; // rsi
  _QWORD *v6; // r14
  _QWORD *v8; // rbx
  _QWORD *v9; // rdi
  __int64 **v10; // rcx
  __int64 k; // rax
  __int64 *m; // rcx
  __int64 **v13; // rcx
  __int64 n; // rax
  __int64 *ii; // rcx
  __int64 **v16; // rcx
  __int64 jj; // rax
  __int64 *kk; // rcx
  __int64 **v19; // rcx
  __int64 *mm; // rcx
  __int64 **v21; // rcx
  __int64 i; // rax
  __int64 *j; // rcx
  __int64 **v24; // rcx
  __int64 nn; // rax
  __int64 *i1; // rcx
  _BYTE v27[16]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v28[88]; // [rsp+30h] [rbp-58h] BYREF

  v4 = *a1;
  v6 = *a2;
  v8 = (_QWORD *)**a1;
  v9 = (_QWORD *)**a2;
  while ( v9 != v6 )
  {
    if ( v8 == v4 )
    {
      while ( v9 != v6 )
      {
        std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(a4, v28, v9 + 4);
        v21 = (__int64 **)v9[2];
        if ( *((_BYTE *)v21 + 25) )
        {
          for ( i = v9[1]; !*(_BYTE *)(i + 25) && v9 == *(_QWORD **)(i + 16); i = *(_QWORD *)(i + 8) )
            v9 = (_QWORD *)i;
          v9 = (_QWORD *)i;
        }
        else
        {
          v9 = (_QWORD *)v9[2];
          for ( j = *v21; !*((_BYTE *)j + 25); j = (__int64 *)*j )
            v9 = j;
        }
      }
      return;
    }
    if ( (unsigned __int8)operator<(v8 + 4, v9 + 4) )
    {
      std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
        a3,
        v27,
        v8 + 6);
      v10 = (__int64 **)v8[2];
      if ( *((_BYTE *)v10 + 25) )
      {
        for ( k = v8[1]; !*(_BYTE *)(k + 25) && v8 == *(_QWORD **)(k + 16); k = *(_QWORD *)(k + 8) )
          v8 = (_QWORD *)k;
        v8 = (_QWORD *)k;
      }
      else
      {
        v8 = (_QWORD *)v8[2];
        for ( m = *v10; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v8 = m;
      }
    }
    else if ( (unsigned __int8)operator<(v9 + 4, v8 + 4) )
    {
      std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(a4, v28, v9 + 4);
      v13 = (__int64 **)v9[2];
      if ( *((_BYTE *)v13 + 25) )
      {
        for ( n = v9[1]; !*(_BYTE *)(n + 25) && v9 == *(_QWORD **)(n + 16); n = *(_QWORD *)(n + 8) )
          v9 = (_QWORD *)n;
        goto LABEL_37;
      }
      v9 = (_QWORD *)v9[2];
      for ( ii = *v13; !*((_BYTE *)ii + 25); ii = (__int64 *)*ii )
        v9 = ii;
    }
    else
    {
      v16 = (__int64 **)v8[2];
      if ( *((_BYTE *)v16 + 25) )
      {
        for ( jj = v8[1]; !*(_BYTE *)(jj + 25) && v8 == *(_QWORD **)(jj + 16); jj = *(_QWORD *)(jj + 8) )
          v8 = (_QWORD *)jj;
        v8 = (_QWORD *)jj;
      }
      else
      {
        v8 = (_QWORD *)v8[2];
        for ( kk = *v16; !*((_BYTE *)kk + 25); kk = (__int64 *)*kk )
          v8 = kk;
      }
      v19 = (__int64 **)v9[2];
      if ( *((_BYTE *)v19 + 25) )
      {
        for ( n = v9[1]; !*(_BYTE *)(n + 25) && v9 == *(_QWORD **)(n + 16); n = *(_QWORD *)(n + 8) )
          v9 = (_QWORD *)n;
LABEL_37:
        v9 = (_QWORD *)n;
      }
      else
      {
        v9 = (_QWORD *)v9[2];
        for ( mm = *v19; !*((_BYTE *)mm + 25); mm = (__int64 *)*mm )
          v9 = mm;
      }
    }
  }
  while ( v8 != v4 )
  {
    std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(
      a3,
      v28,
      v8 + 6);
    v24 = (__int64 **)v8[2];
    if ( *((_BYTE *)v24 + 25) )
    {
      for ( nn = v8[1]; !*(_BYTE *)(nn + 25) && v8 == *(_QWORD **)(nn + 16); nn = *(_QWORD *)(nn + 8) )
        v8 = (_QWORD *)nn;
      v8 = (_QWORD *)nn;
    }
    else
    {
      v8 = (_QWORD *)v8[2];
      for ( i1 = *v24; !*((_BYTE *)i1 + 25); i1 = (__int64 *)*i1 )
        v8 = i1;
    }
  }
}

```

## disassembly

```asm
0x18001e12c  push    rbx
0x18001e12e  push    rbp
0x18001e12f  push    rsi
0x18001e130  push    rdi
0x18001e131  push    r12
0x18001e133  push    r13
0x18001e135  push    r14
0x18001e137  push    r15
0x18001e139  sub     rsp, 48h
0x18001e13d  mov     rsi, [rcx]
0x18001e140  mov     r13, r9
0x18001e143  mov     r14, [rdx]
0x18001e146  mov     r12, r8
0x18001e149  xor     r15d, r15d
0x18001e14c  mov     rbx, [rsi]
0x18001e14f  mov     rdi, [r14]
0x18001e152  cmp     rdi, r14
0x18001e155  jz      loc_18001E335
0x18001e15b  cmp     rbx, rsi
0x18001e15e  jz      loc_18001E2D6
0x18001e164  lea     rbp, [rdi+20h]
0x18001e168  mov     rdx, rbp
0x18001e16b  lea     rcx, [rbx+20h]
0x18001e16f  call    ??M@YA_NAEBU_GUID@@0@Z; operator<(_GUID const &,_GUID const &)
0x18001e174  test    al, al
0x18001e176  jz      short loc_18001E1D1
0x18001e178  lea     r8, [rbx+30h]
0x18001e17c  mov     rcx, r12
0x18001e17f  lea     rdx, [rsp+88h+var_68]
0x18001e184  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18001e189  mov     rcx, [rbx+10h]
0x18001e18d  xor     r15b, r15b
0x18001e190  cmp     [rcx+19h], r15b
0x18001e194  jz      short loc_18001E1B4
0x18001e196  mov     rax, [rbx+8]
0x18001e19a  jmp     short loc_18001E1A9
0x18001e19c  cmp     rbx, [rax+10h]
0x18001e1a0  jnz     short loc_18001E1AF
0x18001e1a2  mov     rbx, rax
0x18001e1a5  mov     rax, [rax+8]
0x18001e1a9  cmp     [rax+19h], r15b
0x18001e1ad  jz      short loc_18001E19C
0x18001e1af  mov     rbx, rax
0x18001e1b2  jmp     short loc_18001E152
0x18001e1b4  mov     rbx, rcx
0x18001e1b7  mov     rcx, [rcx]
0x18001e1ba  cmp     [rcx+19h], r15b
0x18001e1be  jnz     short loc_18001E152
0x18001e1c0  mov     rax, [rcx]
0x18001e1c3  mov     rbx, rcx
0x18001e1c6  mov     rcx, rax
0x18001e1c9  cmp     [rax+19h], r15b
0x18001e1cd  jz      short loc_18001E1C0
0x18001e1cf  jmp     short loc_18001E152
0x18001e1d1  lea     rdx, [rbx+20h]
0x18001e1d5  mov     rcx, rbp
0x18001e1d8  call    ??M@YA_NAEBU_GUID@@0@Z; operator<(_GUID const &,_GUID const &)
0x18001e1dd  xor     r15b, r15b
0x18001e1e0  test    al, al
0x18001e1e2  jz      short loc_18001E244
0x18001e1e4  mov     r8, rbp
0x18001e1e7  lea     rdx, [rsp+88h+var_58]
0x18001e1ec  mov     rcx, r13
0x18001e1ef  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x18001e1f4  mov     rcx, [rdi+10h]
0x18001e1f8  cmp     [rcx+19h], r15b
0x18001e1fc  jz      short loc_18001E220
0x18001e1fe  mov     rax, [rdi+8]
0x18001e202  jmp     short loc_18001E215
0x18001e204  cmp     rdi, [rax+10h]
0x18001e208  jnz     loc_18001E2AA
0x18001e20e  mov     rdi, rax
0x18001e211  mov     rax, [rax+8]
0x18001e215  cmp     [rax+19h], r15b
0x18001e219  jz      short loc_18001E204
0x18001e21b  jmp     loc_18001E2AA
0x18001e220  mov     rdi, rcx
0x18001e223  mov     rcx, [rcx]
0x18001e226  cmp     [rcx+19h], r15b
0x18001e22a  jnz     loc_18001E152
0x18001e230  mov     rax, [rcx]
0x18001e233  mov     rdi, rcx
0x18001e236  mov     rcx, rax
0x18001e239  cmp     [rax+19h], r15b
0x18001e23d  jz      short loc_18001E230
0x18001e23f  jmp     loc_18001E152
0x18001e244  mov     rcx, [rbx+10h]
0x18001e248  cmp     [rcx+19h], r15b
0x18001e24c  jz      short loc_18001E26C
0x18001e24e  mov     rax, [rbx+8]
0x18001e252  jmp     short loc_18001E261
0x18001e254  cmp     rbx, [rax+10h]
0x18001e258  jnz     short loc_18001E267
0x18001e25a  mov     rbx, rax
0x18001e25d  mov     rax, [rax+8]
0x18001e261  cmp     [rax+19h], r15b
0x18001e265  jz      short loc_18001E254
0x18001e267  mov     rbx, rax
0x18001e26a  jmp     short loc_18001E287
0x18001e26c  mov     rbx, rcx
0x18001e26f  mov     rcx, [rcx]
0x18001e272  cmp     [rcx+19h], r15b
0x18001e276  jnz     short loc_18001E287
0x18001e278  mov     rax, [rcx]
0x18001e27b  mov     rbx, rcx
0x18001e27e  mov     rcx, rax
0x18001e281  cmp     [rax+19h], r15b
0x18001e285  jz      short loc_18001E278
0x18001e287  mov     rcx, [rdi+10h]
0x18001e28b  cmp     [rcx+19h], r15b
0x18001e28f  jz      short loc_18001E2B2
0x18001e291  mov     rax, [rdi+8]
0x18001e295  jmp     short loc_18001E2A4
0x18001e297  cmp     rdi, [rax+10h]
0x18001e29b  jnz     short loc_18001E2AA
0x18001e29d  mov     rdi, rax
0x18001e2a0  mov     rax, [rax+8]
0x18001e2a4  cmp     [rax+19h], r15b
0x18001e2a8  jz      short loc_18001E297
0x18001e2aa  mov     rdi, rax
0x18001e2ad  jmp     loc_18001E152
0x18001e2b2  mov     rdi, rcx
0x18001e2b5  mov     rcx, [rcx]
0x18001e2b8  cmp     [rcx+19h], r15b
0x18001e2bc  jnz     loc_18001E152
0x18001e2c2  mov     rax, [rcx]
0x18001e2c5  mov     rdi, rcx
0x18001e2c8  mov     rcx, rax
0x18001e2cb  cmp     [rax+19h], r15b
0x18001e2cf  jz      short loc_18001E2C2
0x18001e2d1  jmp     loc_18001E152
0x18001e2d6  cmp     rdi, r14
0x18001e2d9  jz      loc_18001E390
0x18001e2df  lea     r8, [rdi+20h]
0x18001e2e3  mov     rcx, r13
0x18001e2e6  lea     rdx, [rsp+88h+var_58]
0x18001e2eb  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@U_GUID@@U?$less@U_GUID@@@std@@V?$allocator@U_GUID@@@3@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U_GUID@@@std@@@std@@@std@@_N@1@AEBU_GUID@@@Z; std::_Tree<std::_Tset_traits<_GUID,std::less<_GUID>,std::allocator<_GUID>,0>>::insert<0,0>(_GUID const &)
0x18001e2f0  mov     rcx, [rdi+10h]
0x18001e2f4  cmp     [rcx+19h], r15b
0x18001e2f8  jz      short loc_18001E318
0x18001e2fa  mov     rax, [rdi+8]
0x18001e2fe  jmp     short loc_18001E30D
0x18001e300  cmp     rdi, [rax+10h]
0x18001e304  jnz     short loc_18001E313
0x18001e306  mov     rdi, rax
0x18001e309  mov     rax, [rax+8]
0x18001e30d  cmp     [rax+19h], r15b
0x18001e311  jz      short loc_18001E300
0x18001e313  mov     rdi, rax
0x18001e316  jmp     short loc_18001E2D6
0x18001e318  mov     rdi, rcx
0x18001e31b  mov     rcx, [rcx]
0x18001e31e  cmp     [rcx+19h], r15b
0x18001e322  jnz     short loc_18001E2D6
0x18001e324  mov     rax, [rcx]
0x18001e327  mov     rdi, rcx
0x18001e32a  mov     rcx, rax
0x18001e32d  cmp     [rax+19h], r15b
0x18001e331  jz      short loc_18001E324
0x18001e333  jmp     short loc_18001E2D6
0x18001e335  cmp     rbx, rsi
0x18001e338  jz      short loc_18001E390
0x18001e33a  lea     r8, [rbx+30h]
0x18001e33e  mov     rcx, r12
0x18001e341  lea     rdx, [rsp+88h+var_58]
0x18001e346  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tset_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@_N@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::insert<0,0>(std::wstring const &)
0x18001e34b  mov     rcx, [rbx+10h]
0x18001e34f  cmp     [rcx+19h], r15b
0x18001e353  jz      short loc_18001E373
0x18001e355  mov     rax, [rbx+8]
0x18001e359  jmp     short loc_18001E368
0x18001e35b  cmp     rbx, [rax+10h]
0x18001e35f  jnz     short loc_18001E36E
0x18001e361  mov     rbx, rax
0x18001e364  mov     rax, [rax+8]
0x18001e368  cmp     [rax+19h], r15b
0x18001e36c  jz      short loc_18001E35B
0x18001e36e  mov     rbx, rax
0x18001e371  jmp     short loc_18001E335
0x18001e373  mov     rbx, rcx
0x18001e376  mov     rcx, [rcx]
0x18001e379  cmp     [rcx+19h], r15b
0x18001e37d  jnz     short loc_18001E335
0x18001e37f  mov     rax, [rcx]
0x18001e382  mov     rbx, rcx
0x18001e385  mov     rcx, rax
0x18001e388  cmp     [rax+19h], r15b
0x18001e38c  jz      short loc_18001E37F
0x18001e38e  jmp     short loc_18001E335
0x18001e390  add     rsp, 48h
0x18001e394  pop     r15
0x18001e396  pop     r14
0x18001e398  pop     r13
0x18001e39a  pop     r12
0x18001e39c  pop     rdi
0x18001e39d  pop     rsi
0x18001e39e  pop     rbp
0x18001e39f  pop     rbx
0x18001e3a0  retn
```
