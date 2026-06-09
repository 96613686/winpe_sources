# TpmVscMgrMeta::basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>::~basic_formatter<ushort,std::char_traits<ushort>,std::allocator<ushort>>(void)

- ea: `0x140008150`
- end: `0x140008179`
- name: `??1?$basic_formatter@GU?$char_traits@G@std@@V?$allocator@G@2@@TpmVscMgrMeta@@QEAA@XZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `8`
- callee_count: `3`
- tags: ``

## callers

- `0x14000641c`
- `0x140008784`
- `0x14000e510`
- `0x14000e62c`
- `0x14000f54c`
- `0x140011b17`
- `0x140011d1f`
- `0x1400123b8`

## callees

- `0x1400080e0`
- `0x140008278`
- `0x140008308`

## pseudocode

```c
__int64 __fastcall TpmVscMgrMeta::basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>::~basic_formatter<unsigned short,std::char_traits<unsigned short>,std::allocator<unsigned short>>(
        __int64 a1)
{
  std::wstring::~wstring(a1 + 40);
  __1___Tree_V___Tmap_traits_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__vector_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std__V__allocator_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std___2__2_U__less_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V__vector_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std__V__allocator_V___List_iterator_V___List_val_U___List_simple_types_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std___std___std___std___2__2__std___2__0A__std___std__QEAA_XZ(a1 + 24);
  return std::list<std::wstring>::~list<std::wstring>(a1 + 8);
}

```

## disassembly

```asm
0x140008150  push    rbx
0x140008152  sub     rsp, 20h
0x140008156  mov     rbx, rcx
0x140008159  add     rcx, 28h ; '('
0x14000815d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140008162  lea     rcx, [rbx+18h]
0x140008166  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$vector@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@V?$allocator@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@@std@@@2@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ
0x14000816b  lea     rcx, [rbx+8]
0x14000816f  add     rsp, 20h
0x140008173  pop     rbx
0x140008174  jmp     ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
```
