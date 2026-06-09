# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180020250`
- end: `0x180020368`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fc0c`
- `0x180024c50`

## callees

- `0x180020250`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020290`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800202dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020306`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020290`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800202dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180020306`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020330`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002033e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002034c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020330`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002033e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002034c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020278`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800202c4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180020278`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800202c4`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800202ee`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800202ee`

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
0x180020250  mov     [rsp+arg_0], rbx
0x180020255  mov     [rsp+arg_10], rbp
0x18002025a  push    rsi
0x18002025b  push    rdi
0x18002025c  push    r14
0x18002025e  sub     rsp, 20h
0x180020262  mov     r14d, ecx
0x180020265  mov     edi, 800h
0x18002026a  mov     r8d, edi; dwFlags
0x18002026d  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x180020274  xor     edx, edx; hFile
0x180020276  xor     ebx, ebx
0x180020278  call    cs:__imp_LoadLibraryExW
0x18002027e  mov     rsi, rax
0x180020281  test    rax, rax
0x180020284  jz      short loc_1800202B1
0x180020286  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x18002028d  mov     rcx, rax; hModule
0x180020290  call    cs:__imp_GetProcAddress
0x180020296  test    rax, rax
0x180020299  jz      short loc_1800202B1
0x18002029b  mov     ecx, r14d
0x18002029e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202a3  test    eax, eax
0x1800202a5  js      short loc_1800202B1
0x1800202a7  xor     edi, edi
0x1800202a9  test    eax, eax
0x1800202ab  setz    bpl
0x1800202af  jmp     short loc_18002032D
0x1800202b1  mov     r8d, edi; dwFlags
0x1800202b4  mov     [rsp+38h+arg_8], ebx
0x1800202b8  xor     edx, edx; hFile
0x1800202ba  lea     rcx, aAepic; "Aepic"
0x1800202c1  xor     bpl, bpl
0x1800202c4  call    cs:__imp_LoadLibraryExW
0x1800202ca  mov     rdi, rax
0x1800202cd  test    rax, rax
0x1800202d0  jz      short loc_1800202E7
0x1800202d2  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800202d9  mov     rcx, rax; hModule
0x1800202dc  call    cs:__imp_GetProcAddress
0x1800202e2  test    rax, rax
0x1800202e5  jnz     short loc_180020311
0x1800202e7  lea     rcx, aDevinv; "Devinv"
0x1800202ee  call    cs:__imp_LoadLibraryW
0x1800202f4  mov     rbx, rax
0x1800202f7  test    rax, rax
0x1800202fa  jz      short loc_180020328
0x1800202fc  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180020303  mov     rcx, rax; hModule
0x180020306  call    cs:__imp_GetProcAddress
0x18002030c  test    rax, rax
0x18002030f  jz      short loc_180020328
0x180020311  lea     rcx, [rsp+38h+arg_8]
0x180020316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002031b  test    eax, eax
0x18002031d  js      short loc_180020328
0x18002031f  cmp     r14d, [rsp+38h+arg_8]
0x180020324  setbe   bpl
0x180020328  test    rsi, rsi
0x18002032b  jz      short loc_180020336
0x18002032d  mov     rcx, rsi; hLibModule
0x180020330  call    cs:__imp_FreeLibrary
0x180020336  test    rdi, rdi
0x180020339  jz      short loc_180020344
0x18002033b  mov     rcx, rdi; hLibModule
0x18002033e  call    cs:__imp_FreeLibrary
0x180020344  test    rbx, rbx
0x180020347  jz      short loc_180020352
0x180020349  mov     rcx, rbx; hLibModule
0x18002034c  call    cs:__imp_FreeLibrary
0x180020352  mov     rbx, [rsp+38h+arg_0]
0x180020357  mov     al, bpl
0x18002035a  mov     rbp, [rsp+38h+arg_10]
0x18002035f  add     rsp, 20h
0x180020363  pop     r14
0x180020365  pop     rdi
0x180020366  pop     rsi
0x180020367  retn
```
