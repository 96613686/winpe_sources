# __std_terminate

- ea: `0x18002c870`
- end: `0x18002c876`
- name: `__std_terminate`
- size: `6`
- prototype: ``
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x180008752`
- `0x18000d1d2`
- `0x18000e920`
- `0x18001091a`
- `0x180012134`
- `0x180012fb6`
- `0x180013eba`
- `0x180020fa8`
- `0x180021c36`
- `0x180021fa6`
- `0x1800225d7`
- `0x1800226ef`
- `0x180022baa`
- `0x1800238f6`
- `0x180023c6a`
- `0x18002423e`
- `0x180026c9c`
- `0x180027888`
- `0x18002a8d2`

## import_xrefs

- `VCRUNTIME140!__std_terminate` at `0x18002c870`

## pseudocode

```c
// attributes: thunk
void __noreturn _std_terminate()
{
  __std_terminate();
}

```

## disassembly

```asm
0x18002c870  jmp     cs:__imp___std_terminate
```
