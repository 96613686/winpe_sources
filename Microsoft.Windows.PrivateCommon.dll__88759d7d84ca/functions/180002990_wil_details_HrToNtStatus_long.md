# wil::details::HrToNtStatus(long)

- ea: `0x180002990`
- end: `0x180002b15`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `389`
- prototype: `__int64 __fastcall(wil::details *this)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025a0`
- `0x1800039a0`
- `0x180004e90`
- `0x180004f10`
- `0x180005190`
- `0x1800051e0`

## callees

- `0x180002990`

## pseudocode

```c
__int64 __fastcall wil::details::HrToNtStatus(wil::details *this)
{
  unsigned int v1; // edx
  __int64 result; // rax
  unsigned int v3; // edx

  v1 = (unsigned int)this;
  if ( (int)this <= -2147024895 )
  {
    if ( (_DWORD)this == -2147024895 )
      return 3221225474LL;
    if ( (_DWORD)this == -2147467259 )
      return 3221225473LL;
    goto LABEL_34;
  }
  if ( (int)this > -2147024362 )
  {
    if ( (int)this > -2147023746 )
    {
      switch ( (_DWORD)this )
      {
        case 0x8007050C:
          return (unsigned int)-1073740757;
        case 0x8007054F:
          return 3221225701LL;
        case 0x800705B9:
          return 3221266563LL;
        case 0:
          return 0;
      }
    }
    else
    {
      switch ( (_DWORD)this )
      {
        case 0x8007047E:
          return 3221225561LL;
        case 0x8007023E:
          return 3221225509LL;
        case 0x80070246:
          return 3221225825LL;
        case 0x80070247:
          return 3221225827LL;
        case 0x80070272:
          return 3221226099LL;
      }
    }
LABEL_34:
    if ( ((unsigned int)this & 0x10000000) != 0 )
      return (unsigned int)this & 0xEFFFFFFF;
    if ( ((unsigned int)this & 0x1FFF0000) == 0x70000 )
    {
      v3 = (unsigned __int16)this;
      if ( (_WORD)this )
        return (unsigned __int16)this | 0xC0070000;
      return v3;
    }
    if ( ((unsigned int)this & 0x1FFF0000) == 0x90000 )
    {
      if ( (int)this > 0 )
        return (unsigned __int16)this | 0xC0090000;
      return v1;
    }
    return 3221225701LL;
  }
  if ( (_DWORD)this == -2147024362 )
    return 3221225621LL;
  switch ( (unsigned int)this )
  {
    case 0x80070002:
      result = 3221225524LL;
      break;
    case 0x80070003:
      result = 3221225530LL;
      break;
    case 0x8007000E:
      result = 3221225495LL;
      break;
    case 0x80070057:
      result = 3221225485LL;
      break;
    case 0x80070070:
      result = 3221225599LL;
      break;
    case 0x8007007A:
      result = 3221225507LL;
      break;
    case 0x8007007B:
      result = 3221225523LL;
      break;
    case 0x8007007E:
      result = 3221225781LL;
      break;
    case 0x800700EA:
      result = 2147483653LL;
      break;
    default:
      goto LABEL_34;
  }
  return result;
}

```

## disassembly

```asm
0x180002990  mov     edx, ecx
0x180002992  cmp     ecx, 80070001h
0x180002998  jg      short loc_1800029B8
0x18000299a  jz      short loc_1800029B0
0x18000299c  cmp     ecx, 80004005h
0x1800029a2  jnz     def_1800029F4; jumptable 00000001800029F4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x1800029a8  mov     edx, 0C0000001h
0x1800029ad  mov     eax, edx
0x1800029af  retn
0x1800029b0  mov     edx, 0C0000002h
0x1800029b5  mov     eax, edx
0x1800029b7  retn
0x1800029b8  cmp     edx, 80070216h
0x1800029be  jg      loc_180002A46
0x1800029c4  jz      short loc_180002A3E
0x1800029c6  lea     eax, [rcx+7FF8FFFEh]; switch 233 cases
0x1800029cc  cmp     eax, 0E8h
0x1800029d1  ja      def_1800029F4; jumptable 00000001800029F4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x1800029d7  lea     r8, cs:180000000h
0x1800029de  cdqe
0x1800029e0  movzx   eax, ds:(byte_180002B40 - 180000000h)[r8+rax]
0x1800029e9  mov     ecx, ds:(jpt_1800029F4 - 180000000h)[r8+rax*4]
0x1800029f1  add     rcx, r8
0x1800029f4  jmp     rcx; switch jump
0x1800029f6  mov     edx, 0C000000Dh; jumptable 00000001800029F4 case -2147024809
0x1800029fb  mov     eax, edx
0x1800029fd  retn
0x1800029fe  mov     edx, 0C0000017h; jumptable 00000001800029F4 case -2147024882
0x180002a03  mov     eax, edx
0x180002a05  retn
0x180002a06  mov     edx, 0C000003Ah; jumptable 00000001800029F4 case -2147024893
0x180002a0b  mov     eax, edx
0x180002a0d  retn
0x180002a0e  mov     edx, 0C0000034h; jumptable 00000001800029F4 case -2147024894
0x180002a13  mov     eax, edx
0x180002a15  retn
0x180002a16  mov     edx, 80000005h; jumptable 00000001800029F4 case -2147024662
0x180002a1b  mov     eax, edx
0x180002a1d  retn
0x180002a1e  mov     edx, 0C0000023h; jumptable 00000001800029F4 case -2147024774
0x180002a23  mov     eax, edx
0x180002a25  retn
0x180002a26  mov     edx, 0C000007Fh; jumptable 00000001800029F4 case -2147024784
0x180002a2b  mov     eax, edx
0x180002a2d  retn
0x180002a2e  mov     edx, 0C0000033h; jumptable 00000001800029F4 case -2147024773
0x180002a33  mov     eax, edx
0x180002a35  retn
0x180002a36  mov     edx, 0C0000135h; jumptable 00000001800029F4 case -2147024770
0x180002a3b  mov     eax, edx
0x180002a3d  retn
0x180002a3e  mov     edx, 0C0000095h
0x180002a43  mov     eax, edx
0x180002a45  retn
0x180002a46  cmp     edx, 8007047Eh
0x180002a4c  jg      short loc_180002A98
0x180002a4e  jz      short loc_180002A90
0x180002a50  cmp     edx, 8007023Eh
0x180002a56  jz      short loc_180002A88
0x180002a58  cmp     edx, 80070246h
0x180002a5e  jz      short loc_180002A80
0x180002a60  cmp     edx, 80070247h
0x180002a66  jz      short loc_180002A78
0x180002a68  cmp     edx, 80070272h
0x180002a6e  jnz     short def_1800029F4; jumptable 00000001800029F4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180002a70  mov     edx, 0C0000273h
0x180002a75  mov     eax, edx
0x180002a77  retn
0x180002a78  mov     edx, 0C0000163h
0x180002a7d  mov     eax, edx
0x180002a7f  retn
0x180002a80  mov     edx, 0C0000161h
0x180002a85  mov     eax, edx
0x180002a87  retn
0x180002a88  mov     edx, 0C0000025h
0x180002a8d  mov     eax, edx
0x180002a8f  retn
0x180002a90  mov     edx, 0C0000059h
0x180002a95  mov     eax, edx
0x180002a97  retn
0x180002a98  cmp     edx, 8007050Ch
0x180002a9e  jz      short loc_180002B0D
0x180002aa0  cmp     edx, 8007054Fh
0x180002aa6  jz      short loc_180002B05
0x180002aa8  cmp     edx, 800705B9h
0x180002aae  jz      short loc_180002AFD
0x180002ab0  test    edx, edx
0x180002ab2  jz      short loc_180002AF8
0x180002ab4  bt      edx, 1Ch; jumptable 00000001800029F4 default case, cases -2147024892--2147024883,-2147024881--2147024810,-2147024808--2147024785,-2147024783--2147024775,-2147024772,-2147024771,-2147024769--2147024663
0x180002ab8  jnb     short loc_180002AC1
0x180002aba  btr     edx, 1Ch
0x180002abe  mov     eax, edx
0x180002ac0  retn
0x180002ac1  mov     eax, edx
0x180002ac3  and     eax, 1FFF0000h
0x180002ac8  cmp     eax, 70000h
0x180002acd  jnz     short loc_180002AE1
0x180002acf  movzx   edx, dx
0x180002ad2  mov     eax, edx
0x180002ad4  or      eax, 0C0070000h
0x180002ad9  test    edx, edx
0x180002adb  cmovnz  edx, eax
0x180002ade  mov     eax, edx
0x180002ae0  retn
0x180002ae1  cmp     eax, 90000h
0x180002ae6  jnz     short loc_180002B05
0x180002ae8  test    edx, edx
0x180002aea  jle     short loc_180002B12
0x180002aec  movzx   edx, dx
0x180002aef  or      edx, 0C0090000h
0x180002af5  mov     eax, edx
0x180002af7  retn
0x180002af8  xor     edx, edx
0x180002afa  mov     eax, edx
0x180002afc  retn
0x180002afd  mov     edx, 0C000A083h
0x180002b02  mov     eax, edx
0x180002b04  retn
0x180002b05  mov     edx, 0C00000E5h
0x180002b0a  mov     eax, edx
0x180002b0c  retn
0x180002b0d  mov     edx, 0C000042Bh
0x180002b12  mov     eax, edx
0x180002b14  retn
```
