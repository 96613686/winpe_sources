# pre_c_init

- ea: `0x140001be0`
- end: `0x140001cb7`
- name: `pre_c_init`
- size: `215`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001be0`
- `0x140002104`
- `0x140002160`

## import_xrefs

- `msvcrt!_commode` at `0x140001c86`
- `msvcrt!_fmode` at `0x140001c7d`
- `msvcrt!__setusermatherr` at `0x140001caa`
- `msvcrt!__setusermatherr` at `0x140001caa`
- `msvcrt!__set_app_type` at `0x140001c5f`
- `msvcrt!__set_app_type` at `0x140001c5f`

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
  dword_14002B2A8 = v0;
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
0x140001be0  sub     rsp, 28h
0x140001be4  mov     eax, 5A4Dh
0x140001be9  cmp     cs:__ImageBase, ax
0x140001bf0  jz      short loc_140001BF6
0x140001bf2  xor     eax, eax
0x140001bf4  jmp     short loc_140001C4D
0x140001bf6  movsxd  rcx, cs:off_14000003C
0x140001bfd  lea     rdx, __ImageBase
0x140001c04  cmp     dword ptr [rcx+rdx], 4550h
0x140001c0b  jnz     short loc_140001BF2
0x140001c0d  mov     eax, 10Bh
0x140001c12  cmp     [rcx+rdx+18h], ax
0x140001c17  jz      short loc_140001C3A
0x140001c19  mov     eax, 20Bh
0x140001c1e  cmp     [rcx+rdx+18h], ax
0x140001c23  jnz     short loc_140001BF2
0x140001c25  xor     eax, eax
0x140001c27  cmp     dword ptr [rcx+rdx+84h], 0Eh
0x140001c2f  jbe     short loc_140001C4D
0x140001c31  cmp     [rcx+rdx+0F8h], eax
0x140001c38  jmp     short loc_140001C4A
0x140001c3a  xor     eax, eax
0x140001c3c  cmp     dword ptr [rcx+rdx+74h], 0Eh
0x140001c41  jbe     short loc_140001C4D
0x140001c43  cmp     [rcx+rdx+0E8h], eax
0x140001c4a  setnz   al
0x140001c4d  mov     ecx, 1
0x140001c52  mov     cs:dword_14002B2A8, eax
0x140001c58  call    _get_image_app_type
0x140001c5d  mov     ecx, eax; Type
0x140001c5f  call    cs:__imp___set_app_type
0x140001c65  mov     ecx, cs:_fmode
0x140001c6b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140001c6f  mov     cs:__onexitend, rax
0x140001c76  mov     cs:__onexitbegin, rax
0x140001c7d  mov     rax, cs:__imp__fmode
0x140001c84  mov     [rax], ecx
0x140001c86  mov     rcx, cs:__imp__commode; Except
0x140001c8d  mov     eax, cs:_commode
0x140001c93  mov     [rcx], eax
0x140001c95  call    _matherr
0x140001c9a  cmp     cs:__defaultmatherr, 0
0x140001ca1  jnz     short loc_140001CB0
0x140001ca3  lea     rcx, _matherr; UserMathErrorFunction
0x140001caa  call    cs:__imp___setusermatherr
0x140001cb0  xor     eax, eax
0x140001cb2  add     rsp, 28h
0x140001cb6  retn
```
