# RasRpcUnloadDll

- ea: `0x180022ea0`
- end: `0x180022ea6`
- name: `RasRpcUnloadDll`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 RasRpcUnloadDll()
{
  return 50;
}

```

## disassembly

```asm
0x180022ea0  mov     eax, 32h ; '2'
0x180022ea5  retn
```
