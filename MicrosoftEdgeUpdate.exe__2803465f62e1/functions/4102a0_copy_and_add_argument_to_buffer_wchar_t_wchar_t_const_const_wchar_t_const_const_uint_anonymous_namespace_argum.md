# copy_and_add_argument_to_buffer<wchar_t>(wchar_t const * const,wchar_t const * const,uint,`anonymous namespace'::argument_list<wchar_t> &)

- ea: `0x4102a0`
- end: `0x410353`
- name: `??$copy_and_add_argument_to_buffer@_W@@YAHQB_W0IAAV?$argument_list@_W@?A0x5f5c8891@@@Z`
- size: `179`
- prototype: `int __cdecl(wchar_t *, wchar_t *Source, rsize_t MaxCount, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x410078`
- `0x410354`

## callees

- `0x40de81`
- `0x40ff25`
- `0x40ffbd`
- `0x41001a`
- `0x4102a0`
- `0x4104ea`

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
  v9 = unknown_libname_12(a4);
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
0x4102a0  mov     edi, edi
0x4102a2  push    ebp
0x4102a3  mov     ebp, esp
0x4102a5  push    ecx
0x4102a6  mov     ecx, [ebp+arg_0]
0x4102a9  push    ebx
0x4102aa  push    edi
0x4102ab  xor     ebx, ebx
0x4102ad  lea     edx, [ecx+2]
0x4102b0  mov     ax, [ecx]
0x4102b3  add     ecx, 2
0x4102b6  cmp     ax, bx
0x4102b9  jnz     short loc_4102B0
0x4102bb  mov     edi, [ebp+MaxCount]
0x4102be  sub     ecx, edx
0x4102c0  sar     ecx, 1
0x4102c2  mov     eax, edi
0x4102c4  inc     ecx
0x4102c5  not     eax
0x4102c7  mov     [ebp+var_4], ecx
0x4102ca  cmp     ecx, eax
0x4102cc  jbe     short loc_4102D5
0x4102ce  push    0Ch
0x4102d0  pop     eax
0x4102d1  pop     edi
0x4102d2  pop     ebx
0x4102d3  leave
0x4102d4  retn
0x4102d5  push    esi
0x4102d6  lea     ebx, [edi+1]
0x4102d9  add     ebx, ecx
0x4102db  push    2; Size
0x4102dd  push    ebx; Count
0x4102de  call    __calloc_base
0x4102e3  mov     esi, eax
0x4102e5  pop     ecx
0x4102e6  pop     ecx
0x4102e7  test    edi, edi
0x4102e9  jz      short loc_4102FD
0x4102eb  push    edi; MaxCount
0x4102ec  push    [ebp+Source]; Source
0x4102ef  push    ebx; SizeInWords
0x4102f0  push    esi; Destination
0x4102f1  call    _wcsncpy_s
0x4102f6  add     esp, 10h
0x4102f9  test    eax, eax
0x4102fb  jnz     short loc_410347
0x4102fd  push    [ebp+var_4]; MaxCount
0x410300  sub     ebx, edi
0x410302  lea     eax, [esi+edi*2]
0x410305  push    [ebp+arg_0]; Source
0x410308  push    ebx; SizeInWords
0x410309  push    eax; Destination
0x41030a  call    _wcsncpy_s
0x41030f  add     esp, 10h
0x410312  test    eax, eax
0x410314  jnz     short loc_410347
0x410316  mov     edi, [ebp+arg_C]
0x410319  mov     ecx, edi
0x41031b  call    unknown_libname_12; Microsoft VisualC universal runtime
0x410320  mov     ebx, eax
0x410322  test    ebx, ebx
0x410324  jz      short loc_41032F
0x410326  push    esi; Block
0x410327  call    __free_base
0x41032c  pop     ecx
0x41032d  jmp     short loc_41033A
0x41032f  mov     eax, [edi+4]
0x410332  mov     [eax], esi
0x410334  add     dword ptr [edi+4], 4
0x410338  xor     ebx, ebx
0x41033a  push    0; Block
0x41033c  call    __free_base
0x410341  pop     ecx
0x410342  mov     eax, ebx
0x410344  pop     esi
0x410345  jmp     short loc_4102D1
0x410347  xor     eax, eax
0x410349  push    eax; Reserved
0x41034a  push    eax; LineNo
0x41034b  push    eax; FileName
0x41034c  push    eax; FunctionName
0x41034d  push    eax; Expression
0x41034e  call    __invoke_watson
```
