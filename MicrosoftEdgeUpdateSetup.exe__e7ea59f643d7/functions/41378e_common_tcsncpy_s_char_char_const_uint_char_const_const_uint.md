# common_tcsncpy_s<char>(char * const,uint,char const * const,uint)

- ea: `0x41378e`
- end: `0x413841`
- name: `??$common_tcsncpy_s@D@@YAHQADIQBDI@Z`
- size: `179`
- prototype: `int __cdecl(_BYTE *, int, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x413841`

## callees

- `0x40ec26`
- `0x40ece3`
- `0x41378e`

## pseudocode

```c
int __cdecl common_tcsncpy_s<char>(_BYTE *a1, int a2, int a3, int a4)
{
  _BYTE *v4; // ecx
  int *v5; // eax
  int v7; // ebx
  _BYTE *v8; // edx
  int v9; // edi
  char v10; // al
  int v11; // ecx
  char v12; // al
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
      v10 = v8[v7];
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
      v12 = v8[v7];
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
0x41378e  mov     edi, edi
0x413790  push    ebp
0x413791  mov     ebp, esp
0x413793  mov     ecx, [ebp+arg_0]
0x413796  push    ebx
0x413797  mov     ebx, [ebp+arg_8]
0x41379a  push    esi
0x41379b  mov     esi, [ebp+arg_C]
0x41379e  test    esi, esi
0x4137a0  jnz     short loc_4137C0
0x4137a2  test    ecx, ecx
0x4137a4  jnz     short loc_4137C4
0x4137a6  cmp     [ebp+arg_4], esi
0x4137a9  jz      short loc_4137D2
0x4137ab  call    __errno
0x4137b0  push    16h
0x4137b2  pop     esi
0x4137b3  mov     [eax], esi
0x4137b5  call    __invalid_parameter_noinfo
0x4137ba  mov     eax, esi
0x4137bc  pop     esi
0x4137bd  pop     ebx
0x4137be  pop     ebp
0x4137bf  retn
0x4137c0  test    ecx, ecx
0x4137c2  jz      short loc_4137AB
0x4137c4  mov     eax, [ebp+arg_4]
0x4137c7  test    eax, eax
0x4137c9  jz      short loc_4137AB
0x4137cb  test    esi, esi
0x4137cd  jnz     short loc_4137D6
0x4137cf  mov     byte ptr [ecx], 0
0x4137d2  xor     eax, eax
0x4137d4  jmp     short loc_4137BC
0x4137d6  test    ebx, ebx
0x4137d8  jnz     short loc_4137DE
0x4137da  mov     [ecx], bl
0x4137dc  jmp     short loc_4137AB
0x4137de  sub     ebx, ecx
0x4137e0  mov     edx, ecx
0x4137e2  push    edi
0x4137e3  mov     edi, eax
0x4137e5  cmp     esi, 0FFFFFFFFh
0x4137e8  jnz     short loc_4137FB
0x4137ea  mov     al, [ebx+edx]
0x4137ed  mov     [edx], al
0x4137ef  inc     edx
0x4137f0  test    al, al
0x4137f2  jz      short loc_41381B
0x4137f4  sub     edi, 1
0x4137f7  jnz     short loc_4137EA
0x4137f9  jmp     short loc_41381B
0x4137fb  mov     ecx, esi
0x4137fd  mov     al, [ebx+edx]
0x413800  mov     [edx], al
0x413802  inc     edx
0x413803  test    al, al
0x413805  jz      short loc_413811
0x413807  sub     edi, 1
0x41380a  jz      short loc_413811
0x41380c  sub     ecx, 1
0x41380f  jnz     short loc_4137FD
0x413811  test    ecx, ecx
0x413813  mov     ecx, [ebp+arg_0]
0x413816  jnz     short loc_41381B
0x413818  mov     byte ptr [edx], 0
0x41381b  test    edi, edi
0x41381d  pop     edi
0x41381e  jnz     short loc_4137D2
0x413820  cmp     esi, 0FFFFFFFFh
0x413823  jnz     short loc_413832
0x413825  mov     eax, [ebp+arg_4]
0x413828  push    50h ; 'P'
0x41382a  mov     byte ptr [ecx+eax-1], 0
0x41382f  pop     eax
0x413830  jmp     short loc_4137BC
0x413832  mov     byte ptr [ecx], 0
0x413835  call    __errno
0x41383a  push    22h ; '"'
0x41383c  jmp     loc_4137B2
```
