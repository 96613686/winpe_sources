# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x180043c34`
- end: `0x180043fd5`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `929`
- prototype: `bool __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180042554`

## callees

- `0x180043c34`
- `0x180043fdc`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043c62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043cb7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043cd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043f5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043c62`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043cb7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043cd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180043f5f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043c9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043e4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043e56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043fab`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043c9c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043e4d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043e56`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180043fab`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043c7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043cf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043f7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043c7a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043cf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d19`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043d3f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180043f7a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043ec9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043f02`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043f3f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043ec9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043f02`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180043f3f`

## string_xrefs

- `0x180043c51`: `DiagnosticDataSettings.dll`
- `0x180043ccc`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x180043cae`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x180043d1f`: `WindowsCreateString`
- `0x180043d32`: `WindowsDeleteString`
- `0x180043f56`: `slc.dll`

## pseudocode

```c
bool __fastcall TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(int a1)
{
  bool v1; // bl
  char v2; // si
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  int v6; // eax
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // cx
  HMODULE v9; // rdi
  unsigned __int16 v10; // r8
  HMODULE v11; // r14
  FARPROC v12; // r12
  FARPROC v13; // r15
  void (*v14)(void); // r13
  FARPROC v15; // rcx
  FARPROC v16; // rcx
  char v17; // al
  HMODULE v18; // rax
  HMODULE v19; // rbx
  bool v20; // di
  FARPROC v21; // rax
  int pvData; // [rsp+90h] [rbp+48h] BYREF
  FARPROC pcbData; // [rsp+98h] [rbp+50h] BYREF
  __int64 v25; // [rsp+A0h] [rbp+58h] BYREF
  void (*v26)(void); // [rsp+A8h] [rbp+60h]

  pvData = a1;
  v1 = 0;
  v2 = 0;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "TelIsTelemetryTypeAllowed");
    if ( ProcAddress )
    {
      v6 = ((__int64 (__fastcall *)(__int64))ProcAddress)(1);
      if ( v6 >= 0 )
      {
        v2 = 1;
        v1 = v6 == 0;
      }
    }
    FreeLibrary(v4);
    if ( v2 )
      return v1;
  }
  v9 = LoadLibraryExW(L"api-ms-win-core-winrt-l1-1-0.dll", 0, 0x800u);
  if ( v9 )
  {
    v11 = LoadLibraryExW(L"api-ms-win-core-winrt-string-l1-1-0.dll", 0, 0x800u);
    if ( v11 )
    {
      pcbData = GetProcAddress(v9, "RoInitialize");
      v26 = (void (*)(void))GetProcAddress(v9, "RoUninitialize");
      v12 = GetProcAddress(v9, "RoGetActivationFactory");
      v13 = GetProcAddress(v11, "WindowsCreateString");
      v14 = (void (*)(void))GetProcAddress(v11, "WindowsDeleteString");
      if ( pcbData && v26 && v12 && v13 && v14 && ((int (__fastcall *)(__int64))pcbData)(1) >= 0 )
      {
        v25 = 0;
        pcbData = 0;
        LOBYTE(pvData) = 0;
        if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *))v13)(
               L"Windows.System.Profile.PlatformDiagnosticsAndUsageDataSettings",
               62,
               &v25) >= 0 )
        {
          v15 = pcbData;
          if ( pcbData )
          {
            pcbData = 0;
            (*(void (__fastcall **)(FARPROC))(*(_QWORD *)v15 + 16LL))(v15);
          }
          if ( ((int (__fastcall *)(__int64, GUID *, FARPROC *))v12)(
                 v25,
                 &GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a,
                 &pcbData) >= 0
            && (*(int (__fastcall **)(FARPROC, __int64, int *))(*(_QWORD *)pcbData + 72LL))(pcbData, 1, &pvData) >= 0 )
          {
            v2 = 1;
            v1 = (_BYTE)pvData != 0;
          }
        }
        if ( v25 )
          v14();
        v16 = pcbData;
        if ( pcbData )
        {
          pcbData = 0;
          (*(void (__fastcall **)(FARPROC))(*(_QWORD *)v16 + 16LL))(v16);
        }
        v26();
      }
      FreeLibrary(v11);
    }
    FreeLibrary(v9);
    if ( v2 )
      return v1;
  }
  if ( IsWindowsVersionOrGreaterEx(v8, v7, v10, 0x295Au) )
    return v1;
  pvData = 0;
  LODWORD(pcbData) = 4;
  if ( RegGetValueW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
         L"AllowTelemetry",
         0x10u,
         0,
         &pvData,
         (LPDWORD)&pcbData) )
  {
    if ( RegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Policies\\Microsoft\\Windows\\DataCollection",
           L"AllowTelemetry_PolicyManager",
           0x10u,
           0,
           &pvData,
           (LPDWORD)&pcbData) )
    {
      pvData = 4;
      if ( (RegGetValueW(
              HKEY_LOCAL_MACHINE,
              L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Policies\\DataCollection",
              L"AllowTelemetry",
              0x10u,
              0,
              &pvData,
              (LPDWORD)&pcbData)
          & 0xFFFFFFFD) != 0 )
        return v1;
    }
  }
  v17 = pvData;
  if ( !pvData )
  {
    v18 = LoadLibraryExW(L"slc.dll", 0, 0x800u);
    v19 = v18;
    if ( !v18 )
      goto LABEL_37;
    v20 = 0;
    v21 = GetProcAddress(v18, "SLGetWindowsInformationDWORD");
    if ( v21 )
    {
      LODWORD(v25) = 0;
      if ( ((int (__fastcall *)(const wchar_t *, __int64 *))v21)(L"TelemetryPermission-AllowDisable", &v25) >= 0 )
        v20 = (_DWORD)v25 == 1;
    }
    FreeLibrary(v19);
    v17 = pvData;
    if ( !v20 )
LABEL_37:
      v17 = 1;
  }
  return v17 & 1;
}

```

## disassembly

```asm
0x180043c34  mov     [rsp-40h+arg_0], ecx
0x180043c38  push    rbp
0x180043c39  push    rbx
0x180043c3a  push    rsi
0x180043c3b  push    rdi
0x180043c3c  push    r12
0x180043c3e  push    r13
0x180043c40  push    r14
0x180043c42  push    r15
0x180043c44  mov     rbp, rsp
0x180043c47  sub     rsp, 48h
0x180043c4b  mov     r14d, 800h
0x180043c51  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x180043c58  mov     r8d, r14d; dwFlags
0x180043c5b  xor     edx, edx; hFile
0x180043c5d  xor     bl, bl
0x180043c5f  xor     sil, sil
0x180043c62  call    cs:__imp_LoadLibraryExW
0x180043c68  mov     rdi, rax
0x180043c6b  test    rax, rax
0x180043c6e  jz      short loc_180043CAB
0x180043c70  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x180043c77  mov     rcx, rax; hModule
0x180043c7a  call    cs:__imp_GetProcAddress
0x180043c80  test    rax, rax
0x180043c83  jz      short loc_180043C99
0x180043c85  mov     ecx, 1
0x180043c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c8f  test    eax, eax
0x180043c91  js      short loc_180043C99
0x180043c93  mov     sil, 1
0x180043c96  setz    bl
0x180043c99  mov     rcx, rdi; hLibModule
0x180043c9c  call    cs:__imp_FreeLibrary
0x180043ca2  test    sil, sil
0x180043ca5  jnz     loc_180043FC2
0x180043cab  mov     r8d, r14d; dwFlags
0x180043cae  lea     rcx, aApiMsWinCoreWi_0; "api-ms-win-core-winrt-l1-1-0.dll"
0x180043cb5  xor     edx, edx; hFile
0x180043cb7  call    cs:__imp_LoadLibraryExW
0x180043cbd  mov     rdi, rax
0x180043cc0  test    rax, rax
0x180043cc3  jz      loc_180043E6B
0x180043cc9  mov     r8d, r14d; dwFlags
0x180043ccc  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x180043cd3  xor     edx, edx; hFile
0x180043cd5  call    cs:__imp_LoadLibraryExW
0x180043cdb  mov     r14, rax
0x180043cde  test    rax, rax
0x180043ce1  jz      loc_180043E53
0x180043ce7  lea     rdx, aRoinitialize; "RoInitialize"
0x180043cee  mov     rcx, rdi; hModule
0x180043cf1  call    cs:__imp_GetProcAddress
0x180043cf7  lea     rdx, aRouninitialize; "RoUninitialize"
0x180043cfe  mov     rcx, rdi; hModule
0x180043d01  mov     [rbp+arg_8], rax
0x180043d05  call    cs:__imp_GetProcAddress
0x180043d0b  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x180043d12  mov     rcx, rdi; hModule
0x180043d15  mov     [rbp+arg_18], rax
0x180043d19  call    cs:__imp_GetProcAddress
0x180043d1f  lea     rdx, aWindowscreates; "WindowsCreateString"
0x180043d26  mov     rcx, r14; hModule
0x180043d29  mov     r12, rax
0x180043d2c  call    cs:__imp_GetProcAddress
0x180043d32  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x180043d39  mov     rcx, r14; hModule
0x180043d3c  mov     r15, rax
0x180043d3f  call    cs:__imp_GetProcAddress
0x180043d45  mov     r13, rax
0x180043d48  mov     rax, [rbp+arg_8]
0x180043d4c  test    rax, rax
0x180043d4f  jz      loc_180043E4A
0x180043d55  cmp     [rbp+arg_18], 0
0x180043d5a  jz      loc_180043E4A
0x180043d60  test    r12, r12
0x180043d63  jz      loc_180043E4A
0x180043d69  test    r15, r15
0x180043d6c  jz      loc_180043E4A
0x180043d72  test    r13, r13
0x180043d75  jz      loc_180043E4A
0x180043d7b  mov     ecx, 1
0x180043d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d85  xor     ecx, ecx
0x180043d87  test    eax, eax
0x180043d89  js      loc_180043E4A
0x180043d8f  mov     [rbp+arg_10], rcx
0x180043d93  lea     edx, [rcx+3Eh]
0x180043d96  mov     [rbp+arg_8], rcx
0x180043d9a  lea     r8, [rbp+arg_10]
0x180043d9e  mov     byte ptr [rbp+arg_0], cl
0x180043da1  mov     rax, r15
0x180043da4  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x180043dab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043db0  test    eax, eax
0x180043db2  js      short loc_180043E13
0x180043db4  mov     rcx, [rbp+arg_8]
0x180043db8  test    rcx, rcx
0x180043dbb  jz      short loc_180043DD1
0x180043dbd  mov     [rbp+arg_8], 0
0x180043dc5  mov     rdx, [rcx]
0x180043dc8  mov     rax, [rdx+10h]
0x180043dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dd1  mov     rcx, [rbp+arg_10]
0x180043dd5  lea     r8, [rbp+arg_8]
0x180043dd9  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x180043de0  mov     rax, r12
0x180043de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043de8  test    eax, eax
0x180043dea  js      short loc_180043E13
0x180043dec  mov     rcx, [rbp+arg_8]
0x180043df0  lea     r8, [rbp+arg_0]
0x180043df4  mov     edx, 1
0x180043df9  mov     rax, [rcx]
0x180043dfc  mov     rax, [rax+48h]
0x180043e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e05  test    eax, eax
0x180043e07  js      short loc_180043E13
0x180043e09  cmp     byte ptr [rbp+arg_0], 0
0x180043e0d  mov     sil, 1
0x180043e10  setnz   bl
0x180043e13  mov     rcx, [rbp+arg_10]
0x180043e17  test    rcx, rcx
0x180043e1a  jz      short loc_180043E24
0x180043e1c  mov     rax, r13
0x180043e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e24  mov     rcx, [rbp+arg_8]
0x180043e28  test    rcx, rcx
0x180043e2b  jz      short loc_180043E41
0x180043e2d  mov     [rbp+arg_8], 0
0x180043e35  mov     rdx, [rcx]
0x180043e38  mov     rax, [rdx+10h]
0x180043e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e41  mov     rax, [rbp+arg_18]
0x180043e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e4a  mov     rcx, r14; hLibModule
0x180043e4d  call    cs:__imp_FreeLibrary
0x180043e53  mov     rcx, rdi; hLibModule
0x180043e56  call    cs:__imp_FreeLibrary
0x180043e5c  test    sil, sil
0x180043e5f  jnz     loc_180043FC2
0x180043e65  mov     r14d, 800h
0x180043e6b  mov     r9d, 295Ah; unsigned __int16
0x180043e71  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x180043e76  test    al, al
0x180043e78  jnz     loc_180043FC2
0x180043e7e  mov     r15d, 4
0x180043e84  mov     [rbp+arg_0], 0
0x180043e8b  lea     rax, [rbp+arg_8]
0x180043e8f  mov     dword ptr [rbp+arg_8], r15d
0x180043e93  mov     [rsp+48h+pcbData], rax; pcbData
0x180043e98  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x180043e9f  lea     rax, [rbp+arg_0]
0x180043ea3  mov     rsi, 0FFFFFFFF80000002h
0x180043eaa  mov     [rsp+48h+pvData], rax; pvData
0x180043eaf  lea     edi, [r15+0Ch]
0x180043eb3  mov     r9d, edi; dwFlags
0x180043eb6  mov     [rsp+48h+pdwType], 0; pdwType
0x180043ebf  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180043ec6  mov     rcx, rsi; hkey
0x180043ec9  call    cs:__imp_RegGetValueW
0x180043ecf  test    eax, eax
0x180043ed1  jz      short loc_180043F4C
0x180043ed3  lea     rax, [rbp+arg_8]
0x180043ed7  mov     r9d, edi; dwFlags
0x180043eda  mov     [rsp+48h+pcbData], rax; pcbData
0x180043edf  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x180043ee6  lea     rax, [rbp+arg_0]
0x180043eea  mov     rcx, rsi; hkey
0x180043eed  mov     [rsp+48h+pvData], rax; pvData
0x180043ef2  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x180043ef9  mov     [rsp+48h+pdwType], 0; pdwType
0x180043f02  call    cs:__imp_RegGetValueW
0x180043f08  test    eax, eax
0x180043f0a  jz      short loc_180043F4C
0x180043f0c  lea     rax, [rbp+arg_8]
0x180043f10  mov     [rbp+arg_0], r15d
0x180043f14  mov     [rsp+48h+pcbData], rax; pcbData
0x180043f19  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x180043f20  lea     rax, [rbp+arg_0]
0x180043f24  mov     r9d, edi; dwFlags
0x180043f27  mov     [rsp+48h+pvData], rax; pvData
0x180043f2c  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180043f33  mov     rcx, rsi; hkey
0x180043f36  mov     [rsp+48h+pdwType], 0; pdwType
0x180043f3f  call    cs:__imp_RegGetValueW
0x180043f45  test    eax, 0FFFFFFFDh
0x180043f4a  jnz     short loc_180043FC2
0x180043f4c  mov     eax, [rbp+arg_0]
0x180043f4f  test    eax, eax
0x180043f51  jnz     short loc_180043FBE
0x180043f53  mov     r8d, r14d; dwFlags
0x180043f56  lea     rcx, aSlcDll; "slc.dll"
0x180043f5d  xor     edx, edx; hFile
0x180043f5f  call    cs:__imp_LoadLibraryExW
0x180043f65  mov     rbx, rax
0x180043f68  test    rax, rax
0x180043f6b  jz      short loc_180043FB9
0x180043f6d  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x180043f74  mov     rcx, rax; hModule
0x180043f77  xor     dil, dil
0x180043f7a  call    cs:__imp_GetProcAddress
0x180043f80  test    rax, rax
0x180043f83  jz      short loc_180043FA8
0x180043f85  lea     rdx, [rbp+arg_10]
0x180043f89  mov     dword ptr [rbp+arg_10], 0
0x180043f90  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x180043f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f9c  test    eax, eax
0x180043f9e  js      short loc_180043FA8
0x180043fa0  cmp     dword ptr [rbp+arg_10], 1
0x180043fa4  setz    dil
0x180043fa8  mov     rcx, rbx; hLibModule
0x180043fab  call    cs:__imp_FreeLibrary
0x180043fb1  mov     eax, [rbp+arg_0]
0x180043fb4  test    dil, dil
0x180043fb7  jnz     short loc_180043FBE
0x180043fb9  mov     eax, 1
0x180043fbe  and     al, 1
0x180043fc0  jmp     short loc_180043FC4
0x180043fc2  mov     al, bl
0x180043fc4  add     rsp, 48h
0x180043fc8  pop     r15
0x180043fca  pop     r14
0x180043fcc  pop     r13
0x180043fce  pop     r12
0x180043fd0  pop     rdi
0x180043fd1  pop     rsi
0x180043fd2  pop     rbx
0x180043fd3  pop     rbp
0x180043fd4  retn
```
