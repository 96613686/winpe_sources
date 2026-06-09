# wil::details::HrToNtStatus(long)

- ea: `0x1400050f0`
- end: `0x1400052ac`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140002428`
- `0x1400024a0`
- `0x14000251c`
- `0x14000256c`
- `0x140002bfc`
- `0x1400040c8`
- `0x1400052e0`
- `0x140006080`
- `0x140009a3f`
- `0x140009a8a`
- `0x140009b4d`
- `0x140009b98`

## callees

- `0x1400050f0`

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
0x1400050f0  mov     eax, 800700EAh
0x1400050f5  cmp     ecx, eax
0x1400050f7  jg      loc_1400051CC
0x1400050fd  jz      loc_1400051C2
0x140005103  mov     eax, 80070057h
0x140005108  cmp     ecx, eax
0x14000510a  jg      short loc_140005176
0x14000510c  jz      short loc_14000516C
0x14000510e  cmp     ecx, 80004005h
0x140005114  jz      short loc_140005162
0x140005116  cmp     ecx, 80070001h
0x14000511c  jz      short loc_140005158
0x14000511e  cmp     ecx, 80070002h
0x140005124  jz      short loc_14000514E
0x140005126  cmp     ecx, 80070003h
0x14000512c  jz      short loc_140005144
0x14000512e  cmp     ecx, 8007000Eh
0x140005134  jnz     loc_140005251
0x14000513a  mov     ecx, 0C0000017h
0x14000513f  jmp     loc_1400052A9
0x140005144  mov     ecx, 0C000003Ah
0x140005149  jmp     loc_1400052A9
0x14000514e  mov     ecx, 0C0000034h
0x140005153  jmp     loc_1400052A9
0x140005158  mov     ecx, 0C0000002h
0x14000515d  jmp     loc_1400052A9
0x140005162  mov     ecx, 0C0000001h
0x140005167  jmp     loc_1400052A9
0x14000516c  mov     ecx, 0C000000Dh
0x140005171  jmp     loc_1400052A9
0x140005176  cmp     ecx, 80070070h
0x14000517c  jz      short loc_1400051B8
0x14000517e  cmp     ecx, 8007007Ah
0x140005184  jz      short loc_1400051AE
0x140005186  cmp     ecx, 8007007Bh
0x14000518c  jz      short loc_1400051A4
0x14000518e  cmp     ecx, 8007007Eh
0x140005194  jnz     loc_140005251
0x14000519a  mov     ecx, 0C0000135h
0x14000519f  jmp     loc_1400052A9
0x1400051a4  mov     ecx, 0C0000033h
0x1400051a9  jmp     loc_1400052A9
0x1400051ae  mov     ecx, 0C0000023h
0x1400051b3  jmp     loc_1400052A9
0x1400051b8  mov     ecx, 0C000007Fh
0x1400051bd  jmp     loc_1400052A9
0x1400051c2  mov     ecx, 80000005h
0x1400051c7  jmp     loc_1400052A9
0x1400051cc  mov     eax, 8007047Eh
0x1400051d1  cmp     ecx, eax
0x1400051d3  jg      short loc_140005235
0x1400051d5  jz      short loc_14000522E
0x1400051d7  cmp     ecx, 80070216h
0x1400051dd  jz      short loc_140005227
0x1400051df  cmp     ecx, 8007023Eh
0x1400051e5  jz      short loc_14000521D
0x1400051e7  cmp     ecx, 80070246h
0x1400051ed  jz      short loc_140005213
0x1400051ef  cmp     ecx, 80070247h
0x1400051f5  jz      short loc_140005209
0x1400051f7  cmp     ecx, 80070272h
0x1400051fd  jnz     short loc_140005251
0x1400051ff  mov     ecx, 0C0000273h
0x140005204  jmp     loc_1400052A9
0x140005209  mov     ecx, 0C0000163h
0x14000520e  jmp     loc_1400052A9
0x140005213  mov     ecx, 0C0000161h
0x140005218  jmp     loc_1400052A9
0x14000521d  mov     ecx, 0C0000025h
0x140005222  jmp     loc_1400052A9
0x140005227  mov     ecx, 0C0000095h
0x14000522c  jmp     short loc_1400052A9
0x14000522e  mov     ecx, 0C0000059h
0x140005233  jmp     short loc_1400052A9
0x140005235  cmp     ecx, 8007050Ch
0x14000523b  jz      short loc_1400052A4
0x14000523d  cmp     ecx, 8007054Fh
0x140005243  jz      short loc_14000529D
0x140005245  cmp     ecx, 800705B9h
0x14000524b  jz      short loc_140005296
0x14000524d  test    ecx, ecx
0x14000524f  jz      short loc_140005292
0x140005251  bt      ecx, 1Ch
0x140005255  jnb     short loc_14000525D
0x140005257  btr     ecx, 1Ch
0x14000525b  jmp     short loc_1400052A9
0x14000525d  mov     eax, ecx
0x14000525f  and     eax, 1FFF0000h
0x140005264  cmp     eax, 70000h
0x140005269  jnz     short loc_14000527C
0x14000526b  movzx   ecx, cx
0x14000526e  mov     eax, ecx
0x140005270  or      eax, 0C0070000h
0x140005275  test    ecx, ecx
0x140005277  cmovnz  ecx, eax
0x14000527a  jmp     short loc_1400052A9
0x14000527c  cmp     eax, 90000h
0x140005281  jnz     short loc_14000529D
0x140005283  test    ecx, ecx
0x140005285  jle     short loc_1400052A9
0x140005287  movzx   ecx, cx
0x14000528a  or      ecx, 0C0090000h
0x140005290  jmp     short loc_1400052A9
0x140005292  xor     ecx, ecx
0x140005294  jmp     short loc_1400052A9
0x140005296  mov     ecx, 0C000A083h
0x14000529b  jmp     short loc_1400052A9
0x14000529d  mov     ecx, 0C00000E5h
0x1400052a2  jmp     short loc_1400052A9
0x1400052a4  mov     ecx, 0C000042Bh
0x1400052a9  mov     eax, ecx
0x1400052ab  retn
```
