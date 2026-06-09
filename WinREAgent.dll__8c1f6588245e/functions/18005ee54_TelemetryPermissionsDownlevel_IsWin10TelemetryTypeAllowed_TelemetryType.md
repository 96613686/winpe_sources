# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x18005ee54`
- end: `0x18005f1ce`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `890`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005dc50`

## callees

- `0x18005edb8`
- `0x18005ee54`
- `0x18005f290`
- `0x18006f010`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18005f0c2`
- `ADVAPI32!RegGetValueW` at `0x18005f0fb`
- `ADVAPI32!RegGetValueW` at `0x18005f138`
- `ADVAPI32!RegGetValueW` at `0x18005f0c2`
- `ADVAPI32!RegGetValueW` at `0x18005f0fb`
- `ADVAPI32!RegGetValueW` at `0x18005f138`
- `KERNEL32!LoadLibraryExW` at `0x18005ee82`
- `KERNEL32!LoadLibraryExW` at `0x18005eed7`
- `KERNEL32!LoadLibraryExW` at `0x18005eef5`
- `KERNEL32!LoadLibraryExW` at `0x18005f158`
- `KERNEL32!LoadLibraryExW` at `0x18005ee82`
- `KERNEL32!LoadLibraryExW` at `0x18005eed7`
- `KERNEL32!LoadLibraryExW` at `0x18005eef5`
- `KERNEL32!LoadLibraryExW` at `0x18005f158`
- `KERNEL32!FreeLibrary` at `0x18005eebc`
- `KERNEL32!FreeLibrary` at `0x18005f046`
- `KERNEL32!FreeLibrary` at `0x18005f04f`
- `KERNEL32!FreeLibrary` at `0x18005f1a4`
- `KERNEL32!FreeLibrary` at `0x18005eebc`
- `KERNEL32!FreeLibrary` at `0x18005f046`
- `KERNEL32!FreeLibrary` at `0x18005f04f`
- `KERNEL32!FreeLibrary` at `0x18005f1a4`
- `KERNEL32!GetProcAddress` at `0x18005ee9a`
- `KERNEL32!GetProcAddress` at `0x18005ef11`
- `KERNEL32!GetProcAddress` at `0x18005ef25`
- `KERNEL32!GetProcAddress` at `0x18005ef38`
- `KERNEL32!GetProcAddress` at `0x18005ef4b`
- `KERNEL32!GetProcAddress` at `0x18005ef5e`
- `KERNEL32!GetProcAddress` at `0x18005f173`
- `KERNEL32!GetProcAddress` at `0x18005ee9a`
- `KERNEL32!GetProcAddress` at `0x18005ef11`
- `KERNEL32!GetProcAddress` at `0x18005ef25`
- `KERNEL32!GetProcAddress` at `0x18005ef38`
- `KERNEL32!GetProcAddress` at `0x18005ef4b`
- `KERNEL32!GetProcAddress` at `0x18005ef5e`
- `KERNEL32!GetProcAddress` at `0x18005f173`

## string_xrefs

- `0x18005ee71`: `DiagnosticDataSettings.dll`
- `0x18005eece`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x18005eeec`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18005ef51`: `WindowsDeleteString`
- `0x18005ef3e`: `WindowsCreateString`
- `0x18005f14f`: `slc.dll`

## pseudocode

```c
bool __fastcall TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(int a1)
{
  bool v1; // bl
  char v2; // di
  HMODULE Library; // rax
  HMODULE v4; // rsi
  FARPROC ProcAddress; // rax
  int v6; // eax
  unsigned __int16 v7; // dx
  unsigned __int16 v8; // cx
  HMODULE v9; // rsi
  unsigned __int16 v10; // r8
  HMODULE v11; // r14
  void (*v12)(void); // r13
  FARPROC v13; // r12
  FARPROC v14; // r15
  FARPROC v15; // rax
  char v16; // al
  HMODULE v17; // rax
  HMODULE v18; // rbx
  bool v19; // di
  FARPROC v20; // rax
  int pvData; // [rsp+90h] [rbp+48h] BYREF
  FARPROC pcbData; // [rsp+98h] [rbp+50h] BYREF
  __int64 v24; // [rsp+A0h] [rbp+58h] BYREF
  void (*v25)(void); // [rsp+A8h] [rbp+60h]

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
      v12 = (void (*)(void))GetProcAddress(v9, "RoUninitialize");
      v13 = GetProcAddress(v9, "RoGetActivationFactory");
      v14 = GetProcAddress(v11, "WindowsCreateString");
      v15 = GetProcAddress(v11, "WindowsDeleteString");
      v25 = (void (*)(void))v15;
      if ( pcbData && v12 && v13 && v14 && v15 && ((int (__fastcall *)(__int64))pcbData)(1) >= 0 )
      {
        v24 = 0;
        pcbData = 0;
        LOBYTE(pvData) = 0;
        if ( ((int (__fastcall *)(const unsigned __int16 *, __int64, __int64 *))v14)(
               L"Windows.System.Profile.PlatformDiagnosticsAndUsageDataSettings",
               62,
               &v24) >= 0 )
        {
          Microsoft::WRL::ComPtr<ABI::Windows::System::Profile::IPlatformDiagnosticsAndUsageDataSettingsStatics>::InternalRelease(&pcbData);
          if ( ((int (__fastcall *)(__int64, GUID *, FARPROC *))v13)(
                 v24,
                 &GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a,
                 &pcbData) >= 0
            && (*(int (__fastcall **)(FARPROC, __int64, int *))(*(_QWORD *)pcbData + 72LL))(pcbData, 1, &pvData) >= 0 )
          {
            v2 = 1;
            v1 = (_BYTE)pvData != 0;
          }
        }
        if ( v24 )
          v25();
        Microsoft::WRL::ComPtr<ABI::Windows::System::Profile::IPlatformDiagnosticsAndUsageDataSettingsStatics>::InternalRelease(&pcbData);
        v12();
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
  v16 = pvData;
  if ( !pvData )
  {
    v17 = LoadLibraryExW(L"slc.dll", 0, 0x800u);
    v18 = v17;
    if ( !v17 )
      goto LABEL_33;
    v19 = 0;
    v20 = GetProcAddress(v17, "SLGetWindowsInformationDWORD");
    if ( v20 )
    {
      LODWORD(v24) = 0;
      if ( ((int (__fastcall *)(const wchar_t *, __int64 *))v20)(L"TelemetryPermission-AllowDisable", &v24) >= 0 )
        v19 = (_DWORD)v24 == 1;
    }
    FreeLibrary(v18);
    v16 = pvData;
    if ( !v19 )
LABEL_33:
      v16 = 1;
  }
  return v16 & 1;
}

```

## disassembly

```asm
0x18005ee54  mov     [rsp-40h+arg_0], ecx
0x18005ee58  push    rbp
0x18005ee59  push    rbx
0x18005ee5a  push    rsi
0x18005ee5b  push    rdi
0x18005ee5c  push    r12
0x18005ee5e  push    r13
0x18005ee60  push    r14
0x18005ee62  push    r15
0x18005ee64  mov     rbp, rsp
0x18005ee67  sub     rsp, 48h
0x18005ee6b  mov     r14d, 800h
0x18005ee71  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x18005ee78  mov     r8d, r14d; dwFlags
0x18005ee7b  xor     edx, edx; hFile
0x18005ee7d  xor     bl, bl
0x18005ee7f  xor     dil, dil
0x18005ee82  call    cs:__imp_LoadLibraryExW
0x18005ee88  mov     rsi, rax
0x18005ee8b  test    rax, rax
0x18005ee8e  jz      short loc_18005EECB
0x18005ee90  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x18005ee97  mov     rcx, rax; hModule
0x18005ee9a  call    cs:__imp_GetProcAddress
0x18005eea0  test    rax, rax
0x18005eea3  jz      short loc_18005EEB9
0x18005eea5  mov     ecx, 1
0x18005eeaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eeaf  test    eax, eax
0x18005eeb1  js      short loc_18005EEB9
0x18005eeb3  mov     dil, 1
0x18005eeb6  setz    bl
0x18005eeb9  mov     rcx, rsi; hLibModule
0x18005eebc  call    cs:__imp_FreeLibrary
0x18005eec2  test    dil, dil
0x18005eec5  jnz     loc_18005F1BB
0x18005eecb  mov     r8d, r14d; dwFlags
0x18005eece  lea     rcx, aApiMsWinCoreWi_0; "api-ms-win-core-winrt-l1-1-0.dll"
0x18005eed5  xor     edx, edx; hFile
0x18005eed7  call    cs:__imp_LoadLibraryExW
0x18005eedd  mov     rsi, rax
0x18005eee0  test    rax, rax
0x18005eee3  jz      loc_18005F064
0x18005eee9  mov     r8d, r14d; dwFlags
0x18005eeec  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18005eef3  xor     edx, edx; hFile
0x18005eef5  call    cs:__imp_LoadLibraryExW
0x18005eefb  mov     r14, rax
0x18005eefe  test    rax, rax
0x18005ef01  jz      loc_18005F04C
0x18005ef07  lea     rdx, aRoinitialize; "RoInitialize"
0x18005ef0e  mov     rcx, rsi; hModule
0x18005ef11  call    cs:__imp_GetProcAddress
0x18005ef17  lea     rdx, aRouninitialize; "RoUninitialize"
0x18005ef1e  mov     rcx, rsi; hModule
0x18005ef21  mov     [rbp+arg_8], rax
0x18005ef25  call    cs:__imp_GetProcAddress
0x18005ef2b  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x18005ef32  mov     rcx, rsi; hModule
0x18005ef35  mov     r13, rax
0x18005ef38  call    cs:__imp_GetProcAddress
0x18005ef3e  lea     rdx, aWindowscreates; "WindowsCreateString"
0x18005ef45  mov     rcx, r14; hModule
0x18005ef48  mov     r12, rax
0x18005ef4b  call    cs:__imp_GetProcAddress
0x18005ef51  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x18005ef58  mov     rcx, r14; hModule
0x18005ef5b  mov     r15, rax
0x18005ef5e  call    cs:__imp_GetProcAddress
0x18005ef64  mov     rdx, [rbp+arg_8]
0x18005ef68  mov     [rbp+arg_18], rax
0x18005ef6c  test    rdx, rdx
0x18005ef6f  jz      loc_18005F043
0x18005ef75  test    r13, r13
0x18005ef78  jz      loc_18005F043
0x18005ef7e  test    r12, r12
0x18005ef81  jz      loc_18005F043
0x18005ef87  test    r15, r15
0x18005ef8a  jz      loc_18005F043
0x18005ef90  test    rax, rax
0x18005ef93  jz      loc_18005F043
0x18005ef99  mov     ecx, 1
0x18005ef9e  mov     rax, rdx
0x18005efa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efa6  xor     ecx, ecx
0x18005efa8  test    eax, eax
0x18005efaa  js      loc_18005F043
0x18005efb0  mov     [rbp+arg_10], rcx
0x18005efb4  lea     edx, [rcx+3Eh]
0x18005efb7  mov     [rbp+arg_8], rcx
0x18005efbb  lea     r8, [rbp+arg_10]
0x18005efbf  mov     byte ptr [rbp+arg_0], cl
0x18005efc2  mov     rax, r15
0x18005efc5  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x18005efcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005efd1  test    eax, eax
0x18005efd3  js      short loc_18005F020
0x18005efd5  lea     rcx, [rbp+arg_8]
0x18005efd9  call    ?InternalRelease@?$ComPtr@UIPlatformDiagnosticsAndUsageDataSettingsStatics@Profile@System@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::System::Profile::IPlatformDiagnosticsAndUsageDataSettingsStatics>::InternalRelease(void)
0x18005efde  mov     rcx, [rbp+arg_10]
0x18005efe2  lea     r8, [rbp+arg_8]
0x18005efe6  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x18005efed  mov     rax, r12
0x18005eff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005eff5  test    eax, eax
0x18005eff7  js      short loc_18005F020
0x18005eff9  mov     rcx, [rbp+arg_8]
0x18005effd  lea     r8, [rbp+arg_0]
0x18005f001  mov     edx, 1
0x18005f006  mov     rax, [rcx]
0x18005f009  mov     rax, [rax+48h]
0x18005f00d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f012  test    eax, eax
0x18005f014  js      short loc_18005F020
0x18005f016  cmp     byte ptr [rbp+arg_0], 0
0x18005f01a  mov     dil, 1
0x18005f01d  setnz   bl
0x18005f020  mov     rcx, [rbp+arg_10]
0x18005f024  test    rcx, rcx
0x18005f027  jz      short loc_18005F032
0x18005f029  mov     rax, [rbp+arg_18]
0x18005f02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f032  lea     rcx, [rbp+arg_8]
0x18005f036  call    ?InternalRelease@?$ComPtr@UIPlatformDiagnosticsAndUsageDataSettingsStatics@Profile@System@Windows@ABI@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ABI::Windows::System::Profile::IPlatformDiagnosticsAndUsageDataSettingsStatics>::InternalRelease(void)
0x18005f03b  mov     rax, r13
0x18005f03e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f043  mov     rcx, r14; hLibModule
0x18005f046  call    cs:__imp_FreeLibrary
0x18005f04c  mov     rcx, rsi; hLibModule
0x18005f04f  call    cs:__imp_FreeLibrary
0x18005f055  test    dil, dil
0x18005f058  jnz     loc_18005F1BB
0x18005f05e  mov     r14d, 800h
0x18005f064  mov     r9d, 295Ah; unsigned __int16
0x18005f06a  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18005f06f  test    al, al
0x18005f071  jnz     loc_18005F1BB
0x18005f077  mov     r15d, 4
0x18005f07d  mov     [rbp+arg_0], 0
0x18005f084  lea     rax, [rbp+arg_8]
0x18005f088  mov     dword ptr [rbp+arg_8], r15d
0x18005f08c  mov     [rsp+48h+pcbData], rax; pcbData
0x18005f091  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x18005f098  lea     rax, [rbp+arg_0]
0x18005f09c  mov     rsi, 0FFFFFFFF80000002h
0x18005f0a3  mov     [rsp+48h+pvData], rax; pvData
0x18005f0a8  lea     edi, [r15+0Ch]
0x18005f0ac  mov     r9d, edi; dwFlags
0x18005f0af  mov     [rsp+48h+pdwType], 0; pdwType
0x18005f0b8  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18005f0bf  mov     rcx, rsi; hkey
0x18005f0c2  call    cs:__imp_RegGetValueW
0x18005f0c8  test    eax, eax
0x18005f0ca  jz      short loc_18005F145
0x18005f0cc  lea     rax, [rbp+arg_8]
0x18005f0d0  mov     r9d, edi; dwFlags
0x18005f0d3  mov     [rsp+48h+pcbData], rax; pcbData
0x18005f0d8  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x18005f0df  lea     rax, [rbp+arg_0]
0x18005f0e3  mov     rcx, rsi; hkey
0x18005f0e6  mov     [rsp+48h+pvData], rax; pvData
0x18005f0eb  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18005f0f2  mov     [rsp+48h+pdwType], 0; pdwType
0x18005f0fb  call    cs:__imp_RegGetValueW
0x18005f101  test    eax, eax
0x18005f103  jz      short loc_18005F145
0x18005f105  lea     rax, [rbp+arg_8]
0x18005f109  mov     [rbp+arg_0], r15d
0x18005f10d  mov     [rsp+48h+pcbData], rax; pcbData
0x18005f112  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x18005f119  lea     rax, [rbp+arg_0]
0x18005f11d  mov     r9d, edi; dwFlags
0x18005f120  mov     [rsp+48h+pvData], rax; pvData
0x18005f125  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18005f12c  mov     rcx, rsi; hkey
0x18005f12f  mov     [rsp+48h+pdwType], 0; pdwType
0x18005f138  call    cs:__imp_RegGetValueW
0x18005f13e  test    eax, 0FFFFFFFDh
0x18005f143  jnz     short loc_18005F1BB
0x18005f145  mov     eax, [rbp+arg_0]
0x18005f148  test    eax, eax
0x18005f14a  jnz     short loc_18005F1B7
0x18005f14c  mov     r8d, r14d; dwFlags
0x18005f14f  lea     rcx, aSlcDll; "slc.dll"
0x18005f156  xor     edx, edx; hFile
0x18005f158  call    cs:__imp_LoadLibraryExW
0x18005f15e  mov     rbx, rax
0x18005f161  test    rax, rax
0x18005f164  jz      short loc_18005F1B2
0x18005f166  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x18005f16d  mov     rcx, rax; hModule
0x18005f170  xor     dil, dil
0x18005f173  call    cs:__imp_GetProcAddress
0x18005f179  test    rax, rax
0x18005f17c  jz      short loc_18005F1A1
0x18005f17e  lea     rdx, [rbp+arg_10]
0x18005f182  mov     dword ptr [rbp+arg_10], 0
0x18005f189  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x18005f190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f195  test    eax, eax
0x18005f197  js      short loc_18005F1A1
0x18005f199  cmp     dword ptr [rbp+arg_10], 1
0x18005f19d  setz    dil
0x18005f1a1  mov     rcx, rbx; hLibModule
0x18005f1a4  call    cs:__imp_FreeLibrary
0x18005f1aa  mov     eax, [rbp+arg_0]
0x18005f1ad  test    dil, dil
0x18005f1b0  jnz     short loc_18005F1B7
0x18005f1b2  mov     eax, 1
0x18005f1b7  and     al, 1
0x18005f1b9  jmp     short loc_18005F1BD
0x18005f1bb  mov     al, bl
0x18005f1bd  add     rsp, 48h
0x18005f1c1  pop     r15
0x18005f1c3  pop     r14
0x18005f1c5  pop     r13
0x18005f1c7  pop     r12
0x18005f1c9  pop     rdi
0x18005f1ca  pop     rsi
0x18005f1cb  pop     rbx
0x18005f1cc  pop     rbp
0x18005f1cd  retn
```
