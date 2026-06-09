# _std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0

- ea: `0x14000abca`
- end: `0x14000ac2a`
- name: `_std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch$0`
- size: `96`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x14000844c`
- `0x14000845c`
- `0x140008470`
- `0x1400094b0`
- `0x14000a21a`
- `0x14000abca`

## pseudocode

```c
void __fastcall __noreturn std::list_Command_std::allocator_Command___::_Insert_range_std::_List_const_iterator_std::_List_val_std::_List_simple_types_Command________::_1_::catch_0(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rbx
  void **v4; // rax

  if ( std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
         (_QWORD *)(a2 + 120),
         (_QWORD *)(a2 + 112)) )
  {
    v3 = *(_QWORD *)(a2 + 104);
    do
    {
      *(_QWORD *)(a2 + 32) = v3;
      v4 = (void **)std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(a2 + 32);
      std::list<Command>::_Unchecked_erase(*(void ***)(a2 + 96), *v4);
      std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++((_QWORD **)(a2 + 120));
    }
    while ( std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(
              (_QWORD *)(a2 + 120),
              (_QWORD *)(a2 + 112)) );
  }
  throw;
}

```

## disassembly

```asm
0x14000abca  mov     [rsp+arg_8], rdx
0x14000abcf  push    rbx
0x14000abd0  push    rbp
0x14000abd1  sub     rsp, 28h
0x14000abd5  mov     rbp, rdx
0x14000abd8  lea     rdx, [rbp+70h]
0x14000abdc  lea     rcx, [rbp+78h]
0x14000abe0  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)
0x14000abe5  test    al, al
0x14000abe7  jz      short loc_14000AC20
0x14000abe9  mov     rbx, [rbp+68h]
0x14000abed  mov     [rbp+20h], rbx
0x14000abf1  lea     rcx, [rbp+20h]
0x14000abf5  call    ??F?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>::operator--(void)
0x14000abfa  mov     rdx, [rax]
0x14000abfd  mov     rcx, [rbp+60h]
0x14000ac01  call    ?_Unchecked_erase@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::list<Command>::_Unchecked_erase(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Command>>,std::_Iterator_base0>)
0x14000ac06  lea     rcx, [rbp+78h]
0x14000ac0a  call    ??E?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator++(void)
0x14000ac0f  lea     rdx, [rbp+70h]
0x14000ac13  lea     rcx, [rbp+78h]
0x14000ac17  call    ??9?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@UCommand@@@std@@@std@@@std@@QEBA_NAEBV01@@Z; std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>>::operator!=(std::_List_const_iterator<std::_List_val<std::_List_simple_types<Command>>> const &)
0x14000ac1c  test    al, al
0x14000ac1e  jnz     short loc_14000ABED
0x14000ac20  xor     edx, edx; pThrowInfo
0x14000ac22  xor     ecx, ecx; pExceptionObject
0x14000ac24  call    _CxxThrowException_0
```
