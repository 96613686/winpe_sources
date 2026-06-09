# std::_Compressed_pair<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>,std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>,1>::_Compressed_pair<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>,std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>,1>(std::_One_then_variadic_args_t,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)

- ea: `0x180015630`
- end: `0x180015671`
- name: `??$?0AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@$$V@?$_Compressed_pair@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@V?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180015680`

## callees

- `0x18000b810`
- `0x1800157e0`
- `0x1800167e4`

## pseudocode

```c
__int64 __fastcall std::_Compressed_pair<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>,std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>,1>::_Compressed_pair<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>,std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>,1>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax

  v3 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>(
    a1,
    v3);
  std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>(a1);
  return a1;
}

```

## disassembly

```asm
0x180015630  mov     [rsp+arg_10], r8
0x180015635  mov     [rsp+arg_8], dl
0x180015639  mov     [rsp+arg_0], rcx
0x18001563e  sub     rsp, 28h
0x180015642  mov     rcx, [rsp+28h+arg_10]
0x180015647  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x18001564c  mov     rdx, rax
0x18001564f  mov     rcx, [rsp+28h+arg_0]
0x180015654  call    ??$?0U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z; std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>(std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)
0x180015659  mov     rax, [rsp+28h+arg_0]
0x18001565e  mov     rcx, rax
0x180015661  call    ??0?$_Vector_val@U?$_Simple_types@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>::_Vector_val<std::_Simple_types<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>>>>(void)
0x180015666  nop
0x180015667  mov     rax, [rsp+28h+arg_0]
0x18001566c  add     rsp, 28h
0x180015670  retn
```
