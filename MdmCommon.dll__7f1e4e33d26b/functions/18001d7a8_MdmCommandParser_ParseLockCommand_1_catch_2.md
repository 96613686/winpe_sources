# _MdmCommandParser::ParseLockCommand_::_1_::catch$2

- ea: `0x18001d7a8`
- end: `0x18001d7d5`
- name: `_MdmCommandParser::ParseLockCommand_::_1_::catch$2`
- size: `45`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aa7c`

## pseudocode

```c
__int64 __fastcall MdmCommandParser::ParseLockCommand_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 248),
                           (void *)a2,
                           a3,
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18001d7a8  mov     [rsp+arg_8], rdx
0x18001d7ad  push    rbp
0x18001d7ae  sub     rsp, 30h
0x18001d7b2  mov     rbp, rdx
0x18001d7b5  mov     rcx, [rbp+0F8h]; this
0x18001d7bc  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001d7c1  mov     [rbp+38h], eax
0x18001d7c4  mov     rax, 0
0x18001d7ce  add     rsp, 30h
0x18001d7d2  pop     rbp
0x18001d7d3  retn
```
