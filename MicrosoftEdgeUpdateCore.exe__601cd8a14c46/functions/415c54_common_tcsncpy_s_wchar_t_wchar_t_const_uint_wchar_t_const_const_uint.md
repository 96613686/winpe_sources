# common_tcsncpy_s<wchar_t>(wchar_t * const,uint,wchar_t const * const,uint)

- ea: `0x415c54`
- end: `0x415d1f`
- name: `??$common_tcsncpy_s@_W@@YAHQA_WIQB_WI@Z`
- size: `203`
- prototype: `int __cdecl(_WORD *, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x415d1f`

## callees

- `0x410369`
- `0x410443`
- `0x415c54`

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
0x415c54  mov     edi, edi
0x415c56  push    ebp
0x415c57  mov     ebp, esp
0x415c59  mov     ecx, [ebp+arg_0]
0x415c5c  push    ebx
0x415c5d  mov     ebx, [ebp+arg_8]
0x415c60  push    esi
0x415c61  mov     esi, [ebp+arg_C]
0x415c64  test    esi, esi
0x415c66  jnz     short loc_415C86
0x415c68  test    ecx, ecx
0x415c6a  jnz     short loc_415C8A
0x415c6c  cmp     [ebp+arg_4], esi
0x415c6f  jz      short loc_415C9A
0x415c71  call    __errno
0x415c76  push    16h
0x415c78  pop     esi
0x415c79  mov     [eax], esi
0x415c7b  call    __invalid_parameter_noinfo
0x415c80  mov     eax, esi
0x415c82  pop     esi
0x415c83  pop     ebx
0x415c84  pop     ebp
0x415c85  retn
0x415c86  test    ecx, ecx
0x415c88  jz      short loc_415C71
0x415c8a  mov     eax, [ebp+arg_4]
0x415c8d  test    eax, eax
0x415c8f  jz      short loc_415C71
0x415c91  test    esi, esi
0x415c93  jnz     short loc_415C9E
0x415c95  xor     eax, eax
0x415c97  mov     [ecx], ax
0x415c9a  xor     eax, eax
0x415c9c  jmp     short loc_415C82
0x415c9e  test    ebx, ebx
0x415ca0  jnz     short loc_415CA9
0x415ca2  xor     eax, eax
0x415ca4  mov     [ecx], ax
0x415ca7  jmp     short loc_415C71
0x415ca9  sub     ebx, ecx
0x415cab  mov     edx, ecx
0x415cad  push    edi
0x415cae  mov     edi, eax
0x415cb0  cmp     esi, 0FFFFFFFFh
0x415cb3  jnz     short loc_415CCB
0x415cb5  movzx   eax, word ptr [ebx+edx]
0x415cb9  mov     [edx], ax
0x415cbc  lea     edx, [edx+2]
0x415cbf  test    ax, ax
0x415cc2  jz      short loc_415CF2
0x415cc4  sub     edi, 1
0x415cc7  jnz     short loc_415CB5
0x415cc9  jmp     short loc_415CF2
0x415ccb  mov     ecx, esi
0x415ccd  movzx   eax, word ptr [ebx+edx]
0x415cd1  mov     [edx], ax
0x415cd4  lea     edx, [edx+2]
0x415cd7  test    ax, ax
0x415cda  jz      short loc_415CE6
0x415cdc  sub     edi, 1
0x415cdf  jz      short loc_415CE6
0x415ce1  sub     ecx, 1
0x415ce4  jnz     short loc_415CCD
0x415ce6  test    ecx, ecx
0x415ce8  mov     ecx, [ebp+arg_0]
0x415ceb  jnz     short loc_415CF2
0x415ced  xor     eax, eax
0x415cef  mov     [edx], ax
0x415cf2  test    edi, edi
0x415cf4  pop     edi
0x415cf5  jnz     short loc_415C9A
0x415cf7  cmp     esi, 0FFFFFFFFh
0x415cfa  jnz     short loc_415D0E
0x415cfc  mov     eax, [ebp+arg_4]
0x415cff  xor     edx, edx
0x415d01  push    50h ; 'P'
0x415d03  mov     [ecx+eax*2-2], dx
0x415d08  pop     eax
0x415d09  jmp     loc_415C82
0x415d0e  xor     eax, eax
0x415d10  mov     [ecx], ax
0x415d13  call    __errno
0x415d18  push    22h ; '"'
0x415d1a  jmp     loc_415C78
```
