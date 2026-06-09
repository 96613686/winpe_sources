# SilentProcessExitMain(int,wchar_t const * * const)

- ea: `0x14000b398`
- end: `0x14000b441`
- name: `?SilentProcessExitMain@@YAHHQEAPEB_W@Z`
- size: `169`
- prototype: `__int64 __fastcall(unsigned int, const wchar_t **const)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x14000ddb8`

## callees

- `0x14000b398`
- `0x14000bee0`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000b422`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000b422`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b3ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b3ef`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000b3c7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000b3c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b400`

## string_xrefs

- `0x14000b3c0`: `werui.dll`

## pseudocode

```c
__int64 __fastcall SilentProcessExitMain(unsigned int a1, const wchar_t **const a2)
{
  HMODULE Library; // rax
  HMODULE v5; // rbx
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  DWORD LastError; // eax

  UtilCheckDebugWait(L"SilentProcessExit");
  Library = LoadLibraryExW(L"werui.dll", 0, 0x800u);
  v5 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "WerUIReportSilentProcessExit");
    if ( ProcAddress )
      LastError = ((__int64 (__fastcall *)(_QWORD, const wchar_t **const))ProcAddress)(a1, a2);
    else
      LastError = GetLastError();
    v6 = LastError;
  }
  else
  {
    v6 = 50;
  }
  if ( v5 )
    FreeLibrary(v5);
  return v6;
}

```

## disassembly

```asm
0x14000b398  mov     [rsp+arg_0], rbx
0x14000b39d  mov     [rsp+arg_8], rsi
0x14000b3a2  push    rdi
0x14000b3a3  sub     rsp, 20h
0x14000b3a7  mov     rdi, rdx
0x14000b3aa  mov     esi, ecx
0x14000b3ac  lea     rcx, aSilentprocesse; "SilentProcessExit"
0x14000b3b3  call    ?UtilCheckDebugWait@@YAXPEB_W@Z; UtilCheckDebugWait(wchar_t const *)
0x14000b3b8  xor     edx, edx; hFile
0x14000b3ba  mov     r8d, 800h; dwFlags
0x14000b3c0  lea     rcx, LibFileName; "werui.dll"
0x14000b3c7  call    cs:__imp_LoadLibraryExW
0x14000b3ce  nop     dword ptr [rax+rax+00h]
0x14000b3d3  mov     rbx, rax
0x14000b3d6  mov     [rsp+28h+arg_10], rax
0x14000b3db  test    rax, rax
0x14000b3de  jnz     short loc_14000B3E5
0x14000b3e0  lea     edi, [rax+32h]
0x14000b3e3  jmp     short loc_14000B41A
0x14000b3e5  lea     rdx, aWeruireportsil; "WerUIReportSilentProcessExit"
0x14000b3ec  mov     rcx, rbx; hModule
0x14000b3ef  call    cs:__imp_GetProcAddress
0x14000b3f6  nop     dword ptr [rax+rax+00h]
0x14000b3fb  test    rax, rax
0x14000b3fe  jnz     short loc_14000B40E
0x14000b400  call    cs:__imp_GetLastError
0x14000b407  nop     dword ptr [rax+rax+00h]
0x14000b40c  jmp     short loc_14000B418
0x14000b40e  mov     rdx, rdi
0x14000b411  mov     ecx, esi
0x14000b413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b418  mov     edi, eax
0x14000b41a  test    rbx, rbx
0x14000b41d  jz      short loc_14000B42E
0x14000b41f  mov     rcx, rbx; hLibModule
0x14000b422  call    cs:__imp_FreeLibrary
0x14000b429  nop     dword ptr [rax+rax+00h]
0x14000b42e  mov     eax, edi
0x14000b430  mov     rbx, [rsp+28h+arg_0]
0x14000b435  mov     rsi, [rsp+28h+arg_8]
0x14000b43a  add     rsp, 20h
0x14000b43e  pop     rdi
0x14000b43f  retn
```
