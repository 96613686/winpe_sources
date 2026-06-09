# CbsIsMobilePC(ulong *)

- ea: `0x18013fc0c`
- end: `0x18013ff80`
- name: `?CbsIsMobilePC@@YAJPEAK@Z`
- size: `884`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180138638`

## callees

- `0x180013250`
- `0x1800150c0`
- `0x180015420`
- `0x180016d40`
- `0x180049ec0`
- `0x18005aa38`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800eb920`
- `0x1800ec920`
- `0x18013fc0c`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013fe9f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18013fe9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013fc84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013fdf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013feb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013fc84`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013fdf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18013feb0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18013fdcd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18013fdcd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18013fc70`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x18013fc70`

## string_xrefs

- `0x18013fda1`: `system32\`
- `0x18013fd9a`: `powrprof.dll`
- `0x18013fca3`: `Failed to get windows directory for powrprof.dll path.`
- `0x18013fe13`: `Failed to acquire a handle to powrprof.dll`

## pseudocode

```c
int __fastcall CbsIsMobilePC(unsigned int *a1)
{
  UINT SystemWindowsDirectoryW; // eax
  signed int v4; // ebx
  unsigned int v5; // eax
  int v6; // ebx
  int v7; // eax
  __int64 v8; // rdx
  HMODULE LibraryW; // rax
  signed int LastError; // ebx
  unsigned int v11; // eax
  __int64 v12; // rdx
  __int64 (*ProcAddress)(void); // rax
  unsigned int v14; // eax
  unsigned int v15; // [rsp+20h] [rbp-E0h]
  unsigned int v16; // [rsp+30h] [rbp-D0h] BYREF
  LPCWSTR lpLibFileName; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE hModule; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v19[2]; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  if ( dword_1803AF5D0 != -1 )
  {
    *a1 = dword_1803AF5D0;
    return 0;
  }
  *a1 = -1;
  memset_0(Buffer, 0, 0x208u);
  SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(Buffer, 0x104u);
  if ( SystemWindowsDirectoryW )
  {
    if ( SystemWindowsDirectoryW >= 0x104 )
    {
      v6 = -2147024774;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsperfhelper.cpp",
        (const char *)0x8007007ALL,
        v15);
      return v6;
    }
    lpLibFileName = 0;
    v7 = SczAllocFromSz(&lpLibFileName, Buffer);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 166;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecore\\base\\cbs\\core\\cbsperfhelper.cpp",
        (const char *)(unsigned int)v7,
        v15);
LABEL_40:
      Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(&lpLibFileName);
      return v6;
    }
    v7 = SczEnsureBackslashTerminated(&lpLibFileName);
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 168;
      goto LABEL_18;
    }
    v7 = SczAllocConcat2Sz(&lpLibFileName, L"system32\\", L"powrprof.dll");
    v6 = v7;
    if ( v7 < 0 )
    {
      v8 = 170;
      goto LABEL_18;
    }
    hModule = 0;
    LibraryW = LoadLibraryW(lpLibFileName);
    Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(&hModule, LibraryW);
    if ( hModule )
    {
      ProcAddress = GetProcAddress(hModule, "PowerDeterminePlatformRole");
      if ( ProcAddress )
      {
        dword_1803AF5D0 = ProcAddress() == 2;
        *a1 = dword_1803AF5D0;
      }
      else
      {
        LastError = GetLastError();
        if ( LogAdapter::g_Logger )
        {
          LogAdapter::Logger::LogNumObjects<>(
            (__int64)LogAdapter::g_Logger,
            0,
            3,
            (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to acquire platform role function pointer.");
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
          else
            v14 = LastError;
          v16 = v14;
          *(_QWORD *)v19 = &v16;
          LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
            (__int64)LogAdapter::g_Logger,
            1,
            3,
            (__int64)": {0}",
            (__int64)v19);
        }
        if ( LastError )
        {
          v12 = 178;
          goto LABEL_29;
        }
      }
    }
    else
    {
      LastError = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to acquire a handle to powrprof.dll");
        if ( LastError > 0 )
          v11 = (unsigned __int16)LastError | 0x80070000;
        else
          v11 = LastError;
        v16 = v11;
        *(_QWORD *)v19 = &v16;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v19);
      }
      if ( LastError )
      {
        v12 = 174;
LABEL_29:
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v12,
               (unsigned int)"onecore\\base\\cbs\\core\\cbsperfhelper.cpp",
               (const char *)(unsigned int)LastError,
               v15);
        Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
        goto LABEL_40;
      }
    }
    Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&void Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(&hModule);
    v6 = 0;
    goto LABEL_40;
  }
  v4 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to get windows directory for powrprof.dll path.");
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    else
      v5 = v4;
    v16 = v5;
    lpLibFileName = (LPCWSTR)&v16;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)&lpLibFileName);
  }
  if ( !v4 )
    return 0;
  return wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0xA1,
           (unsigned int)"onecore\\base\\cbs\\core\\cbsperfhelper.cpp",
           (const char *)(unsigned int)v4,
           v15);
}

```

## disassembly

```asm
0x18013fc0c  mov     [rsp-8+arg_8], rbx
0x18013fc11  mov     [rsp-8+arg_10], rdi
0x18013fc16  push    rbp
0x18013fc17  lea     rbp, [rsp-170h]
0x18013fc1f  sub     rsp, 270h
0x18013fc26  mov     rax, cs:__security_cookie
0x18013fc2d  xor     rax, rsp
0x18013fc30  mov     [rbp+170h+var_10], rax
0x18013fc37  mov     eax, cs:dword_1803AF5D0
0x18013fc3d  mov     rdi, rcx
0x18013fc40  or      ecx, 0FFFFFFFFh
0x18013fc43  cmp     eax, ecx
0x18013fc45  jz      short loc_18013FC50
0x18013fc47  mov     [rdi], eax
0x18013fc49  xor     eax, eax
0x18013fc4b  jmp     loc_18013FF5B
0x18013fc50  mov     [rdi], ecx
0x18013fc52  xor     edx, edx; Val
0x18013fc54  lea     rcx, [rsp+270h+Buffer]; void *
0x18013fc59  mov     r8d, 208h; Size
0x18013fc5f  call    memset_0
0x18013fc64  mov     ebx, 104h
0x18013fc69  lea     rcx, [rsp+270h+Buffer]; lpBuffer
0x18013fc6e  mov     edx, ebx; uSize
0x18013fc70  call    cs:__imp_GetSystemWindowsDirectoryW
0x18013fc77  nop     dword ptr [rax+rax+00h]
0x18013fc7c  test    eax, eax
0x18013fc7e  jnz     loc_18013FD1C
0x18013fc84  call    cs:__imp_GetLastError
0x18013fc8b  nop     dword ptr [rax+rax+00h]
0x18013fc90  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013fc97  mov     ebx, eax
0x18013fc99  test    rcx, rcx
0x18013fc9c  jz      short loc_18013FCF4
0x18013fc9e  mov     edi, 3
0x18013fca3  lea     r9, aFailedToGetWin_3; "Failed to get windows directory for pow"...
0x18013fcaa  mov     r8d, edi
0x18013fcad  xor     edx, edx
0x18013fcaf  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013fcb4  test    ebx, ebx
0x18013fcb6  jg      short loc_18013FCBC
0x18013fcb8  mov     eax, ebx
0x18013fcba  jmp     short loc_18013FCC4
0x18013fcbc  movzx   eax, bx
0x18013fcbf  or      eax, 80070000h
0x18013fcc4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013fccb  lea     r9, a0; ": {0}"
0x18013fcd2  mov     [rsp+270h+var_240], eax
0x18013fcd6  mov     r8d, edi
0x18013fcd9  lea     rax, [rsp+270h+var_240]
0x18013fcde  mov     dl, 1
0x18013fce0  mov     [rsp+270h+lpLibFileName], rax
0x18013fce5  lea     rax, [rsp+270h+lpLibFileName]
0x18013fcea  mov     qword ptr [rsp+270h+var_250], rax; unsigned int
0x18013fcef  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013fcf4  test    ebx, ebx
0x18013fcf6  jz      loc_18013FC49
0x18013fcfc  mov     rcx, [rbp+178h]; this
0x18013fd03  lea     r8, aOnecoreBaseCbs_155; "onecore\\base\\cbs\\core\\cbsperfhelper"...
0x18013fd0a  mov     r9d, ebx; char *
0x18013fd0d  mov     edx, 0A1h; void *
0x18013fd12  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013fd17  jmp     loc_18013FF5B
0x18013fd1c  cmp     eax, ebx
0x18013fd1e  jb      short loc_18013FD45
0x18013fd20  mov     rcx, [rbp+178h]; this
0x18013fd27  lea     r8, aOnecoreBaseCbs_155; "onecore\\base\\cbs\\core\\cbsperfhelper"...
0x18013fd2e  mov     ebx, 8007007Ah
0x18013fd33  mov     edx, 0A2h; void *
0x18013fd38  mov     r9d, ebx; char *
0x18013fd3b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013fd40  jmp     loc_18013FF59
0x18013fd45  lea     rdx, [rsp+270h+Buffer]
0x18013fd4a  mov     [rsp+270h+lpLibFileName], 0
0x18013fd53  lea     rcx, [rsp+270h+lpLibFileName]
0x18013fd58  call    SczAllocFromSz
0x18013fd5d  mov     ebx, eax
0x18013fd5f  test    eax, eax
0x18013fd61  jns     short loc_18013FD6A
0x18013fd63  mov     edx, 0A6h
0x18013fd68  jmp     short loc_18013FD7F
0x18013fd6a  lea     rcx, [rsp+270h+lpLibFileName]
0x18013fd6f  call    SczEnsureBackslashTerminated
0x18013fd74  mov     ebx, eax
0x18013fd76  test    eax, eax
0x18013fd78  jns     short loc_18013FD9A
0x18013fd7a  mov     edx, 0A8h; void *
0x18013fd7f  mov     rcx, [rbp+178h]; this
0x18013fd86  lea     r8, aOnecoreBaseCbs_155; "onecore\\base\\cbs\\core\\cbsperfhelper"...
0x18013fd8d  mov     r9d, eax; char *
0x18013fd90  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013fd95  jmp     loc_18013FF4F
0x18013fd9a  lea     r8, aPowrprofDll; "powrprof.dll"
0x18013fda1  lea     rdx, aSystem32; "system32\\"
0x18013fda8  lea     rcx, [rsp+270h+lpLibFileName]
0x18013fdad  call    SczAllocConcat2Sz
0x18013fdb2  mov     ebx, eax
0x18013fdb4  test    eax, eax
0x18013fdb6  jns     short loc_18013FDBF
0x18013fdb8  mov     edx, 0AAh
0x18013fdbd  jmp     short loc_18013FD7F
0x18013fdbf  mov     rcx, [rsp+270h+lpLibFileName]; lpLibFileName
0x18013fdc4  mov     [rsp+270h+hModule], 0
0x18013fdcd  call    cs:__imp_LoadLibraryW
0x18013fdd4  nop     dword ptr [rax+rax+00h]
0x18013fdd9  mov     rdx, rax
0x18013fddc  lea     rcx, [rsp+270h+hModule]
0x18013fde1  call    ?TakeOwnership@?$AutoComPtr@VCCbsCancelSessionExecutionObject@@@Windows@@QEAAXPEAVCCbsCancelSessionExecutionObject@@@Z; Windows::AutoComPtr<CCbsCancelSessionExecutionObject>::TakeOwnership(CCbsCancelSessionExecutionObject *)
0x18013fde6  mov     rcx, [rsp+270h+hModule]; hModule
0x18013fdeb  test    rcx, rcx
0x18013fdee  jnz     loc_18013FE98
0x18013fdf4  call    cs:__imp_GetLastError
0x18013fdfb  nop     dword ptr [rax+rax+00h]
0x18013fe00  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013fe07  mov     ebx, eax
0x18013fe09  test    rcx, rcx
0x18013fe0c  jz      short loc_18013FE64
0x18013fe0e  mov     edi, 3
0x18013fe13  lea     r9, aFailedToAcquir_0; "Failed to acquire a handle to powrprof."...
0x18013fe1a  mov     r8d, edi
0x18013fe1d  xor     edx, edx
0x18013fe1f  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013fe24  test    ebx, ebx
0x18013fe26  jg      short loc_18013FE2C
0x18013fe28  mov     eax, ebx
0x18013fe2a  jmp     short loc_18013FE34
0x18013fe2c  movzx   eax, bx
0x18013fe2f  or      eax, 80070000h
0x18013fe34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013fe3b  lea     r9, a0; ": {0}"
0x18013fe42  mov     [rsp+270h+var_240], eax
0x18013fe46  mov     r8d, edi
0x18013fe49  lea     rax, [rsp+270h+var_240]
0x18013fe4e  mov     dl, 1
0x18013fe50  mov     qword ptr [rsp+270h+var_228], rax
0x18013fe55  lea     rax, [rsp+270h+var_228]
0x18013fe5a  mov     qword ptr [rsp+270h+var_250], rax; unsigned int
0x18013fe5f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013fe64  test    ebx, ebx
0x18013fe66  jz      loc_18013FF43
0x18013fe6c  mov     edx, 0AEh; void *
0x18013fe71  mov     rcx, [rbp+178h]; this
0x18013fe78  lea     r8, aOnecoreBaseCbs_155; "onecore\\base\\cbs\\core\\cbsperfhelper"...
0x18013fe7f  mov     r9d, ebx; char *
0x18013fe82  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18013fe87  lea     rcx, [rsp+270h+hModule]
0x18013fe8c  mov     ebx, eax
0x18013fe8e  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18013fe93  jmp     loc_18013FF4F
0x18013fe98  lea     rdx, aPowerdetermine; "PowerDeterminePlatformRole"
0x18013fe9f  call    cs:__imp_GetProcAddress
0x18013fea6  nop     dword ptr [rax+rax+00h]
0x18013feab  test    rax, rax
0x18013feae  jnz     short loc_18013FF2E
0x18013feb0  call    cs:__imp_GetLastError
0x18013feb7  nop     dword ptr [rax+rax+00h]
0x18013febc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013fec3  mov     ebx, eax
0x18013fec5  test    rcx, rcx
0x18013fec8  jz      short loc_18013FF20
0x18013feca  mov     edi, 3
0x18013fecf  lea     r9, aFailedToAcquir_4; "Failed to acquire platform role functio"...
0x18013fed6  mov     r8d, edi
0x18013fed9  xor     edx, edx
0x18013fedb  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18013fee0  test    ebx, ebx
0x18013fee2  jg      short loc_18013FEE8
0x18013fee4  mov     eax, ebx
0x18013fee6  jmp     short loc_18013FEF0
0x18013fee8  movzx   eax, bx
0x18013feeb  or      eax, 80070000h
0x18013fef0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18013fef7  lea     r9, a0; ": {0}"
0x18013fefe  mov     [rsp+270h+var_240], eax
0x18013ff02  mov     r8d, edi
0x18013ff05  lea     rax, [rsp+270h+var_240]
0x18013ff0a  mov     dl, 1
0x18013ff0c  mov     qword ptr [rsp+270h+var_228], rax
0x18013ff11  lea     rax, [rsp+270h+var_228]
0x18013ff16  mov     qword ptr [rsp+270h+var_250], rax
0x18013ff1b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x18013ff20  test    ebx, ebx
0x18013ff22  jz      short loc_18013FF43
0x18013ff24  mov     edx, 0B2h
0x18013ff29  jmp     loc_18013FE71
0x18013ff2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013ff33  xor     ecx, ecx
0x18013ff35  cmp     eax, 2
0x18013ff38  setz    cl
0x18013ff3b  mov     cs:dword_1803AF5D0, ecx
0x18013ff41  mov     [rdi], ecx
0x18013ff43  lea     rcx, [rsp+270h+hModule]
0x18013ff48  call    ?Close@?$AutoGenericHandleBase@PEAUHINSTANCE__@@$0A@V?$AutoGenericHandle@PEAUHINSTANCE__@@$0A@$1?CloseWithFreeLibrary@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HINSTANCE__ *,0,Windows::AutoGenericHandle<HINSTANCE__ *,0,&Windows::Detail::CloseWithFreeLibrary(HINSTANCE__ *)>>::Close(void)
0x18013ff4d  xor     ebx, ebx
0x18013ff4f  lea     rcx, [rsp+270h+lpLibFileName]
0x18013ff54  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x18013ff59  mov     eax, ebx
0x18013ff5b  mov     rcx, [rbp+170h+var_10]
0x18013ff62  xor     rcx, rsp; StackCookie
0x18013ff65  call    __security_check_cookie
0x18013ff6a  lea     r11, [rsp+270h+var_s0]
0x18013ff72  mov     rbx, [r11+18h]
0x18013ff76  mov     rdi, [r11+20h]
0x18013ff7a  mov     rsp, r11
0x18013ff7d  pop     rbp
0x18013ff7e  retn
```
