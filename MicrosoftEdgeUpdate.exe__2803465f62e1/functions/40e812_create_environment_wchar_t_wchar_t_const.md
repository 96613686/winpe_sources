# create_environment<wchar_t>(wchar_t * const)

- ea: `0x40e812`
- end: `0x40e91e`
- name: `??$create_environment@_W@@YAQAPA_WQA_W@Z`
- size: `268`
- prototype: `wchar_t **__cdecl(wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x40e7c4`

## callees

- `0x40de81`
- `0x40e812`
- `0x40e91f`
- `0x40fdf6`
- `0x40ffbd`
- `0x41001a`

## pseudocode

```c
wchar_t **__cdecl create_environment<wchar_t>(wchar_t *Source)
{
  wchar_t *v1; // ebx
  int v2; // edx
  const unsigned __int16 *v3; // esi
  unsigned __int16 v4; // cx
  wchar_t **v5; // edi
  unsigned __int16 v6; // dx
  size_t v7; // eax
  wchar_t *v8; // eax
  wchar_t *v9; // esi
  rsize_t SizeInWords; // [esp+Ch] [ebp-Ch]
  wchar_t **v12; // [esp+10h] [ebp-8h]

  v1 = Source;
  v2 = 0;
  v3 = Source;
  if ( *Source )
  {
    v4 = *Source;
    do
    {
      if ( v4 != 61 )
        ++v2;
      v3 += wcslen(v3) + 1;
      v4 = *v3;
    }
    while ( *v3 );
    v1 = Source;
  }
  v5 = (wchar_t **)_calloc_base(v2 + 1, 4u);
  if ( v5 )
  {
    v12 = v5;
    if ( *v1 )
    {
      v6 = *v1;
      do
      {
        v7 = wcslen(v1) + 1;
        SizeInWords = v7;
        if ( v6 != 61 )
        {
          v8 = (wchar_t *)_calloc_base(v7, 2u);
          v9 = v8;
          if ( !v8 )
          {
            unknown_libname_5(v5);
            v5 = 0;
            _free_base(0);
            break;
          }
          if ( wcscpy_s(v8, SizeInWords, v1) )
            _invoke_watson(0, 0, 0, 0, 0);
          *v12++ = v9;
          _free_base(0);
          v7 = SizeInWords;
        }
        v1 += v7;
        v6 = *v1;
      }
      while ( *v1 );
    }
  }
  _free_base(0);
  return v5;
}

```

## disassembly

```asm
0x40e812  mov     edi, edi
0x40e814  push    ebp
0x40e815  mov     ebp, esp
0x40e817  sub     esp, 0Ch
0x40e81a  push    ebx
0x40e81b  mov     ebx, [ebp+Source]
0x40e81e  xor     eax, eax
0x40e820  mov     [ebp+var_4], eax
0x40e823  mov     edx, eax
0x40e825  push    esi
0x40e826  push    edi
0x40e827  movzx   eax, word ptr [ebx]
0x40e82a  mov     esi, ebx
0x40e82c  test    ax, ax
0x40e82f  jz      short loc_40E864
0x40e831  push    3Dh ; '='
0x40e833  mov     ecx, eax
0x40e835  pop     ebx
0x40e836  cmp     cx, bx
0x40e839  jz      short loc_40E83C
0x40e83b  inc     edx
0x40e83c  mov     ecx, esi
0x40e83e  lea     edi, [ecx+2]
0x40e841  mov     ax, [ecx]
0x40e844  add     ecx, 2
0x40e847  cmp     ax, word ptr [ebp+var_4]
0x40e84b  jnz     short loc_40E841
0x40e84d  sub     ecx, edi
0x40e84f  sar     ecx, 1
0x40e851  lea     esi, [esi+ecx*2]
0x40e854  add     esi, 2
0x40e857  movzx   eax, word ptr [esi]
0x40e85a  mov     ecx, eax
0x40e85c  test    ax, ax
0x40e85f  jnz     short loc_40E836
0x40e861  mov     ebx, [ebp+Source]
0x40e864  lea     eax, [edx+1]
0x40e867  push    4; Size
0x40e869  push    eax; Count
0x40e86a  call    __calloc_base
0x40e86f  mov     edi, eax
0x40e871  pop     ecx
0x40e872  pop     ecx
0x40e873  test    edi, edi
0x40e875  jz      loc_40E902
0x40e87b  movzx   eax, word ptr [ebx]
0x40e87e  mov     [ebp+var_8], edi
0x40e881  test    ax, ax
0x40e884  jz      short loc_40E902
0x40e886  mov     edx, eax
0x40e888  mov     ecx, ebx
0x40e88a  lea     esi, [ecx+2]
0x40e88d  mov     ax, [ecx]
0x40e890  add     ecx, 2
0x40e893  cmp     ax, word ptr [ebp+var_4]
0x40e897  jnz     short loc_40E88D
0x40e899  sub     ecx, esi
0x40e89b  sar     ecx, 1
0x40e89d  push    3Dh ; '='
0x40e89f  lea     eax, [ecx+1]
0x40e8a2  pop     ecx
0x40e8a3  mov     [ebp+SizeInWords], eax
0x40e8a6  cmp     dx, cx
0x40e8a9  jz      short loc_40E8E3
0x40e8ab  push    2; Size
0x40e8ad  push    eax; Count
0x40e8ae  call    __calloc_base
0x40e8b3  mov     esi, eax
0x40e8b5  pop     ecx
0x40e8b6  pop     ecx
0x40e8b7  test    esi, esi
0x40e8b9  jz      short loc_40E8F2
0x40e8bb  push    ebx; Source
0x40e8bc  push    [ebp+SizeInWords]; SizeInWords
0x40e8bf  push    esi; Destination
0x40e8c0  call    _wcscpy_s
0x40e8c5  add     esp, 0Ch
0x40e8c8  test    eax, eax
0x40e8ca  jnz     short loc_40E912
0x40e8cc  mov     eax, [ebp+var_8]
0x40e8cf  mov     [eax], esi
0x40e8d1  add     eax, 4
0x40e8d4  mov     [ebp+var_8], eax
0x40e8d7  xor     eax, eax
0x40e8d9  push    eax; Block
0x40e8da  call    __free_base
0x40e8df  mov     eax, [ebp+SizeInWords]
0x40e8e2  pop     ecx
0x40e8e3  lea     ebx, [ebx+eax*2]
0x40e8e6  movzx   eax, word ptr [ebx]
0x40e8e9  mov     edx, eax
0x40e8eb  test    ax, ax
0x40e8ee  jnz     short loc_40E888
0x40e8f0  jmp     short loc_40E902
0x40e8f2  push    edi; Block
0x40e8f3  call    unknown_libname_5; Microsoft VisualC universal runtime
0x40e8f8  xor     edi, edi
0x40e8fa  push    edi; Block
0x40e8fb  call    __free_base
0x40e900  pop     ecx
0x40e901  pop     ecx
0x40e902  xor     eax, eax
0x40e904  push    eax; Block
0x40e905  call    __free_base
0x40e90a  pop     ecx
0x40e90b  mov     eax, edi
0x40e90d  pop     edi
0x40e90e  pop     esi
0x40e90f  pop     ebx
0x40e910  leave
0x40e911  retn
0x40e912  xor     eax, eax
0x40e914  push    eax; Reserved
0x40e915  push    eax; LineNo
0x40e916  push    eax; FileName
0x40e917  push    eax; FunctionName
0x40e918  push    eax; Expression
0x40e919  call    __invoke_watson
```
