# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x140018c98`
- end: `0x140018db0`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400184cc`

## callees

- `0x140018c98`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018cd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018d24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018d4e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018cd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018d24`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140018d4e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018cc0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018d0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018cc0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140018d0c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018d78`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018d86`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018d94`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018d78`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018d86`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018d94`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140018d36`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140018d36`

## pseudocode

```c
bool __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(unsigned int a1)
{
  HMODULE v2; // rbx
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  int v6; // eax
  HMODULE v7; // rdi
  bool v8; // bp
  HMODULE v9; // rax
  FARPROC v10; // rax
  HMODULE LibraryW; // rax
  unsigned int v13; // [rsp+48h] [rbp+10h] BYREF

  v2 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(_QWORD))ProcAddress)(a1);
      if ( v6 >= 0 )
      {
        v7 = 0;
        v8 = v6 == 0;
LABEL_12:
        FreeLibrary(v4);
        goto LABEL_13;
      }
    }
  }
  v13 = 0;
  v8 = 0;
  v9 = LoadLibraryExW(L"Aepic", 0, 0x800u);
  v7 = v9;
  if ( v9 && (v10 = GetProcAddress(v9, "GetPrivacyLevel")) != 0
    || (LibraryW = LoadLibraryW(L"Devinv"), (v2 = LibraryW) != 0)
    && (v10 = GetProcAddress(LibraryW, "GetPrivacyLevel")) != 0 )
  {
    if ( ((int (__fastcall *)(unsigned int *))v10)(&v13) >= 0 )
      v8 = a1 <= v13;
  }
  if ( v4 )
    goto LABEL_12;
LABEL_13:
  if ( v7 )
    FreeLibrary(v7);
  if ( v2 )
    FreeLibrary(v2);
  return v8;
}

```

## disassembly

```asm
0x140018c98  mov     [rsp+arg_0], rbx
0x140018c9d  mov     [rsp+arg_10], rbp
0x140018ca2  push    rsi
0x140018ca3  push    rdi
0x140018ca4  push    r14
0x140018ca6  sub     rsp, 20h
0x140018caa  mov     r14d, ecx
0x140018cad  mov     edi, 800h
0x140018cb2  mov     r8d, edi; dwFlags
0x140018cb5  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x140018cbc  xor     edx, edx; hFile
0x140018cbe  xor     ebx, ebx
0x140018cc0  call    cs:__imp_LoadLibraryExW
0x140018cc6  mov     rsi, rax
0x140018cc9  test    rax, rax
0x140018ccc  jz      short loc_140018CF9
0x140018cce  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x140018cd5  mov     rcx, rax; hModule
0x140018cd8  call    cs:__imp_GetProcAddress
0x140018cde  test    rax, rax
0x140018ce1  jz      short loc_140018CF9
0x140018ce3  mov     ecx, r14d
0x140018ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018ceb  test    eax, eax
0x140018ced  js      short loc_140018CF9
0x140018cef  xor     edi, edi
0x140018cf1  test    eax, eax
0x140018cf3  setz    bpl
0x140018cf7  jmp     short loc_140018D75
0x140018cf9  mov     r8d, edi; dwFlags
0x140018cfc  mov     [rsp+38h+arg_8], ebx
0x140018d00  xor     edx, edx; hFile
0x140018d02  lea     rcx, aAepic; "Aepic"
0x140018d09  xor     bpl, bpl
0x140018d0c  call    cs:__imp_LoadLibraryExW
0x140018d12  mov     rdi, rax
0x140018d15  test    rax, rax
0x140018d18  jz      short loc_140018D2F
0x140018d1a  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x140018d21  mov     rcx, rax; hModule
0x140018d24  call    cs:__imp_GetProcAddress
0x140018d2a  test    rax, rax
0x140018d2d  jnz     short loc_140018D59
0x140018d2f  lea     rcx, aDevinv; "Devinv"
0x140018d36  call    cs:__imp_LoadLibraryW
0x140018d3c  mov     rbx, rax
0x140018d3f  test    rax, rax
0x140018d42  jz      short loc_140018D70
0x140018d44  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x140018d4b  mov     rcx, rax; hModule
0x140018d4e  call    cs:__imp_GetProcAddress
0x140018d54  test    rax, rax
0x140018d57  jz      short loc_140018D70
0x140018d59  lea     rcx, [rsp+38h+arg_8]
0x140018d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018d63  test    eax, eax
0x140018d65  js      short loc_140018D70
0x140018d67  cmp     r14d, [rsp+38h+arg_8]
0x140018d6c  setbe   bpl
0x140018d70  test    rsi, rsi
0x140018d73  jz      short loc_140018D7E
0x140018d75  mov     rcx, rsi; hLibModule
0x140018d78  call    cs:__imp_FreeLibrary
0x140018d7e  test    rdi, rdi
0x140018d81  jz      short loc_140018D8C
0x140018d83  mov     rcx, rdi; hLibModule
0x140018d86  call    cs:__imp_FreeLibrary
0x140018d8c  test    rbx, rbx
0x140018d8f  jz      short loc_140018D9A
0x140018d91  mov     rcx, rbx; hLibModule
0x140018d94  call    cs:__imp_FreeLibrary
0x140018d9a  mov     rbx, [rsp+38h+arg_0]
0x140018d9f  mov     al, bpl
0x140018da2  mov     rbp, [rsp+38h+arg_10]
0x140018da7  add     rsp, 20h
0x140018dab  pop     r14
0x140018dad  pop     rdi
0x140018dae  pop     rsi
0x140018daf  retn
```
