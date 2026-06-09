# stdext::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)

- ea: `0x1800160b8`
- end: `0x1800163c1`
- name: `?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@stdext@@QEAA?AU?$pair@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@_N@std@@AEBQEBG@Z`
- size: `777`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180015f20`

## callees

- `0x180013ac8`
- `0x1800160b8`
- `0x180016418`
- `0x1800166a0`
- `0x180026e30`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180016338`
- `msvcrt!_wcsicmp` at `0x180016368`
- `msvcrt!_wcsicmp` at `0x180016338`
- `msvcrt!_wcsicmp` at `0x180016368`

## pseudocode

```c
__int64 __fastcall stdext::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::insert(
        unsigned __int64 a1,
        __int64 a2,
        const wchar_t **a3)
{
  _QWORD *v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rcx
  unsigned __int64 v10; // r8
  __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rsi
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // r8
  unsigned __int64 i; // rdx
  __int64 v23; // r8
  unsigned __int64 v24; // rbx
  unsigned __int64 v25; // rsi
  __int64 v26; // rax
  __int64 *v27; // rbx
  __int64 v28; // rax
  __int64 v30; // [rsp+20h] [rbp-48h] BYREF

  v5 = (_QWORD *)a1;
  if ( *(_QWORD *)(a1 + 72) <= *(_QWORD *)(a1 + 24) >> 2 )
  {
    if ( *(_QWORD *)(a1 + 40) )
      v6 = (__int64)(*(_QWORD *)(a1 + 48) - *(_QWORD *)(a1 + 40)) >> 3;
    else
      v6 = 0;
    if ( (unsigned __int64)(v6 - 1) > *(_QWORD *)(a1 + 72) )
    {
      v13 = *(_QWORD *)(a1 + 64);
      if ( v13 < *(_QWORD *)(a1 + 72) )
        *(_QWORD *)(a1 + 64) = 2 * v13 + 1;
    }
    else
    {
      if ( *(_QWORD *)(a1 + 40) )
        v7 = (__int64)(*(_QWORD *)(a1 + 48) - *(_QWORD *)(a1 + 40)) >> 3;
      else
        v7 = 0;
      v8 = v5[2];
      v9 = 2 * v7 - 3;
      v5[8] = v9;
      v10 = v9 + 2;
      v30 = v8;
      v11 = v5[5];
      if ( v11 )
        a1 = (v5[6] - v11) >> 3;
      else
        a1 = 0;
      if ( a1 >= v10 )
      {
        if ( v11 )
        {
          a1 = (v5[6] - v11) >> 3;
          if ( v10 < a1 )
          {
            a1 = v11 + 8 * v10;
            if ( a1 != v5[6] )
              v5[6] = a1;
          }
        }
      }
      else
      {
        if ( v11 )
          v12 = (v5[6] - v11) >> 3;
        else
          v12 = 0;
        ((void (__fastcall *)(_QWORD *, _QWORD, unsigned __int64, __int64 *))std::vector<std::list<unsigned short const *>::iterator,std::allocator<std::list<unsigned short const *>::iterator>>::_Insert_n)(
          v5 + 4,
          v5[6],
          v10 - v12,
          &v30);
      }
    }
    v14 = v5[5];
    v15 = v5[9] - (v5[8] >> 1) - 1LL;
    v16 = *(_QWORD *)(v14 + 8 * v15);
    while ( v16 != *(_QWORD *)(v14 + 8 * v15 + 8) )
    {
      if ( (v5[8] & Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, *(_QWORD *)(v16 + 16))) == v15 )
      {
        v16 = *(_QWORD *)v16;
      }
      else
      {
        a1 = *(_QWORD *)v16;
        if ( *(_QWORD *)v16 != v5[2] )
        {
          v17 = v15;
          if ( v16 == *(_QWORD *)(v5[5] + 8 * v15) )
          {
            v18 = 8 * v15;
            do
            {
              *(_QWORD *)(v18 + v5[5]) = a1;
              if ( !v17 )
                break;
              --v17;
              v18 = 8 * v17;
            }
            while ( v16 == *(_QWORD *)(8 * v17 + v5[5]) );
          }
          v19 = v5[2];
          **(_QWORD **)(v16 + 8) = a1;
          **(_QWORD **)(a1 + 8) = v19;
          **(_QWORD **)(v19 + 8) = v16;
          v20 = *(_QWORD *)(v19 + 8);
          *(_QWORD *)(v19 + 8) = *(_QWORD *)(a1 + 8);
          *(_QWORD *)(a1 + 8) = *(_QWORD *)(v16 + 8);
          *(_QWORD *)(v16 + 8) = v20;
          v21 = v5[2];
          v16 = *(_QWORD *)(v21 + 8);
          *(_QWORD *)(v5[5] + 8LL * v5[9] + 8) = v21;
        }
        for ( i = v5[9]; v15 < i; --i )
        {
          v23 = v5[5];
          if ( *(_QWORD *)(v23 + 8 * i) != v5[2] )
            break;
          *(_QWORD *)(v23 + 8 * i) = v16;
        }
        if ( a1 == v5[2] )
          break;
        v16 = a1;
      }
      v14 = v5[5];
    }
    ++v5[9];
  }
  v24 = v5[8];
  v25 = v24 & Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, *a3);
  if ( v5[9] <= v25 )
    v25 += -1LL - (v24 >> 1);
  v26 = v5[5];
  v27 = *(__int64 **)(v26 + 8 * v25 + 8);
  while ( v27 != *(__int64 **)(v26 + 8 * v25) )
  {
    v27 = (__int64 *)v27[1];
    if ( _wcsicmp(*a3, (const wchar_t *)v27[2]) >= 0 )
    {
      if ( _wcsicmp((const wchar_t *)v27[2], *a3) >= 0 )
      {
        *(_QWORD *)a2 = v27;
        *(_BYTE *)(a2 + 8) = 0;
        return a2;
      }
      v27 = (__int64 *)*v27;
      break;
    }
    v26 = v5[5];
  }
  std::list<unsigned short const *>::_Insert(v5 + 1, v27, a3);
  v28 = v27[1];
  while ( v27 == *(__int64 **)(v5[5] + 8 * v25) )
  {
    *(_QWORD *)(v5[5] + 8 * v25) = v28;
    if ( !v25 )
      break;
    --v25;
  }
  *(_QWORD *)a2 = v28;
  *(_BYTE *)(a2 + 8) = 1;
  return a2;
}

```

## disassembly

```asm
0x1800160b8  push    rbx
0x1800160ba  push    rbp
0x1800160bb  push    rsi
0x1800160bc  push    rdi
0x1800160bd  push    r12
0x1800160bf  push    r14
0x1800160c1  push    r15
0x1800160c3  sub     rsp, 30h
0x1800160c7  mov     rax, cs:__security_cookie
0x1800160ce  xor     rax, rsp
0x1800160d1  mov     [rsp+68h+var_40], rax
0x1800160d6  mov     rax, [rcx+18h]
0x1800160da  xor     r12d, r12d
0x1800160dd  shr     rax, 2
0x1800160e1  mov     r15, r8
0x1800160e4  mov     r14, rdx
0x1800160e7  mov     rdi, rcx
0x1800160ea  cmp     [rcx+48h], rax
0x1800160ee  ja      loc_1800162FD
0x1800160f4  cmp     [rcx+28h], r12
0x1800160f8  jnz     short loc_1800160FF
0x1800160fa  mov     eax, r12d
0x1800160fd  jmp     short loc_18001610B
0x1800160ff  mov     rax, [rcx+30h]
0x180016103  sub     rax, [rcx+28h]
0x180016107  sar     rax, 3
0x18001610b  dec     rax
0x18001610e  cmp     rax, [rcx+48h]
0x180016112  ja      loc_1800161EC
0x180016118  cmp     [rcx+28h], r12
0x18001611c  jnz     short loc_180016123
0x18001611e  mov     rcx, r12
0x180016121  jmp     short loc_18001612F
0x180016123  mov     rcx, [rcx+30h]
0x180016127  sub     rcx, [rdi+28h]
0x18001612b  sar     rcx, 3
0x18001612f  mov     rax, [rdi+10h]
0x180016133  lea     rcx, ds:0FFFFFFFFFFFFFFFDh[rcx*2]
0x18001613b  mov     [rdi+40h], rcx
0x18001613f  lea     r8, [rcx+2]
0x180016143  mov     [rsp+68h+var_48], rax
0x180016148  mov     rax, [rdi+28h]
0x18001614c  test    rax, rax
0x18001614f  jnz     short loc_180016156
0x180016151  mov     rcx, r12
0x180016154  jmp     short loc_180016161
0x180016156  mov     rcx, [rdi+30h]
0x18001615a  sub     rcx, rax
0x18001615d  sar     rcx, 3
0x180016161  cmp     rcx, r8
0x180016164  jnb     short loc_180016192
0x180016166  test    rax, rax
0x180016169  jnz     short loc_180016170
0x18001616b  mov     rcx, r12
0x18001616e  jmp     short loc_18001617B
0x180016170  mov     rcx, [rdi+30h]
0x180016174  sub     rcx, rax
0x180016177  sar     rcx, 3
0x18001617b  mov     rdx, [rdi+30h]
0x18001617f  lea     r9, [rsp+68h+var_48]
0x180016184  sub     r8, rcx
0x180016187  lea     rcx, [rdi+20h]
0x18001618b  call    ?_Insert_n@?$vector@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@V?$allocator@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@@3@@std@@IEAAXV?$_Vector_iterator@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@V?$allocator@Viterator@?$list@PEBGV?$allocator@PEBG@std@@@std@@@3@@2@_KAEBViterator@?$list@PEBGV?$allocator@PEBG@std@@@2@@Z; std::vector<std::list<ushort const *>::iterator,std::allocator<std::list<ushort const *>::iterator>>::_Insert_n(std::_Vector_iterator<std::list<ushort const *>::iterator,std::allocator<std::list<ushort const *>::iterator>>,unsigned __int64,std::list<ushort const *>::iterator const &)
0x180016190  jmp     short loc_180016202
0x180016192  test    rax, rax
0x180016195  jz      short loc_180016202
0x180016197  mov     rdx, [rdi+30h]
0x18001619b  mov     rcx, rdx
0x18001619e  sub     rcx, rax
0x1800161a1  sar     rcx, 3
0x1800161a5  cmp     r8, rcx
0x1800161a8  jnb     short loc_180016202
0x1800161aa  lea     rcx, [rax+r8*8]
0x1800161ae  cmp     rcx, rdx
0x1800161b1  jz      short loc_180016202
0x1800161b3  mov     r8, rdx
0x1800161b6  mov     r9, r12
0x1800161b9  sub     r8, rdx
0x1800161bc  add     r8, 7
0x1800161c0  shr     r8, 3
0x1800161c4  cmp     rdx, rdx
0x1800161c7  cmova   r8, r12
0x1800161cb  test    r8, r8
0x1800161ce  jz      short loc_1800161E6
0x1800161d0  sub     rdx, rcx
0x1800161d3  mov     rax, [rdx+rcx]
0x1800161d7  inc     r9
0x1800161da  mov     [rcx], rax
0x1800161dd  add     rcx, 8
0x1800161e1  cmp     r9, r8
0x1800161e4  jnz     short loc_1800161D3
0x1800161e6  mov     [rdi+30h], rcx
0x1800161ea  jmp     short loc_180016202
0x1800161ec  mov     rax, [rcx+40h]
0x1800161f0  cmp     rax, [rcx+48h]
0x1800161f4  jnb     short loc_180016202
0x1800161f6  lea     rax, ds:1[rax*2]
0x1800161fe  mov     [rcx+40h], rax
0x180016202  mov     rax, [rdi+40h]
0x180016206  mov     rsi, [rdi+48h]
0x18001620a  shr     rax, 1
0x18001620d  sub     rsi, rax
0x180016210  mov     rax, [rdi+28h]
0x180016214  dec     rsi
0x180016217  mov     rbp, rsi
0x18001621a  shl     rbp, 3
0x18001621e  mov     rbx, [rax+rbp]
0x180016222  jmp     loc_1800162EE
0x180016227  mov     rdx, [rbx+10h]
0x18001622b  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180016230  and     rax, [rdi+40h]
0x180016234  cmp     rax, rsi
0x180016237  jnz     short loc_180016241
0x180016239  mov     rbx, [rbx]
0x18001623c  jmp     loc_1800162EA
0x180016241  mov     rcx, [rbx]
0x180016244  cmp     rcx, [rdi+10h]
0x180016248  jz      short loc_1800162C1
0x18001624a  mov     rax, [rdi+28h]
0x18001624e  mov     rdx, rsi
0x180016251  cmp     rbx, [rax+rbp]
0x180016255  jnz     short loc_18001627B
0x180016257  mov     r8, rbp
0x18001625a  mov     rax, [rdi+28h]
0x18001625e  mov     [r8+rax], rcx
0x180016262  test    rdx, rdx
0x180016265  jz      short loc_18001627B
0x180016267  mov     rax, [rdi+28h]
0x18001626b  dec     rdx
0x18001626e  mov     r8, rdx
0x180016271  shl     r8, 3
0x180016275  cmp     rbx, [r8+rax]
0x180016279  jz      short loc_18001625A
0x18001627b  mov     rax, [rdi+10h]
0x18001627f  mov     rdx, [rbx+8]
0x180016283  mov     [rdx], rcx
0x180016286  mov     rdx, [rcx+8]
0x18001628a  mov     [rdx], rax
0x18001628d  mov     rdx, [rax+8]
0x180016291  mov     [rdx], rbx
0x180016294  mov     r8, [rax+8]
0x180016298  mov     rdx, [rcx+8]
0x18001629c  mov     [rax+8], rdx
0x1800162a0  mov     rax, [rbx+8]
0x1800162a4  mov     [rcx+8], rax
0x1800162a8  mov     [rbx+8], r8
0x1800162ac  mov     r8, [rdi+10h]
0x1800162b0  mov     rdx, [rdi+48h]
0x1800162b4  mov     rax, [rdi+28h]
0x1800162b8  mov     rbx, [r8+8]
0x1800162bc  mov     [rax+rdx*8+8], r8
0x1800162c1  mov     rdx, [rdi+48h]
0x1800162c5  jmp     short loc_1800162DC
0x1800162c7  mov     r8, [rdi+28h]
0x1800162cb  mov     rax, [rdi+10h]
0x1800162cf  cmp     [r8+rdx*8], rax
0x1800162d3  jnz     short loc_1800162E1
0x1800162d5  mov     [r8+rdx*8], rbx
0x1800162d9  dec     rdx
0x1800162dc  cmp     rsi, rdx
0x1800162df  jb      short loc_1800162C7
0x1800162e1  cmp     rcx, [rdi+10h]
0x1800162e5  jz      short loc_1800162F9
0x1800162e7  mov     rbx, rcx
0x1800162ea  mov     rax, [rdi+28h]
0x1800162ee  cmp     rbx, [rax+rbp+8]
0x1800162f3  jnz     loc_180016227
0x1800162f9  inc     qword ptr [rdi+48h]
0x1800162fd  mov     rdx, [r15]
0x180016300  mov     rbx, [rdi+40h]
0x180016304  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180016309  mov     rsi, rax
0x18001630c  and     rsi, rbx
0x18001630f  cmp     [rdi+48h], rsi
0x180016313  ja      short loc_180016322
0x180016315  shr     rbx, 1
0x180016318  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001631c  sub     rax, rbx
0x18001631f  add     rsi, rax
0x180016322  mov     rax, [rdi+28h]
0x180016326  mov     rbx, [rax+rsi*8+8]
0x18001632b  jmp     short loc_180016346
0x18001632d  mov     rbx, [rbx+8]
0x180016331  mov     rcx, [r15]; String1
0x180016334  mov     rdx, [rbx+10h]; String2
0x180016338  call    cs:__imp__wcsicmp
0x18001633e  test    eax, eax
0x180016340  jns     short loc_180016361
0x180016342  mov     rax, [rdi+28h]
0x180016346  cmp     rbx, [rax+rsi*8]
0x18001634a  jnz     short loc_18001632D
0x18001634c  lea     rcx, [rdi+8]
0x180016350  mov     r8, r15
0x180016353  mov     rdx, rbx
0x180016356  call    ?_Insert@?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAAXViterator@12@AEBQEBG@Z; std::list<ushort const *>::_Insert(std::list<ushort const *>::iterator,ushort const * const &)
0x18001635b  mov     rax, [rbx+8]
0x18001635f  jmp     short loc_180016390
0x180016361  mov     rdx, [r15]; String2
0x180016364  mov     rcx, [rbx+10h]; String1
0x180016368  call    cs:__imp__wcsicmp
0x18001636e  test    eax, eax
0x180016370  jns     short loc_180016377
0x180016372  mov     rbx, [rbx]
0x180016375  jmp     short loc_18001634C
0x180016377  mov     [r14], rbx
0x18001637a  mov     [r14+8], r12b
0x18001637e  jmp     short loc_1800163A2
0x180016380  mov     rcx, [rdi+28h]
0x180016384  mov     [rcx+rsi*8], rax
0x180016388  test    rsi, rsi
0x18001638b  jz      short loc_18001639A
0x18001638d  dec     rsi
0x180016390  mov     rcx, [rdi+28h]
0x180016394  cmp     rbx, [rcx+rsi*8]
0x180016398  jz      short loc_180016380
0x18001639a  mov     [r14], rax
0x18001639d  mov     byte ptr [r14+8], 1
0x1800163a2  mov     rax, r14
0x1800163a5  mov     rcx, [rsp+68h+var_40]
0x1800163aa  xor     rcx, rsp; StackCookie
0x1800163ad  call    __security_check_cookie
0x1800163b2  add     rsp, 30h
0x1800163b6  pop     r15
0x1800163b8  pop     r14
0x1800163ba  pop     r12
0x1800163bc  pop     rdi
0x1800163bd  pop     rsi
0x1800163be  pop     rbp
0x1800163bf  pop     rbx
0x1800163c0  retn
```
