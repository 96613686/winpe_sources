# pre_c_init

- ea: `0x140001f10`
- end: `0x140001fe7`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001f10`
- `0x140002a24`
- `0x1400598d0`

## import_xrefs

- `msvcrt!_commode` at `0x140001fb6`
- `msvcrt!_fmode` at `0x140001fad`
- `msvcrt!__setusermatherr` at `0x140001fda`
- `msvcrt!__setusermatherr` at `0x140001fda`
- `msvcrt!__set_app_type` at `0x140001f8f`
- `msvcrt!__set_app_type` at `0x140001f8f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( LOWORD(_ImageBase.unused) != 23117 || *(int *)((char *)&_ImageBase.unused + (int)off_14000003C) != 17744 )
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
  dword_1400A0DB0 = v0;
  image_app_type = (unsigned int)get_image_app_type(2);
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
0x140001f10  sub     rsp, 28h
0x140001f14  mov     eax, 5A4Dh
0x140001f19  cmp     word ptr cs:__ImageBase.unused, ax
0x140001f20  jz      short loc_140001F26
0x140001f22  xor     eax, eax
0x140001f24  jmp     short loc_140001F7D
0x140001f26  movsxd  rcx, cs:off_14000003C
0x140001f2d  lea     rdx, __ImageBase
0x140001f34  cmp     dword ptr [rcx+rdx], 4550h
0x140001f3b  jnz     short loc_140001F22
0x140001f3d  mov     eax, 10Bh
0x140001f42  cmp     [rcx+rdx+18h], ax
0x140001f47  jz      short loc_140001F6A
0x140001f49  mov     eax, 20Bh
0x140001f4e  cmp     [rcx+rdx+18h], ax
0x140001f53  jnz     short loc_140001F22
0x140001f55  xor     eax, eax
0x140001f57  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001f5f  jbe     short loc_140001F7D
0x140001f61  cmp     [rcx+rdx+0F8h], eax
0x140001f68  jmp     short loc_140001F7A
0x140001f6a  xor     eax, eax
0x140001f6c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001f71  jbe     short loc_140001F7D
0x140001f73  cmp     [rcx+rdx+0E8h], eax
0x140001f7a  setnz   al
0x140001f7d  mov     ecx, 2
0x140001f82  mov     cs:dword_1400A0DB0, eax
0x140001f88  call    _get_image_app_type
0x140001f8d  mov     ecx, eax; Type
0x140001f8f  call    cs:__imp___set_app_type
0x140001f95  mov     ecx, cs:_fmode
0x140001f9b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001f9f  mov     cs:__onexitend, rax
0x140001fa6  mov     cs:__onexitbegin, rax
0x140001fad  mov     rax, cs:__imp__fmode
0x140001fb4  mov     [rax], ecx
0x140001fb6  mov     rcx, cs:__imp__commode; Except
0x140001fbd  mov     eax, cs:_commode
0x140001fc3  mov     [rcx], eax
0x140001fc5  call    _matherr
0x140001fca  cmp     cs:__defaultmatherr, 0
0x140001fd1  jnz     short loc_140001FE0
0x140001fd3  lea     rcx, _matherr; UserMathErrorFunction
0x140001fda  call    cs:__imp___setusermatherr
0x140001fe0  xor     eax, eax
0x140001fe2  add     rsp, 28h
0x140001fe6  retn
```
