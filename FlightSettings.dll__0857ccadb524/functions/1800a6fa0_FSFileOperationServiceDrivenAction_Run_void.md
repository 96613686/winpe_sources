# FSFileOperationServiceDrivenAction::Run(void)

- ea: `0x1800a6fa0`
- end: `0x1800a7444`
- name: `?Run@FSFileOperationServiceDrivenAction@@UEAAJXZ`
- size: `1188`
- prototype: `__int64 __fastcall(FSFileOperationServiceDrivenAction *__hidden this)`
- caller_count: `0`
- callee_count: `16`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x180004b80`
- `0x180005744`
- `0x18000cc8c`
- `0x180013da0`
- `0x1800177bc`
- `0x18001c6f4`
- `0x18002035c`
- `0x1800a3c50`
- `0x1800a5f50`
- `0x1800a5f8c`
- `0x1800a60a4`
- `0x1800a6338`
- `0x1800a6590`
- `0x1800a66ac`
- `0x1800a6a74`
- `0x1800a6fa0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a704d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x1800a704d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a710b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a73ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a710b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7229`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a7333`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a73ba`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800a721f`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x1800a721f`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800a7101`
- `api-ms-win-core-file-l1-1-0!DefineDosDeviceW` at `0x1800a7101`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a736a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800a736a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a7325`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a7325`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a71cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a71cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a717f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7288`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a717f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800a7288`
- `ext-ms-win-shell-shell32-l1-2-1!SHFileOperationW` at `0x1800a73b4`
- `ext-ms-win-shell-shell32-l1-2-1!SHFileOperationW` at `0x1800a73b4`

## string_xrefs

- `0x1800a701f`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a7252`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a72dd`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a70a7`: `EFIESPVolumePath`
- `0x1800a6fe9`: `UsingFilePath`
- `0x1800a73f6`: `SuccessfullyDeletedDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FSFileOperationServiceDrivenAction::Run(FSFileOperationServiceDrivenAction *this)
{
  char *v1; // rdi
  signed int EFIESPVolumePath; // ebx
  __int64 v4; // rdx
  LPCWSTR v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int8 v7; // cl
  __int64 v8; // rcx
  FlightSettingsAPITelemetryClass *v9; // rax
  __int64 v10; // rcx
  signed int LastError; // eax
  __int64 v12; // r9
  void *v13; // rcx
  LPCWSTR v14; // rbx
  bool v15; // cc
  __int64 v16; // r8
  int v17; // eax
  unsigned __int64 v18; // r9
  __int64 v19; // rdx
  LPCWSTR v20; // r14
  signed int v21; // eax
  void *v22; // rcx
  int v23; // eax
  int v24; // eax
  unsigned __int64 v25; // rdx
  unsigned __int8 v26; // cl
  unsigned __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // rcx
  FlightSettingsAPITelemetryClass *v30; // rax
  const unsigned __int16 *v31; // rdx
  signed int v32; // eax
  DWORD FileAttributesW; // eax
  const WCHAR *v34; // rax
  signed int v35; // eax
  unsigned __int64 v36; // rdx
  unsigned __int8 v37; // cl
  __int64 v38; // rcx
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  signed int v41; // [rsp+24h] [rbp-DCh] BYREF
  unsigned __int16 v42; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpNewFileName; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h]
  __int64 v45; // [rsp+40h] [rbp-C0h]
  _QWORD v46[4]; // [rsp+48h] [rbp-B8h] BYREF
  char v47; // [rsp+68h] [rbp-98h]
  _SHFILEOPSTRUCTW FileOp; // [rsp+70h] [rbp-90h] BYREF
  WCHAR DeviceName[4]; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR TargetPath[264]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v1 = (char *)this + 56;
  wcscpy(DeviceName, L"?:");
  FlightSettingsAPITelemetryClass::FSFileOperationAction<unsigned short const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(L"UsingFilePath");
  if ( FSAllowlist::IsValueInAllowlist(*(FSAllowlist **)(*((_QWORD *)this + 18) + 24LL), *(const unsigned __int16 **)v1) )
  {
    v5 = *(LPCWSTR *)v1;
    v41 = 0;
    BYTE1(v40) = 0;
    if ( !(unsigned int)_o__wcsnicmp(v5, L"\\EFI", 2) )
    {
      memset_0(TargetPath, 0, 0x208u);
      EFIESPVolumePath = FSFileOperationServiceDrivenAction::GetEFIESPVolumePath(TargetPath);
      if ( EFIESPVolumePath < 0 )
      {
        v4 = 94;
        goto LABEL_3;
      }
      if ( FlightSettingsAPITelemetryClass::IsEnabled(v7, v6) )
      {
        v9 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                  v8,
                                                  _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
        FlightSettingsAPITelemetryClass::FSFileOperationAction_(v9, L"EFIESPVolumePath", TargetPath);
      }
      LOBYTE(v40) = 0;
      v42 = 63;
      EFIESPVolumePath = FSFileOperationServiceDrivenAction::DetermineDriveLetterForEFIESP(
                           TargetPath,
                           &v42,
                           (bool *)&v40);
      if ( EFIESPVolumePath < 0 )
      {
        v4 = 99;
        goto LABEL_3;
      }
      DeviceName[0] = v42;
      if ( !(_BYTE)v40 )
      {
        EFIESPVolumePath = 0;
        if ( !DefineDosDeviceW(1u, DeviceName, TargetPath) )
        {
          LastError = GetLastError();
          EFIESPVolumePath = LastError;
          if ( LastError > 0 )
            EFIESPVolumePath = (unsigned __int16)LastError | 0x80070000;
        }
        v41 = EFIESPVolumePath;
        BYTE1(v40) = 1;
        if ( EFIESPVolumePath < 0 )
        {
          v4 = 106;
          goto LABEL_3;
        }
        FlightSettingsAPITelemetryClass::FSFileOperationAction<unsigned short const (&)[24],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(
          v10,
          v1);
      }
      v12 = *(_QWORD *)v1;
      lpNewFileName = 0;
      v44 = 0;
      v45 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
        &lpNewFileName,
        L"%s%s",
        DeviceName,
        v12);
      v13 = *(void **)v1;
      v14 = lpNewFileName;
      lpNewFileName = 0;
      v45 = 0;
      v44 = 0;
      if ( v13 )
        CoTaskMemFree(v13);
      *(_QWORD *)v1 = v14;
      *((_QWORD *)v1 + 2) = -1;
      *((_QWORD *)v1 + 1) = -1;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpNewFileName);
    }
    v15 = *((_DWORD *)this + 38) <= 1u;
    v46[0] = (char *)&v40 + 1;
    v46[2] = &v41;
    v46[3] = DeviceName;
    v46[1] = this;
    if ( v15 && PathFileExistsW(*(LPCWSTR *)v1) )
    {
      v16 = *(_QWORD *)v1;
      lpNewFileName = 0;
      v44 = 0;
      v45 = 0;
      v17 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              &lpNewFileName,
              L"%s.bak",
              v16);
      v41 = v17;
      EFIESPVolumePath = v17;
      if ( v17 < 0 )
      {
        v18 = (unsigned int)v17;
        v19 = 152;
        goto LABEL_30;
      }
      v20 = lpNewFileName;
      if ( !CopyFileW(*(LPCWSTR *)v1, lpNewFileName, 0) )
      {
        v21 = GetLastError();
        EFIESPVolumePath = v21;
        if ( v21 > 0 )
          EFIESPVolumePath = (unsigned __int16)v21 | 0x80070000;
        v41 = EFIESPVolumePath;
        if ( EFIESPVolumePath >= 0 )
          goto LABEL_31;
        v18 = (unsigned int)EFIESPVolumePath;
        v19 = 157;
LABEL_30:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
          (const char *)v18,
          v40);
LABEL_31:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpNewFileName);
LABEL_59:
        v47 = 0;
        lambda_59d4a9dc8efc6c4b3edb67c64f33fb01_::operator()(v46);
        return (unsigned int)EFIESPVolumePath;
      }
      lpNewFileName = 0;
      v22 = (void *)*((_QWORD *)this + 10);
      v45 = 0;
      v44 = 0;
      if ( v22 )
        CoTaskMemFree(v22);
      *((_QWORD *)this + 10) = v20;
      *((_QWORD *)this + 12) = -1;
      *((_QWORD *)this + 11) = -1;
      FlightSettingsAPITelemetryClass::FSFileOperationAction<unsigned short const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(L"SuccessfullyBackedUpFile");
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&lpNewFileName);
    }
    v23 = *((_DWORD *)this + 38);
    if ( v23 )
    {
      if ( v23 == 1 )
      {
        if ( *((_QWORD *)this + 10) && !DeleteFileW(*(LPCWSTR *)v1) )
        {
          v32 = GetLastError();
          EFIESPVolumePath = v32;
          if ( v32 > 0 )
            EFIESPVolumePath = (unsigned __int16)v32 | 0x80070000;
          v41 = EFIESPVolumePath;
          if ( EFIESPVolumePath >= 0 )
            goto LABEL_59;
          v27 = (unsigned int)EFIESPVolumePath;
          v28 = 177;
          goto LABEL_38;
        }
      }
      else if ( v23 == 2 )
      {
        FileAttributesW = GetFileAttributesW(*(LPCWSTR *)v1);
        if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
        {
          v34 = *(const WCHAR **)v1;
          memset(&FileOp.pTo, 0, 32);
          FileOp.pFrom = v34;
          *(_OWORD *)&FileOp.hwnd = 0;
          FileOp.wFunc = 3;
          FileOp.fFlags = 1044;
          SHFileOperationW(&FileOp);
          v35 = GetLastError();
          EFIESPVolumePath = v35;
          if ( v35 > 0 )
            EFIESPVolumePath = (unsigned __int16)v35 | 0x80070000;
          v41 = EFIESPVolumePath;
          if ( EFIESPVolumePath < 0 )
          {
            v27 = (unsigned int)EFIESPVolumePath;
            v28 = 194;
            goto LABEL_38;
          }
          if ( FlightSettingsAPITelemetryClass::IsEnabled(v37, v36) )
          {
            v30 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                       v38,
                                                       _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
            v31 = L"SuccessfullyDeletedDirectory";
            goto LABEL_57;
          }
        }
      }
    }
    else
    {
      v24 = FSFileOperationServiceDrivenAction::FlushContentToFile(this);
      v41 = v24;
      EFIESPVolumePath = v24;
      if ( v24 < 0 )
      {
        v27 = (unsigned int)v24;
        v28 = 167;
LABEL_38:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v28,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
          (const char *)v27,
          v40);
        goto LABEL_59;
      }
      if ( FlightSettingsAPITelemetryClass::IsEnabled(v26, v25) )
      {
        v30 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                                   v29,
                                                   _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
        v31 = L"SuccessfullyFlushedContentToFile";
LABEL_57:
        FlightSettingsAPITelemetryClass::FSFileOperationAction_(v30, v31, *(const unsigned __int16 **)v1);
      }
    }
    v41 = 0;
    EFIESPVolumePath = 0;
    goto LABEL_59;
  }
  EFIESPVolumePath = -2146698744;
  v4 = 83;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
    (const char *)(unsigned int)EFIESPVolumePath,
    v40);
  return (unsigned int)EFIESPVolumePath;
}

```

## disassembly

```asm
0x1800a6fa0  push    rbp
0x1800a6fa2  push    rbx
0x1800a6fa3  push    rsi
0x1800a6fa4  push    rdi
0x1800a6fa5  push    r12
0x1800a6fa7  push    r13
0x1800a6fa9  push    r14
0x1800a6fab  push    r15
0x1800a6fad  lea     rbp, [rsp-1D8h]
0x1800a6fb5  sub     rsp, 2D8h
0x1800a6fbc  mov     rax, cs:__security_cookie
0x1800a6fc3  xor     rax, rsp
0x1800a6fc6  mov     [rbp+210h+var_50], rax
0x1800a6fcd  lea     rdi, [rcx+38h]
0x1800a6fd1  mov     [rbp+210h+var_266], 3Ah ; ':'
0x1800a6fd8  mov     rsi, rcx
0x1800a6fdb  mov     r14d, 3Fh ; '?'
0x1800a6fe1  mov     rdx, rdi
0x1800a6fe4  mov     [rbp+210h+DeviceName], r14w
0x1800a6fe9  lea     rcx, aUsingfilepath; "UsingFilePath"
0x1800a6ff0  call    ??$FSFileOperationAction@AEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@FlightSettingsAPITelemetryClass@@SAXAEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction<ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a6ff5  mov     rcx, [rsi+90h]
0x1800a6ffc  mov     rdx, [rdi]; unsigned __int16 *
0x1800a6fff  mov     rcx, [rcx+18h]; this
0x1800a7003  call    ?IsValueInAllowlist@FSAllowlist@@QEAA_NPEBG@Z; FSAllowlist::IsValueInAllowlist(ushort const *)
0x1800a7008  xor     r15d, r15d
0x1800a700b  test    al, al
0x1800a700d  jnz     short loc_1800A7033
0x1800a700f  mov     ebx, 800BFA08h
0x1800a7014  lea     edx, [r14+14h]; void *
0x1800a7018  mov     rcx, [rbp+218h]; this
0x1800a701f  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a7026  mov     r9d, ebx; char *
0x1800a7029  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a702e  jmp     loc_1800A741F
0x1800a7033  mov     rcx, [rdi]
0x1800a7036  lea     rdx, aEfi; "\\EFI"
0x1800a703d  mov     r8d, 2
0x1800a7043  mov     [rsp+310h+var_2EC], r15d
0x1800a7048  mov     [rsp+310h+var_2EF], r15b
0x1800a704d  call    cs:__imp__o__wcsnicmp
0x1800a7053  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800a7057  mov     r12d, 80070000h
0x1800a705d  test    eax, eax
0x1800a705f  jnz     loc_1800A719A
0x1800a7065  xor     edx, edx; Val
0x1800a7067  lea     rcx, [rbp+210h+TargetPath]; void *
0x1800a706b  mov     r8d, 208h; Size
0x1800a7071  call    memset_0
0x1800a7076  lea     rcx, [rbp+210h+TargetPath]; unsigned __int16 *
0x1800a707a  call    ?GetEFIESPVolumePath@FSFileOperationServiceDrivenAction@@CAJPEAG@Z; FSFileOperationServiceDrivenAction::GetEFIESPVolumePath(ushort *)
0x1800a707f  mov     ebx, eax
0x1800a7081  test    eax, eax
0x1800a7083  jns     short loc_1800A708B
0x1800a7085  lea     edx, [r13+5Fh]
0x1800a7089  jmp     short loc_1800A7018
0x1800a708b  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a7090  test    al, al
0x1800a7092  jz      short loc_1800A70B3
0x1800a7094  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a709b  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a70a0  lea     r8, [rbp+210h+TargetPath]; unsigned __int16 *
0x1800a70a4  mov     rcx, rax; this
0x1800a70a7  lea     rdx, aEfiespvolumepa; "EFIESPVolumePath"
0x1800a70ae  call    ?FSFileOperationAction_@FlightSettingsAPITelemetryClass@@QEAAXPEBG0@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction_(ushort const *,ushort const *)
0x1800a70b3  lea     r8, [rsp+310h+var_2F0]; bool *
0x1800a70b8  mov     [rsp+310h+var_2F0], r15b; int
0x1800a70bd  lea     rdx, [rsp+310h+var_2E8]; unsigned __int16 *
0x1800a70c2  mov     [rsp+310h+var_2E8], r14w
0x1800a70c8  lea     rcx, [rbp+210h+TargetPath]; lpString2
0x1800a70cc  call    ?DetermineDriveLetterForEFIESP@FSFileOperationServiceDrivenAction@@CAJPEBGPEAGPEA_N@Z; FSFileOperationServiceDrivenAction::DetermineDriveLetterForEFIESP(ushort const *,ushort *,bool *)
0x1800a70d1  mov     ebx, eax
0x1800a70d3  test    eax, eax
0x1800a70d5  jns     short loc_1800A70E1
0x1800a70d7  mov     edx, 63h ; 'c'
0x1800a70dc  jmp     loc_1800A7018
0x1800a70e1  movzx   eax, [rsp+310h+var_2E8]
0x1800a70e6  mov     [rbp+210h+DeviceName], ax
0x1800a70ea  cmp     [rsp+310h+var_2F0], r15b
0x1800a70ef  jnz     short loc_1800A713C
0x1800a70f1  lea     r8, [rbp+210h+TargetPath]; lpTargetPath
0x1800a70f5  mov     ecx, 1; dwFlags
0x1800a70fa  lea     rdx, [rbp+210h+DeviceName]; lpDeviceName
0x1800a70fe  mov     ebx, r15d
0x1800a7101  call    cs:__imp_DefineDosDeviceW
0x1800a7107  test    eax, eax
0x1800a7109  jnz     short loc_1800A711D
0x1800a710b  call    cs:__imp_GetLastError
0x1800a7111  mov     ebx, eax
0x1800a7113  test    eax, eax
0x1800a7115  jle     short loc_1800A711D
0x1800a7117  movzx   ebx, ax
0x1800a711a  or      ebx, r12d
0x1800a711d  mov     [rsp+310h+var_2EC], ebx
0x1800a7121  mov     [rsp+310h+var_2EF], 1
0x1800a7126  test    ebx, ebx
0x1800a7128  jns     short loc_1800A7134
0x1800a712a  mov     edx, 6Ah ; 'j'
0x1800a712f  jmp     loc_1800A7018
0x1800a7134  mov     rdx, rdi
0x1800a7137  call    ??$FSFileOperationAction@AEAY0BI@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@FlightSettingsAPITelemetryClass@@SAXAEAY0BI@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction<ushort const (&)[24],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(ushort const (&)[24],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a713c  mov     r9, [rdi]
0x1800a713f  lea     r8, [rbp+210h+DeviceName]
0x1800a7143  lea     rdx, aSS_4; "%s%s"
0x1800a714a  mov     [rsp+310h+lpNewFileName], r15
0x1800a714f  lea     rcx, [rsp+310h+lpNewFileName]
0x1800a7154  mov     [rsp+310h+var_2D8], r15
0x1800a7159  mov     [rsp+310h+var_2D0], r15
0x1800a715e  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a7163  mov     rcx, [rdi]; pv
0x1800a7166  mov     rbx, [rsp+310h+lpNewFileName]
0x1800a716b  mov     [rsp+310h+lpNewFileName], r15
0x1800a7170  mov     [rsp+310h+var_2D0], r15
0x1800a7175  mov     [rsp+310h+var_2D8], r15
0x1800a717a  test    rcx, rcx
0x1800a717d  jz      short loc_1800A7185
0x1800a717f  call    cs:__imp_CoTaskMemFree
0x1800a7185  lea     rcx, [rsp+310h+lpNewFileName]
0x1800a718a  mov     [rdi], rbx
0x1800a718d  mov     [rdi+10h], r13
0x1800a7191  mov     [rdi+8], r13
0x1800a7195  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a719a  cmp     dword ptr [rsi+98h], 1
0x1800a71a1  lea     rax, [rsp+310h+var_2EF]
0x1800a71a6  mov     [rsp+310h+var_2C8], rax
0x1800a71ab  lea     rax, [rsp+310h+var_2EC]
0x1800a71b0  mov     [rsp+310h+var_2B8], rax
0x1800a71b5  lea     rax, [rbp+210h+DeviceName]
0x1800a71b9  mov     [rsp+310h+var_2B0], rax
0x1800a71be  mov     [rsp+310h+var_2C0], rsi
0x1800a71c3  ja      loc_1800A72B2
0x1800a71c9  mov     rcx, [rdi]; pszPath
0x1800a71cc  call    cs:__imp_PathFileExistsW
0x1800a71d2  test    eax, eax
0x1800a71d4  jz      loc_1800A72B2
0x1800a71da  mov     r8, [rdi]
0x1800a71dd  lea     rdx, aSBak; "%s.bak"
0x1800a71e4  lea     rcx, [rsp+310h+lpNewFileName]
0x1800a71e9  mov     [rsp+310h+lpNewFileName], r15
0x1800a71ee  mov     [rsp+310h+var_2D8], r15
0x1800a71f3  mov     [rsp+310h+var_2D0], r15
0x1800a71f8  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x1800a71fd  mov     [rsp+310h+var_2EC], eax
0x1800a7201  mov     ebx, eax
0x1800a7203  test    eax, eax
0x1800a7205  jns     short loc_1800A7211
0x1800a7207  mov     r9d, eax
0x1800a720a  mov     edx, 98h
0x1800a720f  jmp     short loc_1800A724B
0x1800a7211  mov     r14, [rsp+310h+lpNewFileName]
0x1800a7216  xor     r8d, r8d; bFailIfExists
0x1800a7219  mov     rcx, [rdi]; lpExistingFileName
0x1800a721c  mov     rdx, r14; lpNewFileName
0x1800a721f  call    cs:__imp_CopyFileW
0x1800a7225  test    eax, eax
0x1800a7227  jnz     short loc_1800A726D
0x1800a7229  call    cs:__imp_GetLastError
0x1800a722f  mov     ebx, eax
0x1800a7231  test    eax, eax
0x1800a7233  jle     short loc_1800A723B
0x1800a7235  movzx   ebx, ax
0x1800a7238  or      ebx, r12d
0x1800a723b  mov     [rsp+310h+var_2EC], ebx
0x1800a723f  test    ebx, ebx
0x1800a7241  jns     short loc_1800A725E
0x1800a7243  mov     r9d, ebx; char *
0x1800a7246  mov     edx, 9Dh; void *
0x1800a724b  mov     rcx, [rbp+218h]; this
0x1800a7252  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a7259  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a725e  lea     rcx, [rsp+310h+lpNewFileName]
0x1800a7263  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a7268  jmp     loc_1800A7410
0x1800a726d  lea     rbx, [rsi+50h]
0x1800a7271  mov     [rsp+310h+lpNewFileName], r15
0x1800a7276  mov     rcx, [rbx]; pv
0x1800a7279  mov     [rsp+310h+var_2D0], r15
0x1800a727e  mov     [rsp+310h+var_2D8], r15
0x1800a7283  test    rcx, rcx
0x1800a7286  jz      short loc_1800A728E
0x1800a7288  call    cs:__imp_CoTaskMemFree
0x1800a728e  mov     rdx, rbx
0x1800a7291  mov     [rbx], r14
0x1800a7294  lea     rcx, aSuccessfullyba; "SuccessfullyBackedUpFile"
0x1800a729b  mov     [rbx+10h], r13
0x1800a729f  mov     [rbx+8], r13
0x1800a72a3  call    ??$FSFileOperationAction@AEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@FlightSettingsAPITelemetryClass@@SAXAEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction<ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a72a8  lea     rcx, [rsp+310h+lpNewFileName]
0x1800a72ad  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a72b2  mov     eax, [rsi+98h]
0x1800a72b8  test    eax, eax
0x1800a72ba  jnz     short loc_1800A7313
0x1800a72bc  mov     rcx, rsi; this
0x1800a72bf  call    ?FlushContentToFile@FSFileOperationServiceDrivenAction@@AEAAJXZ; FSFileOperationServiceDrivenAction::FlushContentToFile(void)
0x1800a72c4  mov     [rsp+310h+var_2EC], eax
0x1800a72c8  mov     ebx, eax
0x1800a72ca  test    eax, eax
0x1800a72cc  jns     short loc_1800A72EE
0x1800a72ce  mov     r9d, eax; char *
0x1800a72d1  mov     edx, 0A7h; void *
0x1800a72d6  mov     rcx, [rbp+218h]; this
0x1800a72dd  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a72e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a72e9  jmp     loc_1800A7410
0x1800a72ee  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a72f3  test    al, al
0x1800a72f5  jz      loc_1800A7408
0x1800a72fb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a7302  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a7307  lea     rdx, aSuccessfullyfl_0; "SuccessfullyFlushedContentToFile"
0x1800a730e  jmp     loc_1800A73FD
0x1800a7313  cmp     eax, 1
0x1800a7316  jnz     short loc_1800A735E
0x1800a7318  cmp     [rsi+50h], r15
0x1800a731c  jz      loc_1800A7408
0x1800a7322  mov     rcx, [rdi]; lpFileName
0x1800a7325  call    cs:__imp_DeleteFileW
0x1800a732b  test    eax, eax
0x1800a732d  jnz     loc_1800A7408
0x1800a7333  call    cs:__imp_GetLastError
0x1800a7339  mov     ebx, eax
0x1800a733b  test    eax, eax
0x1800a733d  jle     short loc_1800A7345
0x1800a733f  movzx   ebx, ax
0x1800a7342  or      ebx, r12d
0x1800a7345  mov     [rsp+310h+var_2EC], ebx
0x1800a7349  test    ebx, ebx
0x1800a734b  jns     loc_1800A7410
0x1800a7351  mov     r9d, ebx
0x1800a7354  mov     edx, 0B1h
0x1800a7359  jmp     loc_1800A72D6
0x1800a735e  cmp     eax, 2
0x1800a7361  jnz     loc_1800A7408
0x1800a7367  mov     rcx, [rdi]; lpFileName
0x1800a736a  call    cs:__imp_GetFileAttributesW
0x1800a7370  cmp     eax, 0FFFFFFFFh
0x1800a7373  jz      loc_1800A7408
0x1800a7379  test    al, 10h
0x1800a737b  jz      loc_1800A7408
0x1800a7381  xor     eax, eax
0x1800a7383  lea     rcx, [rsp+310h+FileOp]; lpFileOp
0x1800a7388  xorps   xmm0, xmm0
0x1800a738b  mov     [rbp+210h+FileOp.lpszProgressTitle], rax
0x1800a738f  mov     rax, [rdi]
0x1800a7392  movups  xmmword ptr [rbp+210h+FileOp.pFrom], xmm0
0x1800a7396  mov     [rbp+210h+FileOp.pFrom], rax
0x1800a739a  mov     eax, 414h
0x1800a739f  movups  xmmword ptr [rsp+310h+FileOp.hwnd], xmm0
0x1800a73a4  mov     [rsp+310h+FileOp.wFunc], 3
0x1800a73ac  movups  xmmword ptr [rbp+210h+FileOp.fFlags], xmm0
0x1800a73b0  mov     [rbp+210h+FileOp.fFlags], ax
0x1800a73b4  call    cs:__imp_SHFileOperationW
0x1800a73ba  call    cs:__imp_GetLastError
0x1800a73c0  mov     ebx, eax
0x1800a73c2  test    eax, eax
0x1800a73c4  jle     short loc_1800A73CC
0x1800a73c6  movzx   ebx, ax
0x1800a73c9  or      ebx, r12d
0x1800a73cc  mov     [rsp+310h+var_2EC], ebx
0x1800a73d0  test    ebx, ebx
0x1800a73d2  jns     short loc_1800A73E1
0x1800a73d4  mov     r9d, ebx
0x1800a73d7  mov     edx, 0C2h
0x1800a73dc  jmp     loc_1800A72D6
0x1800a73e1  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a73e6  test    al, al
0x1800a73e8  jz      short loc_1800A7408
0x1800a73ea  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a73f1  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a73f6  lea     rdx, aSuccessfullyde_2; "SuccessfullyDeletedDirectory"
0x1800a73fd  mov     r8, [rdi]; unsigned __int16 *
0x1800a7400  mov     rcx, rax; this
0x1800a7403  call    ?FSFileOperationAction_@FlightSettingsAPITelemetryClass@@QEAAXPEBG0@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction_(ushort const *,ushort const *)
0x1800a7408  mov     [rsp+310h+var_2EC], r15d
0x1800a740d  mov     ebx, r15d
0x1800a7410  lea     rcx, [rsp+310h+var_2C8]
0x1800a7415  mov     [rsp+310h+var_2A8], r15b
0x1800a741a  call    _lambda_59d4a9dc8efc6c4b3edb67c64f33fb01___operator__
0x1800a741f  mov     eax, ebx
0x1800a7421  mov     rcx, [rbp+210h+var_50]
0x1800a7428  xor     rcx, rsp; StackCookie
0x1800a742b  call    __security_check_cookie
0x1800a7430  add     rsp, 2D8h
0x1800a7437  pop     r15
0x1800a7439  pop     r14
0x1800a743b  pop     r13
0x1800a743d  pop     r12
0x1800a743f  pop     rdi
0x1800a7440  pop     rsi
0x1800a7441  pop     rbx
0x1800a7442  pop     rbp
0x1800a7443  retn
```
