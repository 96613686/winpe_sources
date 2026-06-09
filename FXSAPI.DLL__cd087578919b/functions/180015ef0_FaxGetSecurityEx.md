# FaxGetSecurityEx

- ea: `0x180015ef0`
- end: `0x180015efb`
- name: `FaxGetSecurityEx`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800145a0`

## pseudocode

```c
__int64 __fastcall FaxGetSecurityEx(_DWORD *a1, int a2, void **a3)
{
  return FaxGetSecurityExInternal(a1, a2, a3, 0x20000u);
}

```

## disassembly

```asm
0x180015ef0  mov     r9d, 20000h; unsigned int
0x180015ef6  jmp     ?FaxGetSecurityExInternal@@YAHPEAXKPEAPEAXK@Z; FaxGetSecurityExInternal(void *,ulong,void * *,ulong)
```
