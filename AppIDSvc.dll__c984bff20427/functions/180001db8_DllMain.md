# DllMain

- ea: `0x180001db8`
- end: `0x180001dbe`
- name: `DllMain`
- size: `6`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001644`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  return 1;
}

```

## disassembly

```asm
0x180001db8  mov     eax, 1
0x180001dbd  retn
```
