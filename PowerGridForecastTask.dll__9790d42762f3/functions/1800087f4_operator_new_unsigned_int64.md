# operator new[](unsigned __int64)

- ea: `0x1800087f4`
- end: `0x1800087f9`
- name: `??_U@YAPEAX_K@Z`
- size: `5`
- prototype: `void *__fastcall(size_t)`
- caller_count: `11`
- callee_count: `1`
- tags: ``

## callers

- `0x180005a24`
- `0x180009240`
- `0x180009374`
- `0x1800094c8`
- `0x180011d18`
- `0x180011ec0`
- `0x180012068`
- `0x180012268`
- `0x18001ca40`
- `0x18001cb44`
- `0x18001f2b4`

## callees

- `0x1800020c4`

## pseudocode

```c
// attributes: thunk
void *__fastcall operator new[](size_t a1)
{
  return operator new(a1);
}

```

## disassembly

```asm
0x1800087f4  jmp     ??2@YAPEAX_K@Z; operator new(unsigned __int64)
```
