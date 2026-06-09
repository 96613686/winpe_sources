# KerbMapKerbError(long)

- ea: `0x180007ee0`
- end: `0x180007fbe`
- name: `?KerbMapKerbError@@YAJJ@Z`
- size: `222`
- prototype: `__int64 __fastcall(int)`
- caller_count: `18`
- callee_count: `1`
- tags: ``

## callers

- `0x180009d60`
- `0x180009fa0`
- `0x18000a1b0`
- `0x18000a3d0`
- `0x18000a650`
- `0x18000a920`
- `0x18000aed0`
- `0x18000b5b0`
- `0x18000b790`
- `0x18000be90`
- `0x18000c2d0`
- `0x18000c8c0`
- `0x18000cf30`
- `0x180014cec`
- `0x180014dd0`
- `0x180015010`
- `0x180015ce0`
- `0x180016190`

## callees

- `0x180007ee0`

## pseudocode

```c
__int64 __fastcall KerbMapKerbError(int a1)
{
  __int64 result; // rax

  if ( !a1 )
    return 0;
  if ( a1 > 5 )
  {
    switch ( a1 )
    {
      case 6:
        result = 3221225572LL;
        break;
      case 7:
        result = 3221225867LL;
        break;
      case 12:
        result = 3221225582LL;
        break;
      case 14:
      case 80:
        result = 3221226237LL;
        break;
      case 16:
        result = 3221225659LL;
        break;
      case 18:
        result = 3221225586LL;
        break;
      case 23:
        result = 3221225585LL;
        break;
      case 24:
      case 25:
      case 41:
        result = 3221225578LL;
        break;
      case 27:
      case 69:
        result = 3221226504LL;
        break;
      case 28:
        result = 3221225872LL;
        break;
      case 29:
      case 68:
        result = 3221225566LL;
        break;
      case 32:
      case 33:
      case 37:
      case 90:
        result = 3221225779LL;
        break;
      case 35:
        result = 2148074274LL;
        break;
      case 39:
      case 40:
      case 71:
        result = 3221225485LL;
        break;
      case 45:
        result = 3221226274LL;
        break;
      case 52:
        result = 3221225990LL;
        break;
      case 60:
        result = 3221225626LL;
        break;
      case 70:
        result = 2148098049LL;
        break;
      case 72:
        result = 2148081680LL;
        break;
      case 73:
        result = 2148081682LL;
        break;
      case 74:
        result = 2148081683LL;
        break;
      case 75:
      case 76:
        return 3221226233LL;
      case 77:
        result = 2148204816LL;
        break;
      default:
        return 3221225581LL;
    }
  }
  else if ( a1 == 5 )
  {
    return 3221226233LL;
  }
  else if ( a1 == -2147483644 )
  {
    return 3221225734LL;
  }
  else
  {
    return 3221225581LL;
  }
  return result;
}

```

## disassembly

```asm
0x180007ee0  test    ecx, ecx
0x180007ee2  jnz     short loc_180007EE7
0x180007ee4  xor     eax, eax
0x180007ee6  retn
0x180007ee7  cmp     ecx, 5
0x180007eea  jg      short loc_180007F04
0x180007eec  jz      loc_180007F9A; jumptable 0000000180007F2C cases 75,76
0x180007ef2  cmp     ecx, 80000004h
0x180007ef8  jnz     def_180007F2C; jumptable 0000000180007F2C default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180007efe  mov     eax, 0C0000106h
0x180007f03  retn
0x180007f04  add     ecx, 0FFFFFFFAh; switch 85 cases
0x180007f07  cmp     ecx, 54h
0x180007f0a  ja      def_180007F2C; jumptable 0000000180007F2C default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180007f10  movsxd  rax, ecx
0x180007f13  lea     rdx, __ImageBase
0x180007f1a  movzx   eax, ds:(byte_180008020 - 180000000h)[rdx+rax]
0x180007f22  mov     ecx, ds:(jpt_180007F2C - 180000000h)[rdx+rax*4]
0x180007f29  add     rcx, rdx
0x180007f2c  jmp     rcx; switch jump
0x180007f2e  mov     eax, 0C0000072h; jumptable 0000000180007F2C case 18
0x180007f33  retn
0x180007f34  mov     eax, 0C0000071h; jumptable 0000000180007F2C case 23
0x180007f39  retn
0x180007f3a  mov     eax, 0C000009Ah; jumptable 0000000180007F2C case 60
0x180007f3f  retn
0x180007f40  mov     eax, 0C0000133h; jumptable 0000000180007F2C cases 32,33,37,90
0x180007f45  retn
0x180007f46  mov     eax, 0C000006Eh; jumptable 0000000180007F2C case 12
0x180007f4b  retn
0x180007f4c  mov     eax, 0C0000064h; jumptable 0000000180007F2C case 6
0x180007f51  retn
0x180007f52  mov     eax, 0C000018Bh; jumptable 0000000180007F2C case 7
0x180007f57  retn
0x180007f58  mov     eax, 0C000006Ah; jumptable 0000000180007F2C cases 24,25,41
0x180007f5d  retn
0x180007f5e  mov     eax, 0C0000206h; jumptable 0000000180007F2C case 52
0x180007f63  retn
0x180007f64  mov     eax, 0C00000BBh; jumptable 0000000180007F2C case 16
0x180007f69  retn
0x180007f6a  mov     eax, 80090322h; jumptable 0000000180007F2C case 35
0x180007f6f  retn
0x180007f70  mov     eax, 0C000005Eh; jumptable 0000000180007F2C cases 29,68
0x180007f75  retn
0x180007f76  mov     eax, 80096001h; jumptable 0000000180007F2C case 70
0x180007f7b  retn
0x180007f7c  mov     eax, 0C000000Dh; jumptable 0000000180007F2C cases 39,40,71
0x180007f81  retn
0x180007f82  mov     eax, 80092010h; jumptable 0000000180007F2C case 72
0x180007f87  retn
0x180007f88  mov     eax, 80092012h; jumptable 0000000180007F2C case 73
0x180007f8d  retn
0x180007f8e  mov     eax, 800B0110h; jumptable 0000000180007F2C case 77
0x180007f93  retn
0x180007f94  mov     eax, 80092013h; jumptable 0000000180007F2C case 74
0x180007f99  retn
0x180007f9a  mov     eax, 0C00002F9h; jumptable 0000000180007F2C cases 75,76
0x180007f9f  retn
0x180007fa0  mov     eax, 0C0000190h; jumptable 0000000180007F2C case 28
0x180007fa5  retn
0x180007fa6  mov     eax, 0C00002FDh; jumptable 0000000180007F2C cases 14,80
0x180007fab  retn
0x180007fac  mov     eax, 0C0000408h; jumptable 0000000180007F2C cases 27,69
0x180007fb1  retn
0x180007fb2  mov     eax, 0C0000322h; jumptable 0000000180007F2C case 45
0x180007fb7  retn
0x180007fb8  mov     eax, 0C000006Dh; jumptable 0000000180007F2C default case, cases 8-11,13,15,17,19-22,26,30,31,34,36,38,42-44,46-51,53-59,61-67,78,79,81-89
0x180007fbd  retn
```
