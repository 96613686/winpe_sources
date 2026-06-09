# std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const,UusComponent>>>>(void)

- ea: `0x18003f11c`
- end: `0x18003f1b3`
- name: `??1?$_Tree_head_scoped_ptr@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `151`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18003eef0`
- `0x18004d29d`

## callees

- `0x18000f84c`
- `0x180029644`
- `0x18003b274`
- `0x18003f11c`
- `0x180042bc4`

## pseudocode

```c
void __fastcall std::_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>>::~_Tree_head_scoped_ptr<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>,std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>>(
        __int64 *a1)
{
  void **v1; // r14
  __int64 v2; // rbp
  char *v3; // r15
  char *v4; // rsi

  v1 = (void **)a1[1];
  if ( v1 )
  {
    v2 = *a1;
    v3 = (char *)*((_QWORD *)*v1 + 1);
    while ( !v3[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(
        (__int64)v1,
        v2,
        *((char **)v3 + 2));
      v4 = v3;
      v3 = *(char **)v3;
      std::vector<enum UusCapability>::~vector<enum UusCapability>(v4 + 96);
      std::wstring::_Tidy_deallocate(v4 + 64);
      std::wstring::_Tidy_deallocate(v4 + 32);
      operator delete(v4);
    }
    operator delete(*v1);
  }
}

```

## disassembly

```asm
0x18003f11c  mov     [rsp+arg_8], rbx
0x18003f121  mov     [rsp+arg_10], rbp
0x18003f126  mov     [rsp+arg_18], rsi
0x18003f12b  push    rdi
0x18003f12c  push    r14
0x18003f12e  push    r15
0x18003f130  sub     rsp, 20h
0x18003f134  mov     r14, [rcx+8]
0x18003f138  test    r14, r14
0x18003f13b  jz      short loc_18003F19A
0x18003f13d  mov     rax, [r14]
0x18003f140  mov     rbp, [rcx]
0x18003f143  mov     r15, [rax+8]
0x18003f147  jmp     short loc_18003F186
0x18003f149  mov     r8, [r15+10h]
0x18003f14d  mov     rdx, rbp
0x18003f150  mov     rcx, r14
0x18003f153  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VUusComponent@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,UusComponent>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *>> &,std::_Tree_node<std::pair<std::wstring const,UusComponent>,void *> *)
0x18003f158  mov     rsi, r15
0x18003f15b  mov     r15, [r15]
0x18003f15e  lea     rcx, [rsi+60h]
0x18003f162  call    ??1?$vector@W4UusCapability@@V?$allocator@W4UusCapability@@@std@@@std@@QEAA@XZ; std::vector<UusCapability>::~vector<UusCapability>(void)
0x18003f167  lea     rcx, [rsi+40h]
0x18003f16b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f170  lea     rcx, [rsi+20h]
0x18003f174  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003f179  mov     edx, 88h; unsigned __int64
0x18003f17e  mov     rcx, rsi; void *
0x18003f181  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003f186  cmp     byte ptr [r15+19h], 0
0x18003f18b  jz      short loc_18003F149
0x18003f18d  mov     rcx, [r14]; void *
0x18003f190  mov     edx, 88h; unsigned __int64
0x18003f195  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18003f19a  mov     rbx, [rsp+38h+arg_8]
0x18003f19f  mov     rbp, [rsp+38h+arg_10]
0x18003f1a4  mov     rsi, [rsp+38h+arg_18]
0x18003f1a9  add     rsp, 20h
0x18003f1ad  pop     r15
0x18003f1af  pop     r14
0x18003f1b1  pop     rdi
0x18003f1b2  retn
```
