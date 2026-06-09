# std::_List_alloc<0,std::_List_base_types<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>,std::allocator<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>>>>::_Buynode0(std::_List_node<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>,void *> *,std::_List_node<std::pair<FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>,std::default_delete<std::vector<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>,std::allocator<std::unique_ptr<FilterAgent,std::default_delete<FilterAgent>>>>>>>,void *> *)

- ea: `0x18000e1c8`
- end: `0x18000e214`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@V?$allocator@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@@2@@std@@@std@@QEAAPEAU?$_List_node@U?$pair@$$CBW4FilterType@@V?$unique_ptr@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@U?$default_delete@V?$vector@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@V?$allocator@V?$unique_ptr@VFilterAgent@@U?$default_delete@VFilterAgent@@@std@@@std@@@2@@std@@@2@@std@@@std@@PEAX@2@PEAU32@0@Z`
- size: `76`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000bab0`
- `0x18000f9bc`

## callees

- `0x180001a30`
- `0x180001bd8`
- `0x18000e1c8`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<std::pair<enum FilterType const,std::unique_ptr<std::vector<std::unique_ptr<FilterAgent>>>>>>::_Buynode0(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x20u);
  if ( !result )
    std::_Xbad_alloc();
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  *result = a2;
  result[1] = a3;
  return result;
}

```

## disassembly

```asm
0x18000e1c8  mov     [rsp+arg_8], rbx
0x18000e1cd  mov     [rsp+arg_0], rcx
0x18000e1d2  push    rdi
0x18000e1d3  sub     rsp, 20h
0x18000e1d7  mov     rdi, r8
0x18000e1da  mov     rbx, rdx
0x18000e1dd  mov     ecx, 20h ; ' '; Size
0x18000e1e2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000e1e7  mov     [rsp+28h+arg_0], rax
0x18000e1ec  test    rax, rax
0x18000e1ef  jz      short loc_18000E20E
0x18000e1f1  test    rbx, rbx
0x18000e1f4  jnz     short loc_18000E1FC
0x18000e1f6  mov     rbx, rax
0x18000e1f9  mov     rdi, rax
0x18000e1fc  mov     [rax], rbx
0x18000e1ff  mov     [rax+8], rdi
0x18000e203  mov     rbx, [rsp+28h+arg_8]
0x18000e208  add     rsp, 20h
0x18000e20c  pop     rdi
0x18000e20d  retn
0x18000e20e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
