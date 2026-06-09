# std::_Uninit_move<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> *,std::_Wrap_alloc<std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>>>>> &,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,ushort>>>> *,std::_Nonscalar_ptr_iterator_tag)

- ea: `0x180009060`
- end: `0x180009081`
- name: `??$_Uninit_move@PEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@PEAV12@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@2@V12@@std@@YAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@0@PEAV10@00AEAU?$_Wrap_alloc@U?$_Wrap_alloc@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@G@std@@@std@@@std@@@std@@@std@@@std@@@0@0U_Nonscalar_ptr_iterator_tag@0@@Z`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000cfbc`
- `0x18000d208`

## callees

- `0x180009060`

## pseudocode

```c
_QWORD *__fastcall std::_Uninit_move<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>> *,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>> *,std::_Wrap_alloc<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>>,std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<_GUID const,unsigned short>>>>>(
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
0x180009060  sub     rsp, 28h
0x180009064  jmp     short loc_180009074
0x180009066  mov     rax, [rcx]
0x180009069  mov     [r8], rax
0x18000906c  add     r8, 8
0x180009070  add     rcx, 8
0x180009074  cmp     rcx, rdx
0x180009077  jnz     short loc_180009066
0x180009079  mov     rax, r8
0x18000907c  add     rsp, 28h
0x180009080  retn
```
