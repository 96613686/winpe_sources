# std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)

- ea: `0x18001877c`
- end: `0x180018908`
- name: `?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@2@AEBQEBG@Z`
- size: `396`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017afc`

## callees

- `0x1800018a0`
- `0x180015ca4`
- `0x18001645c`
- `0x180018550`
- `0x18001877c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800187e0`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x1800187e0`

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
0x18001877c  push    rbx
0x18001877e  push    rbp
0x18001877f  push    rsi
0x180018780  push    rdi
0x180018781  push    r12
0x180018783  push    r13
0x180018785  push    r14
0x180018787  push    r15
0x180018789  sub     rsp, 48h
0x18001878d  mov     r14, r8
0x180018790  mov     rsi, rdx
0x180018793  mov     rdi, rcx
0x180018796  mov     rdx, [r8]
0x180018799  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18001879e  mov     r15, rax
0x1800187a1  mov     r9, rax
0x1800187a4  mov     r8, r14
0x1800187a7  lea     rdx, [rsp+88h+var_68]
0x1800187ac  mov     rcx, rdi
0x1800187af  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x1800187b4  mov     rcx, qword ptr [rsp+88h+var_68+8]
0x1800187b9  test    rcx, rcx
0x1800187bc  jz      short loc_1800187C9
0x1800187be  mov     [rsi], rcx
0x1800187c1  xor     bpl, bpl
0x1800187c4  jmp     loc_1800188E8
0x1800187c9  mov     rax, 0AAAAAAAAAAAAAAAh
0x1800187d3  cmp     [rdi+10h], rax
0x1800187d7  jnz     short loc_1800187E7
0x1800187d9  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x1800187e0  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1800187e7  lea     r13, [rdi+8]
0x1800187eb  mov     [rsp+88h+var_58], r13
0x1800187f0  mov     [rsp+88h+var_50], 0
0x1800187f9  mov     ecx, 18h; Size
0x1800187fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180018803  mov     rbx, rax
0x180018806  mov     [rsp+88h+var_50], rax
0x18001880b  mov     rcx, [r14]
0x18001880e  mov     [rax+10h], rcx
0x180018812  mov     rcx, [rdi+10h]
0x180018816  mov     ebp, 1
0x18001881b  add     rcx, rbp
0x18001881e  xorps   xmm0, xmm0
0x180018821  js      short loc_18001882A
0x180018823  cvtsi2ss xmm0, rcx
0x180018828  jmp     short loc_18001883F
0x18001882a  mov     rax, rcx
0x18001882d  shr     rax, 1
0x180018830  and     rcx, rbp
0x180018833  or      rax, rcx
0x180018836  cvtsi2ss xmm0, rax
0x18001883b  addss   xmm0, xmm0
0x18001883f  mov     rcx, [rdi+38h]
0x180018843  xorps   xmm1, xmm1
0x180018846  test    rcx, rcx
0x180018849  js      short loc_180018852
0x18001884b  cvtsi2ss xmm1, rcx
0x180018850  jmp     short loc_180018867
0x180018852  mov     rax, rcx
0x180018855  shr     rax, 1
0x180018858  and     rcx, rbp
0x18001885b  or      rax, rcx
0x18001885e  cvtsi2ss xmm1, rax
0x180018863  addss   xmm1, xmm1
0x180018867  divss   xmm0, xmm1
0x18001886b  comiss  xmm0, dword ptr [rdi]
0x18001886e  jbe     short loc_180018895
0x180018870  mov     rcx, rdi
0x180018873  call    ?_Rehash_for_1@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEAAXXZ; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Rehash_for_1(void)
0x180018878  mov     r9, r15
0x18001887b  lea     r8, [rbx+10h]
0x18001887f  lea     rdx, [rsp+88h+var_58]
0x180018884  mov     rcx, rdi
0x180018887  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x18001888c  movups  xmm0, xmmword ptr [rax]
0x18001888f  movdqu  [rsp+88h+var_68], xmm0
0x180018895  mov     rdx, qword ptr [rsp+88h+var_68]
0x18001889a  mov     r8, [rdx+8]
0x18001889e  add     [rdi+10h], rbp
0x1800188a2  mov     [rbx], rdx
0x1800188a5  mov     [rbx+8], r8
0x1800188a9  mov     [r8], rbx
0x1800188ac  mov     [rdx+8], rbx
0x1800188b0  mov     rcx, [rdi+18h]
0x1800188b4  mov     rax, [rdi+30h]
0x1800188b8  and     rax, r15
0x1800188bb  add     rax, rax
0x1800188be  mov     r9, [rcx+rax*8]
0x1800188c2  cmp     r9, [r13+0]
0x1800188c6  jnz     short loc_1800188CE
0x1800188c8  mov     [rcx+rax*8], rbx
0x1800188cc  jmp     short loc_1800188E0
0x1800188ce  cmp     r9, rdx
0x1800188d1  jnz     short loc_1800188D9
0x1800188d3  mov     [rcx+rax*8], rbx
0x1800188d7  jmp     short loc_1800188E5
0x1800188d9  cmp     [rcx+rax*8+8], r8
0x1800188de  jnz     short loc_1800188E5
0x1800188e0  mov     [rcx+rax*8+8], rbx
0x1800188e5  mov     [rsi], rbx
0x1800188e8  mov     eax, 8
0x1800188ed  mov     rcx, rsi
0x1800188f0  mov     [rcx+rax], bpl
0x1800188f4  mov     rax, rsi
0x1800188f7  add     rsp, 48h
0x1800188fb  pop     r15
0x1800188fd  pop     r14
0x1800188ff  pop     r13
0x180018901  pop     r12
0x180018903  pop     rdi
0x180018904  pop     rsi
0x180018905  pop     rbp
0x180018906  pop     rbx
0x180018907  retn
```
