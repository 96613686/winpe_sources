# std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature,std::allocator<CbsLanguageFeature>>>>,0>>::_Rehash_for_1(void)

- ea: `0x1800211f0`
- end: `0x180021431`
- name: `?_Rehash_for_1@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@IEAAXXZ`
- size: `577`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000f808`
- `0x18000fd14`

## callees

- `0x180003520`
- `0x1800040c4`
- `0x1800135d4`
- `0x18001dea4`
- `0x1800211f0`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800212bf`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800212bf`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Rehash_for_1(
        __int64 a1)
{
  __int64 v1; // rdx
  bool v3; // sf
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rbx
  float v6; // xmm0_4
  float v7; // xmm0_4
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rax
  _QWORD *v13; // rbx
  unsigned __int64 v14; // rcx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  _QWORD *v17; // rcx
  __int64 v18; // r8
  unsigned __int64 i; // r9
  __int64 v20; // rdx
  __int64 v21; // r11
  __int64 v22; // r10
  __int64 *v23; // rdx
  int v24; // r8d
  _QWORD *v25; // rdi
  _QWORD *v26; // r9
  _QWORD *v27; // r8
  _QWORD *v28; // rdx
  __int64 **v29; // rdi
  __int64 v30; // r10
  _QWORD *v31; // r9
  _QWORD *v32; // r8
  _QWORD *v33; // rdx
  _QWORD *v34; // r9
  __int64 **v35; // r8
  __int64 *v36; // rdx
  unsigned __int64 *v37; // [rsp+20h] [rbp-38h] BYREF

  v1 = *(_QWORD *)(a1 + 16);
  v3 = v1 + 1 < 0;
  v4 = v1 + 1;
  v5 = *(_QWORD *)(a1 + 56);
  if ( v3 )
    v6 = (float)(int)(v4 & 1 | (v4 >> 1)) + (float)(int)(v4 & 1 | (v4 >> 1));
  else
    v6 = (float)(int)v4;
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
  if ( v5 < v10 )
  {
    if ( v5 >= 0x200 || (v5 *= 8LL, v5 < v10) )
      v5 = v10;
  }
  LODWORD(v37) = 0;
  _BitScanReverse64(&v11, 0xFFFFFFFFFFFFFFFuLL);
  if ( v5 > 1LL << v11 )
    std::_Xlength_error("invalid hash bucket count");
  v12 = v5 - 1;
  LODWORD(v37) = 0;
  v13 = *(_QWORD **)(a1 + 8);
  _BitScanReverse64(&v14, v12 | 1);
  v15 = 1LL << ((unsigned __int8)v14 + 1);
  std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::_Assign_grow(
    a1 + 24,
    2 * v15,
    v13);
  *(_QWORD *)(a1 + 56) = v15;
  *(_QWORD *)(a1 + 48) = v15 - 1;
  v16 = **(_QWORD ***)(a1 + 8);
  v17 = v16;
  while ( v16 != v13 )
  {
    v17 = (_QWORD *)*v17;
    v18 = 0xCBF29CE484222325uLL;
    for ( i = 0; i < 4; ++i )
    {
      v20 = *((unsigned __int8 *)v16 + i + 16);
      v18 = 0x100000001B3LL * (v20 ^ v18);
    }
    v21 = *(_QWORD *)(a1 + 24);
    v22 = 2 * (v18 & *(_QWORD *)(a1 + 48));
    if ( *(_QWORD **)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48))) == v13 )
    {
      *(_QWORD *)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48))) = v16;
LABEL_21:
      *(_QWORD *)(v21 + 8 * v22 + 8) = v16;
      goto LABEL_29;
    }
    v23 = *(__int64 **)(v21 + 16 * (v18 & *(_QWORD *)(a1 + 48)) + 8);
    v24 = *((_DWORD *)v16 + 4);
    if ( v24 == *((_DWORD *)v23 + 4) )
    {
      v25 = (_QWORD *)*v23;
      if ( (_QWORD *)*v23 != v16 )
      {
        v26 = (_QWORD *)v16[1];
        *v26 = v17;
        v27 = (_QWORD *)v17[1];
        *v27 = v25;
        v28 = (_QWORD *)v25[1];
        *v28 = v16;
        v25[1] = v27;
        v17[1] = v26;
        v16[1] = v28;
      }
      goto LABEL_21;
    }
    while ( 1 )
    {
      v29 = (__int64 **)(v23 + 1);
      if ( *(__int64 **)(v21 + 8 * v22) == v23 )
        break;
      v23 = *v29;
      if ( v24 == *((_DWORD *)*v29 + 4) )
      {
        v30 = *v23;
        v31 = (_QWORD *)v16[1];
        *v31 = v17;
        v32 = (_QWORD *)v17[1];
        *v32 = v30;
        v33 = *(_QWORD **)(v30 + 8);
        *v33 = v16;
        *(_QWORD *)(v30 + 8) = v32;
        v17[1] = v31;
        v16[1] = v33;
        goto LABEL_29;
      }
    }
    v34 = (_QWORD *)v16[1];
    *v34 = v17;
    v35 = (__int64 **)v17[1];
    *v35 = v23;
    v36 = *v29;
    *v36 = (__int64)v16;
    *v29 = (__int64 *)v35;
    v17[1] = v34;
    v16[1] = v36;
    *(_QWORD *)(v21 + 8 * v22) = v16;
LABEL_29:
    v16 = v17;
  }
  v37 = 0;
  std::_Hash<std::_Umap_traits<enum PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<enum PayloadType,std::hash<enum PayloadType>,std::equal_to<enum PayloadType>>,std::allocator<std::pair<enum PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Clear_guard::~_Clear_guard(&v37);
}

```

## disassembly

```asm
0x1800211f0  push    rbx
0x1800211f2  push    rsi
0x1800211f3  push    rdi
0x1800211f4  push    r14
0x1800211f6  sub     rsp, 38h
0x1800211fa  mov     rax, cs:__security_cookie
0x180021201  xor     rax, rsp
0x180021204  mov     [rsp+58h+var_30], rax
0x180021209  mov     rdx, [rcx+10h]
0x18002120d  mov     rsi, rcx
0x180021210  add     rdx, 1
0x180021214  mov     rbx, [rcx+38h]
0x180021218  xorps   xmm0, xmm0
0x18002121b  js      short loc_180021224
0x18002121d  cvtsi2ss xmm0, rdx
0x180021222  jmp     short loc_180021239
0x180021224  mov     rax, rdx
0x180021227  and     edx, 1
0x18002122a  shr     rax, 1
0x18002122d  or      rax, rdx
0x180021230  cvtsi2ss xmm0, rax
0x180021235  addss   xmm0, xmm0
0x180021239  divss   xmm0, dword ptr [rcx]; X
0x18002123d  call    _o_ceilf_0
0x180021242  movss   xmm1, cs:__real@5f000000
0x18002124a  xor     ecx, ecx
0x18002124c  comiss  xmm0, xmm1
0x18002124f  jb      short loc_180021267
0x180021251  subss   xmm0, xmm1
0x180021255  comiss  xmm0, xmm1
0x180021258  jnb     short loc_180021267
0x18002125a  mov     rax, 8000000000000000h
0x180021264  mov     rcx, rax
0x180021267  cvttss2si rax, xmm0
0x18002126c  add     rax, rcx
0x18002126f  mov     ecx, 8
0x180021274  cmp     rax, rcx
0x180021277  cmova   rcx, rax
0x18002127b  cmp     rbx, rcx
0x18002127e  jnb     short loc_180021295
0x180021280  cmp     rbx, 200h
0x180021287  jnb     short loc_180021292
0x180021289  shl     rbx, 3
0x18002128d  cmp     rbx, rcx
0x180021290  jnb     short loc_180021295
0x180021292  mov     rbx, rcx
0x180021295  mov     rax, 0FFFFFFFFFFFFFFFh
0x18002129f  mov     dword ptr [rsp+58h+var_38], 0
0x1800212a7  bsr     rcx, rax
0x1800212ab  mov     eax, 1
0x1800212b0  shl     rax, cl
0x1800212b3  cmp     rbx, rax
0x1800212b6  jbe     short loc_1800212C6
0x1800212b8  lea     rcx, aInvalidHashBuc; "invalid hash bucket count"
0x1800212bf  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800212c6  lea     rax, [rbx-1]
0x1800212ca  mov     dword ptr [rsp+58h+var_38], 0
0x1800212d2  mov     rbx, [rsi+8]
0x1800212d6  or      rax, 1
0x1800212da  bsr     rcx, rax
0x1800212de  mov     edi, 1
0x1800212e3  mov     r8, rbx
0x1800212e6  inc     ecx
0x1800212e8  shl     rdi, cl
0x1800212eb  lea     rcx, [rsi+18h]
0x1800212ef  lea     rdx, [rdi+rdi]
0x1800212f3  call    ?_Assign_grow@?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAX_KV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@std@@@std@@@2@@Z; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>>>::_Assign_grow(unsigned __int64,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>>>)
0x1800212f8  lea     rax, [rdi-1]
0x1800212fc  mov     [rsi+38h], rdi
0x180021300  mov     [rsi+30h], rax
0x180021304  mov     rax, [rsi+8]
0x180021308  mov     rax, [rax]
0x18002130b  mov     rcx, rax
0x18002130e  cmp     rax, rbx
0x180021311  jz      loc_180021407
0x180021317  mov     rcx, [rcx]
0x18002131a  mov     r8, 0CBF29CE484222325h
0x180021324  xor     r9d, r9d
0x180021327  movzx   edx, byte ptr [rax+r9+10h]
0x18002132d  mov     r10, 100000001B3h
0x180021337  xor     r8, rdx
0x18002133a  inc     r9
0x18002133d  imul    r8, r10
0x180021341  cmp     r9, 4
0x180021345  jb      short loc_180021327
0x180021347  mov     r10, [rsi+30h]
0x18002134b  mov     r11, [rsi+18h]
0x18002134f  and     r10, r8
0x180021352  add     r10, r10
0x180021355  cmp     [r11+r10*8], rbx
0x180021359  jnz     short loc_180021369
0x18002135b  mov     [r11+r10*8], rax
0x18002135f  mov     [r11+r10*8+8], rax
0x180021364  jmp     loc_1800213FF
0x180021369  mov     rdx, [r11+r10*8+8]
0x18002136e  mov     r8d, [rax+10h]
0x180021372  cmp     r8d, [rdx+10h]
0x180021376  jnz     short loc_1800213A3
0x180021378  mov     rdi, [rdx]
0x18002137b  cmp     rdi, rax
0x18002137e  jz      short loc_18002135F
0x180021380  mov     r9, [rax+8]
0x180021384  mov     [r9], rcx
0x180021387  mov     r8, [rcx+8]
0x18002138b  mov     [r8], rdi
0x18002138e  mov     rdx, [rdi+8]
0x180021392  mov     [rdx], rax
0x180021395  mov     [rdi+8], r8
0x180021399  mov     [rcx+8], r9
0x18002139d  mov     [rax+8], rdx
0x1800213a1  jmp     short loc_18002135F
0x1800213a3  lea     rdi, [rdx+8]
0x1800213a7  cmp     [r11+r10*8], rdx
0x1800213ab  jz      short loc_1800213DC
0x1800213ad  mov     rdx, [rdi]
0x1800213b0  cmp     r8d, [rdx+10h]
0x1800213b4  jnz     short loc_1800213A3
0x1800213b6  mov     r10, [rdx]
0x1800213b9  mov     r9, [rax+8]
0x1800213bd  mov     [r9], rcx
0x1800213c0  mov     r8, [rcx+8]
0x1800213c4  mov     [r8], r10
0x1800213c7  mov     rdx, [r10+8]
0x1800213cb  mov     [rdx], rax
0x1800213ce  mov     [r10+8], r8
0x1800213d2  mov     [rcx+8], r9
0x1800213d6  mov     [rax+8], rdx
0x1800213da  jmp     short loc_1800213FF
0x1800213dc  mov     r9, [rax+8]
0x1800213e0  mov     [r9], rcx
0x1800213e3  mov     r8, [rcx+8]
0x1800213e7  mov     [r8], rdx
0x1800213ea  mov     rdx, [rdi]
0x1800213ed  mov     [rdx], rax
0x1800213f0  mov     [rdi], r8
0x1800213f3  mov     [rcx+8], r9
0x1800213f7  mov     [rax+8], rdx
0x1800213fb  mov     [r11+r10*8], rax
0x1800213ff  mov     rax, rcx
0x180021402  jmp     loc_18002130E
0x180021407  lea     rcx, [rsp+58h+var_38]
0x18002140c  mov     [rsp+58h+var_38], 0
0x180021415  call    ??1_Clear_guard@?$_Hash@V?$_Umap_traits@W4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@V?$_Uhash_compare@W4PayloadType@@U?$hash@W4PayloadType@@@std@@U?$equal_to@W4PayloadType@@@3@@3@V?$allocator@U?$pair@$$CBW4PayloadType@@V?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<PayloadType,std::vector<CbsLanguageFeature>,std::_Uhash_compare<PayloadType,std::hash<PayloadType>,std::equal_to<PayloadType>>,std::allocator<std::pair<PayloadType const,std::vector<CbsLanguageFeature>>>,0>>::_Clear_guard::~_Clear_guard(void)
0x18002141a  mov     rcx, [rsp+58h+var_30]
0x18002141f  xor     rcx, rsp; StackCookie
0x180021422  call    __security_check_cookie
0x180021427  add     rsp, 38h
0x18002142b  pop     r14
0x18002142d  pop     rdi
0x18002142e  pop     rsi
0x18002142f  pop     rbx
0x180021430  retn
```
