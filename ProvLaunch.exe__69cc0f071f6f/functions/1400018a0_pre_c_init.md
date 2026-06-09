# pre_c_init

- ea: `0x1400018a0`
- end: `0x140001977`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400018a0`
- `0x140001db4`
- `0x140001e10`

## import_xrefs

- `msvcrt!_commode` at `0x140001946`
- `msvcrt!_fmode` at `0x14000193d`
- `msvcrt!__setusermatherr` at `0x14000196a`
- `msvcrt!__setusermatherr` at `0x14000196a`
- `msvcrt!__set_app_type` at `0x14000191f`
- `msvcrt!__set_app_type` at `0x14000191f`

## pseudocode

```c
// write access to const memory has been detected, the output may be wrong!
__int64 pre_c_init()
{
  int v0; // eax
  bool v1; // zf
  _crt_app_type image_app_type; // eax

  if ( MEMORY[0x140000000] != 23117 || *(_DWORD *)(MEMORY[0x14000003C] + 0x140000000LL) != 17744 )
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
  dword_1400102A8 = v0;
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
0x1400018a0  sub     rsp, 28h
0x1400018a4  mov     eax, 5A4Dh
0x1400018a9  cmp     cs:140000000h, ax
0x1400018b0  jz      short loc_1400018B6
0x1400018b2  xor     eax, eax
0x1400018b4  jmp     short loc_14000190D
0x1400018b6  movsxd  rcx, dword ptr cs:14000003Ch
0x1400018bd  lea     rdx, cs:140000000h
0x1400018c4  cmp     dword ptr [rcx+rdx], 4550h
0x1400018cb  jnz     short loc_1400018B2
0x1400018cd  mov     eax, 10Bh
0x1400018d2  cmp     [rcx+rdx+18h], ax
0x1400018d7  jz      short loc_1400018FA
0x1400018d9  mov     eax, 20Bh
0x1400018de  cmp     [rcx+rdx+18h], ax
0x1400018e3  jnz     short loc_1400018B2
0x1400018e5  xor     eax, eax
0x1400018e7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x1400018ef  jbe     short loc_14000190D
0x1400018f1  cmp     [rcx+rdx+0F8h], eax
0x1400018f8  jmp     short loc_14000190A
0x1400018fa  xor     eax, eax
0x1400018fc  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001901  jbe     short loc_14000190D
0x140001903  cmp     [rcx+rdx+0E8h], eax
0x14000190a  setnz   al
0x14000190d  mov     ecx, 1
0x140001912  mov     cs:dword_1400102A8, eax
0x140001918  call    _get_image_app_type
0x14000191d  mov     ecx, eax; Type
0x14000191f  call    cs:__imp___set_app_type
0x140001925  mov     ecx, cs:_fmode
0x14000192b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000192f  mov     cs:__onexitend, rax
0x140001936  mov     cs:__onexitbegin, rax
0x14000193d  mov     rax, cs:__imp__fmode
0x140001944  mov     [rax], ecx
0x140001946  mov     rcx, cs:__imp__commode; Except
0x14000194d  mov     eax, cs:_commode
0x140001953  mov     [rcx], eax
0x140001955  call    _matherr
0x14000195a  cmp     cs:__defaultmatherr, 0
0x140001961  jnz     short loc_140001970
0x140001963  lea     rcx, _matherr; UserMathErrorFunction
0x14000196a  call    cs:__imp___setusermatherr
0x140001970  xor     eax, eax
0x140001972  add     rsp, 28h
0x140001976  retn
```
