# _std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch$2

- ea: `0x14000ac42`
- end: `0x14000ac62`
- name: `_std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch$2`
- size: `32`
- prototype: `void __fastcall __noreturn(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007dd8`
- `0x14000a21a`

## pseudocode

```c
void __fastcall __noreturn std::list_Command_std::allocator_Command___::list_Command_std::allocator_Command____::_1_::catch_2(
        __int64 a1,
        __int64 a2)
{
  std::list<Command>::_Tidy(*(_QWORD *)(a2 + 64));
  throw;
}

```

## disassembly

```asm
0x14000ac42  mov     [rsp+arg_8], rdx
0x14000ac47  push    rbp
0x14000ac48  sub     rsp, 30h
0x14000ac4c  mov     rbp, rdx
0x14000ac4f  mov     rcx, [rbp+40h]
0x14000ac53  call    ?_Tidy@?$list@UCommand@@V?$allocator@UCommand@@@std@@@std@@QEAAXXZ; std::list<Command>::_Tidy(void)
0x14000ac58  xor     edx, edx; pThrowInfo
0x14000ac5a  xor     ecx, ecx; pExceptionObject
0x14000ac5c  call    _CxxThrowException_0
```
