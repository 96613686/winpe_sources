# LogKernelDump

- ea: `0x18005c8c0`
- end: `0x18005cc90`
- name: `LogKernelDump`
- size: `976`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned int, unsigned int, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180001734`
- `0x18001b5bc`
- `0x18001f374`
- `0x180033ccc`
- `0x1800364d4`
- `0x18003e920`
- `0x18003f7a4`
- `0x180047e44`
- `0x180048804`
- `0x180048bd4`
- `0x18005c5a0`
- `0x18005c8c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005cc18`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x18005cc18`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005cc36`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005cc36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cabe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005cabe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cc58`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005cc58`
- `ntdll!RtlNtStatusToDosError` at `0x18005cbdd`
- `ntdll!RtlNtStatusToDosError` at `0x18005cbdd`
- `ntdll!NtSystemDebugControl` at `0x18005cbbb`
- `ntdll!NtSystemDebugControl` at `0x18005cbbb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005ca9b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005ca9b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cab8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cb3a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cbd5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cab8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cb3a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18005cbd5`
- `RPCRT4!UuidToStringW` at `0x18005c9aa`
- `RPCRT4!UuidToStringW` at `0x18005c9aa`
- `RPCRT4!UuidCreate` at `0x18005c934`
- `RPCRT4!UuidCreate` at `0x18005c934`
- `RPCRT4!RpcStringFreeW` at `0x18005cc49`
- `RPCRT4!RpcStringFreeW` at `0x18005cc49`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall LogKernelDump(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v8; // rsi
  __int64 v9; // r15
  RPC_STATUS v10; // eax
  unsigned int LastError; // edi
  const struct _tlgProvider_t *v12; // rax
  int v13; // r8d
  int v14; // r9d
  int v15; // ecx
  char *v16; // rdx
  int *v17; // rax
  const struct _tlgProvider_t *v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // rax
  const WCHAR *v23; // rcx
  HANDLE FileW; // rax
  const WCHAR *v25; // rcx
  const struct _tlgProvider_t *v26; // r8
  int v27; // r9d
  __int16 *v28; // rdx
  const WCHAR *v29; // rcx
  int v30; // ebx
  const WCHAR *v31; // rcx
  int v32; // ebx
  void *v33; // rax
  LPCWSTR *v34; // r8
  int *hTemplateFile; // [rsp+30h] [rbp-D0h]
  int v37; // [rsp+40h] [rbp-C0h] BYREF
  int v38; // [rsp+44h] [rbp-BCh] BYREF
  const char *v39; // [rsp+48h] [rbp-B8h] BYREF
  RPC_WSTR StringUuid; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v41; // [rsp+58h] [rbp-A8h] BYREF
  _DWORD InputBuffer[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h]
  __int64 *v44; // [rsp+70h] [rbp-90h]
  __int64 v45; // [rsp+78h] [rbp-88h]
  __int64 v46; // [rsp+80h] [rbp-80h]
  __int64 v47; // [rsp+88h] [rbp-78h]
  int v48; // [rsp+98h] [rbp-68h]
  LPCWSTR lpFileName[2]; // [rsp+B0h] [rbp-50h] BYREF
  int v50; // [rsp+C0h] [rbp-40h]
  unsigned __int64 v51; // [rsp+C8h] [rbp-38h]
  UUID Uuid; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v53[32]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v54[32]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v55[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v56[32]; // [rsp+140h] [rbp+40h] BYREF

  v41 = a3;
  v8 = -1;
  v9 = a4;
  memset_0(InputBuffer, 0, 0x48u);
  std::wstring::wstring(lpFileName);
  StringUuid = 0;
  Uuid = 0;
  v10 = UuidCreate(&Uuid);
  LastError = v10;
  if ( v10 && v10 != 1824 )
  {
    v12 = AudioEndpointBuilderTelemetryProvider::Provider();
    v15 = (int)v12;
    if ( *(_DWORD *)v12 <= 2u )
      goto LABEL_31;
    v37 = LastError;
    v39 = "LogKernelDump";
    v16 = byte_18007854B;
    v38 = 308;
    hTemplateFile = &v37;
    v17 = &v38;
LABEL_5:
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v15,
      (_DWORD)v16,
      v13,
      v14,
      (__int64)&v39,
      (__int64)v17,
      (__int64)hTemplateFile);
    goto LABEL_31;
  }
  LastError = UuidToStringW(&Uuid, &StringUuid);
  if ( LastError )
  {
    v18 = AudioEndpointBuilderTelemetryProvider::Provider();
    v15 = (int)v18;
    if ( *(_DWORD *)v18 <= 2u )
      goto LABEL_31;
    v38 = LastError;
    v39 = "LogKernelDump";
    v16 = byte_180078513;
    v37 = 324;
    hTemplateFile = &v38;
    v17 = &v37;
    goto LABEL_5;
  }
  v19 = std::wstring::wstring(v56, StringUuid);
  v20 = std::wstring::wstring(v55, a6);
  std::wstring::wstring(v53, v21, v20, v19);
  v22 = std::operator+<unsigned short>(v54, v53, L".dmp");
  std::wstring::operator=(lpFileName, v22);
  std::wstring::_Tidy_deallocate(v54);
  std::wstring::_Tidy_deallocate(v53);
  std::wstring::_Tidy_deallocate(v55);
  std::wstring::_Tidy_deallocate(v56);
  v23 = (const WCHAR *)lpFileName;
  if ( v51 > 7 )
    v23 = lpFileName[0];
  FileW = CreateFileW(v23, 0x40040001u, 0, 0, 2u, 0x80u, 0);
  v8 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    v25 = (const WCHAR *)lpFileName;
    if ( v51 > 7 )
      v25 = lpFileName[0];
    DeleteFileW(v25);
    LastError = GetLastError();
    v26 = AudioEndpointBuilderTelemetryProvider::Provider();
    if ( *(_DWORD *)v26 > 2u )
    {
      v37 = 358;
      v28 = (__int16 *)byte_1800784DD;
LABEL_17:
      v39 = "LogKernelDump";
      v38 = LastError;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v26,
        (_DWORD)v28,
        (_DWORD)v26,
        v27,
        (__int64)&v39,
        (__int64)&v37,
        (__int64)&v38);
    }
  }
  else
  {
    LastError = SetDumpFileSecurity(FileW);
    if ( LastError )
    {
      v29 = (const WCHAR *)lpFileName;
      if ( v51 > 7 )
        v29 = lpFileName[0];
      DeleteFileW(v29);
      v26 = AudioEndpointBuilderTelemetryProvider::Provider();
      if ( *(_DWORD *)v26 > 2u )
      {
        v37 = 375;
        v28 = &word_18007849E;
        goto LABEL_17;
      }
    }
    else
    {
      v48 |= 4u;
      v44 = &v41;
      InputBuffer[0] = 2;
      InputBuffer[1] = 353;
      v43 = a2;
      v45 = v9;
      v46 = a5;
      v47 = v8;
      v30 = NtSystemDebugControl(SysDbgClearUmAttachPid|SysDbgQueryTraceInformation, InputBuffer, 0x48u, 0, 0, 0);
      if ( v30 >= 0 )
      {
        v32 = 2 * v50 + 2;
        v33 = malloc(2 * v32);
        v34 = lpFileName;
        if ( v51 > 7 )
          v34 = (LPCWSTR *)lpFileName[0];
        *a7 = v33;
        _o_wcscpy_s(v33, v32, v34);
      }
      else
      {
        v31 = (const WCHAR *)lpFileName;
        if ( v51 > 7 )
          v31 = lpFileName[0];
        DeleteFileW(v31);
        LastError = RtlNtStatusToDosError(v30);
        v26 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v26 > 2u )
        {
          v37 = 408;
          v28 = &word_18007845E;
          goto LABEL_17;
        }
      }
    }
  }
LABEL_31:
  if ( StringUuid )
    RpcStringFreeW(&StringUuid);
  if ( v8 != -1 )
    CloseHandle((HANDLE)v8);
  std::wstring::_Tidy_deallocate(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x18005c8c0  mov     [rsp-8+arg_0], rbx
0x18005c8c5  push    rbp
0x18005c8c6  push    rsi
0x18005c8c7  push    rdi
0x18005c8c8  push    r12
0x18005c8ca  push    r13
0x18005c8cc  push    r14
0x18005c8ce  push    r15
0x18005c8d0  lea     rbp, [rsp-70h]
0x18005c8d5  sub     rsp, 170h
0x18005c8dc  mov     rax, cs:__security_cookie
0x18005c8e3  xor     rax, rsp
0x18005c8e6  mov     [rbp+0A0h+var_40], rax
0x18005c8ea  mov     r13, [rbp+0A0h+arg_28]
0x18005c8f1  lea     rcx, [rsp+1A0h+InputBuffer]; void *
0x18005c8f6  mov     r12, [rbp+0A0h+arg_30]
0x18005c8fd  mov     r14, rdx
0x18005c900  mov     [rsp+1A0h+var_148], r8
0x18005c905  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005c909  xor     edx, edx; Val
0x18005c90b  mov     r15d, r9d
0x18005c90e  lea     r8d, [rsi+49h]; Size
0x18005c912  call    memset_0
0x18005c917  lea     rcx, [rbp+0A0h+lpFileName]
0x18005c91b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18005c920  xorps   xmm1, xmm1
0x18005c923  mov     [rsp+1A0h+StringUuid], 0
0x18005c92c  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x18005c930  movups  xmmword ptr [rbp+0A0h+Uuid.Data1], xmm1
0x18005c934  call    cs:__imp_UuidCreate
0x18005c93a  mov     edi, eax
0x18005c93c  test    eax, eax
0x18005c93e  jz      short loc_18005C9A1
0x18005c940  cmp     eax, 720h
0x18005c945  jz      short loc_18005C9A1
0x18005c947  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c94c  mov     rcx, rax
0x18005c94f  mov     eax, [rax]
0x18005c951  cmp     eax, 2
0x18005c954  jbe     loc_18005CC3C
0x18005c95a  lea     rax, aLogkerneldump; "LogKernelDump"
0x18005c961  mov     [rsp+1A0h+var_160], edi
0x18005c965  mov     [rsp+1A0h+var_158], rax
0x18005c96a  lea     rdx, byte_18007854B
0x18005c971  lea     rax, [rsp+1A0h+var_160]
0x18005c976  mov     [rsp+1A0h+var_15C], 134h
0x18005c97e  mov     [rsp+1A0h+hTemplateFile], rax
0x18005c983  lea     rax, [rsp+1A0h+var_15C]
0x18005c988  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], rax
0x18005c98d  lea     rax, [rsp+1A0h+var_158]
0x18005c992  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x18005c997  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18005c99c  jmp     loc_18005CC3C
0x18005c9a1  lea     rdx, [rsp+1A0h+StringUuid]; StringUuid
0x18005c9a6  lea     rcx, [rbp+0A0h+Uuid]; Uuid
0x18005c9aa  call    cs:__imp_UuidToStringW
0x18005c9b0  mov     edi, eax
0x18005c9b2  test    eax, eax
0x18005c9b4  jz      short loc_18005C9F9
0x18005c9b6  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005c9bb  mov     rcx, rax
0x18005c9be  mov     eax, [rax]
0x18005c9c0  cmp     eax, 2
0x18005c9c3  jbe     loc_18005CC3C
0x18005c9c9  lea     rax, aLogkerneldump; "LogKernelDump"
0x18005c9d0  mov     [rsp+1A0h+var_15C], edi
0x18005c9d4  mov     [rsp+1A0h+var_158], rax
0x18005c9d9  lea     rdx, byte_180078513
0x18005c9e0  lea     rax, [rsp+1A0h+var_15C]
0x18005c9e5  mov     [rsp+1A0h+var_160], 144h
0x18005c9ed  mov     [rsp+1A0h+hTemplateFile], rax
0x18005c9f2  lea     rax, [rsp+1A0h+var_160]
0x18005c9f7  jmp     short loc_18005C988
0x18005c9f9  mov     rdx, [rsp+1A0h+StringUuid]
0x18005c9fe  lea     rcx, [rbp+0A0h+var_60]
0x18005ca02  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ca07  mov     rdx, r13
0x18005ca0a  lea     rcx, [rbp+0A0h+var_80]
0x18005ca0e  mov     rbx, rax
0x18005ca11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005ca16  mov     r9, rbx
0x18005ca19  lea     rcx, [rbp+0A0h+var_C0]
0x18005ca1d  mov     r8, rax
0x18005ca20  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEAV01@1@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring &,std::wstring &)
0x18005ca25  lea     r8, aDmp; ".dmp"
0x18005ca2c  lea     rdx, [rbp+0A0h+var_C0]
0x18005ca30  lea     rcx, [rbp+0A0h+var_A0]
0x18005ca34  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18005ca39  mov     rdx, rax
0x18005ca3c  lea     rcx, [rbp+0A0h+lpFileName]
0x18005ca40  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18005ca45  lea     rcx, [rbp+0A0h+var_A0]
0x18005ca49  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ca4e  lea     rcx, [rbp+0A0h+var_C0]
0x18005ca52  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ca57  lea     rcx, [rbp+0A0h+var_80]
0x18005ca5b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ca60  lea     rcx, [rbp+0A0h+var_60]
0x18005ca64  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005ca69  cmp     [rbp+0A0h+var_D8], 7
0x18005ca6e  lea     rcx, [rbp+0A0h+lpFileName]
0x18005ca72  mov     [rsp+1A0h+hTemplateFile], 0; hTemplateFile
0x18005ca7b  mov     edx, 40040001h; dwDesiredAccess
0x18005ca80  cmova   rcx, [rbp+0A0h+lpFileName]; lpFileName
0x18005ca85  xor     r9d, r9d; lpSecurityAttributes
0x18005ca88  xor     r8d, r8d; dwShareMode
0x18005ca8b  mov     [rsp+1A0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18005ca93  mov     [rsp+1A0h+dwCreationDisposition], 2; dwCreationDisposition
0x18005ca9b  call    cs:__imp_CreateFileW
0x18005caa1  mov     rsi, rax
0x18005caa4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005caa8  jnz     short loc_18005CB1E
0x18005caaa  cmp     [rbp+0A0h+var_D8], 7
0x18005caaf  lea     rcx, [rbp+0A0h+lpFileName]
0x18005cab3  cmova   rcx, [rbp+0A0h+lpFileName]; lpFileName
0x18005cab8  call    cs:__imp_DeleteFileW
0x18005cabe  call    cs:__imp_GetLastError
0x18005cac4  mov     edi, eax
0x18005cac6  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005cacb  mov     r8, rax
0x18005cace  mov     ecx, [rax]
0x18005cad0  cmp     ecx, 2
0x18005cad3  jbe     loc_18005CC3C
0x18005cad9  mov     [rsp+1A0h+var_160], 166h
0x18005cae1  lea     rdx, byte_1800784DD
0x18005cae8  lea     rax, aLogkerneldump; "LogKernelDump"
0x18005caef  mov     [rsp+1A0h+var_158], rax
0x18005caf4  lea     rax, [rsp+1A0h+var_15C]
0x18005caf9  mov     [rsp+1A0h+hTemplateFile], rax
0x18005cafe  lea     rax, [rsp+1A0h+var_160]
0x18005cb03  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], rax
0x18005cb08  lea     rax, [rsp+1A0h+var_158]
0x18005cb0d  mov     qword ptr [rsp+1A0h+dwCreationDisposition], rax
0x18005cb12  mov     [rsp+1A0h+var_15C], edi
0x18005cb16  mov     rcx, r8
0x18005cb19  jmp     loc_18005C997
0x18005cb1e  mov     rcx, rsi; handle
0x18005cb21  call    ?SetDumpFileSecurity@@YAKPEAX@Z; SetDumpFileSecurity(void *)
0x18005cb26  mov     edi, eax
0x18005cb28  test    eax, eax
0x18005cb2a  jz      short loc_18005CB64
0x18005cb2c  cmp     [rbp+0A0h+var_D8], 7
0x18005cb31  lea     rcx, [rbp+0A0h+lpFileName]
0x18005cb35  cmova   rcx, [rbp+0A0h+lpFileName]; lpFileName
0x18005cb3a  call    cs:__imp_DeleteFileW
0x18005cb40  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005cb45  mov     r8, rax
0x18005cb48  mov     ecx, [rax]
0x18005cb4a  cmp     ecx, 2
0x18005cb4d  jbe     loc_18005CC3C
0x18005cb53  mov     [rsp+1A0h+var_160], 177h
0x18005cb5b  lea     rdx, word_18007849E
0x18005cb62  jmp     short loc_18005CAE8
0x18005cb64  or      [rbp+0A0h+var_108], 4
0x18005cb68  lea     rax, [rsp+1A0h+var_148]
0x18005cb6d  xor     r9d, r9d; OutputBuffer
0x18005cb70  mov     [rsp+1A0h+var_130], rax
0x18005cb75  mov     eax, [rbp+0A0h+arg_20]
0x18005cb7b  lea     rdx, [rsp+1A0h+InputBuffer]; InputBuffer
0x18005cb80  mov     qword ptr [rsp+1A0h+dwFlagsAndAttributes], 0; ReturnLength
0x18005cb89  mov     [rsp+1A0h+InputBuffer], 2
0x18005cb91  lea     r8d, [r9+48h]; InputBufferLength
0x18005cb95  mov     [rsp+1A0h+var_13C], 161h
0x18005cb9d  lea     ecx, [r9+25h]; ControlCode
0x18005cba1  mov     [rsp+1A0h+var_138], r14
0x18005cba6  mov     [rsp+1A0h+var_128], r15
0x18005cbab  mov     [rbp+0A0h+var_120], rax
0x18005cbaf  mov     [rbp+0A0h+var_118], rsi
0x18005cbb3  mov     [rsp+1A0h+dwCreationDisposition], 0; OutputBufferLength
0x18005cbbb  call    cs:__imp_NtSystemDebugControl
0x18005cbc1  mov     ebx, eax
0x18005cbc3  test    eax, eax
0x18005cbc5  jns     short loc_18005CC08
0x18005cbc7  cmp     [rbp+0A0h+var_D8], 7
0x18005cbcc  lea     rcx, [rbp+0A0h+lpFileName]
0x18005cbd0  cmova   rcx, [rbp+0A0h+lpFileName]; lpFileName
0x18005cbd5  call    cs:__imp_DeleteFileW
0x18005cbdb  mov     ecx, ebx; Status
0x18005cbdd  call    cs:__imp_RtlNtStatusToDosError
0x18005cbe3  mov     edi, eax
0x18005cbe5  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005cbea  mov     r8, rax
0x18005cbed  mov     ecx, [rax]
0x18005cbef  cmp     ecx, 2
0x18005cbf2  jbe     short loc_18005CC3C
0x18005cbf4  mov     [rsp+1A0h+var_160], 198h
0x18005cbfc  lea     rdx, word_18007845E
0x18005cc03  jmp     loc_18005CAE8
0x18005cc08  mov     eax, [rbp+0A0h+var_E0]
0x18005cc0b  lea     ebx, ds:2[rax*2]
0x18005cc12  lea     eax, [rbx+rbx]
0x18005cc15  movsxd  rcx, eax; Size
0x18005cc18  call    cs:__imp_malloc
0x18005cc1e  cmp     [rbp+0A0h+var_D8], 7
0x18005cc23  lea     r8, [rbp+0A0h+lpFileName]
0x18005cc27  movsxd  rdx, ebx
0x18005cc2a  mov     rcx, rax
0x18005cc2d  cmova   r8, [rbp+0A0h+lpFileName]
0x18005cc32  mov     [r12], rax
0x18005cc36  call    cs:__imp__o_wcscpy_s
0x18005cc3c  cmp     [rsp+1A0h+StringUuid], 0
0x18005cc42  jz      short loc_18005CC4F
0x18005cc44  lea     rcx, [rsp+1A0h+StringUuid]; String
0x18005cc49  call    cs:__imp_RpcStringFreeW
0x18005cc4f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18005cc53  jz      short loc_18005CC5E
0x18005cc55  mov     rcx, rsi; hObject
0x18005cc58  call    cs:__imp_CloseHandle
0x18005cc5e  lea     rcx, [rbp+0A0h+lpFileName]
0x18005cc62  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005cc67  mov     eax, edi
0x18005cc69  mov     rcx, [rbp+0A0h+var_40]
0x18005cc6d  xor     rcx, rsp; StackCookie
0x18005cc70  call    __security_check_cookie
0x18005cc75  mov     rbx, [rsp+1A0h+arg_0]
0x18005cc7d  add     rsp, 170h
0x18005cc84  pop     r15
0x18005cc86  pop     r14
0x18005cc88  pop     r13
0x18005cc8a  pop     r12
0x18005cc8c  pop     rdi
0x18005cc8d  pop     rsi
0x18005cc8e  pop     rbp
0x18005cc8f  retn
```
