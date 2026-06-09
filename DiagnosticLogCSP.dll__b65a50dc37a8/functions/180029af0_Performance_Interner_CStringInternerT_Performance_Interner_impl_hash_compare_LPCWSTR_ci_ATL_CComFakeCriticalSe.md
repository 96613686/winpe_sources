# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x180029af0`
- end: `0x180029bb0`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180029f2c`

## callees

- `0x180002c74`
- `0x180002d25`
- `0x180027c0c`
- `0x1800283f0`
- `0x180029af0`
- `0x18002a768`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(
        __int64 a1,
        void *a2)
{
  void *result; // rax
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  unsigned __int64 v8; // rbx
  _BYTE v9[56]; // [rsp+30h] [rbp-38h] BYREF
  void *v10; // [rsp+78h] [rbp+10h] BYREF

  v10 = a2;
  if ( !a2 )
    return 0;
  v5 = Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(a1, a2);
  v6 = *(_QWORD *)(std::_Hash<stdext::_Hset_traits<unsigned short const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<unsigned short const *>,0>>::_Find_last<unsigned short const *>(
                     a1,
                     v9,
                     &v10,
                     v5)
                 + 8);
  if ( v6 && v6 != *(_QWORD *)(a1 + 8) )
    return *(void **)(v6 + 16);
  v7 = -1;
  do
    ++v7;
  while ( *((_WORD *)a2 + v7) );
  v8 = v7 + 1;
  v10 = operator new[](saturated_mul(v8, 2u));
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
0x180029af0  mov     [rsp+arg_8], rdx
0x180029af5  push    rbx
0x180029af6  push    rsi
0x180029af7  push    rdi
0x180029af8  push    r14
0x180029afa  sub     rsp, 48h
0x180029afe  mov     rdi, rdx
0x180029b01  mov     rsi, rcx
0x180029b04  xor     r14d, r14d
0x180029b07  test    rdx, rdx
0x180029b0a  jnz     short loc_180029B19
0x180029b0c  xor     eax, eax
0x180029b0e  add     rsp, 48h
0x180029b12  pop     r14
0x180029b14  pop     rdi
0x180029b15  pop     rsi
0x180029b16  pop     rbx
0x180029b17  retn
0x180029b19  lea     rax, [rcx+40h]
0x180029b1d  mov     [rsp+68h+var_48], rax
0x180029b22  mov     [rsp+68h+var_40], 1
0x180029b27  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180029b2c  mov     r9, rax
0x180029b2f  lea     r8, [rsp+68h+arg_8]
0x180029b34  lea     rdx, [rsp+68h+var_38]
0x180029b39  mov     rcx, rsi
0x180029b3c  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x180029b41  mov     rax, [rax+8]
0x180029b45  test    rax, rax
0x180029b48  jz      short loc_180029B56
0x180029b4a  cmp     rax, [rsi+8]
0x180029b4e  jz      short loc_180029B56
0x180029b50  mov     rax, [rax+10h]
0x180029b54  jmp     short loc_180029B0E
0x180029b56  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180029b5a  mov     rbx, rcx
0x180029b5d  inc     rbx
0x180029b60  cmp     [rdi+rbx*2], r14w
0x180029b65  jnz     short loc_180029B5D
0x180029b67  inc     rbx
0x180029b6a  mov     eax, 2
0x180029b6f  mul     rbx
0x180029b72  cmovb   rax, rcx
0x180029b76  mov     rcx, rax; unsigned __int64
0x180029b79  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180029b7e  mov     [rsp+68h+arg_8], rax
0x180029b83  lea     r8, [rbx+rbx]; Size
0x180029b87  mov     rdx, rdi; Src
0x180029b8a  mov     rcx, rax; void *
0x180029b8d  call    memcpy_0
0x180029b92  nop
0x180029b93  lea     r8, [rsp+68h+arg_8]
0x180029b98  lea     rdx, [rsp+68h+var_38]
0x180029b9d  mov     rcx, rsi
0x180029ba0  call    ?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@2@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)
0x180029ba5  nop
0x180029ba6  mov     rax, [rsp+68h+arg_8]
0x180029bab  jmp     loc_180029B0E
```
