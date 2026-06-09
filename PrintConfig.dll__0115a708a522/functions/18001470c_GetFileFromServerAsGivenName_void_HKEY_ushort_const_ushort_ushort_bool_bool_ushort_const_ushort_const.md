# GetFileFromServerAsGivenName(void *,HKEY__ *,ushort const *,ushort *,ushort *,bool,bool,ushort const *,ushort const *)

- ea: `0x18001470c`
- end: `0x180014aae`
- name: `?GetFileFromServerAsGivenName@@YAJPEAXPEAUHKEY__@@PEBGPEAG3_N422@Z`
- size: `930`
- prototype: `__int64 __fastcall(HANDLE hPrinter, HKEY, const unsigned __int16 *, unsigned __int16 *, LPCWSTR lpValueName, bool, bool, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x180014558`
- `0x180016ef0`
- `0x1800177b0`

## callees

- `0x180003400`
- `0x180004558`
- `0x180006268`
- `0x180010abc`
- `0x18001470c`
- `0x180015010`
- `0x180015d08`
- `0x180018d54`
- `0x180018f00`
- `0x180018f58`
- `0x1800197b4`
- `0x1800197f8`
- `0x1801cb010`

## import_xrefs

- `KERNEL32!SetFileInformationByHandle` at `0x180014905`
- `KERNEL32!SetFileInformationByHandle` at `0x180014905`
- `KERNEL32!DeleteFileW` at `0x1800149f6`
- `KERNEL32!DeleteFileW` at `0x1800149f6`
- `KERNEL32!FreeLibrary` at `0x1800149a1`
- `KERNEL32!FreeLibrary` at `0x1800149a1`
- `KERNEL32!CloseHandle` at `0x18001496d`
- `KERNEL32!CloseHandle` at `0x180014a44`
- `KERNEL32!CloseHandle` at `0x18001496d`
- `KERNEL32!CloseHandle` at `0x180014a44`
- `KERNEL32!GetLastError` at `0x180014927`
- `KERNEL32!GetLastError` at `0x180014927`
- `ADVAPI32!RegSetValueExW` at `0x1800149e0`
- `ADVAPI32!RegSetValueExW` at `0x1800149e0`

## string_xrefs

- `0x1800148b4`: `Resource DLL contains code (%ws).`

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
              (char **)((unsigned __int64)&hFile & -(__int64)((char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL)));
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
              (void **)((unsigned __int64)&hFile & -(__int64)((char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL))) )
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
            0x3Cu,
            (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
            LastError);
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
                (void **)((unsigned __int64)&hFile & -(__int64)((char *)hFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL))) )
    {
      v13 = -2147024885;
      if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
        && *((char *)WPP_GLOBAL_Control + 68) < 0 )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          0x3Bu,
          (const GUID *)WPP_799f402e917533f804c44f52fde54aed_Traceguids,
          FileName);
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
0x18001470c  push    rbp
0x18001470e  push    rbx
0x18001470f  push    rsi
0x180014710  push    rdi
0x180014711  push    r12
0x180014713  push    r13
0x180014715  push    r14
0x180014717  push    r15
0x180014719  lea     rbp, [rsp-1A8h]
0x180014721  sub     rsp, 2A8h
0x180014728  mov     [rsp+2E0h+var_270], 0FFFFFFFFFFFFFFFEh
0x180014731  mov     rax, cs:__security_cookie
0x180014738  xor     rax, rsp
0x18001473b  mov     [rbp+1E0h+var_50], rax
0x180014742  mov     rsi, r9
0x180014745  mov     r13, r8
0x180014748  mov     r15, rdx
0x18001474b  mov     r14, rcx
0x18001474e  mov     r12, [rbp+1E0h+lpValueName]
0x180014755  mov     rdi, [rbp+1E0h+arg_38]
0x18001475c  mov     rbx, [rbp+1E0h+arg_40]
0x180014763  xor     edx, edx; Val
0x180014765  mov     r8d, 208h; Size
0x18001476b  lea     rcx, [rbp+1E0h+FileName]; void *
0x18001476f  call    memset_0
0x180014774  xor     eax, eax
0x180014776  mov     [rsp+2E0h+hFile], rax
0x18001477b  lea     rax, [rsp+2E0h+hFile]
0x180014780  mov     [rsp+2E0h+var_2A8], rax; struct Win32HandleRAII *
0x180014785  mov     [rsp+2E0h+var_2B0], rbx; unsigned __int16 *
0x18001478a  lea     rax, [rbp+1E0h+FileName]
0x18001478e  mov     [rsp+2E0h+lpData], rax; lpFileName
0x180014793  mov     r9, rsi; unsigned __int16 *
0x180014796  mov     r8, r13; unsigned __int16 *
0x180014799  mov     rdx, r15; HKEY
0x18001479c  mov     rcx, r14; hPrinter
0x18001479f  call    ?CopyFileFromPrinterData@@YAJPEAXPEAUHKEY__@@PEBGPEAG3K2PEAVWin32HandleRAII@@@Z; CopyFileFromPrinterData(void *,HKEY__ *,ushort const *,ushort *,ushort *,ulong,ushort const *,Win32HandleRAII *)
0x1800147a4  mov     ebx, eax
0x1800147a6  xor     eax, eax
0x1800147a8  test    ebx, ebx
0x1800147aa  js      loc_180014A76
0x1800147b0  test    rdi, rdi
0x1800147b3  jz      short loc_180014800
0x1800147b5  mov     rax, [rsp+2E0h+hFile]
0x1800147ba  dec     rax
0x1800147bd  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800147c1  setbe   al
0x1800147c4  neg     al
0x1800147c6  sbb     rdx, rdx
0x1800147c9  lea     rax, [rsp+2E0h+hFile]
0x1800147ce  and     rdx, rax
0x1800147d1  mov     [rsp+2E0h+lpData], rdx; struct Win32HandleRAII *
0x1800147d6  mov     r9, rdi; unsigned __int16 *
0x1800147d9  lea     r8, [rbp+1E0h+FileName]; unsigned __int16 *
0x1800147dd  mov     rdx, r15; HKEY
0x1800147e0  mov     rcx, r14; hPrinter
0x1800147e3  call    ?VerifyFileUsingPrinterDataCatalog@@YAJPEAXPEAUHKEY__@@PEBG2PEAVWin32HandleRAII@@@Z; VerifyFileUsingPrinterDataCatalog(void *,HKEY__ *,ushort const *,ushort const *,Win32HandleRAII *)
0x1800147e8  mov     ebx, eax
0x1800147ea  xor     r14d, r14d
0x1800147ed  test    eax, eax
0x1800147ef  jns     short loc_180014803
0x1800147f1  mov     r8, rsi
0x1800147f4  lea     rdx, aFileWsFailedCa; "File '%ws' failed catalog check."
0x1800147fb  jmp     loc_1800148BB
0x180014800  xor     r14d, r14d
0x180014803  mov     dil, [rbp+1E0h+arg_30]
0x18001480a  test    dil, dil
0x18001480d  jnz     short loc_18001487E
0x18001480f  mov     rax, [rsp+2E0h+hFile]
0x180014814  dec     rax
0x180014817  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001481b  setbe   al
0x18001481e  neg     al
0x180014820  sbb     rdx, rdx
0x180014823  lea     rax, [rsp+2E0h+hFile]
0x180014828  and     rdx, rax; struct Win32HandleRAII *
0x18001482b  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x18001482f  call    ?HasValidPEHeader@@YA_NPEBGPEAVWin32HandleRAII@@@Z; HasValidPEHeader(ushort const *,Win32HandleRAII *)
0x180014834  test    al, al
0x180014836  jz      short loc_180014871
0x180014838  mov     ebx, 8007000Bh
0x18001483d  mov     rcx, cs:WPP_GLOBAL_Control
0x180014844  lea     rdi, WPP_GLOBAL_Control
0x18001484b  cmp     rcx, rdi
0x18001484e  jz      short loc_1800148CE
0x180014850  test    byte ptr [rcx+44h], 80h
0x180014854  jz      short loc_1800148CE
0x180014856  mov     edx, 3Bh ; ';'
0x18001485b  lea     r9, [rbp+1E0h+FileName]
0x18001485f  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x180014866  mov     rcx, [rcx+38h]
0x18001486a  call    WPP_SF_S
0x18001486f  jmp     short loc_1800148CE
0x180014871  test    ebx, ebx
0x180014873  js      short loc_1800148C7
0x180014875  test    dil, dil
0x180014878  jz      loc_1800149B0
0x18001487e  mov     rax, [rsp+2E0h+hFile]
0x180014883  dec     rax
0x180014886  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001488a  setbe   al
0x18001488d  neg     al
0x18001488f  sbb     rdx, rdx
0x180014892  lea     rax, [rsp+2E0h+hFile]
0x180014897  and     rdx, rax; struct Win32HandleRAII *
0x18001489a  lea     rcx, [rbp+1E0h+FileName]; unsigned __int16 *
0x18001489e  call    ?IsResourceOnlyDll@@YA_NPEBGPEAVWin32HandleRAII@@@Z; IsResourceOnlyDll(ushort const *,Win32HandleRAII *)
0x1800148a3  test    al, al
0x1800148a5  jnz     loc_1800149B0
0x1800148ab  mov     ebx, 8007000Bh
0x1800148b0  lea     r8, [rbp+1E0h+FileName]
0x1800148b4  lea     rdx, aResourceDllCon; "Resource DLL contains code (%ws)."
0x1800148bb  lea     rcx, aGetfilefromser; "GetFileFromServerAsGivenName"
0x1800148c2  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800148c7  lea     rdi, WPP_GLOBAL_Control
0x1800148ce  mov     [rsp+2E0h+var_290], r14d
0x1800148d3  lea     rdx, [rsp+2E0h+var_290]; int *
0x1800148d8  lea     rcx, [rsp+2E0h+hLibModule]; this
0x1800148dd  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x1800148e2  mov     [rsp+2E0h+FileInformation], 1
0x1800148e7  mov     rcx, [rsp+2E0h+hFile]; hFile
0x1800148ec  lea     rax, [rcx-1]
0x1800148f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800148f4  ja      short loc_18001495E
0x1800148f6  mov     r9d, 1; dwBufferSize
0x1800148fc  lea     r8, [rsp+2E0h+FileInformation]; lpFileInformation
0x180014901  lea     edx, [r9+3]; FileInformationClass
0x180014905  call    cs:__imp_SetFileInformationByHandle
0x18001490c  nop     dword ptr [rax+rax+00h]
0x180014911  test    eax, eax
0x180014913  jnz     short loc_18001495E
0x180014915  mov     rax, cs:WPP_GLOBAL_Control
0x18001491c  cmp     rax, rdi
0x18001491f  jz      short loc_18001495E
0x180014921  test    byte ptr [rax+44h], 80h
0x180014925  jz      short loc_18001495E
0x180014927  call    cs:__imp_GetLastError
0x18001492e  nop     dword ptr [rax+rax+00h]
0x180014933  test    eax, eax
0x180014935  jle     short loc_18001493F
0x180014937  movzx   eax, ax
0x18001493a  or      eax, 80070000h
0x18001493f  mov     edx, 3Ch ; '<'
0x180014944  mov     r9d, eax
0x180014947  lea     r8, WPP_799f402e917533f804c44f52fde54aed_Traceguids
0x18001494e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014955  mov     rcx, [rcx+38h]
0x180014959  call    WPP_SF_d
0x18001495e  mov     rcx, [rsp+2E0h+hFile]; hObject
0x180014963  lea     rax, [rcx-1]
0x180014967  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001496b  ja      short loc_18001497E
0x18001496d  call    cs:__imp_CloseHandle
0x180014974  nop     dword ptr [rax+rax+00h]
0x180014979  mov     [rsp+2E0h+hFile], r14
0x18001497e  mov     rax, [rsp+2E0h+var_278]
0x180014983  test    rax, rax
0x180014986  jz      short loc_180014997
0x180014988  mov     rcx, [rsp+2E0h+var_280]
0x18001498d  test    rcx, rcx
0x180014990  jz      short loc_180014997
0x180014992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014997  mov     rcx, [rsp+2E0h+hLibModule]; hLibModule
0x18001499c  test    rcx, rcx
0x18001499f  jz      short loc_1800149AE
0x1800149a1  call    cs:__imp_FreeLibrary
0x1800149a8  nop     dword ptr [rax+rax+00h]
0x1800149ad  nop
0x1800149ae  jmp     short loc_180014A13
0x1800149b0  mov     ebx, r14d
0x1800149b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800149b7  inc     rax
0x1800149ba  cmp     [rsi+rax*2], r14w
0x1800149bf  jnz     short loc_1800149B7
0x1800149c1  lea     eax, ds:2[rax*2]
0x1800149c8  mov     [rsp+2E0h+cbData], eax; cbData
0x1800149cc  mov     [rsp+2E0h+lpData], rsi; lpData
0x1800149d1  mov     r9d, 1; dwType
0x1800149d7  xor     r8d, r8d; Reserved
0x1800149da  mov     rdx, r12; lpValueName
0x1800149dd  mov     rcx, r15; hKey
0x1800149e0  call    cs:__imp_RegSetValueExW
0x1800149e7  nop     dword ptr [rax+rax+00h]
0x1800149ec  mov     edi, eax
0x1800149ee  test    eax, eax
0x1800149f0  jz      short loc_180014A13
0x1800149f2  lea     rcx, [rbp+1E0h+FileName]; lpFileName
0x1800149f6  call    cs:__imp_DeleteFileW
0x1800149fd  nop     dword ptr [rax+rax+00h]
0x180014a02  test    edi, edi
0x180014a04  jg      short loc_180014A0A
0x180014a06  mov     ebx, edi
0x180014a08  jmp     short loc_180014A13
0x180014a0a  movzx   ebx, di
0x180014a0d  or      ebx, 80070000h
0x180014a13  test    ebx, ebx
0x180014a15  jns     short loc_180014A35
0x180014a17  mov     dword ptr [rsp+2E0h+lpData], ebx
0x180014a1b  mov     r9, rsi
0x180014a1e  mov     r8, r13
0x180014a21  lea     rdx, aFailedToRetrie_3; "Failed to retrieve %ws as %ws (hr: 0x%x"...
0x180014a28  lea     rcx, aGetfilefromser; "GetFileFromServerAsGivenName"
0x180014a2f  call    ?WriteDbgTraceWarning@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180014a34  nop
0x180014a35  mov     rcx, [rsp+2E0h+hFile]; hObject
0x180014a3a  lea     rax, [rcx-1]
0x180014a3e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014a42  ja      short loc_180014A50
0x180014a44  call    cs:__imp_CloseHandle
0x180014a4b  nop     dword ptr [rax+rax+00h]
0x180014a50  mov     eax, ebx
0x180014a52  mov     rcx, [rbp+1E0h+var_50]
0x180014a59  xor     rcx, rsp; StackCookie
0x180014a5c  call    __security_check_cookie
0x180014a61  add     rsp, 2A8h
0x180014a68  pop     r15
0x180014a6a  pop     r14
0x180014a6c  pop     r13
0x180014a6e  pop     r12
0x180014a70  pop     rdi
0x180014a71  pop     rsi
0x180014a72  pop     rbx
0x180014a73  pop     rbp
0x180014a74  retn
0x180014a76  cmp     [rbp+1E0h+arg_28], al
0x180014a7c  jnz     short loc_180014A17
0x180014a7e  cmp     ebx, 80070002h
0x180014a84  jz      short loc_180014A8E
0x180014a86  cmp     ebx, 80070032h
0x180014a8c  jnz     short loc_180014A17
0x180014a8e  mov     r9d, ebx
0x180014a91  mov     r8, r13
0x180014a94  lea     rdx, aTheConnectionF; "The connection file (%ws) could not be "...
0x180014a9b  lea     rcx, aGetfilefromser; "GetFileFromServerAsGivenName"
0x180014aa2  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180014aa7  xor     eax, eax
0x180014aa9  mov     ebx, eax
0x180014aab  jmp     short loc_180014A35
```
