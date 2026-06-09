# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x180028904`
- end: `0x1800289c3`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `191`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028d3c`

## callees

- `0x180002c44`
- `0x180002cf5`
- `0x180026aa0`
- `0x180027258`
- `0x180028904`
- `0x18002957c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned __int16 *__fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(
        float *a1,
        unsigned __int16 *a2)
{
  unsigned __int16 *result; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  _QWORD v9[7]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 *v10; // [rsp+78h] [rbp+10h] BYREF

  v10 = a2;
  if ( !a2 )
    return 0;
  v5 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()((__int64)a1, a2);
  v6 = std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
         a1,
         v9,
         &v10,
         v5)[1];
  if ( v6 && v6 != *((_QWORD *)a1 + 1) )
    return *(unsigned __int16 **)(v6 + 16);
  v7 = -1;
  do
    ++v7;
  while ( a2[v7] );
  v8 = v7 + 1;
  v10 = (unsigned __int16 *)operator new[](saturated_mul(v8, 2u));
  memcpy_0(v10, a2, 2 * v8);
  try
  {
    std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::insert(
      a1,
      (__int64)v9,
      &v10);
    result = v10;
  }
  catch ( ... )
  {
    operator delete(v10);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180028904  mov     [rsp+arg_8], rdx
0x180028909  push    rbx
0x18002890a  push    rsi
0x18002890b  push    rdi
0x18002890c  push    r14
0x18002890e  sub     rsp, 48h
0x180028912  mov     rdi, rdx
0x180028915  mov     rsi, rcx
0x180028918  xor     r14d, r14d
0x18002891b  test    rdx, rdx
0x18002891e  jnz     short loc_18002892C
0x180028920  xor     eax, eax
0x180028922  add     rsp, 48h
0x180028926  pop     r14
0x180028928  pop     rdi
0x180028929  pop     rsi
0x18002892a  pop     rbx
0x18002892b  retn
0x18002892c  lea     rax, [rcx+40h]
0x180028930  mov     [rsp+68h+var_48], rax
0x180028935  mov     [rsp+68h+var_40], 1
0x18002893a  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x18002893f  mov     r9, rax
0x180028942  lea     r8, [rsp+68h+arg_8]
0x180028947  lea     rdx, [rsp+68h+var_38]
0x18002894c  mov     rcx, rsi
0x18002894f  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x180028954  mov     rax, [rax+8]
0x180028958  test    rax, rax
0x18002895b  jz      short loc_180028969
0x18002895d  cmp     rax, [rsi+8]
0x180028961  jz      short loc_180028969
0x180028963  mov     rax, [rax+10h]
0x180028967  jmp     short loc_180028922
0x180028969  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002896d  mov     rbx, rcx
0x180028970  inc     rbx
0x180028973  cmp     [rdi+rbx*2], r14w
0x180028978  jnz     short loc_180028970
0x18002897a  inc     rbx
0x18002897d  mov     eax, 2
0x180028982  mul     rbx
0x180028985  cmovb   rax, rcx
0x180028989  mov     rcx, rax; unsigned __int64
0x18002898c  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180028991  mov     [rsp+68h+arg_8], rax
0x180028996  lea     r8, [rbx+rbx]; Size
0x18002899a  mov     rdx, rdi; Src
0x18002899d  mov     rcx, rax; void *
0x1800289a0  call    memcpy_0
0x1800289a5  nop
0x1800289a6  lea     r8, [rsp+68h+arg_8]
0x1800289ab  lea     rdx, [rsp+68h+var_38]
0x1800289b0  mov     rcx, rsi
0x1800289b3  call    ?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@2@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)
0x1800289b8  nop
0x1800289b9  mov     rax, [rsp+68h+arg_8]
0x1800289be  jmp     loc_180028922
```
