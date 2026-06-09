# ApplicationActivationImpl::ActivateApplicationForPlugin(IInspectable *,HSTRING__ *,_GUID,IInspectable *,IInspectable *,ActivationParameters,ActivationResult *)

- ea: `0x180036ee0`
- end: `0x1800374c0`
- name: `?ActivateApplicationForPlugin@ApplicationActivationImpl@@UEAAJPEAUIInspectable@@PEAUHSTRING__@@U_GUID@@00UActivationParameters@@PEAUActivationResult@@@Z`
- size: `1504`
- prototype: `int __high(struct IInspectable *, HSTRING, struct _GUID, struct IInspectable *, struct IInspectable *, struct ActivationParameters, struct ActivationResult *)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18000b5c0`
- `0x180011328`
- `0x1800169e4`
- `0x18001baa4`
- `0x18001e3c4`
- `0x18001e5ac`
- `0x180036ee0`
- `0x1800374c8`
- `0x180037574`
- `0x1800375ec`
- `0x18004c4dc`
- `0x18004cd58`
- `0x180050314`
- `0x18005ae90`
- `0x18005b33c`
- `0x18005b3a0`
- `0x18005d1ac`
- `0x180079268`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800373da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800373da`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003713a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003719d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800371d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003713a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003719d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800371d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180037212`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036f44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003718f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037369`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180036f44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037169`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003718f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180037369`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180037332`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x180037332`

## string_xrefs

- `0x180036f4d`: `ActivateApplicationForPlugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall ApplicationActivationImpl::ActivateApplicationForPlugin(
        __int64 a1,
        struct IInspectable *a2,
        HSTRING a3,
        const struct _GUID *a4,
        __int64 (__fastcall ***a5)(_QWORD, GUID *, __int64 *),
        __int64 a6,
        __int64 a7)
{
  struct IInspectable *v8; // r14
  const unsigned __int16 *StringRawBuffer; // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 (__fastcall *v13)(_QWORD, GUID *, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rcx
  void *v16; // rbx
  char *v17; // r12
  unsigned int *v18; // rdx
  ApplicationActivationImpl *v19; // rcx
  int UserToken; // edi
  __int64 v21; // rdx
  unsigned __int64 v22; // rax
  void *v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rax
  bool v26; // cf
  unsigned __int64 v27; // rax
  _QWORD *v28; // rax
  unsigned int i; // r14d
  __int64 v30; // rsi
  __int64 (__fastcall *v31)(__int64, _QWORD, HSTRING *); // rdi
  int v32; // eax
  int v33; // edi
  const unsigned __int16 *v34; // rax
  const struct std::nothrow_t *v35; // rdx
  const struct std::nothrow_t *v36; // rdx
  __int64 v37; // rcx
  const struct std::nothrow_t *v38; // rdx
  __int64 v39; // rcx
  __int64 v40; // rdx
  __int64 v41; // r15
  __int64 (__fastcall *v42)(__int64, _QWORD, _QWORD, __int128 *); // r14
  const struct std::nothrow_t *v43; // rdx
  __int64 v44; // rcx
  const struct std::nothrow_t *v45; // rdx
  int v47; // [rsp+20h] [rbp-E0h]
  __int64 v48; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v49; // [rsp+78h] [rbp-88h] BYREF
  HSTRING string; // [rsp+80h] [rbp-80h] BYREF
  int Parameter; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v52; // [rsp+8Ch] [rbp-74h]
  unsigned __int64 v53; // [rsp+90h] [rbp-70h] BYREF
  HANDLE hObject; // [rsp+98h] [rbp-68h]
  void *v55; // [rsp+A0h] [rbp-60h]
  char *v56; // [rsp+A8h] [rbp-58h]
  struct IInspectable *v57; // [rsp+B0h] [rbp-50h]
  HSTRING v58; // [rsp+B8h] [rbp-48h]
  __int128 v59; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v60; // [rsp+D0h] [rbp-30h]
  __int64 v61; // [rsp+D8h] [rbp-28h]
  _QWORD v62[42]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *(_QWORD *)&v59 = a4;
  v58 = a3;
  v8 = a2;
  v57 = a2;
  v60 = a6;
  v61 = a7;
  StringRawBuffer = WindowsGetStringRawBuffer(a3, 0);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v62,
    "ActivateApplicationForPlugin");
  v62[0] = &AAMTraceProvider::ActivateApplicationForPlugin::`vftable';
  AAMTraceProvider::ActivateApplicationForPlugin::StartActivity(
    (AAMTraceProvider::ActivateApplicationForPlugin *)v62,
    StringRawBuffer,
    a4);
  v11 = ApplicationActivationImpl::CheckCallerCapabilities((ApplicationActivationImpl *)(a1 - 32));
  v12 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v11,
      v47);
LABEL_63:
    AAMTraceProvider::ActivateApplicationForPlugin::~ActivateApplicationForPlugin((AAMTraceProvider::ActivateApplicationForPlugin *)v62);
    return v12;
  }
  v48 = 0;
  v13 = **a5;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
  v14 = v13(a5, &GUID_2f13c006_a03a_5f69_b090_75a43e33423e, &v48);
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12F,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v14,
      v47);
    v15 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    goto LABEL_57;
  }
  LODWORD(v49) = 0;
  v16 = 0;
  v55 = 0;
  v17 = 0;
  v56 = 0;
  UserToken = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v48 + 56LL))(v48, &v49);
  if ( UserToken < 0 )
  {
    v21 = 309;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)UserToken,
      v47);
LABEL_10:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    v12 = UserToken;
    goto LABEL_63;
  }
  if ( !(_DWORD)v49 )
  {
LABEL_38:
    if ( *(_DWORD *)(a7 + 4)
      || (UserToken = DevPlat::Shared::GetRPCClientProcessId((DevPlat::Shared *)(a7 + 4), v18), UserToken >= 0) )
    {
      v53 = 0;
      UserToken = ApplicationActivationImpl::GetUserToken(v19, v8, &v53);
      if ( UserToken >= 0 )
      {
        Parameter = 0;
        InitOnceExecuteOnce(
          &ApplicationActivationImpl::s_activationBrokerInitOnce,
          lambda_35ab20b8c7d896d226e8e5809c686a22_::_lambda_invoker_cdecl_,
          &Parameter,
          0);
        UserToken = Parameter;
        if ( Parameter >= 0 )
        {
          v52 = 0;
          hObject = 0;
          v41 = ApplicationActivationImpl::s_activationBrokerManager;
          v42 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int128 *))(*(_QWORD *)ApplicationActivationImpl::s_activationBrokerManager
                                                                              + 24LL);
          WindowsGetStringRawBuffer(v58, 0);
          v59 = *(_OWORD *)v59;
          v33 = v42(v41, *(unsigned int *)(a7 + 4), *(unsigned int *)(v61 + 8), &v59);
          CloseHandle(hObject);
          if ( v33 >= 0 )
          {
            AAMTraceProvider::ActivateApplicationForPlugin::Stop(
              (AAMTraceProvider::ActivateApplicationForPlugin *)v62,
              v52);
            if ( v17 )
              tlx::_delete_array<Windows::Internal::String>(v17);
            if ( v16 )
              operator delete(v16, v45);
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
            v12 = 0;
            goto LABEL_63;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x171,
            (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
            (const char *)(unsigned int)v33,
            0);
          if ( v17 )
            tlx::_delete_array<Windows::Internal::String>(v17);
          if ( v16 )
            operator delete(v16, v43);
          v44 = v48;
          if ( v48 )
          {
            v48 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
          }
          goto LABEL_56;
        }
        v40 = 350;
      }
      else
      {
        v40 = 332;
      }
    }
    else
    {
      v40 = 328;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v40,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)UserToken,
      v47);
    if ( v17 )
      tlx::_delete_array<Windows::Internal::String>(v17);
    if ( v16 )
LABEL_29:
      operator delete(v16, v35);
    goto LABEL_10;
  }
  v22 = 8LL * (unsigned int)v49;
  if ( !is_mul_ok((unsigned int)v49, 8u) )
    v22 = -1;
  v23 = operator new[](v22, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v23;
  if ( !v23 )
  {
    UserToken = -2147024882;
    v21 = 313;
    goto LABEL_9;
  }
  v55 = v23;
  v24 = (unsigned int)v49;
  v25 = 8LL * (unsigned int)v49;
  if ( !is_mul_ok((unsigned int)v49, 8u) )
    v25 = -1;
  v26 = __CFADD__(v25, 8);
  v27 = v25 + 8;
  if ( v26 )
    v27 = -1;
  v28 = operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
  if ( v28
    && (*v28 = v24,
        v17 = (char *)(v28 + 1),
        `eh vector constructor iterator'(
          v28 + 1,
          8u,
          (unsigned int)v24,
          (void (*)(void *))Windows::Internal::String::String,
          (void (*)(void *))Windows::Internal::String::~String),
        v17) )
  {
    v56 = v17;
    for ( i = 0; ; ++i )
    {
      if ( i >= (unsigned int)v49 )
      {
        v8 = v57;
        goto LABEL_38;
      }
      string = 0;
      v30 = v48;
      v31 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v48 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v32 = v31(v30, i, &string);
      v33 = v32;
      if ( v32 < 0 )
        break;
      v34 = WindowsGetStringRawBuffer(string, 0);
      if ( !v34 )
      {
        UserToken = -2147467261;
LABEL_28:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x141,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
          (const char *)(unsigned int)UserToken,
          v47);
        WindowsDeleteString(string);
        string = 0;
        tlx::_delete_array<Windows::Internal::String>(v17);
        goto LABEL_29;
      }
      UserToken = Windows::Internal::String::_InitializeHelper((Windows::Internal::String *)&v17[8 * i], v34);
      if ( UserToken < 0 )
        goto LABEL_28;
      *((_QWORD *)v16 + i) = WindowsGetStringRawBuffer(*(HSTRING *)&v17[8 * i], 0);
      WindowsDeleteString(string);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)(unsigned int)v32,
      v47);
    WindowsDeleteString(string);
    string = 0;
    tlx::_delete_array<Windows::Internal::String>(v17);
    operator delete(v16, v36);
    v37 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
  }
  else
  {
    v33 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13B,
      (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\applicationactivationimpl.cpp",
      (const char *)0x8007000ELL,
      v47);
    operator delete(v16, v38);
    v39 = v48;
    if ( v48 )
    {
      v48 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
    }
  }
LABEL_56:
  v12 = v33;
LABEL_57:
  v62[0] = &AAMTraceProvider::ActivateApplicationForPlugin::`vftable';
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v62);
  wil::ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<AAMTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v62);
  return v12;
}

```

## disassembly

```asm
0x180036ee0  push    rbp
0x180036ee2  push    rbx
0x180036ee3  push    rsi
0x180036ee4  push    rdi
0x180036ee5  push    r12
0x180036ee7  push    r13
0x180036ee9  push    r14
0x180036eeb  push    r15
0x180036eed  lea     rbp, [rsp-148h]
0x180036ef5  sub     rsp, 248h
0x180036efc  mov     rax, cs:__security_cookie
0x180036f03  xor     rax, rsp
0x180036f06  mov     [rbp+180h+var_50], rax
0x180036f0d  mov     r12, r9
0x180036f10  mov     qword ptr [rbp+180h+var_1C0], r9
0x180036f14  mov     [rbp+180h+var_1C8], r8
0x180036f18  mov     r14, rdx
0x180036f1b  mov     [rbp+180h+var_1D0], rdx
0x180036f1f  mov     rdi, rcx
0x180036f22  mov     rsi, [rbp+180h+arg_20]
0x180036f29  mov     rcx, [rbp+180h+arg_28]
0x180036f30  mov     [rbp+180h+var_1B0], rcx
0x180036f34  mov     r15, [rbp+180h+arg_30]
0x180036f3b  mov     [rbp+180h+var_1A8], r15
0x180036f3f  xor     edx, edx; length
0x180036f41  mov     rcx, r8; string
0x180036f44  call    cs:__imp_WindowsGetStringRawBuffer
0x180036f4a  mov     rbx, rax
0x180036f4d  lea     rdx, aActivateapplic_0
0x180036f54  lea     rcx, [rbp+180h+var_1A0]
0x180036f58  call    ??0?$ActivityBase@VAAMTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z
0x180036f5d  lea     rax, ??_7ActivateApplicationForPlugin@AAMTraceProvider@@6B@
0x180036f64  mov     [rbp+180h+var_1A0], rax
0x180036f68  mov     r8, r12; struct _GUID *
0x180036f6b  mov     rdx, rbx; unsigned __int16 *
0x180036f6e  lea     rcx, [rbp+180h+var_1A0]; this
0x180036f72  call    ?StartActivity@ActivateApplicationForPlugin@AAMTraceProvider@@QEAAXPEBGAEBU_GUID@@@Z
0x180036f77  nop
0x180036f78  lea     rcx, [rdi-20h]; this
0x180036f7c  call    ?CheckCallerCapabilities@ApplicationActivationImpl@@AEAAJXZ
0x180036f81  mov     ebx, eax
0x180036f83  test    eax, eax
0x180036f85  jns     short loc_180036FA7
0x180036f87  mov     rcx, [rbp+188h]; this
0x180036f8e  mov     r9d, eax; char *
0x180036f91  lea     r8, aOnecoreuapBase_12
0x180036f98  mov     edx, 12Bh; void *
0x180036f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180036fa2  jmp     loc_180037492
0x180036fa7  mov     [rsp+280h+var_210], 0
0x180036fb0  mov     rax, [rsi]
0x180036fb3  mov     rbx, [rax]
0x180036fb6  lea     rcx, [rsp+280h+var_210]
0x180036fbb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180036fc0  lea     r8, [rsp+280h+var_210]
0x180036fc5  lea     rdx, _GUID_2f13c006_a03a_5f69_b090_75a43e33423e
0x180036fcc  mov     rcx, rsi
0x180036fcf  mov     rax, rbx
0x180036fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036fd7  mov     ebx, eax
0x180036fd9  xor     esi, esi
0x180036fdb  test    eax, eax
0x180036fdd  jns     short loc_18003701C
0x180036fdf  mov     rcx, [rbp+188h]; this
0x180036fe6  mov     r9d, eax; char *
0x180036fe9  lea     r8, aOnecoreuapBase_12
0x180036ff0  mov     edx, 12Fh; void *
0x180036ff5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180036ffa  nop
0x180036ffb  mov     rcx, [rsp+280h+var_210]
0x180037000  test    rcx, rcx
0x180037003  jz      short loc_180037017
0x180037005  mov     [rsp+280h+var_210], rsi
0x18003700a  mov     rax, [rcx]
0x18003700d  mov     rax, [rax+10h]
0x180037011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037016  nop
0x180037017  jmp     loc_18003743E
0x18003701c  mov     dword ptr [rsp+280h+var_208], esi
0x180037020  mov     rbx, rsi
0x180037023  mov     [rbp+180h+var_1E0], rbx
0x180037027  mov     r12, rsi
0x18003702a  mov     [rbp+180h+var_1D8], rsi
0x18003702e  mov     rcx, [rsp+280h+var_210]
0x180037033  mov     rax, [rcx]
0x180037036  lea     rdx, [rsp+280h+var_208]
0x18003703b  mov     rax, [rax+38h]
0x18003703f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037044  mov     edi, eax
0x180037046  test    eax, eax
0x180037048  jns     short loc_180037077
0x18003704a  mov     edx, 135h; void *
0x18003704f  lea     r8, aOnecoreuapBase_12
0x180037056  mov     r9d, edi; char *
0x180037059  mov     rcx, [rbp+188h]; this
0x180037060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180037065  nop
0x180037066  lea     rcx, [rsp+280h+var_210]
0x18003706b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ
0x180037070  mov     ebx, edi
0x180037072  jmp     loc_180037492
0x180037077  mov     eax, dword ptr [rsp+280h+var_208]
0x18003707b  test    eax, eax
0x18003707d  jz      loc_1800372AD
0x180037083  mov     ecx, eax
0x180037085  mov     r14d, 8
0x18003708b  mov     eax, r14d
0x18003708e  mul     rcx
0x180037091  lea     r12, [r14-9]
0x180037095  cmovb   rax, r12
0x180037099  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800370a0  mov     rcx, rax; unsigned __int64
0x1800370a3  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z
0x1800370a8  mov     rbx, rax
0x1800370ab  test    rax, rax
0x1800370ae  jz      loc_18003729A
0x1800370b4  mov     [rbp+180h+var_1E0], rax
0x1800370b8  mov     edi, dword ptr [rsp+280h+var_208]
0x1800370bc  mov     eax, r14d
0x1800370bf  mul     rdi
0x1800370c2  cmovb   rax, r12
0x1800370c6  add     rax, r14
0x1800370c9  cmovb   rax, r12
0x1800370cd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800370d4  mov     rcx, rax; unsigned __int64
0x1800370d7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z
0x1800370dc  test    rax, rax
0x1800370df  jz      loc_18003724F
0x1800370e5  mov     [rax], rdi
0x1800370e8  lea     r12, [rax+8]
0x1800370ec  lea     rax, ??1String@Internal@Windows@@QEAA@XZ
0x1800370f3  mov     [rsp+280h+var_260], rax; int
0x1800370f8  lea     r9, ??0String@Internal@Windows@@QEAA@XZ; void (*)(void *)
0x1800370ff  mov     r8d, edi; unsigned __int64
0x180037102  mov     edx, r14d; unsigned __int64
0x180037105  mov     rcx, r12; void *
0x180037108  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z
0x18003710d  test    r12, r12
0x180037110  jz      loc_18003724F
0x180037116  mov     [rbp+180h+var_1D8], r12
0x18003711a  mov     r14d, esi
0x18003711d  cmp     r14d, dword ptr [rsp+280h+var_208]
0x180037122  jnb     loc_1800372A9
0x180037128  mov     [rbp+180h+string], rsi
0x18003712c  mov     rsi, [rsp+280h+var_210]
0x180037131  mov     rax, [rsi]
0x180037134  mov     rdi, [rax+30h]
0x180037138  xor     ecx, ecx; string
0x18003713a  call    cs:__imp_WindowsDeleteString
0x180037140  xor     r13d, r13d
0x180037143  mov     [rbp+180h+string], r13
0x180037147  lea     r8, [rbp+180h+string]
0x18003714b  mov     edx, r14d
0x18003714e  mov     rcx, rsi
0x180037151  mov     rax, rdi
0x180037154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037159  mov     edi, eax
0x18003715b  test    eax, eax
0x18003715d  js      loc_1800371F2
0x180037163  xor     edx, edx; length
0x180037165  mov     rcx, [rbp+180h+string]; string
0x180037169  call    cs:__imp_WindowsGetStringRawBuffer
0x18003716f  test    rax, rax
0x180037172  jz      short loc_1800371AD
0x180037174  mov     esi, r14d
0x180037177  lea     rcx, [r12+rsi*8]; this
0x18003717b  mov     rdx, rax; unsigned __int16 *
0x18003717e  call    ?_InitializeHelper@String@Internal@Windows@@AEAAJPEBG@Z
0x180037183  mov     edi, eax
0x180037185  test    eax, eax
0x180037187  js      short loc_1800371B2
0x180037189  xor     edx, edx; length
0x18003718b  mov     rcx, [r12+rsi*8]; string
0x18003718f  call    cs:__imp_WindowsGetStringRawBuffer
0x180037195  mov     [rbx+rsi*8], rax
0x180037199  mov     rcx, [rbp+180h+string]; string
0x18003719d  call    cs:__imp_WindowsDeleteString
0x1800371a3  inc     r14d
0x1800371a6  xor     esi, esi
0x1800371a8  jmp     loc_18003711D
0x1800371ad  mov     edi, 80004003h
0x1800371b2  mov     rcx, [rbp+188h]; this
0x1800371b9  mov     r9d, edi; char *
0x1800371bc  lea     r8, aOnecoreuapBase_12
0x1800371c3  mov     edx, 141h; void *
0x1800371c8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800371cd  nop
0x1800371ce  mov     rcx, [rbp+180h+string]; string
0x1800371d2  call    cs:__imp_WindowsDeleteString
0x1800371d8  mov     [rbp+180h+string], r13
0x1800371dc  mov     rcx, r12
0x1800371df  call    ??$_delete_array@VString@Internal@Windows@@@tlx@@YAXPEAVString@Internal@Windows@@@Z
0x1800371e4  nop
0x1800371e5  mov     rcx, rbx; void *
0x1800371e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x1800371ed  jmp     loc_180037066
0x1800371f2  mov     rcx, [rbp+188h]; this
0x1800371f9  mov     r9d, edi; char *
0x1800371fc  lea     r8, aOnecoreuapBase_12
0x180037203  mov     edx, 140h; void *
0x180037208  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18003720d  nop
0x18003720e  mov     rcx, [rbp+180h+string]; string
0x180037212  call    cs:__imp_WindowsDeleteString
0x180037218  mov     [rbp+180h+string], r13
0x18003721c  mov     rcx, r12
0x18003721f  call    ??$_delete_array@VString@Internal@Windows@@@tlx@@YAXPEAVString@Internal@Windows@@@Z
0x180037224  nop
0x180037225  mov     rcx, rbx; void *
0x180037228  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x18003722d  nop
0x18003722e  mov     rcx, [rsp+280h+var_210]
0x180037233  test    rcx, rcx
0x180037236  jz      short loc_18003724A
0x180037238  mov     [rsp+280h+var_210], r13
0x18003723d  mov     rax, [rcx]
0x180037240  mov     rax, [rax+10h]
0x180037244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037249  nop
0x18003724a  jmp     loc_18003743C
0x18003724f  mov     rcx, [rbp+188h]; this
0x180037256  mov     edi, 8007000Eh
0x18003725b  mov     r9d, edi; char *
0x18003725e  lea     r8, aOnecoreuapBase_12
0x180037265  mov     edx, 13Bh; void *
0x18003726a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18003726f  nop
0x180037270  mov     rcx, rbx; void *
0x180037273  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z
0x180037278  nop
0x180037279  mov     rcx, [rsp+280h+var_210]
0x18003727e  test    rcx, rcx
0x180037281  jz      short loc_180037295
0x180037283  mov     [rsp+280h+var_210], rsi
0x180037288  mov     rax, [rcx]
0x18003728b  mov     rax, [rax+10h]
0x18003728f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037294  nop
0x180037295  jmp     loc_18003743C
0x18003729a  mov     edi, 8007000Eh
0x18003729f  mov     edx, 139h
0x1800372a4  jmp     loc_18003704F
0x1800372a9  mov     r14, [rbp+180h+var_1D0]
0x1800372ad  lea     r13, [r15+4]
0x1800372b1  cmp     [r13+0], esi
0x1800372b5  jnz     short loc_1800372FD
0x1800372b7  mov     rcx, r13; this
0x1800372ba  call    ?GetRPCClientProcessId@Shared@DevPlat@@YAJPEAK@Z
0x1800372bf  mov     edi, eax
0x1800372c1  test    eax, eax
0x1800372c3  jns     short loc_1800372FD
0x1800372c5  mov     edx, 148h; void *
0x1800372ca  lea     r8, aOnecoreuapBase_12
0x1800372d1  mov     r9d, edi; char *
0x1800372d4  mov     rcx, [rbp+188h]; this
0x1800372db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800372e0  nop
0x1800372e1  test    r12, r12
0x1800372e4  jz      short loc_1800372EF
0x1800372e6  mov     rcx, r12
0x1800372e9  call    ??$_delete_array@VString@Internal@Windows@@@tlx@@YAXPEAVString@Internal@Windows@@@Z
0x1800372ee  nop
0x1800372ef  test    rbx, rbx
0x1800372f2  jz      loc_180037066
0x1800372f8  jmp     loc_1800371E5
0x1800372fd  mov     [rbp+180h+var_1F0], rsi
0x180037301  lea     r8, [rbp+180h+var_1F0]; unsigned __int64 *
0x180037305  mov     rdx, r14; struct IInspectable *
0x180037308  call    ?GetUserToken@ApplicationActivationImpl@@AEAAJPEAUIInspectable@@PEA_K@Z
0x18003730d  mov     edi, eax
0x18003730f  test    eax, eax
0x180037311  jns     short loc_18003731A
0x180037313  mov     edx, 14Ch
0x180037318  jmp     short loc_1800372CA
0x18003731a  mov     [rbp+180h+Parameter], esi
0x18003731d  xor     r9d, r9d; Context
0x180037320  lea     r8, [rbp+180h+Parameter]; Parameter
0x180037324  lea     rdx, _lambda_35ab20b8c7d896d226e8e5809c686a22____lambda_invoker_cdecl_; InitFn
0x18003732b  lea     rcx, ?s_activationBrokerInitOnce@ApplicationActivationImpl@@0T_RTL_RUN_ONCE@@A; InitOnce
0x180037332  call    cs:__imp_InitOnceExecuteOnce
0x180037338  mov     edi, [rbp+180h+Parameter]
0x18003733b  test    edi, edi
0x18003733d  jns     short loc_180037346
0x18003733f  mov     edx, 15Eh
0x180037344  jmp     short loc_1800372CA
0x180037346  mov     [rbp+180h+var_1F4], esi
0x180037349  mov     [rbp+180h+hObject], rsi
0x18003734d  mov     r15, cs:?s_activationBrokerManager@ApplicationActivationImpl@@0V?$ComPtr@UIActivationBrokerManager@@@WRL@Microsoft@@A
0x180037354  mov     rax, [r15]
0x180037357  mov     r14, [rax+18h]
0x18003735b  mov     rdi, [rbp+180h+var_1F0]
0x18003735f  mov     esi, dword ptr [rsp+280h+var_208]
0x180037363  xor     edx, edx; length
0x180037365  mov     rcx, [rbp+180h+var_1C8]; string
0x180037369  call    cs:__imp_WindowsGetStringRawBuffer
0x18003736f  mov     rcx, qword ptr [rbp+180h+var_1C0]
0x180037373  movups  xmm0, xmmword ptr [rcx]
0x180037376  movdqu  [rbp+180h+var_1C0], xmm0
0x18003737b  lea     rcx, [rbp+180h+hObject]
0x18003737f  mov     [rsp+280h+var_220], rcx
  ... truncated ...
```
