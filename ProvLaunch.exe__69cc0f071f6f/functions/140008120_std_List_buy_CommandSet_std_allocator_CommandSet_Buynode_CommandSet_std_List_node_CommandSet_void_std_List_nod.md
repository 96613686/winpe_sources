# std::_List_buy<CommandSet,std::allocator<CommandSet>>::_Buynode<CommandSet>(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *,CommandSet &&)

- ea: `0x140008120`
- end: `0x140008198`
- name: `??$_Buynode@UCommandSet@@@?$_List_buy@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@1@PEAU21@0$$QEAUCommandSet@@@Z`
- size: `120`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400090ec`

## callees

- `0x140008234`
- `0x140009328`
- `0x14000961c`

## pseudocode

```c
__int64 __fastcall std::_List_buy<CommandSet>::_Buynode<CommandSet>(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rbx
  __int64 v8; // rcx
  __int64 result; // rax
  __int64 v10; // [rsp+30h] [rbp+8h]

  v5 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, a2, a3);
  v6 = v5;
  v10 = v5;
  v7 = v5 + 16;
  *(_DWORD *)(v5 + 16) = *a4;
  try
  {
    std::list<Command>::list<Command>();
    *(_QWORD *)(v7 + 48) = 7;
    *(_QWORD *)(v7 + 40) = 0;
    *(_WORD *)(v7 + 24) = 0;
    std::wstring::assign((void *)(v7 + 24));
    result = v6;
  }
  catch ( ... )
  {
    std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(v8, v10);
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x140008120  mov     [rsp+arg_8], rbx
0x140008125  mov     [rsp+arg_10], rsi
0x14000812a  mov     [rsp+arg_0], rcx
0x14000812f  push    rdi
0x140008130  sub     rsp, 20h
0x140008134  mov     rsi, r9
0x140008137  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x14000813c  mov     rdi, rax
0x14000813f  mov     [rsp+28h+arg_0], rax
0x140008144  lea     rbx, [rax+10h]
0x140008148  mov     [rsp+28h+arg_18], rbx
0x14000814d  mov     ecx, [rsi]
0x14000814f  mov     [rbx], ecx
0x140008151  lea     rdx, [rsi+8]
0x140008155  lea     rcx, [rbx+8]
0x140008159  call    ??0?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAA@AEBV01@@Z; std::list<Command>::list<Command>(std::list<Command> const &)
0x14000815e  nop
0x14000815f  lea     rcx, [rbx+18h]; void *
0x140008163  mov     qword ptr [rcx+18h], 7
0x14000816b  xor     eax, eax
0x14000816d  mov     [rcx+10h], rax
0x140008171  mov     [rcx], ax
0x140008174  lea     rdx, [rsi+18h]
0x140008178  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000817c  xor     r8d, r8d
0x14000817f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x140008184  nop
0x140008185  mov     rax, rdi
0x140008188  mov     rbx, [rsp+28h+arg_8]
0x14000818d  mov     rsi, [rsp+28h+arg_10]
0x140008192  add     rsp, 20h
0x140008196  pop     rdi
0x140008197  retn
```
