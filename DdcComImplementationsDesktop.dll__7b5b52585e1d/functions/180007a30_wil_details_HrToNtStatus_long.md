# wil::details::HrToNtStatus(long)

- ea: `0x180007a30`
- end: `0x180007bec`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e80`
- `0x180004f20`
- `0x180004f70`
- `0x180005030`
- `0x180007008`
- `0x180007bf4`

## callees

- `0x180007a30`

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
0x180007a30  mov     eax, 800700EAh
0x180007a35  cmp     ecx, eax
0x180007a37  jg      loc_180007B0C
0x180007a3d  jz      loc_180007B02
0x180007a43  mov     eax, 80070057h
0x180007a48  cmp     ecx, eax
0x180007a4a  jg      short loc_180007AB6
0x180007a4c  jz      short loc_180007AAC
0x180007a4e  cmp     ecx, 80004005h
0x180007a54  jz      short loc_180007AA2
0x180007a56  cmp     ecx, 80070001h
0x180007a5c  jz      short loc_180007A98
0x180007a5e  cmp     ecx, 80070002h
0x180007a64  jz      short loc_180007A8E
0x180007a66  cmp     ecx, 80070003h
0x180007a6c  jz      short loc_180007A84
0x180007a6e  cmp     ecx, 8007000Eh
0x180007a74  jnz     loc_180007B91
0x180007a7a  mov     ecx, 0C0000017h
0x180007a7f  jmp     loc_180007BE9
0x180007a84  mov     ecx, 0C000003Ah
0x180007a89  jmp     loc_180007BE9
0x180007a8e  mov     ecx, 0C0000034h
0x180007a93  jmp     loc_180007BE9
0x180007a98  mov     ecx, 0C0000002h
0x180007a9d  jmp     loc_180007BE9
0x180007aa2  mov     ecx, 0C0000001h
0x180007aa7  jmp     loc_180007BE9
0x180007aac  mov     ecx, 0C000000Dh
0x180007ab1  jmp     loc_180007BE9
0x180007ab6  cmp     ecx, 80070070h
0x180007abc  jz      short loc_180007AF8
0x180007abe  cmp     ecx, 8007007Ah
0x180007ac4  jz      short loc_180007AEE
0x180007ac6  cmp     ecx, 8007007Bh
0x180007acc  jz      short loc_180007AE4
0x180007ace  cmp     ecx, 8007007Eh
0x180007ad4  jnz     loc_180007B91
0x180007ada  mov     ecx, 0C0000135h
0x180007adf  jmp     loc_180007BE9
0x180007ae4  mov     ecx, 0C0000033h
0x180007ae9  jmp     loc_180007BE9
0x180007aee  mov     ecx, 0C0000023h
0x180007af3  jmp     loc_180007BE9
0x180007af8  mov     ecx, 0C000007Fh
0x180007afd  jmp     loc_180007BE9
0x180007b02  mov     ecx, 80000005h
0x180007b07  jmp     loc_180007BE9
0x180007b0c  mov     eax, 8007047Eh
0x180007b11  cmp     ecx, eax
0x180007b13  jg      short loc_180007B75
0x180007b15  jz      short loc_180007B6E
0x180007b17  cmp     ecx, 80070216h
0x180007b1d  jz      short loc_180007B67
0x180007b1f  cmp     ecx, 8007023Eh
0x180007b25  jz      short loc_180007B5D
0x180007b27  cmp     ecx, 80070246h
0x180007b2d  jz      short loc_180007B53
0x180007b2f  cmp     ecx, 80070247h
0x180007b35  jz      short loc_180007B49
0x180007b37  cmp     ecx, 80070272h
0x180007b3d  jnz     short loc_180007B91
0x180007b3f  mov     ecx, 0C0000273h
0x180007b44  jmp     loc_180007BE9
0x180007b49  mov     ecx, 0C0000163h
0x180007b4e  jmp     loc_180007BE9
0x180007b53  mov     ecx, 0C0000161h
0x180007b58  jmp     loc_180007BE9
0x180007b5d  mov     ecx, 0C0000025h
0x180007b62  jmp     loc_180007BE9
0x180007b67  mov     ecx, 0C0000095h
0x180007b6c  jmp     short loc_180007BE9
0x180007b6e  mov     ecx, 0C0000059h
0x180007b73  jmp     short loc_180007BE9
0x180007b75  cmp     ecx, 8007050Ch
0x180007b7b  jz      short loc_180007BE4
0x180007b7d  cmp     ecx, 8007054Fh
0x180007b83  jz      short loc_180007BDD
0x180007b85  cmp     ecx, 800705B9h
0x180007b8b  jz      short loc_180007BD6
0x180007b8d  test    ecx, ecx
0x180007b8f  jz      short loc_180007BD2
0x180007b91  bt      ecx, 1Ch
0x180007b95  jnb     short loc_180007B9D
0x180007b97  btr     ecx, 1Ch
0x180007b9b  jmp     short loc_180007BE9
0x180007b9d  mov     eax, ecx
0x180007b9f  and     eax, 1FFF0000h
0x180007ba4  cmp     eax, 70000h
0x180007ba9  jnz     short loc_180007BBC
0x180007bab  movzx   ecx, cx
0x180007bae  mov     eax, ecx
0x180007bb0  or      eax, 0C0070000h
0x180007bb5  test    ecx, ecx
0x180007bb7  cmovnz  ecx, eax
0x180007bba  jmp     short loc_180007BE9
0x180007bbc  cmp     eax, 90000h
0x180007bc1  jnz     short loc_180007BDD
0x180007bc3  test    ecx, ecx
0x180007bc5  jle     short loc_180007BE9
0x180007bc7  movzx   ecx, cx
0x180007bca  or      ecx, 0C0090000h
0x180007bd0  jmp     short loc_180007BE9
0x180007bd2  xor     ecx, ecx
0x180007bd4  jmp     short loc_180007BE9
0x180007bd6  mov     ecx, 0C000A083h
0x180007bdb  jmp     short loc_180007BE9
0x180007bdd  mov     ecx, 0C00000E5h
0x180007be2  jmp     short loc_180007BE9
0x180007be4  mov     ecx, 0C000042Bh
0x180007be9  mov     eax, ecx
0x180007beb  retn
```
