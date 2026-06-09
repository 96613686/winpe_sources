# create_environment<wchar_t>(wchar_t * const)

- ea: `0x410c9a`
- end: `0x410da6`
- name: `??$create_environment@_W@@YAQAPA_WQA_W@Z`
- size: `268`
- prototype: `wchar_t **__cdecl(wchar_t *Source)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x410c4c`

## callees

- `0x410396`
- `0x410c9a`
- `0x410da7`
- `0x4136b2`
- `0x413e19`
- `0x414ba9`

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
            unknown_libname_7(v5);
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
0x410c9a  mov     edi, edi
0x410c9c  push    ebp
0x410c9d  mov     ebp, esp
0x410c9f  sub     esp, 0Ch
0x410ca2  push    ebx
0x410ca3  mov     ebx, [ebp+Source]
0x410ca6  xor     eax, eax
0x410ca8  mov     [ebp+var_4], eax
0x410cab  mov     edx, eax
0x410cad  push    esi
0x410cae  push    edi
0x410caf  movzx   eax, word ptr [ebx]
0x410cb2  mov     esi, ebx
0x410cb4  test    ax, ax
0x410cb7  jz      short loc_410CEC
0x410cb9  push    3Dh ; '='
0x410cbb  mov     ecx, eax
0x410cbd  pop     ebx
0x410cbe  cmp     cx, bx
0x410cc1  jz      short loc_410CC4
0x410cc3  inc     edx
0x410cc4  mov     ecx, esi
0x410cc6  lea     edi, [ecx+2]
0x410cc9  mov     ax, [ecx]
0x410ccc  add     ecx, 2
0x410ccf  cmp     ax, word ptr [ebp+var_4]
0x410cd3  jnz     short loc_410CC9
0x410cd5  sub     ecx, edi
0x410cd7  sar     ecx, 1
0x410cd9  lea     esi, [esi+ecx*2]
0x410cdc  add     esi, 2
0x410cdf  movzx   eax, word ptr [esi]
0x410ce2  mov     ecx, eax
0x410ce4  test    ax, ax
0x410ce7  jnz     short loc_410CBE
0x410ce9  mov     ebx, [ebp+Source]
0x410cec  lea     eax, [edx+1]
0x410cef  push    4; Size
0x410cf1  push    eax; Count
0x410cf2  call    __calloc_base
0x410cf7  mov     edi, eax
0x410cf9  pop     ecx
0x410cfa  pop     ecx
0x410cfb  test    edi, edi
0x410cfd  jz      loc_410D8A
0x410d03  movzx   eax, word ptr [ebx]
0x410d06  mov     [ebp+var_8], edi
0x410d09  test    ax, ax
0x410d0c  jz      short loc_410D8A
0x410d0e  mov     edx, eax
0x410d10  mov     ecx, ebx
0x410d12  lea     esi, [ecx+2]
0x410d15  mov     ax, [ecx]
0x410d18  add     ecx, 2
0x410d1b  cmp     ax, word ptr [ebp+var_4]
0x410d1f  jnz     short loc_410D15
0x410d21  sub     ecx, esi
0x410d23  sar     ecx, 1
0x410d25  push    3Dh ; '='
0x410d27  lea     eax, [ecx+1]
0x410d2a  pop     ecx
0x410d2b  mov     [ebp+SizeInWords], eax
0x410d2e  cmp     dx, cx
0x410d31  jz      short loc_410D6B
0x410d33  push    2; Size
0x410d35  push    eax; Count
0x410d36  call    __calloc_base
0x410d3b  mov     esi, eax
0x410d3d  pop     ecx
0x410d3e  pop     ecx
0x410d3f  test    esi, esi
0x410d41  jz      short loc_410D7A
0x410d43  push    ebx; Source
0x410d44  push    [ebp+SizeInWords]; SizeInWords
0x410d47  push    esi; Destination
0x410d48  call    _wcscpy_s
0x410d4d  add     esp, 0Ch
0x410d50  test    eax, eax
0x410d52  jnz     short loc_410D9A
0x410d54  mov     eax, [ebp+var_8]
0x410d57  mov     [eax], esi
0x410d59  add     eax, 4
0x410d5c  mov     [ebp+var_8], eax
0x410d5f  xor     eax, eax
0x410d61  push    eax; Block
0x410d62  call    __free_base
0x410d67  mov     eax, [ebp+SizeInWords]
0x410d6a  pop     ecx
0x410d6b  lea     ebx, [ebx+eax*2]
0x410d6e  movzx   eax, word ptr [ebx]
0x410d71  mov     edx, eax
0x410d73  test    ax, ax
0x410d76  jnz     short loc_410D10
0x410d78  jmp     short loc_410D8A
0x410d7a  push    edi; Block
0x410d7b  call    unknown_libname_7; Microsoft VisualC universal runtime
0x410d80  xor     edi, edi
0x410d82  push    edi; Block
0x410d83  call    __free_base
0x410d88  pop     ecx
0x410d89  pop     ecx
0x410d8a  xor     eax, eax
0x410d8c  push    eax; Block
0x410d8d  call    __free_base
0x410d92  pop     ecx
0x410d93  mov     eax, edi
0x410d95  pop     edi
0x410d96  pop     esi
0x410d97  pop     ebx
0x410d98  leave
0x410d99  retn
0x410d9a  xor     eax, eax
0x410d9c  push    eax; Reserved
0x410d9d  push    eax; LineNo
0x410d9e  push    eax; FileName
0x410d9f  push    eax; FunctionName
0x410da0  push    eax; Expression
0x410da1  call    __invoke_watson
```
