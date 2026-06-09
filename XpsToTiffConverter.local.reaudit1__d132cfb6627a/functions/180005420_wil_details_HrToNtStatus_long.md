# wil::details::HrToNtStatus(long)

- ea: `0x180005420`
- end: `0x1800055dc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800023dc`
- `0x1800025a8`
- `0x180002658`
- `0x1800026b8`
- `0x180002780`
- `0x1800049f8`
- `0x1800055e4`
- `0x180006ed0`
- `0x18000cdd5`
- `0x18000ce40`
- `0x18000cf09`
- `0x18000cf74`

## callees

- `0x180005420`

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
0x180005420  mov     eax, 800700EAh
0x180005425  cmp     ecx, eax
0x180005427  jg      loc_1800054FC
0x18000542d  jz      loc_1800054F2
0x180005433  mov     eax, 80070057h
0x180005438  cmp     ecx, eax
0x18000543a  jg      short loc_1800054A6
0x18000543c  jz      short loc_18000549C
0x18000543e  cmp     ecx, 80004005h
0x180005444  jz      short loc_180005492
0x180005446  cmp     ecx, 80070001h
0x18000544c  jz      short loc_180005488
0x18000544e  cmp     ecx, 80070002h
0x180005454  jz      short loc_18000547E
0x180005456  cmp     ecx, 80070003h
0x18000545c  jz      short loc_180005474
0x18000545e  cmp     ecx, 8007000Eh
0x180005464  jnz     loc_180005581
0x18000546a  mov     ecx, 0C0000017h
0x18000546f  jmp     loc_1800055D9
0x180005474  mov     ecx, 0C000003Ah
0x180005479  jmp     loc_1800055D9
0x18000547e  mov     ecx, 0C0000034h
0x180005483  jmp     loc_1800055D9
0x180005488  mov     ecx, 0C0000002h
0x18000548d  jmp     loc_1800055D9
0x180005492  mov     ecx, 0C0000001h
0x180005497  jmp     loc_1800055D9
0x18000549c  mov     ecx, 0C000000Dh
0x1800054a1  jmp     loc_1800055D9
0x1800054a6  cmp     ecx, 80070070h
0x1800054ac  jz      short loc_1800054E8
0x1800054ae  cmp     ecx, 8007007Ah
0x1800054b4  jz      short loc_1800054DE
0x1800054b6  cmp     ecx, 8007007Bh
0x1800054bc  jz      short loc_1800054D4
0x1800054be  cmp     ecx, 8007007Eh
0x1800054c4  jnz     loc_180005581
0x1800054ca  mov     ecx, 0C0000135h
0x1800054cf  jmp     loc_1800055D9
0x1800054d4  mov     ecx, 0C0000033h
0x1800054d9  jmp     loc_1800055D9
0x1800054de  mov     ecx, 0C0000023h
0x1800054e3  jmp     loc_1800055D9
0x1800054e8  mov     ecx, 0C000007Fh
0x1800054ed  jmp     loc_1800055D9
0x1800054f2  mov     ecx, 80000005h
0x1800054f7  jmp     loc_1800055D9
0x1800054fc  mov     eax, 8007047Eh
0x180005501  cmp     ecx, eax
0x180005503  jg      short loc_180005565
0x180005505  jz      short loc_18000555E
0x180005507  cmp     ecx, 80070216h
0x18000550d  jz      short loc_180005557
0x18000550f  cmp     ecx, 8007023Eh
0x180005515  jz      short loc_18000554D
0x180005517  cmp     ecx, 80070246h
0x18000551d  jz      short loc_180005543
0x18000551f  cmp     ecx, 80070247h
0x180005525  jz      short loc_180005539
0x180005527  cmp     ecx, 80070272h
0x18000552d  jnz     short loc_180005581
0x18000552f  mov     ecx, 0C0000273h
0x180005534  jmp     loc_1800055D9
0x180005539  mov     ecx, 0C0000163h
0x18000553e  jmp     loc_1800055D9
0x180005543  mov     ecx, 0C0000161h
0x180005548  jmp     loc_1800055D9
0x18000554d  mov     ecx, 0C0000025h
0x180005552  jmp     loc_1800055D9
0x180005557  mov     ecx, 0C0000095h
0x18000555c  jmp     short loc_1800055D9
0x18000555e  mov     ecx, 0C0000059h
0x180005563  jmp     short loc_1800055D9
0x180005565  cmp     ecx, 8007050Ch
0x18000556b  jz      short loc_1800055D4
0x18000556d  cmp     ecx, 8007054Fh
0x180005573  jz      short loc_1800055CD
0x180005575  cmp     ecx, 800705B9h
0x18000557b  jz      short loc_1800055C6
0x18000557d  test    ecx, ecx
0x18000557f  jz      short loc_1800055C2
0x180005581  bt      ecx, 1Ch
0x180005585  jnb     short loc_18000558D
0x180005587  btr     ecx, 1Ch
0x18000558b  jmp     short loc_1800055D9
0x18000558d  mov     eax, ecx
0x18000558f  and     eax, 1FFF0000h
0x180005594  cmp     eax, 70000h
0x180005599  jnz     short loc_1800055AC
0x18000559b  movzx   ecx, cx
0x18000559e  mov     eax, ecx
0x1800055a0  or      eax, 0C0070000h
0x1800055a5  test    ecx, ecx
0x1800055a7  cmovnz  ecx, eax
0x1800055aa  jmp     short loc_1800055D9
0x1800055ac  cmp     eax, 90000h
0x1800055b1  jnz     short loc_1800055CD
0x1800055b3  test    ecx, ecx
0x1800055b5  jle     short loc_1800055D9
0x1800055b7  movzx   ecx, cx
0x1800055ba  or      ecx, 0C0090000h
0x1800055c0  jmp     short loc_1800055D9
0x1800055c2  xor     ecx, ecx
0x1800055c4  jmp     short loc_1800055D9
0x1800055c6  mov     ecx, 0C000A083h
0x1800055cb  jmp     short loc_1800055D9
0x1800055cd  mov     ecx, 0C00000E5h
0x1800055d2  jmp     short loc_1800055D9
0x1800055d4  mov     ecx, 0C000042Bh
0x1800055d9  mov     eax, ecx
0x1800055db  retn
```
