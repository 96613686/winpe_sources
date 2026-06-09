# DllMain

- ea: `0x1800a83e4`
- end: `0x1800a86f2`
- name: `DllMain`
- size: `782`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18013f644`

## callees

- `0x1800a83e4`
- `0x1800a86f8`
- `0x1800a8730`
- `0x1800a8760`
- `0x1800a87b8`
- `0x1800f9224`
- `0x180130554`
- `0x1801406ec`
- `0x180159258`
- `0x180210010`

## import_xrefs

- `SHLWAPI!__imp_SHUnregisterClassesW` at `0x1800a865e`
- `SHLWAPI!__imp_SHUnregisterClassesW` at `0x1800a865e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800a85a7`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x1800a85a7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a86d1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800a86d1`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a866b`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a866b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a85bb`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x1800a85bb`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800a857b`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800a857b`
- `KERNEL32!ReleaseActCtx` at `0x1800a86e3`
- `KERNEL32!ReleaseActCtx` at `0x1800a86e3`
- `USER32!RegisterWindowMessageW` at `0x1800a85c8`
- `USER32!RegisterWindowMessageW` at `0x1800a85c8`
- `GDI32!DeleteObject` at `0x1800a86c6`
- `GDI32!DeleteObject` at `0x1800a86c6`

## string_xrefs

- `0x1800a85c1`: `ItemsviewSpyServiceRequest`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v5; // rdi
  const GUID **v6; // r14
  const GUID *v7; // r8
  struct ATL::_ATL_OBJMAP_ENTRY30 *v8; // rdx
  ATL::CComModule *v9; // rcx
  HINSTANCE v10; // r8
  const struct _GUID *v11; // r9
  ATL::CComModule *v12; // rcx
  CGlobalObject *v13; // rcx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // rdx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-D8h] BYREF
  _BYTE v17[200]; // [rsp+50h] [rbp-C8h] BYREF

  if ( fdwReason == 1 )
  {
    qword_180292E18 = 1;
    qword_180292E10 = 0;
    WPP_MAIN_CB = (__int64)&qword_180292E28;
    v5 = (ULONG64 *)&WPP_MAIN_CB;
    qword_180292E38 = 0;
    qword_180292E28 = (__int64)&qword_180292E50;
    v6 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    qword_180292E40 = 1;
    qword_180292E50 = (__int64)&qword_180292E78;
    qword_180292E78 = (__int64)&qword_180292EA0;
    qword_180292EA0 = (__int64)&qword_180292EC8;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShellTraceProvider;
    qword_180292EF8 = (__int64)WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
    qword_180292F00 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
    qword_180292F08 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider;
    qword_180292F10 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider;
    qword_180292F18 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider;
    qword_180292E60 = 0;
    qword_180292E68 = 1;
    qword_180292E88 = 0;
    qword_180292E90 = 1;
    qword_180292EB0 = 0;
    qword_180292EB8 = 1;
    qword_180292ED8 = 0;
    qword_180292EC8 = 0;
    qword_180292EE0 = 1;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    do
    {
      v7 = *v6;
      TraceGuidReg.Guid = v7;
      ++v6;
      TraceGuidReg.RegHandle = 0;
      v5[4] = (ULONG64)v7;
      RegisterTraceGuidsW(WppControlCallback, v5, v7, 1u, &TraceGuidReg, 0, 0, v5 + 1);
      v5 = (ULONG64 *)*v5;
    }
    while ( v5 );
    McGenEventRegister_EventRegister();
    hModule = hinstDLL;
    dword_180292F48 = 123;
    ATL::CComModule::Init(v9, v8, v10, v11);
    DisableThreadLibraryCalls(hinstDLL);
    g_hinst = hinstDLL;
    InitializeCriticalSection(&g_csToolTipHookLock);
    g_msgItemsviewMarshal = RegisterWindowMessageW(L"ItemsviewSpyServiceRequest");
    if ( wil::details::g_pfnTelemetryCallback
      && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != FileExplorerErrorFallback::FallbackTelemetryCallback )
    {
      memset_0(v17, 0, 0x98u);
      wil::details::WilFailFast((wil::details *)v17, v15);
    }
    wil::details::g_pfnTelemetryCallback = (__int64)FileExplorerErrorFallback::FallbackTelemetryCallback;
  }
  else if ( !fdwReason )
  {
    g_bProcessShutdown = lpvReserved != 0;
    if ( g_hpalHalftone )
      DeleteObject(g_hpalHalftone);
    v12 = (ATL::CComModule *)g_hinstImageRes;
    if ( g_hinstImageRes )
    {
      FreeLibrary(g_hinstImageRes);
      g_hinstImageRes = 0;
    }
    ATL::CComModule::Term(v12);
    CGlobalObject::Uninitialize(v13);
    v14 = _InterlockedExchange64((volatile __int64 *)&g_punkWarmScheduler, 0);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    SHUnregisterClassesW(g_hinst, off_18028F7A0, 19);
    DeleteCriticalSection(&g_csToolTipHookLock);
    if ( g_hActCtx != (HANDLE)-1LL )
    {
      ReleaseActCtx(g_hActCtx);
      g_hActCtx = (HANDLE)-1LL;
    }
    if ( hModule )
      hModule = (HMODULE)-1LL;
    McGenEventUnregister_EventUnregister();
    WppCleanupUm();
  }
  return 1;
}

```

## disassembly

```asm
0x1800a83e4  push    rbx
0x1800a83e6  push    rsi
0x1800a83e7  push    rdi
0x1800a83e8  push    r14
0x1800a83ea  sub     rsp, 0F8h
0x1800a83f1  mov     rsi, rcx
0x1800a83f4  cmp     edx, 1
0x1800a83f7  jz      short loc_1800A8415
0x1800a83f9  xor     ebx, ebx
0x1800a83fb  test    edx, edx
0x1800a83fd  jz      loc_1800A85F7
0x1800a8403  mov     eax, 1
0x1800a8408  add     rsp, 0F8h
0x1800a840f  pop     r14
0x1800a8411  pop     rdi
0x1800a8412  pop     rsi
0x1800a8413  pop     rbx
0x1800a8414  retn
0x1800a8415  xor     ebx, ebx
0x1800a8417  mov     cs:qword_180292E18, 1
0x1800a8422  lea     rax, qword_180292E28
0x1800a8429  mov     cs:qword_180292E10, rbx
0x1800a8430  mov     cs:WPP_MAIN_CB, rax
0x1800a8437  lea     rdi, WPP_MAIN_CB
0x1800a843e  lea     rax, qword_180292E50
0x1800a8445  mov     cs:qword_180292E38, rbx
0x1800a844c  mov     cs:qword_180292E28, rax
0x1800a8453  lea     r14, WPP_REGISTRATION_GUIDS
0x1800a845a  lea     rax, qword_180292E78
0x1800a8461  mov     cs:qword_180292E40, 1
0x1800a846c  mov     cs:qword_180292E50, rax
0x1800a8473  lea     rax, qword_180292EA0
0x1800a847a  mov     cs:qword_180292E78, rax
0x1800a8481  lea     rax, qword_180292EC8
0x1800a8488  mov     cs:qword_180292EA0, rax
0x1800a848f  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x1800a8496  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x1800a849d  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x1800a84a4  mov     cs:qword_180292EF8, rax
0x1800a84ab  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x1800a84b2  mov     cs:qword_180292F00, rax
0x1800a84b9  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceCredUIProvider
0x1800a84c0  mov     cs:qword_180292F08, rax
0x1800a84c7  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImageValidatorProvider
0x1800a84ce  mov     cs:qword_180292F10, rax
0x1800a84d5  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceImmersiveColorProvider
0x1800a84dc  mov     cs:qword_180292F18, rax
0x1800a84e3  mov     cs:qword_180292E60, rbx
0x1800a84ea  mov     cs:qword_180292E68, 1
0x1800a84f5  mov     cs:qword_180292E88, rbx
0x1800a84fc  mov     cs:qword_180292E90, 1
0x1800a8507  mov     cs:qword_180292EB0, rbx
0x1800a850e  mov     cs:qword_180292EB8, 1
0x1800a8519  mov     cs:qword_180292ED8, rbx
0x1800a8520  mov     cs:qword_180292EC8, rbx
0x1800a8527  mov     cs:qword_180292EE0, 1
0x1800a8532  mov     cs:WPP_GLOBAL_Control, rdi
0x1800a8539  mov     r8, [r14]; ControlGuid
0x1800a853c  lea     rax, [rdi+8]
0x1800a8540  mov     [rsp+118h+RegistrationHandle], rax; RegistrationHandle
0x1800a8545  lea     rcx, WppControlCallback; RequestAddress
0x1800a854c  mov     [rsp+118h+MofResourceName], rbx; MofResourceName
0x1800a8551  lea     rax, [rsp+118h+var_D8]
0x1800a8556  mov     [rsp+118h+var_D8.Guid], r8
0x1800a855b  lea     r14, [r14+8]
0x1800a855f  mov     [rsp+118h+var_D8.RegHandle], rbx
0x1800a8564  mov     r9d, 1; GuidCount
0x1800a856a  mov     [rsp+118h+MofImagePath], rbx; MofImagePath
0x1800a856f  mov     rdx, rdi; RequestContext
0x1800a8572  mov     [rsp+118h+TraceGuidReg], rax; TraceGuidReg
0x1800a8577  mov     [rdi+20h], r8
0x1800a857b  call    cs:__imp_RegisterTraceGuidsW
0x1800a8581  mov     rdi, [rdi]
0x1800a8584  test    rdi, rdi
0x1800a8587  jnz     short loc_1800A8539
0x1800a8589  call    McGenEventRegister_EventRegister
0x1800a858e  mov     cs:hModule, rsi
0x1800a8595  mov     cs:dword_180292F48, 7Bh ; '{'
0x1800a859f  call    ?Init@CComModule@ATL@@QEAAJPEAU_ATL_OBJMAP_ENTRY30@2@PEAUHINSTANCE__@@PEBU_GUID@@@Z; ATL::CComModule::Init(ATL::_ATL_OBJMAP_ENTRY30 *,HINSTANCE__ *,_GUID const *)
0x1800a85a4  mov     rcx, rsi; hLibModule
0x1800a85a7  call    cs:__imp_DisableThreadLibraryCalls
0x1800a85ad  lea     rcx, ?g_csToolTipHookLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a85b4  mov     cs:g_hinst, rsi
0x1800a85bb  call    cs:__imp_InitializeCriticalSection
0x1800a85c1  lea     rcx, aItemsviewspyse; "ItemsviewSpyServiceRequest"
0x1800a85c8  call    cs:__imp_RegisterWindowMessageW
0x1800a85ce  mov     cs:?g_msgItemsviewMarshal@@3IA, eax; uint g_msgItemsviewMarshal
0x1800a85d4  lea     rcx, ?FallbackTelemetryCallback@FileExplorerErrorFallback@@SAX_NAEBUFailureInfo@wil@@@Z; FileExplorerErrorFallback::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x1800a85db  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x1800a85e2  test    rax, rax
0x1800a85e5  jnz     loc_1800A86A0
0x1800a85eb  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x1800a85f2  jmp     loc_1800A8403
0x1800a85f7  mov     rcx, cs:?g_hpalHalftone@@3PEAUHPALETTE__@@EA; ho
0x1800a85fe  test    r8, r8
0x1800a8601  mov     eax, ebx
0x1800a8603  setnz   al
0x1800a8606  mov     cs:g_bProcessShutdown, eax
0x1800a860c  test    rcx, rcx
0x1800a860f  jnz     loc_1800A86C6
0x1800a8615  mov     rcx, cs:?g_hinstImageRes@@3PEAUHINSTANCE__@@EA; this
0x1800a861c  test    rcx, rcx
0x1800a861f  jnz     loc_1800A86D1
0x1800a8625  call    ?Term@CComModule@ATL@@QEAAXXZ; ATL::CComModule::Term(void)
0x1800a862a  call    ?Uninitialize@CGlobalObject@@QEAAXXZ; CGlobalObject::Uninitialize(void)
0x1800a862f  mov     rcx, rbx
0x1800a8632  xchg    rcx, cs:?g_punkWarmScheduler@@3PEAUIUnknown@@EA; IUnknown * g_punkWarmScheduler
0x1800a8639  test    rcx, rcx
0x1800a863c  jz      short loc_1800A864A
0x1800a863e  mov     rax, [rcx]
0x1800a8641  mov     rax, [rax+10h]
0x1800a8645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a864a  mov     rcx, cs:g_hinst
0x1800a8651  lea     rdx, off_18028F7A0; "Address Band Root"
0x1800a8658  mov     r8d, 13h
0x1800a865e  call    cs:__imp_SHUnregisterClassesW
0x1800a8664  lea     rcx, ?g_csToolTipHookLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a866b  call    cs:__imp_DeleteCriticalSection
0x1800a8671  mov     rcx, cs:g_hActCtx; hActCtx
0x1800a8678  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800a867c  cmp     rcx, rdi
0x1800a867f  jnz     short loc_1800A86E3
0x1800a8681  cmp     cs:hModule, rbx
0x1800a8688  jz      short loc_1800A8691
0x1800a868a  mov     cs:hModule, rdi
0x1800a8691  call    McGenEventUnregister_EventUnregister
0x1800a8696  call    WppCleanupUm
0x1800a869b  jmp     loc_1800A8403
0x1800a86a0  cmp     rax, rcx
0x1800a86a3  jz      loc_1800A85EB
0x1800a86a9  xor     edx, edx; Val
0x1800a86ab  lea     rcx, [rsp+118h+var_C8]; void *
0x1800a86b0  mov     r8d, 98h; Size
0x1800a86b6  call    memset_0
0x1800a86bb  lea     rcx, [rsp+118h+var_C8]; this
0x1800a86c0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800a86c6  call    cs:__imp_DeleteObject
0x1800a86cc  jmp     loc_1800A8615
0x1800a86d1  call    cs:__imp_FreeLibrary
0x1800a86d7  mov     cs:?g_hinstImageRes@@3PEAUHINSTANCE__@@EA, rbx; HINSTANCE__ * g_hinstImageRes
0x1800a86de  jmp     loc_1800A8625
0x1800a86e3  call    cs:__imp_ReleaseActCtx
0x1800a86e9  mov     cs:g_hActCtx, rdi
0x1800a86f0  jmp     short loc_1800A8681
```
