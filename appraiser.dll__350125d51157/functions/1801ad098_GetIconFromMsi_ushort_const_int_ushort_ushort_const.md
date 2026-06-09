# GetIconFromMsi(ushort const *,int,ushort *,ushort const *)

- ea: `0x1801ad098`
- end: `0x1801ad6de`
- name: `?GetIconFromMsi@@YAJPEBGHPEAG0@Z`
- size: `1606`
- prototype: `__int64 __fastcall(LPCWSTR szDatabasePath, __int64, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1801acbdc`
- `0x1801ad6e4`

## callees

- `0x180008570`
- `0x180009e6c`
- `0x180009e84`
- `0x180093a1c`
- `0x1801ac668`
- `0x1801ad01c`
- `0x1801ad098`
- `0x18021f010`

## import_xrefs

- `KERNEL32!GetTempPathW` at `0x1801ad57a`
- `KERNEL32!GetTempPathW` at `0x1801ad57a`
- `KERNEL32!CreateFileW` at `0x1801ad16a`
- `KERNEL32!CreateFileW` at `0x1801ad5c1`
- `KERNEL32!CreateFileW` at `0x1801ad16a`
- `KERNEL32!CreateFileW` at `0x1801ad5c1`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1801ad136`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1801ad136`
- `KERNEL32!WriteFile` at `0x1801ad64a`
- `KERNEL32!WriteFile` at `0x1801ad64a`
- `KERNEL32!LoadLibraryExW` at `0x1801ad53e`
- `KERNEL32!LoadLibraryExW` at `0x1801ad5ec`
- `KERNEL32!LoadLibraryExW` at `0x1801ad53e`
- `KERNEL32!LoadLibraryExW` at `0x1801ad5ec`
- `KERNEL32!FreeLibrary` at `0x1801ad406`
- `KERNEL32!FreeLibrary` at `0x1801ad414`
- `KERNEL32!FreeLibrary` at `0x1801ad406`
- `KERNEL32!FreeLibrary` at `0x1801ad414`
- `KERNEL32!GetProcessHeap` at `0x1801ad1fc`
- `KERNEL32!GetProcessHeap` at `0x1801ad384`
- `KERNEL32!GetProcessHeap` at `0x1801ad695`
- `KERNEL32!GetProcessHeap` at `0x1801ad1fc`
- `KERNEL32!GetProcessHeap` at `0x1801ad384`
- `KERNEL32!GetProcessHeap` at `0x1801ad695`
- `KERNEL32!GetProcAddress` at `0x1801ad556`
- `KERNEL32!GetProcAddress` at `0x1801ad608`
- `KERNEL32!GetProcAddress` at `0x1801ad556`
- `KERNEL32!GetProcAddress` at `0x1801ad608`
- `KERNEL32!HeapAlloc` at `0x1801ad20d`
- `KERNEL32!HeapAlloc` at `0x1801ad396`
- `KERNEL32!HeapAlloc` at `0x1801ad20d`
- `KERNEL32!HeapAlloc` at `0x1801ad396`
- `KERNEL32!CloseHandle` at `0x1801ad65d`
- `KERNEL32!CloseHandle` at `0x1801ad6b6`
- `KERNEL32!CloseHandle` at `0x1801ad65d`
- `KERNEL32!CloseHandle` at `0x1801ad6b6`
- `KERNEL32!GetLastError` at `0x1801ad2e3`
- `KERNEL32!GetLastError` at `0x1801ad464`
- `KERNEL32!GetLastError` at `0x1801ad6c6`
- `KERNEL32!GetLastError` at `0x1801ad2e3`
- `KERNEL32!GetLastError` at `0x1801ad464`
- `KERNEL32!GetLastError` at `0x1801ad6c6`
- `KERNEL32!HeapFree` at `0x1801ad6a3`
- `KERNEL32!HeapFree` at `0x1801ad6a3`
- `SHLWAPI!PathAppendW` at `0x1801ad58f`
- `SHLWAPI!PathAppendW` at `0x1801ad58f`
- `MSI!MsiOpenDatabaseW` at `0x1801ad116`
- `MSI!MsiOpenDatabaseW` at `0x1801ad116`
- `MSI!MsiSetInternalUI` at `0x1801ad0ff`
- `MSI!MsiSetInternalUI` at `0x1801ad3f8`
- `MSI!MsiSetInternalUI` at `0x1801ad0ff`
- `MSI!MsiSetInternalUI` at `0x1801ad3f8`
- `MSI!MsiViewFetch` at `0x1801ad1bf`
- `MSI!MsiViewFetch` at `0x1801ad521`
- `MSI!MsiViewFetch` at `0x1801ad1bf`
- `MSI!MsiViewFetch` at `0x1801ad521`
- `MSI!MsiViewExecute` at `0x1801ad1a8`
- `MSI!MsiViewExecute` at `0x1801ad50a`
- `MSI!MsiViewExecute` at `0x1801ad1a8`
- `MSI!MsiViewExecute` at `0x1801ad50a`
- `MSI!MsiRecordGetStringW` at `0x1801ad1e0`
- `MSI!MsiRecordGetStringW` at `0x1801ad236`
- `MSI!MsiRecordGetStringW` at `0x1801ad1e0`
- `MSI!MsiRecordGetStringW` at `0x1801ad236`
- `MSI!MsiCloseHandle` at `0x1801ad25b`
- `MSI!MsiCloseHandle` at `0x1801ad26e`
- `MSI!MsiCloseHandle` at `0x1801ad3bd`
- `MSI!MsiCloseHandle` at `0x1801ad3d0`
- `MSI!MsiCloseHandle` at `0x1801ad3e3`
- `MSI!MsiCloseHandle` at `0x1801ad25b`
- `MSI!MsiCloseHandle` at `0x1801ad26e`
- `MSI!MsiCloseHandle` at `0x1801ad3bd`
- `MSI!MsiCloseHandle` at `0x1801ad3d0`
- `MSI!MsiCloseHandle` at `0x1801ad3e3`
- `MSI!MsiDatabaseOpenViewW` at `0x1801ad192`
- `MSI!MsiDatabaseOpenViewW` at `0x1801ad4f4`
- `MSI!MsiDatabaseOpenViewW` at `0x1801ad192`
- `MSI!MsiDatabaseOpenViewW` at `0x1801ad4f4`

## string_xrefs

- `0x1801ad531`: `kernelbase.dll`
- `0x1801ad54c`: `GetTempPath2W`
- `0x1801ad5df`: `msi.dll`
- `0x1801ad31e`: `GetIconFromMsi`
- `0x1801ad49c`: `GetIconFromMsi`
- `0x1801ad344`: `onecore\base\appcompat\shared\unmanaged\appdeviceicon\lib\appicon.cpp`
- `0x1801ad4c2`: `onecore\base\appcompat\shared\unmanaged\appdeviceicon\lib\appicon.cpp`
- `0x1801ad2fe`: `GetIconFromMsi`
- `0x1801ad47c`: `GetIconFromMsi`
- `0x1801ad5fe`: `MsiRecordReadStream`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetIconFromMsi(LPCWSTR szDatabasePath, __int64 a2, unsigned __int16 *a3, unsigned __int16 *a4)
{
  WCHAR *v4; // r15
  signed int v7; // esi
  HMODULE v8; // r12
  HMODULE v9; // r13
  INSTALLUILEVEL v10; // r14d
  __int64 FileW; // r14
  UINT StringW; // eax
  SIZE_T v13; // rbx
  HANDLE v14; // rax
  unsigned __int16 *v15; // rax
  unsigned __int16 *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  const unsigned __int16 *v19; // rax
  DWORD LastError; // edi
  __int64 v21; // rax
  int v22; // r14d
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  __int64 v25; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v27; // rax
  DWORD v29; // edi
  __int64 v30; // rbx
  struct tagLOG_PARTIAL_MSG *v31; // rax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  HMODULE v35; // rax
  FARPROC v36; // rax
  __int64 v37; // r8
  int IconFromBinary; // eax
  HANDLE v39; // rax
  MSIHANDLE hRecord; // [rsp+60h] [rbp-A0h] BYREF
  MSIHANDLE phView; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD pcchValueBuf; // [rsp+68h] [rbp-98h] BYREF
  INSTALLUILEVEL v43; // [rsp+6Ch] [rbp-94h]
  MSIHANDLE phDatabase; // [rsp+70h] [rbp-90h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned __int16 *v46; // [rsp+78h] [rbp-88h]
  WCHAR Dst[264]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE Buffer[272]; // [rsp+290h] [rbp+190h] BYREF

  v4 = 0;
  v46 = a4;
  pcchValueBuf = 0;
  NumberOfBytesWritten = 0;
  phDatabase = 0;
  v7 = -2147467259;
  phView = 0;
  hRecord = 0;
  v8 = 0;
  v9 = 0;
  v43 = MsiSetInternalUI(INSTALLUILEVEL_NONE, 0);
  v10 = v43;
  if ( !MsiOpenDatabaseW(szDatabasePath, 0, &phDatabase) )
  {
    if ( a3 )
    {
      if ( !ExpandEnvironmentStringsW(a3, Dst, 0x104u) )
        goto LABEL_33;
      FileW = (__int64)CreateFileW(Dst, 0x80000000, 0, 0, 3u, 0x80u, 0);
      if ( FileW != -1 )
      {
LABEL_64:
        CloseHandle((HANDLE)FileW);
        IconFromBinary = GetIconFromBinary(Dst, 0, v37, v46);
        v7 = 0;
        if ( IconFromBinary < 0 )
          v7 = IconFromBinary;
        if ( !v4 )
          goto LABEL_32;
        FileW = -1;
        goto LABEL_70;
      }
LABEL_19:
      if ( a3 )
      {
        v16 = a3;
        v17 = 0x7FFFFFFF;
        do
        {
          if ( !*v16 )
            break;
          ++v16;
          --v17;
        }
        while ( v17 );
        v7 = v17 == 0 ? 0x80070057 : 0;
        if ( v17 )
        {
          v18 = 0x7FFFFFFF;
          v19 = L"SELECT `Icon`.`Data` FROM `Icon` WHERE `Icon`.`Name`='%s'";
          do
          {
            if ( !*v19 )
              break;
            ++v19;
            --v18;
          }
          while ( v18 );
          v7 = v18 == 0 ? 0x80070057 : 0;
          if ( !v18 )
          {
            LastError = GetLastError();
            v21 = CurrentIP_0();
            v22 = 461;
LABEL_29:
            v23 = v21;
            v24 = ConstructPartialMsgW(0x2000000u, "[%hs] [0x%x] Failed at %d", "GetIconFromMsi", v7, v22);
            WdsSetupLogMessageW_0(
              v24,
              0,
              L"D",
              0,
              v22,
              L"onecore\\base\\appcompat\\shared\\unmanaged\\appdeviceicon\\lib\\appicon.cpp",
              L"GetIconFromMsi",
              v23,
              LastError,
              0,
              0);
LABEL_32:
            v10 = v43;
            goto LABEL_33;
          }
          v25 = ((2 * (0x7FFFFFFF - v17)) & -(__int64)(v17 != 0)) + (-(__int64)(v18 != 0) & (2 * (0x7FFFFFFF - v18)));
          ProcessHeap = GetProcessHeap();
          v27 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v25 + 4);
          v4 = v27;
          if ( !v27 )
          {
            v7 = -2147024882;
            goto LABEL_32;
          }
          v7 = StringCbPrintfW(v27, v25 + 4, L"SELECT `Icon`.`Data` FROM `Icon` WHERE `Icon`.`Name`='%s'", a3);
          if ( v7 >= 0 )
          {
            v7 = -2147467259;
            if ( !MsiDatabaseOpenViewW(phDatabase, v4, &phView)
              && !MsiViewExecute(phView, hRecord)
              && !MsiViewFetch(phView, &hRecord) )
            {
              Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
              v9 = Library;
              if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
                TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Dst);
              else
                TempPathW = GetTempPathW(0x104u, Dst);
              if ( TempPathW )
              {
                if ( PathAppendW(Dst, a3) )
                {
                  FileW = (__int64)CreateFileW(Dst, 0x40000000u, 0, 0, 2u, 0x80u, 0);
                  if ( FileW != -1 )
                  {
                    pcchValueBuf = 260;
                    while ( 1 )
                    {
                      v35 = LoadLibraryExW(L"msi.dll", 0, 0x800u);
                      v8 = v35;
                      if ( !v35 )
                        break;
                      v36 = GetProcAddress(v35, "MsiRecordReadStream");
                      if ( !v36 )
                      {
                        v7 = -2147024769;
                        goto LABEL_70;
                      }
                      if ( ((unsigned int (__fastcall *)(_QWORD, __int64, _BYTE *, DWORD *))v36)(
                             hRecord,
                             1,
                             Buffer,
                             &pcchValueBuf)
                        || !WriteFile((HANDLE)FileW, Buffer, pcchValueBuf, &NumberOfBytesWritten, 0) )
                      {
                        goto LABEL_70;
                      }
                      if ( pcchValueBuf != 260 )
                        goto LABEL_64;
                    }
                    v7 = -2147024770;
                  }
                }
              }
            }
          }
          else
          {
            v29 = GetLastError();
            v30 = CurrentIP_0();
            v31 = ConstructPartialMsgW(0x2000000u, "[%hs] [0x%x] Failed at %d", "GetIconFromMsi", v7, 470);
            WdsSetupLogMessageW_0(
              v31,
              0,
              L"D",
              0,
              470,
              L"onecore\\base\\appcompat\\shared\\unmanaged\\appdeviceicon\\lib\\appicon.cpp",
              L"GetIconFromMsi",
              v30,
              v29,
              0,
              0);
          }
LABEL_70:
          v39 = GetProcessHeap();
          HeapFree(v39, 0, v4);
          if ( FileW != -1 )
            CloseHandle((HANDLE)FileW);
          goto LABEL_32;
        }
      }
      else
      {
        v7 = -2147024809;
      }
      LastError = GetLastError();
      v21 = CurrentIP_0();
      v22 = 455;
      goto LABEL_29;
    }
    if ( !MsiDatabaseOpenViewW(
            phDatabase,
            L"SELECT `Property`.`Value` FROM `Property` WHERE `Property`.`Property`='ARPPRODUCTICON'",
            &phView)
      && !MsiViewExecute(phView, hRecord)
      && !MsiViewFetch(phView, &hRecord) )
    {
      StringW = MsiRecordGetStringW(hRecord, 1u, (LPWSTR)&szValueBuf, &pcchValueBuf);
      if ( StringW == 234 )
      {
        v13 = 2LL * ++pcchValueBuf;
        v14 = GetProcessHeap();
        v15 = (unsigned __int16 *)HeapAlloc(v14, 8u, v13);
        a3 = v15;
        if ( !v15 )
        {
          v7 = -2147024882;
          goto LABEL_33;
        }
        StringW = MsiRecordGetStringW(hRecord, 1u, v15, &pcchValueBuf);
      }
      if ( !StringW && pcchValueBuf )
      {
        FileW = -1;
        if ( phView )
        {
          MsiCloseHandle(phView);
          phView = 0;
        }
        if ( hRecord )
        {
          MsiCloseHandle(hRecord);
          hRecord = 0;
        }
        goto LABEL_19;
      }
    }
  }
LABEL_33:
  if ( hRecord )
  {
    MsiCloseHandle(hRecord);
    hRecord = 0;
  }
  if ( phView )
  {
    MsiCloseHandle(phView);
    phView = 0;
  }
  if ( phDatabase )
  {
    MsiCloseHandle(phDatabase);
    phDatabase = 0;
  }
  if ( v10 )
    MsiSetInternalUI(v10, 0);
  if ( v8 )
    FreeLibrary(v8);
  if ( v9 )
    FreeLibrary(v9);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1801ad098  mov     [rsp-8+arg_8], rbx
0x1801ad09d  push    rbp
0x1801ad09e  push    rsi
0x1801ad09f  push    rdi
0x1801ad0a0  push    r12
0x1801ad0a2  push    r13
0x1801ad0a4  push    r14
0x1801ad0a6  push    r15
0x1801ad0a8  lea     rbp, [rsp-2B0h]
0x1801ad0b0  sub     rsp, 3B0h
0x1801ad0b7  mov     rax, cs:__security_cookie
0x1801ad0be  xor     rax, rsp
0x1801ad0c1  mov     [rbp+2E0h+var_40], rax
0x1801ad0c8  xor     r15d, r15d
0x1801ad0cb  mov     [rsp+3E0h+var_368], r9
0x1801ad0d0  xor     edx, edx; phWnd
0x1801ad0d2  mov     [rsp+3E0h+pcchValueBuf], r15d
0x1801ad0d7  mov     rbx, rcx
0x1801ad0da  mov     [rsp+3E0h+NumberOfBytesWritten], r15d
0x1801ad0df  mov     rdi, r8
0x1801ad0e2  mov     [rsp+3E0h+phDatabase], r15d
0x1801ad0e7  mov     esi, 80004005h
0x1801ad0ec  mov     [rsp+3E0h+phView], r15d
0x1801ad0f1  lea     ecx, [rdx+2]; dwUILevel
0x1801ad0f4  mov     [rsp+3E0h+hRecord], r15d
0x1801ad0f9  mov     r12d, r15d
0x1801ad0fc  mov     r13d, r15d
0x1801ad0ff  call    cs:__imp_MsiSetInternalUI
0x1801ad105  lea     r8, [rsp+3E0h+phDatabase]; phDatabase
0x1801ad10a  xor     edx, edx; szPersist
0x1801ad10c  mov     rcx, rbx; szDatabasePath
0x1801ad10f  mov     [rsp+3E0h+var_374], eax
0x1801ad113  mov     r14d, eax
0x1801ad116  call    cs:__imp_MsiOpenDatabaseW
0x1801ad11c  test    eax, eax
0x1801ad11e  jnz     loc_1801AD3B5
0x1801ad124  test    rdi, rdi
0x1801ad127  jz      short loc_1801AD182
0x1801ad129  mov     r8d, 104h; nSize
0x1801ad12f  lea     rdx, [rbp+2E0h+Dst]; lpDst
0x1801ad133  mov     rcx, rdi; lpSrc
0x1801ad136  call    cs:__imp_ExpandEnvironmentStringsW
0x1801ad13c  test    eax, eax
0x1801ad13e  jz      loc_1801AD3B5
0x1801ad144  xor     ebx, ebx
0x1801ad146  lea     rcx, [rbp+2E0h+Dst]; lpFileName
0x1801ad14a  mov     [rsp+3E0h+hTemplateFile], rbx; hTemplateFile
0x1801ad14f  xor     r9d, r9d; lpSecurityAttributes
0x1801ad152  mov     [rsp+3E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1801ad15a  xor     r8d, r8d; dwShareMode
0x1801ad15d  mov     edx, 80000000h; dwDesiredAccess
0x1801ad162  mov     [rsp+3E0h+dwCreationDisposition], 3; dwCreationDisposition
0x1801ad16a  call    cs:__imp_CreateFileW
0x1801ad170  mov     r14, rax
0x1801ad173  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801ad177  jnz     loc_1801AD65A
0x1801ad17d  jmp     loc_1801AD279
0x1801ad182  mov     ecx, [rsp+3E0h+phDatabase]; hDatabase
0x1801ad186  lea     r8, [rsp+3E0h+phView]; phView
0x1801ad18b  lea     rdx, szQuery; "SELECT `Property`.`Value` FROM `Propert"...
0x1801ad192  call    cs:__imp_MsiDatabaseOpenViewW
0x1801ad198  test    eax, eax
0x1801ad19a  jnz     loc_1801AD3B5
0x1801ad1a0  mov     edx, [rsp+3E0h+hRecord]; hRecord
0x1801ad1a4  mov     ecx, [rsp+3E0h+phView]; hView
0x1801ad1a8  call    cs:__imp_MsiViewExecute
0x1801ad1ae  test    eax, eax
0x1801ad1b0  jnz     loc_1801AD3B5
0x1801ad1b6  mov     ecx, [rsp+3E0h+phView]; hView
0x1801ad1ba  lea     rdx, [rsp+3E0h+hRecord]; phRecord
0x1801ad1bf  call    cs:__imp_MsiViewFetch
0x1801ad1c5  test    eax, eax
0x1801ad1c7  jnz     loc_1801AD3B5
0x1801ad1cd  mov     ecx, [rsp+3E0h+hRecord]; hRecord
0x1801ad1d1  lea     r9, [rsp+3E0h+pcchValueBuf]; pcchValueBuf
0x1801ad1d6  lea     r8, szValueBuf; szValueBuf
0x1801ad1dd  lea     edx, [rax+1]; iField
0x1801ad1e0  call    cs:__imp_MsiRecordGetStringW
0x1801ad1e6  cmp     eax, 0EAh
0x1801ad1eb  jnz     short loc_1801AD23C
0x1801ad1ed  mov     eax, [rsp+3E0h+pcchValueBuf]
0x1801ad1f1  inc     eax
0x1801ad1f3  mov     ebx, eax
0x1801ad1f5  add     rbx, rbx
0x1801ad1f8  mov     [rsp+3E0h+pcchValueBuf], eax
0x1801ad1fc  call    cs:__imp_GetProcessHeap
0x1801ad202  mov     r8, rbx; dwBytes
0x1801ad205  mov     edx, 8; dwFlags
0x1801ad20a  mov     rcx, rax; hHeap
0x1801ad20d  call    cs:__imp_HeapAlloc
0x1801ad213  mov     rdi, rax
0x1801ad216  test    rax, rax
0x1801ad219  jnz     short loc_1801AD225
0x1801ad21b  mov     esi, 8007000Eh
0x1801ad220  jmp     loc_1801AD3B5
0x1801ad225  mov     ecx, [rsp+3E0h+hRecord]; hRecord
0x1801ad229  lea     r9, [rsp+3E0h+pcchValueBuf]; pcchValueBuf
0x1801ad22e  mov     r8, rax; szValueBuf
0x1801ad231  mov     edx, 1; iField
0x1801ad236  call    cs:__imp_MsiRecordGetStringW
0x1801ad23c  test    eax, eax
0x1801ad23e  jnz     loc_1801AD3B5
0x1801ad244  cmp     [rsp+3E0h+pcchValueBuf], r15d
0x1801ad249  jz      loc_1801AD3B5
0x1801ad24f  mov     ecx, [rsp+3E0h+phView]; hAny
0x1801ad253  or      r14, 0FFFFFFFFFFFFFFFFh
0x1801ad257  test    ecx, ecx
0x1801ad259  jz      short loc_1801AD266
0x1801ad25b  call    cs:__imp_MsiCloseHandle
0x1801ad261  mov     [rsp+3E0h+phView], r15d
0x1801ad266  mov     ecx, [rsp+3E0h+hRecord]; hAny
0x1801ad26a  test    ecx, ecx
0x1801ad26c  jz      short loc_1801AD279
0x1801ad26e  call    cs:__imp_MsiCloseHandle
0x1801ad274  mov     [rsp+3E0h+hRecord], r15d
0x1801ad279  test    rdi, rdi
0x1801ad27c  jz      loc_1801AD6C1
0x1801ad282  mov     r9d, 7FFFFFFFh
0x1801ad288  mov     rax, rdi
0x1801ad28b  mov     edx, r9d
0x1801ad28e  cmp     [rax], r15w
0x1801ad292  jz      short loc_1801AD29E
0x1801ad294  add     rax, 2
0x1801ad298  sub     rdx, 1
0x1801ad29c  jnz     short loc_1801AD28E
0x1801ad29e  mov     rax, rdx
0x1801ad2a1  mov     ecx, 80070057h
0x1801ad2a6  neg     rax
0x1801ad2a9  sbb     esi, esi
0x1801ad2ab  not     esi
0x1801ad2ad  and     esi, ecx
0x1801ad2af  test    rdx, rdx
0x1801ad2b2  jz      loc_1801AD6C6
0x1801ad2b8  mov     r8, r9
0x1801ad2bb  lea     rax, aSelectIconData; "SELECT `Icon`.`Data` FROM `Icon` WHERE "...
0x1801ad2c2  cmp     [rax], r15w
0x1801ad2c6  jz      short loc_1801AD2D2
0x1801ad2c8  add     rax, 2
0x1801ad2cc  sub     r8, 1
0x1801ad2d0  jnz     short loc_1801AD2C2
0x1801ad2d2  mov     rax, r8
0x1801ad2d5  neg     rax
0x1801ad2d8  sbb     esi, esi
0x1801ad2da  not     esi
0x1801ad2dc  and     esi, ecx
0x1801ad2de  test    r8, r8
0x1801ad2e1  jnz     short loc_1801AD35F
0x1801ad2e3  call    cs:__imp_GetLastError
0x1801ad2e9  mov     edi, eax
0x1801ad2eb  call    CurrentIP_0
0x1801ad2f0  mov     r14d, 1CDh
0x1801ad2f6  mov     r9d, esi
0x1801ad2f9  mov     [rsp+3E0h+dwCreationDisposition], r14d
0x1801ad2fe  lea     r8, aGeticonfrommsi_0; "GetIconFromMsi"
0x1801ad305  mov     ecx, 2000000h; unsigned int
0x1801ad30a  lea     rdx, aHs0xXFailedAtD; "[%hs] [0x%x] Failed at %d"
0x1801ad311  mov     rbx, rax
0x1801ad314  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801ad319  mov     [rsp+3E0h+var_390], r15d
0x1801ad31e  lea     rcx, aGeticonfrommsi; "GetIconFromMsi"
0x1801ad325  mov     [rsp+3E0h+var_398], r15
0x1801ad32a  lea     r8, aD_2; "D"
0x1801ad331  mov     [rsp+3E0h+var_3A0], edi
0x1801ad335  xor     r9d, r9d
0x1801ad338  mov     [rsp+3E0h+var_3A8], rbx
0x1801ad33d  xor     edx, edx
0x1801ad33f  mov     [rsp+3E0h+hTemplateFile], rcx
0x1801ad344  lea     rcx, aOnecoreBaseApp_94; "onecore\\base\\appcompat\\shared\\unman"...
0x1801ad34b  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], rcx
0x1801ad350  mov     rcx, rax
0x1801ad353  mov     [rsp+3E0h+dwCreationDisposition], r14d
0x1801ad358  call    WdsSetupLogMessageW_0
0x1801ad35d  jmp     short loc_1801AD3B0
0x1801ad35f  mov     rax, r9
0x1801ad362  sub     rax, r8
0x1801ad365  neg     r8
0x1801ad368  sbb     rcx, rcx
0x1801ad36b  sub     r9, rdx
0x1801ad36e  lea     rbx, [rax+rax]
0x1801ad372  add     r9, r9
0x1801ad375  and     rbx, rcx
0x1801ad378  neg     rdx
0x1801ad37b  sbb     rax, rax
0x1801ad37e  and     rax, r9
0x1801ad381  add     rbx, rax
0x1801ad384  call    cs:__imp_GetProcessHeap
0x1801ad38a  lea     r8, [rbx+4]; dwBytes
0x1801ad38e  mov     edx, 8; dwFlags
0x1801ad393  mov     rcx, rax; hHeap
0x1801ad396  call    cs:__imp_HeapAlloc
0x1801ad39c  mov     r15, rax
0x1801ad39f  test    rax, rax
0x1801ad3a2  jnz     loc_1801AD446
0x1801ad3a8  mov     esi, 8007000Eh
0x1801ad3ad  xor     r15d, r15d
0x1801ad3b0  mov     r14d, [rsp+3E0h+var_374]
0x1801ad3b5  mov     ecx, [rsp+3E0h+hRecord]; hAny
0x1801ad3b9  test    ecx, ecx
0x1801ad3bb  jz      short loc_1801AD3C8
0x1801ad3bd  call    cs:__imp_MsiCloseHandle
0x1801ad3c3  mov     [rsp+3E0h+hRecord], r15d
0x1801ad3c8  mov     ecx, [rsp+3E0h+phView]; hAny
0x1801ad3cc  test    ecx, ecx
0x1801ad3ce  jz      short loc_1801AD3DB
0x1801ad3d0  call    cs:__imp_MsiCloseHandle
0x1801ad3d6  mov     [rsp+3E0h+phView], r15d
0x1801ad3db  mov     ecx, [rsp+3E0h+phDatabase]; hAny
0x1801ad3df  test    ecx, ecx
0x1801ad3e1  jz      short loc_1801AD3EE
0x1801ad3e3  call    cs:__imp_MsiCloseHandle
0x1801ad3e9  mov     [rsp+3E0h+phDatabase], r15d
0x1801ad3ee  test    r14d, r14d
0x1801ad3f1  jz      short loc_1801AD3FE
0x1801ad3f3  xor     edx, edx; phWnd
0x1801ad3f5  mov     ecx, r14d; dwUILevel
0x1801ad3f8  call    cs:__imp_MsiSetInternalUI
0x1801ad3fe  test    r12, r12
0x1801ad401  jz      short loc_1801AD40C
0x1801ad403  mov     rcx, r12; hLibModule
0x1801ad406  call    cs:__imp_FreeLibrary
0x1801ad40c  test    r13, r13
0x1801ad40f  jz      short loc_1801AD41A
0x1801ad411  mov     rcx, r13; hLibModule
0x1801ad414  call    cs:__imp_FreeLibrary
0x1801ad41a  mov     eax, esi
0x1801ad41c  mov     rcx, [rbp+2E0h+var_40]
0x1801ad423  xor     rcx, rsp; StackCookie
0x1801ad426  call    __security_check_cookie
0x1801ad42b  mov     rbx, [rsp+3E0h+arg_8]
0x1801ad433  add     rsp, 3B0h
0x1801ad43a  pop     r15
0x1801ad43c  pop     r14
0x1801ad43e  pop     r13
0x1801ad440  pop     r12
0x1801ad442  pop     rdi
0x1801ad443  pop     rsi
0x1801ad444  pop     rbp
0x1801ad445  retn
0x1801ad446  mov     r9, rdi
0x1801ad449  lea     r8, aSelectIconData; "SELECT `Icon`.`Data` FROM `Icon` WHERE "...
0x1801ad450  lea     rdx, [rbx+4]; unsigned __int64
0x1801ad454  mov     rcx, r15; unsigned __int16 *
0x1801ad457  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1801ad45c  xor     ebx, ebx
0x1801ad45e  mov     esi, eax
0x1801ad460  test    eax, eax
0x1801ad462  jns     short loc_1801AD4E3
0x1801ad464  call    cs:__imp_GetLastError
0x1801ad46a  mov     edi, eax
0x1801ad46c  call    CurrentIP_0
0x1801ad471  mov     r9d, esi
0x1801ad474  mov     [rsp+3E0h+dwCreationDisposition], 1D6h
0x1801ad47c  lea     r8, aGeticonfrommsi_0; "GetIconFromMsi"
0x1801ad483  mov     ecx, 2000000h; unsigned int
0x1801ad488  lea     rdx, aHs0xXFailedAtD; "[%hs] [0x%x] Failed at %d"
0x1801ad48f  mov     rbx, rax
0x1801ad492  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1801ad497  mov     [rsp+3E0h+var_390], r12d
0x1801ad49c  lea     rcx, aGeticonfrommsi; "GetIconFromMsi"
0x1801ad4a3  mov     [rsp+3E0h+var_398], r12
0x1801ad4a8  lea     r8, aD_2; "D"
0x1801ad4af  mov     [rsp+3E0h+var_3A0], edi
0x1801ad4b3  xor     r9d, r9d
0x1801ad4b6  mov     [rsp+3E0h+var_3A8], rbx
0x1801ad4bb  xor     edx, edx
0x1801ad4bd  mov     [rsp+3E0h+hTemplateFile], rcx
0x1801ad4c2  lea     rcx, aOnecoreBaseApp_94; "onecore\\base\\appcompat\\shared\\unman"...
0x1801ad4c9  mov     qword ptr [rsp+3E0h+dwFlagsAndAttributes], rcx
0x1801ad4ce  mov     rcx, rax
0x1801ad4d1  mov     [rsp+3E0h+dwCreationDisposition], 1D6h
0x1801ad4d9  call    WdsSetupLogMessageW_0
0x1801ad4de  jmp     loc_1801AD695
0x1801ad4e3  mov     ecx, [rsp+3E0h+phDatabase]; hDatabase
0x1801ad4e7  lea     r8, [rsp+3E0h+phView]; phView
0x1801ad4ec  mov     rdx, r15; szQuery
0x1801ad4ef  mov     esi, 80004005h
0x1801ad4f4  call    cs:__imp_MsiDatabaseOpenViewW
0x1801ad4fa  test    eax, eax
0x1801ad4fc  jnz     loc_1801AD695
0x1801ad502  mov     edx, [rsp+3E0h+hRecord]; hRecord
0x1801ad506  mov     ecx, [rsp+3E0h+phView]; hView
0x1801ad50a  call    cs:__imp_MsiViewExecute
0x1801ad510  test    eax, eax
0x1801ad512  jnz     loc_1801AD695
0x1801ad518  mov     ecx, [rsp+3E0h+phView]; hView
0x1801ad51c  lea     rdx, [rsp+3E0h+hRecord]; phRecord
0x1801ad521  call    cs:__imp_MsiViewFetch
0x1801ad527  test    eax, eax
0x1801ad529  jnz     loc_1801AD695
0x1801ad52f  xor     edx, edx; hFile
0x1801ad531  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1801ad538  mov     r8d, 800h; dwFlags
0x1801ad53e  call    cs:__imp_LoadLibraryExW
0x1801ad544  mov     r13, rax
0x1801ad547  test    rax, rax
0x1801ad54a  jz      short loc_1801AD571
0x1801ad54c  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1801ad553  mov     rcx, rax; hModule
0x1801ad556  call    cs:__imp_GetProcAddress
0x1801ad55c  test    rax, rax
  ... truncated ...
```
