# memset_0

- ea: `0x18001ae8e`
- end: `0x18001ae94`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `29`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e00`
- `0x1800030a0`
- `0x180003170`
- `0x180003270`
- `0x180003430`
- `0x180003978`
- `0x180003a08`
- `0x1800046e4`
- `0x180007b50`
- `0x1800095c0`
- `0x180009e90`
- `0x18000c340`
- `0x18000c420`
- `0x18000c9c0`
- `0x18000f3e0`
- `0x180010d00`
- `0x1800114ac`
- `0x180011a90`
- `0x180012bfc`
- `0x1800130c8`
- `0x180015980`
- `0x180015d10`
- `0x1800163b4`
- `0x180016a08`
- `0x180016b4c`
- `0x180017024`
- `0x180017600`
- `0x1800177d0`
- `0x180019e00`

## import_xrefs

- `msvcrt!memset` at `0x18001ae8e`

## pseudocode

```c
// attributes: thunk
void *__cdecl memset_0(void *a1, int Val, size_t Size)
{
  return memset(a1, Val, Size);
}

```

## disassembly

```asm
0x18001ae8e  jmp     cs:__imp_memset
```
