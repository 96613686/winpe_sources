# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x1800066cc`
- end: `0x180006764`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `152`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005630`
- `0x180005740`
- `0x180005990`
- `0x180005aa0`
- `0x180005d80`
- `0x1800060e0`

## callees

- `0x1800066cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006720`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000673a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006720`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000673a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180006707`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180006707`

## string_xrefs

- `0x1800066fa`: `MFPLAT.DLL`
- `0x180006716`: `MFCreateMediaTypeFromRepresentation`
- `0x180006733`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`

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
0x1800066cc  mov     [rsp+arg_0], rbx
0x1800066d1  mov     [rsp+arg_8], rsi
0x1800066d6  push    rdi
0x1800066d7  sub     rsp, 20h
0x1800066db  xor     ebx, ebx
0x1800066dd  mov     rdi, rcx
0x1800066e0  cmp     [rcx+10h], rbx
0x1800066e4  jnz     short loc_180006752
0x1800066e6  mov     rax, [rcx+8]
0x1800066ea  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800066ee  cmp     rax, rsi
0x1800066f1  jz      short loc_18000674D
0x1800066f3  test    rax, rax
0x1800066f6  jnz     short loc_180006716
0x1800066f8  xor     edx, edx; hFile
0x1800066fa  lea     rcx, LibFileName; "MFPLAT.DLL"
0x180006701  mov     r8d, 800h; dwFlags
0x180006707  call    cs:__imp_LoadLibraryExA
0x18000670d  mov     [rdi+8], rax
0x180006711  test    rax, rax
0x180006714  jz      short loc_180006749
0x180006716  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x18000671d  mov     rcx, rax; hModule
0x180006720  call    cs:__imp_GetProcAddress
0x180006726  mov     [rdi+10h], rax
0x18000672a  test    rax, rax
0x18000672d  jz      short loc_180006749
0x18000672f  mov     rcx, [rdi+8]; hModule
0x180006733  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x18000673a  call    cs:__imp_GetProcAddress
0x180006740  mov     [rdi+18h], rax
0x180006744  test    rax, rax
0x180006747  jnz     short loc_180006752
0x180006749  mov     [rdi+8], rsi
0x18000674d  mov     ebx, 80004005h
0x180006752  mov     rsi, [rsp+28h+arg_8]
0x180006757  mov     eax, ebx
0x180006759  mov     rbx, [rsp+28h+arg_0]
0x18000675e  add     rsp, 20h
0x180006762  pop     rdi
0x180006763  retn
```
