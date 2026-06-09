# GetDllMajorVersion(void)

- ea: `0x180005a30`
- end: `0x180005a36`
- name: `?GetDllMajorVersion@@YA?AW4tagOEDLLVERSION@@XZ`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting`

## pseudocode

```c
__int64 GetDllMajorVersion()
{
  return 1;
}

```

## disassembly

```asm
0x180005a30  mov     eax, 1
0x180005a35  retn
```
