# TelemetryPermissionsDownlevel::IsWin10TelemetryTypeAllowed(TelemetryType)

- ea: `0x18001de58`
- end: `0x18001e1f9`
- name: `?IsWin10TelemetryTypeAllowed@TelemetryPermissionsDownlevel@@CA_NW4TelemetryType@@@Z`
- size: `929`
- prototype: `bool __fastcall(int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001cc9c`

## callees

- `0x18001de58`
- `0x18001e200`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001de86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001dedb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001def9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e183`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001de86`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001dedb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001def9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e183`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dec0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e071`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e07a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e1cf`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001dec0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e071`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e07a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e1cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e19e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001de9e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df15`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df29`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df50`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df63`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001e19e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e0ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e126`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e163`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e0ed`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e126`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001e163`

## string_xrefs

- `0x18001de75`: `DiagnosticDataSettings.dll`
- `0x18001ded2`: `api-ms-win-core-winrt-l1-1-0.dll`
- `0x18001def0`: `api-ms-win-core-winrt-string-l1-1-0.dll`
- `0x18001df43`: `WindowsCreateString`
- `0x18001df56`: `WindowsDeleteString`
- `0x18001e17a`: `slc.dll`

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
0x18001de58  mov     [rsp-40h+arg_0], ecx
0x18001de5c  push    rbp
0x18001de5d  push    rbx
0x18001de5e  push    rsi
0x18001de5f  push    rdi
0x18001de60  push    r12
0x18001de62  push    r13
0x18001de64  push    r14
0x18001de66  push    r15
0x18001de68  mov     rbp, rsp
0x18001de6b  sub     rsp, 48h
0x18001de6f  mov     r14d, 800h
0x18001de75  lea     rcx, aDiagnosticdata; "DiagnosticDataSettings.dll"
0x18001de7c  mov     r8d, r14d; dwFlags
0x18001de7f  xor     edx, edx; hFile
0x18001de81  xor     bl, bl
0x18001de83  xor     sil, sil
0x18001de86  call    cs:__imp_LoadLibraryExW
0x18001de8c  mov     rdi, rax
0x18001de8f  test    rax, rax
0x18001de92  jz      short loc_18001DECF
0x18001de94  lea     rdx, aTelistelemetry; "TelIsTelemetryTypeAllowed"
0x18001de9b  mov     rcx, rax; hModule
0x18001de9e  call    cs:__imp_GetProcAddress
0x18001dea4  test    rax, rax
0x18001dea7  jz      short loc_18001DEBD
0x18001dea9  mov     ecx, 1
0x18001deae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001deb3  test    eax, eax
0x18001deb5  js      short loc_18001DEBD
0x18001deb7  mov     sil, 1
0x18001deba  setz    bl
0x18001debd  mov     rcx, rdi; hLibModule
0x18001dec0  call    cs:__imp_FreeLibrary
0x18001dec6  test    sil, sil
0x18001dec9  jnz     loc_18001E1E6
0x18001decf  mov     r8d, r14d; dwFlags
0x18001ded2  lea     rcx, aApiMsWinCoreWi_0; "api-ms-win-core-winrt-l1-1-0.dll"
0x18001ded9  xor     edx, edx; hFile
0x18001dedb  call    cs:__imp_LoadLibraryExW
0x18001dee1  mov     rdi, rax
0x18001dee4  test    rax, rax
0x18001dee7  jz      loc_18001E08F
0x18001deed  mov     r8d, r14d; dwFlags
0x18001def0  lea     rcx, aApiMsWinCoreWi; "api-ms-win-core-winrt-string-l1-1-0.dll"
0x18001def7  xor     edx, edx; hFile
0x18001def9  call    cs:__imp_LoadLibraryExW
0x18001deff  mov     r14, rax
0x18001df02  test    rax, rax
0x18001df05  jz      loc_18001E077
0x18001df0b  lea     rdx, aRoinitialize; "RoInitialize"
0x18001df12  mov     rcx, rdi; hModule
0x18001df15  call    cs:__imp_GetProcAddress
0x18001df1b  lea     rdx, aRouninitialize; "RoUninitialize"
0x18001df22  mov     rcx, rdi; hModule
0x18001df25  mov     [rbp+arg_8], rax
0x18001df29  call    cs:__imp_GetProcAddress
0x18001df2f  lea     rdx, aRogetactivatio; "RoGetActivationFactory"
0x18001df36  mov     rcx, rdi; hModule
0x18001df39  mov     [rbp+arg_18], rax
0x18001df3d  call    cs:__imp_GetProcAddress
0x18001df43  lea     rdx, aWindowscreates; "WindowsCreateString"
0x18001df4a  mov     rcx, r14; hModule
0x18001df4d  mov     r12, rax
0x18001df50  call    cs:__imp_GetProcAddress
0x18001df56  lea     rdx, aWindowsdeletes; "WindowsDeleteString"
0x18001df5d  mov     rcx, r14; hModule
0x18001df60  mov     r15, rax
0x18001df63  call    cs:__imp_GetProcAddress
0x18001df69  mov     r13, rax
0x18001df6c  mov     rax, [rbp+arg_8]
0x18001df70  test    rax, rax
0x18001df73  jz      loc_18001E06E
0x18001df79  cmp     [rbp+arg_18], 0
0x18001df7e  jz      loc_18001E06E
0x18001df84  test    r12, r12
0x18001df87  jz      loc_18001E06E
0x18001df8d  test    r15, r15
0x18001df90  jz      loc_18001E06E
0x18001df96  test    r13, r13
0x18001df99  jz      loc_18001E06E
0x18001df9f  mov     ecx, 1
0x18001dfa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfa9  xor     ecx, ecx
0x18001dfab  test    eax, eax
0x18001dfad  js      loc_18001E06E
0x18001dfb3  mov     [rbp+arg_10], rcx
0x18001dfb7  lea     edx, [rcx+3Eh]
0x18001dfba  mov     [rbp+arg_8], rcx
0x18001dfbe  lea     r8, [rbp+arg_10]
0x18001dfc2  mov     byte ptr [rbp+arg_0], cl
0x18001dfc5  mov     rax, r15
0x18001dfc8  lea     rcx, ?RuntimeClass_Windows_System_Profile_PlatformDiagnosticsAndUsageDataSettings@@3QBGB; "Windows.System.Profile.PlatformDiagnost"...
0x18001dfcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dfd4  test    eax, eax
0x18001dfd6  js      short loc_18001E037
0x18001dfd8  mov     rcx, [rbp+arg_8]
0x18001dfdc  test    rcx, rcx
0x18001dfdf  jz      short loc_18001DFF5
0x18001dfe1  mov     [rbp+arg_8], 0
0x18001dfe9  mov     rdx, [rcx]
0x18001dfec  mov     rax, [rdx+10h]
0x18001dff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dff5  mov     rcx, [rbp+arg_10]
0x18001dff9  lea     r8, [rbp+arg_8]
0x18001dffd  lea     rdx, _GUID_b6e24c1b_7b1c_4b32_8c62_a66597ce723a
0x18001e004  mov     rax, r12
0x18001e007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e00c  test    eax, eax
0x18001e00e  js      short loc_18001E037
0x18001e010  mov     rcx, [rbp+arg_8]
0x18001e014  lea     r8, [rbp+arg_0]
0x18001e018  mov     edx, 1
0x18001e01d  mov     rax, [rcx]
0x18001e020  mov     rax, [rax+48h]
0x18001e024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e029  test    eax, eax
0x18001e02b  js      short loc_18001E037
0x18001e02d  cmp     byte ptr [rbp+arg_0], 0
0x18001e031  mov     sil, 1
0x18001e034  setnz   bl
0x18001e037  mov     rcx, [rbp+arg_10]
0x18001e03b  test    rcx, rcx
0x18001e03e  jz      short loc_18001E048
0x18001e040  mov     rax, r13
0x18001e043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e048  mov     rcx, [rbp+arg_8]
0x18001e04c  test    rcx, rcx
0x18001e04f  jz      short loc_18001E065
0x18001e051  mov     [rbp+arg_8], 0
0x18001e059  mov     rdx, [rcx]
0x18001e05c  mov     rax, [rdx+10h]
0x18001e060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e065  mov     rax, [rbp+arg_18]
0x18001e069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e06e  mov     rcx, r14; hLibModule
0x18001e071  call    cs:__imp_FreeLibrary
0x18001e077  mov     rcx, rdi; hLibModule
0x18001e07a  call    cs:__imp_FreeLibrary
0x18001e080  test    sil, sil
0x18001e083  jnz     loc_18001E1E6
0x18001e089  mov     r14d, 800h
0x18001e08f  mov     r9d, 295Ah; unsigned __int16
0x18001e095  call    ?IsWindowsVersionOrGreaterEx@@YA_NGGGG@Z; IsWindowsVersionOrGreaterEx(ushort,ushort,ushort,ushort)
0x18001e09a  test    al, al
0x18001e09c  jnz     loc_18001E1E6
0x18001e0a2  mov     r15d, 4
0x18001e0a8  mov     [rbp+arg_0], 0
0x18001e0af  lea     rax, [rbp+arg_8]
0x18001e0b3  mov     dword ptr [rbp+arg_8], r15d
0x18001e0b7  mov     [rsp+48h+pcbData], rax; pcbData
0x18001e0bc  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x18001e0c3  lea     rax, [rbp+arg_0]
0x18001e0c7  mov     rsi, 0FFFFFFFF80000002h
0x18001e0ce  mov     [rsp+48h+pvData], rax; pvData
0x18001e0d3  lea     edi, [r15+0Ch]
0x18001e0d7  mov     r9d, edi; dwFlags
0x18001e0da  mov     [rsp+48h+pdwType], 0; pdwType
0x18001e0e3  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001e0ea  mov     rcx, rsi; hkey
0x18001e0ed  call    cs:__imp_RegGetValueW
0x18001e0f3  test    eax, eax
0x18001e0f5  jz      short loc_18001E170
0x18001e0f7  lea     rax, [rbp+arg_8]
0x18001e0fb  mov     r9d, edi; dwFlags
0x18001e0fe  mov     [rsp+48h+pcbData], rax; pcbData
0x18001e103  lea     r8, aAllowtelemetry; "AllowTelemetry_PolicyManager"
0x18001e10a  lea     rax, [rbp+arg_0]
0x18001e10e  mov     rcx, rsi; hkey
0x18001e111  mov     [rsp+48h+pvData], rax; pvData
0x18001e116  lea     rdx, aSoftwarePolici; "SOFTWARE\\Policies\\Microsoft\\Windows"...
0x18001e11d  mov     [rsp+48h+pdwType], 0; pdwType
0x18001e126  call    cs:__imp_RegGetValueW
0x18001e12c  test    eax, eax
0x18001e12e  jz      short loc_18001E170
0x18001e130  lea     rax, [rbp+arg_8]
0x18001e134  mov     [rbp+arg_0], r15d
0x18001e138  mov     [rsp+48h+pcbData], rax; pcbData
0x18001e13d  lea     r8, aAllowtelemetry_0; "AllowTelemetry"
0x18001e144  lea     rax, [rbp+arg_0]
0x18001e148  mov     r9d, edi; dwFlags
0x18001e14b  mov     [rsp+48h+pvData], rax; pvData
0x18001e150  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18001e157  mov     rcx, rsi; hkey
0x18001e15a  mov     [rsp+48h+pdwType], 0; pdwType
0x18001e163  call    cs:__imp_RegGetValueW
0x18001e169  test    eax, 0FFFFFFFDh
0x18001e16e  jnz     short loc_18001E1E6
0x18001e170  mov     eax, [rbp+arg_0]
0x18001e173  test    eax, eax
0x18001e175  jnz     short loc_18001E1E2
0x18001e177  mov     r8d, r14d; dwFlags
0x18001e17a  lea     rcx, aSlcDll; "slc.dll"
0x18001e181  xor     edx, edx; hFile
0x18001e183  call    cs:__imp_LoadLibraryExW
0x18001e189  mov     rbx, rax
0x18001e18c  test    rax, rax
0x18001e18f  jz      short loc_18001E1DD
0x18001e191  lea     rdx, aSlgetwindowsin; "SLGetWindowsInformationDWORD"
0x18001e198  mov     rcx, rax; hModule
0x18001e19b  xor     dil, dil
0x18001e19e  call    cs:__imp_GetProcAddress
0x18001e1a4  test    rax, rax
0x18001e1a7  jz      short loc_18001E1CC
0x18001e1a9  lea     rdx, [rbp+arg_10]
0x18001e1ad  mov     dword ptr [rbp+arg_10], 0
0x18001e1b4  lea     rcx, aTelemetrypermi; "TelemetryPermission-AllowDisable"
0x18001e1bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1c0  test    eax, eax
0x18001e1c2  js      short loc_18001E1CC
0x18001e1c4  cmp     dword ptr [rbp+arg_10], 1
0x18001e1c8  setz    dil
0x18001e1cc  mov     rcx, rbx; hLibModule
0x18001e1cf  call    cs:__imp_FreeLibrary
0x18001e1d5  mov     eax, [rbp+arg_0]
0x18001e1d8  test    dil, dil
0x18001e1db  jnz     short loc_18001E1E2
0x18001e1dd  mov     eax, 1
0x18001e1e2  and     al, 1
0x18001e1e4  jmp     short loc_18001E1E8
0x18001e1e6  mov     al, bl
0x18001e1e8  add     rsp, 48h
0x18001e1ec  pop     r15
0x18001e1ee  pop     r14
0x18001e1f0  pop     r13
0x18001e1f2  pop     r12
0x18001e1f4  pop     rdi
0x18001e1f5  pop     rsi
0x18001e1f6  pop     rbx
0x18001e1f7  pop     rbp
0x18001e1f8  retn
```
