# FSFileOperationServiceDrivenAction::Rollback(void)

- ea: `0x1800a6ea0`
- end: `0x1800a6f8d`
- name: `?Rollback@FSFileOperationServiceDrivenAction@@UEAAJXZ`
- size: `237`
- prototype: `__int64 __fastcall(FSFileOperationServiceDrivenAction *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x18000cc6c`
- `0x180013da0`
- `0x1800177bc`
- `0x1800a5f8c`
- `0x1800a6590`
- `0x1800a6ea0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800a6ed0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800a6f47`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800a6ed0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800a6f47`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a6f06`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800a6f06`

## string_xrefs

- `0x1800a6ee4`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a6f6d`: `SuccessfullyDeletedFileOnRollback`
- `0x1800a6f2c`: `SuccessfullyDeletedFileOnDownloadRollback`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall FSFileOperationServiceDrivenAction::Rollback(FSFileOperationServiceDrivenAction *this)
{
  int v1; // eax
  LPCWSTR *v3; // rdi
  const WCHAR *v4; // rcx
  const char *v5; // r9
  __int64 v6; // rdx
  unsigned __int64 v8; // rdx
  unsigned __int8 v9; // cl
  __int64 v10; // rcx
  FlightSettingsAPITelemetryClass *v11; // rax
  const unsigned __int16 *v12; // rdx
  const WCHAR *v13; // rcx
  unsigned __int64 v14; // rdx
  unsigned __int8 v15; // cl
  __int64 v16; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *((_DWORD *)this + 38);
  if ( v1 )
  {
    if ( v1 != 1 )
      return 0;
    v13 = (const WCHAR *)*((_QWORD *)this + 10);
    if ( !v13 )
      return 0;
    if ( !MoveFileW(v13, *((LPCWSTR *)this + 7)) )
    {
      v6 = 225;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationserv"
                             "icedrivenaction.cpp",
               v5);
    }
    if ( !FlightSettingsAPITelemetryClass::IsEnabled(v15, v14) )
      return 0;
    v11 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v16,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v12 = L"SuccessfullyDeletedFileOnRollback";
LABEL_17:
    FlightSettingsAPITelemetryClass::FSFileOperationAction_(v11, v12, *((const unsigned __int16 **)this + 7));
    return 0;
  }
  v3 = (LPCWSTR *)((char *)this + 80);
  v4 = (const WCHAR *)*((_QWORD *)this + 7);
  if ( *v3 )
  {
    if ( !MoveFileW(*v3, v4) )
    {
      v6 = 213;
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)v6,
               (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationserv"
                             "icedrivenaction.cpp",
               v5);
    }
    FlightSettingsAPITelemetryClass::FSFileOperationAction<unsigned short const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(L"SuccessfullyRestoredFile");
    return 0;
  }
  if ( !DeleteFileW(v4) )
  {
    v6 = 218;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v6,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservic"
                           "edrivenaction.cpp",
             v5);
  }
  if ( FlightSettingsAPITelemetryClass::IsEnabled(v9, v8) )
  {
    v11 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v10,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    v12 = L"SuccessfullyDeletedFileOnDownloadRollback";
    goto LABEL_17;
  }
  return 0;
}

```

## disassembly

```asm
0x1800a6ea0  mov     [rsp+arg_0], rbx
0x1800a6ea5  push    rdi
0x1800a6ea6  sub     rsp, 20h
0x1800a6eaa  mov     eax, [rcx+98h]
0x1800a6eb0  mov     rbx, rcx
0x1800a6eb3  test    eax, eax
0x1800a6eb5  jnz     short loc_1800A6F35
0x1800a6eb7  lea     rdi, [rcx+50h]
0x1800a6ebb  mov     rcx, [rcx+38h]; lpFileName
0x1800a6ebf  cmp     qword ptr [rdi], 0
0x1800a6ec3  setnz   al
0x1800a6ec6  test    al, al
0x1800a6ec8  jz      short loc_1800A6F06
0x1800a6eca  mov     rdx, rcx; lpNewFileName
0x1800a6ecd  mov     rcx, [rdi]; lpExistingFileName
0x1800a6ed0  call    cs:__imp_MoveFileW
0x1800a6ed6  test    eax, eax
0x1800a6ed8  jnz     short loc_1800A6EF5
0x1800a6eda  mov     edx, 0D5h; void *
0x1800a6edf  mov     rcx, [rsp+28h]; this
0x1800a6ee4  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a6eeb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a6ef0  jmp     loc_1800A6F82
0x1800a6ef5  mov     rdx, rdi
0x1800a6ef8  lea     rcx, aSuccessfullyre; "SuccessfullyRestoredFile"
0x1800a6eff  call    ??$FSFileOperationAction@AEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@FlightSettingsAPITelemetryClass@@SAXAEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction<ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a6f04  jmp     short loc_1800A6F80
0x1800a6f06  call    cs:__imp_DeleteFileW
0x1800a6f0c  test    eax, eax
0x1800a6f0e  jnz     short loc_1800A6F17
0x1800a6f10  mov     edx, 0DAh
0x1800a6f15  jmp     short loc_1800A6EDF
0x1800a6f17  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a6f1c  test    al, al
0x1800a6f1e  jz      short loc_1800A6F80
0x1800a6f20  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a6f27  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a6f2c  lea     rdx, aSuccessfullyde_1; "SuccessfullyDeletedFileOnDownloadRollba"...
0x1800a6f33  jmp     short loc_1800A6F74
0x1800a6f35  cmp     eax, 1
0x1800a6f38  jnz     short loc_1800A6F80
0x1800a6f3a  mov     rcx, [rcx+50h]; lpExistingFileName
0x1800a6f3e  test    rcx, rcx
0x1800a6f41  jz      short loc_1800A6F80
0x1800a6f43  mov     rdx, [rbx+38h]; lpNewFileName
0x1800a6f47  call    cs:__imp_MoveFileW
0x1800a6f4d  test    eax, eax
0x1800a6f4f  jnz     short loc_1800A6F58
0x1800a6f51  mov     edx, 0E1h
0x1800a6f56  jmp     short loc_1800A6EDF
0x1800a6f58  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a6f5d  test    al, al
0x1800a6f5f  jz      short loc_1800A6F80
0x1800a6f61  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a6f68  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a6f6d  lea     rdx, aSuccessfullyde_0; "SuccessfullyDeletedFileOnRollback"
0x1800a6f74  mov     r8, [rbx+38h]; unsigned __int16 *
0x1800a6f78  mov     rcx, rax; this
0x1800a6f7b  call    ?FSFileOperationAction_@FlightSettingsAPITelemetryClass@@QEAAXPEBG0@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction_(ushort const *,ushort const *)
0x1800a6f80  xor     eax, eax
0x1800a6f82  mov     rbx, [rsp+28h+arg_0]
0x1800a6f87  add     rsp, 20h
0x1800a6f8b  pop     rdi
0x1800a6f8c  retn
```
