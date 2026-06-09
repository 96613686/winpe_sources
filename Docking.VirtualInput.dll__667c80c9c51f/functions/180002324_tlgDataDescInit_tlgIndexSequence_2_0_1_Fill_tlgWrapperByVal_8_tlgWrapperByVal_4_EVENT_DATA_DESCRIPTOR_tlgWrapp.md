# _tlgDataDescInit<_tlgIndexSequence<2,0,1>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_EVENT_DATA_DESCRIPTOR *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)

- ea: `0x180002324`
- end: `0x180002398`
- name: `??$Fill@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgDataDescInit@U?$_tlgIndexSequence@$01$0A@$00@@@@SAXPEAU_EVENT_DATA_DESCRIPTOR@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002bdc`

## callees

- `0x180001ae4`
- `0x180001afc`
- `0x180001d50`

## pseudocode

```c
__int64 __fastcall _tlgDataDescInit<_tlgIndexSequence<2,0,1>>::Fill<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v4; // [rsp+20h] [rbp-18h]
  _QWORD *v5; // [rsp+28h] [rbp-10h]

  v4 = _tlgWrapperByVal<4>::Fill(a3, a1 + 2);
  v5 = _tlgWrapperByVal<8>::Fill(a2, a1);
  return std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::destroy<std::pair<int const,Docking::VirtualInput::TouchInput>>(
           v5,
           v4);
}

```

## disassembly

```asm
0x180002324  mov     [rsp+arg_10], r8
0x180002329  mov     [rsp+arg_8], rdx
0x18000232e  mov     [rsp+arg_0], rcx
0x180002333  sub     rsp, 38h
0x180002337  mov     eax, 10h
0x18000233c  imul    rax, 1
0x180002340  mov     rcx, [rsp+38h+arg_0]
0x180002345  add     rcx, rax
0x180002348  mov     rax, rcx
0x18000234b  mov     rdx, rax
0x18000234e  mov     rcx, [rsp+38h+arg_10]
0x180002353  call    ?Fill@?$_tlgWrapperByVal@$03@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<4>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x180002358  mov     [rsp+38h+var_18], rax
0x18000235d  mov     eax, 10h
0x180002362  imul    rax, 0
0x180002366  mov     rcx, [rsp+38h+arg_0]
0x18000236b  add     rcx, rax
0x18000236e  mov     rax, rcx
0x180002371  mov     rdx, rax
0x180002374  mov     rcx, [rsp+38h+arg_8]
0x180002379  call    ?Fill@?$_tlgWrapperByVal@$07@@QEBAPEAXPEAU_EVENT_DATA_DESCRIPTOR@@@Z; _tlgWrapperByVal<8>::Fill(_EVENT_DATA_DESCRIPTOR *)
0x18000237e  mov     [rsp+38h+var_10], rax
0x180002383  mov     rdx, [rsp+38h+var_18]
0x180002388  mov     rcx, [rsp+38h+var_10]
0x18000238d  call    ??$destroy@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@@?$_Default_allocator_traits@V?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@std@@@std@@SAXAEAV?$allocator@U?$_List_node@U?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@std@@PEAX@std@@@1@QEAU?$pair@$$CBHUTouchInput@VirtualInput@Docking@@@1@@Z; std::_Default_allocator_traits<std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>>>::destroy<std::pair<int const,Docking::VirtualInput::TouchInput>>(std::allocator<std::_List_node<std::pair<int const,Docking::VirtualInput::TouchInput>,void *>> &,std::pair<int const,Docking::VirtualInput::TouchInput> * const)
0x180002392  nop
0x180002393  add     rsp, 38h
0x180002397  retn
```
