# wil::details::HrToNtStatus(long)

- ea: `0x180005560`
- end: `0x18000571c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180002920`
- `0x1800029c8`
- `0x180002a1c`
- `0x180002adc`
- `0x180004b38`
- `0x180005724`

## callees

- `0x180005560`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  if ( (int)this > -2147024662 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          LODWORD(this) = -1073740757;
          return (unsigned int)this;
        case 0x8007054F:
          goto LABEL_53;
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
        case 0x80070216:
          LODWORD(this) = -1073741675;
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
  }
  else
  {
    if ( (_DWORD)this == -2147024662 )
    {
      LODWORD(this) = -2147483643;
      return (unsigned int)this;
    }
    if ( (int)this > -2147024809 )
    {
      switch ( (_DWORD)this )
      {
        case 0x80070070:
          LODWORD(this) = -1073741697;
          return (unsigned int)this;
        case 0x8007007A:
          LODWORD(this) = -1073741789;
          return (unsigned int)this;
        case 0x8007007B:
          LODWORD(this) = -1073741773;
          return (unsigned int)this;
        case 0x8007007E:
          LODWORD(this) = -1073741515;
          return (unsigned int)this;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x80070057:
          LODWORD(this) = -1073741811;
          return (unsigned int)this;
        case 0x80004005:
          LODWORD(this) = -1073741823;
          return (unsigned int)this;
        case 0x80070001:
          LODWORD(this) = -1073741822;
          return (unsigned int)this;
        case 0x80070002:
          LODWORD(this) = -1073741772;
          return (unsigned int)this;
        case 0x80070003:
          LODWORD(this) = -1073741766;
          return (unsigned int)this;
        case 0x8007000E:
          LODWORD(this) = -1073741801;
          return (unsigned int)this;
      }
    }
  }
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
  if ( ((unsigned int)this & 0x1FFF0000) != 0x90000 )
  {
LABEL_53:
    LODWORD(this) = -1073741595;
    return (unsigned int)this;
  }
  if ( (int)this > 0 )
    LODWORD(this) = (unsigned __int16)this | 0xC0090000;
  return (unsigned int)this;
}

```

## disassembly

```asm
0x180005560  mov     eax, 800700EAh
0x180005565  cmp     ecx, eax
0x180005567  jg      loc_18000563C
0x18000556d  jz      loc_180005632
0x180005573  mov     eax, 80070057h
0x180005578  cmp     ecx, eax
0x18000557a  jg      short loc_1800055E6
0x18000557c  jz      short loc_1800055DC
0x18000557e  cmp     ecx, 80004005h
0x180005584  jz      short loc_1800055D2
0x180005586  cmp     ecx, 80070001h
0x18000558c  jz      short loc_1800055C8
0x18000558e  cmp     ecx, 80070002h
0x180005594  jz      short loc_1800055BE
0x180005596  cmp     ecx, 80070003h
0x18000559c  jz      short loc_1800055B4
0x18000559e  cmp     ecx, 8007000Eh
0x1800055a4  jnz     loc_1800056C1
0x1800055aa  mov     ecx, 0C0000017h
0x1800055af  jmp     loc_180005719
0x1800055b4  mov     ecx, 0C000003Ah
0x1800055b9  jmp     loc_180005719
0x1800055be  mov     ecx, 0C0000034h
0x1800055c3  jmp     loc_180005719
0x1800055c8  mov     ecx, 0C0000002h
0x1800055cd  jmp     loc_180005719
0x1800055d2  mov     ecx, 0C0000001h
0x1800055d7  jmp     loc_180005719
0x1800055dc  mov     ecx, 0C000000Dh
0x1800055e1  jmp     loc_180005719
0x1800055e6  cmp     ecx, 80070070h
0x1800055ec  jz      short loc_180005628
0x1800055ee  cmp     ecx, 8007007Ah
0x1800055f4  jz      short loc_18000561E
0x1800055f6  cmp     ecx, 8007007Bh
0x1800055fc  jz      short loc_180005614
0x1800055fe  cmp     ecx, 8007007Eh
0x180005604  jnz     loc_1800056C1
0x18000560a  mov     ecx, 0C0000135h
0x18000560f  jmp     loc_180005719
0x180005614  mov     ecx, 0C0000033h
0x180005619  jmp     loc_180005719
0x18000561e  mov     ecx, 0C0000023h
0x180005623  jmp     loc_180005719
0x180005628  mov     ecx, 0C000007Fh
0x18000562d  jmp     loc_180005719
0x180005632  mov     ecx, 80000005h
0x180005637  jmp     loc_180005719
0x18000563c  mov     eax, 8007047Eh
0x180005641  cmp     ecx, eax
0x180005643  jg      short loc_1800056A5
0x180005645  jz      short loc_18000569E
0x180005647  cmp     ecx, 80070216h
0x18000564d  jz      short loc_180005697
0x18000564f  cmp     ecx, 8007023Eh
0x180005655  jz      short loc_18000568D
0x180005657  cmp     ecx, 80070246h
0x18000565d  jz      short loc_180005683
0x18000565f  cmp     ecx, 80070247h
0x180005665  jz      short loc_180005679
0x180005667  cmp     ecx, 80070272h
0x18000566d  jnz     short loc_1800056C1
0x18000566f  mov     ecx, 0C0000273h
0x180005674  jmp     loc_180005719
0x180005679  mov     ecx, 0C0000163h
0x18000567e  jmp     loc_180005719
0x180005683  mov     ecx, 0C0000161h
0x180005688  jmp     loc_180005719
0x18000568d  mov     ecx, 0C0000025h
0x180005692  jmp     loc_180005719
0x180005697  mov     ecx, 0C0000095h
0x18000569c  jmp     short loc_180005719
0x18000569e  mov     ecx, 0C0000059h
0x1800056a3  jmp     short loc_180005719
0x1800056a5  cmp     ecx, 8007050Ch
0x1800056ab  jz      short loc_180005714
0x1800056ad  cmp     ecx, 8007054Fh
0x1800056b3  jz      short loc_18000570D
0x1800056b5  cmp     ecx, 800705B9h
0x1800056bb  jz      short loc_180005706
0x1800056bd  test    ecx, ecx
0x1800056bf  jz      short loc_180005702
0x1800056c1  bt      ecx, 1Ch
0x1800056c5  jnb     short loc_1800056CD
0x1800056c7  btr     ecx, 1Ch
0x1800056cb  jmp     short loc_180005719
0x1800056cd  mov     eax, ecx
0x1800056cf  and     eax, 1FFF0000h
0x1800056d4  cmp     eax, 70000h
0x1800056d9  jnz     short loc_1800056EC
0x1800056db  movzx   ecx, cx
0x1800056de  mov     eax, ecx
0x1800056e0  or      eax, 0C0070000h
0x1800056e5  test    ecx, ecx
0x1800056e7  cmovnz  ecx, eax
0x1800056ea  jmp     short loc_180005719
0x1800056ec  cmp     eax, 90000h
0x1800056f1  jnz     short loc_18000570D
0x1800056f3  test    ecx, ecx
0x1800056f5  jle     short loc_180005719
0x1800056f7  movzx   ecx, cx
0x1800056fa  or      ecx, 0C0090000h
0x180005700  jmp     short loc_180005719
0x180005702  xor     ecx, ecx
0x180005704  jmp     short loc_180005719
0x180005706  mov     ecx, 0C000A083h
0x18000570b  jmp     short loc_180005719
0x18000570d  mov     ecx, 0C00000E5h
0x180005712  jmp     short loc_180005719
0x180005714  mov     ecx, 0C000042Bh
0x180005719  mov     eax, ecx
0x18000571b  retn
```
