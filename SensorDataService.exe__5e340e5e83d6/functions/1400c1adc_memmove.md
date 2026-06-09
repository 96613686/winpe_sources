# memmove

- ea: `0x1400c1adc`
- end: `0x1400c1ae2`
- name: `memmove`
- size: `6`
- prototype: `void *__cdecl(void *, const void *Src, size_t Size)`
- caller_count: `32`
- callee_count: `0`
- tags: ``

## callers

- `0x14000ca68`
- `0x140015640`
- `0x140015864`
- `0x14002721c`
- `0x14002e204`
- `0x140034704`
- `0x14003da18`
- `0x14004a1ac`
- `0x14004d9b0`
- `0x1400504c8`
- `0x14005f338`
- `0x14005f484`
- `0x14005f5e0`
- `0x14005f73c`
- `0x14005f8a8`
- `0x14005fa10`
- `0x1400bb160`
- `0x1400bb2e4`
- `0x1400bbb60`
- `0x1400bc3b8`
- `0x1400bc4fc`
- `0x1400bc678`
- `0x1400bc7fc`
- `0x1400bc98c`
- `0x1400bcce0`
- `0x1400bdb60`
- `0x1400bdd74`
- `0x1400be64c`
- `0x1400be9f0`
- `0x1400beaec`
- `0x1400c1524`
- `0x1400c18c8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!memmove` at `0x1400c1adc`

## pseudocode

```c
// attributes: thunk
void *__cdecl memmove(void *a1, const void *Src, size_t Size)
{
  return __imp_memmove(a1, Src, Size);
}

```

## disassembly

```asm
0x1400c1adc  jmp     cs:__imp_memmove
```
