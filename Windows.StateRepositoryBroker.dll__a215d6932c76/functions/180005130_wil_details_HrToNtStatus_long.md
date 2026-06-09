# wil::details::HrToNtStatus(long)

- ea: `0x180005130`
- end: `0x1800052ec`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000358c`
- `0x1800035dc`
- `0x1800047f0`
- `0x1800053f8`
- `0x1800078b0`
- `0x1800079d0`

## callees

- `0x180005130`

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
0x180005130  mov     eax, 800700EAh
0x180005135  cmp     ecx, eax
0x180005137  jg      loc_18000520C
0x18000513d  jz      loc_180005202
0x180005143  mov     eax, 80070057h
0x180005148  cmp     ecx, eax
0x18000514a  jg      short loc_1800051B6
0x18000514c  jz      short loc_1800051AC
0x18000514e  cmp     ecx, 80004005h
0x180005154  jz      short loc_1800051A2
0x180005156  cmp     ecx, 80070001h
0x18000515c  jz      short loc_180005198
0x18000515e  cmp     ecx, 80070002h
0x180005164  jz      short loc_18000518E
0x180005166  cmp     ecx, 80070003h
0x18000516c  jz      short loc_180005184
0x18000516e  cmp     ecx, 8007000Eh
0x180005174  jnz     loc_180005291
0x18000517a  mov     ecx, 0C0000017h
0x18000517f  jmp     loc_1800052E9
0x180005184  mov     ecx, 0C000003Ah
0x180005189  jmp     loc_1800052E9
0x18000518e  mov     ecx, 0C0000034h
0x180005193  jmp     loc_1800052E9
0x180005198  mov     ecx, 0C0000002h
0x18000519d  jmp     loc_1800052E9
0x1800051a2  mov     ecx, 0C0000001h
0x1800051a7  jmp     loc_1800052E9
0x1800051ac  mov     ecx, 0C000000Dh
0x1800051b1  jmp     loc_1800052E9
0x1800051b6  cmp     ecx, 80070070h
0x1800051bc  jz      short loc_1800051F8
0x1800051be  cmp     ecx, 8007007Ah
0x1800051c4  jz      short loc_1800051EE
0x1800051c6  cmp     ecx, 8007007Bh
0x1800051cc  jz      short loc_1800051E4
0x1800051ce  cmp     ecx, 8007007Eh
0x1800051d4  jnz     loc_180005291
0x1800051da  mov     ecx, 0C0000135h
0x1800051df  jmp     loc_1800052E9
0x1800051e4  mov     ecx, 0C0000033h
0x1800051e9  jmp     loc_1800052E9
0x1800051ee  mov     ecx, 0C0000023h
0x1800051f3  jmp     loc_1800052E9
0x1800051f8  mov     ecx, 0C000007Fh
0x1800051fd  jmp     loc_1800052E9
0x180005202  mov     ecx, 80000005h
0x180005207  jmp     loc_1800052E9
0x18000520c  mov     eax, 8007047Eh
0x180005211  cmp     ecx, eax
0x180005213  jg      short loc_180005275
0x180005215  jz      short loc_18000526E
0x180005217  cmp     ecx, 80070216h
0x18000521d  jz      short loc_180005267
0x18000521f  cmp     ecx, 8007023Eh
0x180005225  jz      short loc_18000525D
0x180005227  cmp     ecx, 80070246h
0x18000522d  jz      short loc_180005253
0x18000522f  cmp     ecx, 80070247h
0x180005235  jz      short loc_180005249
0x180005237  cmp     ecx, 80070272h
0x18000523d  jnz     short loc_180005291
0x18000523f  mov     ecx, 0C0000273h
0x180005244  jmp     loc_1800052E9
0x180005249  mov     ecx, 0C0000163h
0x18000524e  jmp     loc_1800052E9
0x180005253  mov     ecx, 0C0000161h
0x180005258  jmp     loc_1800052E9
0x18000525d  mov     ecx, 0C0000025h
0x180005262  jmp     loc_1800052E9
0x180005267  mov     ecx, 0C0000095h
0x18000526c  jmp     short loc_1800052E9
0x18000526e  mov     ecx, 0C0000059h
0x180005273  jmp     short loc_1800052E9
0x180005275  cmp     ecx, 8007050Ch
0x18000527b  jz      short loc_1800052E4
0x18000527d  cmp     ecx, 8007054Fh
0x180005283  jz      short loc_1800052DD
0x180005285  cmp     ecx, 800705B9h
0x18000528b  jz      short loc_1800052D6
0x18000528d  test    ecx, ecx
0x18000528f  jz      short loc_1800052D2
0x180005291  bt      ecx, 1Ch
0x180005295  jnb     short loc_18000529D
0x180005297  btr     ecx, 1Ch
0x18000529b  jmp     short loc_1800052E9
0x18000529d  mov     eax, ecx
0x18000529f  and     eax, 1FFF0000h
0x1800052a4  cmp     eax, 70000h
0x1800052a9  jnz     short loc_1800052BC
0x1800052ab  movzx   ecx, cx
0x1800052ae  mov     eax, ecx
0x1800052b0  or      eax, 0C0070000h
0x1800052b5  test    ecx, ecx
0x1800052b7  cmovnz  ecx, eax
0x1800052ba  jmp     short loc_1800052E9
0x1800052bc  cmp     eax, 90000h
0x1800052c1  jnz     short loc_1800052DD
0x1800052c3  test    ecx, ecx
0x1800052c5  jle     short loc_1800052E9
0x1800052c7  movzx   ecx, cx
0x1800052ca  or      ecx, 0C0090000h
0x1800052d0  jmp     short loc_1800052E9
0x1800052d2  xor     ecx, ecx
0x1800052d4  jmp     short loc_1800052E9
0x1800052d6  mov     ecx, 0C000A083h
0x1800052db  jmp     short loc_1800052E9
0x1800052dd  mov     ecx, 0C00000E5h
0x1800052e2  jmp     short loc_1800052E9
0x1800052e4  mov     ecx, 0C000042Bh
0x1800052e9  mov     eax, ecx
0x1800052eb  retn
```
