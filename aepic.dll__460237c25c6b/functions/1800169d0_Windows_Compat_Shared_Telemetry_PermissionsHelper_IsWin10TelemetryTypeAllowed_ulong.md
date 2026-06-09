# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x1800169d0`
- end: `0x180016ae8`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016954`
- `0x180039e64`

## callees

- `0x1800169d0`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016ab0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016abe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016acc`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016ab0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016abe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180016acc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800169f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016a44`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800169f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180016a44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a86`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016a86`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180016a6e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180016a6e`

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
0x1800169d0  mov     [rsp+arg_0], rbx
0x1800169d5  mov     [rsp+arg_10], rbp
0x1800169da  push    rsi
0x1800169db  push    rdi
0x1800169dc  push    r14
0x1800169de  sub     rsp, 20h
0x1800169e2  mov     r14d, ecx
0x1800169e5  mov     edi, 800h
0x1800169ea  mov     r8d, edi; dwFlags
0x1800169ed  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x1800169f4  xor     edx, edx; hFile
0x1800169f6  xor     ebx, ebx
0x1800169f8  call    cs:__imp_LoadLibraryExW
0x1800169fe  mov     rsi, rax
0x180016a01  test    rax, rax
0x180016a04  jz      short loc_180016A31
0x180016a06  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180016a0d  mov     rcx, rax; hModule
0x180016a10  call    cs:__imp_GetProcAddress
0x180016a16  test    rax, rax
0x180016a19  jz      short loc_180016A31
0x180016a1b  mov     ecx, r14d
0x180016a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a23  test    eax, eax
0x180016a25  js      short loc_180016A31
0x180016a27  xor     edi, edi
0x180016a29  test    eax, eax
0x180016a2b  setz    bpl
0x180016a2f  jmp     short loc_180016AAD
0x180016a31  mov     r8d, edi; dwFlags
0x180016a34  mov     [rsp+38h+arg_8], ebx
0x180016a38  xor     edx, edx; hFile
0x180016a3a  lea     rcx, aAepic; "Aepic"
0x180016a41  xor     bpl, bpl
0x180016a44  call    cs:__imp_LoadLibraryExW
0x180016a4a  mov     rdi, rax
0x180016a4d  test    rax, rax
0x180016a50  jz      short loc_180016A67
0x180016a52  lea     rdx, aGetprivacyleve_0; "GetPrivacyLevel"
0x180016a59  mov     rcx, rax; hModule
0x180016a5c  call    cs:__imp_GetProcAddress
0x180016a62  test    rax, rax
0x180016a65  jnz     short loc_180016A91
0x180016a67  lea     rcx, aDevinv; "Devinv"
0x180016a6e  call    cs:__imp_LoadLibraryW
0x180016a74  mov     rbx, rax
0x180016a77  test    rax, rax
0x180016a7a  jz      short loc_180016AA8
0x180016a7c  lea     rdx, aGetprivacyleve_0; "GetPrivacyLevel"
0x180016a83  mov     rcx, rax; hModule
0x180016a86  call    cs:__imp_GetProcAddress
0x180016a8c  test    rax, rax
0x180016a8f  jz      short loc_180016AA8
0x180016a91  lea     rcx, [rsp+38h+arg_8]
0x180016a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a9b  test    eax, eax
0x180016a9d  js      short loc_180016AA8
0x180016a9f  cmp     r14d, [rsp+38h+arg_8]
0x180016aa4  setbe   bpl
0x180016aa8  test    rsi, rsi
0x180016aab  jz      short loc_180016AB6
0x180016aad  mov     rcx, rsi; hLibModule
0x180016ab0  call    cs:__imp_FreeLibrary
0x180016ab6  test    rdi, rdi
0x180016ab9  jz      short loc_180016AC4
0x180016abb  mov     rcx, rdi; hLibModule
0x180016abe  call    cs:__imp_FreeLibrary
0x180016ac4  test    rbx, rbx
0x180016ac7  jz      short loc_180016AD2
0x180016ac9  mov     rcx, rbx; hLibModule
0x180016acc  call    cs:__imp_FreeLibrary
0x180016ad2  mov     rbx, [rsp+38h+arg_0]
0x180016ad7  mov     al, bpl
0x180016ada  mov     rbp, [rsp+38h+arg_10]
0x180016adf  add     rsp, 20h
0x180016ae3  pop     r14
0x180016ae5  pop     rdi
0x180016ae6  pop     rsi
0x180016ae7  retn
```
