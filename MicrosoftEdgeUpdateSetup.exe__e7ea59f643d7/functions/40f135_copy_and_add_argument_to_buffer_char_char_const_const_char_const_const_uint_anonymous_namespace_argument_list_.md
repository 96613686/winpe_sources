# copy_and_add_argument_to_buffer<char>(char const * const,char const * const,uint,`anonymous namespace'::argument_list<char> &)

- ea: `0x40f135`
- end: `0x40f1e5`
- name: `??$copy_and_add_argument_to_buffer@D@@YAHQBD0IAAV?$argument_list@D@?A0x5f5c8891@@@Z`
- size: `176`
- prototype: `rsize_t __cdecl(char *, char *Source, rsize_t MaxCount, int)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x40ef46`
- `0x40f1e6`

## callees

- `0x40ec36`
- `0x40ecf6`
- `0x40ed53`
- `0x40f135`
- `0x40f530`
- `0x413841`

## pseudocode

```c
rsize_t __cdecl copy_and_add_argument_to_buffer<char>(char *a1, char *Source, rsize_t MaxCount, int a4)
{
  rsize_t v4; // ecx
  size_t v6; // ebx
  char *v7; // eax
  char *v8; // esi
  rsize_t v9; // esi
  rsize_t v10; // [esp+0h] [ebp-4h]
  rsize_t v11; // [esp+0h] [ebp-4h]

  v4 = strlen(a1) + 1;
  v10 = v4;
  if ( v4 > ~MaxCount )
    return 12;
  v6 = v4 + MaxCount + 1;
  v7 = (char *)_calloc_base(v6, 1u);
  v8 = v7;
  if ( MaxCount && strncpy_s(v7, v6, Source, MaxCount) || strncpy_s(&v8[MaxCount], v6 - MaxCount, a1, v10) )
    _invoke_watson(0, 0, 0, 0, 0);
  v11 = unknown_libname_28(a4);
  if ( v11 )
  {
    _free_base(v8);
    v9 = v11;
  }
  else
  {
    **(_DWORD **)(a4 + 4) = v8;
    v9 = 0;
    *(_DWORD *)(a4 + 4) += 4;
  }
  _free_base(0);
  return v9;
}

```

## disassembly

```asm
0x40f135  mov     edi, edi
0x40f137  push    ebp
0x40f138  mov     ebp, esp
0x40f13a  push    ecx
0x40f13b  mov     ecx, [ebp+arg_0]
0x40f13e  lea     edx, [ecx+1]
0x40f141  mov     al, [ecx]
0x40f143  inc     ecx
0x40f144  test    al, al
0x40f146  jnz     short loc_40F141
0x40f148  push    edi
0x40f149  mov     edi, [ebp+MaxCount]
0x40f14c  sub     ecx, edx
0x40f14e  mov     eax, edi
0x40f150  inc     ecx
0x40f151  not     eax
0x40f153  mov     [ebp+var_4], ecx
0x40f156  cmp     ecx, eax
0x40f158  jbe     short loc_40F160
0x40f15a  push    0Ch
0x40f15c  pop     eax
0x40f15d  pop     edi
0x40f15e  leave
0x40f15f  retn
0x40f160  push    ebx
0x40f161  push    esi
0x40f162  lea     ebx, [edi+1]
0x40f165  add     ebx, ecx
0x40f167  push    1; Size
0x40f169  push    ebx; Count
0x40f16a  call    __calloc_base
0x40f16f  mov     esi, eax
0x40f171  pop     ecx
0x40f172  pop     ecx
0x40f173  test    edi, edi
0x40f175  jz      short loc_40F189
0x40f177  push    edi; MaxCount
0x40f178  push    [ebp+Source]; Source
0x40f17b  push    ebx; SizeInBytes
0x40f17c  push    esi; Destination
0x40f17d  call    _strncpy_s
0x40f182  add     esp, 10h
0x40f185  test    eax, eax
0x40f187  jnz     short loc_40F1D9
0x40f189  push    [ebp+var_4]; MaxCount
0x40f18c  sub     ebx, edi
0x40f18e  lea     eax, [esi+edi]
0x40f191  push    [ebp+arg_0]; Source
0x40f194  push    ebx; SizeInBytes
0x40f195  push    eax; Destination
0x40f196  call    _strncpy_s
0x40f19b  add     esp, 10h
0x40f19e  test    eax, eax
0x40f1a0  jnz     short loc_40F1D9
0x40f1a2  mov     ebx, [ebp+arg_C]
0x40f1a5  mov     ecx, ebx
0x40f1a7  call    unknown_libname_28; Microsoft VisualC universal runtime
0x40f1ac  xor     edi, edi
0x40f1ae  mov     [ebp+var_4], eax
0x40f1b1  test    eax, eax
0x40f1b3  jz      short loc_40F1C1
0x40f1b5  push    esi; Block
0x40f1b6  call    __free_base
0x40f1bb  mov     esi, [ebp+var_4]
0x40f1be  pop     ecx
0x40f1bf  jmp     short loc_40F1CC
0x40f1c1  mov     eax, [ebx+4]
0x40f1c4  mov     [eax], esi
0x40f1c6  mov     esi, edi
0x40f1c8  add     dword ptr [ebx+4], 4
0x40f1cc  push    edi; Block
0x40f1cd  call    __free_base
0x40f1d2  pop     ecx
0x40f1d3  mov     eax, esi
0x40f1d5  pop     esi
0x40f1d6  pop     ebx
0x40f1d7  jmp     short loc_40F15D
0x40f1d9  xor     edi, edi
0x40f1db  push    edi; Reserved
0x40f1dc  push    edi; LineNo
0x40f1dd  push    edi; FileName
0x40f1de  push    edi; FunctionName
0x40f1df  push    edi; Expression
0x40f1e0  call    __invoke_watson
```
