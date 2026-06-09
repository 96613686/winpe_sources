# memset_0

- ea: `0x140002fbc`
- end: `0x140002fc2`
- name: `memset_0`
- size: `6`
- prototype: `void *__cdecl(void *, int Val, size_t Size)`
- caller_count: `30`
- callee_count: `0`
- tags: ``

## callers

- `0x1400029dc`
- `0x140003df4`
- `0x140004090`
- `0x140007298`
- `0x140007888`
- `0x140007cf0`
- `0x140008220`
- `0x14000a1ac`
- `0x14000bd00`
- `0x14000be08`
- `0x14000d6ec`
- `0x14000dcc8`
- `0x14000e154`
- `0x14000e49c`
- `0x14000fa90`
- `0x140010778`
- `0x140010b80`
- `0x140013534`
- `0x140013858`
- `0x140014b48`
- `0x140014d88`
- `0x1400150c0`
- `0x140015604`
- `0x1400170a4`
- `0x1400190d0`
- `0x14001a5ac`
- `0x14001aaa4`
- `0x14001b130`
- `0x14001b4a8`
- `0x14001c4a8`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memset` at `0x140002fbc`

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
0x140002fbc  jmp     cs:__imp_memset
```
