# ComponentUIHostedActivationManager::EnsureApplicationActivated(void)

- ea: `0x1801107dc`
- end: `0x180110b47`
- name: `?EnsureApplicationActivated@ComponentUIHostedActivationManager@@AEAAJXZ`
- size: `875`
- prototype: `__int64 __fastcall(ComponentUIHostedActivationManager *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1802a84c0`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x1800378dc`
- `0x180082830`
- `0x1800a0f20`
- `0x1800ed2c0`
- `0x1800f1a00`
- `0x1801107dc`
- `0x180110b50`
- `0x180110b94`
- `0x180142e10`
- `0x1802a88f8`
- `0x1802a8d1c`
- `0x1802a9f70`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180110849`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180110849`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180110940`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180110940`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180110a3a`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x180110a3a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180110921`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180110921`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180110aa6`
- `api-ms-win-core-com-l1-1-0!CoWaitForMultipleHandles` at `0x180110aa6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180110967`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180110967`

## string_xrefs

- `0x180110826`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`
- `0x18011086c`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`
- `0x1801108a8`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`
- `0x1801108e9`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`
- `0x180110985`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`
- `0x180110a4e`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`
- `0x180110ac4`: `shell\twinui\picker\apptoapp\componentuihostedactivationmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall ComponentUIHostedActivationManager::EnsureApplicationActivated(
        ComponentUIHostedActivationManager *this)
{
  HANDLE *v2; // r15
  unsigned int LastError; // ebx
  HANDLE Event; // rbx
  const char *v5; // r9
  int v7; // eax
  int v8; // eax
  HSTRING v9; // rbx
  int ActivationFactory; // eax
  __int64 v11; // rdx
  __int64 (__fastcall ***v12)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v13)(_QWORD, GUID *, char *); // rdi
  HSTRING v14; // rdi
  ULONG (__stdcall *v15)(PVOID); // rax
  const char *v16; // r9
  HRESULT v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  int lpdwindex; // [rsp+20h] [rbp-49h]
  int lpdwindexa; // [rsp+20h] [rbp-49h]
  __int64 (__fastcall ***v22)(_QWORD, GUID *, char *); // [rsp+30h] [rbp-39h] BYREF
  __int64 v23; // [rsp+38h] [rbp-31h] BYREF
  DWORD dwindex; // [rsp+40h] [rbp-29h] BYREF
  struct IInspectable *v25; // [rsp+48h] [rbp-21h] BYREF
  __int64 *Context; // [rsp+50h] [rbp-19h] BYREF
  ComponentUIHostedActivationManager *v27; // [rsp+58h] [rbp-11h]
  __int64 **p_Context; // [rsp+60h] [rbp-9h] BYREF
  char v29; // [rsp+68h] [rbp-1h]
  HSTRING string; // [rsp+70h] [rbp+7h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v2 = (HANDLE *)((char *)this + 304);
  if ( !*((_QWORD *)this + 38) )
  {
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    CAutoHandle<void *>::~CAutoHandle<void *>(v2);
    *v2 = Event;
    if ( !Event )
      return wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x18D,
               (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
               v5);
    v25 = 0;
    Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v25);
    v7 = ComponentUIHostedActivationManager::CreateWindowFactory(this, &v25);
    LastError = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x191,
        (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
        (const char *)(unsigned int)v7,
        lpdwindex);
LABEL_32:
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&v25);
      return LastError;
    }
    v23 = 0;
    v8 = CMarshaledInterface::Marshal(&v23, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, v25, 2);
    LastError = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x194,
        (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
        (const char *)(unsigned int)v8,
        lpdwindex);
LABEL_9:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
      goto LABEL_32;
    }
    v22 = 0;
    if ( WindowsCreateStringReference(L"Windows.ApplicationModel.Core.CoreApplication", 0x2Du, &hstringHeader, &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v9 = string;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    ActivationFactory = RoGetActivationFactory(v9, &GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1, &v22);
    LastError = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v12 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v22;
      v13 = **v22;
      Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease((char *)this + 256);
      ActivationFactory = v13(v12, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, (char *)this + 256);
      LastError = ActivationFactory;
      if ( ActivationFactory >= 0 )
      {
        ActivationFactory = ComponentUIHostedActivationManager::CreateAndAddComponentSite(this);
        LastError = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          Context = 0;
          v27 = this;
          Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,CWRLObjectWithSite,IComponentUIHostedActivationManager,ICoreWindowFactoryPriv,ISplashScreen,IServiceProvider,IComponentUIHostedActivationManagerTest,IObjectWithWindow>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,ISplashScreenUI,IComponentUIEventHandler>>::InternalAddRef(this);
          Context = &v23;
          v14 = *(HSTRING *)_lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(
                              (_lambda_aec159daf75c9a566e43618f77172940_ *)&p_Context,
                              this);
          string = v14;
          hstringHeader.Reserved.Reserved2[0] = 1;
          p_Context = &Context;
          v29 = 1;
          v15 = (ULONG (__stdcall *)(PVOID))lambda_7adc88e33a33f11f43cdec229628c8d8_::operator_unsigned_long____cdecl___void___();
          if ( QueueUserWorkItem(v15, &Context, 0) )
          {
            v29 = 0;
            dwindex = 0;
            v17 = CoWaitForMultipleHandles(0x18u, 0xFFFFFFFF, 1u, v2, &dwindex);
            LastError = v17;
            if ( v17 >= 0 )
            {
              if ( dwindex )
              {
                LastError = -2147418113;
                v18 = 2147549183LL;
                v19 = 495;
              }
              else
              {
                LastError = *((_DWORD *)this + 58);
                if ( (LastError & 0x80000000) == 0 )
                {
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
                  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v23);
                  LastError = 0;
                  goto LABEL_32;
                }
                v18 = LastError;
                v19 = 497;
              }
            }
            else
            {
              v18 = (unsigned int)v17;
              v19 = 492;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v19,
              (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
              (const char *)v18,
              lpdwindexa);
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x1E8,
                          (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
                          v16);
            Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,CWRLObjectWithSite,IComponentUIHostedActivationManager,ICoreWindowFactoryPriv,ISplashScreen,IServiceProvider,IComponentUIHostedActivationManagerTest,IObjectWithWindow>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,ISplashScreenUI,IComponentUIEventHandler>>::Release(v27);
          }
          if ( *((_QWORD *)v14 + 38) )
            CAutoHandle<void *>::~CAutoHandle<void *>(v14 + 76);
          goto LABEL_15;
        }
        v11 = 410;
      }
      else
      {
        v11 = 408;
      }
    }
    else
    {
      v11 = 407;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
      (const char *)(unsigned int)ActivationFactory,
      lpdwindex);
LABEL_15:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v22);
    goto LABEL_9;
  }
  LastError = -2147467260;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x188,
    (unsigned int)"shell\\twinui\\picker\\apptoapp\\componentuihostedactivationmanager.cpp",
    (const char *)0x80004004LL,
    lpdwindex);
  return LastError;
}

```

## disassembly

```asm
0x1801107dc  mov     [rsp-8+arg_8], rbx
0x1801107e1  mov     [rsp-8+arg_10], rsi
0x1801107e6  push    rbp
0x1801107e7  push    rdi
0x1801107e8  push    r12
0x1801107ea  push    r14
0x1801107ec  push    r15
0x1801107ee  lea     rbp, [rsp-37h]
0x1801107f3  sub     rsp, 0A0h
0x1801107fa  mov     rax, cs:__security_cookie
0x180110801  xor     rax, rsp
0x180110804  mov     [rbp+57h+var_30], rax
0x180110808  mov     r14, rcx
0x18011080b  lea     r15, [rcx+130h]
0x180110812  xor     r12d, r12d
0x180110815  cmp     [r15], r12
0x180110818  jz      short loc_18011083C
0x18011081a  mov     rcx, [rbp+5Fh]; this
0x18011081e  mov     ebx, 80004004h
0x180110823  mov     r9d, ebx; char *
0x180110826  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x18011082d  mov     edx, 188h; void *
0x180110832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110837  jmp     loc_180110B1C
0x18011083c  mov     r9d, 1F0003h; dwDesiredAccess
0x180110842  xor     r8d, r8d; dwFlags
0x180110845  xor     edx, edx; lpName
0x180110847  xor     ecx, ecx; lpEventAttributes
0x180110849  call    cs:__imp_CreateEventExW
0x180110850  nop     dword ptr [rax+rax+00h]
0x180110855  mov     rbx, rax
0x180110858  mov     rcx, r15
0x18011085b  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180110860  mov     [r15], rbx
0x180110863  test    rbx, rbx
0x180110866  jnz     short loc_180110882
0x180110868  mov     rcx, [rbp+5Fh]; this
0x18011086c  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x180110873  mov     edx, 18Dh; void *
0x180110878  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011087d  jmp     loc_180110B1E
0x180110882  mov     [rbp+57h+var_78], r12
0x180110886  lea     rcx, [rbp+57h+var_78]
0x18011088a  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x18011088f  lea     rdx, [rbp+57h+var_78]; struct IInspectable **
0x180110893  mov     rcx, r14; this
0x180110896  call    ?CreateWindowFactory@ComponentUIHostedActivationManager@@AEAAJPEAPEAUIInspectable@@@Z; ComponentUIHostedActivationManager::CreateWindowFactory(IInspectable * *)
0x18011089b  mov     ebx, eax
0x18011089d  test    eax, eax
0x18011089f  jns     short loc_1801108BE
0x1801108a1  mov     rcx, [rbp+5Fh]; this
0x1801108a5  mov     r9d, eax; char *
0x1801108a8  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x1801108af  mov     edx, 191h; void *
0x1801108b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801108b9  jmp     loc_180110B13
0x1801108be  mov     [rbp+57h+var_88], r12
0x1801108c2  mov     r9d, 2
0x1801108c8  mov     r8, [rbp+57h+var_78]
0x1801108cc  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1801108d3  lea     rcx, [rbp+57h+var_88]
0x1801108d7  call    ?Marshal@CMarshaledInterface@@QEAAJAEBU_GUID@@PEAUIUnknown@@W4MARSHAL_KIND@@@Z; CMarshaledInterface::Marshal(_GUID const &,IUnknown *,MARSHAL_KIND)
0x1801108dc  mov     ebx, eax
0x1801108de  test    eax, eax
0x1801108e0  jns     short loc_180110909
0x1801108e2  mov     rcx, [rbp+5Fh]; this
0x1801108e6  mov     r9d, eax; char *
0x1801108e9  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x1801108f0  mov     edx, 194h; void *
0x1801108f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801108fa  nop
0x1801108fb  lea     rcx, [rbp+57h+var_88]
0x1801108ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180110904  jmp     loc_180110B13
0x180110909  mov     [rbp+57h+var_90], r12
0x18011090d  lea     r9, [rbp+57h+string]; string
0x180110911  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180110915  mov     edx, 2Dh ; '-'; length
0x18011091a  lea     rcx, ?RuntimeClass_Windows_ApplicationModel_Core_CoreApplication@@3QBGB; "Windows.ApplicationModel.Core.CoreAppli"...
0x180110921  call    cs:__imp_WindowsCreateStringReference
0x180110928  nop     dword ptr [rax+rax+00h]
0x18011092d  test    eax, eax
0x18011092f  jns     short loc_18011094C
0x180110931  xor     r9d, r9d; lpArguments
0x180110934  xor     r8d, r8d; nNumberOfArguments
0x180110937  lea     edx, [r9+1]; dwExceptionFlags
0x18011093b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180110940  call    cs:__imp_RaiseException
0x180110947  nop     dword ptr [rax+rax+00h]
0x18011094c  mov     rbx, [rbp+57h+string]
0x180110950  lea     rcx, [rbp+57h+var_90]
0x180110954  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180110959  lea     r8, [rbp+57h+var_90]
0x18011095d  lea     rdx, _GUID_0aacf7a4_5e1d_49df_8034_fb6a68bc5ed1
0x180110964  mov     rcx, rbx
0x180110967  call    cs:__imp_RoGetActivationFactory
0x18011096e  nop     dword ptr [rax+rax+00h]
0x180110973  mov     ebx, eax
0x180110975  test    eax, eax
0x180110977  jns     short loc_1801109A0
0x180110979  mov     edx, 197h; void *
0x18011097e  mov     rcx, [rbp+5Fh]; this
0x180110982  mov     r9d, eax; char *
0x180110985  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x18011098c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110991  nop
0x180110992  lea     rcx, [rbp+57h+var_90]
0x180110996  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18011099b  jmp     loc_1801108FB
0x1801109a0  lea     rsi, [r14+100h]
0x1801109a7  mov     rbx, [rbp+57h+var_90]
0x1801109ab  mov     rax, [rbx]
0x1801109ae  mov     rdi, [rax]
0x1801109b1  mov     rcx, rsi
0x1801109b4  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x1801109b9  mov     r8, rsi
0x1801109bc  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x1801109c3  mov     rcx, rbx
0x1801109c6  mov     rax, rdi
0x1801109c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801109ce  mov     ebx, eax
0x1801109d0  test    eax, eax
0x1801109d2  jns     short loc_1801109DB
0x1801109d4  mov     edx, 198h
0x1801109d9  jmp     short loc_18011097E
0x1801109db  mov     rcx, r14; this
0x1801109de  call    ?CreateAndAddComponentSite@ComponentUIHostedActivationManager@@AEAAJXZ; ComponentUIHostedActivationManager::CreateAndAddComponentSite(void)
0x1801109e3  mov     ebx, eax
0x1801109e5  test    eax, eax
0x1801109e7  jns     short loc_1801109F0
0x1801109e9  mov     edx, 19Ah
0x1801109ee  jmp     short loc_18011097E
0x1801109f0  mov     [rbp+57h+Context], r12
0x1801109f4  mov     [rbp+57h+var_68], r14
0x1801109f8  mov     rcx, r14
0x1801109fb  call    ?InternalAddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@VCWRLObjectWithSite@@UIComponentUIHostedActivationManager@@UICoreWindowFactoryPriv@@UISplashScreen@@UIServiceProvider@@UIComponentUIHostedActivationManagerTest@@UIObjectWithWindow@@@23@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISplashScreenUI@@UIComponentUIEventHandler@@@23@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,CWRLObjectWithSite,IComponentUIHostedActivationManager,ICoreWindowFactoryPriv,ISplashScreen,IServiceProvider,IComponentUIHostedActivationManagerTest,IObjectWithWindow>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,ISplashScreenUI,IComponentUIEventHandler>>::InternalAddRef(void)
0x180110a00  lea     r9, [rbp+57h+var_88]
0x180110a04  mov     [rbp+57h+Context], r9
0x180110a08  mov     rdx, r14; struct CSearchSuggestionsProvider *
0x180110a0b  lea     rcx, [rbp+57h+var_60]; this
0x180110a0f  call    ??0_lambda_aec159daf75c9a566e43618f77172940_@@QEAA@PEAVCSearchSuggestionsProvider@@@Z; _lambda_aec159daf75c9a566e43618f77172940_::_lambda_aec159daf75c9a566e43618f77172940_(CSearchSuggestionsProvider *)
0x180110a14  mov     rdi, [rax]
0x180110a17  mov     [rbp+57h+string], rdi
0x180110a1b  mov     byte ptr [rbp+57h+hstringHeader.Reserved], 1
0x180110a1f  lea     rax, [rbp+57h+Context]
0x180110a23  mov     [rbp+57h+var_60], rax
0x180110a27  mov     [rbp+57h+var_58], 1
0x180110a2b  call    _lambda_7adc88e33a33f11f43cdec229628c8d8___operator_unsigned_long____cdecl___void___
0x180110a30  mov     rcx, rax; Function
0x180110a33  xor     r8d, r8d; Flags
0x180110a36  lea     rdx, [rbp+57h+Context]; Context
0x180110a3a  call    cs:__imp_QueueUserWorkItem
0x180110a41  nop     dword ptr [rax+rax+00h]
0x180110a46  test    eax, eax
0x180110a48  jnz     short loc_180110A85
0x180110a4a  mov     rcx, [rbp+5Fh]; this
0x180110a4e  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x180110a55  mov     edx, 1E8h; void *
0x180110a5a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180110a5f  mov     ebx, eax
0x180110a61  mov     rcx, [rbp+57h+var_68]
0x180110a65  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@VCWRLObjectWithSite@@UIComponentUIHostedActivationManager@@UICoreWindowFactoryPriv@@UISplashScreen@@UIServiceProvider@@UIComponentUIHostedActivationManagerTest@@UIObjectWithWindow@@@23@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISplashScreenUI@@UIComponentUIEventHandler@@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,CWRLObjectWithSite,IComponentUIHostedActivationManager,ICoreWindowFactoryPriv,ISplashScreen,IServiceProvider,IComponentUIHostedActivationManagerTest,IObjectWithWindow>,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,ISplashScreenUI,IComponentUIEventHandler>>::Release(void)
0x180110a6a  nop
0x180110a6b  lea     rcx, [rdi+130h]
0x180110a72  cmp     [rcx], r12
0x180110a75  jz      loc_180110992
0x180110a7b  call    ??1?$CAutoHandle@PEAX@@QEAA@XZ; CAutoHandle<void *>::~CAutoHandle<void *>(void)
0x180110a80  jmp     loc_180110992
0x180110a85  mov     [rbp+57h+var_58], r12b
0x180110a89  mov     [rbp+57h+dwindex], r12d
0x180110a8d  lea     rax, [rbp+57h+dwindex]
0x180110a91  mov     qword ptr [rsp+0C0h+lpdwindex], rax; int
0x180110a96  mov     r9, r15; pHandles
0x180110a99  mov     r8d, 1; cHandles
0x180110a9f  or      edx, 0FFFFFFFFh; dwTimeout
0x180110aa2  lea     ecx, [r8+17h]; dwFlags
0x180110aa6  call    cs:__imp_CoWaitForMultipleHandles
0x180110aad  nop     dword ptr [rax+rax+00h]
0x180110ab2  mov     ebx, eax
0x180110ab4  test    eax, eax
0x180110ab6  jns     short loc_180110AD3
0x180110ab8  mov     r9d, eax; char *
0x180110abb  mov     edx, 1ECh; void *
0x180110ac0  mov     rcx, [rbp+5Fh]; this
0x180110ac4  lea     r8, aShellTwinuiPic_11; "shell\\twinui\\picker\\apptoapp\\compon"...
0x180110acb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180110ad0  nop
0x180110ad1  jmp     short loc_180110A6B
0x180110ad3  cmp     [rbp+57h+dwindex], r12d
0x180110ad7  jz      short loc_180110AE8
0x180110ad9  mov     ebx, 8000FFFFh
0x180110ade  mov     r9d, ebx
0x180110ae1  mov     edx, 1EFh
0x180110ae6  jmp     short loc_180110AC0
0x180110ae8  mov     ebx, [r14+0E8h]
0x180110aef  test    ebx, ebx
0x180110af1  jns     short loc_180110AFD
0x180110af3  mov     r9d, ebx
0x180110af6  mov     edx, 1F1h
0x180110afb  jmp     short loc_180110AC0
0x180110afd  lea     rcx, [rbp+57h+var_90]
0x180110b01  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180110b06  nop
0x180110b07  lea     rcx, [rbp+57h+var_88]
0x180110b0b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180110b10  mov     ebx, r12d
0x180110b13  lea     rcx, [rbp+57h+var_78]
0x180110b17  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180110b1c  mov     eax, ebx
0x180110b1e  mov     rcx, [rbp+57h+var_30]
0x180110b22  xor     rcx, rsp; StackCookie
0x180110b25  call    __security_check_cookie
0x180110b2a  lea     r11, [rsp+0C0h+var_20]
0x180110b32  mov     rbx, [r11+38h]
0x180110b36  mov     rsi, [r11+40h]
0x180110b3a  mov     rsp, r11
0x180110b3d  pop     r15
0x180110b3f  pop     r14
0x180110b41  pop     r12
0x180110b43  pop     rdi
0x180110b44  pop     rbp
0x180110b45  retn
```
