# WaasMedic::TimeHelper::SyncSystemTime(void)

- ea: `0x18002a0a0`
- end: `0x18002a244`
- name: `?SyncSystemTime@TimeHelper@WaasMedic@@SAJXZ`
- size: `420`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180028bec`

## callees

- `0x180002730`
- `0x18000d04c`
- `0x18002a0a0`
- `0x18002e81c`
- `0x1800376ec`
- `0x1800379b0`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a131`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002a131`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a1f5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002a1f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a1fd`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002a117`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002a117`

## string_xrefs

- `0x18002a0b7`: `Attempting to enable and start service %s`
- `0x18002a0e3`: `Failed to enable service %s, hr = 0x%08X.`
- `0x18002a110`: `w32time.DLL`
- `0x18002a215`: `w32time.DLL`
- `0x18002a21c`: `Failed to load library: %s.  TimeSyncPlugin may not supported in this SKU, , hr = 0x%08X.`

## pseudocode

```c
__int64 WaasMedic::TimeHelper::SyncSystemTime(void)
{
  const unsigned __int16 *v0; // rcx
  unsigned int v1; // ebx
  unsigned int v2; // edi
  __int64 v3; // rdx
  const unsigned __int16 *v4; // rcx
  bool *v5; // r8
  HMODULE LibraryW; // rax
  HMODULE v7; // rsi
  FARPROC ProcAddress; // rax
  int v9; // eax
  __int64 v10; // rcx
  int v11; // r9d
  signed int LastError; // eax
  unsigned int v14; // [rsp+60h] [rbp+8h] BYREF
  unsigned __int16 *v15; // [rsp+68h] [rbp+10h] BYREF
  __int64 v16; // [rsp+70h] [rbp+18h] BYREF

  LogLevelW(4u, L"Attempting to enable and start service %s", L"w32time");
  v1 = WaasMedic::CSvcUtil::EnableService(v0);
  v2 = v1;
  if ( (int)(v1 + 0x80000000) >= 0 && v1 != -2147023840 )
  {
    LogLevelW(3u, L"Failed to enable service %s, hr = 0x%08X.", L"w32time", v1);
LABEL_19:
    WaasMedic::CSvcUtil::ServiceStop(v4, v3, v5);
    return v1;
  }
  LogLevelW(4u, L"%s was successfully enabled.", L"w32time");
  LibraryW = LoadLibraryW(L"w32time.DLL");
  v7 = LibraryW;
  if ( LibraryW )
  {
    ProcAddress = GetProcAddress(LibraryW, (LPCSTR)0x19);
    if ( ProcAddress )
    {
      v9 = ((__int64 (__fastcall *)(_QWORD, __int64, __int64))ProcAddress)(0, 1, 18);
      v1 = v9;
      if ( v9 > 0 )
        v1 = (unsigned __int16)v9 | 0x80070000;
      if ( (v1 & 0x80000000) != 0 )
      {
        LogLevelW(3u, L"Failed to call W32TimeSyncNow() with hr = 0x%08X.", v1);
        v10 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
        if ( *(_DWORD *)v10 > 5u
          && (*(_QWORD *)(v10 + 16) & 0x400000000000LL) != 0
          && (*(_QWORD *)(v10 + 24) & 0x400000000000LL) == *(_QWORD *)(v10 + 24) )
        {
          v14 = v1;
          v15 = &gc_pszVersionString;
          v16 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)byte_18009302D,
            0,
            v11,
            (__int64)&v16,
            (__int64)&v15,
            (__int64)&v14);
        }
        v1 = 0;
      }
    }
    FreeLibrary(v7);
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
0x18002a0a0  push    rbx
0x18002a0a2  push    rsi
0x18002a0a3  push    rdi
0x18002a0a4  sub     rsp, 40h
0x18002a0a8  lea     rsi, ServiceName; "w32time"
0x18002a0af  mov     ecx, 4; unsigned __int8
0x18002a0b4  mov     r8, rsi
0x18002a0b7  lea     rdx, aAttemptingToEn; "Attempting to enable and start service "...
0x18002a0be  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a0c3  call    ?EnableService@CSvcUtil@WaasMedic@@SAJPEBG_N@Z; WaasMedic::CSvcUtil::EnableService(ushort const *,bool)
0x18002a0c8  mov     ebx, eax
0x18002a0ca  mov     edi, eax
0x18002a0cc  mov     eax, 80000000h
0x18002a0d1  lea     ecx, [rbx+rax]
0x18002a0d4  test    eax, ecx
0x18002a0d6  jnz     short loc_18002A0FC
0x18002a0d8  cmp     ebx, 80070420h
0x18002a0de  jz      short loc_18002A0FC
0x18002a0e0  mov     r9d, ebx
0x18002a0e3  lea     rdx, aFailedToEnable_0; "Failed to enable service %s, hr = 0x%08"...
0x18002a0ea  mov     r8, rsi
0x18002a0ed  mov     ecx, 3; unsigned __int8
0x18002a0f2  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a0f7  jmp     loc_18002A235
0x18002a0fc  mov     r8, rsi
0x18002a0ff  lea     rdx, aSWasSuccessful; "%s was successfully enabled."
0x18002a106  mov     ecx, 4; unsigned __int8
0x18002a10b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a110  lea     rcx, aW32timeDll; "w32time.DLL"
0x18002a117  call    cs:__imp_LoadLibraryW
0x18002a11d  mov     rsi, rax
0x18002a120  test    rax, rax
0x18002a123  jz      loc_18002A1FD
0x18002a129  mov     edx, 19h; lpProcName
0x18002a12e  mov     rcx, rax; hModule
0x18002a131  call    cs:__imp_GetProcAddress
0x18002a137  test    rax, rax
0x18002a13a  jz      loc_18002A1F2
0x18002a140  mov     edx, 1
0x18002a145  xor     ecx, ecx
0x18002a147  lea     r8d, [rdx+11h]
0x18002a14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a150  mov     ebx, eax
0x18002a152  test    eax, eax
0x18002a154  jle     short loc_18002A15F
0x18002a156  movzx   ebx, ax
0x18002a159  or      ebx, 80070000h
0x18002a15f  test    ebx, ebx
0x18002a161  jns     loc_18002A1F2
0x18002a167  mov     r8d, ebx
0x18002a16a  lea     rdx, aFailedToCallW3; "Failed to call W32TimeSyncNow() with hr"...
0x18002a171  mov     ecx, 3; unsigned __int8
0x18002a176  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a17b  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18002a180  mov     rcx, [rax+8]
0x18002a184  mov     eax, [rcx]
0x18002a186  cmp     eax, 5
0x18002a189  jbe     short loc_18002A1F0
0x18002a18b  mov     rdx, [rcx+18h]
0x18002a18f  mov     r8, 400000000000h
0x18002a199  mov     rax, [rcx+10h]
0x18002a19d  test    r8, rax
0x18002a1a0  jz      short loc_18002A1F0
0x18002a1a2  mov     rax, rdx
0x18002a1a5  and     rax, r8
0x18002a1a8  cmp     rax, rdx
0x18002a1ab  jnz     short loc_18002A1F0
0x18002a1ad  lea     rax, ?gc_pszVersionString@@3PAGA; ushort near * gc_pszVersionString
0x18002a1b4  mov     [rsp+58h+arg_0], ebx
0x18002a1b8  mov     [rsp+58h+arg_8], rax
0x18002a1bd  lea     rdx, byte_18009302D
0x18002a1c4  lea     rax, [rsp+58h+arg_0]
0x18002a1c9  mov     [rsp+58h+arg_10], 1000000h
0x18002a1d2  mov     [rsp+58h+var_28], rax
0x18002a1d7  lea     rax, [rsp+58h+arg_8]
0x18002a1dc  mov     [rsp+58h+var_30], rax
0x18002a1e1  lea     rax, [rsp+58h+arg_10]
0x18002a1e6  mov     [rsp+58h+var_38], rax
0x18002a1eb  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18002a1f0  xor     ebx, ebx
0x18002a1f2  mov     rcx, rsi; hLibModule
0x18002a1f5  call    cs:__imp_FreeLibrary
0x18002a1fb  jmp     short loc_18002A22D
0x18002a1fd  call    cs:__imp_GetLastError
0x18002a203  mov     ebx, eax
0x18002a205  test    eax, eax
0x18002a207  jle     short loc_18002A212
0x18002a209  movzx   ebx, ax
0x18002a20c  or      ebx, 80070000h
0x18002a212  mov     r9d, ebx
0x18002a215  lea     r8, aW32timeDll; "w32time.DLL"
0x18002a21c  lea     rdx, aFailedToLoadLi; "Failed to load library: %s.  TimeSyncPl"...
0x18002a223  mov     ecx, 3; unsigned __int8
0x18002a228  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18002a22d  cmp     edi, 80070420h
0x18002a233  jz      short loc_18002A23A
0x18002a235  call    ?ServiceStop@CSvcUtil@WaasMedic@@SAJPEBG_NPEA_N@Z; WaasMedic::CSvcUtil::ServiceStop(ushort const *,bool,bool *)
0x18002a23a  mov     eax, ebx
0x18002a23c  add     rsp, 40h
0x18002a240  pop     rdi
0x18002a241  pop     rsi
0x18002a242  pop     rbx
0x18002a243  retn
```
