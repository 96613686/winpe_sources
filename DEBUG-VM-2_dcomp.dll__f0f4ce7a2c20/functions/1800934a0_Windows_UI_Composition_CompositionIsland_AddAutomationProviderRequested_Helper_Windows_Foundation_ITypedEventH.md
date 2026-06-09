# Windows::UI::Composition::CompositionIsland::AddAutomationProviderRequested_Helper(Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::CompositionIsland *,Windows::UI::Composition::CompositionIslandAutomationProviderRequestedEventArgs *> *,EventRegistrationToken *)

- ea: `0x1800934a0`
- end: `0x1800936a4`
- name: `?AddAutomationProviderRequested_Helper@CompositionIsland@Composition@UI@Windows@@AEAAXPEAU?$ITypedEventHandler@PEAVCompositionIsland@Composition@UI@Windows@@PEAVCompositionIslandAutomationProviderRequestedEventArgs@234@@Foundation@4@PEAUEventRegistrationToken@@@Z`
- size: `516`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180093424`

## callees

- `0x1800093f4`
- `0x180029c5c`
- `0x18002b06c`
- `0x18002be50`
- `0x180093148`
- `0x1800934a0`
- `0x1800936ac`
- `0x1800f6f10`
- `0x180182010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180093635`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18009357a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18009357a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180093583`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180093583`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18009355a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18009355a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009356f`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18009356f`

## string_xrefs

- `0x180093645`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositionisland.cpp`
- `0x180093662`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositionisland.cpp`
- `0x18009368b`: `onecoreuap\windows\dwm\dcomp\winrtnested\global\wrtcompositionisland.cpp`

## pseudocode

```c
void __fastcall Windows::UI::Composition::CompositionIsland::AddAutomationProviderRequested_Helper(
        __int64 *a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v6; // rax
  int v7; // eax
  __int64 v8; // rcx
  struct _TP_WORK *v9; // rax
  struct _TP_WORK *v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rcx
  __int64 v13; // rcx
  int v14; // eax
  signed int LastError; // eax
  bool v16; // sf
  unsigned __int64 v17; // [rsp+20h] [rbp-50h]
  __int128 pv; // [rsp+30h] [rbp-40h] BYREF
  __int64 v19; // [rsp+40h] [rbp-30h] BYREF
  __int128 v20; // [rsp+48h] [rbp-28h] BYREF
  __int64 v21; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( !a1[54] )
  {
    v19 = 0;
    v21 = 0;
    v6 = *a1;
    pv = 0;
    v20 = 0;
    v7 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v6 + 280))(a1, &v19);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x665,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositionisland.cpp",
        (const char *)(unsigned int)v7,
        v17);
    v17 = a1[24];
    pv = v17;
    Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(&v20, a1);
    v8 = *((_QWORD *)&v20 + 1);
    if ( *((_QWORD *)&v20 + 1) )
    {
      *((_QWORD *)&v20 + 1) = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    v9 = CreateThreadpoolWork(Windows::UI::Composition::CompositionIsland::RegisterUIAEndpoint_Callback, &pv, 0);
    v10 = v9;
    if ( v9 )
    {
      SubmitThreadpoolWork(v9);
      WaitForThreadpoolWorkCallbacks(v10, 0);
      CloseThreadpoolWork(v10);
      v11 = *((_QWORD *)&v20 + 1);
      if ( a1[54] != *((_QWORD *)&v20 + 1) )
      {
        if ( *((_QWORD *)&v20 + 1) )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v20 + 1) + 8LL))(*((_QWORD *)&v20 + 1));
        v12 = a1[54];
        a1[54] = v11;
        if ( v12 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
      }
      Microsoft::WRL::ComPtr<Windows::UI::Composition::UiaEndpointNotifierCallback>::operator=(a1 + 55, &v21);
    }
    else
    {
      LastError = GetLastError();
      v16 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v16 = LastError < 0;
      }
      if ( v16 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x687,
          (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositionisland.cpp",
          (const char *)(unsigned int)LastError,
          v17);
    }
    Microsoft::WRL::ComPtr<Windows::UI::Composition::UiaEndpointNotifierCallback>::InternalRelease(&v21);
    Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease((char *)&v20 + 8);
    v13 = v20;
    if ( (_QWORD)v20 )
    {
      *(_QWORD *)&v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
  }
  v14 = Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::CompositionIsland *,Windows::UI::Composition::CompositionIslandAutomationProviderRequestedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(
          a1 + 51,
          a2,
          a3);
  if ( v14 < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x68B,
      (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\global\\wrtcompositionisland.cpp",
      (const char *)(unsigned int)v14,
      v17);
}

```

## disassembly

```asm
0x1800934a0  push    rbp
0x1800934a2  push    rbx
0x1800934a3  push    rsi
0x1800934a4  push    rdi
0x1800934a5  push    r14
0x1800934a7  mov     rbp, rsp
0x1800934aa  sub     rsp, 70h
0x1800934ae  mov     rax, cs:__security_cookie
0x1800934b5  xor     rax, rsp
0x1800934b8  mov     [rbp+var_10], rax
0x1800934bc  cmp     qword ptr [rcx+1B0h], 0
0x1800934c4  mov     r14, r8
0x1800934c7  mov     rsi, rdx
0x1800934ca  mov     rdi, rcx
0x1800934cd  jnz     loc_180093608
0x1800934d3  xor     eax, eax
0x1800934d5  lea     rdx, [rbp+var_30]
0x1800934d9  mov     [rbp+var_30], rax
0x1800934dd  xorps   xmm0, xmm0
0x1800934e0  mov     [rbp+var_18], rax
0x1800934e4  xorps   xmm1, xmm1
0x1800934e7  mov     rax, [rcx]
0x1800934ea  movups  [rbp+pv], xmm0
0x1800934ee  movdqu  [rbp+var_28], xmm1
0x1800934f3  mov     rax, [rax+118h]
0x1800934fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800934ff  test    eax, eax
0x180093501  js      loc_18009365E
0x180093507  mov     rax, [rdi+0C0h]
0x18009350e  lea     rcx, [rbp+var_28]
0x180093512  mov     qword ptr [rbp+var_50], rax
0x180093516  mov     rdx, rdi
0x180093519  mov     qword ptr [rbp+var_50+8], 0
0x180093521  movups  xmm0, [rbp+var_50]
0x180093525  movdqu  [rbp+pv], xmm0
0x18009352a  call    ??4?$ComPtr@UIDispatcherQueue@System@Windows@@@WRL@Microsoft@@QEAAAEAV012@PEAUIDispatcherQueue@System@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::System::IDispatcherQueue>::operator=(Windows::System::IDispatcherQueue *)
0x18009352f  mov     rcx, qword ptr [rbp+var_28+8]
0x180093533  test    rcx, rcx
0x180093536  jz      short loc_18009354C
0x180093538  mov     qword ptr [rbp+var_28+8], 0
0x180093540  mov     rax, [rcx]
0x180093543  mov     rax, [rax+10h]
0x180093547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009354c  xor     r8d, r8d; pcbe
0x18009354f  lea     rdx, [rbp+pv]; pv
0x180093553  lea     rcx, ?RegisterUIAEndpoint_Callback@CompositionIsland@Composition@UI@Windows@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18009355a  call    cs:__imp_CreateThreadpoolWork
0x180093560  mov     rbx, rax
0x180093563  test    rax, rax
0x180093566  jz      loc_180093635
0x18009356c  mov     rcx, rax; pwk
0x18009356f  call    cs:__imp_SubmitThreadpoolWork
0x180093575  xor     edx, edx; fCancelPendingCallbacks
0x180093577  mov     rcx, rbx; pwk
0x18009357a  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x180093580  mov     rcx, rbx; pwk
0x180093583  call    cs:__imp_CloseThreadpoolWork
0x180093589  mov     rbx, qword ptr [rbp+var_28+8]
0x18009358d  cmp     [rdi+1B0h], rbx
0x180093594  jz      short loc_1800935C9
0x180093596  test    rbx, rbx
0x180093599  jz      short loc_1800935AA
0x18009359b  mov     rax, [rbx]
0x18009359e  mov     rcx, rbx
0x1800935a1  mov     rax, [rax+8]
0x1800935a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800935aa  mov     rcx, [rdi+1B0h]
0x1800935b1  mov     [rdi+1B0h], rbx
0x1800935b8  test    rcx, rcx
0x1800935bb  jz      short loc_1800935C9
0x1800935bd  mov     rax, [rcx]
0x1800935c0  mov     rax, [rax+10h]
0x1800935c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800935c9  lea     rcx, [rdi+1B8h]
0x1800935d0  lea     rdx, [rbp+var_18]
0x1800935d4  call    ??4?$ComPtr@VUiaEndpointNotifierCallback@Composition@UI@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::UI::Composition::UiaEndpointNotifierCallback>::operator=(Microsoft::WRL::ComPtr<Windows::UI::Composition::UiaEndpointNotifierCallback> const &)
0x1800935d9  lea     rcx, [rbp+var_18]
0x1800935dd  call    ?InternalRelease@?$ComPtr@VUiaEndpointNotifierCallback@Composition@UI@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::UI::Composition::UiaEndpointNotifierCallback>::InternalRelease(void)
0x1800935e2  lea     rcx, [rbp+var_28+8]
0x1800935e6  call    ?InternalRelease@?$ComPtr@UIDCompositionSurface@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IDCompositionSurface>::InternalRelease(void)
0x1800935eb  mov     rcx, qword ptr [rbp+var_28]
0x1800935ef  test    rcx, rcx
0x1800935f2  jz      short loc_180093608
0x1800935f4  mov     qword ptr [rbp+var_28], 0
0x1800935fc  mov     rax, [rcx]
0x1800935ff  mov     rax, [rax+10h]
0x180093603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180093608  lea     rcx, [rdi+198h]
0x18009360f  mov     r8, r14
0x180093612  mov     rdx, rsi
0x180093615  call    ?Add@?$AgileEventSource@U?$ITypedEventHandler@PEAVCompositionIsland@Composition@UI@Windows@@PEAVCompositionIslandAutomationProviderRequestedEventArgs@234@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAAJPEAU?$ITypedEventHandler@PEAVCompositionIsland@Composition@UI@Windows@@PEAVCompositionIslandAutomationProviderRequestedEventArgs@234@@Foundation@Windows@@PEAUEventRegistrationToken@@@Z; Microsoft::WRL::AgileEventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::CompositionIsland *,Windows::UI::Composition::CompositionIslandAutomationProviderRequestedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::Add(Windows::Foundation::ITypedEventHandler<Windows::UI::Composition::CompositionIsland *,Windows::UI::Composition::CompositionIslandAutomationProviderRequestedEventArgs *> *,EventRegistrationToken *)
0x18009361a  test    eax, eax
0x18009361c  js      short loc_180093687
0x18009361e  mov     rcx, [rbp+var_10]
0x180093622  xor     rcx, rsp; StackCookie
0x180093625  call    __security_check_cookie
0x18009362a  add     rsp, 70h
0x18009362e  pop     r14
0x180093630  pop     rdi
0x180093631  pop     rsi
0x180093632  pop     rbx
0x180093633  pop     rbp
0x180093634  retn
0x180093635  call    cs:__imp_GetLastError
0x18009363b  test    eax, eax
0x18009363d  jg      short loc_18009367B
0x18009363f  jns     short loc_1800935D9
0x180093641  mov     rcx, [rbp+28h]; this
0x180093645  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x18009364c  mov     r9d, eax; char *
0x18009364f  mov     edx, 687h; void *
0x180093654  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093659  jmp     loc_1800935D9
0x18009365e  mov     rcx, [rbp+28h]; this
0x180093662  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180093669  mov     r9d, eax; char *
0x18009366c  mov     edx, 665h; void *
0x180093671  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180093676  jmp     loc_180093507
0x18009367b  movzx   eax, ax
0x18009367e  or      eax, 80070000h
0x180093683  test    eax, eax
0x180093685  jmp     short loc_18009363F
0x180093687  mov     rcx, [rbp+28h]; this
0x18009368b  lea     r8, aOnecoreuapWind_62; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x180093692  mov     r9d, eax; char *
0x180093695  mov     edx, 68Bh; void *
0x18009369a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009369f  jmp     loc_18009361E
```
