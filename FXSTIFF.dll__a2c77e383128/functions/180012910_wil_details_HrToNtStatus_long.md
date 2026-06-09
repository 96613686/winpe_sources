# wil::details::HrToNtStatus(long)

- ea: `0x180012910`
- end: `0x180012acc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fab4`
- `0x18000fb54`
- `0x18000fba4`
- `0x18000fc64`
- `0x180011fa8`
- `0x180012b9c`

## callees

- `0x180012910`

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
0x180012910  mov     eax, 800700EAh
0x180012915  cmp     ecx, eax
0x180012917  jg      loc_1800129EC
0x18001291d  jz      loc_1800129E2
0x180012923  mov     eax, 80070057h
0x180012928  cmp     ecx, eax
0x18001292a  jg      short loc_180012996
0x18001292c  jz      short loc_18001298C
0x18001292e  cmp     ecx, 80004005h
0x180012934  jz      short loc_180012982
0x180012936  cmp     ecx, 80070001h
0x18001293c  jz      short loc_180012978
0x18001293e  cmp     ecx, 80070002h
0x180012944  jz      short loc_18001296E
0x180012946  cmp     ecx, 80070003h
0x18001294c  jz      short loc_180012964
0x18001294e  cmp     ecx, 8007000Eh
0x180012954  jnz     loc_180012A71
0x18001295a  mov     ecx, 0C0000017h
0x18001295f  jmp     loc_180012AC9
0x180012964  mov     ecx, 0C000003Ah
0x180012969  jmp     loc_180012AC9
0x18001296e  mov     ecx, 0C0000034h
0x180012973  jmp     loc_180012AC9
0x180012978  mov     ecx, 0C0000002h
0x18001297d  jmp     loc_180012AC9
0x180012982  mov     ecx, 0C0000001h
0x180012987  jmp     loc_180012AC9
0x18001298c  mov     ecx, 0C000000Dh
0x180012991  jmp     loc_180012AC9
0x180012996  cmp     ecx, 80070070h
0x18001299c  jz      short loc_1800129D8
0x18001299e  cmp     ecx, 8007007Ah
0x1800129a4  jz      short loc_1800129CE
0x1800129a6  cmp     ecx, 8007007Bh
0x1800129ac  jz      short loc_1800129C4
0x1800129ae  cmp     ecx, 8007007Eh
0x1800129b4  jnz     loc_180012A71
0x1800129ba  mov     ecx, 0C0000135h
0x1800129bf  jmp     loc_180012AC9
0x1800129c4  mov     ecx, 0C0000033h
0x1800129c9  jmp     loc_180012AC9
0x1800129ce  mov     ecx, 0C0000023h
0x1800129d3  jmp     loc_180012AC9
0x1800129d8  mov     ecx, 0C000007Fh
0x1800129dd  jmp     loc_180012AC9
0x1800129e2  mov     ecx, 80000005h
0x1800129e7  jmp     loc_180012AC9
0x1800129ec  mov     eax, 8007047Eh
0x1800129f1  cmp     ecx, eax
0x1800129f3  jg      short loc_180012A55
0x1800129f5  jz      short loc_180012A4E
0x1800129f7  cmp     ecx, 80070216h
0x1800129fd  jz      short loc_180012A47
0x1800129ff  cmp     ecx, 8007023Eh
0x180012a05  jz      short loc_180012A3D
0x180012a07  cmp     ecx, 80070246h
0x180012a0d  jz      short loc_180012A33
0x180012a0f  cmp     ecx, 80070247h
0x180012a15  jz      short loc_180012A29
0x180012a17  cmp     ecx, 80070272h
0x180012a1d  jnz     short loc_180012A71
0x180012a1f  mov     ecx, 0C0000273h
0x180012a24  jmp     loc_180012AC9
0x180012a29  mov     ecx, 0C0000163h
0x180012a2e  jmp     loc_180012AC9
0x180012a33  mov     ecx, 0C0000161h
0x180012a38  jmp     loc_180012AC9
0x180012a3d  mov     ecx, 0C0000025h
0x180012a42  jmp     loc_180012AC9
0x180012a47  mov     ecx, 0C0000095h
0x180012a4c  jmp     short loc_180012AC9
0x180012a4e  mov     ecx, 0C0000059h
0x180012a53  jmp     short loc_180012AC9
0x180012a55  cmp     ecx, 8007050Ch
0x180012a5b  jz      short loc_180012AC4
0x180012a5d  cmp     ecx, 8007054Fh
0x180012a63  jz      short loc_180012ABD
0x180012a65  cmp     ecx, 800705B9h
0x180012a6b  jz      short loc_180012AB6
0x180012a6d  test    ecx, ecx
0x180012a6f  jz      short loc_180012AB2
0x180012a71  bt      ecx, 1Ch
0x180012a75  jnb     short loc_180012A7D
0x180012a77  btr     ecx, 1Ch
0x180012a7b  jmp     short loc_180012AC9
0x180012a7d  mov     eax, ecx
0x180012a7f  and     eax, 1FFF0000h
0x180012a84  cmp     eax, 70000h
0x180012a89  jnz     short loc_180012A9C
0x180012a8b  movzx   ecx, cx
0x180012a8e  mov     eax, ecx
0x180012a90  or      eax, 0C0070000h
0x180012a95  test    ecx, ecx
0x180012a97  cmovnz  ecx, eax
0x180012a9a  jmp     short loc_180012AC9
0x180012a9c  cmp     eax, 90000h
0x180012aa1  jnz     short loc_180012ABD
0x180012aa3  test    ecx, ecx
0x180012aa5  jle     short loc_180012AC9
0x180012aa7  movzx   ecx, cx
0x180012aaa  or      ecx, 0C0090000h
0x180012ab0  jmp     short loc_180012AC9
0x180012ab2  xor     ecx, ecx
0x180012ab4  jmp     short loc_180012AC9
0x180012ab6  mov     ecx, 0C000A083h
0x180012abb  jmp     short loc_180012AC9
0x180012abd  mov     ecx, 0C00000E5h
0x180012ac2  jmp     short loc_180012AC9
0x180012ac4  mov     ecx, 0C000042Bh
0x180012ac9  mov     eax, ecx
0x180012acb  retn
```
