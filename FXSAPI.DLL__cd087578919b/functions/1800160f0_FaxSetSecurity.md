# FaxSetSecurity

- ea: `0x1800160f0`
- end: `0x1800160fb`
- name: `FaxSetSecurity`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180014908`

## pseudocode

```c
__int64 __fastcall FaxSetSecurity(_DWORD *a1, int a2, void *a3)
{
  return FaxSetSecurityInternal(a1, a2, a3, 0x20000u);
}

```

## disassembly

```asm
0x1800160f0  mov     r9d, 20000h; unsigned int
0x1800160f6  jmp     ?FaxSetSecurityInternal@@YAHPEAXK0K@Z; FaxSetSecurityInternal(void *,ulong,void *,ulong)
```
