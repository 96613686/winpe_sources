# AiSvcOnCreateProcess$catch$9

- ea: `0x18000ca3e`
- end: `0x18000ca62`
- name: `AiSvcOnCreateProcess$catch$9`
- size: `36`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 AiSvcOnCreateProcess_catch_9()
{
  return 0;
}

```

## disassembly

```asm
0x18000ca3e  mov     [rsp+arg_8], rdx
0x18000ca43  push    rbp
0x18000ca44  sub     rsp, 90h
0x18000ca4b  mov     rbp, rdx
0x18000ca4e  mov     rax, 0
0x18000ca58  add     rsp, 90h
0x18000ca5f  pop     rbp
0x18000ca60  retn
```
