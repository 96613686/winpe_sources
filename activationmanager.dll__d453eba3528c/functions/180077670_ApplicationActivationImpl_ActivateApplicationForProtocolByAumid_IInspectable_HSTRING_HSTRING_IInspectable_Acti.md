# ApplicationActivationImpl::ActivateApplicationForProtocolByAumid(IInspectable *,HSTRING__ *,HSTRING__ *,IInspectable *,ActivationParameters,ActivationResult *)

- ea: `0x180077670`
- end: `0x180077c9b`
- name: `?ActivateApplicationForProtocolByAumid@ApplicationActivationImpl@@UEAAJPEAUIInspectable@@PEAUHSTRING__@@10UActivationParameters@@PEAUActivationResult@@@Z`
- size: `1579`
- prototype: `int __high(struct IInspectable *, HSTRING, HSTRING, struct IInspectable *, struct ActivationParameters, struct ActivationResult *)`
- caller_count: `0`
- callee_count: `18`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x18001e3c4`
- `0x1800374c8`
- `0x1800375ec`
- `0x18004a58c`
- `0x18004f278`
- `0x18005ae90`
- `0x18005ba40`
- `0x18005ede8`
- `0x180076440`
- `0x18007663c`
- `0x18007689c`
- `0x180076d04`
- `0x180077670`
- `0x1800790fc`
- `0x180079720`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077b63`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180077b63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007797b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800779be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077be9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007797b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800779be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a08`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077a51`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077abb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077ac7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077bdd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077be9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c2c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180077c38`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800776cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800776d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800778aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800779dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800779ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800776cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800776d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800778aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800779dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800779ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077b4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180077b4a`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x180077925`
- `ext-ms-win-desktopappx-l1-1-0!TryActivateDesktopAppXApplication` at `0x180077925`

## string_xrefs

- `0x1800778c3`: `Windows.Protocol`
- `0x18007795e`: `Windows.Protocol`
- `0x1800776e2`: `ActivateApplicationForProtocolByAumid`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ApplicationActivationImpl::ActivateApplicationForProtocolByAumid(
        __int64 a1,
        struct IInspectable *a2,
        HSTRING a3,
        HSTRING a4,
        struct IInspectable *a5,
        __int64 a6,
        _DWORD *a7)
{
  const unsigned __int16 *StringRawBuffer; // rdi
  const unsigned __int16 *v12; // rbx
  int v13; // eax
  const unsigned __int16 *v14; // rdx
  unsigned int v15; // ebx
  _QWORD *v16; // rax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING, HSTRING *); // rbx
  int v20; // eax
  int UserToken; // eax
  ApplicationActivationImpl *v22; // rcx
  __int64 v23; // rdx
  unsigned int v24; // r14d
  HSTRING v25; // rdi
  __int64 (__fastcall *v26)(HSTRING, HSTRING *); // rbx
  int v27; // eax
  PCWSTR v28; // rbx
  PCWSTR v29; // rax
  __int64 v30; // rdx
  HSTRING *ExtensionId; // rdi
  HSTRING v32; // rbx
  const char *v33; // r9
  ApplicationActivationImpl *v34; // rcx
  int v35; // edi
  __int64 v36; // rdx
  struct IApplicationActivationManagerPriv *v37; // rdi
  int v39; // [rsp+20h] [rbp-288h]
  int v40; // [rsp+20h] [rbp-288h]
  HSTRING v41; // [rsp+50h] [rbp-258h] BYREF
  HSTRING v42; // [rsp+58h] [rbp-250h] BYREF
  void *v43; // [rsp+60h] [rbp-248h] BYREF
  __int64 v44; // [rsp+68h] [rbp-240h] BYREF
  HSTRING string; // [rsp+70h] [rbp-238h] BYREF
  struct IApplicationActivationManagerPriv *v46; // [rsp+78h] [rbp-230h] BYREF
  int v47; // [rsp+80h] [rbp-228h]
  unsigned int v48[2]; // [rsp+88h] [rbp-220h] BYREF
  struct IInspectable *v49; // [rsp+90h] [rbp-218h]
  HSTRING v50; // [rsp+98h] [rbp-210h]
  unsigned __int64 v51; // [rsp+A0h] [rbp-208h] BYREF
  __int64 (__fastcall *v52)(struct IApplicationActivationManagerPriv *, HSTRING, _QWORD, HSTRING); // [rsp+A8h] [rbp-200h]
  PCWSTR v53; // [rsp+B0h] [rbp-1F8h] BYREF
  int v54; // [rsp+B8h] [rbp-1F0h]
  const WCHAR *v55; // [rsp+C0h] [rbp-1E8h]
  void *v56; // [rsp+C8h] [rbp-1E0h]
  int v57; // [rsp+D8h] [rbp-1D0h]
  int v58; // [rsp+DCh] [rbp-1CCh]
  unsigned __int64 v59; // [rsp+E0h] [rbp-1C8h]
  struct IInspectable *v60; // [rsp+E8h] [rbp-1C0h]
  HSTRING v61; // [rsp+F0h] [rbp-1B8h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+F8h] [rbp-1B0h] BYREF
  _QWORD v63[42]; // [rsp+110h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+0h]

  string = a3;
  v49 = a5;
  StringRawBuffer = WindowsGetStringRawBuffer(a4, 0);
  v12 = WindowsGetStringRawBuffer(a3, 0);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v63,
    "ActivateApplicationForProtocolByAumid");
  v63[0] = &AAMTraceProvider::ActivateApplicationForProtocolByAumid::`vftable';
  AAMTraceProvider::ActivateApplicationForProtocolByAumid::StartActivity(
    (AAMTraceProvider::ActivateApplicationForProtocolByAumid *)v63,
    v12,
    StringRawBuffer);
  v13 = ApplicationActivationImpl::CheckCallerCapabilities((ApplicationActivationImpl *)(a1 - 32));
  v15 = v13;
  if ( v13 >= 0 )
  {
    v44 = 0;
    v16 = (_QWORD *)Windows::Internal::StringReference::StringReference(&v61, (const unsigned __int16 (*)[23])v14);
    v17 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(
            *v16,
            &v44);
    v15 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v17,
        v39);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
      goto LABEL_40;
    }
    v42 = 0;
    v18 = v44;
    v19 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING *))(*(_QWORD *)v44 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    v20 = v19(v18, a4, &v42);
    v15 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v20,
        v39);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      goto LABEL_5;
    }
    v43 = 0;
    v50 = v42;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    UserToken = Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,Windows::Foundation::IUriRuntimeClass *>(&v43);
    v15 = UserToken;
    if ( UserToken < 0 )
    {
      v23 = 220;
LABEL_11:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)UserToken,
        v39);
LABEL_12:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      goto LABEL_8;
    }
    v51 = 0;
    UserToken = ApplicationActivationImpl::GetUserToken(v22, a2, &v51);
    v15 = UserToken;
    if ( UserToken < 0 )
    {
      v23 = 223;
      goto LABEL_11;
    }
    if ( (unsigned __int8)IsTryActivateDesktopAppXApplicationPresent() )
    {
      memset_0(&v53, 0, 0x40u);
      *(_QWORD *)v48 = 0;
      v53 = WindowsGetStringRawBuffer(string, 0);
      v54 = 1;
      v55 = L"Windows.Protocol";
      v56 = v43;
      v58 = *(_DWORD *)(a6 + 4);
      v59 = v51;
      v57 = 16;
      v60 = v49;
      UserToken = TryActivateDesktopAppXApplication(&v53, v48);
      v15 = UserToken;
      if ( UserToken < 0 )
      {
        v23 = 240;
        goto LABEL_11;
      }
      v24 = v48[1];
      if ( a7 )
        *a7 = v48[1];
      if ( v48[0] != 1 )
        goto LABEL_39;
    }
    else
    {
      v24 = 0;
    }
    v41 = 0;
    v25 = v42;
    v26 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)v42 + 136LL);
    WindowsDeleteString(0);
    v41 = 0;
    v27 = v26(v25, &v41);
    v15 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xFC,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v27,
        v39);
LABEL_25:
      WindowsDeleteString(v41);
      v41 = 0;
      goto LABEL_12;
    }
    v50 = 0;
    v28 = WindowsGetStringRawBuffer(string, 0);
    v29 = WindowsGetStringRawBuffer(v41, 0);
    try
    {
      ExtensionId = (HSTRING *)GetExtensionId(&string, v30, v29, v28);
      WindowsDeleteString(0);
      v32 = *ExtensionId;
      v50 = *ExtensionId;
      *ExtensionId = 0;
      WindowsDeleteString(string);
    }
    catch ( ... )
    {
      LODWORD(string) = wil::details::in1diag3::Return_CaughtException(
                          retaddr,
                          (void *)0x103,
                          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
                          v33);
      WindowsDeleteString(v50);
      WindowsDeleteString(v41);
      v41 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
      v15 = (unsigned int)string;
      goto LABEL_40;
    }
    if ( !v32 )
    {
      v15 = -2144927148;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x104,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)0x80270254LL,
        v39);
      WindowsDeleteString(0);
      goto LABEL_25;
    }
    v46 = 0;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    v35 = ApplicationActivationImpl::CreateActivationManagerAndSetInfo(
            v34,
            *(_DWORD *)(a6 + 4),
            *(_DWORD *)(a6 + 8),
            v49,
            &v46);
    if ( v35 < 0 )
    {
      v36 = 263;
LABEL_31:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v36,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
        (const char *)(unsigned int)v35,
        v40);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      WindowsDeleteString(v32);
      WindowsDeleteString(v41);
      v41 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
      v15 = v35;
      goto LABEL_40;
    }
    v47 = 0;
    v37 = v46;
    v52 = *(__int64 (__fastcall **)(struct IApplicationActivationManagerPriv *, HSTRING, _QWORD, HSTRING))(*(_QWORD *)v46 + 72LL);
    v49 = (struct IInspectable *)v51;
    string = (HSTRING)v43;
    if ( WindowsCreateStringReference(L"Windows.Protocol", 0x10u, &hstringHeader, &v61) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v40 = (int)string;
    v35 = v52(v37, v32, 0, v61);
    if ( v35 < 0 )
    {
      v36 = 273;
      goto LABEL_31;
    }
    if ( a7 )
      *a7 = v47;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    WindowsDeleteString(v32);
    WindowsDeleteString(v41);
LABEL_39:
    AAMTraceProvider::ActivateApplicationForProtocolByAumid::Stop(
      (AAMTraceProvider::ActivateApplicationForProtocolByAumid *)v63,
      v24);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v43);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v44);
    v15 = 0;
    goto LABEL_40;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD3,
    (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
    (const char *)(unsigned int)v13,
    v39);
LABEL_40:
  AAMTraceProvider::ActivateApplicationForProtocolByAumid::~ActivateApplicationForProtocolByAumid((AAMTraceProvider::ActivateApplicationForProtocolByAumid *)v63);
  return v15;
}

```

## disassembly

```asm
0x180077670  push    rbx
0x180077672  push    rsi
0x180077673  push    rdi
0x180077674  push    r12
0x180077676  push    r13
0x180077678  push    r14
0x18007767a  push    r15
0x18007767c  sub     rsp, 270h
0x180077683  mov     rax, cs:__security_cookie
0x18007768a  xor     rax, rsp
0x18007768d  mov     [rsp+2A8h+var_48], rax
0x180077695  mov     r12, r9
0x180077698  mov     rbx, r8
0x18007769b  mov     [rsp+2A8h+string], rbx
0x1800776a0  mov     r14, rdx
0x1800776a3  mov     rsi, rcx
0x1800776a6  mov     r13, [rsp+2A8h+arg_28]
0x1800776ae  mov     r15, [rsp+2A8h+arg_30]
0x1800776b6  mov     rax, [rsp+2A8h+arg_20]
0x1800776be  mov     [rsp+2A8h+var_218], rax
0x1800776c6  xor     edx, edx; length
0x1800776c8  mov     rcx, r9; string
0x1800776cb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800776d1  mov     rdi, rax
0x1800776d4  xor     edx, edx; length
0x1800776d6  mov     rcx, rbx; string
0x1800776d9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800776df  mov     rbx, rax
0x1800776e2  lea     rdx, aActivateapplic_1; "ActivateApplicationForProtocolByAumid"
0x1800776e9  lea     rcx, [rsp+2A8h+var_198]
0x1800776f1  call    ??0?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800776f6  lea     rax, ??_7ActivateApplicationForProtocolByAumid@AAMTraceProvider@@6B@; const AAMTraceProvider::ActivateApplicationForProtocolByAumid::`vftable'
0x1800776fd  mov     [rsp+2A8h+var_198], rax
0x180077705  mov     r8, rdi; unsigned __int16 *
0x180077708  mov     rdx, rbx; unsigned __int16 *
0x18007770b  lea     rcx, [rsp+2A8h+var_198]; this
0x180077713  call    ?StartActivity@ActivateApplicationForProtocolByAumid@AAMTraceProvider@@QEAAXPEBG0@Z; AAMTraceProvider::ActivateApplicationForProtocolByAumid::StartActivity(ushort const *,ushort const *)
0x180077718  nop
0x180077719  lea     rcx, [rsi-20h]; this
0x18007771d  call    ?CheckCallerCapabilities@ApplicationActivationImpl@@AEAAJXZ; ApplicationActivationImpl::CheckCallerCapabilities(void)
0x180077722  mov     ebx, eax
0x180077724  xor     esi, esi
0x180077726  test    eax, eax
0x180077728  jns     short loc_18007774B
0x18007772a  mov     rcx, [rsp+2A8h]; this
0x180077732  mov     r9d, eax; char *
0x180077735  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18007773c  mov     edx, 0D3h; void *
0x180077741  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077746  jmp     loc_180077C69
0x18007774b  mov     [rsp+2A8h+var_240], rsi
0x180077750  lea     rcx, [rsp+2A8h+var_1B8]; string
0x180077758  call    ??$?0$0BH@@StringReference@Internal@Windows@@QEAA@AEAY0BH@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[23])
0x18007775d  lea     rdx, [rsp+2A8h+var_240]
0x180077762  mov     rcx, [rax]
0x180077765  call    ??$GetActivationFactory@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIUriRuntimeClassFactory@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IUriRuntimeClassFactory>>)
0x18007776a  mov     ebx, eax
0x18007776c  test    eax, eax
0x18007776e  jns     short loc_18007779C
0x180077770  mov     rcx, [rsp+2A8h]; this
0x180077778  mov     r9d, eax; char *
0x18007777b  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077782  mov     edx, 0D6h; void *
0x180077787  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007778c  nop
0x18007778d  lea     rcx, [rsp+2A8h+var_240]
0x180077792  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077797  jmp     loc_180077C69
0x18007779c  mov     [rsp+2A8h+var_250], rsi
0x1800777a1  mov     rdi, [rsp+2A8h+var_240]
0x1800777a6  mov     rax, [rdi]
0x1800777a9  mov     rbx, [rax+30h]
0x1800777ad  lea     rcx, [rsp+2A8h+var_250]
0x1800777b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800777b7  lea     r8, [rsp+2A8h+var_250]
0x1800777bc  mov     rdx, r12
0x1800777bf  mov     rcx, rdi
0x1800777c2  mov     rax, rbx
0x1800777c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800777ca  mov     ebx, eax
0x1800777cc  test    eax, eax
0x1800777ce  jns     short loc_1800777F9
0x1800777d0  mov     rcx, [rsp+2A8h]; this
0x1800777d8  mov     r9d, eax; char *
0x1800777db  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800777e2  mov     edx, 0D9h; void *
0x1800777e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800777ec  nop
0x1800777ed  lea     rcx, [rsp+2A8h+var_250]
0x1800777f2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800777f7  jmp     short loc_18007778D
0x1800777f9  mov     [rsp+2A8h+var_248], rsi
0x1800777fe  mov     rax, [rsp+2A8h+var_250]
0x180077803  mov     [rsp+2A8h+var_210], rax
0x18007780b  lea     rcx, [rsp+2A8h+var_248]
0x180077810  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077815  lea     rdx, [rsp+2A8h+var_210]
0x18007781d  lea     rcx, [rsp+2A8h+var_248]; void **
0x180077822  call    ??$MakeAndInitialize@VCProtocolActivatedEventArgs@@UIActivatedEventArgs@Activation@ApplicationModel@Windows@@PEAUIUriRuntimeClass@Foundation@5@@Details@WRL@Microsoft@@YAJPEAPEAUIActivatedEventArgs@Activation@ApplicationModel@Windows@@$$QEAPEAUIUriRuntimeClass@Foundation@6@@Z; Microsoft::WRL::Details::MakeAndInitialize<CProtocolActivatedEventArgs,Windows::ApplicationModel::Activation::IActivatedEventArgs,Windows::Foundation::IUriRuntimeClass *>(Windows::ApplicationModel::Activation::IActivatedEventArgs * *,Windows::Foundation::IUriRuntimeClass * &&)
0x180077827  mov     ebx, eax
0x180077829  test    eax, eax
0x18007782b  jns     short loc_180077856
0x18007782d  mov     edx, 0DCh; void *
0x180077832  mov     rcx, [rsp+2A8h]; this
0x18007783a  mov     r9d, eax; char *
0x18007783d  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077844  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077849  nop
0x18007784a  lea     rcx, [rsp+2A8h+var_248]
0x18007784f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077854  jmp     short loc_1800777ED
0x180077856  mov     [rsp+2A8h+var_208], rsi
0x18007785e  lea     r8, [rsp+2A8h+var_208]; unsigned __int64 *
0x180077866  mov     rdx, r14; struct IInspectable *
0x180077869  call    ?GetUserToken@ApplicationActivationImpl@@AEAAJPEAUIInspectable@@PEA_K@Z; ApplicationActivationImpl::GetUserToken(IInspectable *,unsigned __int64 *)
0x18007786e  mov     ebx, eax
0x180077870  test    eax, eax
0x180077872  jns     short loc_18007787B
0x180077874  mov     edx, 0DFh
0x180077879  jmp     short loc_180077832
0x18007787b  call    IsTryActivateDesktopAppXApplicationPresent
0x180077880  test    al, al
0x180077882  jz      loc_18007795B
0x180077888  xor     edx, edx; Val
0x18007788a  lea     r8d, [rdx+40h]; Size
0x18007788e  lea     rcx, [rsp+2A8h+var_1F8]; void *
0x180077896  call    memset_0
0x18007789b  mov     qword ptr [rsp+2A8h+var_220], rsi
0x1800778a3  xor     edx, edx; length
0x1800778a5  mov     rcx, [rsp+2A8h+string]; string
0x1800778aa  call    cs:__imp_WindowsGetStringRawBuffer
0x1800778b0  mov     [rsp+2A8h+var_1F8], rax
0x1800778b8  mov     [rsp+2A8h+var_1F0], 1
0x1800778c3  lea     r12, sourceString; "Windows.Protocol"
0x1800778ca  mov     [rsp+2A8h+var_1E8], r12
0x1800778d2  mov     rax, [rsp+2A8h+var_248]
0x1800778d7  mov     [rsp+2A8h+var_1E0], rax
0x1800778df  mov     eax, [r13+4]
0x1800778e3  mov     [rsp+2A8h+var_1CC], eax
0x1800778ea  mov     rax, [rsp+2A8h+var_208]
0x1800778f2  mov     [rsp+2A8h+var_1C8], rax
0x1800778fa  mov     [rsp+2A8h+var_1D0], 10h
0x180077905  mov     rax, [rsp+2A8h+var_218]
0x18007790d  mov     [rsp+2A8h+var_1C0], rax
0x180077915  lea     rdx, [rsp+2A8h+var_220]
0x18007791d  lea     rcx, [rsp+2A8h+var_1F8]
0x180077925  call    cs:__imp_TryActivateDesktopAppXApplication
0x18007792b  mov     ebx, eax
0x18007792d  test    eax, eax
0x18007792f  jns     short loc_18007793B
0x180077931  mov     edx, 0F0h
0x180077936  jmp     loc_180077832
0x18007793b  mov     r14d, [rsp+2A8h+var_220+4]
0x180077943  test    r15, r15
0x180077946  jz      short loc_18007794B
0x180077948  mov     [r15], r14d
0x18007794b  cmp     [rsp+2A8h+var_220], 1
0x180077953  jnz     loc_180077BEF
0x180077959  jmp     short loc_180077965
0x18007795b  mov     r14d, esi
0x18007795e  lea     r12, sourceString; "Windows.Protocol"
0x180077965  mov     [rsp+2A8h+var_258], rsi
0x18007796a  mov     rdi, [rsp+2A8h+var_250]
0x18007796f  mov     rax, [rdi]
0x180077972  mov     rbx, [rax+88h]
0x180077979  xor     ecx, ecx; string
0x18007797b  call    cs:__imp_WindowsDeleteString
0x180077981  mov     [rsp+2A8h+var_258], rsi
0x180077986  lea     rdx, [rsp+2A8h+var_258]
0x18007798b  mov     rcx, rdi
0x18007798e  mov     rax, rbx
0x180077991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077996  mov     ebx, eax
0x180077998  test    eax, eax
0x18007799a  jns     short loc_1800779CE
0x18007799c  mov     rcx, [rsp+2A8h]; this
0x1800779a4  mov     r9d, eax; char *
0x1800779a7  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x1800779ae  mov     edx, 0FCh; void *
0x1800779b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800779b8  nop
0x1800779b9  mov     rcx, [rsp+2A8h+var_258]; string
0x1800779be  call    cs:__imp_WindowsDeleteString
0x1800779c4  mov     [rsp+2A8h+var_258], rsi
0x1800779c9  jmp     loc_18007784A
0x1800779ce  mov     [rsp+2A8h+var_210], rsi
0x1800779d6  xor     edx, edx; length
0x1800779d8  mov     rcx, [rsp+2A8h+string]; string
0x1800779dd  call    cs:__imp_WindowsGetStringRawBuffer
0x1800779e3  mov     rbx, rax
0x1800779e6  xor     edx, edx; length
0x1800779e8  mov     rcx, [rsp+2A8h+var_258]; string
0x1800779ed  call    cs:__imp_WindowsGetStringRawBuffer
0x1800779f3  mov     r9, rbx
0x1800779f6  mov     r8, rax
0x1800779f9  lea     rcx, [rsp+2A8h+string]
0x1800779fe  call    ?GetExtensionId@@YA?AVHString@Wrappers@WRL@Microsoft@@PEBG00@Z; GetExtensionId(ushort const *,ushort const *,ushort const *)
0x180077a03  mov     rdi, rax
0x180077a06  xor     ecx, ecx; string
0x180077a08  call    cs:__imp_WindowsDeleteString
0x180077a0e  mov     rbx, [rdi]
0x180077a11  mov     [rsp+2A8h+var_210], rbx
0x180077a19  mov     [rdi], rsi
0x180077a1c  mov     rcx, [rsp+2A8h+string]; string
0x180077a21  call    cs:__imp_WindowsDeleteString
0x180077a27  nop
0x180077a28  test    rbx, rbx
0x180077a2b  jnz     short loc_180077A5C
0x180077a2d  mov     rcx, [rsp+2A8h]; this
0x180077a35  mov     ebx, 80270254h
0x180077a3a  mov     r9d, ebx; char *
0x180077a3d  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077a44  mov     edx, 104h; void *
0x180077a49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077a4e  nop
0x180077a4f  xor     ecx, ecx; string
0x180077a51  call    cs:__imp_WindowsDeleteString
0x180077a57  jmp     loc_1800779B9
0x180077a5c  mov     [rsp+2A8h+var_230], rsi
0x180077a61  lea     rcx, [rsp+2A8h+var_230]
0x180077a66  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077a6b  lea     rax, [rsp+2A8h+var_230]
0x180077a70  mov     [rsp+2A8h+var_288], rax; int
0x180077a75  mov     r9, [rsp+2A8h+var_218]; struct IInspectable *
0x180077a7d  mov     r8d, [r13+8]; unsigned int
0x180077a81  mov     edx, [r13+4]; unsigned int
0x180077a85  call    ?CreateActivationManagerAndSetInfo@ApplicationActivationImpl@@AEAAJIIPEAUIInspectable@@PEAPEAUIApplicationActivationManagerPriv@@@Z; ApplicationActivationImpl::CreateActivationManagerAndSetInfo(uint,uint,IInspectable *,IApplicationActivationManagerPriv * *)
0x180077a8a  mov     edi, eax
0x180077a8c  test    eax, eax
0x180077a8e  jns     short loc_180077AF9
0x180077a90  mov     edx, 107h; void *
0x180077a95  lea     r8, aOnecoreuapBase_12; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180077a9c  mov     r9d, edi; char *
0x180077a9f  mov     rcx, [rsp+2A8h]; this
0x180077aa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180077aac  nop
0x180077aad  lea     rcx, [rsp+2A8h+var_230]
0x180077ab2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077ab7  nop
0x180077ab8  mov     rcx, rbx; string
0x180077abb  call    cs:__imp_WindowsDeleteString
0x180077ac1  nop
0x180077ac2  mov     rcx, [rsp+2A8h+var_258]; string
0x180077ac7  call    cs:__imp_WindowsDeleteString
0x180077acd  mov     [rsp+2A8h+var_258], rsi
0x180077ad2  lea     rcx, [rsp+2A8h+var_248]
0x180077ad7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077adc  nop
0x180077add  lea     rcx, [rsp+2A8h+var_250]
0x180077ae2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077ae7  nop
0x180077ae8  lea     rcx, [rsp+2A8h+var_240]
0x180077aed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180077af2  mov     ebx, edi
0x180077af4  jmp     loc_180077C69
0x180077af9  mov     [rsp+2A8h+var_228], esi
0x180077b00  mov     rdi, [rsp+2A8h+var_230]
0x180077b05  mov     rax, [rdi]
0x180077b08  mov     rax, [rax+48h]
0x180077b0c  mov     [rsp+2A8h+var_200], rax
0x180077b14  mov     rax, [rsp+2A8h+var_208]
0x180077b1c  mov     [rsp+2A8h+var_218], rax
0x180077b24  mov     r13d, [r13+0]
0x180077b28  mov     rax, [rsp+2A8h+var_248]
0x180077b2d  mov     [rsp+2A8h+string], rax
0x180077b32  lea     r9, [rsp+2A8h+var_1B8]; string
0x180077b3a  lea     r8, [rsp+2A8h+hstringHeader]; hstringHeader
0x180077b42  mov     edx, 10h; length
0x180077b47  mov     rcx, r12; sourceString
0x180077b4a  call    cs:__imp_WindowsCreateStringReference
0x180077b50  test    eax, eax
0x180077b52  jns     short loc_180077B69
0x180077b54  xor     r9d, r9d; lpArguments
0x180077b57  xor     r8d, r8d; nNumberOfArguments
0x180077b5a  lea     edx, [r9+1]; dwExceptionFlags
0x180077b5e  mov     ecx, 0C000000Dh; dwExceptionCode
0x180077b63  call    cs:__imp_RaiseException
0x180077b69  lea     rax, [rsp+2A8h+var_228]
0x180077b71  mov     [rsp+2A8h+var_270], rax
0x180077b76  mov     rcx, [rsp+2A8h+var_218]
0x180077b7e  mov     [rsp+2A8h+var_278], rcx
0x180077b83  mov     [rsp+2A8h+var_280], r13d
0x180077b88  mov     rcx, [rsp+2A8h+string]
0x180077b8d  mov     [rsp+2A8h+var_288], rcx
0x180077b92  mov     r9, [rsp+2A8h+var_1B8]
0x180077b9a  xor     r8d, r8d
0x180077b9d  mov     rdx, rbx
0x180077ba0  mov     rcx, rdi
0x180077ba3  mov     rax, [rsp+2A8h+var_200]
0x180077bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077bb0  mov     edi, eax
0x180077bb2  test    eax, eax
0x180077bb4  jns     short loc_180077BC0
0x180077bb6  mov     edx, 111h
0x180077bbb  jmp     loc_180077A95
0x180077bc0  test    r15, r15
0x180077bc3  jz      short loc_180077BCF
0x180077bc5  mov     eax, [rsp+2A8h+var_228]
0x180077bcc  mov     [r15], eax
0x180077bcf  lea     rcx, [rsp+2A8h+var_230]
  ... truncated ...
```
