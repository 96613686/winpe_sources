# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x18000b364`
- end: `0x18000b400`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `156`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000a900`
- `0x18000aa00`
- `0x18000aaf0`
- `0x18000abf0`
- `0x18000ae90`
- `0x18000f640`

## callees

- `0x18000b364`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3ca`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000b3b1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18000b3b1`

## string_xrefs

- `0x18000b3c0`: `MFCreateMediaTypeFromRepresentation`
- `0x18000b3a4`: `MFPLAT.DLL`
- `0x18000b3e8`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`

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
0x18000b364  mov     [rsp+arg_0], rbx
0x18000b369  mov     [rsp+arg_8], rsi
0x18000b36e  push    rdi
0x18000b36f  sub     rsp, 20h
0x18000b373  xor     ebx, ebx
0x18000b375  mov     rdi, rcx
0x18000b378  cmp     [rcx+10h], rbx
0x18000b37c  jz      short loc_18000B390
0x18000b37e  mov     rsi, [rsp+28h+arg_8]
0x18000b383  mov     eax, ebx
0x18000b385  mov     rbx, [rsp+28h+arg_0]
0x18000b38a  add     rsp, 20h
0x18000b38e  pop     rdi
0x18000b38f  retn
0x18000b390  mov     rax, [rcx+8]
0x18000b394  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000b398  cmp     rax, rsi
0x18000b39b  jz      short loc_18000B3DD
0x18000b39d  test    rax, rax
0x18000b3a0  jnz     short loc_18000B3C0
0x18000b3a2  xor     edx, edx; hFile
0x18000b3a4  lea     rcx, LibFileName; "MFPLAT.DLL"
0x18000b3ab  mov     r8d, 800h; dwFlags
0x18000b3b1  call    cs:__imp_LoadLibraryExA
0x18000b3b7  mov     [rdi+8], rax
0x18000b3bb  test    rax, rax
0x18000b3be  jz      short loc_18000B3D9
0x18000b3c0  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x18000b3c7  mov     rcx, rax; hModule
0x18000b3ca  call    cs:__imp_GetProcAddress
0x18000b3d0  mov     [rdi+10h], rax
0x18000b3d4  test    rax, rax
0x18000b3d7  jnz     short loc_18000B3E4
0x18000b3d9  mov     [rdi+8], rsi
0x18000b3dd  mov     ebx, 80004005h
0x18000b3e2  jmp     short loc_18000B37E
0x18000b3e4  mov     rcx, [rdi+8]; hModule
0x18000b3e8  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x18000b3ef  call    cs:__imp_GetProcAddress
0x18000b3f5  mov     [rdi+18h], rax
0x18000b3f9  test    rax, rax
0x18000b3fc  jnz     short loc_18000B37E
0x18000b3fe  jmp     short loc_18000B3D9
```
