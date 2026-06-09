# wil::details::HrToNtStatus(long)

- ea: `0x180001c34`
- end: `0x180001df0`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180001bb0`
- `0x180002e80`
- `0x1800044d4`
- `0x1800045c8`
- `0x180004648`
- `0x1800046a0`
- `0x1800061e8`
- `0x180006ac0`
- `0x18000c588`
- `0x1800176ed`
- `0x180017738`
- `0x1800177fb`
- `0x180017846`

## callees

- `0x180001c34`

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
        case 0x8007054F:
          goto LABEL_53;
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
0x180001c34  mov     eax, 800700EAh
0x180001c39  cmp     ecx, eax
0x180001c3b  jg      loc_180001D10
0x180001c41  jz      loc_180001D06
0x180001c47  mov     eax, 80070057h
0x180001c4c  cmp     ecx, eax
0x180001c4e  jg      short loc_180001CBA
0x180001c50  jz      short loc_180001CB0
0x180001c52  cmp     ecx, 80004005h
0x180001c58  jz      short loc_180001CA6
0x180001c5a  cmp     ecx, 80070001h
0x180001c60  jz      short loc_180001C9C
0x180001c62  cmp     ecx, 80070002h
0x180001c68  jz      short loc_180001C92
0x180001c6a  cmp     ecx, 80070003h
0x180001c70  jz      short loc_180001C88
0x180001c72  cmp     ecx, 8007000Eh
0x180001c78  jnz     loc_180001D95
0x180001c7e  mov     ecx, 0C0000017h
0x180001c83  jmp     loc_180001DED
0x180001c88  mov     ecx, 0C000003Ah
0x180001c8d  jmp     loc_180001DED
0x180001c92  mov     ecx, 0C0000034h
0x180001c97  jmp     loc_180001DED
0x180001c9c  mov     ecx, 0C0000002h
0x180001ca1  jmp     loc_180001DED
0x180001ca6  mov     ecx, 0C0000001h
0x180001cab  jmp     loc_180001DED
0x180001cb0  mov     ecx, 0C000000Dh
0x180001cb5  jmp     loc_180001DED
0x180001cba  cmp     ecx, 80070070h
0x180001cc0  jz      short loc_180001CFC
0x180001cc2  cmp     ecx, 8007007Ah
0x180001cc8  jz      short loc_180001CF2
0x180001cca  cmp     ecx, 8007007Bh
0x180001cd0  jz      short loc_180001CE8
0x180001cd2  cmp     ecx, 8007007Eh
0x180001cd8  jnz     loc_180001D95
0x180001cde  mov     ecx, 0C0000135h
0x180001ce3  jmp     loc_180001DED
0x180001ce8  mov     ecx, 0C0000033h
0x180001ced  jmp     loc_180001DED
0x180001cf2  mov     ecx, 0C0000023h
0x180001cf7  jmp     loc_180001DED
0x180001cfc  mov     ecx, 0C000007Fh
0x180001d01  jmp     loc_180001DED
0x180001d06  mov     ecx, 80000005h
0x180001d0b  jmp     loc_180001DED
0x180001d10  mov     eax, 8007047Eh
0x180001d15  cmp     ecx, eax
0x180001d17  jg      short loc_180001D79
0x180001d19  jz      short loc_180001D72
0x180001d1b  cmp     ecx, 80070216h
0x180001d21  jz      short loc_180001D6B
0x180001d23  cmp     ecx, 8007023Eh
0x180001d29  jz      short loc_180001D61
0x180001d2b  cmp     ecx, 80070246h
0x180001d31  jz      short loc_180001D57
0x180001d33  cmp     ecx, 80070247h
0x180001d39  jz      short loc_180001D4D
0x180001d3b  cmp     ecx, 80070272h
0x180001d41  jnz     short loc_180001D95
0x180001d43  mov     ecx, 0C0000273h
0x180001d48  jmp     loc_180001DED
0x180001d4d  mov     ecx, 0C0000163h
0x180001d52  jmp     loc_180001DED
0x180001d57  mov     ecx, 0C0000161h
0x180001d5c  jmp     loc_180001DED
0x180001d61  mov     ecx, 0C0000025h
0x180001d66  jmp     loc_180001DED
0x180001d6b  mov     ecx, 0C0000095h
0x180001d70  jmp     short loc_180001DED
0x180001d72  mov     ecx, 0C0000059h
0x180001d77  jmp     short loc_180001DED
0x180001d79  cmp     ecx, 8007054Fh
0x180001d7f  jz      short loc_180001DE1
0x180001d81  cmp     ecx, 8007050Ch
0x180001d87  jz      short loc_180001DE8
0x180001d89  cmp     ecx, 800705B9h
0x180001d8f  jz      short loc_180001DDA
0x180001d91  test    ecx, ecx
0x180001d93  jz      short loc_180001DD6
0x180001d95  bt      ecx, 1Ch
0x180001d99  jnb     short loc_180001DA1
0x180001d9b  btr     ecx, 1Ch
0x180001d9f  jmp     short loc_180001DED
0x180001da1  mov     eax, ecx
0x180001da3  and     eax, 1FFF0000h
0x180001da8  cmp     eax, 70000h
0x180001dad  jnz     short loc_180001DC0
0x180001daf  movzx   ecx, cx
0x180001db2  mov     eax, ecx
0x180001db4  or      eax, 0C0070000h
0x180001db9  test    ecx, ecx
0x180001dbb  cmovnz  ecx, eax
0x180001dbe  jmp     short loc_180001DED
0x180001dc0  cmp     eax, 90000h
0x180001dc5  jnz     short loc_180001DE1
0x180001dc7  test    ecx, ecx
0x180001dc9  jle     short loc_180001DED
0x180001dcb  movzx   ecx, cx
0x180001dce  or      ecx, 0C0090000h
0x180001dd4  jmp     short loc_180001DED
0x180001dd6  xor     ecx, ecx
0x180001dd8  jmp     short loc_180001DED
0x180001dda  mov     ecx, 0C000A083h
0x180001ddf  jmp     short loc_180001DED
0x180001de1  mov     ecx, 0C00000E5h
0x180001de6  jmp     short loc_180001DED
0x180001de8  mov     ecx, 0C000042Bh
0x180001ded  mov     eax, ecx
0x180001def  retn
```
