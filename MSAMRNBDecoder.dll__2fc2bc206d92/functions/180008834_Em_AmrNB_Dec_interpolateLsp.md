# Em_AmrNB_Dec_interpolateLsp

- ea: `0x180008834`
- end: `0x180008922`
- name: `Em_AmrNB_Dec_interpolateLsp`
- size: `238`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180008078`
- `0x180008e48`

## callees

- `0x180008834`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_interpolateLsp(int a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  __int64 i; // rax
  __int16 v6; // cx
  __int16 v7; // dx
  __int64 j; // r11
  __int16 v9; // cx
  __int64 k; // rdx
  __int16 v11; // dx

  v3 = 0;
  if ( a1 == 7 )
  {
    for ( i = 0; i != 10; *(_WORD *)(a2 + 2 * i) = v6 )
    {
      v6 = (*(__int16 *)(a3 + 2 * i) >> 1) + (*(__int16 *)(a2 + 2 * i + 24) >> 1);
      ++i;
    }
    do
    {
      v7 = *(_WORD *)(a2 + 2 * v3 + 68);
      *(_WORD *)(a2 + 2 * v3 + 46) = (v7 >> 1) + (*(__int16 *)(a2 + 2 * v3 + 24) >> 1);
      *(_WORD *)(a3 + 2 * v3++) = v7;
    }
    while ( v3 != 10 );
  }
  else
  {
    for ( j = 0; j != 10; *(_WORD *)(a2 + 2 * j) = v9 )
    {
      v9 = *(_WORD *)(a3 + 2 * j) + (*(__int16 *)(a2 + 2 * j + 68) >> 2) - (*(__int16 *)(a3 + 2 * j) >> 2);
      ++j;
    }
    for ( k = 0; k != 10; ++k )
      *(_WORD *)(a2 + 2 * k + 24) = (*(__int16 *)(a3 + 2 * k) >> 1) + (*(__int16 *)(a2 + 2 * k + 68) >> 1);
    do
    {
      v11 = *(_WORD *)(a2 + 2 * v3 + 68);
      *(_WORD *)(a2 + 2 * v3 + 46) = v11 + (*(__int16 *)(a3 + 2 * v3) >> 2) - (v11 >> 2);
      *(_WORD *)(a3 + 2 * v3++) = v11;
    }
    while ( v3 != 10 );
  }
  return 0;
}

```

## disassembly

```asm
0x180008834  xor     r9d, r9d
0x180008837  mov     r10, rdx
0x18000883a  cmp     ecx, 7
0x18000883d  jnz     short loc_180008899
0x18000883f  mov     eax, r9d
0x180008842  movzx   ecx, word ptr [r10+rax*2+18h]
0x180008848  lea     rdx, [rax+1]
0x18000884c  movzx   eax, word ptr [r8+rax*2]
0x180008851  sar     ax, 1
0x180008854  sar     cx, 1
0x180008857  add     cx, ax
0x18000885a  mov     rax, rdx
0x18000885d  mov     [r10+rdx*2], cx
0x180008862  cmp     rdx, 0Ah
0x180008866  jnz     short loc_180008842
0x180008868  movzx   edx, word ptr [r10+r9*2+44h]
0x18000886e  movzx   ecx, word ptr [r10+r9*2+18h]
0x180008874  movzx   eax, dx
0x180008877  sar     ax, 1
0x18000887a  sar     cx, 1
0x18000887d  add     cx, ax
0x180008880  mov     [r10+r9*2+2Eh], cx
0x180008886  mov     [r8+r9*2], dx
0x18000888b  inc     r9
0x18000888e  cmp     r9, 0Ah
0x180008892  jnz     short loc_180008868
0x180008894  jmp     loc_18000891F
0x180008899  mov     r11, r9
0x18000889c  movzx   eax, word ptr [r8+r11*2]
0x1800088a1  lea     rdx, [r11+1]
0x1800088a5  movzx   ecx, word ptr [r10+r11*2+44h]
0x1800088ab  sar     cx, 2
0x1800088af  sar     ax, 2
0x1800088b3  sub     cx, ax
0x1800088b6  add     cx, [r8+r11*2]
0x1800088bb  mov     r11, rdx
0x1800088be  mov     [r10+rdx*2], cx
0x1800088c3  cmp     rdx, 0Ah
0x1800088c7  jnz     short loc_18000889C
0x1800088c9  mov     rdx, r9
0x1800088cc  movzx   eax, word ptr [r8+rdx*2]
0x1800088d1  movzx   ecx, word ptr [r10+rdx*2+44h]
0x1800088d7  sar     cx, 1
0x1800088da  sar     ax, 1
0x1800088dd  add     cx, ax
0x1800088e0  mov     [r10+rdx*2+18h], cx
0x1800088e6  inc     rdx
0x1800088e9  cmp     rdx, 0Ah
0x1800088ed  jnz     short loc_1800088CC
0x1800088ef  movzx   edx, word ptr [r10+r9*2+44h]
0x1800088f5  movzx   ecx, word ptr [r8+r9*2]
0x1800088fa  movzx   eax, dx
0x1800088fd  sar     cx, 2
0x180008901  sar     ax, 2
0x180008905  sub     cx, ax
0x180008908  add     cx, dx
0x18000890b  mov     [r10+r9*2+2Eh], cx
0x180008911  mov     [r8+r9*2], dx
0x180008916  inc     r9
0x180008919  cmp     r9, 0Ah
0x18000891d  jnz     short loc_1800088EF
0x18000891f  xor     eax, eax
0x180008921  retn
```
