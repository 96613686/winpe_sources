# _RevokableAccessor::RevokableAccessor_::_1_::catch$0

- ea: `0x180011420`
- end: `0x180011445`
- name: `_RevokableAccessor::RevokableAccessor_::_1_::catch$0`
- size: `37`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000257c`

## pseudocode

```c
void __fastcall __noreturn RevokableAccessor::RevokableAccessor_::_1_::catch_0(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 40) = 0;
  throw (TestException *)(a2 + 40);
}

```

## disassembly

```asm
0x180011420  mov     [rsp+arg_8], rdx
0x180011425  push    rbp
0x180011426  sub     rsp, 20h
0x18001142a  mov     rbp, rdx
0x18001142d  mov     dword ptr [rbp+28h], 0
0x180011434  lea     rdx, _TI1?AW4TestException@@; pThrowInfo
0x18001143b  lea     rcx, [rbp+28h]; pExceptionObject
0x18001143f  call    _CxxThrowException_0
```
