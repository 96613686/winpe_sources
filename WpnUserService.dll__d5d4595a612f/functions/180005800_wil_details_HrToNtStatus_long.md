# wil::details::HrToNtStatus(long)

- ea: `0x180005800`
- end: `0x1800059bc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x180003918`
- `0x1800039c8`
- `0x180003a20`
- `0x180003ae8`
- `0x180004d28`
- `0x1800059c4`
- `0x1800060c0`
- `0x1800077ec`
- `0x180007a10`
- `0x180007acc`
- `0x18000d4ec`
- `0x180010e2e`
- `0x180010e99`
- `0x180010f62`
- `0x180010fcd`

## callees

- `0x180005800`

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
0x180005800  mov     eax, 800700EAh
0x180005805  cmp     ecx, eax
0x180005807  jg      loc_1800058DC
0x18000580d  jz      loc_1800058D2
0x180005813  mov     eax, 80070057h
0x180005818  cmp     ecx, eax
0x18000581a  jg      short loc_180005886
0x18000581c  jz      short loc_18000587C
0x18000581e  cmp     ecx, 80004005h
0x180005824  jz      short loc_180005872
0x180005826  cmp     ecx, 80070001h
0x18000582c  jz      short loc_180005868
0x18000582e  cmp     ecx, 80070002h
0x180005834  jz      short loc_18000585E
0x180005836  cmp     ecx, 80070003h
0x18000583c  jz      short loc_180005854
0x18000583e  cmp     ecx, 8007000Eh
0x180005844  jnz     loc_180005961
0x18000584a  mov     ecx, 0C0000017h
0x18000584f  jmp     loc_1800059B9
0x180005854  mov     ecx, 0C000003Ah
0x180005859  jmp     loc_1800059B9
0x18000585e  mov     ecx, 0C0000034h
0x180005863  jmp     loc_1800059B9
0x180005868  mov     ecx, 0C0000002h
0x18000586d  jmp     loc_1800059B9
0x180005872  mov     ecx, 0C0000001h
0x180005877  jmp     loc_1800059B9
0x18000587c  mov     ecx, 0C000000Dh
0x180005881  jmp     loc_1800059B9
0x180005886  cmp     ecx, 80070070h
0x18000588c  jz      short loc_1800058C8
0x18000588e  cmp     ecx, 8007007Ah
0x180005894  jz      short loc_1800058BE
0x180005896  cmp     ecx, 8007007Bh
0x18000589c  jz      short loc_1800058B4
0x18000589e  cmp     ecx, 8007007Eh
0x1800058a4  jnz     loc_180005961
0x1800058aa  mov     ecx, 0C0000135h
0x1800058af  jmp     loc_1800059B9
0x1800058b4  mov     ecx, 0C0000033h
0x1800058b9  jmp     loc_1800059B9
0x1800058be  mov     ecx, 0C0000023h
0x1800058c3  jmp     loc_1800059B9
0x1800058c8  mov     ecx, 0C000007Fh
0x1800058cd  jmp     loc_1800059B9
0x1800058d2  mov     ecx, 80000005h
0x1800058d7  jmp     loc_1800059B9
0x1800058dc  mov     eax, 8007047Eh
0x1800058e1  cmp     ecx, eax
0x1800058e3  jg      short loc_180005945
0x1800058e5  jz      short loc_18000593E
0x1800058e7  cmp     ecx, 80070216h
0x1800058ed  jz      short loc_180005937
0x1800058ef  cmp     ecx, 8007023Eh
0x1800058f5  jz      short loc_18000592D
0x1800058f7  cmp     ecx, 80070246h
0x1800058fd  jz      short loc_180005923
0x1800058ff  cmp     ecx, 80070247h
0x180005905  jz      short loc_180005919
0x180005907  cmp     ecx, 80070272h
0x18000590d  jnz     short loc_180005961
0x18000590f  mov     ecx, 0C0000273h
0x180005914  jmp     loc_1800059B9
0x180005919  mov     ecx, 0C0000163h
0x18000591e  jmp     loc_1800059B9
0x180005923  mov     ecx, 0C0000161h
0x180005928  jmp     loc_1800059B9
0x18000592d  mov     ecx, 0C0000025h
0x180005932  jmp     loc_1800059B9
0x180005937  mov     ecx, 0C0000095h
0x18000593c  jmp     short loc_1800059B9
0x18000593e  mov     ecx, 0C0000059h
0x180005943  jmp     short loc_1800059B9
0x180005945  cmp     ecx, 8007050Ch
0x18000594b  jz      short loc_1800059B4
0x18000594d  cmp     ecx, 8007054Fh
0x180005953  jz      short loc_1800059AD
0x180005955  cmp     ecx, 800705B9h
0x18000595b  jz      short loc_1800059A6
0x18000595d  test    ecx, ecx
0x18000595f  jz      short loc_1800059A2
0x180005961  bt      ecx, 1Ch
0x180005965  jnb     short loc_18000596D
0x180005967  btr     ecx, 1Ch
0x18000596b  jmp     short loc_1800059B9
0x18000596d  mov     eax, ecx
0x18000596f  and     eax, 1FFF0000h
0x180005974  cmp     eax, 70000h
0x180005979  jnz     short loc_18000598C
0x18000597b  movzx   ecx, cx
0x18000597e  mov     eax, ecx
0x180005980  or      eax, 0C0070000h
0x180005985  test    ecx, ecx
0x180005987  cmovnz  ecx, eax
0x18000598a  jmp     short loc_1800059B9
0x18000598c  cmp     eax, 90000h
0x180005991  jnz     short loc_1800059AD
0x180005993  test    ecx, ecx
0x180005995  jle     short loc_1800059B9
0x180005997  movzx   ecx, cx
0x18000599a  or      ecx, 0C0090000h
0x1800059a0  jmp     short loc_1800059B9
0x1800059a2  xor     ecx, ecx
0x1800059a4  jmp     short loc_1800059B9
0x1800059a6  mov     ecx, 0C000A083h
0x1800059ab  jmp     short loc_1800059B9
0x1800059ad  mov     ecx, 0C00000E5h
0x1800059b2  jmp     short loc_1800059B9
0x1800059b4  mov     ecx, 0C000042Bh
0x1800059b9  mov     eax, ecx
0x1800059bb  retn
```
