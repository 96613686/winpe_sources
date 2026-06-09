# std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *>> &,std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *> *)

- ea: `0x18003b274`
- end: `0x18003b2e9`
- name: `??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@1@@Z`
- size: `117`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003a884`
- `0x18003b274`
- `0x18003f11c`
- `0x18003f958`

## callees

- `0x18000f84c`
- `0x180029644`
- `0x18003b274`
- `0x180042bc4`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(
        __int64 a1,
        __int64 a2,
        char *a3)
{
  char *v3; // r14
  char *v6; // rsi

  v3 = a3;
  while ( !v3[25] )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(
      a1,
      a2,
      *((_QWORD *)v3 + 2));
    v6 = v3;
    v3 = *(char **)v3;
    std::vector<enum UusCapability>::~vector<enum UusCapability>(v6 + 96);
    std::wstring::_Tidy_deallocate(v6 + 64);
    std::wstring::_Tidy_deallocate(v6 + 32);
    operator delete(v6);
  }
}

```

## disassembly

```asm
0x18003b274  mov     [rsp+arg_18], rbx
0x18003b279  push    rbp
0x18003b27a  push    rsi
0x18003b27b  push    rdi
0x18003b27c  push    r14
0x18003b27e  push    r15
0x18003b280  sub     rsp, 20h
0x18003b284  cmp     byte ptr [r8+19h], 0
0x18003b289  mov     r14, r8
0x18003b28c  mov     r15, rdx
0x18003b28f  mov     rbp, rcx
0x18003b292  jnz     short loc_18003B2D8
0x18003b294  mov     r8, [r14+10h]
0x18003b298  mov     rdx, r15
0x18003b29b  mov     rcx, rbp
0x18003b29e  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>> &,std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *> *)
0x18003b2a3  mov     rsi, r14
0x18003b2a6  mov     r14, [r14]
0x18003b2a9  lea     rcx, [rsi+60h]
0x18003b2ad  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18003b2b2  lea     rcx, [rsi+40h]
0x18003b2b6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b2bb  lea     rcx, [rsi+20h]
0x18003b2bf  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003b2c4  mov     edx, 88h; unsigned __int64
0x18003b2c9  mov     rcx, rsi; void *
0x18003b2cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003b2d1  cmp     byte ptr [r14+19h], 0
0x18003b2d6  jz      short loc_18003B294
0x18003b2d8  mov     rbx, [rsp+48h+arg_18]
0x18003b2dd  add     rsp, 20h
0x18003b2e1  pop     r15
0x18003b2e3  pop     r14
0x18003b2e5  pop     rdi
0x18003b2e6  pop     rsi
0x18003b2e7  pop     rbp
0x18003b2e8  retn
```
