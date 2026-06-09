# std::_Uninit_move<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0>>>> &,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<ulong>>,std::_Iterator_base0> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x1800039ac`
- end: `0x1800039cd`
- name: `??$_Uninit_move@PEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@K@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `33`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180006754`
- `0x1800069ac`

## callees

- `0x1800039ac`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0> *,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>>>,std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<unsigned long>>,std::_Iterator_base0>>(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3)
{
  while ( a1 != a2 )
    *a3++ = *a1++;
  return a3;
}

```

## disassembly

```asm
0x1800039ac  sub     rsp, 28h
0x1800039b0  jmp     short loc_1800039C0
0x1800039b2  mov     rax, [rcx]
0x1800039b5  mov     [r8], rax
0x1800039b8  add     r8, 8
0x1800039bc  add     rcx, 8
0x1800039c0  cmp     rcx, rdx
0x1800039c3  jnz     short loc_1800039B2
0x1800039c5  mov     rax, r8
0x1800039c8  add     rsp, 28h
0x1800039cc  retn
```
