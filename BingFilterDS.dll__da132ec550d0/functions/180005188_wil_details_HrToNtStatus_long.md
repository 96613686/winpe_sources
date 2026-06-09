# wil::details::HrToNtStatus(long)

- ea: `0x180005188`
- end: `0x180005344`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180003050`
- `0x180003100`
- `0x180003158`
- `0x180003220`
- `0x180004648`
- `0x1800054b8`
- `0x1800060e0`
- `0x180007b68`
- `0x180007cbc`
- `0x18000ca3e`
- `0x18000caa9`
- `0x18000cb72`
- `0x18000cbdd`

## callees

- `0x180005188`

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
0x180005188  mov     eax, 800700EAh
0x18000518d  cmp     ecx, eax
0x18000518f  jg      loc_180005264
0x180005195  jz      loc_18000525A
0x18000519b  mov     eax, 80070057h
0x1800051a0  cmp     ecx, eax
0x1800051a2  jg      short loc_18000520E
0x1800051a4  jz      short loc_180005204
0x1800051a6  cmp     ecx, 80004005h
0x1800051ac  jz      short loc_1800051FA
0x1800051ae  cmp     ecx, 80070001h
0x1800051b4  jz      short loc_1800051F0
0x1800051b6  cmp     ecx, 80070002h
0x1800051bc  jz      short loc_1800051E6
0x1800051be  cmp     ecx, 80070003h
0x1800051c4  jz      short loc_1800051DC
0x1800051c6  cmp     ecx, 8007000Eh
0x1800051cc  jnz     loc_1800052E9
0x1800051d2  mov     ecx, 0C0000017h
0x1800051d7  jmp     loc_180005341
0x1800051dc  mov     ecx, 0C000003Ah
0x1800051e1  jmp     loc_180005341
0x1800051e6  mov     ecx, 0C0000034h
0x1800051eb  jmp     loc_180005341
0x1800051f0  mov     ecx, 0C0000002h
0x1800051f5  jmp     loc_180005341
0x1800051fa  mov     ecx, 0C0000001h
0x1800051ff  jmp     loc_180005341
0x180005204  mov     ecx, 0C000000Dh
0x180005209  jmp     loc_180005341
0x18000520e  cmp     ecx, 80070070h
0x180005214  jz      short loc_180005250
0x180005216  cmp     ecx, 8007007Ah
0x18000521c  jz      short loc_180005246
0x18000521e  cmp     ecx, 8007007Bh
0x180005224  jz      short loc_18000523C
0x180005226  cmp     ecx, 8007007Eh
0x18000522c  jnz     loc_1800052E9
0x180005232  mov     ecx, 0C0000135h
0x180005237  jmp     loc_180005341
0x18000523c  mov     ecx, 0C0000033h
0x180005241  jmp     loc_180005341
0x180005246  mov     ecx, 0C0000023h
0x18000524b  jmp     loc_180005341
0x180005250  mov     ecx, 0C000007Fh
0x180005255  jmp     loc_180005341
0x18000525a  mov     ecx, 80000005h
0x18000525f  jmp     loc_180005341
0x180005264  mov     eax, 8007047Eh
0x180005269  cmp     ecx, eax
0x18000526b  jg      short loc_1800052CD
0x18000526d  jz      short loc_1800052C6
0x18000526f  cmp     ecx, 80070216h
0x180005275  jz      short loc_1800052BF
0x180005277  cmp     ecx, 8007023Eh
0x18000527d  jz      short loc_1800052B5
0x18000527f  cmp     ecx, 80070246h
0x180005285  jz      short loc_1800052AB
0x180005287  cmp     ecx, 80070247h
0x18000528d  jz      short loc_1800052A1
0x18000528f  cmp     ecx, 80070272h
0x180005295  jnz     short loc_1800052E9
0x180005297  mov     ecx, 0C0000273h
0x18000529c  jmp     loc_180005341
0x1800052a1  mov     ecx, 0C0000163h
0x1800052a6  jmp     loc_180005341
0x1800052ab  mov     ecx, 0C0000161h
0x1800052b0  jmp     loc_180005341
0x1800052b5  mov     ecx, 0C0000025h
0x1800052ba  jmp     loc_180005341
0x1800052bf  mov     ecx, 0C0000095h
0x1800052c4  jmp     short loc_180005341
0x1800052c6  mov     ecx, 0C0000059h
0x1800052cb  jmp     short loc_180005341
0x1800052cd  cmp     ecx, 8007050Ch
0x1800052d3  jz      short loc_18000533C
0x1800052d5  cmp     ecx, 8007054Fh
0x1800052db  jz      short loc_180005335
0x1800052dd  cmp     ecx, 800705B9h
0x1800052e3  jz      short loc_18000532E
0x1800052e5  test    ecx, ecx
0x1800052e7  jz      short loc_18000532A
0x1800052e9  bt      ecx, 1Ch
0x1800052ed  jnb     short loc_1800052F5
0x1800052ef  btr     ecx, 1Ch
0x1800052f3  jmp     short loc_180005341
0x1800052f5  mov     eax, ecx
0x1800052f7  and     eax, 1FFF0000h
0x1800052fc  cmp     eax, 70000h
0x180005301  jnz     short loc_180005314
0x180005303  movzx   ecx, cx
0x180005306  mov     eax, ecx
0x180005308  or      eax, 0C0070000h
0x18000530d  test    ecx, ecx
0x18000530f  cmovnz  ecx, eax
0x180005312  jmp     short loc_180005341
0x180005314  cmp     eax, 90000h
0x180005319  jnz     short loc_180005335
0x18000531b  test    ecx, ecx
0x18000531d  jle     short loc_180005341
0x18000531f  movzx   ecx, cx
0x180005322  or      ecx, 0C0090000h
0x180005328  jmp     short loc_180005341
0x18000532a  xor     ecx, ecx
0x18000532c  jmp     short loc_180005341
0x18000532e  mov     ecx, 0C000A083h
0x180005333  jmp     short loc_180005341
0x180005335  mov     ecx, 0C00000E5h
0x18000533a  jmp     short loc_180005341
0x18000533c  mov     ecx, 0C000042Bh
0x180005341  mov     eax, ecx
0x180005343  retn
```
