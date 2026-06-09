# ComputeNtMediaType(_FMIFS_MEDIA_TYPE)

- ea: `0x180003d40`
- end: `0x180003df5`
- name: `?ComputeNtMediaType@@YA?AW4_MEDIA_TYPE@@W4_FMIFS_MEDIA_TYPE@@@Z`
- size: `181`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180004ca0`
- `0x180005240`
- `0x1800058a0`

## callees

- `0x180003d40`

## pseudocode

```c
__int64 __fastcall ComputeNtMediaType(int a1)
{
  __int64 result; // rax

  if ( a1 == 12 )
    return 12;
  switch ( a1 )
  {
    case 1:
      result = 10;
      break;
    case 2:
      result = 9;
      break;
    case 3:
      result = 7;
      break;
    case 4:
      result = 8;
      break;
    case 5:
      result = 6;
      break;
    case 6:
      result = 5;
      break;
    case 7:
      result = 1;
      break;
    case 8:
      result = 2;
      break;
    case 9:
      result = 3;
      break;
    case 10:
      result = 4;
      break;
    case 11:
      result = 11;
      break;
    case 13:
      result = 13;
      break;
    case 14:
      result = 14;
      break;
    case 15:
      result = 15;
      break;
    case 16:
      result = 16;
      break;
    case 17:
      result = 17;
      break;
    case 18:
      result = 18;
      break;
    case 19:
      result = 19;
      break;
    case 20:
      result = 20;
      break;
    case 21:
      result = 21;
      break;
    case 22:
      result = 23;
      break;
    case 23:
      result = 24;
      break;
    default:
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x180003d40  cmp     ecx, 0Ch
0x180003d43  jz      loc_180003DEF
0x180003d49  cmp     ecx, 17h; switch 24 cases
0x180003d4c  ja      def_180003D66; jumptable 0000000180003D66 default case, cases 0,12
0x180003d52  movsxd  rax, ecx
0x180003d55  lea     rdx, cs:180000000h
0x180003d5c  mov     ecx, ds:(jpt_180003D66 - 180000000h)[rdx+rax*4]
0x180003d63  add     rcx, rdx
0x180003d66  jmp     rcx; switch jump
0x180003d68  mov     eax, 0Bh; jumptable 0000000180003D66 case 11
0x180003d6d  retn
0x180003d6e  mov     eax, 1; jumptable 0000000180003D66 case 7
0x180003d73  retn
0x180003d74  mov     eax, 6; jumptable 0000000180003D66 case 5
0x180003d79  retn
0x180003d7a  mov     eax, 7; jumptable 0000000180003D66 case 3
0x180003d7f  retn
0x180003d80  mov     eax, 8; jumptable 0000000180003D66 case 4
0x180003d85  retn
0x180003d86  mov     eax, 9; jumptable 0000000180003D66 case 2
0x180003d8b  retn
0x180003d8c  mov     eax, 0Ah; jumptable 0000000180003D66 case 1
0x180003d91  retn
0x180003d92  mov     eax, 3; jumptable 0000000180003D66 case 9
0x180003d97  retn
0x180003d98  mov     eax, 2; jumptable 0000000180003D66 case 8
0x180003d9d  retn
0x180003d9e  mov     eax, 5; jumptable 0000000180003D66 case 6
0x180003da3  retn
0x180003da4  mov     eax, 4; jumptable 0000000180003D66 case 10
0x180003da9  retn
0x180003daa  mov     eax, 0Dh; jumptable 0000000180003D66 case 13
0x180003daf  retn
0x180003db0  mov     eax, 17h; jumptable 0000000180003D66 case 22
0x180003db5  retn
0x180003db6  mov     eax, 18h; jumptable 0000000180003D66 case 23
0x180003dbb  retn
0x180003dbc  mov     eax, 13h; jumptable 0000000180003D66 case 19
0x180003dc1  retn
0x180003dc2  mov     eax, 12h; jumptable 0000000180003D66 case 18
0x180003dc7  retn
0x180003dc8  mov     eax, 11h; jumptable 0000000180003D66 case 17
0x180003dcd  retn
0x180003dce  mov     eax, 10h; jumptable 0000000180003D66 case 16
0x180003dd3  retn
0x180003dd4  mov     eax, 0Fh; jumptable 0000000180003D66 case 15
0x180003dd9  retn
0x180003dda  mov     eax, 0Eh; jumptable 0000000180003D66 case 14
0x180003ddf  retn
0x180003de0  mov     eax, 14h; jumptable 0000000180003D66 case 20
0x180003de5  retn
0x180003de6  mov     eax, 15h; jumptable 0000000180003D66 case 21
0x180003deb  retn
0x180003dec  xor     eax, eax; jumptable 0000000180003D66 default case, cases 0,12
0x180003dee  retn
0x180003def  mov     eax, 0Ch
0x180003df4  retn
```
