# DllMain$catch$0

- ea: `0x180013321`
- end: `0x18001333f`
- name: `DllMain$catch$0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 DllMain_catch_0()
{
  return 0;
}

```

## disassembly

```asm
0x180013321  mov     [rsp+arg_8], rdx
0x180013326  push    rbp
0x180013327  sub     rsp, 20h
0x18001332b  mov     rbp, rdx
0x18001332e  mov     rax, 0
0x180013338  add     rsp, 20h
0x18001333c  pop     rbp
0x18001333d  retn
```
