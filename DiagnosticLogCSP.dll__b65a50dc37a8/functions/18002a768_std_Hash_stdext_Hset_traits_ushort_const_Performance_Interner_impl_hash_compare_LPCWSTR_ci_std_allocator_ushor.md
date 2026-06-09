# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)

- ea: `0x18002a768`
- end: `0x18002a8fb`
- name: `?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@2@AEBQEBG@Z`
- size: `403`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180029af0`

## callees

- `0x180001bb4`
- `0x180027c0c`
- `0x1800283f0`
- `0x18002a528`
- `0x18002a768`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002a7cc`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x18002a7cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::insert(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v6; // r15
  char v7; // bp
  _QWORD *v8; // rbx
  __int64 v9; // rcx
  float v10; // xmm0_4
  __int64 v11; // rcx
  float v12; // xmm1_4
  __int64 v13; // rdx
  _QWORD *v14; // r8
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r9
  __int128 v19; // [rsp+20h] [rbp-68h] BYREF
  __int64 v20; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-50h]

  v6 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, *a3);
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
    a1,
    &v19,
    a3,
    v6);
  if ( !*((_QWORD *)&v19 + 1) )
  {
    if ( *(_QWORD *)(a1 + 16) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = a1 + 8;
    v21 = 0;
    v8 = operator new(0x18u);
    v21 = v8;
    v8[2] = *a3;
    v7 = 1;
    v9 = *(_QWORD *)(a1 + 16) + 1LL;
    if ( v9 < 0 )
      v10 = (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1))
          + (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = *(_QWORD *)(a1 + 56);
    if ( v11 < 0 )
      v12 = (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1))
          + (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1));
    else
      v12 = (float)(int)v11;
    if ( (float)(v10 / v12) > *(float *)a1 )
    {
      std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Rehash_for_1(a1);
      v19 = *(_OWORD *)std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
                         a1,
                         &v20,
                         v8 + 2,
                         v6);
    }
    v13 = v19;
    v14 = *(_QWORD **)(v19 + 8);
    ++*(_QWORD *)(a1 + 16);
    *v8 = v13;
    v8[1] = v14;
    *v14 = v8;
    *(_QWORD *)(v13 + 8) = v8;
    v15 = *(_QWORD *)(a1 + 24);
    v16 = 2 * (v6 & *(_QWORD *)(a1 + 48));
    v17 = *(_QWORD *)(v15 + 16 * (v6 & *(_QWORD *)(a1 + 48)));
    if ( v17 == *(_QWORD *)(a1 + 8) )
    {
      *(_QWORD *)(v15 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v8;
LABEL_18:
      *(_QWORD *)(v15 + 8 * v16 + 8) = v8;
      goto LABEL_19;
    }
    if ( v17 == v13 )
    {
      *(_QWORD *)(v15 + 16 * (v6 & *(_QWORD *)(a1 + 48))) = v8;
    }
    else if ( *(_QWORD **)(v15 + 16 * (v6 & *(_QWORD *)(a1 + 48)) + 8) == v14 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v8;
    goto LABEL_20;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v19 + 1);
  v7 = 0;
LABEL_20:
  *(_BYTE *)(a2 + 8) = v7;
  return a2;
}

```

## disassembly

```asm
0x18002a768  push    rbx
0x18002a76a  push    rbp
0x18002a76b  push    rsi
0x18002a76c  push    rdi
0x18002a76d  push    r12
0x18002a76f  push    r13
0x18002a771  push    r14
0x18002a773  push    r15
0x18002a775  sub     rsp, 48h
0x18002a779  mov     r14, r8
0x18002a77c  mov     rsi, rdx
0x18002a77f  mov     rdi, rcx
0x18002a782  mov     rdx, [r8]
0x18002a785  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18002a78a  mov     r15, rax
0x18002a78d  mov     r9, rax
0x18002a790  mov     r8, r14
0x18002a793  lea     rdx, [rsp+88h+var_68]
0x18002a798  mov     rcx, rdi
0x18002a79b  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18002a7a0  mov     rcx, qword ptr [rsp+88h+var_68+8]
0x18002a7a5  test    rcx, rcx
0x18002a7a8  jz      short loc_18002A7B5
0x18002a7aa  mov     [rsi], rcx
0x18002a7ad  xor     bpl, bpl
0x18002a7b0  jmp     loc_18002A8DA
0x18002a7b5  mov     rax, 0AAAAAAAAAAAAAAAh
0x18002a7bf  cmp     [rdi+10h], rax
0x18002a7c3  jnz     short loc_18002A7D9
0x18002a7c5  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x18002a7cc  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18002a7d9  lea     r13, [rdi+8]
0x18002a7dd  mov     [rsp+88h+var_58], r13
0x18002a7e2  mov     [rsp+88h+var_50], 0
0x18002a7eb  mov     ecx, 18h; Size
0x18002a7f0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a7f5  mov     rbx, rax
0x18002a7f8  mov     [rsp+88h+var_50], rax
0x18002a7fd  mov     rcx, [r14]
0x18002a800  mov     [rax+10h], rcx
0x18002a804  mov     rcx, [rdi+10h]
0x18002a808  mov     ebp, 1
0x18002a80d  add     rcx, rbp
0x18002a810  xorps   xmm0, xmm0
0x18002a813  js      short loc_18002A81C
0x18002a815  cvtsi2ss xmm0, rcx
0x18002a81a  jmp     short loc_18002A831
0x18002a81c  mov     rax, rcx
0x18002a81f  shr     rax, 1
0x18002a822  and     rcx, rbp
0x18002a825  or      rax, rcx
0x18002a828  cvtsi2ss xmm0, rax
0x18002a82d  addss   xmm0, xmm0
0x18002a831  mov     rcx, [rdi+38h]
0x18002a835  xorps   xmm1, xmm1
0x18002a838  test    rcx, rcx
0x18002a83b  js      short loc_18002A844
0x18002a83d  cvtsi2ss xmm1, rcx
0x18002a842  jmp     short loc_18002A859
0x18002a844  mov     rax, rcx
0x18002a847  shr     rax, 1
0x18002a84a  and     rcx, rbp
0x18002a84d  or      rax, rcx
0x18002a850  cvtsi2ss xmm1, rax
0x18002a855  addss   xmm1, xmm1
0x18002a859  divss   xmm0, xmm1
0x18002a85d  comiss  xmm0, dword ptr [rdi]
0x18002a860  jbe     short loc_18002A887
0x18002a862  mov     rcx, rdi
0x18002a865  call    ?_Rehash_for_1@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Rehash_for_1(void)
0x18002a86a  mov     r9, r15
0x18002a86d  lea     r8, [rbx+10h]
0x18002a871  lea     rdx, [rsp+88h+var_58]
0x18002a876  mov     rcx, rdi
0x18002a879  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18002a87e  movups  xmm0, xmmword ptr [rax]
0x18002a881  movdqu  [rsp+88h+var_68], xmm0
0x18002a887  mov     rdx, qword ptr [rsp+88h+var_68]
0x18002a88c  mov     r8, [rdx+8]
0x18002a890  add     [rdi+10h], rbp
0x18002a894  mov     [rbx], rdx
0x18002a897  mov     [rbx+8], r8
0x18002a89b  mov     [r8], rbx
0x18002a89e  mov     [rdx+8], rbx
0x18002a8a2  mov     rcx, [rdi+18h]
0x18002a8a6  mov     rax, [rdi+30h]
0x18002a8aa  and     rax, r15
0x18002a8ad  add     rax, rax
0x18002a8b0  mov     r9, [rcx+rax*8]
0x18002a8b4  cmp     r9, [r13+0]
0x18002a8b8  jnz     short loc_18002A8C0
0x18002a8ba  mov     [rcx+rax*8], rbx
0x18002a8be  jmp     short loc_18002A8D2
0x18002a8c0  cmp     r9, rdx
0x18002a8c3  jnz     short loc_18002A8CB
0x18002a8c5  mov     [rcx+rax*8], rbx
0x18002a8c9  jmp     short loc_18002A8D7
0x18002a8cb  cmp     [rcx+rax*8+8], r8
0x18002a8d0  jnz     short loc_18002A8D7
0x18002a8d2  mov     [rcx+rax*8+8], rbx
0x18002a8d7  mov     [rsi], rbx
0x18002a8da  mov     eax, 8
0x18002a8df  mov     rcx, rsi
0x18002a8e2  mov     [rcx+rax], bpl
0x18002a8e6  mov     rax, rsi
0x18002a8e9  add     rsp, 48h
0x18002a8ed  pop     r15
0x18002a8ef  pop     r14
0x18002a8f1  pop     r13
0x18002a8f3  pop     r12
0x18002a8f5  pop     rdi
0x18002a8f6  pop     rsi
0x18002a8f7  pop     rbp
0x18002a8f8  pop     rbx
0x18002a8f9  retn
```
