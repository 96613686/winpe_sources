# wil::details::HrToNtStatus(long)

- ea: `0x180012ff0`
- end: `0x1800131ac`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180010254`
- `0x1800102fc`
- `0x18001034c`
- `0x18001040c`
- `0x180012614`
- `0x180013298`

## callees

- `0x180012ff0`

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
0x180012ff0  mov     eax, 800700EAh
0x180012ff5  cmp     ecx, eax
0x180012ff7  jg      loc_1800130CC
0x180012ffd  jz      loc_1800130C2
0x180013003  mov     eax, 80070057h
0x180013008  cmp     ecx, eax
0x18001300a  jg      short loc_180013076
0x18001300c  jz      short loc_18001306C
0x18001300e  cmp     ecx, 80004005h
0x180013014  jz      short loc_180013062
0x180013016  cmp     ecx, 80070001h
0x18001301c  jz      short loc_180013058
0x18001301e  cmp     ecx, 80070002h
0x180013024  jz      short loc_18001304E
0x180013026  cmp     ecx, 80070003h
0x18001302c  jz      short loc_180013044
0x18001302e  cmp     ecx, 8007000Eh
0x180013034  jnz     loc_180013151
0x18001303a  mov     ecx, 0C0000017h
0x18001303f  jmp     loc_1800131A9
0x180013044  mov     ecx, 0C000003Ah
0x180013049  jmp     loc_1800131A9
0x18001304e  mov     ecx, 0C0000034h
0x180013053  jmp     loc_1800131A9
0x180013058  mov     ecx, 0C0000002h
0x18001305d  jmp     loc_1800131A9
0x180013062  mov     ecx, 0C0000001h
0x180013067  jmp     loc_1800131A9
0x18001306c  mov     ecx, 0C000000Dh
0x180013071  jmp     loc_1800131A9
0x180013076  cmp     ecx, 80070070h
0x18001307c  jz      short loc_1800130B8
0x18001307e  cmp     ecx, 8007007Ah
0x180013084  jz      short loc_1800130AE
0x180013086  cmp     ecx, 8007007Bh
0x18001308c  jz      short loc_1800130A4
0x18001308e  cmp     ecx, 8007007Eh
0x180013094  jnz     loc_180013151
0x18001309a  mov     ecx, 0C0000135h
0x18001309f  jmp     loc_1800131A9
0x1800130a4  mov     ecx, 0C0000033h
0x1800130a9  jmp     loc_1800131A9
0x1800130ae  mov     ecx, 0C0000023h
0x1800130b3  jmp     loc_1800131A9
0x1800130b8  mov     ecx, 0C000007Fh
0x1800130bd  jmp     loc_1800131A9
0x1800130c2  mov     ecx, 80000005h
0x1800130c7  jmp     loc_1800131A9
0x1800130cc  mov     eax, 8007047Eh
0x1800130d1  cmp     ecx, eax
0x1800130d3  jg      short loc_180013135
0x1800130d5  jz      short loc_18001312E
0x1800130d7  cmp     ecx, 80070216h
0x1800130dd  jz      short loc_180013127
0x1800130df  cmp     ecx, 8007023Eh
0x1800130e5  jz      short loc_18001311D
0x1800130e7  cmp     ecx, 80070246h
0x1800130ed  jz      short loc_180013113
0x1800130ef  cmp     ecx, 80070247h
0x1800130f5  jz      short loc_180013109
0x1800130f7  cmp     ecx, 80070272h
0x1800130fd  jnz     short loc_180013151
0x1800130ff  mov     ecx, 0C0000273h
0x180013104  jmp     loc_1800131A9
0x180013109  mov     ecx, 0C0000163h
0x18001310e  jmp     loc_1800131A9
0x180013113  mov     ecx, 0C0000161h
0x180013118  jmp     loc_1800131A9
0x18001311d  mov     ecx, 0C0000025h
0x180013122  jmp     loc_1800131A9
0x180013127  mov     ecx, 0C0000095h
0x18001312c  jmp     short loc_1800131A9
0x18001312e  mov     ecx, 0C0000059h
0x180013133  jmp     short loc_1800131A9
0x180013135  cmp     ecx, 8007050Ch
0x18001313b  jz      short loc_1800131A4
0x18001313d  cmp     ecx, 8007054Fh
0x180013143  jz      short loc_18001319D
0x180013145  cmp     ecx, 800705B9h
0x18001314b  jz      short loc_180013196
0x18001314d  test    ecx, ecx
0x18001314f  jz      short loc_180013192
0x180013151  bt      ecx, 1Ch
0x180013155  jnb     short loc_18001315D
0x180013157  btr     ecx, 1Ch
0x18001315b  jmp     short loc_1800131A9
0x18001315d  mov     eax, ecx
0x18001315f  and     eax, 1FFF0000h
0x180013164  cmp     eax, 70000h
0x180013169  jnz     short loc_18001317C
0x18001316b  movzx   ecx, cx
0x18001316e  mov     eax, ecx
0x180013170  or      eax, 0C0070000h
0x180013175  test    ecx, ecx
0x180013177  cmovnz  ecx, eax
0x18001317a  jmp     short loc_1800131A9
0x18001317c  cmp     eax, 90000h
0x180013181  jnz     short loc_18001319D
0x180013183  test    ecx, ecx
0x180013185  jle     short loc_1800131A9
0x180013187  movzx   ecx, cx
0x18001318a  or      ecx, 0C0090000h
0x180013190  jmp     short loc_1800131A9
0x180013192  xor     ecx, ecx
0x180013194  jmp     short loc_1800131A9
0x180013196  mov     ecx, 0C000A083h
0x18001319b  jmp     short loc_1800131A9
0x18001319d  mov     ecx, 0C00000E5h
0x1800131a2  jmp     short loc_1800131A9
0x1800131a4  mov     ecx, 0C000042Bh
0x1800131a9  mov     eax, ecx
0x1800131ab  retn
```
