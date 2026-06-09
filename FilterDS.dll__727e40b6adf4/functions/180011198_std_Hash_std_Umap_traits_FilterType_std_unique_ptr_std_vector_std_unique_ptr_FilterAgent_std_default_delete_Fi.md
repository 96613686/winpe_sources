# std::_Hash<std::_Umap_traits<FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>,std::_Uhash_compare<FilterType,std::hash<FilterType>,std::equal_to<FilterType>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>,0>>::_Destroy_if_not_nil(std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>>>)

- ea: `0x180011198`
- end: `0x1800111fe`
- name: `?_Destroy_if_not_nil@?$_Hash@V?$_Umap_traits@W4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@V?$_Uhash_compare@W4FilterType@@U?$hash@W4FilterType@@@std@@U?$equal_to@W4FilterType@@@3@@3@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@3@$0A@@std@@@std@@IEAAXV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@std@@@std@@@2@@Z`
- size: `102`
- prototype: `void __fastcall(void **, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180022843`

## callees

- `0x18000dc0c`
- `0x180011198`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800111db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800111e4`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800111db`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800111e4`

## pseudocode

```c
void __fastcall std::_Hash<std::_Umap_traits<enum FilterType,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>,std::_Uhash_compare<enum FilterType,std::hash<enum FilterType>,std::equal_to<enum FilterType>>,std::allocator<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>,0>>::_Destroy_if_not_nil(
        void **a1,
        void *a2)
{
  void *v4; // rsi

  if ( a2 != *a1 )
  {
    **((_QWORD **)a2 + 1) = *(_QWORD *)a2;
    *(_QWORD *)(*(_QWORD *)a2 + 8LL) = *((_QWORD *)a2 + 1);
    v4 = (void *)*((_QWORD *)a2 + 3);
    if ( v4 )
    {
      std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(*((_QWORD *)a2 + 3));
      operator delete(v4);
    }
    operator delete(a2);
    a1[1] = (char *)a1[1] - 1;
  }
}

```

## disassembly

```asm
0x180011198  mov     [rsp+arg_0], rbx
0x18001119d  mov     [rsp+arg_8], rsi
0x1800111a2  push    rdi
0x1800111a3  sub     rsp, 20h
0x1800111a7  mov     rbx, rdx
0x1800111aa  mov     rdi, rcx
0x1800111ad  cmp     rdx, [rcx]
0x1800111b0  jz      short loc_1800111EE
0x1800111b2  mov     rdx, [rdx+8]
0x1800111b6  mov     rax, [rbx]
0x1800111b9  mov     [rdx], rax
0x1800111bc  mov     rdx, [rbx]
0x1800111bf  mov     rax, [rbx+8]
0x1800111c3  mov     [rdx+8], rax
0x1800111c7  mov     rsi, [rbx+18h]
0x1800111cb  test    rsi, rsi
0x1800111ce  jz      short loc_1800111E1
0x1800111d0  mov     rcx, rsi
0x1800111d3  call    ??1?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<FilterAgent>>::~vector<std::unique_ptr<FilterAgent>>(void)
0x1800111d8  mov     rcx, rsi
0x1800111db  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800111e1  mov     rcx, rbx
0x1800111e4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800111ea  dec     qword ptr [rdi+8]
0x1800111ee  mov     rbx, [rsp+28h+arg_0]
0x1800111f3  mov     rsi, [rsp+28h+arg_8]
0x1800111f8  add     rsp, 20h
0x1800111fc  pop     rdi
0x1800111fd  retn
```
