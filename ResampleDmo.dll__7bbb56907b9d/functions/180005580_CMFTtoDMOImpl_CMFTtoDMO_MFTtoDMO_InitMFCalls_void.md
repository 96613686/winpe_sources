# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(void)

- ea: `0x180005580`
- end: `0x180005609`
- name: `?MFTtoDMO_InitMFCalls@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJXZ`
- size: `137`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180005110`
- `0x180005200`
- `0x180005440`
- `0x18006b4c0`

## callees

- `0x180005580`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800055cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800055eb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800055eb`

## string_xrefs

- `0x1800055a7`: `MFCreateMediaTypeFromRepresentation`
- `0x1800055c4`: `MFCreateLegacyMediaBufferOnMFMediaBuffer`
- `0x1800055de`: `MFPLAT.DLL`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_InitMFCalls(__int64 a1)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  FARPROC v5; // rax

  if ( *(_QWORD *)(a1 + 16) )
    return 0;
  Library = *(HMODULE *)(a1 + 8);
  if ( Library != (HMODULE)-1LL )
  {
    if ( Library || (Library = LoadLibraryExA("MFPLAT.DLL", 0, 0x800u), (*(_QWORD *)(a1 + 8) = Library) != 0) )
    {
      ProcAddress = GetProcAddress(Library, "MFCreateMediaTypeFromRepresentation");
      *(_QWORD *)(a1 + 16) = ProcAddress;
      if ( ProcAddress )
      {
        v5 = GetProcAddress(*(HMODULE *)(a1 + 8), "MFCreateLegacyMediaBufferOnMFMediaBuffer");
        *(_QWORD *)(a1 + 24) = v5;
        if ( v5 )
          return 0;
      }
    }
    *(_QWORD *)(a1 + 8) = -1;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180005580  push    rbx
0x180005582  sub     rsp, 20h
0x180005586  cmp     qword ptr [rcx+10h], 0
0x18000558b  mov     rbx, rcx
0x18000558e  jz      short loc_180005598
0x180005590  xor     eax, eax
0x180005592  add     rsp, 20h
0x180005596  pop     rbx
0x180005597  retn
0x180005598  mov     rax, [rcx+8]
0x18000559c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800055a0  jz      short loc_180005602
0x1800055a2  test    rax, rax
0x1800055a5  jz      short loc_1800055DC
0x1800055a7  lea     rdx, ProcName; "MFCreateMediaTypeFromRepresentation"
0x1800055ae  mov     rcx, rax; hModule
0x1800055b1  call    cs:__imp_GetProcAddress
0x1800055b7  mov     [rbx+10h], rax
0x1800055bb  test    rax, rax
0x1800055be  jz      short loc_1800055FA
0x1800055c0  mov     rcx, [rbx+8]; hModule
0x1800055c4  lea     rdx, aMfcreatelegacy; "MFCreateLegacyMediaBufferOnMFMediaBuffe"...
0x1800055cb  call    cs:__imp_GetProcAddress
0x1800055d1  mov     [rbx+18h], rax
0x1800055d5  test    rax, rax
0x1800055d8  jnz     short loc_180005590
0x1800055da  jmp     short loc_1800055FA
0x1800055dc  xor     edx, edx; hFile
0x1800055de  lea     rcx, LibFileName; "MFPLAT.DLL"
0x1800055e5  mov     r8d, 800h; dwFlags
0x1800055eb  call    cs:__imp_LoadLibraryExA
0x1800055f1  mov     [rbx+8], rax
0x1800055f5  test    rax, rax
0x1800055f8  jnz     short loc_1800055A7
0x1800055fa  mov     qword ptr [rbx+8], 0FFFFFFFFFFFFFFFFh
0x180005602  mov     eax, 80004005h
0x180005607  jmp     short loc_180005592
```
