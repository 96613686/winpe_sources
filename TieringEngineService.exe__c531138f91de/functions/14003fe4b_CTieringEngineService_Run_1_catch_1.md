# _CTieringEngineService::Run_::_1_::catch$1

- ea: `0x14003fe4b`
- end: `0x14003fe69`
- name: `_CTieringEngineService::Run_::_1_::catch$1`
- size: `30`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## pseudocode

```c
__int64 CTieringEngineService::Run_::_1_::catch_1()
{
  return 0;
}

```

## disassembly

```asm
0x14003fe4b  mov     [rsp+arg_8], rdx
0x14003fe50  push    rbp
0x14003fe51  sub     rsp, 30h
0x14003fe55  mov     rbp, rdx
0x14003fe58  mov     rax, 0
0x14003fe62  add     rsp, 30h
0x14003fe66  pop     rbp
0x14003fe67  retn
```
