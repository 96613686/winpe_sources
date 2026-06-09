# Cn::Process::NotifyOutOfMemory(unsigned __int64)

- ea: `0x1800a1f68`
- end: `0x1800a1fc9`
- name: `?NotifyOutOfMemory@Process@Cn@@SAX_K@Z`
- size: `97`
- prototype: `void __fastcall __noreturn(unsigned __int64)`
- caller_count: `17`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800056b0`
- `0x1800057e4`
- `0x1800058d4`
- `0x180006e04`
- `0x180011c30`
- `0x180019fa8`
- `0x180028b74`
- `0x18003950c`
- `0x18005ca5c`
- `0x180063570`
- `0x180063738`
- `0x18007d080`
- `0x180083774`
- `0x18008d574`
- `0x1800a235c`
- `0x1800a2900`
- `0x1800ab0a0`

## callees

- `0x18008ae1c`
- `0x1800a1f68`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a1f9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800a1f9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a1fb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800a1fb0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a1f89`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a1f89`

## string_xrefs

- `0x1800a1f92`: `api-ms-win-core-errorhandling-l1-1-3.dll`

## pseudocode

```c
void __fastcall __noreturn Cn::Process::NotifyOutOfMemory(__int64 a1)
{
  HMODULE Library; // rax
  const char16_t *v3; // rcx
  FARPROC ProcAddress; // rax

  if ( Cn::Process::OutOfMemoryHandler )
    Cn::Process::OutOfMemoryHandler();
  OutputDebugStringW(L"Cn::Process::NotifyOutOfMemory().\r\n");
  Library = LoadLibraryExW(L"api-ms-win-core-errorhandling-l1-1-3.dll", 0, 0);
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TerminateProcessOnMemoryExhaustion");
    if ( ProcAddress )
      ((void (__fastcall *)(__int64))ProcAddress)(a1);
  }
  CFlat::Abandonment::Fail(v3);
}

```

## disassembly

```asm
0x1800a1f68  push    rbx
0x1800a1f6a  sub     rsp, 20h
0x1800a1f6e  mov     rax, cs:?OutOfMemoryHandler@Process@Cn@@2P6AX_K@ZEA; void (*Cn::Process::OutOfMemoryHandler)(unsigned __int64)
0x1800a1f75  mov     rbx, rcx
0x1800a1f78  test    rax, rax
0x1800a1f7b  jz      short loc_1800A1F82
0x1800a1f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1f82  lea     rcx, OutputString; "Cn::Process::NotifyOutOfMemory().\r\n"
0x1800a1f89  call    cs:__imp_OutputDebugStringW
0x1800a1f8f  xor     r8d, r8d; dwFlags
0x1800a1f92  lea     rcx, aApiMsWinCoreEr_1; "api-ms-win-core-errorhandling-l1-1-3.dl"...
0x1800a1f99  xor     edx, edx; hFile
0x1800a1f9b  call    cs:__imp_LoadLibraryExW
0x1800a1fa1  test    rax, rax
0x1800a1fa4  jz      short loc_1800A1FC3
0x1800a1fa6  lea     rdx, aTerminateproce; "TerminateProcessOnMemoryExhaustion"
0x1800a1fad  mov     rcx, rax; hModule
0x1800a1fb0  call    cs:__imp_GetProcAddress
0x1800a1fb6  test    rax, rax
0x1800a1fb9  jz      short loc_1800A1FC3
0x1800a1fbb  mov     rcx, rbx
0x1800a1fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1fc3  call    ?Fail@Abandonment@CFlat@@SAXPEB_S@Z; CFlat::Abandonment::Fail(char16_t const *)
```
