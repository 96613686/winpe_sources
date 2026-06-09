# FaxSetSecurityEx2

- ea: `0x180016110`
- end: `0x18001611b`
- name: `FaxSetSecurityEx2`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014908`

## pseudocode

```c
__int64 __fastcall FaxSetSecurityEx2(_DWORD *a1, int a2, void *a3)
{
  return FaxSetSecurityInternal(a1, a2, a3, 0x30000u);
}

```

## disassembly

```asm
0x180016110  mov     r9d, 30000h; unsigned int
0x180016116  jmp     ?FaxSetSecurityInternal@@YAHPEAXK0K@Z; FaxSetSecurityInternal(void *,ulong,void *,ulong)
```
