# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180028400`
- end: `0x180028518`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002c99c`
- `0x180032060`

## callees

- `0x180028400`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002848c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800284b6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180028440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002848c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800284b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028428`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028474`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028428`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180028474`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800284e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800284ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800284fc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800284e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800284ee`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800284fc`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002849e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002849e`

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
0x180028400  mov     [rsp+arg_0], rbx
0x180028405  mov     [rsp+arg_10], rbp
0x18002840a  push    rsi
0x18002840b  push    rdi
0x18002840c  push    r14
0x18002840e  sub     rsp, 20h
0x180028412  mov     r14d, ecx
0x180028415  mov     edi, 800h
0x18002841a  mov     r8d, edi; dwFlags
0x18002841d  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x180028424  xor     edx, edx; hFile
0x180028426  xor     ebx, ebx
0x180028428  call    cs:__imp_LoadLibraryExW
0x18002842e  mov     rsi, rax
0x180028431  test    rax, rax
0x180028434  jz      short loc_180028461
0x180028436  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x18002843d  mov     rcx, rax; hModule
0x180028440  call    cs:__imp_GetProcAddress
0x180028446  test    rax, rax
0x180028449  jz      short loc_180028461
0x18002844b  mov     ecx, r14d
0x18002844e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028453  test    eax, eax
0x180028455  js      short loc_180028461
0x180028457  xor     edi, edi
0x180028459  test    eax, eax
0x18002845b  setz    bpl
0x18002845f  jmp     short loc_1800284DD
0x180028461  mov     r8d, edi; dwFlags
0x180028464  mov     [rsp+38h+arg_8], ebx
0x180028468  xor     edx, edx; hFile
0x18002846a  lea     rcx, aAepic; "Aepic"
0x180028471  xor     bpl, bpl
0x180028474  call    cs:__imp_LoadLibraryExW
0x18002847a  mov     rdi, rax
0x18002847d  test    rax, rax
0x180028480  jz      short loc_180028497
0x180028482  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180028489  mov     rcx, rax; hModule
0x18002848c  call    cs:__imp_GetProcAddress
0x180028492  test    rax, rax
0x180028495  jnz     short loc_1800284C1
0x180028497  lea     rcx, aDevinv; "Devinv"
0x18002849e  call    cs:__imp_LoadLibraryW
0x1800284a4  mov     rbx, rax
0x1800284a7  test    rax, rax
0x1800284aa  jz      short loc_1800284D8
0x1800284ac  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800284b3  mov     rcx, rax; hModule
0x1800284b6  call    cs:__imp_GetProcAddress
0x1800284bc  test    rax, rax
0x1800284bf  jz      short loc_1800284D8
0x1800284c1  lea     rcx, [rsp+38h+arg_8]
0x1800284c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800284cb  test    eax, eax
0x1800284cd  js      short loc_1800284D8
0x1800284cf  cmp     r14d, [rsp+38h+arg_8]
0x1800284d4  setbe   bpl
0x1800284d8  test    rsi, rsi
0x1800284db  jz      short loc_1800284E6
0x1800284dd  mov     rcx, rsi; hLibModule
0x1800284e0  call    cs:__imp_FreeLibrary
0x1800284e6  test    rdi, rdi
0x1800284e9  jz      short loc_1800284F4
0x1800284eb  mov     rcx, rdi; hLibModule
0x1800284ee  call    cs:__imp_FreeLibrary
0x1800284f4  test    rbx, rbx
0x1800284f7  jz      short loc_180028502
0x1800284f9  mov     rcx, rbx; hLibModule
0x1800284fc  call    cs:__imp_FreeLibrary
0x180028502  mov     rbx, [rsp+38h+arg_0]
0x180028507  mov     al, bpl
0x18002850a  mov     rbp, [rsp+38h+arg_10]
0x18002850f  add     rsp, 20h
0x180028513  pop     r14
0x180028515  pop     rdi
0x180028516  pop     rsi
0x180028517  retn
```
