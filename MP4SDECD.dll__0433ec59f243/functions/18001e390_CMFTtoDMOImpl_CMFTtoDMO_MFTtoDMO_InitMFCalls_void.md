# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x18001e390`
- end: `0x18001e42a`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `154`
- prototype: `__int64(void)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001da00`
- `0x18001daf0`
- `0x18001dbf0`
- `0x18001dea0`
- `0x18002d190`
- `0x18002d360`

## callees

- `0x18001e390`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001e3dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001e3dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e410`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e3f6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e410`

## string_xrefs

- `0x18001e3d0`: `MFPLAT.DLL`
- `0x18001e3ec`: `MFCreateMediaTypeFromRepresentation`
- `0x18001e409`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(__int64 a1)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v6; // rax

  v1 = 0;
  if ( *(_QWORD *)(a1 + 16) )
    return v1;
  Library = *(HMODULE *)(a1 + 8);
  if ( Library == (HMODULE)-1LL )
    return (unsigned int)-2147467259;
  if ( !Library && (Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u), (*(_QWORD *)(a1 + 8) = Library) == 0)
    || (ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation"),
        (*(_QWORD *)(a1 + 16) = ProcAddress) == 0)
    || (v6 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer"),
        (*(_QWORD *)(a1 + 24) = v6) == 0) )
  {
    *(_QWORD *)(a1 + 8) = -1;
    return (unsigned int)-2147467259;
  }
  return v1;
}

```

## disassembly

```asm
0x18001e390  mov     [rsp+arg_0], rbx
0x18001e395  mov     [rsp+arg_8], rsi
0x18001e39a  push    rdi
0x18001e39b  sub     rsp, 20h
0x18001e39f  xor     ebx, ebx
0x18001e3a1  mov     rdi, rcx
0x18001e3a4  cmp     [rcx+10h], rbx
0x18001e3a8  jz      short loc_18001E3BC
0x18001e3aa  mov     rsi, [rsp+28h+arg_8]
0x18001e3af  mov     eax, ebx
0x18001e3b1  mov     rbx, [rsp+28h+arg_0]
0x18001e3b6  add     rsp, 20h
0x18001e3ba  pop     rdi
0x18001e3bb  retn
0x18001e3bc  mov     rax, [rcx+8]
0x18001e3c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18001e3c4  cmp     rax, rsi
0x18001e3c7  jz      short loc_18001E423
0x18001e3c9  test    rax, rax
0x18001e3cc  jnz     short loc_18001E3EC
0x18001e3ce  xor     edx, edx; hFile
0x18001e3d0  lea     rcx, LibFileName; "MFPLAT.DLL"
0x18001e3d7  mov     r8d, 800h; dwFlags
0x18001e3dd  call    cs:__imp_LoadLibraryExA
0x18001e3e3  mov     [rdi+8], rax
0x18001e3e7  test    rax, rax
0x18001e3ea  jz      short loc_18001E41F
0x18001e3ec  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x18001e3f3  mov     rcx, rax; hModule
0x18001e3f6  call    cs:__imp_GetProcAddress
0x18001e3fc  mov     [rdi+10h], rax
0x18001e400  test    rax, rax
0x18001e403  jz      short loc_18001E41F
0x18001e405  mov     rcx, [rdi+8]; hModule
0x18001e409  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x18001e410  call    cs:__imp_GetProcAddress
0x18001e416  mov     [rdi+18h], rax
0x18001e41a  test    rax, rax
0x18001e41d  jnz     short loc_18001E3AA
0x18001e41f  mov     [rdi+8], rsi
0x18001e423  mov     ebx, 80004005h
0x18001e428  jmp     short loc_18001E3AA
```
