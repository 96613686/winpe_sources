# ViewOperationBase::ShowHelper(void)

- ea: `0x1800411d0`
- end: `0x1800416cb`
- name: `?ShowHelper@ViewOperationBase@@AEAAJXZ`
- size: `1275`
- prototype: `__int64 __fastcall(ViewOperationBase *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003f220`

## callees

- `0x180006eac`
- `0x18000e87c`
- `0x180011f64`
- `0x180011ffc`
- `0x18001908c`
- `0x1800235a8`
- `0x18002d1d0`
- `0x18003d7d0`
- `0x18003e0c0`
- `0x18003e230`
- `0x18003e9c0`
- `0x18003f768`
- `0x18003f980`
- `0x1800411d0`
- `0x1800417a4`
- `0x180042770`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004121a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004133d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004143e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800414cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004121a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004133d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004143e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800414cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004137b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004138d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004155e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004137b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004138d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004155e`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180041307`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x180041307`

## string_xrefs

- `0x180041414`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800415c2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x1800413da`: `Windows.Internal.PlatformExtensions.UserDataAccountsExperience`
- `0x180041588`: `Windows.Internal.PlatformExtensions.AccountsControlExperience`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ViewOperationBase::ShowHelper(HSTRING *this)
{
  __int64 (__fastcall *v2)(HSTRING *, HSTRING *, char *, _QWORD *); // rbx
  _QWORD *v3; // r12
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // rax
  int (*v8)(ViewOperationBase *__hidden, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, int); // rsi
  int v9; // eax
  int ContractLaunchArgsString; // eax
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v12; // rbx
  _QWORD *v13; // rdi
  int v14; // eax
  int v15; // eax
  int ActivationArgs; // eax
  unsigned int v17; // ebx
  _QWORD *v18; // rdi
  int v19; // eax
  int v20; // eax
  int v21; // [rsp+20h] [rbp-E0h]
  int v22[2]; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+50h] [rbp-B0h] BYREF
  struct IInspectable *v25; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h] BYREF
  HSTRING *v27; // [rsp+68h] [rbp-98h] BYREF
  int (*v28)(ViewOperationBase *__hidden, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, int); // [rsp+70h] [rbp-90h] BYREF
  int v29; // [rsp+78h] [rbp-88h]
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+98h] [rbp-68h]
  _QWORD v32[42]; // [rsp+A0h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v2 = (__int64 (__fastcall *)(HSTRING *, HSTRING *, char *, _QWORD *))*((_QWORD *)*this + 20);
  v3 = this + 67;
  WindowsDeleteString(this[67]);
  *v3 = 0;
  v4 = v2(this, this + 65, (char *)this + 524, v3);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x17F,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
      (const char *)(unsigned int)v4,
      v21);
    return v5;
  }
  if ( *((_BYTE *)this + 520) )
  {
    v27 = this;
    Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v27);
    v28 = ViewOperationBase::OnUIViewClosed;
    v29 = 0;
    v25 = (struct IInspectable *)this;
    v7 = _lambda_f1c2e48c32bbd75b249d369f7cae8583_::_lambda_f1c2e48c32bbd75b249d369f7cae8583_(
           &hstringHeader,
           &v25,
           &v28);
    Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>,_lambda_f1c2e48c32bbd75b249d369f7cae8583_>(
      &v28,
      v7);
    v8 = v28;
    if ( !v28 )
    {
      v5 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x185,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
        (const char *)0x8007000ELL,
        v21);
LABEL_35:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
      return v5;
    }
    v26 = 0;
    v9 = UMgrQueryUserContext(0, &v26);
    if ( v9 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15B,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
        (const char *)(unsigned int)v9,
        v21);
    if ( *((_BYTE *)this + 112) )
    {
      WindowsDeleteString(0);
      string = 0;
      ContractLaunchArgsString = ViewOperationBase::GetContractLaunchArgsString((ViewOperationBase *)this, &string);
      if ( ContractLaunchArgsString < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x195,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
          (const char *)(unsigned int)ContractLaunchArgsString,
          v21);
      StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
      v12 = WindowsGetStringRawBuffer(this[16], 0);
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v32);
      v32[0] = &AccountsControlAPITelemetry::LaunchContractAppActivity::`vftable';
      AccountsControlAPITelemetry::LaunchContractAppActivity::StartActivity(
        (AccountsControlAPITelemetry::LaunchContractAppActivity *)v32,
        v12,
        StringRawBuffer);
      LODWORD(v12) = *((_DWORD *)this + 38);
      v31 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.PlatformExtensions.UserDataAccountsExperience",
        0x3Fu,
        0x3Eu);
      v13 = this + 69;
      v14 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
              v31,
              (unsigned int)v12,
              &GUID_eef49c8f_fb87_4f1e_8e8b_acb445e52ea5,
              this + 69);
      if ( v14 >= 0 )
      {
        if ( *v13 )
        {
          *(_QWORD *)v22 = this[15];
          v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, HSTRING))(*(_QWORD *)*v13 + 48LL))(
                  *v13,
                  *v3,
                  *(HSTRING *)((char *)this + 524),
                  this[16]);
          v5 = v15;
          if ( v15 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1A7,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
              (const char *)(unsigned int)v15,
              v22[0]);
            AccountsControlAPITelemetry::LaunchContractAppActivity::~LaunchContractAppActivity((AccountsControlAPITelemetry::LaunchContractAppActivity *)v32);
            WindowsDeleteString(string);
            string = 0;
            if ( v8 )
              (*(void (__fastcall **)(int (*)(ViewOperationBase *__hidden, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, int)))(*(_QWORD *)v8 + 16LL))(v8);
            goto LABEL_35;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v14,
          v21);
      }
      wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
      AccountsControlAPITelemetry::LaunchContractAppActivity::~LaunchContractAppActivity((AccountsControlAPITelemetry::LaunchContractAppActivity *)v32);
      WindowsDeleteString(string);
    }
    else
    {
      v25 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
      ActivationArgs = ViewOperationBase::GetActivationArgs((ViewOperationBase *)this, &v25);
      v5 = ActivationArgs;
      if ( ActivationArgs < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1AF,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
          (const char *)(unsigned int)ActivationArgs,
          v21);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
        if ( v8 )
          (*(void (__fastcall **)(int (*)(ViewOperationBase *__hidden, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, int)))(*(_QWORD *)v8 + 16LL))(v8);
        goto LABEL_35;
      }
      string = (HSTRING)WindowsGetStringRawBuffer(this[12], 0);
      AccountsControlAPITelemetry::ShowUIEvent<unsigned short const *>(&string);
      v17 = *((_DWORD *)this + 38);
      v31 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Internal.PlatformExtensions.AccountsControlExperience",
        0x3Eu,
        0x3Du);
      v18 = this + 68;
      v19 = Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
              v31,
              v17,
              &GUID_398c5e24_c4ae_4b09_ae41_292a171f478a,
              this + 68);
      if ( v19 >= 0 )
      {
        if ( *v18 )
        {
          v23 = (int)v25;
          v20 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, HSTRING, _QWORD))(*(_QWORD *)*v18 + 48LL))(
                  *v18,
                  this[70],
                  this[71],
                  *v3);
          v5 = v20;
          if ( v20 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1C0,
              (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrolsharedlib\\viewoperationbase.cpp",
              (const char *)(unsigned int)v20,
              v23);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
            if ( v8 )
              (*(void (__fastcall **)(int (*)(ViewOperationBase *__hidden, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, int)))(*(_QWORD *)v8 + 16LL))(v8);
            goto LABEL_35;
          }
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x299,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v19,
          v21);
      }
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
    }
    if ( v8 )
      (*(void (__fastcall **)(int (*)(ViewOperationBase *__hidden, struct Windows::Internal::UI::ApplicationSettings::IViewOperation *, int)))(*(_QWORD *)v8 + 16LL))(v8);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  }
  return 0;
}

```

## disassembly

```asm
0x1800411d0  mov     [rsp-8+arg_8], rbx
0x1800411d5  mov     [rsp-8+arg_10], rsi
0x1800411da  push    rbp
0x1800411db  push    rdi
0x1800411dc  push    r12
0x1800411de  push    r13
0x1800411e0  push    r14
0x1800411e2  lea     rbp, [rsp-100h]
0x1800411ea  sub     rsp, 200h
0x1800411f1  mov     rax, cs:__security_cookie
0x1800411f8  xor     rax, rsp
0x1800411fb  mov     [rbp+120h+var_30], rax
0x180041202  mov     r14, rcx
0x180041205  mov     rax, [rcx]
0x180041208  mov     rbx, [rax+0A0h]
0x18004120f  lea     r12, [rcx+218h]
0x180041216  mov     rcx, [r12]; string
0x18004121a  call    cs:__imp_WindowsDeleteString
0x180041220  mov     qword ptr [r12], 0
0x180041228  lea     r13, [r14+20Ch]
0x18004122f  lea     rdi, [r14+208h]
0x180041236  mov     r9, r12
0x180041239  mov     r8, r13
0x18004123c  mov     rdx, rdi
0x18004123f  mov     rcx, r14
0x180041242  mov     rax, rbx
0x180041245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004124a  mov     ebx, eax
0x18004124c  test    eax, eax
0x18004124e  jns     short loc_180041272
0x180041250  mov     rcx, [rbp+128h]; this
0x180041257  mov     r9d, eax; char *
0x18004125a  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x180041261  mov     edx, 17Fh; void *
0x180041266  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004126b  mov     eax, ebx
0x18004126d  jmp     loc_180041600
0x180041272  cmp     byte ptr [rdi], 0
0x180041275  jz      loc_1800415FE
0x18004127b  mov     [rsp+220h+var_1B8], r14
0x180041280  lea     rcx, [rsp+220h+var_1B8]
0x180041285  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x18004128a  nop
0x18004128b  lea     rax, ?OnUIViewClosed@ViewOperationBase@@AEAAJPEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Z; ViewOperationBase::OnUIViewClosed(Windows::Internal::UI::ApplicationSettings::IViewOperation *,int)
0x180041292  mov     [rsp+220h+var_1B0], rax
0x180041297  xor     edi, edi
0x180041299  mov     [rsp+220h+var_1A8], edi
0x18004129d  mov     eax, [rsp+220h+var_1A4]
0x1800412a1  mov     [rsp+220h+var_1A4], eax
0x1800412a5  mov     [rsp+220h+var_1C8], r14
0x1800412aa  lea     r8, [rsp+220h+var_1B0]
0x1800412af  lea     rdx, [rsp+220h+var_1C8]
0x1800412b4  lea     rcx, [rbp+120h+hstringHeader]
0x1800412b8  call    ??0_lambda_f1c2e48c32bbd75b249d369f7cae8583_@@QEAA@AEBQEAVViewOperationBase@@AEBQ81@EAAJPEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Z@Z; _lambda_f1c2e48c32bbd75b249d369f7cae8583_::_lambda_f1c2e48c32bbd75b249d369f7cae8583_(ViewOperationBase * const &,long (ViewOperationBase::*const &)(Windows::Internal::UI::ApplicationSettings::IViewOperation *,int))
0x1800412bd  mov     rdx, rax
0x1800412c0  lea     rcx, [rsp+220h+var_1B0]
0x1800412c5  call    ??$Callback@U?$ITypedEventHandler@PEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Foundation@Windows@@V_lambda_f1c2e48c32bbd75b249d369f7cae8583_@@@WRL@Microsoft@@YA?AV?$ComPtr@U?$ITypedEventHandler@PEAUIViewOperation@ApplicationSettings@UI@Internal@Windows@@H@Foundation@Windows@@@01@$$QEAV_lambda_f1c2e48c32bbd75b249d369f7cae8583_@@@Z; Microsoft::WRL::Callback<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::ApplicationSettings::IViewOperation *,int>,_lambda_f1c2e48c32bbd75b249d369f7cae8583_>(_lambda_f1c2e48c32bbd75b249d369f7cae8583_ &&)
0x1800412ca  nop
0x1800412cb  mov     rsi, [rsp+220h+var_1B0]
0x1800412d0  test    rsi, rsi
0x1800412d3  jnz     short loc_1800412FB
0x1800412d5  mov     rcx, [rbp+128h]; this
0x1800412dc  mov     ebx, 8007000Eh
0x1800412e1  mov     r9d, ebx; char *
0x1800412e4  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800412eb  mov     edx, 185h; void *
0x1800412f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800412f5  nop
0x1800412f6  jmp     loc_1800416BC
0x1800412fb  mov     [rsp+220h+var_1C0], rdi
0x180041300  lea     rdx, [rsp+220h+var_1C0]
0x180041305  xor     ecx, ecx
0x180041307  call    cs:__imp_UMgrQueryUserContext
0x18004130d  test    eax, eax
0x18004130f  jns     short loc_18004132C
0x180041311  mov     rcx, [rbp+128h]; this
0x180041318  mov     r9d, eax; char *
0x18004131b  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x180041322  mov     edx, 15Bh; void *
0x180041327  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004132c  cmp     [r14+70h], dil
0x180041330  jz      loc_1800414F5
0x180041336  mov     [rsp+220h+string], rdi
0x18004133b  xor     ecx, ecx; string
0x18004133d  call    cs:__imp_WindowsDeleteString
0x180041343  mov     [rsp+220h+string], rdi
0x180041348  lea     rdx, [rsp+220h+string]; HSTRING *
0x18004134d  mov     rcx, r14; this
0x180041350  call    ?GetContractLaunchArgsString@ViewOperationBase@@AEAAJPEAPEAUHSTRING__@@@Z; ViewOperationBase::GetContractLaunchArgsString(HSTRING__ * *)
0x180041355  mov     rcx, [rbp+128h]; this
0x18004135c  test    eax, eax
0x18004135e  jns     short loc_180041374
0x180041360  mov     r9d, eax; char *
0x180041363  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x18004136a  mov     edx, 195h; void *
0x18004136f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180041374  xor     edx, edx; length
0x180041376  mov     rcx, [rsp+220h+string]; string
0x18004137b  call    cs:__imp_WindowsGetStringRawBuffer
0x180041381  mov     rdi, rax
0x180041384  xor     edx, edx; length
0x180041386  mov     rcx, [r14+80h]; string
0x18004138d  call    cs:__imp_WindowsGetStringRawBuffer
0x180041393  mov     rbx, rax
0x180041396  lea     rdx, aLaunchcontract; "LaunchContractAppActivity"
0x18004139d  lea     rcx, [rbp+120h+var_180]; struct wil::details::IFailureCallback *
0x1800413a1  call    ??0?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800413a6  lea     rax, ??_7LaunchContractAppActivity@AccountsControlAPITelemetry@@6B@; const AccountsControlAPITelemetry::LaunchContractAppActivity::`vftable'
0x1800413ad  mov     [rbp+120h+var_180], rax
0x1800413b1  mov     r8, rdi; unsigned __int16 *
0x1800413b4  mov     rdx, rbx; unsigned __int16 *
0x1800413b7  lea     rcx, [rbp+120h+var_180]; this
0x1800413bb  call    ?StartActivity@LaunchContractAppActivity@AccountsControlAPITelemetry@@QEAAXPEBG0@Z; AccountsControlAPITelemetry::LaunchContractAppActivity::StartActivity(ushort const *,ushort const *)
0x1800413c0  nop
0x1800413c1  mov     ebx, [r14+98h]
0x1800413c8  mov     [rbp+120h+var_188], 0
0x1800413d0  mov     r9d, 3Eh ; '>'; unsigned int
0x1800413d6  lea     r8d, [r9+1]; unsigned int
0x1800413da  lea     rdx, aWindowsInterna_13; "Windows.Internal.PlatformExtensions.Use"...
0x1800413e1  lea     rcx, [rbp+120h+hstringHeader]; hstringHeader
0x1800413e5  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800413ea  lea     rdi, [r14+228h]
0x1800413f1  mov     r9, rdi
0x1800413f4  lea     r8, _GUID_eef49c8f_fb87_4f1e_8e8b_acb445e52ea5
0x1800413fb  mov     edx, ebx
0x1800413fd  mov     rcx, [rbp+120h+var_188]
0x180041401  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x180041406  test    eax, eax
0x180041408  jns     short loc_180041449
0x18004140a  mov     rcx, [rbp+128h]; this
0x180041411  mov     r9d, eax; char *
0x180041414  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18004141b  mov     edx, 299h; void *
0x180041420  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041425  lea     rcx, [rbp+120h+var_180]
0x180041429  call    ?Stop@?$ActivityBase@VAccountsControlAPITelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AccountsControlAPITelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004142e  nop
0x18004142f  lea     rcx, [rbp+120h+var_180]; this
0x180041433  call    ??1LaunchContractAppActivity@AccountsControlAPITelemetry@@QEAA@XZ; AccountsControlAPITelemetry::LaunchContractAppActivity::~LaunchContractAppActivity(void)
0x180041438  nop
0x180041439  mov     rcx, [rsp+220h+string]; string
0x18004143e  call    cs:__imp_WindowsDeleteString
0x180041444  jmp     loc_1800415DF
0x180041449  mov     rcx, [rdi]
0x18004144c  test    rcx, rcx
0x18004144f  jz      short loc_180041425
0x180041451  mov     r8, [rsp+220h+var_1C0]
0x180041456  mov     edx, [r14+98h]
0x18004145d  mov     rax, [rcx]
0x180041460  mov     [rsp+220h+var_1E0], r8
0x180041465  mov     [rsp+220h+var_1E8], rsi
0x18004146a  mov     dword ptr [rsp+220h+var_1F0], edx
0x18004146e  mov     rdx, [r14+88h]
0x180041475  mov     [rsp+220h+var_1F8], rdx
0x18004147a  mov     rdx, [r14+78h]
0x18004147e  mov     qword ptr [rsp+220h+var_200], rdx; int
0x180041483  mov     r9, [r14+80h]
0x18004148a  mov     r8, [r13+0]
0x18004148e  mov     rdx, [r12]
0x180041492  mov     rax, [rax+30h]
0x180041496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004149b  mov     ebx, eax
0x18004149d  test    eax, eax
0x18004149f  jns     short loc_180041425
0x1800414a1  mov     rcx, [rbp+128h]; this
0x1800414a8  mov     r9d, eax; char *
0x1800414ab  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800414b2  mov     edx, 1A7h; void *
0x1800414b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800414bc  nop
0x1800414bd  lea     rcx, [rbp+120h+var_180]; this
0x1800414c1  call    ??1LaunchContractAppActivity@AccountsControlAPITelemetry@@QEAA@XZ; AccountsControlAPITelemetry::LaunchContractAppActivity::~LaunchContractAppActivity(void)
0x1800414c6  nop
0x1800414c7  mov     rcx, [rsp+220h+string]; string
0x1800414cc  call    cs:__imp_WindowsDeleteString
0x1800414d2  mov     [rsp+220h+string], 0
0x1800414db  test    rsi, rsi
0x1800414de  jz      short loc_1800414F0
0x1800414e0  mov     rax, [rsi]
0x1800414e3  mov     rcx, rsi
0x1800414e6  mov     rax, [rax+10h]
0x1800414ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414ef  nop
0x1800414f0  jmp     loc_1800416BC
0x1800414f5  mov     [rsp+220h+var_1C8], rdi
0x1800414fa  lea     rcx, [rsp+220h+var_1C8]
0x1800414ff  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180041504  lea     rdx, [rsp+220h+var_1C8]; struct IInspectable **
0x180041509  mov     rcx, r14; this
0x18004150c  call    ?GetActivationArgs@ViewOperationBase@@AEAAJPEAPEAUIInspectable@@@Z; ViewOperationBase::GetActivationArgs(IInspectable * *)
0x180041511  mov     ebx, eax
0x180041513  test    eax, eax
0x180041515  jns     short loc_180041558
0x180041517  mov     rcx, [rbp+128h]; this
0x18004151e  mov     r9d, eax; char *
0x180041521  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x180041528  mov     edx, 1AFh; void *
0x18004152d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041532  nop
0x180041533  lea     rcx, [rsp+220h+var_1C8]
0x180041538  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004153d  nop
0x18004153e  test    rsi, rsi
0x180041541  jz      short loc_180041553
0x180041543  mov     rax, [rsi]
0x180041546  mov     rcx, rsi
0x180041549  mov     rax, [rax+10h]
0x18004154d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041552  nop
0x180041553  jmp     loc_1800416BC
0x180041558  xor     edx, edx; length
0x18004155a  mov     rcx, [r14+60h]; string
0x18004155e  call    cs:__imp_WindowsGetStringRawBuffer
0x180041564  mov     [rsp+220h+string], rax
0x180041569  lea     rcx, [rsp+220h+string]
0x18004156e  call    ??$ShowUIEvent@PEBG@AccountsControlAPITelemetry@@SAX$$QEAPEBG@Z; AccountsControlAPITelemetry::ShowUIEvent<ushort const *>(ushort const * &&)
0x180041573  mov     ebx, [r14+98h]
0x18004157a  mov     [rbp+120h+var_188], rdi
0x18004157e  mov     r9d, 3Dh ; '='; unsigned int
0x180041584  lea     r8d, [r9+1]; unsigned int
0x180041588  lea     rdx, aWindowsInterna_5; "Windows.Internal.PlatformExtensions.Acc"...
0x18004158f  lea     rcx, [rbp+120h+hstringHeader]; hstringHeader
0x180041593  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180041598  lea     rdi, [r14+220h]
0x18004159f  mov     r9, rdi
0x1800415a2  lea     r8, _GUID_398c5e24_c4ae_4b09_ae41_292a171f478a
0x1800415a9  mov     edx, ebx
0x1800415ab  mov     rcx, [rbp+120h+var_188]
0x1800415af  call    ?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z; Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)
0x1800415b4  test    eax, eax
0x1800415b6  jns     short loc_18004162B
0x1800415b8  mov     rcx, [rbp+128h]; this
0x1800415bf  mov     r9d, eax; char *
0x1800415c2  lea     r8, aOnecoreuapInte_2; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800415c9  mov     edx, 299h; void *
0x1800415ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800415d3  nop
0x1800415d4  lea     rcx, [rsp+220h+var_1C8]
0x1800415d9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800415de  nop
0x1800415df  test    rsi, rsi
0x1800415e2  jz      short loc_1800415F4
0x1800415e4  mov     rax, [rsi]
0x1800415e7  mov     rcx, rsi
0x1800415ea  mov     rax, [rax+10h]
0x1800415ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415f3  nop
0x1800415f4  lea     rcx, [rsp+220h+var_1B8]
0x1800415f9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800415fe  xor     eax, eax
0x180041600  mov     rcx, [rbp+120h+var_30]
0x180041607  xor     rcx, rsp; StackCookie
0x18004160a  call    __security_check_cookie
0x18004160f  lea     r11, [rsp+220h+var_20]
0x180041617  mov     rbx, [r11+38h]
0x18004161b  mov     rsi, [r11+40h]
0x18004161f  mov     rsp, r11
0x180041622  pop     r14
0x180041624  pop     r13
0x180041626  pop     r12
0x180041628  pop     rdi
0x180041629  pop     rbp
0x18004162a  retn
0x18004162b  mov     rcx, [rdi]
0x18004162e  test    rcx, rcx
0x180041631  jz      short loc_1800415D4
0x180041633  mov     r9, [rsp+220h+var_1C0]
0x180041638  mov     r8d, [r14+98h]
0x18004163f  mov     r10, [rsp+220h+var_1C8]
0x180041644  mov     rax, [rcx]
0x180041647  mov     [rsp+220h+var_1E8], r9
0x18004164c  mov     [rsp+220h+var_1F0], rsi
0x180041651  mov     dword ptr [rsp+220h+var_1F8], r8d
0x180041656  mov     qword ptr [rsp+220h+var_200], r10; int
0x18004165b  mov     r9, [r12]
0x18004165f  mov     r8, [r14+238h]
0x180041666  mov     rdx, [r14+230h]
0x18004166d  mov     rax, [rax+30h]
0x180041671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041676  mov     ebx, eax
0x180041678  test    eax, eax
0x18004167a  jns     loc_1800415D4
0x180041680  mov     rcx, [rbp+128h]; this
0x180041687  mov     r9d, eax; char *
0x18004168a  lea     r8, aOnecoreuapShel_0; "onecoreuap\\shell\\accountscontrol\\api"...
0x180041691  mov     edx, 1C0h; void *
0x180041696  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004169b  nop
0x18004169c  lea     rcx, [rsp+220h+var_1C8]
0x1800416a1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800416a6  nop
0x1800416a7  test    rsi, rsi
0x1800416aa  jz      short loc_1800416BC
0x1800416ac  mov     rax, [rsi]
0x1800416af  mov     rcx, rsi
0x1800416b2  mov     rax, [rax+10h]
0x1800416b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416bb  nop
0x1800416bc  lea     rcx, [rsp+220h+var_1B8]
0x1800416c1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
  ... truncated ...
```
