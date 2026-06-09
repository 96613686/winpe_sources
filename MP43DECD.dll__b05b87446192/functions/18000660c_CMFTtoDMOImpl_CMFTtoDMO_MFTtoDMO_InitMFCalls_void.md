# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x18000660c`
- end: `0x1800066a4`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `152`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005570`
- `0x180005680`
- `0x1800058d0`
- `0x1800059e0`
- `0x180005cc0`
- `0x180006020`

## callees

- `0x18000660c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000667a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006660`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000667a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180006647`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180006647`

## string_xrefs

- `0x18000663a`: `MFPLAT.DLL`
- `0x180006656`: `MFCreateMediaTypeFromRepresentation`
- `0x180006673`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(__int64 a1)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  v1 = 0;
  if ( !*(_QWORD *)(a1 + 16) )
  {
    Library = *(HMODULE *)(a1 + 8);
    if ( Library == (HMODULE)-1LL )
      return (unsigned int)-2147467259;
    if ( !Library && (Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u), (*(_QWORD *)(a1 + 8) = Library) == 0)
      || (ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation"),
          (*(_QWORD *)(a1 + 16) = ProcAddress) == 0)
      || (v5 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer"),
          (*(_QWORD *)(a1 + 24) = v5) == 0) )
    {
      *(_QWORD *)(a1 + 8) = -1;
      return (unsigned int)-2147467259;
    }
  }
  return v1;
}

```

## disassembly

```asm
0x18000660c  mov     [rsp+arg_0], rbx
0x180006611  mov     [rsp+arg_8], rsi
0x180006616  push    rdi
0x180006617  sub     rsp, 20h
0x18000661b  xor     ebx, ebx
0x18000661d  mov     rdi, rcx
0x180006620  cmp     [rcx+10h], rbx
0x180006624  jnz     short loc_180006692
0x180006626  mov     rax, [rcx+8]
0x18000662a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000662e  cmp     rax, rsi
0x180006631  jz      short loc_18000668D
0x180006633  test    rax, rax
0x180006636  jnz     short loc_180006656
0x180006638  xor     edx, edx; hFile
0x18000663a  lea     rcx, LibFileName; "MFPLAT.DLL"
0x180006641  mov     r8d, 800h; dwFlags
0x180006647  call    cs:__imp_LoadLibraryExA
0x18000664d  mov     [rdi+8], rax
0x180006651  test    rax, rax
0x180006654  jz      short loc_180006689
0x180006656  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x18000665d  mov     rcx, rax; hModule
0x180006660  call    cs:__imp_GetProcAddress
0x180006666  mov     [rdi+10h], rax
0x18000666a  test    rax, rax
0x18000666d  jz      short loc_180006689
0x18000666f  mov     rcx, [rdi+8]; hModule
0x180006673  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x18000667a  call    cs:__imp_GetProcAddress
0x180006680  mov     [rdi+18h], rax
0x180006684  test    rax, rax
0x180006687  jnz     short loc_180006692
0x180006689  mov     [rdi+8], rsi
0x18000668d  mov     ebx, 80004005h
0x180006692  mov     rsi, [rsp+28h+arg_8]
0x180006697  mov     eax, ebx
0x180006699  mov     rbx, [rsp+28h+arg_0]
0x18000669e  add     rsp, 20h
0x1800066a2  pop     rdi
0x1800066a3  retn
```
