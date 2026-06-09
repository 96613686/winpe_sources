# CProtocolHandler::CreateProtocolHandler(_GUID const &,wchar_t const *,ISearchProtocol * *,IProtocolHandler * *)

- ea: `0x140043184`
- end: `0x140043300`
- name: `?CreateProtocolHandler@CProtocolHandler@@CAJAEBU_GUID@@PEB_WPEAPEAUISearchProtocol@@PEAPEAUIProtocolHandler@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(IID *rclsid, const wchar_t *, struct ISearchProtocol **, struct IProtocolHandler **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400440a4`

## callees

- `0x140005240`
- `0x14000e898`
- `0x14000f22c`
- `0x140015958`
- `0x140029998`
- `0x140037ce0`
- `0x140042870`
- `0x140043184`
- `0x1400446b0`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140043255`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x140043255`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400431dd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1400431dd`

## string_xrefs

- `0x14004327f`: `[SrchFilterDaemon] !! Failed to load protocol handler - %ws %ls`
- `0x14004328b`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\prothndlr.cxx"`

## pseudocode

```c
__int64 __fastcall CProtocolHandler::CreateProtocolHandler(
        IID *rclsid,
        const wchar_t *a2,
        struct ISearchProtocol **a3,
        struct IProtocolHandler **a4)
{
  HRESULT v8; // eax
  int v9; // ebx
  int v10; // edi
  LPOLESTR v11; // rdx
  HRESULT v13; // [rsp+30h] [rbp-39h] BYREF
  LPOLESTR lpsz; // [rsp+38h] [rbp-31h] BYREF
  LPVOID ppv; // [rsp+40h] [rbp-29h] BYREF
  LPOLESTR v16; // [rsp+48h] [rbp-21h] BYREF
  _QWORD v17[2]; // [rsp+50h] [rbp-19h] BYREF
  wchar_t v18[12]; // [rsp+60h] [rbp-9h] BYREF
  int v19; // [rsp+78h] [rbp+Fh]

  v17[1] = -2;
  v17[0] = a2;
  ppv = 0;
  v8 = CoCreateInstance(rclsid, 0, 1u, &IID_IUnknown, &ppv);
  v9 = v8;
  v13 = v8;
  if ( v8 < 0 )
  {
    v10 = v8;
  }
  else
  {
    v10 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct ISearchProtocol **))ppv)(
            ppv,
            &GUID_c73106ba_ac80_11d1_8df3_00c04fb6ef4f,
            a3);
    if ( v10 >= 0 )
      goto LABEL_9;
    v9 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, struct IProtocolHandler **))ppv)(
           ppv,
           &GUID_0b63e317_9ccc_11d0_bcdb_00805fccce04,
           a4);
    v13 = v9;
    v10 = v9;
    if ( v9 >= 0 )
      goto LABEL_9;
  }
  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  StringFromCLSID(rclsid, &lpsz);
  v19 = v9;
  StringCbPrintfW(v18, 0x16u, L"0x%08x", (unsigned int)v10);
  SearchIndexerTrace::Error(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\searchprotocolhost\\\\prothndlr.cxx\"",
    (const wchar_t *)0x4E,
    (unsigned int)L"[SrchFilterDaemon] !! Failed to load protocol handler - %ws %ls",
    v18,
    a2);
  CProtocolHandlers::ReportError(v9, a2, 0xC0000C0B);
  v11 = (LPOLESTR)&dword_14007696C;
  if ( lpsz )
    v11 = lpsz;
  v16 = v11;
  SearchIndexerDiagnosticTelemetry::ProtocolHandlerActivationFailure<wchar_t const * &,wchar_t const *,long &>(
    v17,
    &v16,
    &v13);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
LABEL_9:
  TComPointer<IBindCtx>::~TComPointer<IBindCtx>(&ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140043184  push    rbp
0x140043186  push    rbx
0x140043187  push    rsi
0x140043188  push    rdi
0x140043189  push    r14
0x14004318b  push    r15
0x14004318d  lea     rbp, [rsp-2Fh]
0x140043192  sub     rsp, 98h
0x140043199  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x1400431a1  mov     rax, cs:__security_cookie
0x1400431a8  xor     rax, rsp
0x1400431ab  mov     [rbp+57h+var_40], rax
0x1400431af  mov     rsi, r9
0x1400431b2  mov     rdi, r8
0x1400431b5  mov     r14, rdx
0x1400431b8  mov     r15, rcx
0x1400431bb  mov     [rbp+57h+var_70], rdx
0x1400431bf  mov     [rbp+57h+var_80], 0
0x1400431c7  lea     rax, [rbp+57h+var_80]
0x1400431cb  mov     [rsp+0C0h+ppv], rax; ppv
0x1400431d0  lea     r9, IID_IUnknown; riid
0x1400431d7  xor     edx, edx; pUnkOuter
0x1400431d9  lea     r8d, [rdx+1]; dwClsContext
0x1400431dd  call    cs:__imp_CoCreateInstance
0x1400431e3  mov     ebx, eax
0x1400431e5  mov     [rbp+57h+var_90], eax
0x1400431e8  test    eax, eax
0x1400431ea  js      short loc_140043239
0x1400431ec  mov     rcx, [rbp+57h+var_80]
0x1400431f0  mov     rax, [rcx]
0x1400431f3  mov     r8, rdi
0x1400431f6  lea     rdx, _GUID_c73106ba_ac80_11d1_8df3_00c04fb6ef4f
0x1400431fd  mov     rax, [rax]
0x140043200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043205  mov     edi, eax
0x140043207  test    eax, eax
0x140043209  jns     loc_1400432D9
0x14004320f  mov     rcx, [rbp+57h+var_80]
0x140043213  mov     rax, [rcx]
0x140043216  mov     r8, rsi
0x140043219  lea     rdx, _GUID_0b63e317_9ccc_11d0_bcdb_00805fccce04
0x140043220  mov     rax, [rax]
0x140043223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140043228  mov     ebx, eax
0x14004322a  mov     [rbp+57h+var_90], eax
0x14004322d  mov     edi, eax
0x14004322f  test    eax, eax
0x140043231  jns     loc_1400432D9
0x140043237  jmp     short loc_14004323B
0x140043239  mov     edi, eax
0x14004323b  mov     [rbp+57h+lpsz], 0
0x140043243  xor     edx, edx
0x140043245  lea     rcx, [rbp+57h+lpsz]
0x140043249  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14004324e  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x140043252  mov     rcx, r15; rclsid
0x140043255  call    cs:__imp_StringFromCLSID
0x14004325b  mov     [rbp+57h+var_48], ebx
0x14004325e  mov     r9d, edi
0x140043261  lea     r8, a0x08x; "0x%08x"
0x140043268  mov     edx, 16h; unsigned __int64
0x14004326d  lea     rcx, [rbp+57h+var_60]; wchar_t *
0x140043271  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x140043276  mov     [rsp+0C0h+ppv], r14
0x14004327b  lea     r9, [rbp+57h+var_60]; wchar_t *
0x14004327f  lea     r8, aSrchfilterdaem_13; "[SrchFilterDaemon] !! Failed to load pr"...
0x140043286  mov     edx, 4Eh ; 'N'; wchar_t *
0x14004328b  lea     rcx, aOnecoreuapBase_20; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x140043292  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140043297  mov     r8d, 0C0000C0Bh; unsigned int
0x14004329d  mov     rdx, r14; wchar_t *
0x1400432a0  mov     ecx, ebx; int
0x1400432a2  call    ?ReportError@CProtocolHandlers@@SAXJPEB_WK@Z; CProtocolHandlers::ReportError(long,wchar_t const *,ulong)
0x1400432a7  lea     rdx, dword_14007696C
0x1400432ae  mov     rcx, [rbp+57h+lpsz]
0x1400432b2  test    rcx, rcx
0x1400432b5  cmovnz  rdx, rcx
0x1400432b9  mov     [rbp+57h+var_78], rdx
0x1400432bd  lea     r8, [rbp+57h+var_90]
0x1400432c1  lea     rdx, [rbp+57h+var_78]
0x1400432c5  lea     rcx, [rbp+57h+var_70]
0x1400432c9  call    ??$ProtocolHandlerActivationFailure@AEAPEB_WPEB_WAEAJ@SearchIndexerDiagnosticTelemetry@@SAXAEAPEB_W$$QEAPEB_WAEAJ@Z; SearchIndexerDiagnosticTelemetry::ProtocolHandlerActivationFailure<wchar_t const * &,wchar_t const *,long &>(wchar_t const * &,wchar_t const * &&,long &)
0x1400432ce  nop
0x1400432cf  lea     rcx, [rbp+57h+lpsz]
0x1400432d3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400432d8  nop
0x1400432d9  lea     rcx, [rbp+57h+var_80]
0x1400432dd  call    ??1?$TComPointer@UIBindCtx@@@@QEAA@XZ; TComPointer<IBindCtx>::~TComPointer<IBindCtx>(void)
0x1400432e2  mov     eax, edi
0x1400432e4  mov     rcx, [rbp+57h+var_40]
0x1400432e8  xor     rcx, rsp; StackCookie
0x1400432eb  call    __security_check_cookie
0x1400432f0  add     rsp, 98h
0x1400432f7  pop     r15
0x1400432f9  pop     r14
0x1400432fb  pop     rdi
0x1400432fc  pop     rsi
0x1400432fd  pop     rbx
0x1400432fe  pop     rbp
0x1400432ff  retn
```
