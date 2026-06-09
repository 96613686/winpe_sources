# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Rehash_for_1(void)

- ea: `0x180029350`
- end: `0x180029576`
- name: `?_Rehash_for_1@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ`
- size: `550`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002957c`

## callees

- `0x1800025c0`
- `0x180027130`
- `0x180027258`
- `0x180029224`
- `0x180029350`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800294a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800294c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800294a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800294c6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180029419`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180029419`

## pseudocode

```c
void __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Rehash_for_1(
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
  unsigned __int64 *v31; // [rsp+70h] [rbp+8h] BYREF

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
  LODWORD(v31) = 0;
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v4 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = *(_QWORD **)(a1 + 8);
  LODWORD(v31) = 0;
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
    v18 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()((__int64)v15, (unsigned __int16 *)v16[2]);
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
  v31 = 0;
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Clear_guard::~_Clear_guard(&v31);
}

```

## disassembly

```asm
0x180029350  push    rbx
0x180029352  push    rbp
0x180029353  push    rsi
0x180029354  push    rdi
0x180029355  push    r12
0x180029357  push    r13
0x180029359  push    r14
0x18002935b  push    r15
0x18002935d  sub     rsp, 28h
0x180029361  mov     rdx, [rcx+10h]
0x180029365  mov     edi, 1
0x18002936a  add     rdx, rdi
0x18002936d  mov     rbx, [rcx+38h]
0x180029371  mov     r15, rcx
0x180029374  xorps   xmm0, xmm0
0x180029377  js      short loc_180029380
0x180029379  cvtsi2ss xmm0, rdx
0x18002937e  jmp     short loc_180029395
0x180029380  mov     rax, rdx
0x180029383  and     rdx, rdi
0x180029386  shr     rax, 1
0x180029389  or      rax, rdx
0x18002938c  cvtsi2ss xmm0, rax
0x180029391  addss   xmm0, xmm0
0x180029395  divss   xmm0, dword ptr [rcx]; X
0x180029399  call    _o_ceilf_0
0x18002939e  movss   xmm1, cs:__real@5f000000
0x1800293a6  xor     ecx, ecx
0x1800293a8  comiss  xmm0, xmm1
0x1800293ab  jb      short loc_1800293C3
0x1800293ad  subss   xmm0, xmm1
0x1800293b1  comiss  xmm0, xmm1
0x1800293b4  jnb     short loc_1800293C3
0x1800293b6  mov     rax, 8000000000000000h
0x1800293c0  mov     rcx, rax
0x1800293c3  cvttss2si rax, xmm0
0x1800293c8  add     rax, rcx
0x1800293cb  mov     ecx, 8
0x1800293d0  cmp     rax, rcx
0x1800293d3  cmova   rcx, rax
0x1800293d7  cmp     rbx, rcx
0x1800293da  jnb     short loc_1800293F1
0x1800293dc  cmp     rbx, 200h
0x1800293e3  jnb     short loc_1800293EE
0x1800293e5  shl     rbx, 3
0x1800293e9  cmp     rbx, rcx
0x1800293ec  jnb     short loc_1800293F1
0x1800293ee  mov     rbx, rcx
0x1800293f1  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800293fb  mov     dword ptr [rsp+68h+arg_0], 0
0x180029403  bsr     rcx, rax
0x180029407  mov     rax, rdi
0x18002940a  shl     rax, cl
0x18002940d  cmp     rbx, rax
0x180029410  jbe     short loc_180029420
0x180029412  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180029419  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180029420  mov     r12, [r15+8]
0x180029424  lea     rax, [rbx-1]
0x180029428  or      rax, rdi
0x18002942b  mov     dword ptr [rsp+68h+arg_0], 0
0x180029433  bsr     rcx, rax
0x180029437  mov     r8, r12
0x18002943a  inc     ecx
0x18002943c  shl     rdi, cl
0x18002943f  lea     rcx, [r15+18h]
0x180029443  lea     rdx, [rdi+rdi]
0x180029447  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x18002944c  mov     [r15+38h], rdi
0x180029450  lea     rax, [rdi-1]
0x180029454  mov     [r15+30h], rax
0x180029458  mov     rbx, [r15+8]
0x18002945c  mov     rbx, [rbx]
0x18002945f  mov     rdi, rbx
0x180029462  cmp     rbx, r12
0x180029465  jz      loc_180029552
0x18002946b  mov     rdx, [rbx+10h]
0x18002946f  mov     rdi, [rdi]
0x180029472  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180029477  mov     r14, [r15+30h]
0x18002947b  mov     rbp, [r15+18h]
0x18002947f  and     r14, rax
0x180029482  add     r14, r14
0x180029485  cmp     [rbp+r14*8+0], r12
0x18002948a  jnz     short loc_180029496
0x18002948c  mov     [rbp+r14*8+0], rbx
0x180029491  jmp     loc_180029545
0x180029496  mov     rsi, [rbp+r14*8+8]
0x18002949b  mov     rcx, [rbx+10h]
0x18002949f  mov     rdx, [rsi+10h]
0x1800294a3  call    cs:__imp__o__wcsicmp
0x1800294a9  test    eax, eax
0x1800294ab  jns     short loc_18002951C
0x1800294ad  mov     rax, rsi
0x1800294b0  lea     r8, [rsi+8]
0x1800294b4  cmp     [rbp+r14*8+0], rax
0x1800294b9  jz      short loc_1800294F6
0x1800294bb  mov     rsi, [r8]
0x1800294be  mov     rcx, [rbx+10h]
0x1800294c2  mov     rdx, [rsi+10h]
0x1800294c6  call    cs:__imp__o__wcsicmp
0x1800294cc  test    eax, eax
0x1800294ce  js      short loc_1800294AD
0x1800294d0  mov     r8, [rsi]
0x1800294d3  mov     rdx, [rbx+8]
0x1800294d7  mov     [rdx], rdi
0x1800294da  mov     rcx, [rdi+8]
0x1800294de  mov     [rcx], r8
0x1800294e1  mov     rax, [r8+8]
0x1800294e5  mov     [rax], rbx
0x1800294e8  mov     [r8+8], rcx
0x1800294ec  mov     [rdi+8], rdx
0x1800294f0  mov     [rbx+8], rax
0x1800294f4  jmp     short loc_18002954A
0x1800294f6  mov     rdx, [rbx+8]
0x1800294fa  mov     [rdx], rdi
0x1800294fd  mov     rax, [rdi+8]
0x180029501  mov     [rax], rsi
0x180029504  mov     rcx, [r8]
0x180029507  mov     [rcx], rbx
0x18002950a  mov     [r8], rax
0x18002950d  mov     [rdi+8], rdx
0x180029511  mov     [rbx+8], rcx
0x180029515  mov     [rbp+r14*8+0], rbx
0x18002951a  jmp     short loc_18002954A
0x18002951c  mov     r8, [rsi]
0x18002951f  cmp     r8, rbx
0x180029522  jz      short loc_180029545
0x180029524  mov     rdx, [rbx+8]
0x180029528  mov     [rdx], rdi
0x18002952b  mov     rcx, [rdi+8]
0x18002952f  mov     [rcx], r8
0x180029532  mov     rax, [r8+8]
0x180029536  mov     [rax], rbx
0x180029539  mov     [r8+8], rcx
0x18002953d  mov     [rdi+8], rdx
0x180029541  mov     [rbx+8], rax
0x180029545  mov     [rbp+r14*8+8], rbx
0x18002954a  mov     rbx, rdi
0x18002954d  jmp     loc_180029462
0x180029552  lea     rcx, [rsp+68h+arg_0]
0x180029557  mov     [rsp+68h+arg_0], 0
0x180029560  call    ??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)
0x180029565  add     rsp, 28h
0x180029569  pop     r15
0x18002956b  pop     r14
0x18002956d  pop     r13
0x18002956f  pop     r12
0x180029571  pop     rdi
0x180029572  pop     rsi
0x180029573  pop     rbp
0x180029574  pop     rbx
0x180029575  retn
```
