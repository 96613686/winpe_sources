# _tlgCreate1Sz_char

- ea: `0x140001990`
- end: `0x1400019c0`
- name: `_tlgCreate1Sz_char`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001a288`

## callees

- `0x140001990`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_char(__int64 a1, __int16 *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( *((_BYTE *)a2 + v2) );
    result = (unsigned int)(v2 + 1);
  }
  else
  {
    a2 = word_14001ECB2;
    result = 1;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x140001990  test    rdx, rdx
0x140001993  jz      short loc_1400019A6
0x140001995  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001999  inc     rax
0x14000199c  cmp     byte ptr [rdx+rax], 0
0x1400019a0  jnz     short loc_140001999
0x1400019a2  inc     eax
0x1400019a4  jmp     short loc_1400019B2
0x1400019a6  lea     rdx, word_14001ECB2
0x1400019ad  mov     eax, 1
0x1400019b2  mov     [rcx], rdx
0x1400019b5  mov     [rcx+8], eax
0x1400019b8  mov     dword ptr [rcx+0Ch], 0
0x1400019bf  retn
```
