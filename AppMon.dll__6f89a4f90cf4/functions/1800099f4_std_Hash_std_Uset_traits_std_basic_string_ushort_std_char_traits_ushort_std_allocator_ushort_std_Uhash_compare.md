# std::_Hash<std::_Uset_traits<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::_Uhash_compare<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,0>>::_Range_eraser::_Bump_erased(void)

- ea: `0x1800099f4`
- end: `0x180009a1a`
- name: `?_Bump_erased@_Range_eraser@?$_Hash@V?$_Uset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$_Uhash_compare@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAAXXZ`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180009dc0`

## callees

- `0x180007fb8`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<std::wstring,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::wstring>,0>>::_Range_eraser::_Bump_erased(
        _QWORD *a1)
{
  __int64 result; // rax

  a1[2] = *(_QWORD *)a1[2];
  std::_List_node<std::wstring,void *>::_Freenode<std::allocator<std::_List_node<std::wstring,void *>>>();
  result = *a1;
  --*(_QWORD *)(*a1 + 8LL);
  return result;
}

```

## disassembly

```asm
0x1800099f4  push    rbx
0x1800099f6  sub     rsp, 20h
0x1800099fa  mov     rdx, [rcx+10h]
0x1800099fe  mov     rbx, rcx
0x180009a01  mov     rax, [rdx]
0x180009a04  mov     [rcx+10h], rax
0x180009a08  call    ??$_Freenode@V?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@std@@@?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_List_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@PEAU01@@Z; std::_List_node<std::wstring,void *>::_Freenode<std::allocator<std::_List_node<std::wstring,void *>>>(std::allocator<std::_List_node<std::wstring,void *>> &,std::_List_node<std::wstring,void *> *)
0x180009a0d  mov     rax, [rbx]
0x180009a10  dec     qword ptr [rax+8]
0x180009a14  add     rsp, 20h
0x180009a18  pop     rbx
0x180009a19  retn
```
