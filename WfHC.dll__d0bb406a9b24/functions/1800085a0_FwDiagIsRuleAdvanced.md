# FwDiagIsRuleAdvanced

- ea: `0x1800085a0`
- end: `0x1800086e8`
- name: `FwDiagIsRuleAdvanced`
- size: `328`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180007b40`
- `0x180007c80`
- `0x180007d60`
- `0x180008040`

## callees

- `0x1800085a0`

## pseudocode

```c
__int64 __fastcall FwDiagIsRuleAdvanced(__int64 a1)
{
  int v2; // r8d
  int v3; // ecx
  __int16 v4; // ax
  bool v5; // zf
  unsigned int v6; // eax

  if ( *(_QWORD *)(a1 + 312) )
    return 1;
  v2 = *(unsigned __int16 *)(a1 + 292);
  v3 = 393;
  if ( (v2 & 0x80) == 0 )
    v3 = 385;
  if ( *(_QWORD *)(a1 + 280)
    || (unsigned int)(*(_DWORD *)(a1 + 288) - 2) > 1
    || (~v3 & v2) != 0
    || *(_QWORD *)(a1 + 296)
    || *(_QWORD *)(a1 + 304)
    || *(_DWORD *)(a1 + 320) )
  {
    return 1;
  }
  v4 = *(_WORD *)(a1 + 48);
  if ( v4 != 6 )
  {
    if ( !*(_QWORD *)(a1 + 272) )
    {
      v5 = v4 == 17;
      goto LABEL_15;
    }
    if ( v4 != 17 )
    {
      v5 = v4 == 256;
LABEL_15:
      if ( !v5 )
        return 1;
    }
  }
  if ( *(_DWORD *)(a1 + 64) <= 1u
    && (*(_DWORD *)(a1 + 64) != 1 || **(_WORD **)(a1 + 72) == *(_WORD *)(*(_QWORD *)(a1 + 72) + 2LL))
    && !*(_WORD *)(a1 + 56)
    && *(_DWORD *)(a1 + 88) <= 1u
    && (*(_DWORD *)(a1 + 88) != 1 || **(_WORD **)(a1 + 96) == *(_WORD *)(*(_QWORD *)(a1 + 96) + 2LL))
    && !*(_WORD *)(a1 + 80)
    && !*(_DWORD *)(a1 + 104)
    && !*(_DWORD *)(a1 + 108)
    && !*(_DWORD *)(a1 + 112)
    && !*(_DWORD *)(a1 + 144)
    && !*(_DWORD *)(a1 + 128)
    && !*(_DWORD *)(a1 + 160)
    && !*(_DWORD *)(a1 + 248)
    && !*(_DWORD *)(a1 + 264) )
  {
    v6 = *(_DWORD *)(a1 + 176);
    if ( v6 <= 1 && v6 == *(_DWORD *)(a1 + 180) )
      return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800085a0  cmp     qword ptr [rcx+138h], 0
0x1800085a8  mov     rdx, rcx
0x1800085ab  jnz     loc_1800086E2
0x1800085b1  movzx   r8d, word ptr [rcx+124h]
0x1800085b9  mov     eax, 80h
0x1800085be  test    ax, r8w
0x1800085c2  mov     ecx, 189h
0x1800085c7  mov     eax, 181h
0x1800085cc  cmovbe  ecx, eax
0x1800085cf  cmp     qword ptr [rdx+118h], 0
0x1800085d7  jnz     loc_1800086E2
0x1800085dd  mov     eax, [rdx+120h]
0x1800085e3  sub     eax, 2
0x1800085e6  cmp     eax, 1
0x1800085e9  ja      loc_1800086E2
0x1800085ef  not     ecx
0x1800085f1  test    r8d, ecx
0x1800085f4  jnz     loc_1800086E2
0x1800085fa  cmp     qword ptr [rdx+128h], 0
0x180008602  jnz     loc_1800086E2
0x180008608  cmp     qword ptr [rdx+130h], 0
0x180008610  jnz     loc_1800086E2
0x180008616  cmp     dword ptr [rdx+140h], 0
0x18000861d  jnz     loc_1800086E2
0x180008623  movzx   eax, word ptr [rdx+30h]
0x180008627  cmp     ax, 6
0x18000862b  jz      short loc_180008651
0x18000862d  cmp     qword ptr [rdx+110h], 0
0x180008635  jnz     short loc_18000863D
0x180008637  cmp     ax, 11h
0x18000863b  jmp     short loc_18000864B
0x18000863d  cmp     ax, 11h
0x180008641  jz      short loc_180008651
0x180008643  mov     ecx, 100h
0x180008648  cmp     ax, cx
0x18000864b  jnz     loc_1800086E2
0x180008651  cmp     dword ptr [rdx+40h], 1
0x180008655  ja      loc_1800086E2
0x18000865b  jnz     short loc_18000866A
0x18000865d  mov     rcx, [rdx+48h]
0x180008661  movzx   eax, word ptr [rcx+2]
0x180008665  cmp     [rcx], ax
0x180008668  jnz     short loc_1800086E2
0x18000866a  cmp     word ptr [rdx+38h], 0
0x18000866f  jnz     short loc_1800086E2
0x180008671  cmp     dword ptr [rdx+58h], 1
0x180008675  ja      short loc_1800086E2
0x180008677  jnz     short loc_180008686
0x180008679  mov     rcx, [rdx+60h]
0x18000867d  movzx   eax, word ptr [rcx+2]
0x180008681  cmp     [rcx], ax
0x180008684  jnz     short loc_1800086E2
0x180008686  cmp     word ptr [rdx+50h], 0
0x18000868b  jnz     short loc_1800086E2
0x18000868d  cmp     dword ptr [rdx+68h], 0
0x180008691  jnz     short loc_1800086E2
0x180008693  cmp     dword ptr [rdx+6Ch], 0
0x180008697  jnz     short loc_1800086E2
0x180008699  cmp     dword ptr [rdx+70h], 0
0x18000869d  jnz     short loc_1800086E2
0x18000869f  cmp     dword ptr [rdx+90h], 0
0x1800086a6  jnz     short loc_1800086E2
0x1800086a8  cmp     dword ptr [rdx+80h], 0
0x1800086af  jnz     short loc_1800086E2
0x1800086b1  cmp     dword ptr [rdx+0A0h], 0
0x1800086b8  jnz     short loc_1800086E2
0x1800086ba  cmp     dword ptr [rdx+0F8h], 0
0x1800086c1  jnz     short loc_1800086E2
0x1800086c3  cmp     dword ptr [rdx+108h], 0
0x1800086ca  jnz     short loc_1800086E2
0x1800086cc  mov     eax, [rdx+0B0h]
0x1800086d2  cmp     eax, 1
0x1800086d5  ja      short loc_1800086E2
0x1800086d7  cmp     eax, [rdx+0B4h]
0x1800086dd  jnz     short loc_1800086E2
0x1800086df  xor     eax, eax
0x1800086e1  retn
0x1800086e2  mov     eax, 1
0x1800086e7  retn
```
