# PrintConfig::DrvDriverEvent(ulong,_DRIVER_INFO_3W *,ulong)

- ea: `0x18001a6e0`
- end: `0x18001ab38`
- name: `?DrvDriverEvent@PrintConfig@@YAXKPEAU_DRIVER_INFO_3W@@K@Z`
- size: `1112`
- prototype: `void __fastcall(PrintConfig *this, struct _DRIVER_INFO_3W *, struct _DRIVER_INFO_3W *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002e8fc`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x180004424`
- `0x1800060ec`
- `0x18000be0c`
- `0x18000f380`
- `0x180017c3c`
- `0x1800183a0`
- `0x180018bbc`
- `0x18001923c`
- `0x1800193c4`
- `0x18001a6e0`
- `0x180035c90`
- `0x180035e18`
- `0x180152dd8`
- `0x1801c3010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18001a921`
- `KERNEL32!FreeLibrary` at `0x18001a921`
- `KERNEL32!GetLastError` at `0x18001aa85`
- `KERNEL32!GetLastError` at `0x18001aa85`
- `KERNEL32!VerSetConditionMask` at `0x18001a767`
- `KERNEL32!VerSetConditionMask` at `0x18001a776`
- `KERNEL32!VerSetConditionMask` at `0x18001a767`
- `KERNEL32!VerSetConditionMask` at `0x18001a776`
- `KERNEL32!VerifyVersionInfoW` at `0x18001a785`
- `KERNEL32!VerifyVersionInfoW` at `0x18001a785`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18001a7d7`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18001a822`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18001a7d7`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x18001a822`

## string_xrefs

- `0x18001a8a8`: `\SysWOW64\PrintConfig.dll`
- `0x18001a840`: `\3\PrintConfig.dll`
- `0x18001a8e0`: `Failed to unregister WOW64 PrintConfig during driver deletion (hr:0x%x)`
- `0x18001a8e7`: `PrintConfig::DrvDriverEvent`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall PrintConfig::DrvDriverEvent(PrintConfig *this, struct _DRIVER_INFO_3W *a2, struct _DRIVER_INFO_3W *a3)
{
  int v3; // edi
  ULONGLONG v4; // rax
  ULONGLONG v5; // rax
  int v6; // ebx
  int v7; // ebx
  Win32Adapters::Version *v8; // rcx
  int updated; // ebx
  unsigned __int16 *v10; // rdx
  unsigned int v11; // r8d
  int WindowsDirectoryW; // ebx
  int v13; // eax
  signed int LastError; // eax
  unsigned int v15; // ebx
  DWORD pcbNeeded; // [rsp+30h] [rbp-D0h] BYREF
  int v17; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE pExceptionObject[32]; // [rsp+38h] [rbp-C8h] BYREF
  LPBYTE pDriverDirectory; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+60h] [rbp-A0h]
  HMODULE hLibModule[2]; // [rsp+70h] [rbp-90h] BYREF
  void (*v22)(void); // [rsp+80h] [rbp-80h]
  __int64 v23; // [rsp+88h] [rbp-78h]
  _OSVERSIONINFOEXW VersionInformation; // [rsp+90h] [rbp-70h] BYREF

  v23 = -2;
  v3 = (int)this;
  if ( a2->cVersion == 3 && IsDriverUsingMUD(a2) && (unsigned int)(v3 - 1) <= 1 )
  {
    memset_0(&VersionInformation.dwBuildNumber, 0, 0x110u);
    VersionInformation.dwOSVersionInfoSize = 284;
    VersionInformation.dwMajorVersion = 6;
    VersionInformation.dwMinorVersion = 3;
    v4 = VerSetConditionMask(0, 2u, 3u);
    v5 = VerSetConditionMask(v4, 1u, 3u);
    if ( !VerifyVersionInfoW(&VersionInformation, 3u, v5) )
    {
      v17 = 0;
      RevertToPrinterRAII::RevertToPrinterRAII((RevertToPrinterRAII *)hLibModule, &v17);
      v6 = v17;
      if ( v17 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            42,
            WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
            (unsigned int)v17);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v6);
        throw (hr_error *)pExceptionObject;
      }
      pcbNeeded = 0;
      if ( GetPrinterDriverDirectoryW(0, 0, 1u, 0, 0, &pcbNeeded) )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            43,
            WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
            2147549183LL);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, -2147418113);
        throw (hr_error *)pExceptionObject;
      }
      std::vector<unsigned short>::vector<unsigned short>(&pDriverDirectory, ((unsigned __int64)pcbNeeded >> 1) + 18);
      if ( !GetPrinterDriverDirectoryW(
              0,
              0,
              1u,
              pDriverDirectory,
              2 * ((v20 - (__int64)pDriverDirectory) >> 1),
              &pcbNeeded) )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 44, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids, v15);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v15);
        throw (hr_error *)pExceptionObject;
      }
      v7 = StringCchCatW(
             (unsigned __int16 *)pDriverDirectory,
             (v20 - (__int64)pDriverDirectory) >> 1,
             L"\\3\\PrintConfig.dll");
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            45,
            WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
            (unsigned int)v7);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, v7);
        throw (hr_error *)pExceptionObject;
      }
      updated = UpdateDllComRegistration((const unsigned __int16 *)pDriverDirectory, 0, 1, v3 == 1);
      if ( updated < 0 )
      {
        if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            46,
            WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
            (unsigned int)updated);
        }
        hr_error::hr_error((hr_error *)pExceptionObject, updated);
        throw (hr_error *)pExceptionObject;
      }
      if ( v3 == 2 && Win32Adapters::Version::IsOlderThanWin8(v8) )
      {
        memset_0(&VersionInformation, 0, 0x208u);
        WindowsDirectoryW = Win32Adapters::FileSystem::GetWindowsDirectoryW(
                              (Win32Adapters::FileSystem *)&VersionInformation,
                              v10,
                              v11);
        if ( WindowsDirectoryW < 0
          || (WindowsDirectoryW = StringCchCatW(
                                    (unsigned __int16 *)&VersionInformation,
                                    0x104u,
                                    L"\\SysWOW64\\PrintConfig.dll"),
              WindowsDirectoryW < 0) )
        {
          if ( WPP_GLOBAL_Control != (PrintConfig::CPageImageableSize *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 7),
              47,
              WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids,
              (unsigned int)WindowsDirectoryW);
          }
          hr_error::hr_error((hr_error *)pExceptionObject, WindowsDirectoryW);
          throw (hr_error *)pExceptionObject;
        }
        v13 = UpdateDllComRegistration((const unsigned __int16 *)&VersionInformation, 1, 1, 0);
        if ( v13 < 0 )
          Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(
            "PrintConfig::DrvDriverEvent",
            L"Failed to unregister WOW64 PrintConfig during driver deletion (hr:0x%x)",
            (unsigned int)v13);
      }
      std::vector<unsigned short>::~vector<unsigned short>(&pDriverDirectory);
      if ( v22 && hLibModule[1] )
        v22();
      if ( hLibModule[0] )
        FreeLibrary(hLibModule[0]);
    }
  }
}

```

## disassembly

```asm
0x18001a6e0  push    rbp
0x18001a6e2  push    rbx
0x18001a6e3  push    rdi
0x18001a6e4  push    r14
0x18001a6e6  lea     rbp, [rsp-1B8h]
0x18001a6ee  sub     rsp, 2B8h
0x18001a6f5  mov     [rbp+1D0h+var_248], 0FFFFFFFFFFFFFFFEh
0x18001a6fd  mov     rax, cs:__security_cookie
0x18001a704  xor     rax, rsp
0x18001a707  mov     [rbp+1D0h+var_30], rax
0x18001a70e  mov     edi, ecx
0x18001a710  mov     ebx, 3
0x18001a715  cmp     [rdx], ebx
0x18001a717  jnz     loc_18001A928
0x18001a71d  mov     rcx, rdx; struct _DRIVER_INFO_3W *
0x18001a720  call    ?IsDriverUsingMUD@@YA_NPEAU_DRIVER_INFO_3W@@@Z; IsDriverUsingMUD(_DRIVER_INFO_3W *)
0x18001a725  test    al, al
0x18001a727  jz      loc_18001A928
0x18001a72d  lea     eax, [rdi-1]
0x18001a730  lea     r14d, [rbx-2]
0x18001a734  cmp     eax, r14d
0x18001a737  ja      loc_18001A928
0x18001a73d  xor     edx, edx; Val
0x18001a73f  mov     r8d, 110h; Size
0x18001a745  lea     rcx, [rbp+1D0h+VersionInformation.dwBuildNumber]; void *
0x18001a749  call    memset_0
0x18001a74e  mov     [rbp+1D0h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x18001a755  mov     [rbp+1D0h+VersionInformation.dwMajorVersion], 6
0x18001a75c  mov     [rbp+1D0h+VersionInformation.dwMinorVersion], ebx
0x18001a75f  mov     r8b, bl; Condition
0x18001a762  lea     edx, [rbx-1]; TypeMask
0x18001a765  xor     ecx, ecx; ConditionMask
0x18001a767  call    cs:__imp_VerSetConditionMask
0x18001a76d  mov     r8b, bl; Condition
0x18001a770  mov     edx, r14d; TypeMask
0x18001a773  mov     rcx, rax; ConditionMask
0x18001a776  call    cs:__imp_VerSetConditionMask
0x18001a77c  mov     r8, rax; dwlConditionMask
0x18001a77f  mov     edx, ebx; dwTypeMask
0x18001a781  lea     rcx, [rbp+1D0h+VersionInformation]; lpVersionInformation
0x18001a785  call    cs:__imp_VerifyVersionInfoW
0x18001a78b  test    eax, eax
0x18001a78d  jnz     loc_18001A928
0x18001a793  mov     [rsp+2D0h+var_29C], eax
0x18001a797  lea     rdx, [rsp+2D0h+var_29C]; int *
0x18001a79c  lea     rcx, [rsp+2D0h+hLibModule]; this
0x18001a7a1  call    ??0RevertToPrinterRAII@@QEAA@PEAJ@Z; RevertToPrinterRAII::RevertToPrinterRAII(long *)
0x18001a7a6  nop
0x18001a7a7  mov     ebx, [rsp+2D0h+var_29C]
0x18001a7ab  test    ebx, ebx
0x18001a7ad  js      loc_18001A9E2
0x18001a7b3  mov     [rsp+2D0h+var_2A0], 0
0x18001a7bb  lea     rax, [rsp+2D0h+var_2A0]
0x18001a7c0  mov     [rsp+2D0h+pcbNeeded], rax; pcbNeeded
0x18001a7c5  mov     [rsp+2D0h+cbBuf], 0; cbBuf
0x18001a7cd  xor     r9d, r9d; pDriverDirectory
0x18001a7d0  mov     r8d, r14d; Level
0x18001a7d3  xor     edx, edx; pEnvironment
0x18001a7d5  xor     ecx, ecx; pName
0x18001a7d7  call    cs:__imp_GetPrinterDriverDirectoryW
0x18001a7dd  test    eax, eax
0x18001a7df  jnz     loc_18001AA31
0x18001a7e5  mov     edx, [rsp+2D0h+var_2A0]
0x18001a7e9  shr     rdx, 1
0x18001a7ec  add     rdx, 12h
0x18001a7f0  lea     rcx, [rsp+2D0h+pDriverDirectory]
0x18001a7f5  call    ??0?$vector@GV?$allocator@G@std@@@std@@QEAA@_KAEBV?$allocator@G@1@@Z; std::vector<ushort>::vector<ushort>(unsigned __int64,std::allocator<ushort> const &)
0x18001a7fa  nop
0x18001a7fb  mov     r9, [rsp+2D0h+pDriverDirectory]; pDriverDirectory
0x18001a800  mov     rax, [rsp+2D0h+var_270]
0x18001a805  sub     rax, r9
0x18001a808  sar     rax, 1
0x18001a80b  add     eax, eax
0x18001a80d  lea     rcx, [rsp+2D0h+var_2A0]
0x18001a812  mov     [rsp+2D0h+pcbNeeded], rcx; pcbNeeded
0x18001a817  mov     [rsp+2D0h+cbBuf], eax; cbBuf
0x18001a81b  mov     r8d, r14d; Level
0x18001a81e  xor     edx, edx; pEnvironment
0x18001a820  xor     ecx, ecx; pName
0x18001a822  call    cs:__imp_GetPrinterDriverDirectoryW
0x18001a828  test    eax, eax
0x18001a82a  jz      loc_18001AA85
0x18001a830  mov     rcx, [rsp+2D0h+pDriverDirectory]; unsigned __int16 *
0x18001a835  mov     rdx, [rsp+2D0h+var_270]
0x18001a83a  sub     rdx, rcx
0x18001a83d  sar     rdx, 1; unsigned __int64
0x18001a840  lea     r8, a3PrintconfigDl; "\\3\\PrintConfig.dll"
0x18001a847  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a84c  mov     ebx, eax
0x18001a84e  test    eax, eax
0x18001a850  js      loc_18001AAE9
0x18001a856  cmp     edi, r14d
0x18001a859  setz    r9b; bool
0x18001a85d  mov     r8b, r14b; bool
0x18001a860  xor     edx, edx; bool
0x18001a862  mov     rcx, [rsp+2D0h+pDriverDirectory]; unsigned __int16 *
0x18001a867  call    ?UpdateDllComRegistration@@YAJPEBG_N11@Z; UpdateDllComRegistration(ushort const *,bool,bool,bool)
0x18001a86c  mov     ebx, eax
0x18001a86e  test    eax, eax
0x18001a870  js      loc_18001A944
0x18001a876  cmp     edi, 2
0x18001a879  jnz     short loc_18001A8F4
0x18001a87b  call    ?IsOlderThanWin8@Version@Win32Adapters@@YA_NXZ; Win32Adapters::Version::IsOlderThanWin8(void)
0x18001a880  test    al, al
0x18001a882  jz      short loc_18001A8F4
0x18001a884  xor     edx, edx; Val
0x18001a886  mov     r8d, 208h; Size
0x18001a88c  lea     rcx, [rbp+1D0h+VersionInformation]; void *
0x18001a890  call    memset_0
0x18001a895  lea     rcx, [rbp+1D0h+VersionInformation]; this
0x18001a899  call    ?GetWindowsDirectoryW@FileSystem@Win32Adapters@@YAJPEAGK@Z; Win32Adapters::FileSystem::GetWindowsDirectoryW(ushort *,ulong)
0x18001a89e  mov     ebx, eax
0x18001a8a0  test    eax, eax
0x18001a8a2  js      loc_18001A993
0x18001a8a8  lea     r8, aSyswow64Printc; "\\SysWOW64\\PrintConfig.dll"
0x18001a8af  mov     edx, 104h; unsigned __int64
0x18001a8b4  lea     rcx, [rbp+1D0h+VersionInformation]; unsigned __int16 *
0x18001a8b8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001a8bd  mov     ebx, eax
0x18001a8bf  test    eax, eax
0x18001a8c1  js      loc_18001A993
0x18001a8c7  xor     r9d, r9d; bool
0x18001a8ca  mov     r8b, r14b; bool
0x18001a8cd  mov     dl, r14b; bool
0x18001a8d0  lea     rcx, [rbp+1D0h+VersionInformation]; unsigned __int16 *
0x18001a8d4  call    ?UpdateDllComRegistration@@YAJPEBG_N11@Z; UpdateDllComRegistration(ushort const *,bool,bool,bool)
0x18001a8d9  test    eax, eax
0x18001a8db  jns     short loc_18001A8F4
0x18001a8dd  mov     r8d, eax
0x18001a8e0  lea     rdx, aFailedToUnregi; "Failed to unregister WOW64 PrintConfig "...
0x18001a8e7  lea     rcx, aPrintconfigDrv_8; "PrintConfig::DrvDriverEvent"
0x18001a8ee  call    ?WriteDbgTraceInfo@PrintConfigTelemetry@Telemetry@Driver@Print@@SAXPEADPEAGZZ; Print::Driver::Telemetry::PrintConfigTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x18001a8f3  nop
0x18001a8f4  lea     rcx, [rsp+2D0h+pDriverDirectory]
0x18001a8f9  call    ??1?$vector@GV?$allocator@G@std@@@std@@QEAA@XZ; std::vector<ushort>::~vector<ushort>(void)
0x18001a8fe  nop
0x18001a8ff  mov     rax, [rbp+1D0h+var_250]
0x18001a903  test    rax, rax
0x18001a906  jz      short loc_18001A917
0x18001a908  mov     rcx, [rsp+2D0h+var_258]
0x18001a90d  test    rcx, rcx
0x18001a910  jz      short loc_18001A917
0x18001a912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a917  mov     rcx, [rsp+2D0h+hLibModule]; hLibModule
0x18001a91c  test    rcx, rcx
0x18001a91f  jz      short loc_18001A928
0x18001a921  call    cs:__imp_FreeLibrary
0x18001a927  nop
0x18001a928  mov     rcx, [rbp+1D0h+var_30]
0x18001a92f  xor     rcx, rsp; StackCookie
0x18001a932  call    __security_check_cookie
0x18001a937  add     rsp, 2B8h
0x18001a93e  pop     r14
0x18001a940  pop     rdi
0x18001a941  pop     rbx
0x18001a942  pop     rbp
0x18001a943  retn
0x18001a944  lea     rax, WPP_GLOBAL_Control
0x18001a94b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a952  cmp     rcx, rax
0x18001a955  jz      short loc_18001A975
0x18001a957  test    [rcx+44h], r14b
0x18001a95b  jz      short loc_18001A975
0x18001a95d  mov     edx, 2Eh ; '.'
0x18001a962  mov     r9d, ebx
0x18001a965  lea     r8, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids
0x18001a96c  mov     rcx, [rcx+38h]
0x18001a970  call    WPP_SF_d
0x18001a975  mov     edx, ebx; int
0x18001a977  lea     rcx, [rsp+2D0h+pExceptionObject]; this
0x18001a97c  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001a981  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001a988  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18001a98d  call    _CxxThrowException_0
0x18001a993  lea     rax, WPP_GLOBAL_Control
0x18001a99a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9a1  cmp     rcx, rax
0x18001a9a4  jz      short loc_18001A9C4
0x18001a9a6  test    [rcx+44h], r14b
0x18001a9aa  jz      short loc_18001A9C4
0x18001a9ac  mov     edx, 2Fh ; '/'
0x18001a9b1  mov     r9d, ebx
0x18001a9b4  lea     r8, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids
0x18001a9bb  mov     rcx, [rcx+38h]
0x18001a9bf  call    WPP_SF_d
0x18001a9c4  mov     edx, ebx; int
0x18001a9c6  lea     rcx, [rsp+2D0h+pExceptionObject]; this
0x18001a9cb  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001a9d0  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001a9d7  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18001a9dc  call    _CxxThrowException_0
0x18001a9e2  lea     rax, WPP_GLOBAL_Control
0x18001a9e9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a9f0  cmp     rcx, rax
0x18001a9f3  jz      short loc_18001AA13
0x18001a9f5  test    [rcx+44h], r14b
0x18001a9f9  jz      short loc_18001AA13
0x18001a9fb  mov     edx, 2Ah ; '*'
0x18001aa00  mov     r9d, ebx
0x18001aa03  lea     r8, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids
0x18001aa0a  mov     rcx, [rcx+38h]
0x18001aa0e  call    WPP_SF_d
0x18001aa13  mov     edx, ebx; int
0x18001aa15  lea     rcx, [rsp+2D0h+pExceptionObject]; this
0x18001aa1a  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001aa1f  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001aa26  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18001aa2b  call    _CxxThrowException_0
0x18001aa31  lea     rax, WPP_GLOBAL_Control
0x18001aa38  mov     ebx, 8000FFFFh
0x18001aa3d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aa44  cmp     rcx, rax
0x18001aa47  jz      short loc_18001AA67
0x18001aa49  test    [rcx+44h], r14b
0x18001aa4d  jz      short loc_18001AA67
0x18001aa4f  mov     edx, 2Bh ; '+'
0x18001aa54  mov     r9d, ebx
0x18001aa57  lea     r8, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids
0x18001aa5e  mov     rcx, [rcx+38h]
0x18001aa62  call    WPP_SF_d
0x18001aa67  mov     edx, ebx; int
0x18001aa69  lea     rcx, [rsp+2D0h+pExceptionObject]; this
0x18001aa6e  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001aa73  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001aa7a  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18001aa7f  call    _CxxThrowException_0
0x18001aa85  call    cs:__imp_GetLastError
0x18001aa8b  mov     ebx, eax
0x18001aa8d  test    eax, eax
0x18001aa8f  jle     short loc_18001AA9A
0x18001aa91  movzx   ebx, ax
0x18001aa94  or      ebx, 80070000h
0x18001aa9a  lea     rax, WPP_GLOBAL_Control
0x18001aaa1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaa8  cmp     rcx, rax
0x18001aaab  jz      short loc_18001AACB
0x18001aaad  test    [rcx+44h], r14b
0x18001aab1  jz      short loc_18001AACB
0x18001aab3  mov     edx, 2Ch ; ','
0x18001aab8  mov     r9d, ebx
0x18001aabb  lea     r8, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids
0x18001aac2  mov     rcx, [rcx+38h]
0x18001aac6  call    WPP_SF_d
0x18001aacb  mov     edx, ebx; int
0x18001aacd  lea     rcx, [rsp+2D0h+pExceptionObject]; this
0x18001aad2  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001aad7  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001aade  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18001aae3  call    _CxxThrowException_0
0x18001aae9  lea     rax, WPP_GLOBAL_Control
0x18001aaf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001aaf7  cmp     rcx, rax
0x18001aafa  jz      short loc_18001AB1A
0x18001aafc  test    [rcx+44h], r14b
0x18001ab00  jz      short loc_18001AB1A
0x18001ab02  mov     edx, 2Dh ; '-'
0x18001ab07  mov     r9d, ebx
0x18001ab0a  lea     r8, WPP_421ea51b5c763603e0f4e8318451c1f4_Traceguids
0x18001ab11  mov     rcx, [rcx+38h]
0x18001ab15  call    WPP_SF_d
0x18001ab1a  mov     edx, ebx; int
0x18001ab1c  lea     rcx, [rsp+2D0h+pExceptionObject]; this
0x18001ab21  call    ??0hr_error@@QEAA@J@Z; hr_error::hr_error(long)
0x18001ab26  lea     rdx, _TI2?AUhr_error@@; pThrowInfo
0x18001ab2d  lea     rcx, [rsp+2D0h+pExceptionObject]; pExceptionObject
0x18001ab32  call    _CxxThrowException_0
```
