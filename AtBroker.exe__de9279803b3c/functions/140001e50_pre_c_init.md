# pre_c_init

- ea: `0x140001e50`
- end: `0x140001f27`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001e50`
- `0x140002504`
- `0x140002560`

## import_xrefs

- `msvcrt!_commode` at `0x140001ef6`
- `msvcrt!_fmode` at `0x140001eed`
- `msvcrt!__setusermatherr` at `0x140001f1a`
- `msvcrt!__setusermatherr` at `0x140001f1a`
- `msvcrt!__set_app_type` at `0x140001ecf`
- `msvcrt!__set_app_type` at `0x140001ecf`

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
  dword_140020B20 = v0;
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
0x140001e50  sub     rsp, 28h
0x140001e54  mov     eax, 5A4Dh
0x140001e59  cmp     cs:__ImageBase, ax
0x140001e60  jz      short loc_140001E66
0x140001e62  xor     eax, eax
0x140001e64  jmp     short loc_140001EBD
0x140001e66  movsxd  rcx, cs:off_14000003C
0x140001e6d  lea     rdx, __ImageBase
0x140001e74  cmp     dword ptr [rcx+rdx], 4550h
0x140001e7b  jnz     short loc_140001E62
0x140001e7d  mov     eax, 10Bh
0x140001e82  cmp     [rcx+rdx+18h], ax
0x140001e87  jz      short loc_140001EAA
0x140001e89  mov     eax, 20Bh
0x140001e8e  cmp     [rcx+rdx+18h], ax
0x140001e93  jnz     short loc_140001E62
0x140001e95  xor     eax, eax
0x140001e97  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001e9f  jbe     short loc_140001EBD
0x140001ea1  cmp     [rcx+rdx+0F8h], eax
0x140001ea8  jmp     short loc_140001EBA
0x140001eaa  xor     eax, eax
0x140001eac  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001eb1  jbe     short loc_140001EBD
0x140001eb3  cmp     [rcx+rdx+0E8h], eax
0x140001eba  setnz   al
0x140001ebd  mov     ecx, 1
0x140001ec2  mov     cs:dword_140020B20, eax
0x140001ec8  call    _get_image_app_type
0x140001ecd  mov     ecx, eax; Type
0x140001ecf  call    cs:__imp___set_app_type
0x140001ed5  mov     ecx, cs:_fmode
0x140001edb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001edf  mov     cs:__onexitend, rax
0x140001ee6  mov     cs:__onexitbegin, rax
0x140001eed  mov     rax, cs:__imp__fmode
0x140001ef4  mov     [rax], ecx
0x140001ef6  mov     rcx, cs:__imp__commode; Except
0x140001efd  mov     eax, cs:_commode
0x140001f03  mov     [rcx], eax
0x140001f05  call    _matherr
0x140001f0a  cmp     cs:__defaultmatherr, 0
0x140001f11  jnz     short loc_140001F20
0x140001f13  lea     rcx, _matherr; UserMathErrorFunction
0x140001f1a  call    cs:__imp___setusermatherr
0x140001f20  xor     eax, eax
0x140001f22  add     rsp, 28h
0x140001f26  retn
```
