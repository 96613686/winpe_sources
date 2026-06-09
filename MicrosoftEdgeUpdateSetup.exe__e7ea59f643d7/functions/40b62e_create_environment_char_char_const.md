# create_environment<char>(char * const)

- ea: `0x40b62e`
- end: `0x40b6fe`
- name: `??$create_environment@D@@YAQAPADQAD@Z`
- size: `208`
- prototype: `void *__cdecl(char *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x40b5db`

## callees

- `0x40b62e`
- `0x40b6fe`
- `0x40c2b1`
- `0x40ec36`
- `0x40ecf6`
- `0x40ed53`

## pseudocode

```c
void *__cdecl create_environment<char>(char *Source)
{
  const char *v1; // ebx
  int v2; // edx
  char *v3; // esi
  char i; // al
  void *v5; // eax
  void *v6; // edi
  unsigned int v7; // ecx
  rsize_t v8; // eax
  char *v9; // eax
  char *v10; // esi
  rsize_t SizeInBytes; // [esp+Ch] [ebp-8h]
  char **v13; // [esp+10h] [ebp-4h]

  v1 = Source;
  v2 = 0;
  v3 = Source;
  for ( i = *Source; i; i = *v3 )
  {
    if ( i != 61 )
      ++v2;
    v3 += strlen(v3) + 1;
  }
  v5 = _calloc_base(v2 + 1, 4u);
  v6 = v5;
  if ( v5 )
  {
    v13 = (char **)v5;
    while ( *v1 )
    {
      v7 = strlen(v1);
      v8 = v7 + 1;
      SizeInBytes = v7 + 1;
      if ( *v1 != 61 )
      {
        v9 = (char *)_calloc_base(v7 + 1, 1u);
        v10 = v9;
        if ( !v9 )
        {
          unknown_libname_4(v6);
          _free_base(0);
          goto LABEL_16;
        }
        if ( strcpy_s(v9, SizeInBytes, v1) )
          _invoke_watson(0, 0, 0, 0, 0);
        *v13++ = v10;
        _free_base(0);
        v8 = SizeInBytes;
      }
      v1 += v8;
    }
  }
  else
  {
LABEL_16:
    v6 = 0;
  }
  _free_base(0);
  return v6;
}

```

## disassembly

```asm
0x40b62e  mov     edi, edi
0x40b630  push    ebp
0x40b631  mov     ebp, esp
0x40b633  push    ecx
0x40b634  push    ecx
0x40b635  push    ebx
0x40b636  mov     ebx, [ebp+Source]
0x40b639  xor     edx, edx
0x40b63b  push    esi
0x40b63c  push    edi
0x40b63d  mov     esi, ebx
0x40b63f  mov     al, [ebx]
0x40b641  jmp     short loc_40B65B
0x40b643  cmp     al, 3Dh ; '='
0x40b645  jz      short loc_40B648
0x40b647  inc     edx
0x40b648  mov     ecx, esi
0x40b64a  lea     edi, [ecx+1]
0x40b64d  mov     al, [ecx]
0x40b64f  inc     ecx
0x40b650  test    al, al
0x40b652  jnz     short loc_40B64D
0x40b654  sub     ecx, edi
0x40b656  inc     esi
0x40b657  add     esi, ecx
0x40b659  mov     al, [esi]
0x40b65b  test    al, al
0x40b65d  jnz     short loc_40B643
0x40b65f  lea     eax, [edx+1]
0x40b662  push    4; Size
0x40b664  push    eax; Count
0x40b665  call    __calloc_base
0x40b66a  mov     edi, eax
0x40b66c  pop     ecx
0x40b66d  pop     ecx
0x40b66e  test    edi, edi
0x40b670  jz      short loc_40B6E0
0x40b672  mov     [ebp+var_4], edi
0x40b675  jmp     short loc_40B6C9
0x40b677  mov     ecx, ebx
0x40b679  lea     esi, [ecx+1]
0x40b67c  mov     al, [ecx]
0x40b67e  inc     ecx
0x40b67f  test    al, al
0x40b681  jnz     short loc_40B67C
0x40b683  sub     ecx, esi
0x40b685  lea     eax, [ecx+1]
0x40b688  mov     [ebp+SizeInBytes], eax
0x40b68b  cmp     dl, 3Dh ; '='
0x40b68e  jz      short loc_40B6C7
0x40b690  push    1; Size
0x40b692  push    eax; Count
0x40b693  call    __calloc_base
0x40b698  mov     esi, eax
0x40b69a  pop     ecx
0x40b69b  pop     ecx
0x40b69c  test    esi, esi
0x40b69e  jz      short loc_40B6D1
0x40b6a0  push    ebx; Source
0x40b6a1  push    [ebp+SizeInBytes]; SizeInBytes
0x40b6a4  push    esi; Destination
0x40b6a5  call    _strcpy_s
0x40b6aa  add     esp, 0Ch
0x40b6ad  test    eax, eax
0x40b6af  jnz     short loc_40B6F1
0x40b6b1  mov     eax, [ebp+var_4]
0x40b6b4  push    0; Block
0x40b6b6  mov     [eax], esi
0x40b6b8  add     eax, 4
0x40b6bb  mov     [ebp+var_4], eax
0x40b6be  call    __free_base
0x40b6c3  mov     eax, [ebp+SizeInBytes]
0x40b6c6  pop     ecx
0x40b6c7  add     ebx, eax
0x40b6c9  mov     dl, [ebx]
0x40b6cb  test    dl, dl
0x40b6cd  jnz     short loc_40B677
0x40b6cf  jmp     short loc_40B6E2
0x40b6d1  push    edi; Block
0x40b6d2  call    unknown_libname_4; Microsoft VisualC universal runtime
0x40b6d7  push    0; Block
0x40b6d9  call    __free_base
0x40b6de  pop     ecx
0x40b6df  pop     ecx
0x40b6e0  xor     edi, edi
0x40b6e2  push    0; Block
0x40b6e4  call    __free_base
0x40b6e9  pop     ecx
0x40b6ea  mov     eax, edi
0x40b6ec  pop     edi
0x40b6ed  pop     esi
0x40b6ee  pop     ebx
0x40b6ef  leave
0x40b6f0  retn
0x40b6f1  xor     eax, eax
0x40b6f3  push    eax; Reserved
0x40b6f4  push    eax; LineNo
0x40b6f5  push    eax; FileName
0x40b6f6  push    eax; FunctionName
0x40b6f7  push    eax; Expression
0x40b6f8  call    __invoke_watson
```
