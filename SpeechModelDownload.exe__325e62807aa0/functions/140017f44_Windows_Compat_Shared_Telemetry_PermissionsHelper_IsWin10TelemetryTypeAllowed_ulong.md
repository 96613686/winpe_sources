# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x140017f44`
- end: `0x140018049`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `261`
- prototype: `bool __fastcall(int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140017e4c`

## callees

- `0x140017f44`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001801b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018029`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018037`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14001801b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018029`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140018037`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017f7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017fc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017ff1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017f7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017fc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140017ff1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140017f63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140017faf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140017f63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140017faf`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140017fd9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x140017fd9`

## pseudocode

```c
bool __fastcall Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(int a1)
{
  HMODULE v1; // rbx
  HMODULE Library; // rax
  HMODULE v3; // rsi
  FARPROC ProcAddress; // rax
  int v5; // eax
  HMODULE v6; // rdi
  bool v7; // bp
  HMODULE v8; // rax
  FARPROC v9; // rax
  HMODULE LibraryW; // rax
  int v12; // [rsp+50h] [rbp+8h] BYREF

  v12 = a1;
  v1 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings", 0, 0x800u);
  v3 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v5 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
      if ( v5 >= 0 )
      {
        v6 = 0;
        v7 = v5 == 0;
LABEL_12:
        FreeLibrary(v3);
        goto LABEL_13;
      }
    }
  }
  v12 = 0;
  v7 = 0;
  v8 = LoadLibraryExW(L"Aepic", 0, 0x800u);
  v6 = v8;
  if ( v8 && (v9 = GetProcAddress(v8, "GetPrivacyLevel")) != 0
    || (LibraryW = LoadLibraryW(L"Devinv"), (v1 = LibraryW) != 0)
    && (v9 = GetProcAddress(LibraryW, "GetPrivacyLevel")) != 0 )
  {
    if ( ((int (__fastcall *)(int *))v9)(&v12) >= 0 )
      v7 = v12 != 0;
  }
  if ( v3 )
    goto LABEL_12;
LABEL_13:
  if ( v6 )
    FreeLibrary(v6);
  if ( v1 )
    FreeLibrary(v1);
  return v7;
}

```

## disassembly

```asm
0x140017f44  mov     [rsp+arg_0], ecx
0x140017f48  push    rbx
0x140017f49  push    rbp
0x140017f4a  push    rsi
0x140017f4b  push    rdi
0x140017f4c  sub     rsp, 28h
0x140017f50  mov     edi, 800h
0x140017f55  lea     rcx, LibFileName; "DiagnosticDataSettings"
0x140017f5c  mov     r8d, edi; dwFlags
0x140017f5f  xor     edx, edx; hFile
0x140017f61  xor     ebx, ebx
0x140017f63  call    cs:__imp_LoadLibraryExW
0x140017f69  mov     rsi, rax
0x140017f6c  test    rax, rax
0x140017f6f  jz      short loc_140017F9C
0x140017f71  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x140017f78  mov     rcx, rax; hModule
0x140017f7b  call    cs:__imp_GetProcAddress
0x140017f81  test    rax, rax
0x140017f84  jz      short loc_140017F9C
0x140017f86  lea     ecx, [rbx+1]
0x140017f89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140017f8e  test    eax, eax
0x140017f90  js      short loc_140017F9C
0x140017f92  xor     edi, edi
0x140017f94  test    eax, eax
0x140017f96  setz    bpl
0x140017f9a  jmp     short loc_140018018
0x140017f9c  mov     r8d, edi; dwFlags
0x140017f9f  mov     [rsp+48h+arg_0], ebx
0x140017fa3  xor     edx, edx; hFile
0x140017fa5  lea     rcx, aAepic; "Aepic"
0x140017fac  xor     bpl, bpl
0x140017faf  call    cs:__imp_LoadLibraryExW
0x140017fb5  mov     rdi, rax
0x140017fb8  test    rax, rax
0x140017fbb  jz      short loc_140017FD2
0x140017fbd  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x140017fc4  mov     rcx, rax; hModule
0x140017fc7  call    cs:__imp_GetProcAddress
0x140017fcd  test    rax, rax
0x140017fd0  jnz     short loc_140017FFC
0x140017fd2  lea     rcx, aDevinv; "Devinv"
0x140017fd9  call    cs:__imp_LoadLibraryW
0x140017fdf  mov     rbx, rax
0x140017fe2  test    rax, rax
0x140017fe5  jz      short loc_140018013
0x140017fe7  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x140017fee  mov     rcx, rax; hModule
0x140017ff1  call    cs:__imp_GetProcAddress
0x140017ff7  test    rax, rax
0x140017ffa  jz      short loc_140018013
0x140017ffc  lea     rcx, [rsp+48h+arg_0]
0x140018001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140018006  test    eax, eax
0x140018008  js      short loc_140018013
0x14001800a  cmp     [rsp+48h+arg_0], 1
0x14001800f  setnb   bpl
0x140018013  test    rsi, rsi
0x140018016  jz      short loc_140018021
0x140018018  mov     rcx, rsi; hLibModule
0x14001801b  call    cs:__imp_FreeLibrary
0x140018021  test    rdi, rdi
0x140018024  jz      short loc_14001802F
0x140018026  mov     rcx, rdi; hLibModule
0x140018029  call    cs:__imp_FreeLibrary
0x14001802f  test    rbx, rbx
0x140018032  jz      short loc_14001803D
0x140018034  mov     rcx, rbx; hLibModule
0x140018037  call    cs:__imp_FreeLibrary
0x14001803d  mov     al, bpl
0x140018040  add     rsp, 28h
0x140018044  pop     rdi
0x140018045  pop     rsi
0x140018046  pop     rbp
0x140018047  pop     rbx
0x140018048  retn
```
