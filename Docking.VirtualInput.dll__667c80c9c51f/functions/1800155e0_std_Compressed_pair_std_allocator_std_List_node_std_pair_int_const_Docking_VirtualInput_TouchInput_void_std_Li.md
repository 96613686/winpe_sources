# std::_Compressed_pair<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>,std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,1>::_Compressed_pair<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>,std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,1>(std::_One_then_variadic_args_t,std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)

- ea: `0x1800155e0`
- end: `0x180015621`
- name: `??$?0AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@$$V@?$_Compressed_pair@V?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@2@$00@std@@QEAA@U_One_then_variadic_args_t@1@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z`
- size: `65`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18001681c`

## callees

- `0x18000b810`
- `0x1800157e0`
- `0x180016708`

## pseudocode

```c
__int64 __fastcall std::_Compressed_pair<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>,std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,1>::_Compressed_pair<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>,std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>,1>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax

  v3 = Microsoft::WRL::Details::Forward<std::nullptr_t>(a3);
  std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>(
    a1,
    v3);
  std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>(a1);
  return a1;
}

```

## disassembly

```asm
0x1800155e0  mov     [rsp+arg_10], r8
0x1800155e5  mov     [rsp+arg_8], dl
0x1800155e9  mov     [rsp+arg_0], rcx
0x1800155ee  sub     rsp, 28h
0x1800155f2  mov     rcx, [rsp+28h+arg_10]
0x1800155f7  call    ??$Forward@$$T@Details@WRL@Microsoft@@YA$$QEA$$TAEA$$T@Z
0x1800155fc  mov     rdx, rax
0x1800155ff  mov     rcx, [rsp+28h+arg_0]
0x180015604  call    ??$?0U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@QEAA@AEBV?$allocator@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@1@@Z; std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>(std::allocator<std::pair<int const,Docking::VirtualInput::TouchInput>> const &)
0x180015609  mov     rax, [rsp+28h+arg_0]
0x18001560e  mov     rcx, rax
0x180015611  call    ??0?$_List_val@U?$_List_simple_types@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@std@@@std@@QEAA@XZ; std::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>::_List_val<std::_List_simple_types<std::pair<int const,Docking::VirtualInput::TouchInput>>>(void)
0x180015616  nop
0x180015617  mov     rax, [rsp+28h+arg_0]
0x18001561c  add     rsp, 28h
0x180015620  retn
```
