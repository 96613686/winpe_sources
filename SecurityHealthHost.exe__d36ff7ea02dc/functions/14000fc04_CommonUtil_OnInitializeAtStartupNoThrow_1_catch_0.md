# _CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$0

- ea: `0x14000fc04`
- end: `0x14000fc2a`
- name: `_CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$0`
- size: `38`
- prototype: `void __fastcall __noreturn(CommonUtil *, const struct std::exception *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000ebd0`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch_0(
        CommonUtil *a1,
        const struct std::exception *a2)
{
  CommonUtil::HrFromStdException(a1, a2);
}

```

## disassembly

```asm
0x14000fc04  mov     [rsp+arg_8], rdx
0x14000fc09  push    rbp
0x14000fc0a  sub     rsp, 20h
0x14000fc0e  mov     rbp, rdx
0x14000fc11  call    ?HrFromStdException@CommonUtil@@YAJAEBVexception@std@@@Z; CommonUtil::HrFromStdException(std::exception const &)
0x14000fc16  mov     [rbp+40h], eax
0x14000fc19  mov     rax, 0
0x14000fc23  add     rsp, 20h
0x14000fc27  pop     rbp
0x14000fc28  retn
```
