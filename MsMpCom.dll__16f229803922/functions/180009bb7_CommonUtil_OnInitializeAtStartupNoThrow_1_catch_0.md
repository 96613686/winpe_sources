# _CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$0

- ea: `0x180009bb7`
- end: `0x180009bdd`
- name: `_CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007cbc`

## pseudocode

```c
void __fastcall __noreturn CommonUtil::OnInitializeAtStartupNoThrow_::_1_::catch_0(
        CommonUtil *a1,
        const struct exception *a2)
{
  CommonUtil::HrFromStdException(a1, a2);
}

```

## disassembly

```asm
0x180009bb7  mov     [rsp+arg_8], rdx
0x180009bbc  push    rbp
0x180009bbd  sub     rsp, 20h
0x180009bc1  mov     rbp, rdx
0x180009bc4  call    ?HrFromStdException@CommonUtil@@YAJAEBVexception@@@Z; CommonUtil::HrFromStdException(exception const &)
0x180009bc9  mov     [rbp+40h], eax
0x180009bcc  mov     rax, 0
0x180009bd6  add     rsp, 20h
0x180009bda  pop     rbp
0x180009bdb  retn
```
