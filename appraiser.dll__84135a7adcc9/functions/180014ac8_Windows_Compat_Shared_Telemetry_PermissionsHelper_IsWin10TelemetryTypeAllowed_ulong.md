# Windows::Compat::Shared::Telemetry::PermissionsHelper::IsWin10TelemetryTypeAllowed(ulong)

- ea: `0x180014ac8`
- end: `0x180014be0`
- name: `?IsWin10TelemetryTypeAllowed@PermissionsHelper@Telemetry@Shared@Compat@Windows@@CA_NK@Z`
- size: `280`
- prototype: `bool __fastcall(unsigned int)`
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014894`
- `0x180014988`
- `0x180041020`
- `0x1800489d4`
- `0x18004d790`
- `0x18008eac8`
- `0x18009edb8`
- `0x18010b6c4`
- `0x1801d8c88`
- `0x1801d9eb4`

## callees

- `0x180014ac8`
- `0x18021f010`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180014af0`
- `KERNEL32!LoadLibraryExW` at `0x180014b3c`
- `KERNEL32!LoadLibraryExW` at `0x180014af0`
- `KERNEL32!LoadLibraryExW` at `0x180014b3c`
- `KERNEL32!LoadLibraryW` at `0x180014b66`
- `KERNEL32!LoadLibraryW` at `0x180014b66`
- `KERNEL32!FreeLibrary` at `0x180014ba8`
- `KERNEL32!FreeLibrary` at `0x180014bb6`
- `KERNEL32!FreeLibrary` at `0x180014bc4`
- `KERNEL32!FreeLibrary` at `0x180014ba8`
- `KERNEL32!FreeLibrary` at `0x180014bb6`
- `KERNEL32!FreeLibrary` at `0x180014bc4`
- `KERNEL32!GetProcAddress` at `0x180014b08`
- `KERNEL32!GetProcAddress` at `0x180014b54`
- `KERNEL32!GetProcAddress` at `0x180014b7e`
- `KERNEL32!GetProcAddress` at `0x180014b08`
- `KERNEL32!GetProcAddress` at `0x180014b54`
- `KERNEL32!GetProcAddress` at `0x180014b7e`

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
0x180014ac8  mov     [rsp+arg_0], rbx
0x180014acd  mov     [rsp+arg_10], rbp
0x180014ad2  push    rsi
0x180014ad3  push    rdi
0x180014ad4  push    r14
0x180014ad6  sub     rsp, 20h
0x180014ada  mov     r14d, ecx
0x180014add  mov     edi, 800h
0x180014ae2  mov     r8d, edi; dwFlags
0x180014ae5  lea     rcx, LibFileName; "DiagnosticDataSettings"
0x180014aec  xor     edx, edx; hFile
0x180014aee  xor     ebx, ebx
0x180014af0  call    cs:__imp_LoadLibraryExW
0x180014af6  mov     rsi, rax
0x180014af9  test    rax, rax
0x180014afc  jz      short loc_180014B29
0x180014afe  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180014b05  mov     rcx, rax; hModule
0x180014b08  call    cs:__imp_GetProcAddress
0x180014b0e  test    rax, rax
0x180014b11  jz      short loc_180014B29
0x180014b13  mov     ecx, r14d
0x180014b16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b1b  test    eax, eax
0x180014b1d  js      short loc_180014B29
0x180014b1f  xor     edi, edi
0x180014b21  test    eax, eax
0x180014b23  setz    bpl
0x180014b27  jmp     short loc_180014BA5
0x180014b29  mov     r8d, edi; dwFlags
0x180014b2c  mov     [rsp+38h+arg_8], ebx
0x180014b30  xor     edx, edx; hFile
0x180014b32  lea     rcx, aAepic; "Aepic"
0x180014b39  xor     bpl, bpl
0x180014b3c  call    cs:__imp_LoadLibraryExW
0x180014b42  mov     rdi, rax
0x180014b45  test    rax, rax
0x180014b48  jz      short loc_180014B5F
0x180014b4a  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180014b51  mov     rcx, rax; hModule
0x180014b54  call    cs:__imp_GetProcAddress
0x180014b5a  test    rax, rax
0x180014b5d  jnz     short loc_180014B89
0x180014b5f  lea     rcx, aDevinv; "Devinv"
0x180014b66  call    cs:__imp_LoadLibraryW
0x180014b6c  mov     rbx, rax
0x180014b6f  test    rax, rax
0x180014b72  jz      short loc_180014BA0
0x180014b74  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x180014b7b  mov     rcx, rax; hModule
0x180014b7e  call    cs:__imp_GetProcAddress
0x180014b84  test    rax, rax
0x180014b87  jz      short loc_180014BA0
0x180014b89  lea     rcx, [rsp+38h+arg_8]
0x180014b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b93  test    eax, eax
0x180014b95  js      short loc_180014BA0
0x180014b97  cmp     r14d, [rsp+38h+arg_8]
0x180014b9c  setbe   bpl
0x180014ba0  test    rsi, rsi
0x180014ba3  jz      short loc_180014BAE
0x180014ba5  mov     rcx, rsi; hLibModule
0x180014ba8  call    cs:__imp_FreeLibrary
0x180014bae  test    rdi, rdi
0x180014bb1  jz      short loc_180014BBC
0x180014bb3  mov     rcx, rdi; hLibModule
0x180014bb6  call    cs:__imp_FreeLibrary
0x180014bbc  test    rbx, rbx
0x180014bbf  jz      short loc_180014BCA
0x180014bc1  mov     rcx, rbx; hLibModule
0x180014bc4  call    cs:__imp_FreeLibrary
0x180014bca  mov     rbx, [rsp+38h+arg_0]
0x180014bcf  mov     al, bpl
0x180014bd2  mov     rbp, [rsp+38h+arg_10]
0x180014bd7  add     rsp, 20h
0x180014bdb  pop     r14
0x180014bdd  pop     rdi
0x180014bde  pop     rsi
0x180014bdf  retn
```
