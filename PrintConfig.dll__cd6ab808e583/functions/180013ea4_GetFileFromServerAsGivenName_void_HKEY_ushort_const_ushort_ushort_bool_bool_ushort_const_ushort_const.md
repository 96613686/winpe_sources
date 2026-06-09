# GetFileFromServerAsGivenName(void *,HKEY__ *,ushort const *,ushort *,ushort *,bool,bool,ushort const *,ushort const *)

- ea: `0x180013ea4`
- end: `0x18001421b`
- name: `?GetFileFromServerAsGivenName@@YAJPEAXPEAUHKEY__@@PEBGPEAG3_N422@Z`
- size: `887`
- prototype: `__int64 __fastcall(HANDLE hPrinter, HKEY, const unsigned __int16 *, unsigned __int16 *, LPCWSTR lpValueName, bool, bool, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180013cfc`
- `0x180016538`
- `0x180016da8`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x1800060ec`
- `0x18001053c`
- `0x180013ea4`
- `0x180014720`
- `0x180015388`
- `0x180018200`
- `0x1800183a0`
- `0x1800183f8`
- `0x180018bbc`
- `0x180018bfc`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x18001409d`
- `KERNEL32!SetFileInformationByHandle` at `0x18001409d`
- `KERNEL32!DeleteFileW` at `0x180014170`
- `KERNEL32!DeleteFileW` at `0x180014170`
- `KERNEL32!FreeLibrary` at `0x180014127`
- `KERNEL32!FreeLibrary` at `0x180014127`
- `KERNEL32!CloseHandle` at `0x1800140f9`
- `KERNEL32!CloseHandle` at `0x1800141b8`
- `KERNEL32!CloseHandle` at `0x1800140f9`
- `KERNEL32!CloseHandle` at `0x1800141b8`
- `KERNEL32!GetLastError` at `0x1800140b9`
- `KERNEL32!GetLastError` at `0x1800140b9`
- `ADVAPI32!RegSetValueExW` at `0x180014160`
- `ADVAPI32!RegSetValueExW` at `0x180014160`

## string_xrefs

- `0x18001404c`: `Resource DLL contains code (%ws).`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetFileFromServerAsGivenName(
        HANDLE hPrinter,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        LPCWSTR lpValueName,
        bool a6,
        bool a7,
        const unsigned __int16 *a8,
        unsigned __int16 *a9)
{
  int v13; // ebx
  signed int LastError; // eax
  __int64 v15; // rax
  LSTATUS v16; // edi
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  DWORD cbData; // [rsp+28h] [rbp-D8h]
  char FileInformation[8]; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hFile; // [rsp+48h] [rbp-B8h] BYREF
  int v22; // [rsp+50h] [rbp-B0h] BYREF
  HMODULE hLibModule[2]; // [rsp+58h] [rbp-A8h] BYREF
  void (*v24)(void); // [rsp+68h] [rbp-98h]
  __int64 v25; // [rsp+70h] [rbp-90h]
  WCHAR FileName[264]; // [rsp+80h] [rbp-80h] BYREF

  v25 = -2;
  memset_0(FileName, 0, 0x208u);
  hFile = 0;
  v13 = CopyFileFromPrinterData(hPrinter, a2, a3, a4, FileName, cbData, a9, (struct Win32HandleRAII *)&hFile);
  if ( v13 >= 0 )
  {
    if ( a8 )
    {
      v13 = VerifyFileUsingPrinterDataCatalog(
              hPrinter,
              a2,
              FileName,
              a8,
              (struct Win32HandleRAII *)((unsigned __int64)&hFile
                                       & -(__int64)((char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL)));
      if ( v13 < 0 )
      {
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "GetFileFromServerAsGivenName",
          L"File '%ws' failed catalog check.",
          a4);
        goto LABEL_13;
      }
    }
    if ( a7 )
    {
      if ( !IsResourceOnlyDll(
              FileName,
              (struct Win32HandleRAII *)((unsigned __int64)&hFile
                                       & -(__int64)((char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL))) )
      {
        v13 = -2147024885;
        Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
          "GetFileFromServerAsGivenName",
          L"Resource DLL contains code (%ws).",
          FileName);
LABEL_13:
        v22 = 0;
        RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &v22);
        FileInformation[0] = 1;
        if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL
          && !SetFileInformationByHandle(hFile, FileDispositionInfo, FileInformation, 1u)
          && WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && *((char *)WPP_GLOBAL_Control + 68) < 0 )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            60,
            WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids,
            (unsigned int)LastError);
        }
        if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          CloseHandle(hFile);
          hFile = 0;
        }
        if ( v24 && hLibModule[1] )
          v24();
        if ( hLibModule[0] )
          FreeLibrary(hLibModule[0]);
        goto LABEL_34;
      }
    }
    else if ( HasValidPEHeader(
                FileName,
                (struct Win32HandleRAII *)((unsigned __int64)&hFile
                                         & -(__int64)((char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL))) )
    {
      v13 = -2147024885;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 68) < 0 )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 7), 59, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids, FileName);
      }
      goto LABEL_13;
    }
    v13 = 0;
    v15 = -1;
    do
      ++v15;
    while ( a4[v15] );
    v16 = RegSetValueExW(a2, lpValueName, 0, 1u, (const BYTE *)a4, 2 * v15 + 2);
    if ( v16 )
    {
      DeleteFileW(FileName);
      if ( v16 > 0 )
        v13 = (unsigned __int16)v16 | 0x80070000;
      else
        v13 = v16;
    }
LABEL_34:
    if ( v13 >= 0 )
      goto LABEL_36;
    goto LABEL_35;
  }
  if ( a6 || v13 != -2147024894 && v13 != -2147024846 )
  {
LABEL_35:
    LODWORD(lpData) = v13;
    Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(
      "GetFileFromServerAsGivenName",
      L"Failed to retrieve %ws as %ws (hr: 0x%x).",
      a3,
      a4,
      lpData);
    goto LABEL_36;
  }
  Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
    "GetFileFromServerAsGivenName",
    L"The connection file (%ws) could not be found (hr: 0x%x), but fFailIfNotFound is not set. Ignoring error.",
    a3,
    (unsigned int)v13);
  v13 = 0;
LABEL_36:
  if ( (char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hFile);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180013ea4  push    rbp
0x180013ea6  push    rbx
0x180013ea7  push    rsi
0x180013ea8  push    rdi
0x180013ea9  push    r12
0x180013eab  push    r13
0x180013ead  push    r14
0x180013eaf  push    r15
0x180013eb1  lea     rbp, [rsp-1A8h]
0x180013eb9  sub     rsp, 2A8h
0x180013ec0  mov     [rsp+2E0h+var_270], 0FFFFFFFFFFFFFFFEh
0x180013ec9  mov     rax, cs:__security_cookie
0x180013ed0  xor     rax, rsp
0x180013ed3  mov     [rbp+1E0h+var_50], rax
0x180013eda  mov     rsi, r9
0x180013edd  mov     r13, r8
0x180013ee0  mov     r15, rdx
0x180013ee3  mov     r14, rcx
0x180013ee6  mov     r12, [rbp+1E0h+lpValueName]
0x180013eed  mov     rdi, [rbp+1E0h+arg_38]
0x180013ef4  mov     rbx, [rbp+1E0h+arg_40]
0x180013efb  xor     edx, edx; Val
0x180013efd  mov     r8d, 208h; Size
0x180013f03  lea     rcx, [rbp+1E0h+FileName]; void *
0x180013f07  call    memset_0
0x180013f0c  xor     eax, eax
0x180013f0e  mov     [rsp+2E0h+hFile], rax
0x180013f13  lea     rax, [rsp+2E0h+hFile]
0x180013f18  mov     [rsp+2E0h+var_2A8], rax; struct Win32HandleRAII *
0x180013f1d  mov     [rsp+2E0h+var_2B0], rbx; unsigned __int16 *
0x180013f22  lea     rax, [rbp+1E0h+FileName]
0x180013f26  mov     [rsp+2E0h+lpData], rax; lpFileName
0x180013f2b  mov     r9, rsi; unsigned __int16 *
0x180013f2e  mov     r8, r13; unsigned __int16 *
0x180013f31  mov     rdx, r15; HKEY
0x180013f34  mov     rcx, r14; hPrinter
0x180013f37  call    ?CopyFileFromPrinterData@@YAJPEAXPEAUHKEY__@@PEBGPEAG3K2PEAVWin32HandleRAII@@@Z; CopyFileFromPrinterData(void *,HKEY__ *,ushort const *,ushort *,ushort *,ulong,ushort const *,Win32HandleRAII *)
0x180013f3c  mov     ebx, eax
0x180013f3e  xor     eax, eax
0x180013f40  test    ebx, ebx
0x180013f42  js      loc_1800141E3
0x180013f48  test    rdi, rdi
0x180013f4b  jz      short loc_180013F98
0x180013f4d  mov     rax, [rsp+2E0h+hFile]
0x180013f52  dec     rax
0x180013f55  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013f59  setbe   al
0x180013f5c  neg     al
0x180013f5e  sbb     rdx, rdx
0x180013f61  lea     rax, [rsp+2E0h+hFile]
0x180013f66  and     rdx, rax
0x180013f69  mov     [rsp+2E0h+lpData], rdx; struct Win32HandleRAII *
0x180013f6e  mov     r9, rdi; unsigned __int16 *
0x180013f71  lea     r8, [rbp+1E0h+FileName]; unsigned __int16 *
0x180013f75  mov     rdx, r15; HKEY
0x180013f78  mov     rcx, r14; hPrinter
0x180013f7b  call    ?VerifyFileUsingPrinterDataCatalog@@YAJPEAXPEAUHKEY__@@PEBG2PEAVWin32HandleRAII@@@Z; VerifyFileUsingPrinterDataCatalog(void *,HKEY__ *,ushort const *,ushort const *,Win32HandleRAII *)
0x180013f80  mov     ebx, eax
0x180013f82  xor     r14d, r14d
0x180013f85  test    eax, eax
0x180013f87  jns     short loc_180013F9B
0x180013f89  mov     r8, rsi
0x180013f8c  lea     rdx, aFileWsFailedCa; "File '%ws' failed catalog check."
0x180013f93  jmp     loc_180014053
0x180013f98  xor     r14d, r14d
0x180013f9b  mov     dil, [rbp+1E0h+arg_30]
0x180013fa2  test    dil, dil
0x180013fa5  jnz     short loc_180014016
0x180013fa7  mov     rax, [rsp+2E0h+hFile]
0x180013fac  dec     rax
0x180013faf  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180013fb3  setbe   al
0x180013fb6  neg     al
0x180013fb8  sbb     rdx, rdx
0x180013fbb  lea     rax, [rsp+2E0h+hFile]
0x180013fc0  and     rdx, rax; struct Win32HandleRAII *
0x180013fc3  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x180013fc7  call    ?HasValidPEHeader@@YA_NPEBGPEAVWin32HandleRAII@@@Z; HasValidPEHeader(ushort const *,Win32HandleRAII *)
0x180013fcc  test    al, al
0x180013fce  jz      short loc_180014009
0x180013fd0  mov     ebx, 8007000Bh
0x180013fd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180013fdc  lea     rdi, WPP_GLOBAL_Control
0x180013fe3  cmp     rcx, rdi
0x180013fe6  jz      short loc_180014066
0x180013fe8  test    byte ptr [rcx+44h], 80h
0x180013fec  jz      short loc_180014066
0x180013fee  mov     edx, 3Bh ; ';'
0x180013ff3  lea     r9, [rbp+1E0h+FileName]
0x180013ff7  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x180013ffe  mov     rcx, [rcx+38h]
0x180014002  call    WPP_SF_S
0x180014007  jmp     short loc_180014066
0x180014009  test    ebx, ebx
0x18001400b  js      short loc_18001405F
0x18001400d  test    dil, dil
0x180014010  jz      loc_180014130
0x180014016  mov     rax, [rsp+2E0h+hFile]
0x18001401b  dec     rax
0x18001401e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014022  setbe   al
0x180014025  neg     al
0x180014027  sbb     rdx, rdx
0x18001402a  lea     rax, [rsp+2E0h+hFile]
0x18001402f  and     rdx, rax; struct Win32HandleRAII *
0x180014032  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x180014036  call    ?IsResourceOnlyDll@@YA_NPEBGPEAVWin32HandleRAII@@@Z; IsResourceOnlyDll(ushort const *,Win32HandleRAII *)
0x18001403b  test    al, al
0x18001403d  jnz     loc_180014130
0x180014043  mov     ebx, 8007000Bh
0x180014048  lea     r8, [rbp+1E0h+FileName]
0x18001404c  lea     rdx, aResourceDllCon; "Resource DLL contains code (%ws)."
0x180014053  lea     rcx, aGetfilefromser; "GetFileFromServerAsGivenName"
0x18001405a  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18001405f  lea     rdi, WPP_GLOBAL_Control
0x180014066  mov     [rsp+2E0h+var_290], r14d
0x18001406b  lea     rdx, [rsp+2E0h+var_290]; int *
0x180014070  lea     rcx, [rsp+2E0h+hLibModule]; this
0x180014075  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18001407a  mov     [rsp+2E0h+FileInformation], 1
0x18001407f  mov     rcx, [rsp+2E0h+hFile]; hFile
0x180014084  lea     rax, [rcx-1]
0x180014088  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001408c  ja      short loc_1800140EA
0x18001408e  mov     r9d, 1; dwBufferSize
0x180014094  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x180014099  lea     edx, [r9+3]; FileInformationClass
0x18001409d  call    cs:__imp_SetFileInformationByHandle
0x1800140a3  test    eax, eax
0x1800140a5  jnz     short loc_1800140EA
0x1800140a7  mov     rax, cs:WPP_GLOBAL_Control
0x1800140ae  cmp     rax, rdi
0x1800140b1  jz      short loc_1800140EA
0x1800140b3  test    byte ptr [rax+44h], 80h
0x1800140b7  jz      short loc_1800140EA
0x1800140b9  call    cs:__imp_GetLastError
0x1800140bf  test    eax, eax
0x1800140c1  jle     short loc_1800140CB
0x1800140c3  movzx   eax, ax
0x1800140c6  or      eax, 80070000h
0x1800140cb  mov     edx, 3Ch ; '<'
0x1800140d0  mov     r9d, eax
0x1800140d3  lea     r8, WPP_590161d01b393194d11d22bd3bfd07b4_Traceguids
0x1800140da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800140e1  mov     rcx, [rcx+38h]
0x1800140e5  call    WPP_SF_d
0x1800140ea  mov     rcx, [rsp+2E0h+hFile]; hObject
0x1800140ef  lea     rax, [rcx-1]
0x1800140f3  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800140f7  ja      short loc_180014104
0x1800140f9  call    cs:__imp_CloseHandle
0x1800140ff  mov     [rsp+2E0h+hFile], r14
0x180014104  mov     rax, [rsp+2E0h+var_278]
0x180014109  test    rax, rax
0x18001410c  jz      short loc_18001411D
0x18001410e  mov     rcx, [rsp+2E0h+var_280]
0x180014113  test    rcx, rcx
0x180014116  jz      short loc_18001411D
0x180014118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001411d  mov     rcx, [rsp+2E0h+hLibModule]; hLibModule
0x180014122  test    rcx, rcx
0x180014125  jz      short loc_18001412E
0x180014127  call    cs:__imp_FreeLibrary
0x18001412d  nop
0x18001412e  jmp     short loc_180014187
0x180014130  mov     ebx, r14d
0x180014133  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014137  inc     rax
0x18001413a  cmp     [rsi+rax*2], r14w
0x18001413f  jnz     short loc_180014137
0x180014141  lea     eax, ds:2[rax*2]
0x180014148  mov     [rsp+2E0h+cbData], eax; cbData
0x18001414c  mov     [rsp+2E0h+lpData], rsi; lpData
0x180014151  mov     r9d, 1; dwType
0x180014157  xor     r8d, r8d; Reserved
0x18001415a  mov     rdx, r12; lpValueName
0x18001415d  mov     rcx, r15; hKey
0x180014160  call    cs:__imp_RegSetValueExW
0x180014166  mov     edi, eax
0x180014168  test    eax, eax
0x18001416a  jz      short loc_180014187
0x18001416c  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x180014170  call    cs:__imp_DeleteFileW
0x180014176  test    edi, edi
0x180014178  jg      short loc_18001417E
0x18001417a  mov     ebx, edi
0x18001417c  jmp     short loc_180014187
0x18001417e  movzx   ebx, di
0x180014181  or      ebx, 80070000h
0x180014187  test    ebx, ebx
0x180014189  jns     short loc_1800141A9
0x18001418b  mov     dword ptr [rsp+2E0h+lpData], ebx
0x18001418f  mov     r9, rsi
0x180014192  mov     r8, r13
0x180014195  lea     rdx, aFailedToRetrie_3; "Failed to retrieve %ws as %ws (hr: 0x%x"...
0x18001419c  lea     rcx, aGetfilefromser; "GetFileFromServerAsGivenName"
0x1800141a3  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800141a8  nop
0x1800141a9  mov     rcx, [rsp+2E0h+hFile]; hObject
0x1800141ae  lea     rax, [rcx-1]
0x1800141b2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800141b6  ja      short loc_1800141BE
0x1800141b8  call    cs:__imp_CloseHandle
0x1800141be  mov     eax, ebx
0x1800141c0  mov     rcx, [rbp+1E0h+var_50]
0x1800141c7  xor     rcx, rsp; StackCookie
0x1800141ca  call    __security_check_cookie
0x1800141cf  add     rsp, 2A8h
0x1800141d6  pop     r15
0x1800141d8  pop     r14
0x1800141da  pop     r13
0x1800141dc  pop     r12
0x1800141de  pop     rdi
0x1800141df  pop     rsi
0x1800141e0  pop     rbx
0x1800141e1  pop     rbp
0x1800141e2  retn
0x1800141e3  cmp     [rbp+1E0h+arg_28], al
0x1800141e9  jnz     short loc_18001418B
0x1800141eb  cmp     ebx, 80070002h
0x1800141f1  jz      short loc_1800141FB
0x1800141f3  cmp     ebx, 80070032h
0x1800141f9  jnz     short loc_18001418B
0x1800141fb  mov     r9d, ebx
0x1800141fe  mov     r8, r13
0x180014201  lea     rdx, aTheConnectionF; "The connection file (%ws) could not be "...
0x180014208  lea     rcx, aGetfilefromser; "GetFileFromServerAsGivenName"
0x18001420f  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014214  xor     eax, eax
0x180014216  mov     ebx, eax
0x180014218  jmp     short loc_1800141A9
```
