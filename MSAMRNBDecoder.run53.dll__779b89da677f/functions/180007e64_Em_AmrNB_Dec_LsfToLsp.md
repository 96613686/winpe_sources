# Em_AmrNB_Dec_LsfToLsp

- ea: `0x180007e64`
- end: `0x180007ead`
- name: `Em_AmrNB_Dec_LsfToLsp`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180003800`
- `0x1800051e0`
- `0x180008078`
- `0x180008e48`

## callees

- `0x180007e64`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_LsfToLsp(__int64 a1, __int64 a2)
{
  __int64 i; // r8
  __int64 v3; // rax

  for ( i = 0; i != 10; ++i )
  {
    v3 = (__int64)*(__int16 *)(a1 + 2 * i) >> 8;
    *(_WORD *)(a2 + 2 * i) = Em_AmrNB_Dec_LsfToLspTable[v3]
                           + ((*(unsigned __int8 *)(a1 + 2 * i)
                             * (__int16)(Em_AmrNB_Dec_LsfToLspTable[v3 + 1] - Em_AmrNB_Dec_LsfToLspTable[v3])) >> 8);
  }
  return 0;
}

```

## disassembly

```asm
0x180007e64  mov     r9, rdx
0x180007e67  lea     r11, Em_AmrNB_Dec_LsfToLspTable
0x180007e6e  mov     r10, rcx
0x180007e71  xor     r8d, r8d
0x180007e74  movsx   rax, word ptr [r10+r8*2]
0x180007e79  sar     rax, 8
0x180007e7d  movzx   edx, word ptr [r11+rax*2]
0x180007e82  movzx   eax, word ptr [r11+rax*2+2]
0x180007e88  sub     ax, dx
0x180007e8b  movsx   ecx, ax
0x180007e8e  movzx   eax, byte ptr [r10+r8*2]
0x180007e93  imul    ecx, eax
0x180007e96  sar     ecx, 8
0x180007e99  add     cx, dx
0x180007e9c  mov     [r9+r8*2], cx
0x180007ea1  inc     r8
0x180007ea4  cmp     r8, 0Ah
0x180007ea8  jnz     short loc_180007E74
0x180007eaa  xor     eax, eax
0x180007eac  retn
```
