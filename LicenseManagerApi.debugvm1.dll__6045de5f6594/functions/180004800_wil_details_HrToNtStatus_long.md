# wil::details::HrToNtStatus(long)

- ea: `0x180004800`
- end: `0x1800049bc`
- name: `?HrToNtStatus@details@wil@@YAJJ@Z`
- size: `444`
- prototype: `__int64 __fastcall(wil::details *__hidden this, int)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b18`
- `0x180002bd0`
- `0x180002c20`
- `0x180002ce4`
- `0x180003de8`
- `0x1800049c4`
- `0x180005120`
- `0x1800064bc`
- `0x1800065e8`
- `0x180011f72`
- `0x180011fdd`
- `0x1800120a6`
- `0x180012111`

## callees

- `0x180004800`

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
0x180004800  mov     eax, 800700EAh
0x180004805  cmp     ecx, eax
0x180004807  jg      loc_1800048DC
0x18000480d  jz      loc_1800048D2
0x180004813  mov     eax, 80070057h
0x180004818  cmp     ecx, eax
0x18000481a  jg      short loc_180004886
0x18000481c  jz      short loc_18000487C
0x18000481e  cmp     ecx, 80004005h
0x180004824  jz      short loc_180004872
0x180004826  cmp     ecx, 80070001h
0x18000482c  jz      short loc_180004868
0x18000482e  cmp     ecx, 80070002h
0x180004834  jz      short loc_18000485E
0x180004836  cmp     ecx, 80070003h
0x18000483c  jz      short loc_180004854
0x18000483e  cmp     ecx, 8007000Eh
0x180004844  jnz     loc_180004961
0x18000484a  mov     ecx, 0C0000017h
0x18000484f  jmp     loc_1800049B9
0x180004854  mov     ecx, 0C000003Ah
0x180004859  jmp     loc_1800049B9
0x18000485e  mov     ecx, 0C0000034h
0x180004863  jmp     loc_1800049B9
0x180004868  mov     ecx, 0C0000002h
0x18000486d  jmp     loc_1800049B9
0x180004872  mov     ecx, 0C0000001h
0x180004877  jmp     loc_1800049B9
0x18000487c  mov     ecx, 0C000000Dh
0x180004881  jmp     loc_1800049B9
0x180004886  cmp     ecx, 80070070h
0x18000488c  jz      short loc_1800048C8
0x18000488e  cmp     ecx, 8007007Ah
0x180004894  jz      short loc_1800048BE
0x180004896  cmp     ecx, 8007007Bh
0x18000489c  jz      short loc_1800048B4
0x18000489e  cmp     ecx, 8007007Eh
0x1800048a4  jnz     loc_180004961
0x1800048aa  mov     ecx, 0C0000135h
0x1800048af  jmp     loc_1800049B9
0x1800048b4  mov     ecx, 0C0000033h
0x1800048b9  jmp     loc_1800049B9
0x1800048be  mov     ecx, 0C0000023h
0x1800048c3  jmp     loc_1800049B9
0x1800048c8  mov     ecx, 0C000007Fh
0x1800048cd  jmp     loc_1800049B9
0x1800048d2  mov     ecx, 80000005h
0x1800048d7  jmp     loc_1800049B9
0x1800048dc  mov     eax, 8007047Eh
0x1800048e1  cmp     ecx, eax
0x1800048e3  jg      short loc_180004945
0x1800048e5  jz      short loc_18000493E
0x1800048e7  cmp     ecx, 80070216h
0x1800048ed  jz      short loc_180004937
0x1800048ef  cmp     ecx, 8007023Eh
0x1800048f5  jz      short loc_18000492D
0x1800048f7  cmp     ecx, 80070246h
0x1800048fd  jz      short loc_180004923
0x1800048ff  cmp     ecx, 80070247h
0x180004905  jz      short loc_180004919
0x180004907  cmp     ecx, 80070272h
0x18000490d  jnz     short loc_180004961
0x18000490f  mov     ecx, 0C0000273h
0x180004914  jmp     loc_1800049B9
0x180004919  mov     ecx, 0C0000163h
0x18000491e  jmp     loc_1800049B9
0x180004923  mov     ecx, 0C0000161h
0x180004928  jmp     loc_1800049B9
0x18000492d  mov     ecx, 0C0000025h
0x180004932  jmp     loc_1800049B9
0x180004937  mov     ecx, 0C0000095h
0x18000493c  jmp     short loc_1800049B9
0x18000493e  mov     ecx, 0C0000059h
0x180004943  jmp     short loc_1800049B9
0x180004945  cmp     ecx, 8007050Ch
0x18000494b  jz      short loc_1800049B4
0x18000494d  cmp     ecx, 8007054Fh
0x180004953  jz      short loc_1800049AD
0x180004955  cmp     ecx, 800705B9h
0x18000495b  jz      short loc_1800049A6
0x18000495d  test    ecx, ecx
0x18000495f  jz      short loc_1800049A2
0x180004961  bt      ecx, 1Ch
0x180004965  jnb     short loc_18000496D
0x180004967  btr     ecx, 1Ch
0x18000496b  jmp     short loc_1800049B9
0x18000496d  mov     eax, ecx
0x18000496f  and     eax, 1FFF0000h
0x180004974  cmp     eax, 70000h
0x180004979  jnz     short loc_18000498C
0x18000497b  movzx   ecx, cx
0x18000497e  mov     eax, ecx
0x180004980  or      eax, 0C0070000h
0x180004985  test    ecx, ecx
0x180004987  cmovnz  ecx, eax
0x18000498a  jmp     short loc_1800049B9
0x18000498c  cmp     eax, 90000h
0x180004991  jnz     short loc_1800049AD
0x180004993  test    ecx, ecx
0x180004995  jle     short loc_1800049B9
0x180004997  movzx   ecx, cx
0x18000499a  or      ecx, 0C0090000h
0x1800049a0  jmp     short loc_1800049B9
0x1800049a2  xor     ecx, ecx
0x1800049a4  jmp     short loc_1800049B9
0x1800049a6  mov     ecx, 0C000A083h
0x1800049ab  jmp     short loc_1800049B9
0x1800049ad  mov     ecx, 0C00000E5h
0x1800049b2  jmp     short loc_1800049B9
0x1800049b4  mov     ecx, 0C000042Bh
0x1800049b9  mov     eax, ecx
0x1800049bb  retn
```
