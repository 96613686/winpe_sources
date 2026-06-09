# wil::details::HrToNtStatus(long)

- ea: `0x180005590`
- end: `0x18000574c`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800035b0`
- `0x180003660`
- `0x1800036c0`
- `0x180003788`
- `0x180004968`
- `0x180005778`
- `0x180005f50`
- `0x180007adc`
- `0x180007c2c`
- `0x18000c204`
- `0x18000c26f`
- `0x18000c338`
- `0x18000c3a3`

## callees

- `0x180005590`

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
0x180005590  mov     eax, 800700EAh
0x180005595  cmp     ecx, eax
0x180005597  jg      loc_18000566C
0x18000559d  jz      loc_180005662
0x1800055a3  mov     eax, 80070057h
0x1800055a8  cmp     ecx, eax
0x1800055aa  jg      short loc_180005616
0x1800055ac  jz      short loc_18000560C
0x1800055ae  cmp     ecx, 80004005h
0x1800055b4  jz      short loc_180005602
0x1800055b6  cmp     ecx, 80070001h
0x1800055bc  jz      short loc_1800055F8
0x1800055be  cmp     ecx, 80070002h
0x1800055c4  jz      short loc_1800055EE
0x1800055c6  cmp     ecx, 80070003h
0x1800055cc  jz      short loc_1800055E4
0x1800055ce  cmp     ecx, 8007000Eh
0x1800055d4  jnz     loc_1800056F1
0x1800055da  mov     ecx, 0C0000017h
0x1800055df  jmp     loc_180005749
0x1800055e4  mov     ecx, 0C000003Ah
0x1800055e9  jmp     loc_180005749
0x1800055ee  mov     ecx, 0C0000034h
0x1800055f3  jmp     loc_180005749
0x1800055f8  mov     ecx, 0C0000002h
0x1800055fd  jmp     loc_180005749
0x180005602  mov     ecx, 0C0000001h
0x180005607  jmp     loc_180005749
0x18000560c  mov     ecx, 0C000000Dh
0x180005611  jmp     loc_180005749
0x180005616  cmp     ecx, 80070070h
0x18000561c  jz      short loc_180005658
0x18000561e  cmp     ecx, 8007007Ah
0x180005624  jz      short loc_18000564E
0x180005626  cmp     ecx, 8007007Bh
0x18000562c  jz      short loc_180005644
0x18000562e  cmp     ecx, 8007007Eh
0x180005634  jnz     loc_1800056F1
0x18000563a  mov     ecx, 0C0000135h
0x18000563f  jmp     loc_180005749
0x180005644  mov     ecx, 0C0000033h
0x180005649  jmp     loc_180005749
0x18000564e  mov     ecx, 0C0000023h
0x180005653  jmp     loc_180005749
0x180005658  mov     ecx, 0C000007Fh
0x18000565d  jmp     loc_180005749
0x180005662  mov     ecx, 80000005h
0x180005667  jmp     loc_180005749
0x18000566c  mov     eax, 8007047Eh
0x180005671  cmp     ecx, eax
0x180005673  jg      short loc_1800056D5
0x180005675  jz      short loc_1800056CE
0x180005677  cmp     ecx, 80070216h
0x18000567d  jz      short loc_1800056C7
0x18000567f  cmp     ecx, 8007023Eh
0x180005685  jz      short loc_1800056BD
0x180005687  cmp     ecx, 80070246h
0x18000568d  jz      short loc_1800056B3
0x18000568f  cmp     ecx, 80070247h
0x180005695  jz      short loc_1800056A9
0x180005697  cmp     ecx, 80070272h
0x18000569d  jnz     short loc_1800056F1
0x18000569f  mov     ecx, 0C0000273h
0x1800056a4  jmp     loc_180005749
0x1800056a9  mov     ecx, 0C0000163h
0x1800056ae  jmp     loc_180005749
0x1800056b3  mov     ecx, 0C0000161h
0x1800056b8  jmp     loc_180005749
0x1800056bd  mov     ecx, 0C0000025h
0x1800056c2  jmp     loc_180005749
0x1800056c7  mov     ecx, 0C0000095h
0x1800056cc  jmp     short loc_180005749
0x1800056ce  mov     ecx, 0C0000059h
0x1800056d3  jmp     short loc_180005749
0x1800056d5  cmp     ecx, 8007050Ch
0x1800056db  jz      short loc_180005744
0x1800056dd  cmp     ecx, 8007054Fh
0x1800056e3  jz      short loc_18000573D
0x1800056e5  cmp     ecx, 800705B9h
0x1800056eb  jz      short loc_180005736
0x1800056ed  test    ecx, ecx
0x1800056ef  jz      short loc_180005732
0x1800056f1  bt      ecx, 1Ch
0x1800056f5  jnb     short loc_1800056FD
0x1800056f7  btr     ecx, 1Ch
0x1800056fb  jmp     short loc_180005749
0x1800056fd  mov     eax, ecx
0x1800056ff  and     eax, 1FFF0000h
0x180005704  cmp     eax, 70000h
0x180005709  jnz     short loc_18000571C
0x18000570b  movzx   ecx, cx
0x18000570e  mov     eax, ecx
0x180005710  or      eax, 0C0070000h
0x180005715  test    ecx, ecx
0x180005717  cmovnz  ecx, eax
0x18000571a  jmp     short loc_180005749
0x18000571c  cmp     eax, 90000h
0x180005721  jnz     short loc_18000573D
0x180005723  test    ecx, ecx
0x180005725  jle     short loc_180005749
0x180005727  movzx   ecx, cx
0x18000572a  or      ecx, 0C0090000h
0x180005730  jmp     short loc_180005749
0x180005732  xor     ecx, ecx
0x180005734  jmp     short loc_180005749
0x180005736  mov     ecx, 0C000A083h
0x18000573b  jmp     short loc_180005749
0x18000573d  mov     ecx, 0C00000E5h
0x180005742  jmp     short loc_180005749
0x180005744  mov     ecx, 0C000042Bh
0x180005749  mov     eax, ecx
0x18000574b  retn
```
