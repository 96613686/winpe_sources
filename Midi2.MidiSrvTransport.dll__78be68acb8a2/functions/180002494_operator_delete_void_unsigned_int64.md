# operator delete(void *,unsigned __int64)

- ea: `0x180002494`
- end: `0x180002499`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `39`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180003b58`
- `0x180003e90`
- `0x180003f00`
- `0x180003f70`
- `0x180003fb0`
- `0x180003ff0`
- `0x18000440c`
- `0x180004ee0`
- `0x180005430`
- `0x180007bc0`
- `0x18000934c`
- `0x180009400`
- `0x180009460`
- `0x1800094e0`
- `0x180009540`
- `0x18000a940`
- `0x18000a970`
- `0x18000a9a0`
- `0x18000aa10`
- `0x18000b5f0`
- `0x18000b7f0`
- `0x18000b8c0`
- `0x18000bbb0`
- `0x18000bcb0`
- `0x18000bfc0`
- `0x18000c250`
- `0x18000c3b0`
- `0x18000c6d0`
- `0x18000c8d0`
- `0x18000d104`
- `0x18000d190`
- `0x18000d3e4`
- `0x18000f144`
- `0x180010b10`
- `0x180011b40`
- `0x180012574`
- `0x180012b04`
- `0x1800138f8`
- `0x180013ea0`

## callees

- `0x180002454`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180002494  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
