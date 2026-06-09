# av_get_exact_bits_per_sample

- ea: `0x1800122b0`
- end: `0x1800123af`
- name: `av_get_exact_bits_per_sample`
- size: `255`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180009948`
- `0x180012240`
- `0x180012d38`

## callees

- `0x1800122b0`

## pseudocode

```c
__int64 __fastcall av_get_exact_bits_per_sample(int a1)
{
  __int64 result; // rax
  int v2; // ecx
  int v3; // ecx
  int v4; // ecx
  int v5; // ecx
  bool v6; // zf
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx

  if ( a1 > 69636 )
  {
    if ( a1 <= 69678 )
    {
      if ( a1 == 69678 )
        return 4;
      if ( a1 > 69661 )
      {
        v7 = a1 - 69664;
        if ( !v7 )
          return 4;
        v8 = v7 - 6;
        if ( !v8 )
          return 4;
        v9 = v8 - 4;
        if ( !v9 )
          return 4;
        v10 = v9 - 1;
        if ( !v10 )
          return 4;
        v6 = v10 == 2;
      }
      else
      {
        if ( a1 == 69661 )
          return 4;
        v2 = a1 - 69644;
        if ( !v2 )
          return 4;
        v3 = v2 - 2;
        if ( !v3 )
          return 4;
        v4 = v3 - 5;
        if ( !v4 )
          return 4;
        v5 = v4 - 4;
        if ( !v5 )
          return 4;
        v6 = v5 == 5;
      }
      if ( v6 )
        return 4;
      return 0;
    }
    if ( a1 > 86071 )
    {
      v15 = a1 - 86089;
      if ( v15 )
      {
        v16 = v15 - 1;
        if ( v16 )
        {
          v17 = v16 - 1;
          if ( v17 )
          {
            v18 = v17 - 1;
            if ( v18 )
              return v18 == 20;
          }
        }
      }
    }
    else
    {
      if ( a1 == 86071 )
        return 4;
      v11 = a1 - 81924;
      if ( v11 )
      {
        v12 = v11 - 2;
        if ( v12 )
        {
          v13 = v12 - 1;
          if ( v13 )
          {
            v14 = v13 - 1;
            if ( v14 )
            {
              if ( v14 == 4142 )
                return 4;
              return 0;
            }
          }
        }
      }
    }
    return 8;
  }
  if ( a1 == 69636 )
    return 4;
  switch ( a1 )
  {
    case 65536:
    case 65537:
    case 65538:
    case 65539:
    case 65554:
    case 65566:
      result = 16;
      break;
    case 65540:
    case 65541:
    case 65542:
    case 65543:
    case 65563:
    case 65571:
    case 65572:
      return 8;
    case 65544:
    case 65545:
    case 65546:
    case 65547:
    case 65556:
    case 65557:
    case 65565:
    case 65569:
    case 65570:
      result = 32;
      break;
    case 65548:
    case 65549:
    case 65550:
    case 65551:
    case 65552:
    case 65564:
      result = 24;
      break;
    case 65558:
    case 65559:
    case 65567:
    case 65568:
      result = 64;
      break;
    default:
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800122b0  mov     eax, 11004h
0x1800122b5  cmp     ecx, eax
0x1800122b7  jg      short loc_180012304
0x1800122b9  jz      loc_18001237E
0x1800122bf  add     ecx, 0FFFF0000h; switch 37 cases
0x1800122c5  cmp     ecx, 24h
0x1800122c8  ja      def_1800122EA; jumptable 00000001800122EA default case, cases 65553,65555,65560-65562
0x1800122ce  movsxd  rax, ecx
0x1800122d1  lea     rdx, cs:180000000h
0x1800122d8  movzx   eax, ds:(byte_1800123C8 - 180000000h)[rdx+rax]
0x1800122e0  mov     ecx, ds:(jpt_1800122EA - 180000000h)[rdx+rax*4]
0x1800122e7  add     rcx, rdx
0x1800122ea  jmp     rcx; switch jump
0x1800122ec  mov     eax, 10h; jumptable 00000001800122EA cases 65536-65539,65554,65566
0x1800122f1  retn
0x1800122f2  mov     eax, 18h; jumptable 00000001800122EA cases 65548-65552,65564
0x1800122f7  retn
0x1800122f8  mov     eax, 20h ; ' '; jumptable 00000001800122EA cases 65544-65547,65556,65557,65565,65569,65570
0x1800122fd  retn
0x1800122fe  mov     eax, 40h ; '@'; jumptable 00000001800122EA cases 65558,65559,65567,65568
0x180012303  retn
0x180012304  mov     eax, 1102Eh
0x180012309  cmp     ecx, eax
0x18001230b  jg      short loc_180012354
0x18001230d  jz      short loc_18001237E
0x18001230f  mov     eax, 1101Dh
0x180012314  cmp     ecx, eax
0x180012316  jg      short loc_180012336
0x180012318  jz      short loc_18001237E
0x18001231a  sub     ecx, 1100Ch
0x180012320  jz      short loc_18001237E
0x180012322  sub     ecx, 2
0x180012325  jz      short loc_18001237E
0x180012327  sub     ecx, 5
0x18001232a  jz      short loc_18001237E
0x18001232c  sub     ecx, 4
0x18001232f  jz      short loc_18001237E
0x180012331  cmp     ecx, 5
0x180012334  jmp     short loc_180012350
0x180012336  sub     ecx, 11020h
0x18001233c  jz      short loc_18001237E
0x18001233e  sub     ecx, 6
0x180012341  jz      short loc_18001237E
0x180012343  sub     ecx, 4
0x180012346  jz      short loc_18001237E
0x180012348  sub     ecx, 1
0x18001234b  jz      short loc_18001237E
0x18001234d  cmp     ecx, 2
0x180012350  jz      short loc_18001237E
0x180012352  jmp     short def_1800122EA; jumptable 00000001800122EA default case, cases 65553,65555,65560-65562
0x180012354  mov     eax, 15037h
0x180012359  cmp     ecx, eax
0x18001235b  jg      short loc_180012384
0x18001235d  jz      short loc_18001237E
0x18001235f  sub     ecx, 14004h
0x180012365  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x180012367  sub     ecx, 2
0x18001236a  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x18001236c  sub     ecx, 1
0x18001236f  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x180012371  sub     ecx, 1
0x180012374  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x180012376  cmp     ecx, 102Eh
0x18001237c  jnz     short def_1800122EA; jumptable 00000001800122EA default case, cases 65553,65555,65560-65562
0x18001237e  mov     eax, 4
0x180012383  retn
0x180012384  sub     ecx, 15049h
0x18001238a  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x18001238c  sub     ecx, 1
0x18001238f  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x180012391  sub     ecx, 1
0x180012394  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x180012396  sub     ecx, 1
0x180012399  jz      short loc_1800123A9; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x18001239b  cmp     ecx, 14h
0x18001239e  jz      short loc_1800123A3
0x1800123a0  xor     eax, eax; jumptable 00000001800122EA default case, cases 65553,65555,65560-65562
0x1800123a2  retn
0x1800123a3  mov     eax, 1
0x1800123a8  retn
0x1800123a9  mov     eax, 8; jumptable 00000001800122EA cases 65540-65543,65563,65571,65572
0x1800123ae  retn
```
