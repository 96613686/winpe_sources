# CreateCoreIndependentInput_1

- ea: `0x1800c535c`
- end: `0x1800c53e4`
- name: `CreateCoreIndependentInput_1`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800c0a40`

## callees

- `0x1800c535c`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c538d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c538d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c53a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c53a0`

## string_xrefs

- `0x1800c537f`: `windows.ui.dll`

## pseudocode

```c
__int64 __fastcall CreateCoreIndependentInput_1(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  FARPROC ProcAddress; // rax
  unsigned int v6; // ebx
  HMODULE Library; // rax

  ProcAddress = (FARPROC)qword_18015C010;
  *a4 = 0;
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, GUID *, _QWORD *))ProcAddress)(
             0,
             5,
             0,
             &GUID_9f488807_4580_4be8_be68_92a9311713bb,
             a4);
  v6 = -2147467259;
  Library = LoadLibraryExW(L"windows.ui.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, (LPCSTR)0x640);
    qword_18015C010 = (__int64)ProcAddress;
  }
  else
  {
    ProcAddress = (FARPROC)qword_18015C010;
  }
  if ( ProcAddress )
    return ((unsigned int (__fastcall *)(_QWORD, __int64, _QWORD, GUID *, _QWORD *))ProcAddress)(
             0,
             5,
             0,
             &GUID_9f488807_4580_4be8_be68_92a9311713bb,
             a4);
  return v6;
}

```

## disassembly

```asm
0x1800c535c  mov     [rsp+arg_0], rbx
0x1800c5361  push    rdi
0x1800c5362  sub     rsp, 30h
0x1800c5366  mov     rax, cs:qword_18015C010
0x1800c536d  mov     rdi, r9
0x1800c5370  mov     qword ptr [r9], 0
0x1800c5377  test    rax, rax
0x1800c537a  jnz     short loc_1800C53BB
0x1800c537c  xor     r8d, r8d; dwFlags
0x1800c537f  lea     rcx, LibFileName; "windows.ui.dll"
0x1800c5386  xor     edx, edx; hFile
0x1800c5388  mov     ebx, 80004005h
0x1800c538d  call    cs:__imp_LoadLibraryExW
0x1800c5393  test    rax, rax
0x1800c5396  jz      short loc_1800C53AF
0x1800c5398  mov     edx, 640h; lpProcName
0x1800c539d  mov     rcx, rax; hModule
0x1800c53a0  call    cs:__imp_GetProcAddress
0x1800c53a6  mov     cs:qword_18015C010, rax
0x1800c53ad  jmp     short loc_1800C53B6
0x1800c53af  mov     rax, cs:qword_18015C010
0x1800c53b6  test    rax, rax
0x1800c53b9  jz      short loc_1800C53D7
0x1800c53bb  xor     r8d, r8d
0x1800c53be  mov     [rsp+38h+var_18], rdi
0x1800c53c3  lea     r9, _GUID_9f488807_4580_4be8_be68_92a9311713bb
0x1800c53ca  xor     ecx, ecx
0x1800c53cc  lea     edx, [r8+5]
0x1800c53d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c53d5  mov     ebx, eax
0x1800c53d7  mov     eax, ebx
0x1800c53d9  mov     rbx, [rsp+38h+arg_0]
0x1800c53de  add     rsp, 30h
0x1800c53e2  pop     rdi
0x1800c53e3  retn
```
