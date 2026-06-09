# std::_Ref_count<CConfigSource>::_Destroy(void)

- ea: `0x18000be20`
- end: `0x18000be56`
- name: `?_Destroy@?$_Ref_count@VCConfigSource@@@std@@EEAAXXZ`
- size: `54`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config`

## callees

- `0x18000b144`
- `0x18000be20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000be4a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000be4a`

## pseudocode

```c
void __fastcall std::_Ref_count<CConfigSource>::_Destroy(__int64 a1)
{
  char *v1; // rbx

  v1 = *(char **)(a1 + 16);
  if ( v1 )
  {
    std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(v1 + 1072);
    std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(v1 + 1056);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000be20  push    rbx
0x18000be22  sub     rsp, 20h
0x18000be26  mov     rbx, [rcx+10h]
0x18000be2a  test    rbx, rbx
0x18000be2d  jz      short loc_18000BE50
0x18000be2f  lea     rcx, [rbx+430h]
0x18000be36  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(void)
0x18000be3b  lea     rcx, [rbx+420h]
0x18000be42  call    ??1?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@Uwstring_less_no_case@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>::~_Tree<std::_Tset_traits<std::wstring,wstring_less_no_case,std::allocator<std::wstring>,0>>(void)
0x18000be47  mov     rcx, rbx
0x18000be4a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000be50  add     rsp, 20h
0x18000be54  pop     rbx
0x18000be55  retn
```
