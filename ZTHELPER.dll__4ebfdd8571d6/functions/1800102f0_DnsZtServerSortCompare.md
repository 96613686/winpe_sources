# DnsZtServerSortCompare

- ea: `0x1800102f0`
- end: `0x1800102f8`
- name: `DnsZtServerSortCompare`
- size: `8`
- prototype: `__int64 __fastcall(_WORD *, _WORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010274`

## pseudocode

```c
__int64 __fastcall DnsZtServerSortCompare(_WORD *a1, _WORD *a2)
{
  return DnsZtServerCompare(a1, a2, 0);
}

```

## disassembly

```asm
0x1800102f0  xor     r8d, r8d
0x1800102f3  jmp     DnsZtServerCompare
```
