# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Rehash_for_1(void)

- ea: `0x180018550`
- end: `0x180018776`
- name: `?_Rehash_for_1@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ`
- size: `550`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001877c`

## callees

- `0x1800023cc`
- `0x180016334`
- `0x18001645c`
- `0x180018424`
- `0x180018550`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800186a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800186c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800186a3`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800186c6`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018619`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180018619`

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
0x180018550  push    rbx
0x180018552  push    rbp
0x180018553  push    rsi
0x180018554  push    rdi
0x180018555  push    r12
0x180018557  push    r13
0x180018559  push    r14
0x18001855b  push    r15
0x18001855d  sub     rsp, 28h
0x180018561  mov     rdx, [rcx+10h]
0x180018565  mov     edi, 1
0x18001856a  add     rdx, rdi
0x18001856d  mov     rbx, [rcx+38h]
0x180018571  mov     r15, rcx
0x180018574  xorps   xmm0, xmm0
0x180018577  js      short loc_180018580
0x180018579  cvtsi2ss xmm0, rdx
0x18001857e  jmp     short loc_180018595
0x180018580  mov     rax, rdx
0x180018583  and     rdx, rdi
0x180018586  shr     rax, 1
0x180018589  or      rax, rdx
0x18001858c  cvtsi2ss xmm0, rax
0x180018591  addss   xmm0, xmm0
0x180018595  divss   xmm0, dword ptr [rcx]; X
0x180018599  call    _o_ceilf_0
0x18001859e  movss   xmm1, cs:__real@5f000000
0x1800185a6  xor     ecx, ecx
0x1800185a8  comiss  xmm0, xmm1
0x1800185ab  jb      short loc_1800185C3
0x1800185ad  subss   xmm0, xmm1
0x1800185b1  comiss  xmm0, xmm1
0x1800185b4  jnb     short loc_1800185C3
0x1800185b6  mov     rax, 8000000000000000h
0x1800185c0  mov     rcx, rax
0x1800185c3  cvttss2si rax, xmm0
0x1800185c8  add     rax, rcx
0x1800185cb  mov     ecx, 8
0x1800185d0  cmp     rax, rcx
0x1800185d3  cmova   rcx, rax
0x1800185d7  cmp     rbx, rcx
0x1800185da  jnb     short loc_1800185F1
0x1800185dc  cmp     rbx, 200h
0x1800185e3  jnb     short loc_1800185EE
0x1800185e5  shl     rbx, 3
0x1800185e9  cmp     rbx, rcx
0x1800185ec  jnb     short loc_1800185F1
0x1800185ee  mov     rbx, rcx
0x1800185f1  mov     rax, 0FFFFFFFFFFFFFFFh
0x1800185fb  mov     dword ptr [rsp+68h+arg_0], 0
0x180018603  bsr     rcx, rax
0x180018607  mov     rax, rdi
0x18001860a  shl     rax, cl
0x18001860d  cmp     rbx, rax
0x180018610  jbe     short loc_180018620
0x180018612  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x180018619  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180018620  mov     r12, [r15+8]
0x180018624  lea     rax, [rbx-1]
0x180018628  or      rax, rdi
0x18001862b  mov     dword ptr [rsp+68h+arg_0], 0
0x180018633  bsr     rcx, rax
0x180018637  mov     r8, r12
0x18001863a  inc     ecx
0x18001863c  shl     rdi, cl
0x18001863f  lea     rcx, [r15+18h]
0x180018643  lea     rdx, [rdi+rdi]
0x180018647  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>)
0x18001864c  mov     [r15+38h], rdi
0x180018650  lea     rax, [rdi-1]
0x180018654  mov     [r15+30h], rax
0x180018658  mov     rbx, [r15+8]
0x18001865c  mov     rbx, [rbx]
0x18001865f  mov     rdi, rbx
0x180018662  cmp     rbx, r12
0x180018665  jz      loc_180018752
0x18001866b  mov     rdx, [rbx+10h]
0x18001866f  mov     rdi, [rdi]
0x180018672  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180018677  mov     r14, [r15+30h]
0x18001867b  mov     rbp, [r15+18h]
0x18001867f  and     r14, rax
0x180018682  add     r14, r14
0x180018685  cmp     [rbp+r14*8+0], r12
0x18001868a  jnz     short loc_180018696
0x18001868c  mov     [rbp+r14*8+0], rbx
0x180018691  jmp     loc_180018745
0x180018696  mov     rsi, [rbp+r14*8+8]
0x18001869b  mov     rcx, [rbx+10h]
0x18001869f  mov     rdx, [rsi+10h]
0x1800186a3  call    cs:__imp__o__wcsicmp
0x1800186a9  test    eax, eax
0x1800186ab  jns     short loc_18001871C
0x1800186ad  mov     rax, rsi
0x1800186b0  lea     r8, [rsi+8]
0x1800186b4  cmp     [rbp+r14*8+0], rax
0x1800186b9  jz      short loc_1800186F6
0x1800186bb  mov     rsi, [r8]
0x1800186be  mov     rcx, [rbx+10h]
0x1800186c2  mov     rdx, [rsi+10h]
0x1800186c6  call    cs:__imp__o__wcsicmp
0x1800186cc  test    eax, eax
0x1800186ce  js      short loc_1800186AD
0x1800186d0  mov     r8, [rsi]
0x1800186d3  mov     rdx, [rbx+8]
0x1800186d7  mov     [rdx], rdi
0x1800186da  mov     rcx, [rdi+8]
0x1800186de  mov     [rcx], r8
0x1800186e1  mov     rax, [r8+8]
0x1800186e5  mov     [rax], rbx
0x1800186e8  mov     [r8+8], rcx
0x1800186ec  mov     [rdi+8], rdx
0x1800186f0  mov     [rbx+8], rax
0x1800186f4  jmp     short loc_18001874A
0x1800186f6  mov     rdx, [rbx+8]
0x1800186fa  mov     [rdx], rdi
0x1800186fd  mov     rax, [rdi+8]
0x180018701  mov     [rax], rsi
0x180018704  mov     rcx, [r8]
0x180018707  mov     [rcx], rbx
0x18001870a  mov     [r8], rax
0x18001870d  mov     [rdi+8], rdx
0x180018711  mov     [rbx+8], rcx
0x180018715  mov     [rbp+r14*8+0], rbx
0x18001871a  jmp     short loc_18001874A
0x18001871c  mov     r8, [rsi]
0x18001871f  cmp     r8, rbx
0x180018722  jz      short loc_180018745
0x180018724  mov     rdx, [rbx+8]
0x180018728  mov     [rdx], rdi
0x18001872b  mov     rcx, [rdi+8]
0x18001872f  mov     [rcx], r8
0x180018732  mov     rax, [r8+8]
0x180018736  mov     [rax], rbx
0x180018739  mov     [r8+8], rcx
0x18001873d  mov     [rdi+8], rdx
0x180018741  mov     [rbx+8], rax
0x180018745  mov     [rbp+r14*8+8], rbx
0x18001874a  mov     rbx, rdi
0x18001874d  jmp     loc_180018662
0x180018752  lea     rcx, [rsp+68h+arg_0]
0x180018757  mov     [rsp+68h+arg_0], 0
0x180018760  call    ??1_Clear_guard@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Clear_guard::~_Clear_guard(void)
0x180018765  add     rsp, 28h
0x180018769  pop     r15
0x18001876b  pop     r14
0x18001876d  pop     r13
0x18001876f  pop     r12
0x180018771  pop     rdi
0x180018772  pop     rsi
0x180018773  pop     rbp
0x180018774  pop     rbx
0x180018775  retn
```
