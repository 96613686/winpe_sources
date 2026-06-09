# common_tcsncpy_s<wchar_t>(wchar_t * const,uint,wchar_t const * const,uint)

- ea: `0x40fe5a`
- end: `0x40ff25`
- name: `??$common_tcsncpy_s@_W@@YAHQA_WIQB_WI@Z`
- size: `203`
- prototype: `int __cdecl(_WORD *, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x40ff25`

## callees

- `0x40de54`
- `0x40fe5a`
- `0x40ffa9`

## pseudocode

```c
int __cdecl common_tcsncpy_s<wchar_t>(_WORD *a1, int a2, int a3, int a4)
{
  _WORD *v4; // ecx
  int *v5; // eax
  int v7; // ebx
  _WORD *v8; // edx
  int v9; // edi
  __int16 v10; // ax
  int v11; // ecx
  __int16 v12; // ax
  bool v13; // zf
  int v14; // [esp-4h] [ebp-Ch]

  v4 = a1;
  if ( a4 )
  {
    if ( !a1 )
      goto LABEL_4;
  }
  else if ( !a1 )
  {
    if ( a2 )
    {
LABEL_4:
      v5 = _errno();
      v14 = 22;
LABEL_5:
      *v5 = v14;
      _invalid_parameter_noinfo();
      return v14;
    }
    return 0;
  }
  if ( !a2 )
    goto LABEL_4;
  if ( !a4 )
  {
    *a1 = 0;
    return 0;
  }
  if ( !a3 )
  {
    *a1 = 0;
    goto LABEL_4;
  }
  v7 = a3 - (_DWORD)a1;
  v8 = a1;
  v9 = a2;
  if ( a4 == -1 )
  {
    do
    {
      v10 = *(_WORD *)((char *)v8 + v7);
      *v8++ = v10;
      if ( !v10 )
        break;
      --v9;
    }
    while ( v9 );
  }
  else
  {
    v11 = a4;
    do
    {
      v12 = *(_WORD *)((char *)v8 + v7);
      *v8++ = v12;
      if ( !v12 )
        break;
      if ( !--v9 )
        break;
      --v11;
    }
    while ( v11 );
    v13 = v11 == 0;
    v4 = a1;
    if ( v13 )
      *v8 = 0;
  }
  if ( v9 )
    return 0;
  if ( a4 != -1 )
  {
    *v4 = 0;
    v5 = _errno();
    v14 = 34;
    goto LABEL_5;
  }
  v4[a2 - 1] = 0;
  return 80;
}

```

## disassembly

```asm
0x40fe5a  mov     edi, edi
0x40fe5c  push    ebp
0x40fe5d  mov     ebp, esp
0x40fe5f  mov     ecx, [ebp+arg_0]
0x40fe62  push    ebx
0x40fe63  mov     ebx, [ebp+arg_8]
0x40fe66  push    esi
0x40fe67  mov     esi, [ebp+arg_C]
0x40fe6a  test    esi, esi
0x40fe6c  jnz     short loc_40FE8C
0x40fe6e  test    ecx, ecx
0x40fe70  jnz     short loc_40FE90
0x40fe72  cmp     [ebp+arg_4], esi
0x40fe75  jz      short loc_40FEA0
0x40fe77  call    __errno
0x40fe7c  push    16h
0x40fe7e  pop     esi
0x40fe7f  mov     [eax], esi
0x40fe81  call    __invalid_parameter_noinfo
0x40fe86  mov     eax, esi
0x40fe88  pop     esi
0x40fe89  pop     ebx
0x40fe8a  pop     ebp
0x40fe8b  retn
0x40fe8c  test    ecx, ecx
0x40fe8e  jz      short loc_40FE77
0x40fe90  mov     eax, [ebp+arg_4]
0x40fe93  test    eax, eax
0x40fe95  jz      short loc_40FE77
0x40fe97  test    esi, esi
0x40fe99  jnz     short loc_40FEA4
0x40fe9b  xor     eax, eax
0x40fe9d  mov     [ecx], ax
0x40fea0  xor     eax, eax
0x40fea2  jmp     short loc_40FE88
0x40fea4  test    ebx, ebx
0x40fea6  jnz     short loc_40FEAF
0x40fea8  xor     eax, eax
0x40feaa  mov     [ecx], ax
0x40fead  jmp     short loc_40FE77
0x40feaf  sub     ebx, ecx
0x40feb1  mov     edx, ecx
0x40feb3  push    edi
0x40feb4  mov     edi, eax
0x40feb6  cmp     esi, 0FFFFFFFFh
0x40feb9  jnz     short loc_40FED1
0x40febb  movzx   eax, word ptr [ebx+edx]
0x40febf  mov     [edx], ax
0x40fec2  lea     edx, [edx+2]
0x40fec5  test    ax, ax
0x40fec8  jz      short loc_40FEF8
0x40feca  sub     edi, 1
0x40fecd  jnz     short loc_40FEBB
0x40fecf  jmp     short loc_40FEF8
0x40fed1  mov     ecx, esi
0x40fed3  movzx   eax, word ptr [ebx+edx]
0x40fed7  mov     [edx], ax
0x40feda  lea     edx, [edx+2]
0x40fedd  test    ax, ax
0x40fee0  jz      short loc_40FEEC
0x40fee2  sub     edi, 1
0x40fee5  jz      short loc_40FEEC
0x40fee7  sub     ecx, 1
0x40feea  jnz     short loc_40FED3
0x40feec  test    ecx, ecx
0x40feee  mov     ecx, [ebp+arg_0]
0x40fef1  jnz     short loc_40FEF8
0x40fef3  xor     eax, eax
0x40fef5  mov     [edx], ax
0x40fef8  test    edi, edi
0x40fefa  pop     edi
0x40fefb  jnz     short loc_40FEA0
0x40fefd  cmp     esi, 0FFFFFFFFh
0x40ff00  jnz     short loc_40FF14
0x40ff02  mov     eax, [ebp+arg_4]
0x40ff05  xor     edx, edx
0x40ff07  push    50h ; 'P'
0x40ff09  mov     [ecx+eax*2-2], dx
0x40ff0e  pop     eax
0x40ff0f  jmp     loc_40FE88
0x40ff14  xor     eax, eax
0x40ff16  mov     [ecx], ax
0x40ff19  call    __errno
0x40ff1e  push    22h ; '"'
0x40ff20  jmp     loc_40FE7E
```
