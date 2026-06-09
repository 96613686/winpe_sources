# _tlgCreate1Sz_wchar_t

- ea: `0x18000e150`
- end: `0x18000e187`
- name: `_tlgCreate1Sz_wchar_t`
- size: `55`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800070d0`
- `0x1800101c0`
- `0x180014510`
- `0x180014740`

## callees

- `0x18000e150`

## pseudocode

```c
__int64 __fastcall tlgCreate1Sz_wchar_t(__int64 a1, int *a2)
{
  __int64 v2; // rax
  __int64 result; // rax

  if ( a2 )
  {
    v2 = -1;
    do
      ++v2;
    while ( *((_WORD *)a2 + v2) );
    result = (unsigned int)(2 * v2 + 2);
  }
  else
  {
    a2 = &dword_18001E7A4;
    result = 2;
  }
  *(_QWORD *)a1 = a2;
  *(_DWORD *)(a1 + 8) = result;
  *(_DWORD *)(a1 + 12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e150  xor     r8d, r8d
0x18000e153  test    rdx, rdx
0x18000e156  jz      short loc_18000E179
0x18000e158  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e15c  inc     rax
0x18000e15f  cmp     [rdx+rax*2], r8w
0x18000e164  jnz     short loc_18000E15C
0x18000e166  lea     eax, ds:2[rax*2]
0x18000e16d  mov     [rcx], rdx
0x18000e170  mov     [rcx+8], eax
0x18000e173  mov     [rcx+0Ch], r8d
0x18000e177  retn
0x18000e179  lea     rdx, dword_18001E7A4
0x18000e180  mov     eax, 2
0x18000e185  jmp     short loc_18000E16D
```
