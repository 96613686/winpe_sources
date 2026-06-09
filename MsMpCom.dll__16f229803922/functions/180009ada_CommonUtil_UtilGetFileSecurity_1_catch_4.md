# _CommonUtil::UtilGetFileSecurity_::_1_::catch$4

- ea: `0x180009ada`
- end: `0x180009b03`
- name: `_CommonUtil::UtilGetFileSecurity_::_1_::catch$4`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007cbc`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::UtilGetFileSecurity_::_1_::catch_4(CommonUtil *a1, const struct exception *a2)
{
  CommonUtil::HrFromStdException(a1, a2);
}

```

## disassembly

```asm
0x180009ada  mov     [rsp+arg_8], rdx
0x180009adf  push    rbp
0x180009ae0  sub     rsp, 30h
0x180009ae4  mov     rbp, rdx
0x180009ae7  call    ?HrFromStdException@CommonUtil@@YAJAEBVexception@@@Z; CommonUtil::HrFromStdException(exception const &)
0x180009aec  mov     [rbp+90h], eax
0x180009af2  mov     rax, 0
0x180009afc  add     rsp, 30h
0x180009b00  pop     rbp
0x180009b01  retn
```
