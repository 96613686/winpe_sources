# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x140016a54`
- end: `0x140016db4`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `864`
- prototype: `__int64 __fastcall(HSTRING, unsigned int, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400115c4`
- `0x1400137d4`

## callees

- `0x140003620`
- `0x140005850`
- `0x140007d50`
- `0x140008e68`
- `0x140009734`
- `0x14000b47c`
- `0x1400136fc`
- `0x1400147dc`
- `0x1400151b0`
- `0x140016a54`
- `0x140017060`
- `0x14001f010`

## import_xrefs

- `KERNEL32!RaiseException` at `0x140016dad`
- `KERNEL32!RaiseException` at `0x140016dad`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140016b62`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x140016b62`

## string_xrefs

- `0x140016ae1`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x140016b75`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x140016be2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x140016cb1`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int64 v8; // r9
  unsigned __int16 *v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  bool v12; // bl
  unsigned __int64 v13; // r9
  int ActivationFactory; // eax
  int v15; // edi
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rdx
  int (__fastcall **v21)(_QWORD *, GUID *, __int64 **); // rax
  const struct _GUID *v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v24)(_QWORD, __int64, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v25; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v26; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h]
  _QWORD v31[42]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING__ sourceString; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v28 = a2;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v31);
  v31[0] = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    v31,
    a1,
    a2,
    a3);
  v8 = v31[34] + 8LL;
  *a4 = 0;
  v10 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
          a1,
          &sourceString,
          v9,
          v8,
          v22);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v10,
      v23);
LABEL_22:
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v31);
    return v11;
  }
  v12 = 0;
  if ( LOWORD(sourceString.unused) )
  {
    v25 = 0;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)&sourceString.unused + v13) );
    if ( v13 > 0xFFFFFFFF || (int)v13 + 1 < (unsigned int)v13 )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      JUMPOUT(0x140016DB3LL);
    }
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, (PCWSTR)&sourceString, v13 + 1, v13);
    ActivationFactory = RoGetActivationFactory(v30, &GUID_00000035_0000_0000_c000_000000000046, &v25);
    v15 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)ActivationFactory,
        v23);
LABEL_21:
      wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v25);
      v11 = v15;
      goto LABEL_22;
    }
    v24 = 0;
    v26 = 0;
    if ( (*(int (__fastcall **)(_QWORD *, GUID *, __int64 **))*v25)(
           v25,
           &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
           &v26) < 0 )
    {
      v21 = (int (__fastcall **)(_QWORD *, GUID *, __int64 **))*v25;
      v24 = 0;
      v15 = ((__int64 (__fastcall *)(_QWORD *, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))v21[6])(v25, &v24);
      if ( v15 < 0 )
      {
        v19 = 592;
        goto LABEL_20;
      }
    }
    else
    {
      v27 = 0;
      v16 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
              &v27,
              &v28);
      v11 = v16;
      if ( v16 < 0 )
      {
        v17 = 587;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v16,
          v23);
        wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v27);
        wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v26);
        wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v24);
        wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v25);
        goto LABEL_22;
      }
      v18 = *v26;
      v24 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(v18 + 48))(
              v26,
              a1,
              v27,
              &v24);
      v11 = v16;
      if ( v16 < 0 )
      {
        v17 = 588;
        goto LABEL_13;
      }
      v12 = 1;
      wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v27);
    }
    if ( v24 )
    {
      v15 = (**v24)(v24, a3, a4);
      if ( v15 < 0 )
      {
        v19 = 600;
LABEL_20:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v19,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v15,
          v23);
        wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v26);
        wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v24);
        goto LABEL_21;
      }
    }
    wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v26);
    wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v24);
    wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(&v25);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v31,
    *a4 != 0,
    v12,
    (const unsigned __int16 *)&sourceString);
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v31);
  return 0;
}

```

## disassembly

```asm
0x140016a54  push    rbp
0x140016a56  push    rbx
0x140016a57  push    rsi
0x140016a58  push    rdi
0x140016a59  push    r12
0x140016a5b  push    r14
0x140016a5d  push    r15
0x140016a5f  lea     rbp, [rsp-1E0h]
0x140016a67  sub     rsp, 2E0h
0x140016a6e  mov     rax, cs:__security_cookie
0x140016a75  xor     rax, rsp
0x140016a78  mov     [rbp+210h+var_40], rax
0x140016a7f  mov     rsi, rcx
0x140016a82  mov     [rsp+310h+var_2C0], edx
0x140016a86  lea     rcx, [rbp+210h+var_290]; struct wil::details::IFailureCallback *
0x140016a8a  mov     r14, r9
0x140016a8d  mov     r15, r8
0x140016a90  mov     ebx, edx
0x140016a92  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140016a97  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x140016a9e  mov     r9, r15
0x140016aa1  mov     r8d, ebx
0x140016aa4  mov     [rbp+210h+var_290], rax
0x140016aa8  mov     rdx, rsi
0x140016aab  lea     rcx, [rbp+210h+var_290]
0x140016aaf  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x140016ab4  mov     r9, [rbp+210h+var_180]
0x140016abb  lea     rdx, [rbp+210h+sourceString]; HSTRING
0x140016ac2  xor     r12d, r12d
0x140016ac5  add     r9, 8; unsigned __int64
0x140016ac9  mov     rcx, rsi; this
0x140016acc  mov     [r14], r12
0x140016acf  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x140016ad4  mov     ebx, eax
0x140016ad6  test    eax, eax
0x140016ad8  jns     short loc_140016AFA
0x140016ada  mov     rcx, [rbp+218h]; this
0x140016ae1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140016ae8  mov     r9d, eax; char *
0x140016aeb  mov     edx, 23Eh; void *
0x140016af0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016af5  jmp     loc_140016CE0
0x140016afa  mov     bl, r12b
0x140016afd  cmp     word ptr [rbp+210h+sourceString.unused], r12w
0x140016b05  jz      loc_140016D59
0x140016b0b  mov     [rsp+310h+var_2D8], r12
0x140016b10  lea     rax, [rbp+210h+sourceString]
0x140016b17  or      r9, 0FFFFFFFFFFFFFFFFh
0x140016b1b  inc     r9; unsigned int
0x140016b1e  cmp     [rax+r9*2], r12w
0x140016b23  jnz     short loc_140016B1B
0x140016b25  mov     eax, 0FFFFFFFFh
0x140016b2a  cmp     r9, rax
0x140016b2d  ja      loc_140016D9E
0x140016b33  lea     r8d, [r9+1]; unsigned int
0x140016b37  cmp     r8d, r9d
0x140016b3a  jb      loc_140016D9E
0x140016b40  lea     rdx, [rbp+210h+sourceString]; sourceString
0x140016b47  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x140016b4c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140016b51  mov     rcx, [rsp+310h+var_2A0]
0x140016b56  lea     r8, [rsp+310h+var_2D8]
0x140016b5b  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x140016b62  call    cs:__imp_RoGetActivationFactory
0x140016b68  mov     edi, eax
0x140016b6a  test    eax, eax
0x140016b6c  jns     short loc_140016B8E
0x140016b6e  mov     rcx, [rbp+218h]; this
0x140016b75  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140016b7c  mov     r9d, eax; char *
0x140016b7f  mov     edx, 242h; void *
0x140016b84  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016b89  jmp     loc_140016CD4
0x140016b8e  mov     rcx, [rsp+310h+var_2D8]
0x140016b93  lea     r8, [rsp+310h+var_2D0]
0x140016b98  mov     [rsp+310h+var_2E0], r12
0x140016b9d  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x140016ba4  mov     [rsp+310h+var_2D0], r12
0x140016ba9  mov     rax, [rcx]
0x140016bac  mov     rax, [rax]
0x140016baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016bb4  test    eax, eax
0x140016bb6  js      loc_140016CF0
0x140016bbc  lea     rdx, [rsp+310h+var_2C0]
0x140016bc1  mov     [rsp+310h+var_2C8], r12
0x140016bc6  lea     rcx, [rsp+310h+var_2C8]
0x140016bcb  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x140016bd0  mov     ebx, eax
0x140016bd2  test    eax, eax
0x140016bd4  jns     short loc_140016C1E
0x140016bd6  mov     edx, 24Bh; void *
0x140016bdb  mov     rcx, [rbp+218h]; this
0x140016be2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140016be9  mov     r9d, eax; char *
0x140016bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016bf1  lea     rcx, [rsp+310h+var_2C8]
0x140016bf6  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016bfb  lea     rcx, [rsp+310h+var_2D0]
0x140016c00  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016c05  lea     rcx, [rsp+310h+var_2E0]
0x140016c0a  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016c0f  lea     rcx, [rsp+310h+var_2D8]
0x140016c14  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016c19  jmp     loc_140016CE0
0x140016c1e  mov     rcx, [rsp+310h+var_2E0]
0x140016c23  mov     rbx, [rsp+310h+var_2D0]
0x140016c28  mov     rax, [rbx]
0x140016c2b  mov     [rsp+310h+var_2E0], r12
0x140016c30  mov     rdi, [rax+30h]
0x140016c34  test    rcx, rcx
0x140016c37  jz      short loc_140016C45
0x140016c39  mov     r8, [rcx]
0x140016c3c  mov     rax, [r8+10h]
0x140016c40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c45  mov     r8, [rsp+310h+var_2C8]
0x140016c4a  lea     r9, [rsp+310h+var_2E0]
0x140016c4f  mov     rdx, rsi
0x140016c52  mov     rcx, rbx
0x140016c55  mov     rax, rdi
0x140016c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c5d  mov     ebx, eax
0x140016c5f  test    eax, eax
0x140016c61  jns     short loc_140016C6D
0x140016c63  mov     edx, 24Ch
0x140016c68  jmp     loc_140016BDB
0x140016c6d  lea     rcx, [rsp+310h+var_2C8]
0x140016c72  mov     ebx, 1
0x140016c77  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016c7c  mov     rcx, [rsp+310h+var_2E0]
0x140016c81  test    rcx, rcx
0x140016c84  jz      loc_140016D3B
0x140016c8a  mov     rax, [rcx]
0x140016c8d  mov     r8, r14
0x140016c90  mov     rdx, r15
0x140016c93  mov     rax, [rax]
0x140016c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016c9b  mov     edi, eax
0x140016c9d  test    eax, eax
0x140016c9f  jns     loc_140016D3B
0x140016ca5  mov     edx, 258h; void *
0x140016caa  mov     rcx, [rbp+218h]; this
0x140016cb1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x140016cb8  mov     r9d, edi; char *
0x140016cbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140016cc0  lea     rcx, [rsp+310h+var_2D0]
0x140016cc5  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016cca  lea     rcx, [rsp+310h+var_2E0]
0x140016ccf  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016cd4  lea     rcx, [rsp+310h+var_2D8]
0x140016cd9  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016cde  mov     ebx, edi
0x140016ce0  lea     rcx, [rbp+210h+var_290]; this
0x140016ce4  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x140016ce9  mov     eax, ebx
0x140016ceb  jmp     loc_140016D7D
0x140016cf0  mov     rcx, [rsp+310h+var_2E0]
0x140016cf5  mov     rdi, [rsp+310h+var_2D8]
0x140016cfa  mov     rax, [rdi]
0x140016cfd  mov     [rsp+310h+var_2E0], r12
0x140016d02  mov     rsi, [rax+30h]
0x140016d06  test    rcx, rcx
0x140016d09  jz      short loc_140016D17
0x140016d0b  mov     rdx, [rcx]
0x140016d0e  mov     rax, [rdx+10h]
0x140016d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d17  lea     rdx, [rsp+310h+var_2E0]
0x140016d1c  mov     rcx, rdi
0x140016d1f  mov     rax, rsi
0x140016d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140016d27  mov     edi, eax
0x140016d29  test    eax, eax
0x140016d2b  jns     loc_140016C7C
0x140016d31  mov     edx, 250h
0x140016d36  jmp     loc_140016CAA
0x140016d3b  lea     rcx, [rsp+310h+var_2D0]
0x140016d40  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016d45  lea     rcx, [rsp+310h+var_2E0]
0x140016d4a  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016d4f  lea     rcx, [rsp+310h+var_2D8]
0x140016d54  call    ??1?$com_ptr_t@UIInspectable@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IInspectable,wil::err_returncode_policy>::~com_ptr_t<IInspectable,wil::err_returncode_policy>(void)
0x140016d59  cmp     [r14], r12
0x140016d5c  lea     r9, [rbp+210h+sourceString]; unsigned __int16 *
0x140016d63  mov     r8b, bl; bool
0x140016d66  lea     rcx, [rbp+210h+var_290]; this
0x140016d6a  setnz   dl; bool
0x140016d6d  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x140016d72  lea     rcx, [rbp+210h+var_290]; this
0x140016d76  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x140016d7b  xor     eax, eax
0x140016d7d  mov     rcx, [rbp+210h+var_40]
0x140016d84  xor     rcx, rsp; StackCookie
0x140016d87  call    __security_check_cookie
0x140016d8c  add     rsp, 2E0h
0x140016d93  pop     r15
0x140016d95  pop     r14
0x140016d97  pop     r12
0x140016d99  pop     rdi
0x140016d9a  pop     rsi
0x140016d9b  pop     rbx
0x140016d9c  pop     rbp
0x140016d9d  retn
0x140016d9e  xor     r9d, r9d; lpArguments
0x140016da1  xor     r8d, r8d; nNumberOfArguments
0x140016da4  mov     ecx, 80070216h; dwExceptionCode
0x140016da9  lea     edx, [r9+1]; dwExceptionFlags
0x140016dad  call    cs:__imp_RaiseException
```
