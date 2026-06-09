# pre_c_init

- ea: `0x1400010b0`
- end: `0x140001187`
- name: `pre_c_init`
- size: `215`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400010b0`
- `0x140001634`
- `0x140001690`

## import_xrefs

- `msvcrt!_commode` at `0x140001156`
- `msvcrt!_fmode` at `0x14000114d`
- `msvcrt!__setusermatherr` at `0x14000117a`
- `msvcrt!__setusermatherr` at `0x14000117a`
- `msvcrt!__set_app_type` at `0x14000112f`
- `msvcrt!__set_app_type` at `0x14000112f`

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
  dword_14000B200 = v0;
  image_app_type = (unsigned int)get_image_app_type(2u);
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
0x1400010b0  sub     rsp, 28h
0x1400010b4  mov     eax, 5A4Dh
0x1400010b9  cmp     word ptr cs:__ImageBase.unused, ax
0x1400010c0  jz      short loc_1400010C6
0x1400010c2  xor     eax, eax
0x1400010c4  jmp     short loc_14000111D
0x1400010c6  movsxd  rcx, cs:off_14000003C
0x1400010cd  lea     rdx, __ImageBase
0x1400010d4  cmp     dword ptr [rcx+rdx], 4550h
0x1400010db  jnz     short loc_1400010C2
0x1400010dd  mov     eax, 10Bh
0x1400010e2  cmp     [rcx+rdx+18h], ax
0x1400010e7  jz      short loc_14000110A
0x1400010e9  mov     eax, 20Bh
0x1400010ee  cmp     [rcx+rdx+18h], ax
0x1400010f3  jnz     short loc_1400010C2
0x1400010f5  xor     eax, eax
0x1400010f7  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x1400010ff  jbe     short loc_14000111D
0x140001101  cmp     [rcx+rdx+0F8h], eax
0x140001108  jmp     short loc_14000111A
0x14000110a  xor     eax, eax
0x14000110c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001111  jbe     short loc_14000111D
0x140001113  cmp     [rcx+rdx+0E8h], eax
0x14000111a  setnz   al
0x14000111d  mov     ecx, 2
0x140001122  mov     cs:dword_14000B200, eax
0x140001128  call    _get_image_app_type
0x14000112d  mov     ecx, eax; Type
0x14000112f  call    cs:__imp___set_app_type
0x140001135  mov     ecx, cs:_fmode
0x14000113b  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000113f  mov     cs:__onexitend, rax
0x140001146  mov     cs:__onexitbegin, rax
0x14000114d  mov     rax, cs:__imp__fmode
0x140001154  mov     [rax], ecx
0x140001156  mov     rcx, cs:__imp__commode; Except
0x14000115d  mov     eax, cs:_commode
0x140001163  mov     [rcx], eax
0x140001165  call    _matherr
0x14000116a  cmp     cs:__defaultmatherr, 0
0x140001171  jnz     short loc_140001180
0x140001173  lea     rcx, _matherr; UserMathErrorFunction
0x14000117a  call    cs:__imp___setusermatherr
0x140001180  xor     eax, eax
0x140001182  add     rsp, 28h
0x140001186  retn
```
