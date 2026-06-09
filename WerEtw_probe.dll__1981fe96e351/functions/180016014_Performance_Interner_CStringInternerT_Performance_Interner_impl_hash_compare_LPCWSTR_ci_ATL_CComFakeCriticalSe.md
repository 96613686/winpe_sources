# Performance::Interner::CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>::~CStringInternerT<Performance::Interner::impl::hash_compare_LPCWSTR_ci,ATL::CComFakeCriticalSection>(void)

- ea: `0x180016014`
- end: `0x180016086`
- name: `??1?$CStringInternerT@Vhash_compare_LPCWSTR_ci@impl@Interner@Performance@@VCComFakeCriticalSection@ATL@@@Interner@Performance@@QEAA@XZ`
- size: `114`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800161d0`
- `0x1800286b1`

## callees

- `0x180001894`
- `0x180016014`
- `0x1800160b0`

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
0x180016014  mov     [rsp+arg_0], rbx
0x180016019  push    rdi
0x18001601a  sub     rsp, 20h
0x18001601e  mov     rbx, [rcx+8]
0x180016022  mov     rdi, rcx
0x180016025  mov     rbx, [rbx]
0x180016028  cmp     rbx, [rdi+8]
0x18001602c  jz      short loc_180016039
0x18001602e  mov     rcx, [rbx+10h]; Block
0x180016032  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016037  jmp     short loc_180016025
0x180016039  lea     rcx, [rdi+18h]
0x18001603d  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ushort const *>>,std::_Iterator_base0>>>(void)
0x180016042  mov     rcx, [rdi+8]
0x180016046  mov     rax, [rcx+8]
0x18001604a  mov     qword ptr [rax], 0
0x180016051  mov     rcx, [rcx]; Block
0x180016054  test    rcx, rcx
0x180016057  jz      short loc_18001606E
0x180016059  mov     rbx, [rcx]
0x18001605c  mov     edx, 18h
0x180016061  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180016066  mov     rcx, rbx
0x180016069  test    rbx, rbx
0x18001606c  jnz     short loc_180016059
0x18001606e  mov     rcx, [rdi+8]; Block
0x180016072  mov     edx, 18h
0x180016077  mov     rbx, [rsp+28h+arg_0]
0x18001607c  add     rsp, 20h
0x180016080  pop     rdi
0x180016081  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
