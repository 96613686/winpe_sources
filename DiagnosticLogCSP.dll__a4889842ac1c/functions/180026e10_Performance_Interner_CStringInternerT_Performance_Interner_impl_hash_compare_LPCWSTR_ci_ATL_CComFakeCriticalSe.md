# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x180026e10`
- end: `0x180026e82`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `114`
- prototype: `void __fastcall(__int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026fcc`
- `0x180036694`

## callees

- `0x180001bc8`
- `0x180026e10`
- `0x180026eac`

## pseudocode

```c
void __fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(
        __int64 a1,
        unsigned __int64 a2)
{
  __int64 *i; // rbx
  _QWORD **v4; // rcx
  _QWORD *v5; // rcx
  _QWORD *v6; // rbx

  for ( i = *(__int64 **)(a1 + 8); ; operator delete((void *)i[2], a2) )
  {
    i = (__int64 *)*i;
    if ( i == *(__int64 **)(a1 + 8) )
      break;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>(a1 + 24);
  v4 = *(_QWORD ***)(a1 + 8);
  *v4[1] = 0;
  v5 = *v4;
  if ( v5 )
  {
    do
    {
      v6 = (_QWORD *)*v5;
      operator delete(v5, 0x18u);
      v5 = v6;
    }
    while ( v6 );
  }
  operator delete(*(void **)(a1 + 8), 0x18u);
}

```

## disassembly

```asm
0x180026e10  mov     [rsp+arg_0], rbx
0x180026e15  push    rdi
0x180026e16  sub     rsp, 20h
0x180026e1a  mov     rbx, [rcx+8]
0x180026e1e  mov     rdi, rcx
0x180026e21  mov     rbx, [rbx]
0x180026e24  cmp     rbx, [rdi+8]
0x180026e28  jz      short loc_180026E35
0x180026e2a  mov     rcx, [rbx+10h]; void *
0x180026e2e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026e33  jmp     short loc_180026E21
0x180026e35  lea     rcx, [rdi+18h]
0x180026e39  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>(void)
0x180026e3e  mov     rcx, [rdi+8]
0x180026e42  mov     rax, [rcx+8]
0x180026e46  mov     qword ptr [rax], 0
0x180026e4d  mov     rcx, [rcx]; void *
0x180026e50  test    rcx, rcx
0x180026e53  jz      short loc_180026E6A
0x180026e55  mov     rbx, [rcx]
0x180026e58  mov     edx, 18h; unsigned __int64
0x180026e5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180026e62  mov     rcx, rbx
0x180026e65  test    rbx, rbx
0x180026e68  jnz     short loc_180026E55
0x180026e6a  mov     rcx, [rdi+8]; void *
0x180026e6e  mov     edx, 18h; unsigned __int64
0x180026e73  mov     rbx, [rsp+28h+arg_0]
0x180026e78  add     rsp, 20h
0x180026e7c  pop     rdi
0x180026e7d  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
