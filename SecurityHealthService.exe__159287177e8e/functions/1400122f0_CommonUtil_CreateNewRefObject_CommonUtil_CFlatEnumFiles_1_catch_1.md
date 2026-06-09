# _CommonUtil::CreateNewRefObject_CommonUtil::CFlatEnumFiles__::_1_::catch$1

- ea: `0x1400122f0`
- end: `0x140012319`
- name: `_CommonUtil::CreateNewRefObject_CommonUtil::CFlatEnumFiles__::_1_::catch$1`
- size: `41`
- prototype: `void __fastcall __noreturn(CommonUtil *, const struct std::exception *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x14000e5bc`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::CreateNewRefObject_CommonUtil::CFlatEnumFiles__::_1_::catch_1(
        CommonUtil *a1,
        const struct std::exception *a2)
{
  CommonUtil::HrFromStdException(a1, a2);
}

```

## disassembly

```asm
0x1400122f0  mov     [rsp+arg_8], rdx
0x1400122f5  push    rbp
0x1400122f6  sub     rsp, 20h
0x1400122fa  mov     rbp, rdx
0x1400122fd  call    ?HrFromStdException@CommonUtil@@YAJAEBVexception@std@@@Z; CommonUtil::HrFromStdException(std::exception const &)
0x140012302  mov     [rbp+48h], eax
0x140012305  mov     [rbp+50h], eax
0x140012308  mov     rax, 0
0x140012312  add     rsp, 20h
0x140012316  pop     rbp
0x140012317  retn
```
