# std::list<CommandSet,std::allocator<CommandSet>>::list<CommandSet,std::allocator<CommandSet>>(void)

- ea: `0x140008290`
- end: `0x1400082be`
- name: `??0?$list@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@QEAA@XZ`
- size: `46`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009328`

## pseudocode

```c
void __fastcall std::list<CommandSet>::list<CommandSet>(_QWORD *a1)
{
  *a1 = 0;
  a1[1] = 0;
  *a1 = std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(a1, 0, 0);
}

```

## disassembly

```asm
0x140008290  push    rbx
0x140008292  sub     rsp, 20h
0x140008296  xor     r8d, r8d
0x140008299  mov     qword ptr [rcx], 0
0x1400082a0  xor     edx, edx
0x1400082a2  mov     qword ptr [rcx+8], 0
0x1400082aa  mov     rbx, rcx
0x1400082ad  call    ?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@UCommandSet@@V?$allocator@UCommandSet@@@std@@@std@@@std@@QEAAPEAU?$_List_node@UCommandSet@@PEAX@2@PEAU32@0@Z; std::_List_alloc<0,std::_List_base_types<CommandSet>>::_Buynode0(std::_List_node<CommandSet,void *> *,std::_List_node<CommandSet,void *> *)
0x1400082b2  mov     [rbx], rax
0x1400082b5  mov     rax, rbx
0x1400082b8  add     rsp, 20h
0x1400082bc  pop     rbx
0x1400082bd  retn
```
