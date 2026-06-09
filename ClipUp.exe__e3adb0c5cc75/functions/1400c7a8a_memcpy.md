# memcpy

- ea: `0x1400c7a8a`
- end: `0x1400c7a90`
- name: `memcpy`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `59`
- callee_count: `0`
- tags: ``

## callers

- `0x140009e18`
- `0x14000a598`
- `0x14000aeb8`
- `0x140013c84`
- `0x14001b4d0`
- `0x14001b6e8`
- `0x14001e124`
- `0x1400234d0`
- `0x1400240ac`
- `0x14002d5f4`
- `0x1400332c8`
- `0x1400371a0`
- `0x1400380a0`
- `0x1400381d8`
- `0x140038310`
- `0x140038448`
- `0x140038580`
- `0x1400386b8`
- `0x14003882c`
- `0x140038964`
- `0x140038b7c`
- `0x140038cf0`
- `0x140038e64`
- `0x140038f74`
- `0x1400390c8`
- `0x14003979c`
- `0x14003daec`
- `0x14003dcb8`
- `0x14008f588`
- `0x140091188`
- `0x140098488`
- `0x140098ac0`
- `0x14009ca08`
- `0x14009cabc`
- `0x14009cb70`
- `0x14009cca8`
- `0x14009cd5c`
- `0x14009d984`
- `0x14009df60`
- `0x1400a48a4`
- `0x1400a4aec`
- `0x1400a5298`
- `0x1400a57e0`
- `0x1400a61f4`
- `0x1400a7040`
- `0x1400a77f4`
- `0x1400a9a20`
- `0x1400abcc0`
- `0x1400ae234`
- `0x1400b0838`

## import_xrefs

- `msvcrt!memcpy` at `0x1400c7a8a`

## pseudocode

```c
// attributes: thunk
void *__cdecl memcpy(void *a1, const void *Src, size_t Size)
{
  return __imp_memcpy(a1, Src, Size);
}

```

## disassembly

```asm
0x1400c7a8a  jmp     cs:__imp_memcpy
```
