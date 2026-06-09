# avcodec_descriptor_next

- ea: `0x1800062d0`
- end: `0x180006311`
- name: `avcodec_descriptor_next`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800062d0`

## pseudocode

```c
__int64 *__fastcall avcodec_descriptor_next(__int64 a1)
{
  __int64 *result; // rax

  result = &qword_180026D20;
  if ( a1 )
  {
    if ( (unsigned __int64)((a1 - (__int64)&qword_180026D20) / 48) >= 0x211 )
    {
      return 0;
    }
    else
    {
      _mm_lfence();
      return (__int64 *)(a1 + 48);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800062d0  lea     rax, qword_180026D20
0x1800062d7  mov     r8, rcx
0x1800062da  test    rcx, rcx
0x1800062dd  jz      short locret_180006310
0x1800062df  sub     rcx, rax
0x1800062e2  mov     rax, 2AAAAAAAAAAAAAABh
0x1800062ec  imul    rcx
0x1800062ef  sar     rdx, 3
0x1800062f3  mov     rax, rdx
0x1800062f6  shr     rax, 3Fh
0x1800062fa  add     rdx, rax
0x1800062fd  cmp     rdx, 211h
0x180006304  jnb     short loc_18000630E
0x180006306  lfence
0x180006309  lea     rax, [r8+30h]
0x18000630d  retn
0x18000630e  xor     eax, eax
0x180006310  retn
```
