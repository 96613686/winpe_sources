# _CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$0

- ea: `0x1400125e5`
- end: `0x14001260b`
- name: `_CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$0`
- size: `38`
- prototype: `void __fastcall __noreturn(CommonUtil *, const struct std::exception *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000e5bc`

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
0x1400125e5  mov     [rsp+arg_8], rdx
0x1400125ea  push    rbp
0x1400125eb  sub     rsp, 20h
0x1400125ef  mov     rbp, rdx
0x1400125f2  call    ?HrFromStdException@CommonUtil@@YAJAEBVexception@std@@@Z; CommonUtil::HrFromStdException(std::exception const &)
0x1400125f7  mov     [rbp+40h], eax
0x1400125fa  mov     rax, 0
0x140012604  add     rsp, 20h
0x140012608  pop     rbp
0x140012609  retn
```
