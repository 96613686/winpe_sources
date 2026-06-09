# __scrt_initialize_winrt

- ea: `0x140001a80`
- end: `0x140001a83`
- name: `__scrt_initialize_winrt`
- size: `3`
- prototype: `int __cdecl(struct _exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001a78`
- `0x140001a90`
- `0x140001d40`

## pseudocode

```c
__int64 __fastcall _scrt_initialize_winrt(struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140001a80  xor     eax, eax
0x140001a82  retn
```
