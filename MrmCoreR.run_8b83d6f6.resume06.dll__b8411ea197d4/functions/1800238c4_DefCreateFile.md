# _DefCreateFile

- ea: `0x1800238c4`
- end: `0x180023966`
- name: `_DefCreateFile`
- size: `162`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18002418c`
- `0x1800795e4`

## callees

- `0x1800238c4`
- `0x18005fdf8`
- `0x1800804a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023925`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023925`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023902`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180023902`

## string_xrefs

- `0x180023953`: `_DefCreateFile`

## pseudocode

```c
__int64 __fastcall DefCreateFile(const WCHAR *a1, __int64 a2, __int64 a3, __int64 a4, int a5, int a6, _QWORD *a7)
{
  const unsigned __int16 *v7; // rdi
  HANDLE FileW; // rax
  signed int LastError; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax

  v7 = a1;
  if ( !a7 )
    return 2147942487LL;
  FileW = CreateFileW(a1, 0x80000000, 5u, 0, 3u, 0, 0);
  *a7 = FileW;
  if ( FileW != (HANDLE)-1LL )
    return 0;
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
  if ( !v7 )
    v7 = &word_1800DEF74;
  v12 = RemovePiiFromString(v7);
  MrtRuntimeMeasure_GenericEventParam1(L"_DefCreateFile", v12, v11);
  return v11;
}

```

## disassembly

```asm
0x1800238c4  mov     rax, rsp
0x1800238c7  mov     [rax+8], rbx
0x1800238cb  push    rdi
0x1800238cc  sub     rsp, 40h
0x1800238d0  mov     rbx, [rsp+48h+arg_30]
0x1800238d8  mov     rdi, rcx
0x1800238db  test    rbx, rbx
0x1800238de  jz      short loc_18002391E
0x1800238e0  mov     qword ptr [rax-18h], 0
0x1800238e8  xor     r9d, r9d; lpSecurityAttributes
0x1800238eb  mov     dword ptr [rax-20h], 0
0x1800238f2  mov     edx, 80000000h; dwDesiredAccess
0x1800238f7  mov     dword ptr [rax-28h], 3
0x1800238fe  lea     r8d, [r9+5]; dwShareMode
0x180023902  call    cs:__imp_CreateFileW
0x180023908  mov     [rbx], rax
0x18002390b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002390f  jz      short loc_180023925
0x180023911  xor     eax, eax
0x180023913  mov     rbx, [rsp+48h+arg_0]
0x180023918  add     rsp, 40h
0x18002391c  pop     rdi
0x18002391d  retn
0x18002391e  mov     eax, 80070057h
0x180023923  jmp     short loc_180023913
0x180023925  call    cs:__imp_GetLastError
0x18002392b  mov     ebx, eax
0x18002392d  test    eax, eax
0x18002392f  jle     short loc_18002393A
0x180023931  movzx   ebx, ax
0x180023934  or      ebx, 80070000h
0x18002393a  lea     rax, word_1800DEF74
0x180023941  test    rdi, rdi
0x180023944  cmovz   rdi, rax
0x180023948  mov     rcx, rdi
0x18002394b  call    RemovePiiFromString
0x180023950  mov     rdx, rax
0x180023953  lea     rcx, aDefcreatefile; "_DefCreateFile"
0x18002395a  mov     r8d, ebx
0x18002395d  call    MrtRuntimeMeasure_GenericEventParam1
0x180023962  mov     eax, ebx
0x180023964  jmp     short loc_180023913
```
