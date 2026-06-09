# __scrt_initialize_winrt

- ea: `0x140005e40`
- end: `0x140005e43`
- name: `__scrt_initialize_winrt`
- size: `3`
- prototype: `__int64 __fastcall(struct _exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140005810`
- `0x1400058e0`
- `0x140005ffc`

## pseudocode

```c
__int64 __fastcall _scrt_initialize_winrt(struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x140005e40  xor     eax, eax
0x140005e42  retn
```
