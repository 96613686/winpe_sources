# _strcpy_s

- ea: `0x40c2b1`
- end: `0x40c30b`
- name: `_strcpy_s`
- size: `90`
- prototype: `errno_t __cdecl(char *Destination, rsize_t SizeInBytes, const char *Source)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x40afd4`
- `0x40b62e`
- `0x412ad9`
- `0x412e74`
- `0x415318`

## callees

- `0x40c2b1`
- `0x40ec26`
- `0x40ece3`

## pseudocode

```c
errno_t __cdecl strcpy_s(char *Destination, rsize_t SizeInBytes, const char *Source)
{
  rsize_t v3; // ecx
  int *v4; // eax
  errno_t v5; // esi
  char *v7; // edi
  char v8; // al
  int v9; // [esp-4h] [ebp-8h]

  if ( !Destination )
    goto LABEL_5;
  v3 = SizeInBytes;
  if ( !SizeInBytes )
    goto LABEL_5;
  if ( !Source )
  {
    *Destination = 0;
LABEL_5:
    v4 = _errno();
    v9 = 22;
    goto LABEL_6;
  }
  v7 = Destination;
  do
  {
    v8 = v7[Source - Destination];
    *v7++ = v8;
    if ( !v8 )
      break;
    --v3;
  }
  while ( v3 );
  if ( v3 )
    return 0;
  *Destination = 0;
  v4 = _errno();
  v9 = 34;
LABEL_6:
  v5 = v9;
  *v4 = v9;
  _invalid_parameter_noinfo();
  return v5;
}

```

## disassembly

```asm
0x40c2b1  mov     edi, edi
0x40c2b3  push    ebp
0x40c2b4  mov     ebp, esp
0x40c2b6  mov     edx, [ebp+Destination]
0x40c2b9  push    esi
0x40c2ba  test    edx, edx
0x40c2bc  jz      short loc_40C2CF
0x40c2be  mov     ecx, [ebp+SizeInBytes]
0x40c2c1  test    ecx, ecx
0x40c2c3  jz      short loc_40C2CF
0x40c2c5  mov     esi, [ebp+Source]
0x40c2c8  test    esi, esi
0x40c2ca  jnz     short loc_40C2E3
0x40c2cc  mov     byte ptr [edx], 0
0x40c2cf  call    __errno
0x40c2d4  push    16h
0x40c2d6  pop     esi
0x40c2d7  mov     [eax], esi
0x40c2d9  call    __invalid_parameter_noinfo
0x40c2de  mov     eax, esi
0x40c2e0  pop     esi
0x40c2e1  pop     ebp
0x40c2e2  retn
0x40c2e3  push    edi
0x40c2e4  mov     edi, edx
0x40c2e6  sub     esi, edx
0x40c2e8  mov     al, [esi+edi]
0x40c2eb  mov     [edi], al
0x40c2ed  inc     edi
0x40c2ee  test    al, al
0x40c2f0  jz      short loc_40C2F7
0x40c2f2  sub     ecx, 1
0x40c2f5  jnz     short loc_40C2E8
0x40c2f7  pop     edi
0x40c2f8  test    ecx, ecx
0x40c2fa  jnz     short loc_40C307
0x40c2fc  mov     [edx], cl
0x40c2fe  call    __errno
0x40c303  push    22h ; '"'
0x40c305  jmp     short loc_40C2D6
0x40c307  xor     esi, esi
0x40c309  jmp     short loc_40C2DE
```
