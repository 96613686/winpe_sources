# wWinMain

- ea: `0x1400074ec`
- end: `0x1400076ba`
- name: `wWinMain`
- size: `462`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140001ad0`

## callees

- `0x1400028a8`
- `0x140005968`
- `0x1400061a8`
- `0x1400066d0`
- `0x1400068fc`
- `0x140006c30`
- `0x140006d1c`
- `0x14000727c`
- `0x1400074ec`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000759e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14000759e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007685`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140007685`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14000752b`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x14000752b`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007668`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140007668`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007558`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007558`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleObjects` at `0x140007626`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleObjects` at `0x140007626`

## pseudocode

```c
int __stdcall wWinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPWSTR lpCmdLine, int nShowCmd)
{
  int v4; // edi
  Microsoft::WRL::Details *v5; // rbx
  struct Microsoft::WRL::Details::ModuleBase *v6; // rdx
  const unsigned __int16 *v7; // r8
  signed int LastError; // eax
  int v10; // edx
  unsigned int v11; // r8d
  const struct wil::FailureInfo *v12; // rdx
  LPVOID ppv; // [rsp+30h] [rbp-69h] BYREF
  int v14; // [rsp+38h] [rbp-61h] BYREF
  void **v15; // [rsp+40h] [rbp-59h] BYREF
  HANDLE EventW; // [rsp+48h] [rbp-51h] BYREF
  _BYTE v17[160]; // [rsp+50h] [rbp-49h] BYREF

  if ( wil::details::g_pfnTelemetryCallback
    && (void (__fastcall *)(bool, const struct wil::FailureInfo *))wil::details::g_pfnTelemetryCallback != FileDialogBrokerTraceLogging::FallbackTelemetryCallback )
  {
    memset_0(v17, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v17, v12);
  }
  wil::details::g_pfnTelemetryCallback = (__int64)FileDialogBrokerTraceLogging::FallbackTelemetryCallback;
  v4 = RoInitialize(1, hPrevInstance, lpCmdLine, nShowCmd);
  ppv = 0;
  if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 3u, &GUID_0000015b_0000_0000_c000_000000000046, &ppv) >= 0 )
  {
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 2);
    (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 4, 12);
  }
  EventW = CreateEventW(0, 0, 0, 0);
  v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( EventW )
  {
    v5 = (Microsoft::WRL::Details *)Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create();
    if ( !*((_QWORD *)v5 + 1) )
    {
      byte_1400204F8 = 1;
      byte_1400204E8 = 0;
      qword_1400204E0 = (__int64)off_140015198;
      qword_1400204F0 = (__int64)&v15;
      *((_QWORD *)v5 + 1) = &qword_1400204E0;
    }
    if ( (int)Microsoft::WRL::Details::RegisterObjects<2>(v5) >= 0 )
    {
      v14 = 0;
      CoWaitForMultipleObjects(3, 0xFFFFFFFFLL, 1, &EventW, &v14);
      Microsoft::WRL::Details::UnregisterObjects(v5, v6, v7);
    }
  }
  v15 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  if ( EventW )
  {
    if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(&v15) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v10, v11);
      __debugbreak();
    }
    EventW = 0;
  }
  wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(&ppv);
  if ( v4 >= 0 )
    RoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x1400074ec  mov     [rsp-8+arg_0], rbx
0x1400074f1  mov     [rsp-8+arg_8], rdi
0x1400074f6  push    rbp
0x1400074f7  lea     rbp, [rsp-57h]
0x1400074fc  sub     rsp, 0F0h
0x140007503  lea     rcx, ?FallbackTelemetryCallback@FileDialogBrokerTraceLogging@@SAX_NAEBUFailureInfo@wil@@@Z; FileDialogBrokerTraceLogging::FallbackTelemetryCallback(bool,wil::FailureInfo const &)
0x14000750a  mov     rax, cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA
0x140007511  test    rax, rax
0x140007514  jz      short loc_14000751F
0x140007516  cmp     rax, rcx
0x140007519  jnz     loc_14000769F
0x14000751f  mov     cs:?g_pfnTelemetryCallback@details@wil@@3P6AX_NAEBUFailureInfo@2@@_EEA, rcx
0x140007526  mov     ecx, 1
0x14000752b  call    cs:__imp_RoInitialize
0x140007531  mov     edi, eax
0x140007533  mov     [rbp+57h+var_C0], 0
0x14000753b  lea     rax, [rbp+57h+var_C0]
0x14000753f  mov     [rsp+0F0h+ppv], rax; ppv
0x140007544  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x14000754b  xor     edx, edx; pUnkOuter
0x14000754d  lea     r8d, [rdx+3]; dwClsContext
0x140007551  lea     rcx, CLSID_GlobalOptions; rclsid
0x140007558  call    cs:__imp_CoCreateInstance
0x14000755e  test    eax, eax
0x140007560  js      short loc_140007594
0x140007562  mov     rcx, [rbp+57h+var_C0]
0x140007566  mov     rax, [rcx]
0x140007569  mov     edx, 1
0x14000756e  lea     r8d, [rdx+1]
0x140007572  mov     rax, [rax+18h]
0x140007576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000757b  mov     rcx, [rbp+57h+var_C0]
0x14000757f  mov     rax, [rcx]
0x140007582  mov     edx, 4
0x140007587  lea     r8d, [rdx+8]
0x14000758b  mov     rax, [rax+18h]
0x14000758f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007594  xor     r9d, r9d; lpName
0x140007597  xor     r8d, r8d; bInitialState
0x14000759a  xor     edx, edx; bManualReset
0x14000759c  xor     ecx, ecx; lpEventAttributes
0x14000759e  call    cs:__imp_CreateEventW
0x1400075a4  mov     [rbp+57h+var_A8], rax
0x1400075a8  lea     rcx, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x1400075af  mov     [rbp+57h+var_B0], rcx
0x1400075b3  test    rax, rax
0x1400075b6  jz      short loc_140007634
0x1400075b8  call    ?Create@?$OutOfProcModuleBase@V?$DefaultModule@$01@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@SAAEAV?$DefaultModule@$01@234@XZ; Microsoft::WRL::Details::OutOfProcModuleBase<Microsoft::WRL::Details::DefaultModule<2>>::Create(void)
0x1400075bd  mov     rbx, rax
0x1400075c0  cmp     qword ptr [rax+8], 0
0x1400075c5  jnz     short loc_1400075F9
0x1400075c7  mov     cs:byte_1400204F8, 1
0x1400075ce  mov     cs:byte_1400204E8, 0
0x1400075d5  lea     rax, off_140015198
0x1400075dc  mov     cs:qword_1400204E0, rax
0x1400075e3  lea     rax, [rbp+57h+var_B0]
0x1400075e7  mov     cs:qword_1400204F0, rax
0x1400075ee  lea     rax, qword_1400204E0
0x1400075f5  mov     [rbx+8], rax
0x1400075f9  mov     rcx, rbx
0x1400075fc  call    ??$RegisterObjects@$01@Details@WRL@Microsoft@@YAJPEAVModuleBase@012@PEBG@Z; Microsoft::WRL::Details::RegisterObjects<2>(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x140007601  test    eax, eax
0x140007603  js      short loc_140007634
0x140007605  mov     [rbp+57h+var_B8], 0
0x14000760c  lea     rax, [rbp+57h+var_B8]
0x140007610  mov     [rsp+0F0h+ppv], rax
0x140007615  lea     r9, [rbp+57h+var_A8]
0x140007619  mov     r8d, 1
0x14000761f  or      edx, 0FFFFFFFFh
0x140007622  lea     ecx, [r8+2]
0x140007626  call    cs:__imp_CoWaitForMultipleObjects
0x14000762c  mov     rcx, rbx; this
0x14000762f  call    ?UnregisterObjects@Details@WRL@Microsoft@@YAJPEAVModuleBase@123@PEBG@Z; Microsoft::WRL::Details::UnregisterObjects(Microsoft::WRL::Details::ModuleBase *,ushort const *)
0x140007634  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x14000763b  mov     [rbp+57h+var_B0], rax
0x14000763f  cmp     [rbp+57h+var_A8], 0
0x140007644  jz      short loc_14000765B
0x140007646  lea     rcx, [rbp+57h+var_B0]
0x14000764a  call    ?InternalClose@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::InternalClose(void)
0x14000764f  test    al, al
0x140007651  jz      short loc_140007685
0x140007653  mov     [rbp+57h+var_A8], 0
0x14000765b  lea     rcx, [rbp+57h+var_C0]
0x14000765f  call    ??1?$com_ptr_t@UIUnknown@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUnknown,wil::err_exception_policy>::~com_ptr_t<IUnknown,wil::err_exception_policy>(void)
0x140007664  test    edi, edi
0x140007666  js      short loc_14000766E
0x140007668  call    cs:__imp_RoUninitialize
0x14000766e  xor     eax, eax
0x140007670  lea     r11, [rsp+0F0h+var_s0]
0x140007678  mov     rbx, [r11+10h]
0x14000767c  mov     rdi, [r11+18h]
0x140007680  mov     rsp, r11
0x140007683  pop     rbp
0x140007684  retn
0x140007685  call    cs:__imp_GetLastError
0x14000768b  test    eax, eax
0x14000768d  jle     short loc_140007697
0x14000768f  movzx   eax, ax
0x140007692  or      eax, 80070000h
0x140007697  mov     ecx, eax; this
0x140007699  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x14000769e  int     3; Trap to Debugger
0x14000769f  xor     edx, edx; Val
0x1400076a1  mov     r8d, 98h; Size
0x1400076a7  lea     rcx, [rbp+57h+var_A0]; void *
0x1400076ab  call    memset_0
0x1400076b0  lea     rcx, [rbp+57h+var_A0]; this
0x1400076b4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
