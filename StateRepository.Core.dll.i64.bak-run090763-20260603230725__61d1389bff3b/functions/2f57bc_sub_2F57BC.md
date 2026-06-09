# sub_2F57BC

- ea: `0x2f57bc`
- end: `0x2f57c1`
- name: `sub_2F57BC`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_2F57BC(__int64 a1, __int64 a2, char a3, _BYTE *a4)
{
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  *a4 += a3;
  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x2f57bc  add     [rcx], dl
0x2f57be  or      al, [rax]
0x2f57c0  retf
```
