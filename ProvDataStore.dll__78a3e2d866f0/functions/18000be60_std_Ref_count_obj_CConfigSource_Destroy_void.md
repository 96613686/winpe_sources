# std::_Ref_count_obj<CConfigSource>::_Destroy(void)

- ea: `0x18000be60`
- end: `0x18000be86`
- name: `?_Destroy@?$_Ref_count_obj@VCConfigSource@@@std@@EEAAXXZ`
- size: `38`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000b144`

## pseudocode

```c
__int64 __fastcall std::_Ref_count_obj<CConfigSource>::_Destroy(__int64 a1)
{
  std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(a1 + 1088);
  return std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(a1 + 1072);
}

```

## disassembly

```asm
0x18000be60  push    rbx
0x18000be62  sub     rsp, 20h
0x18000be66  mov     rbx, rcx
0x18000be69  add     rcx, 440h
0x18000be70  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(void)
0x18000be75  lea     rcx, [rbx+430h]
0x18000be7c  add     rsp, 20h
0x18000be80  pop     rbx
0x18000be81  jmp     ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(void)
```
