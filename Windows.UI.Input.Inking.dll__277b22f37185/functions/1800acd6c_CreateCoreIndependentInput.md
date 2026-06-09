# CreateCoreIndependentInput

- ea: `0x1800acd6c`
- end: `0x1800acdfe`
- name: `CreateCoreIndependentInput`
- size: `146`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800abdb4`

## callees

- `0x1800acd6c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800acda4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800acda4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acdb7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800acdb7`

## string_xrefs

- `0x1800acd96`: `windows.ui.dll`

## pseudocode

```c
__int64 __fastcall CreateCoreIndependentInput(unsigned int a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v7; // ebx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18015C000;
  *a4 = 0;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, GUID *, _QWORD *))ProcAddress)(
             0,
             a1,
             0,
             &GUID_9f488807_4580_4be8_be68_92a9311713bb,
             a4);
  v7 = -2147467259;
  Library = LoadLibraryExW(L"windows.ui.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x640);
    qword_18015C000 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_18015C000;
  }
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD, _QWORD, _QWORD, GUID *, _QWORD *))ProcAddress)(
             0,
             a1,
             0,
             &GUID_9f488807_4580_4be8_be68_92a9311713bb,
             a4);
  return v7;
}

```

## disassembly

```asm
0x1800acd6c  mov     [rsp+arg_0], rbx
0x1800acd71  mov     [rsp+arg_8], rsi
0x1800acd76  push    rdi
0x1800acd77  sub     rsp, 30h
0x1800acd7b  mov     rax, cs:qword_18015C000
0x1800acd82  mov     rdi, r9
0x1800acd85  mov     qword ptr [r9], 0
0x1800acd8c  mov     esi, ecx
0x1800acd8e  test    rax, rax
0x1800acd91  jnz     short loc_1800ACDD2
0x1800acd93  xor     r8d, r8d; dwFlags
0x1800acd96  lea     rcx, LibFileName; "windows.ui.dll"
0x1800acd9d  xor     edx, edx; hFile
0x1800acd9f  mov     ebx, 80004005h
0x1800acda4  call    cs:__imp_LoadLibraryExW
0x1800acdaa  test    rax, rax
0x1800acdad  jz      short loc_1800ACDC6
0x1800acdaf  mov     edx, 640h; lpProcName
0x1800acdb4  mov     rcx, rax; hModule
0x1800acdb7  call    cs:__imp_GetProcAddress
0x1800acdbd  mov     cs:qword_18015C000, rax
0x1800acdc4  jmp     short loc_1800ACDCD
0x1800acdc6  mov     rax, cs:qword_18015C000
0x1800acdcd  test    rax, rax
0x1800acdd0  jz      short loc_1800ACDEC
0x1800acdd2  lea     r9, _GUID_9f488807_4580_4be8_be68_92a9311713bb
0x1800acdd9  mov     [rsp+38h+var_18], rdi
0x1800acdde  xor     r8d, r8d
0x1800acde1  mov     edx, esi
0x1800acde3  xor     ecx, ecx
0x1800acde5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdea  mov     ebx, eax
0x1800acdec  mov     rsi, [rsp+38h+arg_8]
0x1800acdf1  mov     eax, ebx
0x1800acdf3  mov     rbx, [rsp+38h+arg_0]
0x1800acdf8  add     rsp, 30h
0x1800acdfc  pop     rdi
0x1800acdfd  retn
```
