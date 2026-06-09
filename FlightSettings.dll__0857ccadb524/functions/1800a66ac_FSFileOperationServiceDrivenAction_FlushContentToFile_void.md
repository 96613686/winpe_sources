# FSFileOperationServiceDrivenAction::FlushContentToFile(void)

- ea: `0x1800a66ac`
- end: `0x1800a689a`
- name: `?FlushContentToFile@FSFileOperationServiceDrivenAction@@AEAAJXZ`
- size: `494`
- prototype: `__int64 __fastcall(FSFileOperationServiceDrivenAction *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1800a6fa0`

## callees

- `0x18000cc6c`
- `0x18000cc8c`
- `0x180010e9c`
- `0x180013da0`
- `0x1800175b4`
- `0x1800177bc`
- `0x18001c6f4`
- `0x1800944a0`
- `0x1800a5f8c`
- `0x1800a61b0`
- `0x1800a6590`
- `0x1800a66ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a66ff`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800a66ff`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800a6860`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800a6860`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a679c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a679c`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6808`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800a6808`

## string_xrefs

- `0x1800a671e`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a67b8`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a682b`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`
- `0x1800a6849`: `onecore\base\flighting\flightsettings\broker\libs\serviceactions\fsfileoperationservicedrivenaction.cpp`

## pseudocode

```c
__int64 __fastcall FSFileOperationServiceDrivenAction::FlushContentToFile(FSFileOperationServiceDrivenAction *this)
{
  const unsigned __int16 **v1; // rdi
  int v3; // eax
  unsigned int LastError; // ebx
  __int64 v5; // r9
  __int64 v6; // rdx
  const unsigned __int16 *v7; // rdx
  wchar_t *v8; // rcx
  int DirectoryDeepNoThrow; // eax
  unsigned __int64 v10; // rdx
  unsigned __int8 v11; // cl
  __int64 v12; // rcx
  FlightSettingsAPITelemetryClass *v13; // rax
  const char *v14; // r9
  void *v15; // rbx
  __int64 v16; // rdx
  DWORD v17; // r8d
  const void *v18; // rdx
  int dwCreationDisposition; // [rsp+20h] [rbp-40h]
  int dwCreationDispositiona; // [rsp+20h] [rbp-40h]
  wchar_t *Str[4]; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp+20h] BYREF
  HANDLE FileW; // [rsp+88h] [rbp+28h] BYREF

  v1 = (const unsigned __int16 **)((char *)this + 56);
  memset(Str, 0, 24);
  v3 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::Initialize(
         Str,
         (char *)this + 56);
  LastError = v3;
  if ( v3 < 0 )
  {
    v5 = (unsigned int)v3;
    v6 = 378;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
      (const char *)v5,
      dwCreationDisposition);
    goto LABEL_22;
  }
  v8 = wcsrchr(Str[0], 0x5Cu);
  if ( !v8 )
  {
    LastError = -2147024809;
    v6 = 381;
    v5 = 2147942487LL;
    goto LABEL_5;
  }
  *v8 = 0;
  DirectoryDeepNoThrow = wil::CreateDirectoryDeepNoThrow((wil *)Str[0], v7);
  LastError = DirectoryDeepNoThrow;
  if ( DirectoryDeepNoThrow < 0 )
  {
    v5 = (unsigned int)DirectoryDeepNoThrow;
    v6 = 384;
    goto LABEL_5;
  }
  if ( FlightSettingsAPITelemetryClass::IsEnabled(v11, v10) )
  {
    v13 = (FlightSettingsAPITelemetryClass *)wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(
                                               v12,
                                               _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_);
    FlightSettingsAPITelemetryClass::FSFileOperationAction_(v13, L"UsingContentFlushDir", *v1);
  }
  FileW = CreateFileW(*v1, 0x120116u, 1u, 0, 2u, 0x80u, 0);
  v15 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v16 = 397;
  }
  else
  {
    FlightSettingsAPITelemetryClass::FSFileOperationAction<unsigned short const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>> &>(L"GotFileHandle");
    v17 = *((_DWORD *)this + 34);
    v18 = (const void *)*((_QWORD *)this + 16);
    NumberOfBytesWritten = 0;
    if ( WriteFile(v15, v18, v17, &NumberOfBytesWritten, 0) )
    {
      if ( !*((_DWORD *)this + 34) )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x199,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
          (const char *)0x8000FFFFLL,
          dwCreationDispositiona);
      if ( !NumberOfBytesWritten )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x19A,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationservicedrivenaction.cpp",
          (const char *)0x8000FFFFLL,
          dwCreationDispositiona);
      if ( FlushFileBuffers(v15) )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
        LastError = 0;
        goto LABEL_22;
      }
      v16 = 412;
    }
    else
    {
      v16 = 407;
    }
  }
  LastError = wil::details::in1diag3::Return_GetLastError(
                retaddr,
                (void *)v16,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\serviceactions\\fsfileoperationser"
                              "vicedrivenaction.cpp",
                v14);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&FileW);
LABEL_22:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(Str);
  return LastError;
}

```

## disassembly

```asm
0x1800a66ac  mov     [rsp-18h+arg_10], rbx
0x1800a66b1  push    rbp
0x1800a66b2  push    rsi
0x1800a66b3  push    rdi
0x1800a66b4  mov     rbp, rsp
0x1800a66b7  sub     rsp, 60h
0x1800a66bb  lea     rdi, [rcx+38h]
0x1800a66bf  mov     [rbp+Str], 0
0x1800a66c7  mov     rsi, rcx
0x1800a66ca  mov     [rbp+var_18], 0
0x1800a66d2  mov     rdx, rdi
0x1800a66d5  mov     [rbp+var_10], 0
0x1800a66dd  lea     rcx, [rbp+Str]
0x1800a66e1  call    ?Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJAEBV123@@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::Initialize(Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> const &)
0x1800a66e6  mov     ebx, eax
0x1800a66e8  test    eax, eax
0x1800a66ea  jns     short loc_1800A66F6
0x1800a66ec  mov     r9d, eax
0x1800a66ef  mov     edx, 17Ah
0x1800a66f4  jmp     short loc_1800A671A
0x1800a66f6  mov     rcx, [rbp+Str]; Str
0x1800a66fa  mov     edx, 5Ch ; '\'; Ch
0x1800a66ff  call    cs:__imp_wcsrchr
0x1800a6705  mov     rcx, rax
0x1800a6708  test    rax, rax
0x1800a670b  jnz     short loc_1800A672F
0x1800a670d  mov     ebx, 80070057h
0x1800a6712  mov     edx, 17Dh; void *
0x1800a6717  mov     r9d, ebx; char *
0x1800a671a  mov     rcx, [rbp+18h]; this
0x1800a671e  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a6725  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a672a  jmp     loc_1800A687F
0x1800a672f  xor     eax, eax
0x1800a6731  mov     [rcx], ax
0x1800a6734  mov     rcx, [rbp+Str]; this
0x1800a6738  call    ?CreateDirectoryDeepNoThrow@wil@@YAJPEBG@Z; wil::CreateDirectoryDeepNoThrow(ushort const *)
0x1800a673d  mov     ebx, eax
0x1800a673f  test    eax, eax
0x1800a6741  jns     short loc_1800A674D
0x1800a6743  mov     r9d, eax
0x1800a6746  mov     edx, 180h
0x1800a674b  jmp     short loc_1800A671A
0x1800a674d  call    ?IsEnabled@FlightSettingsAPITelemetryClass@@SA_NE_K@Z; FlightSettingsAPITelemetryClass::IsEnabled(uchar,unsigned __int64)
0x1800a6752  test    al, al
0x1800a6754  jz      short loc_1800A6774
0x1800a6756  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_144f2b6777ef104894e0ad961c1a2ea1_@@CA@XZ; _lambda_144f2b6777ef104894e0ad961c1a2ea1_::_lambda_invoker_cdecl_(void)
0x1800a675d  call    ?get@?$static_lazy@VFlightSettingsAPITelemetryClass@@@details@wil@@QEAAPEAVFlightSettingsAPITelemetryClass@@P6AXXZ@Z; wil::details::static_lazy<FlightSettingsAPITelemetryClass>::get(void (*)(void))
0x1800a6762  mov     r8, [rdi]; unsigned __int16 *
0x1800a6765  lea     rdx, aUsingcontentfl; "UsingContentFlushDir"
0x1800a676c  mov     rcx, rax; this
0x1800a676f  call    ?FSFileOperationAction_@FlightSettingsAPITelemetryClass@@QEAAXPEBG0@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction_(ushort const *,ushort const *)
0x1800a6774  mov     rcx, [rdi]; lpFileName
0x1800a6777  xor     r9d, r9d; lpSecurityAttributes
0x1800a677a  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x1800a6783  mov     edx, 120116h; dwDesiredAccess
0x1800a6788  mov     [rsp+60h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800a6790  mov     [rsp+60h+dwCreationDisposition], 2; dwCreationDisposition
0x1800a6798  lea     r8d, [r9+1]; dwShareMode
0x1800a679c  call    cs:__imp_CreateFileW
0x1800a67a2  mov     [rbp+arg_8], rax
0x1800a67a6  mov     rbx, rax
0x1800a67a9  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a67ad  jnz     short loc_1800A67D4
0x1800a67af  mov     edx, 18Dh; void *
0x1800a67b4  mov     rcx, [rbp+18h]; this
0x1800a67b8  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a67bf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a67c4  lea     rcx, [rbp+arg_8]
0x1800a67c8  mov     ebx, eax
0x1800a67ca  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a67cf  jmp     loc_1800A687F
0x1800a67d4  mov     rdx, rdi
0x1800a67d7  lea     rcx, aGotfilehandle; "GotFileHandle"
0x1800a67de  call    ??$FSFileOperationAction@AEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@FlightSettingsAPITelemetryClass@@SAXAEAY0O@$$CBGAEAV?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@@Z; FlightSettingsAPITelemetryClass::FSFileOperationAction<ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &>(ushort const (&)[14],Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>> &)
0x1800a67e3  mov     r8d, [rsi+88h]; nNumberOfBytesToWrite
0x1800a67ea  lea     r9, [rbp+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800a67ee  mov     rdx, [rsi+80h]; lpBuffer
0x1800a67f5  mov     rcx, rbx; hFile
0x1800a67f8  mov     [rbp+NumberOfBytesWritten], 0
0x1800a67ff  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; int
0x1800a6808  call    cs:__imp_WriteFile
0x1800a680e  test    eax, eax
0x1800a6810  jnz     short loc_1800A6819
0x1800a6812  mov     edx, 197h
0x1800a6817  jmp     short loc_1800A67B4
0x1800a6819  cmp     dword ptr [rsi+88h], 0
0x1800a6820  mov     edi, 8000FFFFh
0x1800a6825  jnz     short loc_1800A683F
0x1800a6827  mov     rcx, [rbp+18h]; this
0x1800a682b  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a6832  mov     r9d, edi; char *
0x1800a6835  mov     edx, 199h; void *
0x1800a683a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a683f  cmp     [rbp+NumberOfBytesWritten], 0
0x1800a6843  jnz     short loc_1800A685D
0x1800a6845  mov     rcx, [rbp+18h]; this
0x1800a6849  lea     r8, aOnecoreBaseFli_93; "onecore\\base\\flighting\\flightsetting"...
0x1800a6850  mov     r9d, edi; char *
0x1800a6853  mov     edx, 19Ah; void *
0x1800a6858  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800a685d  mov     rcx, rbx; hFile
0x1800a6860  call    cs:__imp_FlushFileBuffers
0x1800a6866  test    eax, eax
0x1800a6868  jnz     short loc_1800A6874
0x1800a686a  mov     edx, 19Ch
0x1800a686f  jmp     loc_1800A67B4
0x1800a6874  lea     rcx, [rbp+arg_8]
0x1800a6878  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a687d  xor     ebx, ebx
0x1800a687f  lea     rcx, [rbp+Str]
0x1800a6883  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800a6888  mov     eax, ebx
0x1800a688a  mov     rbx, [rsp+60h+arg_10]
0x1800a6892  add     rsp, 60h
0x1800a6896  pop     rdi
0x1800a6897  pop     rsi
0x1800a6898  pop     rbp
0x1800a6899  retn
```
