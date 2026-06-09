# Em_AmrNB_Dec_ReorderLsf

- ea: `0x180008048`
- end: `0x180008072`
- name: `Em_AmrNB_Dec_ReorderLsf`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800051e0`
- `0x180008078`
- `0x180008e48`

## callees

- `0x180008048`

## pseudocode

```c
__int16 __fastcall Em_AmrNB_Dec_ReorderLsf(__int64 a1)
{
  __int64 v1; // rdx
  __int16 result; // ax

  v1 = 0;
  result = 205;
  do
  {
    if ( *(__int16 *)(a1 + 2 * v1) >= result )
      result = *(_WORD *)(a1 + 2 * v1);
    else
      *(_WORD *)(a1 + 2 * v1) = result;
    result += 205;
    ++v1;
  }
  while ( v1 != 10 );
  return result;
}

```

## disassembly

```asm
0x180008048  mov     r8d, 0CDh
0x18000804e  xor     edx, edx
0x180008050  movzx   eax, r8w
0x180008054  cmp     [rcx+rdx*2], ax
0x180008058  jge     short loc_180008060
0x18000805a  mov     [rcx+rdx*2], ax
0x18000805e  jmp     short loc_180008064
0x180008060  movzx   eax, word ptr [rcx+rdx*2]
0x180008064  add     ax, r8w
0x180008068  inc     rdx
0x18000806b  cmp     rdx, 0Ah
0x18000806f  jnz     short loc_180008054
0x180008071  retn
```
