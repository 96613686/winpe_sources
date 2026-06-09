# DllMain

- ea: `0x180011ffc`
- end: `0x180012227`
- name: `DllMain`
- size: `555`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002134`

## callees

- `0x18000e07c`
- `0x180011ffc`
- `0x180012338`
- `0x18001235c`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012033`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x180012033`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180012132`
- `api-ms-win-eventing-provider-l1-1-0!EventRegister` at `0x180012132`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180012151`
- `api-ms-win-eventing-provider-l1-1-0!EventSetInformation` at `0x180012151`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800121a3`
- `api-ms-win-eventing-provider-l1-1-0!EventUnregister` at `0x1800121a3`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800121c7`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x1800121c7`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800120c0`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x1800120c0`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v3; // rbx
  const GUID **v4; // rdi
  const GUID *v5; // r8
  __int64 v6; // rdx
  REGHANDLE v7; // rcx
  _QWORD *v8; // rbx
  TRACEHANDLE v9; // rcx
  const struct wil::FailureInfo *v11; // rdx
  _BYTE v12[160]; // [rsp+40h] [rbp-C8h] BYREF
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+E0h] [rbp-28h] BYREF

  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      DisableThreadLibraryCalls(hinstDLL);
      qword_180090AB8 = 0;
      v3 = (ULONG64 *)&WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_MODERNAPPCSP_WPP_GUID;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_180090AC0 = 1;
      do
      {
        v5 = *v4;
        TraceGuidReg.Guid = v5;
        ++v4;
        TraceGuidReg.RegHandle = 0;
        v3[4] = (ULONG64)v5;
        RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, &TraceGuidReg, 0, 0, v3 + 1);
        v3 = (ULONG64 *)*v3;
      }
      while ( v3 );
      McGenEventRegister_EventRegister(
        MICROSOFT_WINDOWSPHONE_APPPLATPROVIDER,
        v6,
        MICROSOFT_WINDOWSPHONE_APPPLATPROVIDER_Context,
        &Microsoft_WindowsPhone_AppPlatProviderHandle);
      TraceGuidReg = (struct _TRACE_GUID_REGISTRATION)*((_OWORD *)off_18008F0A8 - 1);
      if ( RegHandle )
        __fastfail(5u);
      xmmword_18008F0C8 = 0;
      if ( !EventRegister((LPCGUID)&TraceGuidReg, tlgEnableCallback, &dword_18008F0A0, &RegHandle) )
        EventSetInformation(RegHandle, 2, off_18008F0A8, *(unsigned __int16 *)off_18008F0A8);
      if ( wil::details::g_pfnLoggingCallback
        && (char *)wil::details::g_pfnLoggingCallback != (char *)lambda_6bdc1fc3071ae4586e0dac10b50b9421_::_lambda_invoker_cdecl_ )
      {
        memset_0(v12, 0, 0x98u);
        wil::details::WilFailFast((wil::details *)v12, v11);
      }
      wil::details::g_pfnLoggingCallback = (__int64 (__fastcall *)(_QWORD))lambda_6bdc1fc3071ae4586e0dac10b50b9421_::_lambda_invoker_cdecl_;
    }
  }
  else
  {
    wil::details::g_pfnLoggingCallback = 0;
    McGenEventUnregister_EventUnregister(&Microsoft_WindowsPhone_AppPlatProviderHandle);
    v7 = RegHandle;
    dword_18008F0A0 = 0;
    RegHandle = 0;
    EventUnregister(v7);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v8 )
      {
        v9 = v8[1];
        if ( v9 )
        {
          UnregisterTraceGuids(v9);
          v8[1] = 0;
        }
        v8 = (_QWORD *)*v8;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x180011ffc  mov     [rsp+arg_8], rbx
0x180012001  mov     [rsp+arg_10], rsi
0x180012006  push    rdi
0x180012007  sub     rsp, 100h
0x18001200e  mov     rax, cs:__security_cookie
0x180012015  xor     rax, rsp
0x180012018  mov     [rsp+108h+var_18], rax
0x180012020  xor     esi, esi
0x180012022  test    edx, edx
0x180012024  jz      loc_18001217C
0x18001202a  cmp     edx, 1
0x18001202d  jnz     loc_1800121E0
0x180012033  call    cs:__imp_DisableThreadLibraryCalls
0x180012039  lea     rax, WPP_ThisDir_CTLGUID_MODERNAPPCSP_WPP_GUID
0x180012040  mov     cs:qword_180090AB8, rsi
0x180012047  lea     rbx, WPP_MAIN_CB
0x18001204e  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180012055  mov     cs:WPP_GLOBAL_Control, rbx
0x18001205c  lea     rdi, WPP_REGISTRATION_GUIDS
0x180012063  mov     cs:WPP_MAIN_CB, rsi
0x18001206a  mov     cs:qword_180090AC0, 1
0x180012075  mov     r8, [rdi]; ControlGuid
0x180012078  lea     rax, [rbx+8]
0x18001207c  mov     [rsp+108h+RegistrationHandle], rax; RegistrationHandle
0x180012081  lea     rcx, WppControlCallback; RequestAddress
0x180012088  mov     [rsp+108h+MofResourceName], rsi; MofResourceName
0x18001208d  lea     rax, [rsp+108h+var_28]
0x180012095  mov     [rsp+108h+var_28.Guid], r8
0x18001209d  lea     rdi, [rdi+8]
0x1800120a1  mov     [rsp+108h+var_28.RegHandle], rsi
0x1800120a9  mov     r9d, 1; GuidCount
0x1800120af  mov     [rsp+108h+MofImagePath], rsi; MofImagePath
0x1800120b4  mov     rdx, rbx; RequestContext
0x1800120b7  mov     [rsp+108h+TraceGuidReg], rax; TraceGuidReg
0x1800120bc  mov     [rbx+20h], r8
0x1800120c0  call    cs:__imp_RegisterTraceGuidsW
0x1800120c6  mov     rbx, [rbx]
0x1800120c9  test    rbx, rbx
0x1800120cc  jnz     short loc_180012075
0x1800120ce  lea     r9, Microsoft_WindowsPhone_AppPlatProviderHandle
0x1800120d5  lea     r8, MICROSOFT_WINDOWSPHONE_APPPLATPROVIDER_Context
0x1800120dc  lea     rcx, MICROSOFT_WINDOWSPHONE_APPPLATPROVIDER
0x1800120e3  call    McGenEventRegister_EventRegister
0x1800120e8  cmp     cs:RegHandle, rsi
0x1800120ef  mov     rax, cs:off_18008F0A8
0x1800120f6  movups  xmm0, xmmword ptr [rax-10h]
0x1800120fa  movdqu  xmmword ptr [rsp+108h+var_28.Guid], xmm0
0x180012103  jz      short loc_18001210A
0x180012105  lea     ecx, [rbx+5]
0x180012108  int     29h; Win8: RtlFailFast(ecx)
0x18001210a  xorps   xmm0, xmm0
0x18001210d  lea     r9, RegHandle; RegHandle
0x180012114  lea     r8, dword_18008F0A0; CallbackContext
0x18001211b  lea     rdx, _tlgEnableCallback; EnableCallback
0x180012122  lea     rcx, [rsp+108h+var_28]; ProviderId
0x18001212a  movdqu  cs:xmmword_18008F0C8, xmm0
0x180012132  call    cs:__imp_EventRegister
0x180012138  test    eax, eax
0x18001213a  jnz     short loc_180012157
0x18001213c  mov     r8, cs:off_18008F0A8
0x180012143  lea     edx, [rax+2]
0x180012146  mov     rcx, cs:RegHandle
0x18001214d  movzx   r9d, word ptr [r8]
0x180012151  call    cs:__imp_EventSetInformation
0x180012157  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001215e  lea     rcx, _lambda_6bdc1fc3071ae4586e0dac10b50b9421____lambda_invoker_cdecl_
0x180012165  test    rax, rax
0x180012168  jz      short loc_180012173
0x18001216a  cmp     rax, rcx
0x18001216d  jnz     loc_18001220A
0x180012173  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18001217a  jmp     short loc_1800121E0
0x18001217c  lea     rcx, Microsoft_WindowsPhone_AppPlatProviderHandle
0x180012183  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rsi
0x18001218a  call    McGenEventUnregister_EventUnregister
0x18001218f  mov     rcx, cs:RegHandle; RegHandle
0x180012196  mov     cs:dword_18008F0A0, esi
0x18001219c  mov     cs:RegHandle, rsi
0x1800121a3  call    cs:__imp_EventUnregister
0x1800121a9  mov     rbx, cs:WPP_GLOBAL_Control
0x1800121b0  lea     rdi, WPP_GLOBAL_Control
0x1800121b7  cmp     rbx, rdi
0x1800121ba  jz      short loc_1800121E0
0x1800121bc  jmp     short loc_1800121D4
0x1800121be  mov     rcx, [rbx+8]; RegistrationHandle
0x1800121c2  test    rcx, rcx
0x1800121c5  jz      short loc_1800121D1
0x1800121c7  call    cs:__imp_UnregisterTraceGuids
0x1800121cd  mov     [rbx+8], rsi
0x1800121d1  mov     rbx, [rbx]
0x1800121d4  test    rbx, rbx
0x1800121d7  jnz     short loc_1800121BE
0x1800121d9  mov     cs:WPP_GLOBAL_Control, rdi
0x1800121e0  mov     eax, 1
0x1800121e5  mov     rcx, [rsp+108h+var_18]
0x1800121ed  xor     rcx, rsp; StackCookie
0x1800121f0  call    __security_check_cookie
0x1800121f5  lea     r11, [rsp+108h+var_8]
0x1800121fd  mov     rbx, [r11+18h]
0x180012201  mov     rsi, [r11+20h]
0x180012205  mov     rsp, r11
0x180012208  pop     rdi
0x180012209  retn
0x18001220a  xor     edx, edx; Val
0x18001220c  lea     rcx, [rsp+108h+var_C8]; void *
0x180012211  mov     r8d, 98h; Size
0x180012217  call    memset_0
0x18001221c  lea     rcx, [rsp+108h+var_C8]; this
0x180012221  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
