# WaasMedic::TimeHelper::SyncSystemTime(void)

- ea: `0x180030d34`
- end: `0x180030ee2`
- name: `?SyncSystemTime@TimeHelper@WaasMedic@@SAJXZ`
- size: `430`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18004edb0`

## callees

- `0x1800024a4`
- `0x180016c9c`
- `0x18002543c`
- `0x180030d34`
- `0x180033fa8`
- `0x18003613c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030dc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030dc7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030e8a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030e8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030e92`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180030dad`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180030dad`

## string_xrefs

- `0x180030d4a`: `Attempting to enable and start service %s`
- `0x180030d7d`: `Failed to enable service %s, hr = 0x%08X.`
- `0x180030da6`: `w32time.DLL`
- `0x180030eaa`: `w32time.DLL`
- `0x180030eb1`: `Failed to load library: %s.  TimeSyncPlugin may not supported in this SKU, , hr = 0x%08X.`

## pseudocode

```c
__int64 WaasMedic::TimeHelper::SyncSystemTime(void)
{
  const unsigned __int16 *v0; // rcx
  unsigned int v1; // ebx
  unsigned int v2; // edi
  bool *v3; // r8
  HMODULE LibraryW; // rax
  HMODULE v5; // rsi
  FARPROC ProcAddress; // rax
  int v7; // eax
  const struct _tlgProvider_t *v8; // rax
  int v9; // r9d
  signed int LastError; // eax
  unsigned int v12; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v13; // [rsp+68h] [rbp+10h] BYREF
  __int64 v14; // [rsp+70h] [rbp+18h] BYREF

  LogLevelW(4u, L"Attempting to enable and start service %s", L"w32time");
  v1 = WaasMedic::CSvcUtil::EnableService(v0);
  v2 = v1;
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -2147023840 )
  {
    LogLevelW(3u, L"Failed to enable service %s, hr = 0x%08X.", L"w32time", v1);
LABEL_19:
    WaasMedic::CSvcUtil::ServiceStop(L"w32time", 0, v3);
    return v1;
  }
  LogLevelW(4u, L"%s was successfully enabled.", L"w32time");
  LibraryW = LoadLibraryW(L"w32time.DLL");
  v5 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x19);
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
      v1 = v7;
      if ( v7 > 0 )
        v1 = (unsigned __int16)v7 | 0x80070000;
      if ( (v1 & 0x80000000) != 0 )
      {
        LogLevelW(3u, L"Failed to call W32TimeSyncNow() with hr = 0x%08X.", v1);
        v8 = WaasMedic::TelemetryProvider::Provider();
        if ( *(_DWORD *)v8 > 5u
          && (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
          && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
        {
          v12 = v1;
          v13 = &gc_pszVersionString;
          v14 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (_DWORD)v8,
            (unsigned int)byte_180089515,
            0,
            v9,
            (__int64)&v14,
            (__int64)&v13,
            (__int64)&v12);
        }
        v1 = 0;
      }
    }
    FreeLibrary(v5);
  }
  else
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    LogLevelW(
      3u,
      L"Failed to load library: %s.  TimeSyncPlugin may not supported in this SKU, , hr = 0x%08X.",
      L"w32time.DLL",
      v1);
  }
  if ( v2 != -2147023840 )
    goto LABEL_19;
  return v1;
}

```

## disassembly

```asm
0x180030d34  push    rbx
0x180030d36  push    rsi
0x180030d37  push    rdi
0x180030d38  sub     rsp, 40h
0x180030d3c  mov     esi, 4
0x180030d41  lea     r8, ServiceName; "w32time"
0x180030d48  mov     ecx, esi; unsigned __int8
0x180030d4a  lea     rdx, aAttemptingToEn; "Attempting to enable and start service "...
0x180030d51  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030d56  call    ?EnableService@CSvcUtil@WaasMedic@@SAJPEBG_N@Z; WaasMedic::CSvcUtil::EnableService(ushort const *,bool)
0x180030d5b  mov     ebx, eax
0x180030d5d  mov     edi, eax
0x180030d5f  mov     eax, 80000000h
0x180030d64  lea     ecx, [rbx+rax]
0x180030d67  test    eax, ecx
0x180030d69  jnz     short loc_180030D91
0x180030d6b  cmp     ebx, 80070420h
0x180030d71  jz      short loc_180030D91
0x180030d73  mov     r9d, ebx
0x180030d76  lea     r8, ServiceName; "w32time"
0x180030d7d  lea     rdx, aFailedToEnable; "Failed to enable service %s, hr = 0x%08"...
0x180030d84  lea     ecx, [rsi-1]; unsigned __int8
0x180030d87  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030d8c  jmp     loc_180030ECA
0x180030d91  lea     r8, ServiceName; "w32time"
0x180030d98  mov     ecx, esi; unsigned __int8
0x180030d9a  lea     rdx, aSWasSuccessful; "%s was successfully enabled."
0x180030da1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030da6  lea     rcx, aW32timeDll; "w32time.DLL"
0x180030dad  call    cs:__imp_LoadLibraryW
0x180030db3  mov     rsi, rax
0x180030db6  test    rax, rax
0x180030db9  jz      loc_180030E92
0x180030dbf  mov     edx, 19h; lpProcName
0x180030dc4  mov     rcx, rax; hModule
0x180030dc7  call    cs:__imp_GetProcAddress
0x180030dcd  test    rax, rax
0x180030dd0  jz      loc_180030E87
0x180030dd6  mov     edx, 1
0x180030ddb  xor     ecx, ecx
0x180030ddd  lea     r8d, [rdx+11h]
0x180030de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030de6  mov     ebx, eax
0x180030de8  test    eax, eax
0x180030dea  jle     short loc_180030DF5
0x180030dec  movzx   ebx, ax
0x180030def  or      ebx, 80070000h
0x180030df5  test    ebx, ebx
0x180030df7  jns     loc_180030E87
0x180030dfd  mov     r8d, ebx
0x180030e00  lea     rdx, aFailedToCallW3; "Failed to call W32TimeSyncNow() with hr"...
0x180030e07  mov     ecx, 3; unsigned __int8
0x180030e0c  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030e11  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x180030e16  mov     ecx, [rax]
0x180030e18  cmp     ecx, 5
0x180030e1b  jbe     short loc_180030E85
0x180030e1d  mov     rdx, [rax+18h]
0x180030e21  mov     r8, 400000000000h
0x180030e2b  mov     rcx, [rax+10h]
0x180030e2f  test    r8, rcx
0x180030e32  jz      short loc_180030E85
0x180030e34  mov     rcx, rdx
0x180030e37  and     rcx, r8
0x180030e3a  cmp     rcx, rdx
0x180030e3d  jnz     short loc_180030E85
0x180030e3f  lea     rcx, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x180030e46  mov     [rsp+58h+arg_0], ebx
0x180030e4a  mov     [rsp+58h+arg_8], rcx
0x180030e4f  lea     rdx, byte_180089515
0x180030e56  lea     rcx, [rsp+58h+arg_0]
0x180030e5b  mov     [rsp+58h+arg_10], 1000000h
0x180030e64  mov     [rsp+58h+var_28], rcx
0x180030e69  lea     rcx, [rsp+58h+arg_8]
0x180030e6e  mov     [rsp+58h+var_30], rcx
0x180030e73  lea     rcx, [rsp+58h+arg_10]
0x180030e78  mov     [rsp+58h+var_38], rcx
0x180030e7d  mov     rcx, rax
0x180030e80  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180030e85  xor     ebx, ebx
0x180030e87  mov     rcx, rsi; hLibModule
0x180030e8a  call    cs:__imp_FreeLibrary
0x180030e90  jmp     short loc_180030EC2
0x180030e92  call    cs:__imp_GetLastError
0x180030e98  mov     ebx, eax
0x180030e9a  test    eax, eax
0x180030e9c  jle     short loc_180030EA7
0x180030e9e  movzx   ebx, ax
0x180030ea1  or      ebx, 80070000h
0x180030ea7  mov     r9d, ebx
0x180030eaa  lea     r8, aW32timeDll; "w32time.DLL"
0x180030eb1  lea     rdx, aFailedToLoadLi; "Failed to load library: %s.  TimeSyncPl"...
0x180030eb8  mov     ecx, 3; unsigned __int8
0x180030ebd  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180030ec2  cmp     edi, 80070420h
0x180030ec8  jz      short loc_180030ED8
0x180030eca  xor     edx, edx; bool
0x180030ecc  lea     rcx, ServiceName; "w32time"
0x180030ed3  call    ?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z; WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)
0x180030ed8  mov     eax, ebx
0x180030eda  add     rsp, 40h
0x180030ede  pop     rdi
0x180030edf  pop     rsi
0x180030ee0  pop     rbx
0x180030ee1  retn
```
