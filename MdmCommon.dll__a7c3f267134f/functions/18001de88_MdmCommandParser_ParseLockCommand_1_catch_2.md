# _MdmCommandParser::ParseLockCommand_::_1_::catch$2

- ea: `0x18001de88`
- end: `0x18001deb5`
- name: `_MdmCommandParser::ParseLockCommand_::_1_::catch$2`
- size: `45`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000aca4`

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
0x18001de88  mov     [rsp+arg_8], rdx
0x18001de8d  push    rbp
0x18001de8e  sub     rsp, 30h
0x18001de92  mov     rbp, rdx
0x18001de95  mov     rcx, [rbp+0F8h]; this
0x18001de9c  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18001dea1  mov     [rbp+38h], eax
0x18001dea4  mov     rax, 0
0x18001deae  add     rsp, 30h
0x18001deb2  pop     rbp
0x18001deb3  retn
```
