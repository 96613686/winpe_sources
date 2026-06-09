# copy_and_add_argument_to_buffer<wchar_t>(wchar_t const * const,wchar_t const * const,uint,`anonymous namespace'::argument_list<wchar_t> &)

- ea: `0x4140c0`
- end: `0x414173`
- name: `??$copy_and_add_argument_to_buffer@_W@@YAHQB_W0IAAV?$argument_list@_W@?A0x5f5c8891@@@Z`
- size: `179`
- prototype: `int __cdecl(wchar_t *, wchar_t *Source, rsize_t MaxCount, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x413e98`
- `0x414174`

## callees

- `0x410396`
- `0x4136b2`
- `0x413e19`
- `0x4140c0`
- `0x41430a`
- `0x415d1f`

## pseudocode

```c
int __cdecl copy_and_add_argument_to_buffer<wchar_t>(wchar_t *a1, wchar_t *Source, rsize_t MaxCount, int a4)
{
  unsigned int v4; // kr00_4
  size_t v6; // ebx
  wchar_t *v7; // eax
  wchar_t *v8; // esi
  int v9; // ebx

  v4 = wcslen(a1);
  if ( v4 + 1 > ~MaxCount )
    return 12;
  v6 = v4 + 1 + MaxCount + 1;
  v7 = (wchar_t *)_calloc_base(v6, 2u);
  v8 = v7;
  if ( MaxCount && wcsncpy_s(v7, v6, Source, MaxCount) || wcsncpy_s(&v8[MaxCount], v6 - MaxCount, a1, v4 + 1) )
    _invoke_watson(0, 0, 0, 0, 0);
  v9 = unknown_libname_31(a4);
  if ( v9 )
  {
    _free_base(v8);
  }
  else
  {
    **(_DWORD **)(a4 + 4) = v8;
    *(_DWORD *)(a4 + 4) += 4;
    v9 = 0;
  }
  _free_base(0);
  return v9;
}

```

## disassembly

```asm
0x4140c0  mov     edi, edi
0x4140c2  push    ebp
0x4140c3  mov     ebp, esp
0x4140c5  push    ecx
0x4140c6  mov     ecx, [ebp+arg_0]
0x4140c9  push    ebx
0x4140ca  push    edi
0x4140cb  xor     ebx, ebx
0x4140cd  lea     edx, [ecx+2]
0x4140d0  mov     ax, [ecx]
0x4140d3  add     ecx, 2
0x4140d6  cmp     ax, bx
0x4140d9  jnz     short loc_4140D0
0x4140db  mov     edi, [ebp+MaxCount]
0x4140de  sub     ecx, edx
0x4140e0  sar     ecx, 1
0x4140e2  mov     eax, edi
0x4140e4  inc     ecx
0x4140e5  not     eax
0x4140e7  mov     [ebp+var_4], ecx
0x4140ea  cmp     ecx, eax
0x4140ec  jbe     short loc_4140F5
0x4140ee  push    0Ch
0x4140f0  pop     eax
0x4140f1  pop     edi
0x4140f2  pop     ebx
0x4140f3  leave
0x4140f4  retn
0x4140f5  push    esi
0x4140f6  lea     ebx, [edi+1]
0x4140f9  add     ebx, ecx
0x4140fb  push    2; Size
0x4140fd  push    ebx; Count
0x4140fe  call    __calloc_base
0x414103  mov     esi, eax
0x414105  pop     ecx
0x414106  pop     ecx
0x414107  test    edi, edi
0x414109  jz      short loc_41411D
0x41410b  push    edi; MaxCount
0x41410c  push    [ebp+Source]; Source
0x41410f  push    ebx; SizeInWords
0x414110  push    esi; Destination
0x414111  call    _wcsncpy_s
0x414116  add     esp, 10h
0x414119  test    eax, eax
0x41411b  jnz     short loc_414167
0x41411d  push    [ebp+var_4]; MaxCount
0x414120  sub     ebx, edi
0x414122  lea     eax, [esi+edi*2]
0x414125  push    [ebp+arg_0]; Source
0x414128  push    ebx; SizeInWords
0x414129  push    eax; Destination
0x41412a  call    _wcsncpy_s
0x41412f  add     esp, 10h
0x414132  test    eax, eax
0x414134  jnz     short loc_414167
0x414136  mov     edi, [ebp+arg_C]
0x414139  mov     ecx, edi
0x41413b  call    unknown_libname_31; Microsoft VisualC universal runtime
0x414140  mov     ebx, eax
0x414142  test    ebx, ebx
0x414144  jz      short loc_41414F
0x414146  push    esi; Block
0x414147  call    __free_base
0x41414c  pop     ecx
0x41414d  jmp     short loc_41415A
0x41414f  mov     eax, [edi+4]
0x414152  mov     [eax], esi
0x414154  add     dword ptr [edi+4], 4
0x414158  xor     ebx, ebx
0x41415a  push    0; Block
0x41415c  call    __free_base
0x414161  pop     ecx
0x414162  mov     eax, ebx
0x414164  pop     esi
0x414165  jmp     short loc_4140F1
0x414167  xor     eax, eax
0x414169  push    eax; Reserved
0x41416a  push    eax; LineNo
0x41416b  push    eax; FileName
0x41416c  push    eax; FunctionName
0x41416d  push    eax; Expression
0x41416e  call    __invoke_watson
```
