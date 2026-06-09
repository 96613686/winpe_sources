# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180064d20`
- end: `0x180064e38`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002bda4`
- `0x180067f64`

## callees

- `0x180064d20`
- `0x180130010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180064d48`
- `KERNEL32!LoadLibraryExW` at `0x180064d94`
- `KERNEL32!LoadLibraryExW` at `0x180064d48`
- `KERNEL32!LoadLibraryExW` at `0x180064d94`
- `KERNEL32!LoadLibraryW` at `0x180064dbe`
- `KERNEL32!LoadLibraryW` at `0x180064dbe`
- `KERNEL32!FreeLibrary` at `0x180064e00`
- `KERNEL32!FreeLibrary` at `0x180064e0e`
- `KERNEL32!FreeLibrary` at `0x180064e1c`
- `KERNEL32!FreeLibrary` at `0x180064e00`
- `KERNEL32!FreeLibrary` at `0x180064e0e`
- `KERNEL32!FreeLibrary` at `0x180064e1c`
- `KERNEL32!GetProcAddress` at `0x180064d60`
- `KERNEL32!GetProcAddress` at `0x180064dac`
- `KERNEL32!GetProcAddress` at `0x180064dd6`
- `KERNEL32!GetProcAddress` at `0x180064d60`
- `KERNEL32!GetProcAddress` at `0x180064dac`
- `KERNEL32!GetProcAddress` at `0x180064dd6`

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
0x180064d20  mov     [rsp+arg_0], rbx
0x180064d25  mov     [rsp+arg_10], rbp
0x180064d2a  push    rsi
0x180064d2b  push    rdi
0x180064d2c  push    r14
0x180064d2e  sub     rsp, 20h
0x180064d32  mov     r14d, ecx
0x180064d35  mov     edi, 800h
0x180064d3a  mov     r8d, edi; dwFlags
0x180064d3d  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings"
0x180064d44  xor     edx, edx; hFile
0x180064d46  xor     ebx, ebx
0x180064d48  call    cs:__imp_LoadLibraryExW
0x180064d4e  mov     rsi, rax
0x180064d51  test    rax, rax
0x180064d54  jz      short loc_180064D81
0x180064d56  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180064d5d  mov     rcx, rax; hModule
0x180064d60  call    cs:__imp_GetProcAddress
0x180064d66  test    rax, rax
0x180064d69  jz      short loc_180064D81
0x180064d6b  mov     ecx, r14d
0x180064d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064d73  test    eax, eax
0x180064d75  js      short loc_180064D81
0x180064d77  xor     edi, edi
0x180064d79  test    eax, eax
0x180064d7b  setz    bpl
0x180064d7f  jmp     short loc_180064DFD
0x180064d81  mov     r8d, edi; dwFlags
0x180064d84  mov     [rsp+38h+arg_8], ebx
0x180064d88  xor     edx, edx; hFile
0x180064d8a  lea     rcx, aAepic; "Aepic"
0x180064d91  xor     bpl, bpl
0x180064d94  call    cs:__imp_LoadLibraryExW
0x180064d9a  mov     rdi, rax
0x180064d9d  test    rax, rax
0x180064da0  jz      short loc_180064DB7
0x180064da2  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180064da9  mov     rcx, rax; hModule
0x180064dac  call    cs:__imp_GetProcAddress
0x180064db2  test    rax, rax
0x180064db5  jnz     short loc_180064DE1
0x180064db7  lea     rcx, aDevinv; "Devinv"
0x180064dbe  call    cs:__imp_LoadLibraryW
0x180064dc4  mov     rbx, rax
0x180064dc7  test    rax, rax
0x180064dca  jz      short loc_180064DF8
0x180064dcc  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180064dd3  mov     rcx, rax; hModule
0x180064dd6  call    cs:__imp_GetProcAddress
0x180064ddc  test    rax, rax
0x180064ddf  jz      short loc_180064DF8
0x180064de1  lea     rcx, [rsp+38h+arg_8]
0x180064de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180064deb  test    eax, eax
0x180064ded  js      short loc_180064DF8
0x180064def  cmp     r14d, [rsp+38h+arg_8]
0x180064df4  setbe   bpl
0x180064df8  test    rsi, rsi
0x180064dfb  jz      short loc_180064E06
0x180064dfd  mov     rcx, rsi; hLibModule
0x180064e00  call    cs:__imp_FreeLibrary
0x180064e06  test    rdi, rdi
0x180064e09  jz      short loc_180064E14
0x180064e0b  mov     rcx, rdi; hLibModule
0x180064e0e  call    cs:__imp_FreeLibrary
0x180064e14  test    rbx, rbx
0x180064e17  jz      short loc_180064E22
0x180064e19  mov     rcx, rbx; hLibModule
0x180064e1c  call    cs:__imp_FreeLibrary
0x180064e22  mov     rbx, [rsp+38h+arg_0]
0x180064e27  mov     al, bpl
0x180064e2a  mov     rbp, [rsp+38h+arg_10]
0x180064e2f  add     rsp, 20h
0x180064e33  pop     r14
0x180064e35  pop     rdi
0x180064e36  pop     rsi
0x180064e37  retn
```
