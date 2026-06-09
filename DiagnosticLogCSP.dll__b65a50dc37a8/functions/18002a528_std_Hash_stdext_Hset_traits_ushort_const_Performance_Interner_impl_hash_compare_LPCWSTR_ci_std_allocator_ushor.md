# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Rehash_for_1(void)

- ea: `0x18002a528`
- end: `0x18002a761`
- name: `?_Rehash_for_1@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002a768`

## callees

- `0x1800025f0`
- `0x1800282b4`
- `0x1800283f0`
- `0x18002a3fc`
- `0x18002a528`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a681`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a6aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a681`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002a6aa`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002a5f1`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002a5f1`

## pseudocode

```c
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v2; // sf
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  _QWORD *v12; // r12
  unsigned __int64 v13; // rcx
  __int64 v14; // rdi
  _QWORD *v15; // rcx
  _QWORD *v16; // rbx
  _QWORD *v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rbp
  __int64 v20; // r14
  _QWORD *v21; // rsi
  _QWORD *v22; // r8
  _QWORD *v23; // r8
  _QWORD *v24; // rdx
  _QWORD *v25; // rax
  _QWORD *v26; // rdx
  _QWORD *v27; // rax
  _QWORD *v28; // r8
  _QWORD *v29; // rdx
  _QWORD *v30; // rax
  __int64 v32; // [rsp+70h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v2 = v1 + 1 < 0;
  v3 = v1 + 1;
  v4 = *(_QWORD *)(a1 + 56);
  if ( v2 )
    v6 = (float)(int)(v3 & 1 | (v3 >> 1)) + (float)(int)(v3 & 1 | (v3 >> 1));
  else
    v6 = (float)(int)v3;
  v7 = o_ceilf_0(v6 / *(float *)a1);
  v8 = 0;
  if ( v7 >= 9.223372e18 )
  {
    v7 = v7 - 9.223372e18;
    if ( v7 < 9.223372e18 )
      v8 = 0x8000000000000000uLL;
  }
  v9 = v8 + (unsigned int)(int)v7;
  v10 = 8;
  if ( v9 > 8 )
    v10 = v9;
  if ( v4 < v10 )
  {
    if ( v4 >= 0x200 || (v4 *= 8LL, v4 < v10) )
      v4 = v10;
  }
  LODWORD(v32) = 0;
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v4 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = *(_QWORD **)(a1 + 8);
  LODWORD(v32) = 0;
  _BitScanReverse64(&v13, (v4 - 1) | 1);
  v14 = 1LL << ((unsigned __int8)v13 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>::_Assign_grow(
    a1 + 24,
    2 * v14,
    v12);
  *(_QWORD *)(a1 + 56) = v14;
  *(_QWORD *)(a1 + 48) = v14 - 1;
  v16 = **(_QWORD ***)(a1 + 8);
  v17 = v16;
  while ( v16 != v12 )
  {
    v17 = (_QWORD *)*v17;
    v18 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(v15, v16[2]);
    v19 = *(_QWORD *)(a1 + 24);
    v20 = 2 * (v18 & *(_QWORD *)(a1 + 48));
    if ( *(_QWORD **)(v19 + 16 * (v18 & *(_QWORD *)(a1 + 48))) == v12 )
    {
      *(_QWORD *)(v19 + 16 * (v18 & *(_QWORD *)(a1 + 48))) = v16;
LABEL_26:
      *(_QWORD *)(v19 + 8 * v20 + 8) = v16;
      goto LABEL_27;
    }
    v21 = *(_QWORD **)(v19 + 16 * (v18 & *(_QWORD *)(a1 + 48)) + 8);
    if ( (int)_o__wcsicmp(v16[2], v21[2]) >= 0 )
    {
      v28 = (_QWORD *)*v21;
      if ( (_QWORD *)*v21 != v16 )
      {
        v29 = (_QWORD *)v16[1];
        *v29 = v17;
        v15 = (_QWORD *)v17[1];
        *v15 = v28;
        v30 = (_QWORD *)v28[1];
        *v30 = v16;
        v28[1] = v15;
        v17[1] = v29;
        v16[1] = v30;
      }
      goto LABEL_26;
    }
    while ( 1 )
    {
      v22 = v21 + 1;
      if ( *(_QWORD **)(v19 + 8 * v20) == v21 )
        break;
      v21 = (_QWORD *)*v22;
      if ( (int)_o__wcsicmp(v16[2], *(_QWORD *)(*v22 + 16LL)) >= 0 )
      {
        v23 = (_QWORD *)*v21;
        v24 = (_QWORD *)v16[1];
        *v24 = v17;
        v15 = (_QWORD *)v17[1];
        *v15 = v23;
        v25 = (_QWORD *)v23[1];
        *v25 = v16;
        v23[1] = v15;
        v17[1] = v24;
        v16[1] = v25;
        goto LABEL_27;
      }
    }
    v26 = (_QWORD *)v16[1];
    *v26 = v17;
    v27 = (_QWORD *)v17[1];
    *v27 = v21;
    v15 = (_QWORD *)*v22;
    *v15 = v16;
    *v22 = v27;
    v17[1] = v26;
    v16[1] = v15;
    *(_QWORD *)(v19 + 8 * v20) = v16;
LABEL_27:
    v16 = v17;
  }
  v32 = 0;
  return std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Clear_guard::~_Clear_guard(&v32);
}

```

## disassembly

```asm
0x18002a528  push    rbx
0x18002a52a  push    rbp
0x18002a52b  push    rsi
0x18002a52c  push    rdi
0x18002a52d  push    r12
0x18002a52f  push    r13
0x18002a531  push    r14
0x18002a533  push    r15
0x18002a535  sub     rsp, 28h
0x18002a539  mov     rdx, [rcx+10h]
0x18002a53d  mov     edi, 1
0x18002a542  add     rdx, rdi
0x18002a545  mov     rbx, [rcx+38h]
0x18002a549  mov     r15, rcx
0x18002a54c  xorps   xmm0, xmm0
0x18002a54f  js      short loc_18002A558
0x18002a551  cvtsi2ss xmm0, rdx
0x18002a556  jmp     short loc_18002A56D
0x18002a558  mov     rax, rdx
0x18002a55b  and     rdx, rdi
0x18002a55e  shr     rax, 1
0x18002a561  or      rax, rdx
0x18002a564  cvtsi2ss xmm0, rax
0x18002a569  addss   xmm0, xmm0
0x18002a56d  divss   xmm0, dword ptr [rcx]; X
0x18002a571  call    _o_ceilf_0
0x18002a576  movss   xmm1, cs:__real@5f000000
0x18002a57e  xor     ecx, ecx
0x18002a580  comiss  xmm0, xmm1
0x18002a583  jb      short loc_18002A59B
0x18002a585  subss   xmm0, xmm1
0x18002a589  comiss  xmm0, xmm1
0x18002a58c  jnb     short loc_18002A59B
0x18002a58e  mov     rax, 8000000000000000h
0x18002a598  mov     rcx, rax
0x18002a59b  cvttss2si rax, xmm0
0x18002a5a0  add     rax, rcx
0x18002a5a3  mov     ecx, 8
0x18002a5a8  cmp     rax, rcx
0x18002a5ab  cmova   rcx, rax
0x18002a5af  cmp     rbx, rcx
0x18002a5b2  jnb     short loc_18002A5C9
0x18002a5b4  cmp     rbx, 200h
0x18002a5bb  jnb     short loc_18002A5C6
0x18002a5bd  shl     rbx, 3
0x18002a5c1  cmp     rbx, rcx
0x18002a5c4  jnb     short loc_18002A5C9
0x18002a5c6  mov     rbx, rcx
0x18002a5c9  mov     rax, 0FFFFFFFFFFFFFFFh
0x18002a5d3  mov     dword ptr [rsp+68h+arg_0], 0
0x18002a5db  bsr     rcx, rax
0x18002a5df  mov     rax, rdi
0x18002a5e2  shl     rax, cl
0x18002a5e5  cmp     rbx, rax
0x18002a5e8  jbe     short loc_18002A5FE
0x18002a5ea  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x18002a5f1  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002a5fe  mov     r12, [r15+8]
0x18002a602  lea     rax, [rbx-1]
0x18002a606  or      rax, rdi
0x18002a609  mov     dword ptr [rsp+68h+arg_0], 0
0x18002a611  bsr     rcx, rax
0x18002a615  mov     r8, r12
0x18002a618  inc     ecx
0x18002a61a  shl     rdi, cl
0x18002a61d  lea     rcx, [r15+18h]
0x18002a621  lea     rdx, [rdi+rdi]
0x18002a625  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x18002a62a  mov     [r15+38h], rdi
0x18002a62e  lea     rax, [rdi-1]
0x18002a632  mov     [r15+30h], rax
0x18002a636  mov     rbx, [r15+8]
0x18002a63a  mov     rbx, [rbx]
0x18002a63d  mov     rdi, rbx
0x18002a640  cmp     rbx, r12
0x18002a643  jz      loc_18002A73C
0x18002a649  mov     rdx, [rbx+10h]
0x18002a64d  mov     rdi, [rdi]
0x18002a650  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18002a655  mov     r14, [r15+30h]
0x18002a659  mov     rbp, [r15+18h]
0x18002a65d  and     r14, rax
0x18002a660  add     r14, r14
0x18002a663  cmp     [rbp+r14*8+0], r12
0x18002a668  jnz     short loc_18002A674
0x18002a66a  mov     [rbp+r14*8+0], rbx
0x18002a66f  jmp     loc_18002A72F
0x18002a674  mov     rsi, [rbp+r14*8+8]
0x18002a679  mov     rcx, [rbx+10h]
0x18002a67d  mov     rdx, [rsi+10h]
0x18002a681  call    cs:__imp__o__wcsicmp
0x18002a688  nop     dword ptr [rax+rax+00h]
0x18002a68d  test    eax, eax
0x18002a68f  jns     short loc_18002A706
0x18002a691  mov     rax, rsi
0x18002a694  lea     r8, [rsi+8]
0x18002a698  cmp     [rbp+r14*8+0], rax
0x18002a69d  jz      short loc_18002A6E0
0x18002a69f  mov     rsi, [r8]
0x18002a6a2  mov     rcx, [rbx+10h]
0x18002a6a6  mov     rdx, [rsi+10h]
0x18002a6aa  call    cs:__imp__o__wcsicmp
0x18002a6b1  nop     dword ptr [rax+rax+00h]
0x18002a6b6  test    eax, eax
0x18002a6b8  js      short loc_18002A691
0x18002a6ba  mov     r8, [rsi]
0x18002a6bd  mov     rdx, [rbx+8]
0x18002a6c1  mov     [rdx], rdi
0x18002a6c4  mov     rcx, [rdi+8]
0x18002a6c8  mov     [rcx], r8
0x18002a6cb  mov     rax, [r8+8]
0x18002a6cf  mov     [rax], rbx
0x18002a6d2  mov     [r8+8], rcx
0x18002a6d6  mov     [rdi+8], rdx
0x18002a6da  mov     [rbx+8], rax
0x18002a6de  jmp     short loc_18002A734
0x18002a6e0  mov     rdx, [rbx+8]
0x18002a6e4  mov     [rdx], rdi
0x18002a6e7  mov     rax, [rdi+8]
0x18002a6eb  mov     [rax], rsi
0x18002a6ee  mov     rcx, [r8]
0x18002a6f1  mov     [rcx], rbx
0x18002a6f4  mov     [r8], rax
0x18002a6f7  mov     [rdi+8], rdx
0x18002a6fb  mov     [rbx+8], rcx
0x18002a6ff  mov     [rbp+r14*8+0], rbx
0x18002a704  jmp     short loc_18002A734
0x18002a706  mov     r8, [rsi]
0x18002a709  cmp     r8, rbx
0x18002a70c  jz      short loc_18002A72F
0x18002a70e  mov     rdx, [rbx+8]
0x18002a712  mov     [rdx], rdi
0x18002a715  mov     rcx, [rdi+8]
0x18002a719  mov     [rcx], r8
0x18002a71c  mov     rax, [r8+8]
0x18002a720  mov     [rax], rbx
0x18002a723  mov     [r8+8], rcx
0x18002a727  mov     [rdi+8], rdx
0x18002a72b  mov     [rbx+8], rax
0x18002a72f  mov     [rbp+r14*8+8], rbx
0x18002a734  mov     rbx, rdi
0x18002a737  jmp     loc_18002A640
0x18002a73c  lea     rcx, [rsp+68h+arg_0]
0x18002a741  mov     [rsp+68h+arg_0], 0
0x18002a74a  call    ??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)
0x18002a74f  add     rsp, 28h
0x18002a753  pop     r15
0x18002a755  pop     r14
0x18002a757  pop     r13
0x18002a759  pop     r12
0x18002a75b  pop     rdi
0x18002a75c  pop     rsi
0x18002a75d  pop     rbp
0x18002a75e  pop     rbx
0x18002a75f  retn
```
