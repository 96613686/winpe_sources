# pre_c_init

- ea: `0x140001ca0`
- end: `0x140001d77`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001ca0`
- `0x140002304`
- `0x140007f30`

## import_xrefs

- `msvcrt!_commode` at `0x140001d46`
- `msvcrt!_fmode` at `0x140001d3d`
- `msvcrt!__setusermatherr` at `0x140001d6a`
- `msvcrt!__setusermatherr` at `0x140001d6a`
- `msvcrt!__set_app_type` at `0x140001d1f`
- `msvcrt!__set_app_type` at `0x140001d1f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( LOWORD(MEMORY[0x140000000].unused) != 23117 || *(_DWORD *)(MEMORY[0x14000003C] + 0x140000000LL) != 17744 )
    goto LABEL_2;
  if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) != 267 )
  {
    if ( *(_WORD *)(MEMORY[0x14000003C] + 0x140000018LL) == 523 )
    {
      v0 = 0;
      if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000084LL) <= 0xEu )
        goto LABEL_11;
      v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000F8LL) == 0;
      goto LABEL_10;
    }
LABEL_2:
    v0 = 0;
    goto LABEL_11;
  }
  v0 = 0;
  if ( *(_DWORD *)(MEMORY[0x14000003C] + 0x140000074LL) <= 0xEu )
    goto LABEL_11;
  v1 = *(_DWORD *)(MEMORY[0x14000003C] + 0x1400000E8LL) == 0;
LABEL_10:
  LOBYTE(v0) = !v1;
LABEL_11:
  dword_1400112D0 = v0;
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
0x140001ca0  sub     rsp, 28h
0x140001ca4  mov     eax, 5A4Dh
0x140001ca9  cmp     cs:140000000h, ax
0x140001cb0  jz      short loc_140001CB6
0x140001cb2  xor     eax, eax
0x140001cb4  jmp     short loc_140001D0D
0x140001cb6  movsxd  rcx, dword ptr cs:14000003Ch
0x140001cbd  lea     rdx, cs:140000000h
0x140001cc4  cmp     dword ptr [rcx+rdx], 4550h
0x140001ccb  jnz     short loc_140001CB2
0x140001ccd  mov     eax, 10Bh
0x140001cd2  cmp     [rcx+rdx+18h], ax
0x140001cd7  jz      short loc_140001CFA
0x140001cd9  mov     eax, 20Bh
0x140001cde  cmp     [rcx+rdx+18h], ax
0x140001ce3  jnz     short loc_140001CB2
0x140001ce5  xor     eax, eax
0x140001ce7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001cef  jbe     short loc_140001D0D
0x140001cf1  cmp     [rcx+rdx+0F8h], eax
0x140001cf8  jmp     short loc_140001D0A
0x140001cfa  xor     eax, eax
0x140001cfc  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001d01  jbe     short loc_140001D0D
0x140001d03  cmp     [rcx+rdx+0E8h], eax
0x140001d0a  setnz   al
0x140001d0d  mov     ecx, 2
0x140001d12  mov     cs:dword_1400112D0, eax
0x140001d18  call    _get_image_app_type
0x140001d1d  mov     ecx, eax; Type
0x140001d1f  call    cs:__imp___set_app_type
0x140001d25  mov     ecx, cs:_fmode
0x140001d2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001d2f  mov     cs:__onexitend, rax
0x140001d36  mov     cs:__onexitbegin, rax
0x140001d3d  mov     rax, cs:__imp__fmode
0x140001d44  mov     [rax], ecx
0x140001d46  mov     rcx, cs:__imp__commode; Except
0x140001d4d  mov     eax, cs:_commode
0x140001d53  mov     [rcx], eax
0x140001d55  call    _matherr
0x140001d5a  cmp     cs:__defaultmatherr, 0
0x140001d61  jnz     short loc_140001D70
0x140001d63  lea     rcx, _matherr; UserMathErrorFunction
0x140001d6a  call    cs:__imp___setusermatherr
0x140001d70  xor     eax, eax
0x140001d72  add     rsp, 28h
0x140001d76  retn
```
