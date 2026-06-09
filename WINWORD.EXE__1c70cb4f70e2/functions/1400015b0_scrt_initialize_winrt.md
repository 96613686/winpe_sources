# __scrt_initialize_winrt

- ea: `0x1400015b0`
- end: `0x1400015b3`
- name: `__scrt_initialize_winrt`
- size: `3`
- prototype: `int __cdecl(struct _exception *)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400017f0`
- `0x1400018c0`
- `0x140002330`

## pseudocode

```c
__int64 __fastcall _scrt_initialize_winrt(struct _exception *a1)
{
  return 0;
}

```

## disassembly

```asm
0x1400015b0  xor     eax, eax
0x1400015b2  retn
```
