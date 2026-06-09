# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x180027f90`
- end: `0x180028002`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028150`
- `0x180037e4f`

## callees

- `0x180001bf8`
- `0x180027f90`
- `0x18002802c`

## pseudocode

```c
void __fastcall Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(
        __int64 a1)
{
  __int64 *i; // rbx
  _QWORD **v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  for ( i = *(__int64 **)(a1 + 8); ; operator delete((void *)i[2]) )
  {
    i = (__int64 *)*i;
    if ( i == *(__int64 **)(a1 + 8) )
      break;
  }
  std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned short const *>>,std::_Iterator_base0>>>(a1 + 24);
  v3 = *(_QWORD ***)(a1 + 8);
  *v3[1] = 0;
  v4 = *v3;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      operator delete(v4);
      v4 = v5;
    }
    while ( v5 );
  }
  operator delete(*(void **)(a1 + 8));
}

```

## disassembly

```asm
0x180027f90  mov     [rsp+arg_0], rbx
0x180027f95  push    rdi
0x180027f96  sub     rsp, 20h
0x180027f9a  mov     rbx, [rcx+8]
0x180027f9e  mov     rdi, rcx
0x180027fa1  mov     rbx, [rbx]
0x180027fa4  cmp     rbx, [rdi+8]
0x180027fa8  jz      short loc_180027FB5
0x180027faa  mov     rcx, [rbx+10h]; void *
0x180027fae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027fb3  jmp     short loc_180027FA1
0x180027fb5  lea     rcx, [rdi+18h]
0x180027fb9  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>(void)
0x180027fbe  mov     rcx, [rdi+8]
0x180027fc2  mov     rax, [rcx+8]
0x180027fc6  mov     qword ptr [rax], 0
0x180027fcd  mov     rcx, [rcx]; void *
0x180027fd0  test    rcx, rcx
0x180027fd3  jz      short loc_180027FEA
0x180027fd5  mov     rbx, [rcx]
0x180027fd8  mov     edx, 18h; unsigned __int64
0x180027fdd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180027fe2  mov     rcx, rbx
0x180027fe5  test    rbx, rbx
0x180027fe8  jnz     short loc_180027FD5
0x180027fea  mov     rcx, [rdi+8]; void *
0x180027fee  mov     edx, 18h; unsigned __int64
0x180027ff3  mov     rbx, [rsp+28h+arg_0]
0x180027ff8  add     rsp, 20h
0x180027ffc  pop     rdi
0x180027ffd  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
