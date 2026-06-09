# Windows::Internal::Shell::TryShellActivateApplicationAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)

- ea: `0x18002d380`
- end: `0x18002d6d7`
- name: `?TryShellActivateApplicationAsync@Shell@Internal@Windows@@YAJPEBG0PEAUIPropertySet@Collections@Foundation@3@0UWindowId@WindowManagement@ApplicationModel@23@_KPEAPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@63@$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@@Z`
- size: `855`
- prototype: `__int64 __usercall@<rax>(PCNZWCH sourceString@<rcx>, PCNZWCH@<rdx>, int, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800274dc`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000c964`
- `0x18002080c`
- `0x1800213d4`
- `0x180021850`
- `0x180021c50`
- `0x1800227a0`
- `0x18002a71c`
- `0x18002d380`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d688`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d698`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d533`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d688`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002d698`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d502`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d4b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002d502`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::Shell::TryShellActivateApplicationAsync(
        PCNZWCH sourceString,
        PCNZWCH a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8)
{
  __int64 v11; // r9
  __int64 v12; // rdi
  __int64 v13; // rdx
  int v14; // edi
  HRESULT v15; // eax
  unsigned __int64 v16; // r9
  __int64 v17; // rdx
  HSTRING v18; // rdi
  HSTRING v19; // r14
  __int64 v20; // r8
  __int64 v21; // r8
  HSTRING string; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+54h] [rbp-ACh]
  void **v27; // [rsp+60h] [rbp-A0h] BYREF
  int v28; // [rsp+68h] [rbp-98h] BYREF
  char v29; // [rsp+6Ch] [rbp-94h]
  int v30; // [rsp+90h] [rbp-70h] BYREF
  const char *v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  char v33; // [rsp+A8h] [rbp-58h]
  int v34; // [rsp+B0h] [rbp-50h]
  _BYTE v35[152]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v36; // [rsp+150h] [rbp+50h]
  int v37; // [rsp+160h] [rbp+60h]
  __int64 v38; // [rsp+168h] [rbp+68h]
  int *v39; // [rsp+170h] [rbp+70h]
  __int64 v40; // [rsp+178h] [rbp+78h]
  __int64 v41; // [rsp+180h] [rbp+80h]
  void ***v42; // [rsp+188h] [rbp+88h]
  __int64 v43; // [rsp+190h] [rbp+90h]
  int v44; // [rsp+198h] [rbp+98h]
  int *v45; // [rsp+1A0h] [rbp+A0h]
  char v46; // [rsp+1A8h] [rbp+A8h]
  _BYTE v47[112]; // [rsp+1B0h] [rbp+B0h] BYREF
  __int64 v48; // [rsp+220h] [rbp+120h]
  char v49; // [rsp+228h] [rbp+128h]
  _BYTE v50[128]; // [rsp+230h] [rbp+130h] BYREF
  HSTRING v51; // [rsp+2B0h] [rbp+1B0h]
  char v52; // [rsp+2B8h] [rbp+1B8h]
  HSTRING v53; // [rsp+2C0h] [rbp+1C0h]
  char v54; // [rsp+2C8h] [rbp+1C8h]
  __int64 v55; // [rsp+2D0h] [rbp+1D0h]
  __int64 v56; // [rsp+2D8h] [rbp+1D8h]
  char v57; // [rsp+2E0h] [rbp+1E0h]
  int v58; // [rsp+2E8h] [rbp+1E8h]
  __int64 v59; // [rsp+2F0h] [rbp+1F0h]
  void **v60; // [rsp+2F8h] [rbp+1F8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+488h] [rbp+388h]

  *a7 = 0;
  v28 = 0;
  v29 = 0;
  v33 = 0;
  v30 = 0;
  v31 = "ShellActivateApplication";
  v32 = 0;
  v34 = 0;
  v36 = 0;
  memset_0(v35, 0, sizeof(v35));
  v37 = 1;
  v38 = 0;
  v39 = &v28;
  v40 = 0;
  v41 = 0;
  v42 = &v27;
  v43 = 0;
  v44 = 0;
  v45 = &v30;
  v46 = 0;
  v27 = &Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::`vftable';
  LOBYTE(v11) = a3 != 0;
  Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::StartActivity(
    &v27,
    sourceString,
    a2,
    v11);
  v12 = -1;
  v13 = -1;
  do
    ++v13;
  while ( sourceString[v13] );
  string = 0;
  WindowsCreateString(sourceString, v13, &string);
  if ( !string )
  {
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x157,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
      (const char *)0x8007000ELL,
      0);
LABEL_11:
    if ( string )
      WindowsDeleteString(string);
    goto LABEL_24;
  }
  v24 = 0;
  if ( a2 )
  {
    do
      ++v12;
    while ( a2[v12] );
    v15 = WindowsCreateString(a2, v12, &v24);
    v14 = v15;
    if ( v15 < 0 )
    {
      v16 = (unsigned int)v15;
      v17 = 350;
      goto LABEL_9;
    }
  }
  wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,unsigned long *)>::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,unsigned long *)>(
    v47,
    a8);
  v49 = 0;
  v18 = string;
  string = 0;
  v19 = v24;
  v24 = 0;
  if ( a3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,unsigned long *)>::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,unsigned long *)>(
    v50,
    v47);
  v50[120] = 0;
  v49 = 1;
  v51 = v18;
  v52 = 0;
  v53 = v19;
  v54 = 0;
  v55 = a3;
  v56 = 0;
  v57 = 0;
  v58 = a5;
  v59 = a6;
  LOBYTE(v20) = v44 != 0;
  wil::ActivityBase<Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v60,
    &v27,
    v20);
  v60 = &Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::`vftable';
  v25 = 3;
  v26 = 128;
  v14 = Z::MakeAsyncOperation<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::PlatformExtensions::IShellActivationResult>,Windows::Internal::PlatformExtensions::IShellActivationResult *,Windows::Internal::ComTaskPoolHandler,`Windows::Internal::Shell::TryShellActivateApplicationAsync'::`2'::_lambda_1_,Windows::Foundation::Collections::AJPEBG0PEAUIPropertySet,Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::PlatformExtensions::IShellActivationResult>,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,unsigned long *)> &&>(
          &v25,
          a7,
          v21,
          v50);
  `Windows::Internal::Shell::TryShellActivateApplicationAsync'::`2'::_lambda_1_::~_lambda_1_(v50);
  if ( v48 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 24LL))(v48);
  if ( v14 < 0 )
  {
    v16 = (unsigned int)v14;
    v17 = 470;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\shellactivationhelpers.h",
      (const char *)v16,
      0);
    if ( v24 )
      WindowsDeleteString(v24);
    goto LABEL_11;
  }
  if ( v24 )
    WindowsDeleteString(v24);
  if ( string )
    WindowsDeleteString(string);
  v14 = 0;
LABEL_24:
  Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::~ShellActivateApplication((Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication *)&v27);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18002d380  mov     [rsp-8+arg_10], rbx
0x18002d385  push    rbp
0x18002d386  push    rsi
0x18002d387  push    rdi
0x18002d388  push    r12
0x18002d38a  push    r13
0x18002d38c  push    r14
0x18002d38e  push    r15
0x18002d390  lea     rbp, [rsp-350h]
0x18002d398  sub     rsp, 450h
0x18002d39f  mov     rax, cs:__security_cookie
0x18002d3a6  xor     rax, rsp
0x18002d3a9  mov     [rbp+380h+var_38], rax
0x18002d3b0  mov     rsi, r8
0x18002d3b3  mov     r14, rdx
0x18002d3b6  mov     r15, rcx
0x18002d3b9  mov     r13, [rbp+380h+arg_30]
0x18002d3c0  mov     r12, [rbp+380h+arg_38]
0x18002d3c7  xor     edi, edi
0x18002d3c9  mov     [r13+0], rdi
0x18002d3cd  mov     [rsp+480h+var_418], edi
0x18002d3d1  mov     [rsp+480h+var_414], dil
0x18002d3d6  mov     [rbp+380h+var_3D8], dil
0x18002d3da  mov     [rbp+380h+var_3F0], edi
0x18002d3dd  lea     rax, aShellactivatea; "ShellActivateApplication"
0x18002d3e4  mov     [rbp+380h+var_3E8], rax
0x18002d3e8  mov     [rbp+380h+var_3E0], rdi
0x18002d3ec  mov     [rbp+380h+var_3D0], edi
0x18002d3ef  xorps   xmm0, xmm0
0x18002d3f2  movdqa  [rbp+380h+var_330], xmm0
0x18002d3f7  xor     edx, edx; Val
0x18002d3f9  mov     r8d, 98h; Size
0x18002d3ff  lea     rcx, [rbp+380h+var_3C8]; void *
0x18002d403  call    memset_0
0x18002d408  mov     [rbp+380h+var_320], 1
0x18002d40f  xor     eax, eax
0x18002d411  mov     [rbp+380h+var_318], rax
0x18002d415  lea     rax, [rsp+480h+var_418]
0x18002d41a  mov     [rbp+380h+var_310], rax
0x18002d41e  mov     [rbp+380h+var_308], rdi
0x18002d422  mov     [rbp+380h+var_300], rdi
0x18002d429  lea     rax, [rsp+480h+var_420]
0x18002d42e  mov     [rbp+380h+var_2F8], rax
0x18002d435  mov     [rbp+380h+var_2F0], rdi
0x18002d43c  mov     [rbp+380h+var_2E8], edi
0x18002d442  lea     rax, [rbp+380h+var_3F0]
0x18002d446  mov     [rbp+380h+var_2E0], rax
0x18002d44d  mov     [rbp+380h+var_2D8], dil
0x18002d454  lea     rax, ??_7ShellActivateApplication@ShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@6B@; const Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::`vftable'
0x18002d45b  mov     [rsp+480h+var_420], rax
0x18002d460  test    rsi, rsi
0x18002d463  setnz   r9b
0x18002d467  mov     rax, [rbp+380h+arg_28]
0x18002d46e  mov     [rsp+480h+var_450], rax
0x18002d473  mov     ebx, [rbp+380h+arg_20]
0x18002d479  mov     [rsp+480h+var_458], ebx
0x18002d47d  mov     qword ptr [rsp+480h+var_460], rdi; int
0x18002d482  mov     r8, r14
0x18002d485  mov     rdx, r15
0x18002d488  lea     rcx, [rsp+480h+var_420]
0x18002d48d  call    ?StartActivity@ShellActivateApplication@ShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@QEAAXPEBG0_N0UWindowId@WindowManagement@ApplicationModel@56@_K@Z; Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::StartActivity(ushort const *,ushort const *,bool,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64)
0x18002d492  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002d496  mov     rdx, rdi
0x18002d499  xor     eax, eax
0x18002d49b  inc     rdx; length
0x18002d49e  cmp     [r15+rdx*2], ax
0x18002d4a3  jnz     short loc_18002D49B
0x18002d4a5  mov     [rsp+480h+string], rax
0x18002d4aa  lea     r8, [rsp+480h+string]; string
0x18002d4af  mov     rcx, r15; sourceString
0x18002d4b2  call    cs:__imp_WindowsCreateString
0x18002d4b8  xor     r15d, r15d
0x18002d4bb  cmp     [rsp+480h+string], r15
0x18002d4c0  jnz     short loc_18002D4E4
0x18002d4c2  mov     rcx, [rbp+388h]; this
0x18002d4c9  mov     edi, 8007000Eh
0x18002d4ce  mov     r9d, edi; char *
0x18002d4d1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x18002d4d8  mov     edx, 157h; void *
0x18002d4dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d4e2  jmp     short loc_18002D539
0x18002d4e4  mov     [rsp+480h+var_438], r15
0x18002d4e9  test    r14, r14
0x18002d4ec  jz      short loc_18002D552
0x18002d4ee  inc     rdi
0x18002d4f1  cmp     [r14+rdi*2], r15w
0x18002d4f6  jnz     short loc_18002D4EE
0x18002d4f8  lea     r8, [rsp+480h+var_438]; string
0x18002d4fd  mov     edx, edi; length
0x18002d4ff  mov     rcx, r14; sourceString
0x18002d502  call    cs:__imp_WindowsCreateString
0x18002d508  mov     edi, eax
0x18002d50a  test    eax, eax
0x18002d50c  jns     short loc_18002D552
0x18002d50e  mov     r9d, eax; char *
0x18002d511  mov     edx, 15Eh; void *
0x18002d516  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\shell"...
0x18002d51d  mov     rcx, [rbp+388h]; this
0x18002d524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002d529  mov     rcx, [rsp+480h+var_438]; string
0x18002d52e  test    rcx, rcx
0x18002d531  jz      short loc_18002D539
0x18002d533  call    cs:__imp_WindowsDeleteString
0x18002d539  mov     rcx, [rsp+480h+string]; string
0x18002d53e  test    rcx, rcx
0x18002d541  jz      loc_18002D6A1
0x18002d547  call    cs:__imp_WindowsDeleteString
0x18002d54d  jmp     loc_18002D6A1
0x18002d552  mov     rdx, r12
0x18002d555  lea     rcx, [rbp+380h+var_2D0]
0x18002d55c  call    ??0?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@QEAA@$$QEAV01@@Z; wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)>::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)>(wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)
0x18002d561  mov     [rbp+380h+var_258], r15b
0x18002d568  mov     rdi, [rsp+480h+string]
0x18002d56d  mov     [rsp+480h+string], r15
0x18002d572  mov     r14, [rsp+480h+var_438]
0x18002d577  mov     [rsp+480h+var_438], r15
0x18002d57c  test    rsi, rsi
0x18002d57f  jz      short loc_18002D591
0x18002d581  mov     rax, [rsi]
0x18002d584  mov     rcx, rsi
0x18002d587  mov     rax, [rax+8]
0x18002d58b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d590  nop
0x18002d591  lea     rdx, [rbp+380h+var_2D0]
0x18002d598  lea     rcx, [rbp+380h+var_250]
0x18002d59f  call    ??0?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@QEAA@$$QEAV01@@Z; wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)>::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)>(wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)
0x18002d5a4  mov     [rbp+380h+var_1D8], r15b
0x18002d5ab  mov     [rbp+380h+var_258], 1
0x18002d5b2  mov     [rbp+380h+var_1D0], rdi
0x18002d5b9  mov     [rbp+380h+var_1C8], r15b
0x18002d5c0  mov     [rbp+380h+var_1C0], r14
0x18002d5c7  mov     [rbp+380h+var_1B8], r15b
0x18002d5ce  mov     [rbp+380h+var_1B0], rsi
0x18002d5d5  mov     [rbp+380h+var_1A8], r15
0x18002d5dc  mov     [rbp+380h+var_1A0], r15b
0x18002d5e3  mov     [rbp+380h+var_198], ebx
0x18002d5e9  mov     rax, [rbp+380h+arg_28]
0x18002d5f0  mov     [rbp+380h+var_190], rax
0x18002d5f7  cmp     [rbp+380h+var_2E8], r15d
0x18002d5fe  setnz   r8b
0x18002d602  lea     rdx, [rsp+480h+var_420]
0x18002d607  lea     rcx, [rbp+380h+var_188]
0x18002d60e  call    ??0?$ActivityBase@VShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@$$QEAV01@_N@Z; wil::ActivityBase<Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(wil::ActivityBase<Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType> &&,bool)
0x18002d613  lea     rax, ??_7ShellActivateApplication@ShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@6B@; const Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::`vftable'
0x18002d61a  mov     [rbp+380h+var_188], rax
0x18002d621  mov     [rsp+480h+var_430], 3
0x18002d629  mov     [rsp+480h+var_42C], 80h
0x18002d632  lea     r9, [rbp+380h+var_250]
0x18002d639  mov     rdx, r13
0x18002d63c  lea     rcx, [rsp+480h+var_430]
0x18002d641  call    ??$MakeAsyncOperation@V?$CMarshaledInterfaceResult@UIShellActivationResult@PlatformExtensions@Internal@Windows@@@Internal@Windows@@PEAUIShellActivationResult@PlatformExtensions@23@VComTaskPoolHandler@23@V_lambda_1_@?1??TryShellActivateApplicationAsync@Shell@23@YAJPEBG0PEAUIPropertySet@Collections@Foundation@3@0UWindowId@WindowManagement@ApplicationModel@23@_KPEAPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@3@$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@@Z@@Internal@Windows@@YAJ$$QEAVComTaskPoolHandler@01@PEAPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@Foundation@1@W4TrustLevel@@$$QEAV_lambda_1_@?1??TryShellActivateApplicationAsync@Shell@01@YAJPEBG3PEAUIPropertySet@Collections@41@3UWindowId@WindowManagement@ApplicationModel@01@_K1$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@@Z@@Z; Windows::Internal::MakeAsyncOperation<Windows::Internal::CMarshaledInterfaceResult<Windows::Internal::PlatformExtensions::IShellActivationResult>,Windows::Internal::PlatformExtensions::IShellActivationResult *,Windows::Internal::ComTaskPoolHandler,`Windows::Internal::Shell::TryShellActivateApplicationAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)'::`2'::_lambda_1_>(Windows::Internal::ComTaskPoolHandler &&,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,TrustLevel,`Windows::Internal::Shell::TryShellActivateApplicationAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)'::`2'::_lambda_1_ &&)
0x18002d646  mov     edi, eax
0x18002d648  lea     rcx, [rbp+380h+var_250]
0x18002d64f  call    ??1_lambda_1_@?1??TryShellActivateApplicationAsync@Shell@Internal@Windows@@YAJPEBG0PEAUIPropertySet@Collections@Foundation@4@0UWindowId@WindowManagement@ApplicationModel@34@_KPEAPEAU?$IAsyncOperation@PEAUIShellActivationResult@PlatformExtensions@Internal@Windows@@@74@$$QEAV?$function@$$A6AJUActivationArguments@Shell@Internal@Windows@@PEAUIPropertySet@Collections@Foundation@4@UWindowId@WindowManagement@ApplicationModel@34@_KPEAK@Z@wistd@@@Z@QEAA@XZ; `Windows::Internal::Shell::TryShellActivateApplicationAsync(ushort const *,ushort const *,Windows::Foundation::Collections::IPropertySet *,ushort const *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::IShellActivationResult *> * *,wistd::function<long (Windows::Internal::Shell::ActivationArguments,Windows::Foundation::Collections::IPropertySet *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,unsigned __int64,ulong *)> &&)'::`2'::_lambda_1_::~_lambda_1_(void)
0x18002d654  nop
0x18002d655  mov     rcx, [rbp+380h+var_260]
0x18002d65c  test    rcx, rcx
0x18002d65f  jz      short loc_18002D66D
0x18002d661  mov     rax, [rcx]
0x18002d664  mov     rax, [rax+18h]
0x18002d668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d66d  test    edi, edi
0x18002d66f  jns     short loc_18002D67E
0x18002d671  mov     r9d, edi
0x18002d674  mov     edx, 1D6h
0x18002d679  jmp     loc_18002D516
0x18002d67e  mov     rcx, [rsp+480h+var_438]; string
0x18002d683  test    rcx, rcx
0x18002d686  jz      short loc_18002D68E
0x18002d688  call    cs:__imp_WindowsDeleteString
0x18002d68e  mov     rcx, [rsp+480h+string]; string
0x18002d693  test    rcx, rcx
0x18002d696  jz      short loc_18002D69E
0x18002d698  call    cs:__imp_WindowsDeleteString
0x18002d69e  mov     edi, r15d
0x18002d6a1  lea     rcx, [rsp+480h+var_420]; this
0x18002d6a6  call    ??1ShellActivateApplication@ShellActivationHelpersTelemetry@Details@Shell@Internal@Windows@@QEAA@XZ; Windows::Internal::Shell::Details::ShellActivationHelpersTelemetry::ShellActivateApplication::~ShellActivateApplication(void)
0x18002d6ab  mov     eax, edi
0x18002d6ad  mov     rcx, [rbp+380h+var_38]
0x18002d6b4  xor     rcx, rsp; StackCookie
0x18002d6b7  call    __security_check_cookie
0x18002d6bc  mov     rbx, [rsp+480h+arg_10]
0x18002d6c4  add     rsp, 450h
0x18002d6cb  pop     r15
0x18002d6cd  pop     r14
0x18002d6cf  pop     r13
0x18002d6d1  pop     r12
0x18002d6d3  pop     rdi
0x18002d6d4  pop     rsi
0x18002d6d5  pop     rbp
0x18002d6d6  retn
```
