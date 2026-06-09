# operator delete(void *,unsigned __int64)

- ea: `0x180001644`
- end: `0x180001649`
- name: `??3@YAXPEAX_K@Z`
- size: `5`
- prototype: `void __fastcall(void *Block)`
- caller_count: `35`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180002930`
- `0x180002dd0`
- `0x18000396c`
- `0x180003e18`
- `0x180003f84`
- `0x180004140`
- `0x1800043a0`
- `0x1800043e0`
- `0x180004440`
- `0x1800044a0`
- `0x1800044e0`
- `0x180004520`
- `0x180004560`
- `0x18000459c`
- `0x180004614`
- `0x180004690`
- `0x180006890`
- `0x18000791c`
- `0x180007fa0`
- `0x180008658`
- `0x18000884c`
- `0x180008950`
- `0x18000896c`
- `0x18000899c`
- `0x180008ad0`
- `0x180008bbc`
- `0x180009904`
- `0x180009928`
- `0x180009b30`
- `0x180009b60`
- `0x18000a328`
- `0x18000a538`
- `0x18000a65c`
- `0x18000cca2`
- `0x18000ceae`

## callees

- `0x180001c90`

## pseudocode

```c
// attributes: thunk
void __fastcall operator delete(void *Block)
{
  ??3@YAXPEAX@Z(Block);
}

```

## disassembly

```asm
0x180001644  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
