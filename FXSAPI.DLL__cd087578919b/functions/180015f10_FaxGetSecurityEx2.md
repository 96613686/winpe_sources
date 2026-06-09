# FaxGetSecurityEx2

- ea: `0x180015f10`
- end: `0x180015f1b`
- name: `FaxGetSecurityEx2`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800145a0`

## pseudocode

```c
__int64 __fastcall FaxGetSecurityEx2(_DWORD *a1, int a2, void **a3)
{
  return FaxGetSecurityExInternal(a1, a2, a3, 0x30000u);
}

```

## disassembly

```asm
0x180015f10  mov     r9d, 30000h; unsigned int
0x180015f16  jmp     ?FaxGetSecurityExInternal@@YAHPEAXKPEAPEAXK@Z; FaxGetSecurityExInternal(void *,ulong,void * *,ulong)
```
