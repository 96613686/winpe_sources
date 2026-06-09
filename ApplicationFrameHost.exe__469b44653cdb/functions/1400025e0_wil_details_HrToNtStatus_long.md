# wil::details::HrToNtStatus(long)

- ea: `0x1400025e0`
- end: `0x14000277e`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `414`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140002a40`
- `0x140002cb0`
- `0x140002d04`
- `0x1400043ec`
- `0x140004464`
- `0x1400069e0`

## callees

- `0x1400025e0`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (_DWORD)this == -2147023537 )
    goto LABEL_46;
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
LABEL_34:
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
LABEL_46:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > -2147024362 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x800705B9:
          LODWORD(this) = -1073700733;
          return (unsigned int)this;
        case 0:
          LODWORD(this) = 0;
          return (unsigned int)this;
      }
    }
    else
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
    goto LABEL_34;
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
        goto LABEL_34;
    }
  }
  return (unsigned int)this;
}

```

## disassembly

```asm
0x1400025e0  cmp     ecx, 8007054Fh
0x1400025e6  jz      loc_140002776
0x1400025ec  cmp     ecx, 80070001h
0x1400025f2  jg      short loc_140002616
0x1400025f4  jz      short loc_14000260C
0x1400025f6  cmp     ecx, 80004005h
0x1400025fc  jnz     def_140002656; jumptable 0000000140002656 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140002602  mov     ecx, 0C0000001h
0x140002607  jmp     loc_14000277B
0x14000260c  mov     ecx, 0C0000002h
0x140002611  jmp     loc_14000277B
0x140002616  cmp     ecx, 80070216h
0x14000261c  jg      loc_1400026BC
0x140002622  jz      loc_1400026B2
0x140002628  lea     eax, [rcx+7FF8FFFEh]; switch 233 cases
0x14000262e  cmp     eax, 0E8h
0x140002633  ja      def_140002656; jumptable 0000000140002656 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140002639  lea     r8, __ImageBase
0x140002640  cdqe
0x140002642  movzx   eax, ds:(byte_1400027A8 - 140000000h)[r8+rax]
0x14000264b  mov     edx, ds:(jpt_140002656 - 140000000h)[r8+rax*4]
0x140002653  add     rdx, r8
0x140002656  jmp     rdx; switch jump
0x140002658  mov     ecx, 0C000000Dh; jumptable 0000000140002656 case -2147024809
0x14000265d  jmp     loc_14000277B
0x140002662  mov     ecx, 0C0000017h; jumptable 0000000140002656 case -2147024882
0x140002667  jmp     loc_14000277B
0x14000266c  mov     ecx, 0C000003Ah; jumptable 0000000140002656 case -2147024893
0x140002671  jmp     loc_14000277B
0x140002676  mov     ecx, 0C0000034h; jumptable 0000000140002656 case -2147024894
0x14000267b  jmp     loc_14000277B
0x140002680  mov     ecx, 80000005h; jumptable 0000000140002656 case -2147024662
0x140002685  jmp     loc_14000277B
0x14000268a  mov     ecx, 0C0000023h; jumptable 0000000140002656 case -2147024774
0x14000268f  jmp     loc_14000277B
0x140002694  mov     ecx, 0C000007Fh; jumptable 0000000140002656 case -2147024784
0x140002699  jmp     loc_14000277B
0x14000269e  mov     ecx, 0C0000033h; jumptable 0000000140002656 case -2147024773
0x1400026a3  jmp     loc_14000277B
0x1400026a8  mov     ecx, 0C0000135h; jumptable 0000000140002656 case -2147024770
0x1400026ad  jmp     loc_14000277B
0x1400026b2  mov     ecx, 0C0000095h
0x1400026b7  jmp     loc_14000277B
0x1400026bc  cmp     ecx, 8007047Eh
0x1400026c2  jg      short loc_14000270F
0x1400026c4  jz      short loc_140002708
0x1400026c6  cmp     ecx, 8007023Eh
0x1400026cc  jz      short loc_140002701
0x1400026ce  cmp     ecx, 80070246h
0x1400026d4  jz      short loc_1400026FA
0x1400026d6  cmp     ecx, 80070247h
0x1400026dc  jz      short loc_1400026F0
0x1400026de  cmp     ecx, 80070272h
0x1400026e4  jnz     short def_140002656; jumptable 0000000140002656 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x1400026e6  mov     ecx, 0C0000273h
0x1400026eb  jmp     loc_14000277B
0x1400026f0  mov     ecx, 0C0000163h
0x1400026f5  jmp     loc_14000277B
0x1400026fa  mov     ecx, 0C0000161h
0x1400026ff  jmp     short loc_14000277B
0x140002701  mov     ecx, 0C0000025h
0x140002706  jmp     short loc_14000277B
0x140002708  mov     ecx, 0C0000059h
0x14000270d  jmp     short loc_14000277B
0x14000270f  cmp     ecx, 8007050Ch
0x140002715  jz      short loc_14000276F
0x140002717  cmp     ecx, 800705B9h
0x14000271d  jz      short loc_140002768
0x14000271f  test    ecx, ecx
0x140002721  jz      short loc_140002764
0x140002723  bt      ecx, 1Ch; jumptable 0000000140002656 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x140002727  jnb     short loc_14000272F
0x140002729  btr     ecx, 1Ch
0x14000272d  jmp     short loc_14000277B
0x14000272f  mov     eax, ecx
0x140002731  and     eax, 1FFF0000h
0x140002736  cmp     eax, 70000h
0x14000273b  jnz     short loc_14000274E
0x14000273d  movzx   ecx, cx
0x140002740  mov     eax, ecx
0x140002742  or      eax, 0C0070000h
0x140002747  test    ecx, ecx
0x140002749  cmovnz  ecx, eax
0x14000274c  jmp     short loc_14000277B
0x14000274e  cmp     eax, 90000h
0x140002753  jnz     short loc_140002776
0x140002755  test    ecx, ecx
0x140002757  jle     short loc_14000277B
0x140002759  movzx   ecx, cx
0x14000275c  or      ecx, 0C0090000h
0x140002762  jmp     short loc_14000277B
0x140002764  xor     ecx, ecx
0x140002766  jmp     short loc_14000277B
0x140002768  mov     ecx, 0C000A083h
0x14000276d  jmp     short loc_14000277B
0x14000276f  mov     ecx, 0C000042Bh
0x140002774  jmp     short loc_14000277B
0x140002776  mov     ecx, 0C00000E5h
0x14000277b  mov     eax, ecx
0x14000277d  retn
```
