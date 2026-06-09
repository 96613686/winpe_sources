# _CThread::Create_::_1_::catch$1

- ea: `0x18000a16c`
- end: `0x18000a18a`
- name: `_CThread::Create_::_1_::catch$1`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 CThread::Create_::_1_::catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x18000a16c  mov     [rsp+arg_8], rdx
0x18000a171  push    rbp
0x18000a172  sub     rsp, 20h
0x18000a176  mov     rbp, rdx
0x18000a179  mov     rax, 0
0x18000a183  add     rsp, 20h
0x18000a187  pop     rbp
0x18000a188  retn
```
