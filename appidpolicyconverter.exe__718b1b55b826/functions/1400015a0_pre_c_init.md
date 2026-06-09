# pre_c_init

- ea: `0x1400015a0`
- end: `0x140001677`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400015a0`
- `0x140001df4`
- `0x140001e50`

## import_xrefs

- `msvcrt!__set_app_type` at `0x14000161f`
- `msvcrt!__set_app_type` at `0x14000161f`
- `msvcrt!__setusermatherr` at `0x14000166a`
- `msvcrt!__setusermatherr` at `0x14000166a`
- `msvcrt!_fmode` at `0x14000163d`
- `msvcrt!_commode` at `0x140001646`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( _ImageBase != 23117 || *(_DWORD *)((char *)&_ImageBase + (int)off_14000003C) != 17744 )
    goto LABEL_2;
  if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) != 267 )
  {
    if ( *(__int16 *)((char *)&word_140000018 + (int)off_14000003C) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 68] <= 0xEu )
        goto LABEL_11;
      v1 = *(int *)((char *)&dword_1400000F8 + (int)off_14000003C) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)&byte_140000040[(int)off_14000003C + 52] <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)&byte_140000040[(int)off_14000003C + 168] == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_140020960 = v0;
  image_app_type = (unsigned int)get_image_app_type(1);
  __set_app_type(image_app_type);
  _onexitend = -1;
  _onexitbegin = -1;
  _fmode = fmode;
  _commode = commode;
  matherr(*(struct _exception **)&_commode);
  if ( !_defaultmatherr )
    __setusermatherr(matherr);
  return 0;
}

```

## disassembly

```asm
0x1400015a0  sub     rsp, 28h
0x1400015a4  mov     eax, 5A4Dh
0x1400015a9  cmp     cs:__ImageBase, ax
0x1400015b0  jz      short loc_1400015B6
0x1400015b2  xor     eax, eax
0x1400015b4  jmp     short loc_14000160D
0x1400015b6  movsxd  rcx, cs:off_14000003C
0x1400015bd  lea     rdx, __ImageBase
0x1400015c4  cmp     dword ptr [rcx+rdx], 4550h
0x1400015cb  jnz     short loc_1400015B2
0x1400015cd  mov     eax, 10Bh
0x1400015d2  cmp     [rcx+rdx+18h], ax
0x1400015d7  jz      short loc_1400015FA
0x1400015d9  mov     eax, 20Bh
0x1400015de  cmp     [rcx+rdx+18h], ax
0x1400015e3  jnz     short loc_1400015B2
0x1400015e5  xor     eax, eax
0x1400015e7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x1400015ef  jbe     short loc_14000160D
0x1400015f1  cmp     [rcx+rdx+0F8h], eax
0x1400015f8  jmp     short loc_14000160A
0x1400015fa  xor     eax, eax
0x1400015fc  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001601  jbe     short loc_14000160D
0x140001603  cmp     [rcx+rdx+0E8h], eax
0x14000160a  setnz   al
0x14000160d  mov     ecx, 1
0x140001612  mov     cs:dword_140020960, eax
0x140001618  call    _get_image_app_type
0x14000161d  mov     ecx, eax; Type
0x14000161f  call    cs:__imp___set_app_type
0x140001625  mov     ecx, cs:_fmode
0x14000162b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000162f  mov     cs:__onexitend, rax
0x140001636  mov     cs:__onexitbegin, rax
0x14000163d  mov     rax, cs:__imp__fmode
0x140001644  mov     [rax], ecx
0x140001646  mov     rcx, cs:__imp__commode; Except
0x14000164d  mov     eax, cs:_commode
0x140001653  mov     [rcx], eax
0x140001655  call    _matherr
0x14000165a  cmp     cs:__defaultmatherr, 0
0x140001661  jnz     short loc_140001670
0x140001663  lea     rcx, _matherr; UserMathErrorFunction
0x14000166a  call    cs:__imp___setusermatherr
0x140001670  xor     eax, eax
0x140001672  add     rsp, 28h
0x140001676  retn
```
