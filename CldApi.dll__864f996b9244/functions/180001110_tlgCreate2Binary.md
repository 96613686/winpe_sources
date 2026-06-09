# _tlgCreate2Binary

- ea: `0x180001110`
- end: `0x18000112f`
- name: `_tlgCreate2Binary`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180011e18`

## pseudocode

```c
__int64 __fastcall tlgCreate2Binary(__int64 a1, __int64 a2, int a3)
{
  __int64 result; // rax

  result = a1 + 24;
  *(_QWORD *)(a1 + 8) = 2;
  *(_QWORD *)a1 = a1 + 24;
  *(_QWORD *)(a1 + 16) = a2;
  *(_DWORD *)(a1 + 24) = a3;
  *(_DWORD *)(a1 + 28) = 0;
  return result;
}

```

## disassembly

```asm
0x180001110  lea     rax, [rcx+18h]
0x180001114  mov     qword ptr [rcx+8], 2
0x18000111c  mov     [rcx], rax
0x18000111f  mov     [rcx+10h], rdx
0x180001123  mov     [rcx+18h], r8d
0x180001127  mov     dword ptr [rcx+1Ch], 0
0x18000112e  retn
```
