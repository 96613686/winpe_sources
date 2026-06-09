# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::Intern(ushort const *)

- ea: `0x180017afc`
- end: `0x180017bbb`
- name: `?Intern@?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAAPEBGPEBG@Z`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017f3c`

## callees

- `0x180002700`
- `0x1800027b1`
- `0x180015ca4`
- `0x18001645c`
- `0x180017afc`
- `0x18001877c`

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
0x180017afc  mov     [rsp+arg_8], rdx
0x180017b01  push    rbx
0x180017b02  push    rsi
0x180017b03  push    rdi
0x180017b04  push    r14
0x180017b06  sub     rsp, 48h
0x180017b0a  mov     rdi, rdx
0x180017b0d  mov     rsi, rcx
0x180017b10  xor     r14d, r14d
0x180017b13  test    rdx, rdx
0x180017b16  jnz     short loc_180017B24
0x180017b18  xor     eax, eax
0x180017b1a  add     rsp, 48h
0x180017b1e  pop     r14
0x180017b20  pop     rdi
0x180017b21  pop     rsi
0x180017b22  pop     rbx
0x180017b23  retn
0x180017b24  lea     rax, [rcx+40h]
0x180017b28  mov     [rsp+68h+var_48], rax
0x180017b2d  mov     [rsp+68h+var_40], 1
0x180017b32  call    ??Rhash_compare_LPCWSTR_ci@impl@Interner@Performance@@QEBA_KPEBG@Z; Performance::Interner::impl::hash_compare_LPCWSTR_ci::operator()(ushort const *)
0x180017b37  mov     r9, rax
0x180017b3a  lea     r8, [rsp+68h+arg_8]
0x180017b3f  lea     rdx, [rsp+68h+var_38]
0x180017b44  mov     rcx, rsi
0x180017b47  call    ??$_Find_last@PEBG@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEBGPEAX@std@@@1@AEBQEBG_K@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::_Find_last<ushort const *>(ushort const * const &,unsigned __int64)
0x180017b4c  mov     rax, [rax+8]
0x180017b50  test    rax, rax
0x180017b53  jz      short loc_180017B61
0x180017b55  cmp     rax, [rsi+8]
0x180017b59  jz      short loc_180017B61
0x180017b5b  mov     rax, [rax+10h]
0x180017b5f  jmp     short loc_180017B1A
0x180017b61  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180017b65  mov     rbx, rcx
0x180017b68  inc     rbx
0x180017b6b  cmp     [rdi+rbx*2], r14w
0x180017b70  jnz     short loc_180017B68
0x180017b72  inc     rbx
0x180017b75  mov     eax, 2
0x180017b7a  mul     rbx
0x180017b7d  cmovb   rax, rcx
0x180017b81  mov     rcx, rax; unsigned __int64
0x180017b84  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180017b89  mov     [rsp+68h+arg_8], rax
0x180017b8e  lea     r8, [rbx+rbx]; Size
0x180017b92  mov     rdx, rdi; Src
0x180017b95  mov     rcx, rax; void *
0x180017b98  call    memcpy_0
0x180017b9d  nop
0x180017b9e  lea     r8, [rsp+68h+arg_8]
0x180017ba3  lea     rdx, [rsp+68h+var_38]
0x180017ba8  mov     rcx, rsi
0x180017bab  call    ?insert@?$_Hash@V?$_Hset_traits@PEBGVhash_compare_LPCWSTR_ci@impl@Interner@Performance@@V?$allocator@PEBG@std@@$0A@@stdext@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@@std@@_N@2@AEBQEBG@Z; std::_Hash<stdext::_Hset_traits<ushort const *,Performance::Interner::impl::hash_compare_LPCWSTR_ci,std::allocator<ushort const *>,0>>::insert(ushort const * const &)
0x180017bb0  nop
0x180017bb1  mov     rax, [rsp+68h+arg_8]
0x180017bb6  jmp     loc_180017B1A
```
