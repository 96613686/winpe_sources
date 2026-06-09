# pre_c_init

- ea: `0x1400016b0`
- end: `0x140001787`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400016b0`
- `0x140001c84`
- `0x140001ce0`

## import_xrefs

- `msvcrt!_commode` at `0x140001756`
- `msvcrt!_fmode` at `0x14000174d`
- `msvcrt!__setusermatherr` at `0x14000177a`
- `msvcrt!__setusermatherr` at `0x14000177a`
- `msvcrt!__set_app_type` at `0x14000172f`
- `msvcrt!__set_app_type` at `0x14000172f`

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
  dword_140017268 = v0;
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
0x1400016b0  sub     rsp, 28h
0x1400016b4  mov     eax, 5A4Dh
0x1400016b9  cmp     word ptr cs:__ImageBase.unused, ax
0x1400016c0  jz      short loc_1400016C6
0x1400016c2  xor     eax, eax
0x1400016c4  jmp     short loc_14000171D
0x1400016c6  movsxd  rcx, cs:off_14000003C
0x1400016cd  lea     rdx, __ImageBase
0x1400016d4  cmp     dword ptr [rcx+rdx], 4550h
0x1400016db  jnz     short loc_1400016C2
0x1400016dd  mov     eax, 10Bh
0x1400016e2  cmp     [rcx+rdx+18h], ax
0x1400016e7  jz      short loc_14000170A
0x1400016e9  mov     eax, 20Bh
0x1400016ee  cmp     [rcx+rdx+18h], ax
0x1400016f3  jnz     short loc_1400016C2
0x1400016f5  xor     eax, eax
0x1400016f7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x1400016ff  jbe     short loc_14000171D
0x140001701  cmp     [rcx+rdx+0F8h], eax
0x140001708  jmp     short loc_14000171A
0x14000170a  xor     eax, eax
0x14000170c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001711  jbe     short loc_14000171D
0x140001713  cmp     [rcx+rdx+0E8h], eax
0x14000171a  setnz   al
0x14000171d  mov     ecx, 2
0x140001722  mov     cs:dword_140017268, eax
0x140001728  call    _get_image_app_type
0x14000172d  mov     ecx, eax; Type
0x14000172f  call    cs:__imp___set_app_type
0x140001735  mov     ecx, cs:_fmode
0x14000173b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000173f  mov     cs:__onexitend, rax
0x140001746  mov     cs:__onexitbegin, rax
0x14000174d  mov     rax, cs:__imp__fmode
0x140001754  mov     [rax], ecx
0x140001756  mov     rcx, cs:__imp__commode; Except
0x14000175d  mov     eax, cs:_commode
0x140001763  mov     [rcx], eax
0x140001765  call    _matherr
0x14000176a  cmp     cs:__defaultmatherr, 0
0x140001771  jnz     short loc_140001780
0x140001773  lea     rcx, _matherr; UserMathErrorFunction
0x14000177a  call    cs:__imp___setusermatherr
0x140001780  xor     eax, eax
0x140001782  add     rsp, 28h
0x140001786  retn
```
