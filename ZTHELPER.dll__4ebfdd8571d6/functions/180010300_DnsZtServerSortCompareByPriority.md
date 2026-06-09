# DnsZtServerSortCompareByPriority

- ea: `0x180010300`
- end: `0x18001030b`
- name: `DnsZtServerSortCompareByPriority`
- size: `11`
- prototype: `__int64 __fastcall(_WORD *, _WORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180010274`

## pseudocode

```c
__int64 __fastcall DnsZtServerSortCompareByPriority(_WORD *a1, _WORD *a2)
{
  return DnsZtServerCompare(a1, a2, 1);
}

```

## disassembly

```asm
0x180010300  mov     r8d, 1
0x180010306  jmp     DnsZtServerCompare
```
