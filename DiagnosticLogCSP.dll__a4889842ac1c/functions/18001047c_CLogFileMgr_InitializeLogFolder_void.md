# CLogFileMgr::InitializeLogFolder(void)

- ea: `0x18001047c`
- end: `0x180010670`
- name: `?InitializeLogFolder@CLogFileMgr@@CAJXZ`
- size: `500`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180010230`

## callees

- `0x180001104`
- `0x180001b60`
- `0x180006518`
- `0x180010180`
- `0x18001047c`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800104c0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800104c0`

## string_xrefs

- `0x1800104b9`: `%PROGRAMDATA%\Microsoft`

## pseudocode

```c
__int64 CLogFileMgr::InitializeLogFolder(void)
{
  int LogFolder; // ebx
  const unsigned __int16 *v1; // rdx
  const unsigned __int16 *v2; // rdx
  const unsigned __int16 *v3; // rdx
  const unsigned __int16 *v4; // rdx
  int v6; // [rsp+30h] [rbp-268h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+38h] [rbp-260h] BYREF
  int *v8; // [rsp+58h] [rbp-240h]
  __int64 v9; // [rsp+60h] [rbp-238h]
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
              LogFolder = CLogFileMgr::CreateLogFolder((wil *)&CLogFileMgr::s_szRootLogFolder, v1);
              if ( LogFolder >= 0 )
              {
                LogFolder = CLogFileMgr::CreateLogFolder((wil *)&CLogFileMgr::s_szCollectorsLogFolder, v2);
                if ( LogFolder >= 0 )
                {
                  LogFolder = CLogFileMgr::CreateLogFolder((wil *)&CLogFileMgr::s_szChannelsLogFolder, v3);
                  if ( LogFolder >= 0 )
                  {
                    LogFolder = CLogFileMgr::CreateLogFolder((wil *)&CLogFileMgr::s_szDeviceStateDataLogFolder, v4);
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
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v6 = LogFolder;
    v8 = &v6;
    v9 = 4;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180048E90, (unsigned __int8 *)byte_18003FA8F, 0, 0, 3u, &v7);
  }
  return (unsigned int)LogFolder;
}

```

## disassembly

```asm
0x18001047c  mov     [rsp+arg_0], rbx
0x180010481  mov     [rsp+arg_8], rsi
0x180010486  push    rdi
0x180010487  sub     rsp, 290h
0x18001048e  mov     rax, cs:__security_cookie
0x180010495  xor     rax, rsp
0x180010498  mov     [rsp+298h+var_18], rax
0x1800104a0  xor     ebx, ebx
0x1800104a2  cmp     cs:?s_fIsLogFolderInitialized@CLogFileMgr@@0HA, ebx; int CLogFileMgr::s_fIsLogFolderInitialized
0x1800104a8  jnz     loc_1800105FC
0x1800104ae  mov     r8d, 104h; nSize
0x1800104b4  lea     rdx, [rsp+298h+Dst]; lpDst
0x1800104b9  lea     rcx, Src; "%PROGRAMDATA%\\Microsoft"
0x1800104c0  call    cs:__imp_ExpandEnvironmentStringsW
0x1800104c6  dec     eax
0x1800104c8  cmp     eax, 103h
0x1800104cd  ja      loc_1800105F7
0x1800104d3  mov     edi, 401h
0x1800104d8  lea     rsi, aDiagnosticlogc_1; "DiagnosticLogCSP"
0x1800104df  mov     edx, edi; unsigned __int64
0x1800104e1  mov     [rsp+298h+var_278], rsi
0x1800104e6  lea     r9, [rsp+298h+Dst]
0x1800104eb  lea     r8, aSS_0; "%s\\%s"
0x1800104f2  lea     rcx, ?s_szRootLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x1800104f9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800104fe  mov     ebx, eax
0x180010500  test    eax, eax
0x180010502  js      loc_1800105FC
0x180010508  lea     rax, aCollectors; "Collectors"
0x18001050f  mov     edx, edi; unsigned __int64
0x180010511  mov     [rsp+298h+var_270], rax
0x180010516  lea     r9, [rsp+298h+Dst]
0x18001051b  lea     r8, aSSS; "%s\\%s\\%s"
0x180010522  mov     [rsp+298h+var_278], rsi
0x180010527  lea     rcx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x18001052e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010533  mov     ebx, eax
0x180010535  test    eax, eax
0x180010537  js      loc_1800105FC
0x18001053d  lea     rax, aChannels; "Channels"
0x180010544  mov     edx, edi; unsigned __int64
0x180010546  mov     [rsp+298h+var_270], rax
0x18001054b  lea     r9, [rsp+298h+Dst]
0x180010550  lea     r8, aSSS; "%s\\%s\\%s"
0x180010557  mov     [rsp+298h+var_278], rsi
0x18001055c  lea     rcx, ?s_szChannelsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010563  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010568  mov     ebx, eax
0x18001056a  test    eax, eax
0x18001056c  js      loc_1800105FC
0x180010572  lea     rax, aDevicestatedat; "DeviceStateData"
0x180010579  mov     edx, edi; unsigned __int64
0x18001057b  mov     [rsp+298h+var_270], rax
0x180010580  lea     r9, [rsp+298h+Dst]
0x180010585  lea     r8, aSSS; "%s\\%s\\%s"
0x18001058c  mov     [rsp+298h+var_278], rsi
0x180010591  lea     rcx, ?s_szDeviceStateDataLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x180010598  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001059d  mov     ebx, eax
0x18001059f  test    eax, eax
0x1800105a1  js      short loc_1800105FC
0x1800105a3  lea     rcx, ?s_szRootLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x1800105aa  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x1800105af  mov     ebx, eax
0x1800105b1  test    eax, eax
0x1800105b3  js      short loc_1800105FC
0x1800105b5  lea     rcx, ?s_szCollectorsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x1800105bc  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x1800105c1  mov     ebx, eax
0x1800105c3  test    eax, eax
0x1800105c5  js      short loc_1800105FC
0x1800105c7  lea     rcx, ?s_szChannelsLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x1800105ce  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x1800105d3  mov     ebx, eax
0x1800105d5  test    eax, eax
0x1800105d7  js      short loc_1800105FC
0x1800105d9  lea     rcx, ?s_szDeviceStateDataLogFolder@CLogFileMgr@@0PAGA; unsigned __int16 *
0x1800105e0  call    ?CreateLogFolder@CLogFileMgr@@CAJPEBG@Z; CLogFileMgr::CreateLogFolder(ushort const *)
0x1800105e5  mov     ebx, eax
0x1800105e7  test    eax, eax
0x1800105e9  js      short loc_1800105FC
0x1800105eb  mov     cs:?s_fIsLogFolderInitialized@CLogFileMgr@@0HA, 1; int CLogFileMgr::s_fIsLogFolderInitialized
0x1800105f5  jmp     short loc_1800105FC
0x1800105f7  mov     ebx, 80004005h
0x1800105fc  mov     eax, cs:dword_180048E90
0x180010602  cmp     eax, 5
0x180010605  jbe     short loc_180010649
0x180010607  lea     rax, [rsp+298h+var_268]
0x18001060c  mov     [rsp+298h+var_268], ebx
0x180010610  mov     [rsp+298h+var_240], rax
0x180010615  lea     rdx, byte_18003FA8F
0x18001061c  lea     rax, [rsp+298h+var_260]
0x180010621  mov     [rsp+298h+var_238], 4
0x18001062a  mov     [rsp+298h+var_270], rax
0x18001062f  lea     rcx, dword_180048E90
0x180010636  xor     r9d, r9d
0x180010639  mov     dword ptr [rsp+298h+var_278], 3
0x180010641  xor     r8d, r8d
0x180010644  call    _tlgWriteTransfer_EventWriteTransfer
0x180010649  mov     eax, ebx
0x18001064b  mov     rcx, [rsp+298h+var_18]
0x180010653  xor     rcx, rsp; StackCookie
0x180010656  call    __security_check_cookie
0x18001065b  lea     r11, [rsp+298h+var_8]
0x180010663  mov     rbx, [r11+10h]
0x180010667  mov     rsi, [r11+18h]
0x18001066b  mov     rsp, r11
0x18001066e  pop     rdi
0x18001066f  retn
```
