# wil::details::HrToNtStatus(long)

- ea: `0x140005d50`
- end: `0x140005f12`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `450`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140005d20`
- `0x140007f8c`
- `0x14000a38c`
- `0x14000a404`
- `0x14000a460`
- `0x14000bcfc`

## callees

- `0x140005d50`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this <= -2147024895 )
  {
    if ( (_DWORD)this == -2147024895 )
    {
      LODWORD(this) = -1073741822;
      return (unsigned int)this;
    }
    if ( (_DWORD)this == -2147467259 )
    {
      LODWORD(this) = -1073741823;
      return (unsigned int)this;
    }
    goto LABEL_4;
  }
  if ( (int)this > -2147024362 )
  {
    if ( (int)this <= -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          LODWORD(this) = -1073741735;
          return (unsigned int)this;
        case 0x8007023E:
          LODWORD(this) = -1073741787;
          return (unsigned int)this;
        case 0x80070246:
          LODWORD(this) = -1073741471;
          return (unsigned int)this;
        case 0x80070247:
          LODWORD(this) = -1073741469;
          return (unsigned int)this;
        case 0x80070272:
          LODWORD(this) = -1073741197;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_45;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          return (unsigned int)this;
      }
    }
LABEL_4:
    if ( ((unsigned int)this & 0x10000000) != 0 )
    {
      LODWORD(this) = (unsigned int)this & 0xEFFFFFFF;
      return (unsigned int)this;
    }
    if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
    {
      LODWORD(this) = (unsigned __int16)this;
      if ( (_WORD)this )
        LODWORD(this) = (unsigned __int16)this | 0xC0070000;
      return (unsigned int)this;
    }
    if ( ((unsigned int)this & 0x1FFF0000) == 0x90000 )
    {
      if ( (int)this > 0 )
        LODWORD(this) = (unsigned __int16)this | 0xC0090000;
      return (unsigned int)this;
    }
LABEL_45:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (_DWORD)this == -2147024362 )
  {
    LODWORD(this) = -1073741675;
  }
  else
  {
    switch ( (unsigned int)this )
    {
      case 0x80070002:
        LODWORD(this) = -1073741772;
        break;
      case 0x80070003:
        LODWORD(this) = -1073741766;
        break;
      case 0x8007000E:
        LODWORD(this) = -1073741801;
        break;
      case 0x80070057:
        LODWORD(this) = -1073741811;
        break;
      case 0x80070070:
        LODWORD(this) = -1073741697;
        break;
      case 0x8007007A:
        LODWORD(this) = -1073741789;
        break;
      case 0x8007007B:
        LODWORD(this) = -1073741773;
        break;
      case 0x8007007E:
        LODWORD(this) = -1073741515;
        break;
      case 0x800700EA:
        LODWORD(this) = -2147483643;
        break;
      default:
        goto LABEL_4;
    }
  }
  return (unsigned int)this;
}

```

## disassembly

```asm
0x140005d50  cmp     ecx, 80070001h
0x140005d56  jg      short loc_140005D90
0x140005d58  jz      short loc_140005DD5
0x140005d5a  cmp     ecx, 80004005h
0x140005d60  jz      short loc_140005DCE
0x140005d62  bt      ecx, 1Ch; jumptable 0000000140005E10 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140005d66  jb      loc_140005ECE
0x140005d6c  mov     eax, ecx
0x140005d6e  and     eax, 1FFF0000h
0x140005d73  cmp     eax, 70000h
0x140005d78  jnz     loc_140005ED7
0x140005d7e  movzx   ecx, cx
0x140005d81  mov     eax, ecx
0x140005d83  or      eax, 0C0070000h
0x140005d88  test    ecx, ecx
0x140005d8a  cmovnz  ecx, eax
0x140005d8d  mov     eax, ecx
0x140005d8f  retn
0x140005d90  cmp     ecx, 80070216h
0x140005d96  jle     short loc_140005DDC
0x140005d98  cmp     ecx, 8007047Eh
0x140005d9e  jle     loc_140005E76
0x140005da4  cmp     ecx, 8007050Ch
0x140005daa  jz      loc_140005F08
0x140005db0  cmp     ecx, 8007054Fh
0x140005db6  jz      loc_140005EFE
0x140005dbc  cmp     ecx, 800705B9h
0x140005dc2  jz      loc_140005EF4
0x140005dc8  test    ecx, ecx
0x140005dca  jnz     short def_140005E10; jumptable 0000000140005E10 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140005dcc  jmp     short loc_140005D8D
0x140005dce  mov     ecx, 0C0000001h
0x140005dd3  jmp     short loc_140005D8D
0x140005dd5  mov     ecx, 0C0000002h
0x140005dda  jmp     short loc_140005D8D
0x140005ddc  jz      loc_140005E6C
0x140005de2  lea     eax, [rcx+7FF8FFFEh]; switch 233 cases
0x140005de8  cmp     eax, 0E8h
0x140005ded  ja      def_140005E10; jumptable 0000000140005E10 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140005df3  lea     r8, __ImageBase
0x140005dfa  cdqe
0x140005dfc  movzx   eax, ds:(byte_140005F3C - 140000000h)[r8+rax]
0x140005e05  mov     edx, ds:(jpt_140005E10 - 140000000h)[r8+rax*4]
0x140005e0d  add     rdx, r8
0x140005e10  jmp     rdx; switch jump
0x140005e12  mov     ecx, 0C000000Dh; jumptable 0000000140005E10 case -2147024809
0x140005e17  jmp     loc_140005D8D
0x140005e1c  mov     ecx, 0C0000017h; jumptable 0000000140005E10 case -2147024882
0x140005e21  jmp     loc_140005D8D
0x140005e26  mov     ecx, 0C000003Ah; jumptable 0000000140005E10 case -2147024893
0x140005e2b  jmp     loc_140005D8D
0x140005e30  mov     ecx, 0C0000034h; jumptable 0000000140005E10 case -2147024894
0x140005e35  jmp     loc_140005D8D
0x140005e3a  mov     ecx, 80000005h; jumptable 0000000140005E10 case -2147024662
0x140005e3f  jmp     loc_140005D8D
0x140005e44  mov     ecx, 0C0000023h; jumptable 0000000140005E10 case -2147024774
0x140005e49  jmp     loc_140005D8D
0x140005e4e  mov     ecx, 0C000007Fh; jumptable 0000000140005E10 case -2147024784
0x140005e53  jmp     loc_140005D8D
0x140005e58  mov     ecx, 0C0000033h; jumptable 0000000140005E10 case -2147024773
0x140005e5d  jmp     loc_140005D8D
0x140005e62  mov     ecx, 0C0000135h; jumptable 0000000140005E10 case -2147024770
0x140005e67  jmp     loc_140005D8D
0x140005e6c  mov     ecx, 0C0000095h
0x140005e71  jmp     loc_140005D8D
0x140005e76  jz      short loc_140005EC4
0x140005e78  cmp     ecx, 8007023Eh
0x140005e7e  jz      short loc_140005EBA
0x140005e80  cmp     ecx, 80070246h
0x140005e86  jz      short loc_140005EB0
0x140005e88  cmp     ecx, 80070247h
0x140005e8e  jz      short loc_140005EA6
0x140005e90  cmp     ecx, 80070272h
0x140005e96  jnz     def_140005E10; jumptable 0000000140005E10 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140005e9c  mov     ecx, 0C0000273h
0x140005ea1  jmp     loc_140005D8D
0x140005ea6  mov     ecx, 0C0000163h
0x140005eab  jmp     loc_140005D8D
0x140005eb0  mov     ecx, 0C0000161h
0x140005eb5  jmp     loc_140005D8D
0x140005eba  mov     ecx, 0C0000025h
0x140005ebf  jmp     loc_140005D8D
0x140005ec4  mov     ecx, 0C0000059h
0x140005ec9  jmp     loc_140005D8D
0x140005ece  btr     ecx, 1Ch
0x140005ed2  jmp     loc_140005D8D
0x140005ed7  cmp     eax, 90000h
0x140005edc  jnz     short loc_140005EFE
0x140005ede  test    ecx, ecx
0x140005ee0  jle     loc_140005D8D
0x140005ee6  movzx   ecx, cx
0x140005ee9  or      ecx, 0C0090000h
0x140005eef  jmp     loc_140005D8D
0x140005ef4  mov     ecx, 0C000A083h
0x140005ef9  jmp     loc_140005D8D
0x140005efe  mov     ecx, 0C00000E5h
0x140005f03  jmp     loc_140005D8D
0x140005f08  mov     ecx, 0C000042Bh
0x140005f0d  jmp     loc_140005D8D
```
