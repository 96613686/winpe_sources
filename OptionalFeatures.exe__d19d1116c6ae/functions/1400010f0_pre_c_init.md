# pre_c_init

- ea: `0x1400010f0`
- end: `0x1400011c7`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400010f0`
- `0x140001644`
- `0x1400016a0`

## import_xrefs

- `msvcrt!_commode` at `0x140001196`
- `msvcrt!_fmode` at `0x14000118d`
- `msvcrt!__setusermatherr` at `0x1400011ba`
- `msvcrt!__setusermatherr` at `0x1400011ba`
- `msvcrt!__set_app_type` at `0x14000116f`
- `msvcrt!__set_app_type` at `0x14000116f`

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
  dword_140008160 = v0;
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
0x1400010f0  sub     rsp, 28h
0x1400010f4  mov     eax, 5A4Dh
0x1400010f9  cmp     cs:140000000h, ax
0x140001100  jz      short loc_140001106
0x140001102  xor     eax, eax
0x140001104  jmp     short loc_14000115D
0x140001106  movsxd  rcx, dword ptr cs:14000003Ch
0x14000110d  lea     rdx, cs:140000000h
0x140001114  cmp     dword ptr [rcx+rdx], 4550h
0x14000111b  jnz     short loc_140001102
0x14000111d  mov     eax, 10Bh
0x140001122  cmp     [rcx+rdx+18h], ax
0x140001127  jz      short loc_14000114A
0x140001129  mov     eax, 20Bh
0x14000112e  cmp     [rcx+rdx+18h], ax
0x140001133  jnz     short loc_140001102
0x140001135  xor     eax, eax
0x140001137  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x14000113f  jbe     short loc_14000115D
0x140001141  cmp     [rcx+rdx+0F8h], eax
0x140001148  jmp     short loc_14000115A
0x14000114a  xor     eax, eax
0x14000114c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001151  jbe     short loc_14000115D
0x140001153  cmp     [rcx+rdx+0E8h], eax
0x14000115a  setnz   al
0x14000115d  mov     ecx, 2
0x140001162  mov     cs:dword_140008160, eax
0x140001168  call    _get_image_app_type
0x14000116d  mov     ecx, eax; Type
0x14000116f  call    cs:__imp___set_app_type
0x140001175  mov     ecx, cs:_fmode
0x14000117b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000117f  mov     cs:__onexitend, rax
0x140001186  mov     cs:__onexitbegin, rax
0x14000118d  mov     rax, cs:__imp__fmode
0x140001194  mov     [rax], ecx
0x140001196  mov     rcx, cs:__imp__commode; Except
0x14000119d  mov     eax, cs:_commode
0x1400011a3  mov     [rcx], eax
0x1400011a5  call    _matherr
0x1400011aa  cmp     cs:__defaultmatherr, 0
0x1400011b1  jnz     short loc_1400011C0
0x1400011b3  lea     rcx, _matherr; UserMathErrorFunction
0x1400011ba  call    cs:__imp___setusermatherr
0x1400011c0  xor     eax, eax
0x1400011c2  add     rsp, 28h
0x1400011c6  retn
```
