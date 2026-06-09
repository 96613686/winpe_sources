# sub_261DCB

- ea: `0x261dcb`
- end: `0x261dd0`
- name: `sub_261DCB`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall sub_261DCB(__int64 a1, __int64 a2, char a3)
{
  _BYTE *v3; // rax
  _BYTE *v4; // rbx

  *v4 += a3;
  return *v3 | (unsigned __int8)v3;
}

```

## disassembly

```asm
0x261dcb  add     [rbx], dl
0x261dcd  or      al, [rax]
0x261dcf  retn
```
