# wil::details::HrToNtStatus(long)

- ea: `0x180007278`
- end: `0x180007434`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `20`
- callee_count: `1`
- tags: ``

## callers

- `0x180003e14`
- `0x180003f08`
- `0x180004008`
- `0x1800040a0`
- `0x180004120`
- `0x18000418c`
- `0x180004210`
- `0x180004268`
- `0x180004390`
- `0x180004990`
- `0x180006838`
- `0x180007ab4`
- `0x180008fb0`
- `0x18000c0ec`
- `0x18000d930`
- `0x18000fb00`
- `0x1800112a5`
- `0x1800112f0`
- `0x1800113b3`
- `0x1800113fe`

## callees

- `0x180007278`

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
0x180007278  mov     eax, 800700EAh
0x18000727d  cmp     ecx, eax
0x18000727f  jg      loc_180007354
0x180007285  jz      loc_18000734A
0x18000728b  mov     eax, 80070057h
0x180007290  cmp     ecx, eax
0x180007292  jg      short loc_1800072FE
0x180007294  jz      short loc_1800072F4
0x180007296  cmp     ecx, 80004005h
0x18000729c  jz      short loc_1800072EA
0x18000729e  cmp     ecx, 80070001h
0x1800072a4  jz      short loc_1800072E0
0x1800072a6  cmp     ecx, 80070002h
0x1800072ac  jz      short loc_1800072D6
0x1800072ae  cmp     ecx, 80070003h
0x1800072b4  jz      short loc_1800072CC
0x1800072b6  cmp     ecx, 8007000Eh
0x1800072bc  jnz     loc_1800073D9
0x1800072c2  mov     ecx, 0C0000017h
0x1800072c7  jmp     loc_180007431
0x1800072cc  mov     ecx, 0C000003Ah
0x1800072d1  jmp     loc_180007431
0x1800072d6  mov     ecx, 0C0000034h
0x1800072db  jmp     loc_180007431
0x1800072e0  mov     ecx, 0C0000002h
0x1800072e5  jmp     loc_180007431
0x1800072ea  mov     ecx, 0C0000001h
0x1800072ef  jmp     loc_180007431
0x1800072f4  mov     ecx, 0C000000Dh
0x1800072f9  jmp     loc_180007431
0x1800072fe  cmp     ecx, 80070070h
0x180007304  jz      short loc_180007340
0x180007306  cmp     ecx, 8007007Ah
0x18000730c  jz      short loc_180007336
0x18000730e  cmp     ecx, 8007007Bh
0x180007314  jz      short loc_18000732C
0x180007316  cmp     ecx, 8007007Eh
0x18000731c  jnz     loc_1800073D9
0x180007322  mov     ecx, 0C0000135h
0x180007327  jmp     loc_180007431
0x18000732c  mov     ecx, 0C0000033h
0x180007331  jmp     loc_180007431
0x180007336  mov     ecx, 0C0000023h
0x18000733b  jmp     loc_180007431
0x180007340  mov     ecx, 0C000007Fh
0x180007345  jmp     loc_180007431
0x18000734a  mov     ecx, 80000005h
0x18000734f  jmp     loc_180007431
0x180007354  mov     eax, 8007047Eh
0x180007359  cmp     ecx, eax
0x18000735b  jg      short loc_1800073BD
0x18000735d  jz      short loc_1800073B6
0x18000735f  cmp     ecx, 80070216h
0x180007365  jz      short loc_1800073AF
0x180007367  cmp     ecx, 8007023Eh
0x18000736d  jz      short loc_1800073A5
0x18000736f  cmp     ecx, 80070246h
0x180007375  jz      short loc_18000739B
0x180007377  cmp     ecx, 80070247h
0x18000737d  jz      short loc_180007391
0x18000737f  cmp     ecx, 80070272h
0x180007385  jnz     short loc_1800073D9
0x180007387  mov     ecx, 0C0000273h
0x18000738c  jmp     loc_180007431
0x180007391  mov     ecx, 0C0000163h
0x180007396  jmp     loc_180007431
0x18000739b  mov     ecx, 0C0000161h
0x1800073a0  jmp     loc_180007431
0x1800073a5  mov     ecx, 0C0000025h
0x1800073aa  jmp     loc_180007431
0x1800073af  mov     ecx, 0C0000095h
0x1800073b4  jmp     short loc_180007431
0x1800073b6  mov     ecx, 0C0000059h
0x1800073bb  jmp     short loc_180007431
0x1800073bd  cmp     ecx, 8007050Ch
0x1800073c3  jz      short loc_18000742C
0x1800073c5  cmp     ecx, 8007054Fh
0x1800073cb  jz      short loc_180007425
0x1800073cd  cmp     ecx, 800705B9h
0x1800073d3  jz      short loc_18000741E
0x1800073d5  test    ecx, ecx
0x1800073d7  jz      short loc_18000741A
0x1800073d9  bt      ecx, 1Ch
0x1800073dd  jnb     short loc_1800073E5
0x1800073df  btr     ecx, 1Ch
0x1800073e3  jmp     short loc_180007431
0x1800073e5  mov     eax, ecx
0x1800073e7  and     eax, 1FFF0000h
0x1800073ec  cmp     eax, 70000h
0x1800073f1  jnz     short loc_180007404
0x1800073f3  movzx   ecx, cx
0x1800073f6  mov     eax, ecx
0x1800073f8  or      eax, 0C0070000h
0x1800073fd  test    ecx, ecx
0x1800073ff  cmovnz  ecx, eax
0x180007402  jmp     short loc_180007431
0x180007404  cmp     eax, 90000h
0x180007409  jnz     short loc_180007425
0x18000740b  test    ecx, ecx
0x18000740d  jle     short loc_180007431
0x18000740f  movzx   ecx, cx
0x180007412  or      ecx, 0C0090000h
0x180007418  jmp     short loc_180007431
0x18000741a  xor     ecx, ecx
0x18000741c  jmp     short loc_180007431
0x18000741e  mov     ecx, 0C000A083h
0x180007423  jmp     short loc_180007431
0x180007425  mov     ecx, 0C00000E5h
0x18000742a  jmp     short loc_180007431
0x18000742c  mov     ecx, 0C000042Bh
0x180007431  mov     eax, ecx
0x180007433  retn
```
