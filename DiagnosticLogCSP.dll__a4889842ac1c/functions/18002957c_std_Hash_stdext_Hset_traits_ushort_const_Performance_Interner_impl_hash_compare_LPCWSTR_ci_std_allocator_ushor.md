# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)

- ea: `0x18002957c`
- end: `0x180029708`
- name: `?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@2@AEBQEBG@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180028904`

## callees

- `0x180001b84`
- `0x180026aa0`
- `0x180027258`
- `0x180029350`
- `0x18002957c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800295e0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800295e0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::insert(
        float *a1,
        __int64 a2,
        unsigned __int16 **a3)
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
  _QWORD *v20; // [rsp+30h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+38h] [rbp-50h]

  v6 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()((__int64)a1, *a3);
  std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
    a1,
    &v19,
    a3,
    v6);
  if ( !*((_QWORD *)&v19 + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = a1 + 2;
    v21 = 0;
    v8 = operator new(0x18u);
    v21 = v8;
    v8[2] = *a3;
    v7 = 1;
    v9 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v9 < 0 )
      v10 = (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1))
          + (float)(v9 & 1 | (unsigned int)((unsigned __int64)v9 >> 1));
    else
      v10 = (float)(int)v9;
    v11 = *((_QWORD *)a1 + 7);
    if ( v11 < 0 )
      v12 = (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1))
          + (float)(v11 & 1 | (unsigned int)((unsigned __int64)v11 >> 1));
    else
      v12 = (float)(int)v11;
    if ( (float)(v10 / v12) > *a1 )
    {
      std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Rehash_for_1((__int64)a1);
      v19 = *(_OWORD *)std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
                         a1,
                         &v20,
                         v8 + 2,
                         v6);
    }
    v13 = v19;
    v14 = *(_QWORD **)(v19 + 8);
    ++*((_QWORD *)a1 + 2);
    *v8 = v13;
    v8[1] = v14;
    *v14 = v8;
    *(_QWORD *)(v13 + 8) = v8;
    v15 = *((_QWORD *)a1 + 3);
    v16 = 2 * (v6 & *((_QWORD *)a1 + 6));
    v17 = *(_QWORD *)(v15 + 16 * (v6 & *((_QWORD *)a1 + 6)));
    if ( v17 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v15 + 16 * (v6 & *((_QWORD *)a1 + 6))) = v8;
LABEL_18:
      *(_QWORD *)(v15 + 8 * v16 + 8) = v8;
      goto LABEL_19;
    }
    if ( v17 == v13 )
    {
      *(_QWORD *)(v15 + 16 * (v6 & *((_QWORD *)a1 + 6))) = v8;
    }
    else if ( *(_QWORD **)(v15 + 16 * (v6 & *((_QWORD *)a1 + 6)) + 8) == v14 )
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
0x18002957c  push    rbx
0x18002957e  push    rbp
0x18002957f  push    rsi
0x180029580  push    rdi
0x180029581  push    r12
0x180029583  push    r13
0x180029585  push    r14
0x180029587  push    r15
0x180029589  sub     rsp, 48h
0x18002958d  mov     r14, r8
0x180029590  mov     rsi, rdx
0x180029593  mov     rdi, rcx
0x180029596  mov     rdx, [r8]
0x180029599  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18002959e  mov     r15, rax
0x1800295a1  mov     r9, rax
0x1800295a4  mov     r8, r14
0x1800295a7  lea     rdx, [rsp+88h+var_68]
0x1800295ac  mov     rcx, rdi
0x1800295af  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x1800295b4  mov     rcx, qword ptr [rsp+88h+var_68+8]
0x1800295b9  test    rcx, rcx
0x1800295bc  jz      short loc_1800295C9
0x1800295be  mov     [rsi], rcx
0x1800295c1  xor     bpl, bpl
0x1800295c4  jmp     loc_1800296E8
0x1800295c9  mov     rax, 0AAAAAAAAAAAAAAAh
0x1800295d3  cmp     [rdi+10h], rax
0x1800295d7  jnz     short loc_1800295E7
0x1800295d9  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x1800295e0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800295e7  lea     r13, [rdi+8]
0x1800295eb  mov     [rsp+88h+var_58], r13
0x1800295f0  mov     [rsp+88h+var_50], 0
0x1800295f9  mov     ecx, 18h; Size
0x1800295fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029603  mov     rbx, rax
0x180029606  mov     [rsp+88h+var_50], rax
0x18002960b  mov     rcx, [r14]
0x18002960e  mov     [rax+10h], rcx
0x180029612  mov     rcx, [rdi+10h]
0x180029616  mov     ebp, 1
0x18002961b  add     rcx, rbp
0x18002961e  xorps   xmm0, xmm0
0x180029621  js      short loc_18002962A
0x180029623  cvtsi2ss xmm0, rcx
0x180029628  jmp     short loc_18002963F
0x18002962a  mov     rax, rcx
0x18002962d  shr     rax, 1
0x180029630  and     rcx, rbp
0x180029633  or      rax, rcx
0x180029636  cvtsi2ss xmm0, rax
0x18002963b  addss   xmm0, xmm0
0x18002963f  mov     rcx, [rdi+38h]
0x180029643  xorps   xmm1, xmm1
0x180029646  test    rcx, rcx
0x180029649  js      short loc_180029652
0x18002964b  cvtsi2ss xmm1, rcx
0x180029650  jmp     short loc_180029667
0x180029652  mov     rax, rcx
0x180029655  shr     rax, 1
0x180029658  and     rcx, rbp
0x18002965b  or      rax, rcx
0x18002965e  cvtsi2ss xmm1, rax
0x180029663  addss   xmm1, xmm1
0x180029667  divss   xmm0, xmm1
0x18002966b  comiss  xmm0, dword ptr [rdi]
0x18002966e  jbe     short loc_180029695
0x180029670  mov     rcx, rdi
0x180029673  call    ?_Rehash_for_1@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Rehash_for_1(void)
0x180029678  mov     r9, r15
0x18002967b  lea     r8, [rbx+10h]
0x18002967f  lea     rdx, [rsp+88h+var_58]
0x180029684  mov     rcx, rdi
0x180029687  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18002968c  movups  xmm0, xmmword ptr [rax]
0x18002968f  movdqu  [rsp+88h+var_68], xmm0
0x180029695  mov     rdx, qword ptr [rsp+88h+var_68]
0x18002969a  mov     r8, [rdx+8]
0x18002969e  add     [rdi+10h], rbp
0x1800296a2  mov     [rbx], rdx
0x1800296a5  mov     [rbx+8], r8
0x1800296a9  mov     [r8], rbx
0x1800296ac  mov     [rdx+8], rbx
0x1800296b0  mov     rcx, [rdi+18h]
0x1800296b4  mov     rax, [rdi+30h]
0x1800296b8  and     rax, r15
0x1800296bb  add     rax, rax
0x1800296be  mov     r9, [rcx+rax*8]
0x1800296c2  cmp     r9, [r13+0]
0x1800296c6  jnz     short loc_1800296CE
0x1800296c8  mov     [rcx+rax*8], rbx
0x1800296cc  jmp     short loc_1800296E0
0x1800296ce  cmp     r9, rdx
0x1800296d1  jnz     short loc_1800296D9
0x1800296d3  mov     [rcx+rax*8], rbx
0x1800296d7  jmp     short loc_1800296E5
0x1800296d9  cmp     [rcx+rax*8+8], r8
0x1800296de  jnz     short loc_1800296E5
0x1800296e0  mov     [rcx+rax*8+8], rbx
0x1800296e5  mov     [rsi], rbx
0x1800296e8  mov     eax, 8
0x1800296ed  mov     rcx, rsi
0x1800296f0  mov     [rcx+rax], bpl
0x1800296f4  mov     rax, rsi
0x1800296f7  add     rsp, 48h
0x1800296fb  pop     r15
0x1800296fd  pop     r14
0x1800296ff  pop     r13
0x180029701  pop     r12
0x180029703  pop     rdi
0x180029704  pop     rsi
0x180029705  pop     rbp
0x180029706  pop     rbx
0x180029707  retn
```
