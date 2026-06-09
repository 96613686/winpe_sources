# pre_c_init

- ea: `0x140001f30`
- end: `0x140002007`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001f30`
- `0x140002a44`
- `0x140002aa0`

## import_xrefs

- `msvcrt!_commode` at `0x140001fd6`
- `msvcrt!_fmode` at `0x140001fcd`
- `msvcrt!__setusermatherr` at `0x140001ffa`
- `msvcrt!__setusermatherr` at `0x140001ffa`
- `msvcrt!__set_app_type` at `0x140001faf`
- `msvcrt!__set_app_type` at `0x140001faf`

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
  dword_1400A6DB0 = v0;
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
0x140001f30  sub     rsp, 28h
0x140001f34  mov     eax, 5A4Dh
0x140001f39  cmp     word ptr cs:__ImageBase.unused, ax
0x140001f40  jz      short loc_140001F46
0x140001f42  xor     eax, eax
0x140001f44  jmp     short loc_140001F9D
0x140001f46  movsxd  rcx, cs:off_14000003C
0x140001f4d  lea     rdx, __ImageBase
0x140001f54  cmp     dword ptr [rcx+rdx], 4550h
0x140001f5b  jnz     short loc_140001F42
0x140001f5d  mov     eax, 10Bh
0x140001f62  cmp     [rcx+rdx+18h], ax
0x140001f67  jz      short loc_140001F8A
0x140001f69  mov     eax, 20Bh
0x140001f6e  cmp     [rcx+rdx+18h], ax
0x140001f73  jnz     short loc_140001F42
0x140001f75  xor     eax, eax
0x140001f77  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001f7f  jbe     short loc_140001F9D
0x140001f81  cmp     [rcx+rdx+0F8h], eax
0x140001f88  jmp     short loc_140001F9A
0x140001f8a  xor     eax, eax
0x140001f8c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001f91  jbe     short loc_140001F9D
0x140001f93  cmp     [rcx+rdx+0E8h], eax
0x140001f9a  setnz   al
0x140001f9d  mov     ecx, 2
0x140001fa2  mov     cs:dword_1400A6DB0, eax
0x140001fa8  call    _get_image_app_type
0x140001fad  mov     ecx, eax; Type
0x140001faf  call    cs:__imp___set_app_type
0x140001fb5  mov     ecx, cs:_fmode
0x140001fbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001fbf  mov     cs:__onexitend, rax
0x140001fc6  mov     cs:__onexitbegin, rax
0x140001fcd  mov     rax, cs:__imp__fmode
0x140001fd4  mov     [rax], ecx
0x140001fd6  mov     rcx, cs:__imp__commode; Except
0x140001fdd  mov     eax, cs:_commode
0x140001fe3  mov     [rcx], eax
0x140001fe5  call    _matherr
0x140001fea  cmp     cs:__defaultmatherr, 0
0x140001ff1  jnz     short loc_140002000
0x140001ff3  lea     rcx, _matherr; UserMathErrorFunction
0x140001ffa  call    cs:__imp___setusermatherr
0x140002000  xor     eax, eax
0x140002002  add     rsp, 28h
0x140002006  retn
```
