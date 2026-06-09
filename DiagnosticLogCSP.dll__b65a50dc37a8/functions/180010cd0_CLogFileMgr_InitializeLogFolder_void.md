# CLogFileMgr::InitializeLogFolder(void)

- ea: `0x180010cd0`
- end: `0x180010ecb`
- name: `?InitializeLogFolder@CLogFileMgr@@CAJXZ`
- size: `507`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010a7c`

## callees

- `0x180001108`
- `0x180001b90`
- `0x180006498`
- `0x1800109bc`
- `0x180010cd0`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010d14`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180010d14`

## string_xrefs

- `0x180010d0d`: `%PROGRAMDATA%\Microsoft`

## pseudocode

```c
__int64 CLogFileMgr::InitializeLogFolder(void)
{
  int LogFolder; // ebx
  int v2; // [rsp+30h] [rbp-268h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+38h] [rbp-260h] BYREF
  int *v4; // [rsp+58h] [rbp-240h]
  __int64 v5; // [rsp+60h] [rbp-238h]
  WCHAR Dst[264]; // [rsp+70h] [rbp-228h] BYREF

  LogFolder = 0;
  if ( !CLogFileMgr::s_fIsLogFolderInitialized )
  {
    if ( ExpandEnvironmentStringsW(L"%PROGRAMDATA%\\Microsoft", Dst, 0x104u) - 1 > 0x103 )
    {
      LogFolder = -2147467259;
    }
    else
    {
      LogFolder = StringCchPrintfW(&CLogFileMgr::s_szRootLogFolder, 0x401u, L"%s\\%s", Dst, L"DiagnosticLogCSP");
      if ( LogFolder >= 0 )
      {
        LogFolder = StringCchPrintfW(
                      &CLogFileMgr::s_szCollectorsLogFolder,
                      0x401u,
                      L"%s\\%s\\%s",
                      Dst,
                      L"DiagnosticLogCSP",
                      L"Collectors");
        if ( LogFolder >= 0 )
        {
          LogFolder = StringCchPrintfW(
                        &CLogFileMgr::s_szChannelsLogFolder,
                        0x401u,
                        L"%s\\%s\\%s",
                        Dst,
                        L"DiagnosticLogCSP",
                        L"Channels");
          if ( LogFolder >= 0 )
          {
            LogFolder = StringCchPrintfW(
                          &CLogFileMgr::s_szDeviceStateDataLogFolder,
                          0x401u,
                          L"%s\\%s\\%s",
                          Dst,
                          L"DiagnosticLogCSP",
                          L"DeviceStateData");
            if ( LogFolder >= 0 )
            {
              LogFolder = CLogFileMgr::CreateLogFolder(&CLogFileMgr::s_szRootLogFolder);
              if ( LogFolder >= 0 )
              {
                LogFolder = CLogFileMgr::CreateLogFolder(&CLogFileMgr::s_szCollectorsLogFolder);
                if ( LogFolder >= 0 )
                {
                  LogFolder = CLogFileMgr::CreateLogFolder(&CLogFileMgr::s_szChannelsLogFolder);
                  if ( LogFolder >= 0 )
                  {
                    LogFolder = CLogFileMgr::CreateLogFolder(&CLogFileMgr::s_szDeviceStateDataLogFolder);
                    if ( LogFolder >= 0 )
                      CLogFileMgr::s_fIsLogFolderInitialized = 1;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v2 = LogFolder;
    v4 = &v2;
    v5 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_18004AE90, (unsigned __int8 *)byte_180041A8F, 0, 0, 3u, &v3);
  }
  return (unsigned int)LogFolder;
}

```

## disassembly

```asm
0x180010cd0  mov     [rsp+arg_0], rbx
0x180010cd5  mov     [rsp+arg_8], rsi
0x180010cda  push    rdi
0x180010cdb  sub     rsp, 290h
0x180010ce2  mov     rax, cs:__security_cookie
0x180010ce9  xor     rax, rsp
0x180010cec  mov     [rsp+298h+var_18], rax
0x180010cf4  xor     ebx, ebx
0x180010cf6  cmp     cs:?s_fIsLogFolderInitialized@CLogFileMgr@@0HA, ebx; int CLogFileMgr::s_fIsLogFolderInitialized
0x180010cfc  jnz     loc_180010E56
0x180010d02  mov     r8d, 104h; nSize
0x180010d08  lea     rdx, [rsp+298h+Dst]; lpDst
0x180010d0d  lea     rcx, Src; "%PROGRAMDATA%\\Microsoft"
0x180010d14  call    cs:__imp_ExpandEnvironmentStringsW
0x180010d1b  nop     dword ptr [rax+rax+00h]
0x180010d20  dec     eax
0x180010d22  cmp     eax, 103h
0x180010d27  ja      loc_180010E51
0x180010d2d  mov     edi, 401h
0x180010d32  lea     rsi, aDiagnosticlogc_1; "DiagnosticLogCSP"
0x180010d39  mov     edx, edi; unsigned __int64
0x180010d3b  mov     [rsp+298h+var_278], rsi
0x180010d40  lea     r9, [rsp+298h+Dst]
0x180010d45  lea     r8, aSS_0; "%s\\%s"
0x180010d4c  lea     rcx, ?s_szRootLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010d53  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010d58  mov     ebx, eax
0x180010d5a  test    eax, eax
0x180010d5c  js      loc_180010E56
0x180010d62  lea     rax, aCollectors; "Collectors"
0x180010d69  mov     edx, edi; unsigned __int64
0x180010d6b  mov     [rsp+298h+var_270], rax
0x180010d70  lea     r9, [rsp+298h+Dst]
0x180010d75  lea     r8, aSSS; "%s\\%s\\%s"
0x180010d7c  mov     [rsp+298h+var_278], rsi
0x180010d81  lea     rcx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010d88  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010d8d  mov     ebx, eax
0x180010d8f  test    eax, eax
0x180010d91  js      loc_180010E56
0x180010d97  lea     rax, aChannels; "Channels"
0x180010d9e  mov     edx, edi; unsigned __int64
0x180010da0  mov     [rsp+298h+var_270], rax
0x180010da5  lea     r9, [rsp+298h+Dst]
0x180010daa  lea     r8, aSSS; "%s\\%s\\%s"
0x180010db1  mov     [rsp+298h+var_278], rsi
0x180010db6  lea     rcx, ?s_szChannelsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010dbd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010dc2  mov     ebx, eax
0x180010dc4  test    eax, eax
0x180010dc6  js      loc_180010E56
0x180010dcc  lea     rax, aDevicestatedat; "DeviceStateData"
0x180010dd3  mov     edx, edi; unsigned __int64
0x180010dd5  mov     [rsp+298h+var_270], rax
0x180010dda  lea     r9, [rsp+298h+Dst]
0x180010ddf  lea     r8, aSSS; "%s\\%s\\%s"
0x180010de6  mov     [rsp+298h+var_278], rsi
0x180010deb  lea     rcx, ?s_szDeviceStateDataLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010df2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010df7  mov     ebx, eax
0x180010df9  test    eax, eax
0x180010dfb  js      short loc_180010E56
0x180010dfd  lea     rcx, ?s_szRootLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010e04  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x180010e09  mov     ebx, eax
0x180010e0b  test    eax, eax
0x180010e0d  js      short loc_180010E56
0x180010e0f  lea     rcx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010e16  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x180010e1b  mov     ebx, eax
0x180010e1d  test    eax, eax
0x180010e1f  js      short loc_180010E56
0x180010e21  lea     rcx, ?s_szChannelsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010e28  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x180010e2d  mov     ebx, eax
0x180010e2f  test    eax, eax
0x180010e31  js      short loc_180010E56
0x180010e33  lea     rcx, ?s_szDeviceStateDataLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010e3a  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x180010e3f  mov     ebx, eax
0x180010e41  test    eax, eax
0x180010e43  js      short loc_180010E56
0x180010e45  mov     cs:?s_fIsLogFolderInitialized@CLogFileMgr@@0HA, 1; int CLogFileMgr::s_fIsLogFolderInitialized
0x180010e4f  jmp     short loc_180010E56
0x180010e51  mov     ebx, 80004005h
0x180010e56  mov     eax, cs:dword_18004AE90
0x180010e5c  cmp     eax, 5
0x180010e5f  jbe     short loc_180010EA3
0x180010e61  lea     rax, [rsp+298h+var_268]
0x180010e66  mov     [rsp+298h+var_268], ebx
0x180010e6a  mov     [rsp+298h+var_240], rax
0x180010e6f  lea     rdx, byte_180041A8F
0x180010e76  lea     rax, [rsp+298h+var_260]
0x180010e7b  mov     [rsp+298h+var_238], 4
0x180010e84  mov     [rsp+298h+var_270], rax
0x180010e89  lea     rcx, dword_18004AE90
0x180010e90  xor     r9d, r9d
0x180010e93  mov     dword ptr [rsp+298h+var_278], 3
0x180010e9b  xor     r8d, r8d
0x180010e9e  call    _tlgWriteTransfer_EventWriteTransfer
0x180010ea3  mov     eax, ebx
0x180010ea5  mov     rcx, [rsp+298h+var_18]
0x180010ead  xor     rcx, rsp; StackCookie
0x180010eb0  call    __security_check_cookie
0x180010eb5  lea     r11, [rsp+298h+var_8]
0x180010ebd  mov     rbx, [r11+10h]
0x180010ec1  mov     rsi, [r11+18h]
0x180010ec5  mov     rsp, r11
0x180010ec8  pop     rdi
0x180010ec9  retn
```
