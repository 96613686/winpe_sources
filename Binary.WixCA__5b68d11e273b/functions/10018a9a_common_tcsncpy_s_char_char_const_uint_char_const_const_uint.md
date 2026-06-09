# common_tcsncpy_s<char>(char * const,uint,char const * const,uint)

- ea: `0x10018a9a`
- end: `0x10018b4d`
- name: `??$common_tcsncpy_s@D@@YAHQADIQBDI@Z`
- size: `179`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x10018b4d`

## callees

- `0x10015cbc`
- `0x10015d79`
- `0x10018a9a`

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
0x10018a9a  mov     edi, edi
0x10018a9c  push    ebp
0x10018a9d  mov     ebp, esp
0x10018a9f  mov     ecx, [ebp+arg_0]
0x10018aa2  push    ebx
0x10018aa3  mov     ebx, [ebp+arg_8]
0x10018aa6  push    esi
0x10018aa7  mov     esi, [ebp+arg_C]
0x10018aaa  test    esi, esi
0x10018aac  jnz     short loc_10018ACC
0x10018aae  test    ecx, ecx
0x10018ab0  jnz     short loc_10018AD0
0x10018ab2  cmp     [ebp+arg_4], esi
0x10018ab5  jz      short loc_10018ADE
0x10018ab7  call    __errno
0x10018abc  push    16h
0x10018abe  pop     esi
0x10018abf  mov     [eax], esi
0x10018ac1  call    __invalid_parameter_noinfo
0x10018ac6  mov     eax, esi
0x10018ac8  pop     esi
0x10018ac9  pop     ebx
0x10018aca  pop     ebp
0x10018acb  retn
0x10018acc  test    ecx, ecx
0x10018ace  jz      short loc_10018AB7
0x10018ad0  mov     eax, [ebp+arg_4]
0x10018ad3  test    eax, eax
0x10018ad5  jz      short loc_10018AB7
0x10018ad7  test    esi, esi
0x10018ad9  jnz     short loc_10018AE2
0x10018adb  mov     byte ptr [ecx], 0
0x10018ade  xor     eax, eax
0x10018ae0  jmp     short loc_10018AC8
0x10018ae2  test    ebx, ebx
0x10018ae4  jnz     short loc_10018AEA
0x10018ae6  mov     [ecx], bl
0x10018ae8  jmp     short loc_10018AB7
0x10018aea  sub     ebx, ecx
0x10018aec  mov     edx, ecx
0x10018aee  push    edi
0x10018aef  mov     edi, eax
0x10018af1  cmp     esi, 0FFFFFFFFh
0x10018af4  jnz     short loc_10018B07
0x10018af6  mov     al, [ebx+edx]
0x10018af9  mov     [edx], al
0x10018afb  inc     edx
0x10018afc  test    al, al
0x10018afe  jz      short loc_10018B27
0x10018b00  sub     edi, 1
0x10018b03  jnz     short loc_10018AF6
0x10018b05  jmp     short loc_10018B27
0x10018b07  mov     ecx, esi
0x10018b09  mov     al, [ebx+edx]
0x10018b0c  mov     [edx], al
0x10018b0e  inc     edx
0x10018b0f  test    al, al
0x10018b11  jz      short loc_10018B1D
0x10018b13  sub     edi, 1
0x10018b16  jz      short loc_10018B1D
0x10018b18  sub     ecx, 1
0x10018b1b  jnz     short loc_10018B09
0x10018b1d  test    ecx, ecx
0x10018b1f  mov     ecx, [ebp+arg_0]
0x10018b22  jnz     short loc_10018B27
0x10018b24  mov     byte ptr [edx], 0
0x10018b27  test    edi, edi
0x10018b29  pop     edi
0x10018b2a  jnz     short loc_10018ADE
0x10018b2c  cmp     esi, 0FFFFFFFFh
0x10018b2f  jnz     short loc_10018B3E
0x10018b31  mov     eax, [ebp+arg_4]
0x10018b34  push    50h ; 'P'
0x10018b36  mov     byte ptr [ecx+eax-1], 0
0x10018b3b  pop     eax
0x10018b3c  jmp     short loc_10018AC8
0x10018b3e  mov     byte ptr [ecx], 0
0x10018b41  call    __errno
0x10018b46  push    22h ; '"'
0x10018b48  jmp     loc_10018ABE
```
