# wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start(void)

- ea: `0x18001195c`
- end: `0x180011b48`
- name: `?start@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXXZ`
- size: `492`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x1800118cc`

## callees

- `0x1800026f0`
- `0x1800033bc`
- `0x18000771c`
- `0x180010b6c`
- `0x1800112d0`
- `0x1800117f0`
- `0x18001195c`
- `0x180011c3c`
- `0x180011ec8`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800119d0`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800119d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011abb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011a13`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011abb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011aa8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800119f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011aa8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800119ff`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180011ab3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x180011ab3`
- `combase!__imp_CoGetSharedServiceId` at `0x1800119ab`
- `combase!__imp_CoGetSharedServiceId` at `0x1800119ab`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011a3b`
- `combase!__imp_CoRegisterServerShutdownDelay` at `0x180011a3b`

## string_xrefs

- `0x180011b36`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180011994`: `onecore\internal\sdk\inc\wil\cppwinrtservice.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start(
        LPVOID *a1)
{
  int SharedServiceId; // eax
  void *v2; // rdx
  HANDLE Event; // rbx
  unsigned int v4; // r8d
  const char *v5; // r9
  HANDLE v6; // rdi
  DWORD LastError; // esi
  const char *v8; // r9
  int v9; // eax
  LPVOID *v10; // rax
  _QWORD *v11; // rbx
  void (__fastcall *v12)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(__int64), __int64 *, int); // r14
  HANDLE v13; // rsi
  HANDLE v14; // rdi
  DWORD v15; // ebx
  int v17; // [rsp+40h] [rbp-28h] BYREF
  const char *v18; // [rsp+48h] [rbp-20h]
  __int64 v19; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+30h]
  LPVOID *v21; // [rsp+A0h] [rbp+38h] BYREF

  v21 = a1;
  wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
    &ADPService::g_service,
    2);
  LODWORD(v21) = 0;
  v17 = 147;
  v18 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v19 = 0;
  SharedServiceId = CoGetSharedServiceId(&v21);
  if ( SharedServiceId < 0 )
    winrt::throw_hresult((unsigned int)SharedServiceId, &v17);
  wil::details::g_service_id = (unsigned int)v21;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v2, v4, v5);
  GetLastError();
  v6 = hObject;
  if ( hObject )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
    SetLastError(LastError);
  }
  hObject = Event;
  v17 = 468;
  v18 = "onecore\\internal\\sdk\\inc\\wil\\cppwinrtservice.h";
  v19 = 0;
  v9 = CoRegisterServerShutdownDelay(Event, 120000);
  if ( v9 < 0 )
    winrt::throw_hresult((unsigned int)v9, &v17);
  v21 = (LPVOID *)operator new(0x18u);
  v10 = wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(v21);
  v11 = qword_18010F9D8;
  qword_18010F9D8 = v10;
  if ( v11 )
  {
    wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(v11);
    operator delete(v11);
  }
  v12 = *(void (__fastcall **)(HANDLE *, const WCHAR *, HANDLE, __int64 (__fastcall *)(__int64), __int64 *, int))(ADPService::g_service + 192);
  v13 = hObject;
  v14 = WaitHandle;
  if ( WaitHandle )
  {
    v15 = GetLastError();
    UnregisterWait(v14);
    SetLastError(v15);
  }
  WaitHandle = 0;
  v12(
    &WaitHandle,
    L"ADPSvc",
    v13,
    `wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
    &ADPService::g_service,
    8);
  return wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(
           &ADPService::g_service,
           4);
}

```

## disassembly

```asm
0x18001195c  mov     [rsp-30h+arg_0], rcx
0x180011961  push    rbp
0x180011962  push    rbx
0x180011963  push    rsi
0x180011964  push    rdi
0x180011965  push    r12
0x180011967  push    r14
0x180011969  mov     rbp, rsp
0x18001196c  sub     rsp, 68h
0x180011970  xor     r8d, r8d
0x180011973  lea     edx, [r8+2]
0x180011977  lea     r12, ?g_service@ADPService@@3V?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@A; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform> ADPService::g_service
0x18001197e  mov     rcx, r12
0x180011981  call    ?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)
0x180011986  mov     dword ptr [rbp+arg_0], 0
0x18001198d  mov     [rbp+var_28], 93h
0x180011994  lea     r14, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\cppwi"...
0x18001199b  mov     [rbp+var_20], r14
0x18001199f  mov     [rbp+var_18], 0
0x1800119a7  lea     rcx, [rbp+arg_0]
0x1800119ab  call    cs:__imp_CoGetSharedServiceId
0x1800119b1  test    eax, eax
0x1800119b3  js      loc_180011B2A
0x1800119b9  mov     eax, dword ptr [rbp+arg_0]
0x1800119bc  mov     cs:?g_service_id@details@wil@@3KA, eax; ulong wil::details::g_service_id
0x1800119c2  xor     edx, edx; lpName
0x1800119c4  xor     ecx, ecx; lpEventAttributes
0x1800119c6  mov     r9d, 1F0003h; dwDesiredAccess
0x1800119cc  lea     r8d, [rdx+1]; dwFlags
0x1800119d0  call    cs:__imp_CreateEventExW
0x1800119d6  mov     rbx, rax
0x1800119d9  test    rax, rax
0x1800119dc  jz      loc_180011B20
0x1800119e2  call    cs:__imp_GetLastError
0x1800119e8  mov     rdi, cs:hObject
0x1800119ef  test    rdi, rdi
0x1800119f2  jz      short loc_180011A19
0x1800119f4  call    cs:__imp_GetLastError
0x1800119fa  mov     esi, eax
0x1800119fc  mov     rcx, rdi; hObject
0x1800119ff  call    cs:__imp_CloseHandle
0x180011a05  mov     rcx, [rbp+30h]; this
0x180011a09  test    eax, eax
0x180011a0b  jz      loc_180011B36
0x180011a11  mov     ecx, esi; dwErrCode
0x180011a13  call    cs:__imp_SetLastError
0x180011a19  mov     cs:hObject, rbx
0x180011a20  mov     [rbp+var_28], 1D4h
0x180011a27  mov     [rbp+var_20], r14
0x180011a2b  mov     [rbp+var_18], 0
0x180011a33  mov     edx, 1D4C0h
0x180011a38  mov     rcx, rbx
0x180011a3b  call    cs:__imp_CoRegisterServerShutdownDelay
0x180011a41  test    eax, eax
0x180011a43  js      loc_180011B14
0x180011a49  mov     edi, 18h
0x180011a4e  mov     ecx, edi; Size
0x180011a50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011a55  mov     [rbp+arg_0], rax
0x180011a59  mov     rcx, rax
0x180011a5c  call    ??0?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)
0x180011a61  nop
0x180011a62  mov     rbx, cs:qword_18010F9D8
0x180011a69  mov     cs:qword_18010F9D8, rax
0x180011a70  test    rbx, rbx
0x180011a73  jz      short loc_180011A87
0x180011a75  mov     rcx, rbx
0x180011a78  call    ??1?$svchost_module@UAggregatedDataPlatform@1Internal@Windows@winrt@@@details@wil@@QEAA@XZ; wil::details::svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::~svchost_module<winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>(void)
0x180011a7d  mov     edx, edi; unsigned __int64
0x180011a7f  mov     rcx, rbx; void *
0x180011a82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011a87  mov     rax, cs:?g_service@ADPService@@3V?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@A; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform> ADPService::g_service
0x180011a8e  mov     r14, [rax+0C0h]
0x180011a95  mov     rsi, cs:hObject
0x180011a9c  mov     rdi, cs:WaitHandle
0x180011aa3  test    rdi, rdi
0x180011aa6  jz      short loc_180011AC1
0x180011aa8  call    cs:__imp_GetLastError
0x180011aae  mov     ebx, eax
0x180011ab0  mov     rcx, rdi; WaitHandle
0x180011ab3  call    cs:__imp_UnregisterWait
0x180011ab9  mov     ecx, ebx; dwErrCode
0x180011abb  call    cs:__imp_SetLastError
0x180011ac1  mov     cs:WaitHandle, 0
0x180011acc  mov     [rsp+68h+var_40], 8
0x180011ad4  mov     [rsp+68h+var_48], r12
0x180011ad9  lea     r9, ?_lambda_invoker_cdecl_@_lambda_1_@?1??start@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXXZ@SA@PEAXE@Z; `wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::start(void)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(void *,uchar)
0x180011ae0  mov     r8, rsi
0x180011ae3  lea     rdx, ServiceName; "ADPSvc"
0x180011aea  lea     rcx, WaitHandle
0x180011af1  mov     rax, r14
0x180011af4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011af9  xor     r8d, r8d
0x180011afc  lea     edx, [r8+4]
0x180011b00  mov     rcx, r12
0x180011b03  add     rsp, 68h
0x180011b07  pop     r14
0x180011b09  pop     r12
0x180011b0b  pop     rdi
0x180011b0c  pop     rsi
0x180011b0d  pop     rbx
0x180011b0e  pop     rbp
0x180011b0f  jmp     ?update_status@?$svchost_service@UAdpServiceTraits@ADPService@@UAggregatedDataPlatform@3Internal@Windows@winrt@@@wil@@AEAAXKK@Z; wil::svchost_service<ADPService::AdpServiceTraits,winrt::Windows::Internal::AggregatedDataPlatform::AggregatedDataPlatform>::update_status(ulong,ulong)
0x180011b14  lea     rdx, [rbp+var_28]
0x180011b18  mov     ecx, eax
0x180011b1a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180011b20  mov     rcx, [rbp+30h]; this
0x180011b24  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180011b2a  lea     rdx, [rbp+var_28]
0x180011b2e  mov     ecx, eax
0x180011b30  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180011b36  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180011b3d  mov     edx, 0A0Bh; void *
0x180011b42  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
