# SmInstanceSetup

- ea: `0x140007010`
- end: `0x14000701f`
- name: `SmInstanceSetup`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 __fastcall SmInstanceSetup(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  result = 3223060495LL;
  if ( a3 != 20 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140007010  xor     ecx, ecx
0x140007012  mov     eax, 0C01C000Fh
0x140007017  cmp     r8d, 14h
0x14000701b  cmovnz  eax, ecx
0x14000701e  retn
```
