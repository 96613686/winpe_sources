# DllMain

- ea: `0x18000e4bc`
- end: `0x18000e616`
- name: `DllMain`
- size: `346`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task`

## callers

- `0x180001c44`

## callees

- `0x180001010`
- `0x1800010c4`
- `0x1800011fc`
- `0x18000da60`
- `0x18000e4bc`
- `0x18000e888`
- `0x18000e988`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000e588`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000e588`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000e5f5`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x18000e5f5`

## string_xrefs

- `0x18000e550`: `BthAvctpSvc.dll`
- `0x18000e5a4`: `BthAvctpSvc.dll`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // r9
  REGHANDLE v12; // rcx
  _QWORD v14[3]; // [rsp+30h] [rbp-18h] BYREF
  const WCHAR *v15; // [rsp+68h] [rbp+20h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      qword_180076F60 = 0;
      dword_180076F80 = 0;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ProfilesAvrcpAvctpServiceDllTraceGuid;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      WPP_MAIN_CB = 0;
      qword_180076F68 = 1;
      qword_180076F78 = 0;
      WppInitUm(hinstDLL, fdwReason, lpvReserved);
      wil::SetResultLoggingCallback(lambda_580fc809f957a5ed450f15311f65631a_::_lambda_invoker_cdecl_);
      TraceLoggingRegisterEx_EventRegister_EventSetInformation();
      if ( (unsigned int)dword_180076000 > 5 && (unsigned __int8)tlgKeywordOn(v5, v4, v6) )
      {
        v14[0] = 33556480;
        v15 = L"BthAvctpSvc.dll";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&byte_180069CFF,
          v8,
          v9,
          (__int64)v14,
          &v15);
      }
      DisableThreadLibraryCalls(hinstDLL);
    }
  }
  else
  {
    if ( (unsigned int)dword_180076000 > 5 && (unsigned __int8)tlgKeywordOn(hinstDLL, fdwReason, lpvReserved) )
    {
      v14[0] = 33556480;
      v15 = L"BthAvctpSvc.dll";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>>(
        (__int64)v14,
        (__int64)byte_180069CC1,
        v10,
        v11,
        (__int64)v14,
        &v15);
    }
    v12 = RegHandle;
    dword_180076000 = 0;
    RegHandle = 0;
    EventUnregister(v12);
    wil::details::g_pfnLoggingCallback = 0;
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x18000e4bc  push    rbx
0x18000e4be  sub     rsp, 40h
0x18000e4c2  mov     rbx, rcx
0x18000e4c5  test    edx, edx
0x18000e4c7  jz      loc_18000E590
0x18000e4cd  cmp     edx, 1
0x18000e4d0  jnz     loc_18000E60B
0x18000e4d6  xor     eax, eax
0x18000e4d8  mov     cs:qword_180076F60, 0
0x18000e4e3  mov     cs:dword_180076F80, eax
0x18000e4e9  lea     rax, WPP_ThisDir_CTLGUID_ProfilesAvrcpAvctpServiceDllTraceGuid
0x18000e4f0  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000e4f7  lea     rax, WPP_MAIN_CB
0x18000e4fe  mov     cs:WPP_GLOBAL_Control, rax
0x18000e505  mov     cs:WPP_MAIN_CB, 0
0x18000e510  mov     cs:qword_180076F68, 1
0x18000e51b  mov     cs:qword_180076F78, 0
0x18000e526  call    WppInitUm
0x18000e52b  lea     rcx, _lambda_580fc809f957a5ed450f15311f65631a____lambda_invoker_cdecl_
0x18000e532  call    ?SetResultLoggingCallback@wil@@YAXP6AXAEBUFailureInfo@1@@_E@Z; wil::SetResultLoggingCallback(void (*)(wil::FailureInfo const &),...)
0x18000e537  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18000e53c  mov     eax, cs:dword_180076000
0x18000e542  cmp     eax, 5
0x18000e545  jbe     short loc_18000E585
0x18000e547  call    _tlgKeywordOn
0x18000e54c  test    al, al
0x18000e54e  jz      short loc_18000E585
0x18000e550  lea     rax, aBthavctpsvcDll_0; "BthAvctpSvc.dll"
0x18000e557  mov     [rsp+48h+var_18], 2000800h
0x18000e560  mov     [rsp+48h+arg_18], rax
0x18000e565  lea     rdx, byte_180069CFF
0x18000e56c  lea     rax, [rsp+48h+arg_18]
0x18000e571  mov     [rsp+48h+var_20], rax
0x18000e576  lea     rax, [rsp+48h+var_18]
0x18000e57b  mov     [rsp+48h+var_28], rax
0x18000e580  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000e585  mov     rcx, rbx; hLibModule
0x18000e588  call    cs:__imp_DisableThreadLibraryCalls
0x18000e58e  jmp     short loc_18000E60B
0x18000e590  mov     eax, cs:dword_180076000
0x18000e596  cmp     eax, 5
0x18000e599  jbe     short loc_18000E5D9
0x18000e59b  call    _tlgKeywordOn
0x18000e5a0  test    al, al
0x18000e5a2  jz      short loc_18000E5D9
0x18000e5a4  lea     rax, aBthavctpsvcDll_0; "BthAvctpSvc.dll"
0x18000e5ab  mov     [rsp+48h+var_18], 2000800h
0x18000e5b4  mov     [rsp+48h+arg_18], rax
0x18000e5b9  lea     rcx, [rsp+48h+var_18]
0x18000e5be  lea     rax, [rsp+48h+arg_18]
0x18000e5c3  mov     [rsp+48h+var_20], rax
0x18000e5c8  lea     rdx, byte_180069CC1
0x18000e5cf  mov     [rsp+48h+var_28], rcx
0x18000e5d4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &)
0x18000e5d9  mov     rcx, cs:RegHandle; RegHandle
0x18000e5e0  mov     cs:dword_180076000, 0
0x18000e5ea  mov     cs:RegHandle, 0
0x18000e5f5  call    cs:__imp_EventUnregister
0x18000e5fb  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, 0
0x18000e606  call    WppCleanupUm
0x18000e60b  mov     eax, 1
0x18000e610  add     rsp, 40h
0x18000e614  pop     rbx
0x18000e615  retn
```
