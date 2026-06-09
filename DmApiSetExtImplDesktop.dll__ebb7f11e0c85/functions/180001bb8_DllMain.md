# DllMain

- ea: `0x180001bb8`
- end: `0x180001bbe`
- name: `DllMain`
- size: `6`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001474`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  return 1;
}

```

## disassembly

```asm
0x180001bb8  mov     eax, 1
0x180001bbd  retn
```
