# wil::details::HrToNtStatus(long)

- ea: `0x140005ed4`
- end: `0x140006090`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x140003adc`
- `0x140003bd0`
- `0x140003c50`
- `0x140003cd4`
- `0x140003d2c`
- `0x14000429c`
- `0x140005378`
- `0x140006194`
- `0x140006a00`
- `0x140019666`
- `0x1400196b1`
- `0x140019774`
- `0x1400197bf`

## callees

- `0x140005ed4`

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
0x140005ed4  mov     eax, 800700EAh
0x140005ed9  cmp     ecx, eax
0x140005edb  jg      loc_140005FB0
0x140005ee1  jz      loc_140005FA6
0x140005ee7  mov     eax, 80070057h
0x140005eec  cmp     ecx, eax
0x140005eee  jg      short loc_140005F5A
0x140005ef0  jz      short loc_140005F50
0x140005ef2  cmp     ecx, 80004005h
0x140005ef8  jz      short loc_140005F46
0x140005efa  cmp     ecx, 80070001h
0x140005f00  jz      short loc_140005F3C
0x140005f02  cmp     ecx, 80070002h
0x140005f08  jz      short loc_140005F32
0x140005f0a  cmp     ecx, 80070003h
0x140005f10  jz      short loc_140005F28
0x140005f12  cmp     ecx, 8007000Eh
0x140005f18  jnz     loc_140006035
0x140005f1e  mov     ecx, 0C0000017h
0x140005f23  jmp     loc_14000608D
0x140005f28  mov     ecx, 0C000003Ah
0x140005f2d  jmp     loc_14000608D
0x140005f32  mov     ecx, 0C0000034h
0x140005f37  jmp     loc_14000608D
0x140005f3c  mov     ecx, 0C0000002h
0x140005f41  jmp     loc_14000608D
0x140005f46  mov     ecx, 0C0000001h
0x140005f4b  jmp     loc_14000608D
0x140005f50  mov     ecx, 0C000000Dh
0x140005f55  jmp     loc_14000608D
0x140005f5a  cmp     ecx, 80070070h
0x140005f60  jz      short loc_140005F9C
0x140005f62  cmp     ecx, 8007007Ah
0x140005f68  jz      short loc_140005F92
0x140005f6a  cmp     ecx, 8007007Bh
0x140005f70  jz      short loc_140005F88
0x140005f72  cmp     ecx, 8007007Eh
0x140005f78  jnz     loc_140006035
0x140005f7e  mov     ecx, 0C0000135h
0x140005f83  jmp     loc_14000608D
0x140005f88  mov     ecx, 0C0000033h
0x140005f8d  jmp     loc_14000608D
0x140005f92  mov     ecx, 0C0000023h
0x140005f97  jmp     loc_14000608D
0x140005f9c  mov     ecx, 0C000007Fh
0x140005fa1  jmp     loc_14000608D
0x140005fa6  mov     ecx, 80000005h
0x140005fab  jmp     loc_14000608D
0x140005fb0  mov     eax, 8007047Eh
0x140005fb5  cmp     ecx, eax
0x140005fb7  jg      short loc_140006019
0x140005fb9  jz      short loc_140006012
0x140005fbb  cmp     ecx, 80070216h
0x140005fc1  jz      short loc_14000600B
0x140005fc3  cmp     ecx, 8007023Eh
0x140005fc9  jz      short loc_140006001
0x140005fcb  cmp     ecx, 80070246h
0x140005fd1  jz      short loc_140005FF7
0x140005fd3  cmp     ecx, 80070247h
0x140005fd9  jz      short loc_140005FED
0x140005fdb  cmp     ecx, 80070272h
0x140005fe1  jnz     short loc_140006035
0x140005fe3  mov     ecx, 0C0000273h
0x140005fe8  jmp     loc_14000608D
0x140005fed  mov     ecx, 0C0000163h
0x140005ff2  jmp     loc_14000608D
0x140005ff7  mov     ecx, 0C0000161h
0x140005ffc  jmp     loc_14000608D
0x140006001  mov     ecx, 0C0000025h
0x140006006  jmp     loc_14000608D
0x14000600b  mov     ecx, 0C0000095h
0x140006010  jmp     short loc_14000608D
0x140006012  mov     ecx, 0C0000059h
0x140006017  jmp     short loc_14000608D
0x140006019  cmp     ecx, 8007050Ch
0x14000601f  jz      short loc_140006088
0x140006021  cmp     ecx, 8007054Fh
0x140006027  jz      short loc_140006081
0x140006029  cmp     ecx, 800705B9h
0x14000602f  jz      short loc_14000607A
0x140006031  test    ecx, ecx
0x140006033  jz      short loc_140006076
0x140006035  bt      ecx, 1Ch
0x140006039  jnb     short loc_140006041
0x14000603b  btr     ecx, 1Ch
0x14000603f  jmp     short loc_14000608D
0x140006041  mov     eax, ecx
0x140006043  and     eax, 1FFF0000h
0x140006048  cmp     eax, 70000h
0x14000604d  jnz     short loc_140006060
0x14000604f  movzx   ecx, cx
0x140006052  mov     eax, ecx
0x140006054  or      eax, 0C0070000h
0x140006059  test    ecx, ecx
0x14000605b  cmovnz  ecx, eax
0x14000605e  jmp     short loc_14000608D
0x140006060  cmp     eax, 90000h
0x140006065  jnz     short loc_140006081
0x140006067  test    ecx, ecx
0x140006069  jle     short loc_14000608D
0x14000606b  movzx   ecx, cx
0x14000606e  or      ecx, 0C0090000h
0x140006074  jmp     short loc_14000608D
0x140006076  xor     ecx, ecx
0x140006078  jmp     short loc_14000608D
0x14000607a  mov     ecx, 0C000A083h
0x14000607f  jmp     short loc_14000608D
0x140006081  mov     ecx, 0C00000E5h
0x140006086  jmp     short loc_14000608D
0x140006088  mov     ecx, 0C000042Bh
0x14000608d  mov     eax, ecx
0x14000608f  retn
```
