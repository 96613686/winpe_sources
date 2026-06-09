# operator delete(void *)

- ea: `0x14000157c`
- end: `0x140001581`
- name: `??3@YAXPEAX@Z`
- size: `5`
- prototype: `void __cdecl(void *Block)`
- caller_count: `67`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x140001970`
- `0x140002854`
- `0x140002894`
- `0x1400037c8`
- `0x140005534`
- `0x1400068bc`
- `0x14000696c`
- `0x140006a24`
- `0x140006ac8`
- `0x140008368`
- `0x140008700`
- `0x140008730`
- `0x140008760`
- `0x1400088e8`
- `0x140009dbc`
- `0x140009dcc`
- `0x140009de8`
- `0x14000a110`
- `0x14000a150`
- `0x14000a190`
- `0x14000a1d0`
- `0x14000a210`
- `0x14000a250`
- `0x14000a290`
- `0x14000a2d0`
- `0x14000a310`
- `0x14000a350`
- `0x14000bb90`
- `0x14000bd30`
- `0x14000c7f4`
- `0x14000c8c0`
- `0x14000c900`
- `0x14000c938`
- `0x14000d6bc`
- `0x14000d840`
- `0x14000d880`
- `0x14000e050`
- `0x14000e1c0`
- `0x14000e200`
- `0x14000ec20`
- `0x14000ed40`
- `0x14000ee60`
- `0x14000f180`
- `0x14000f1c0`
- `0x14000f920`
- `0x14000f958`
- `0x14000fcec`
- `0x14000ff10`
- `0x140010490`
- `0x14001052c`

## callees

- `0x140001cd0`

## pseudocode

```c
// attributes: thunk
void __cdecl operator delete(void *Block)
{
  free_0(Block);
}

```

## disassembly

```asm
0x14000157c  jmp     free_0
```
