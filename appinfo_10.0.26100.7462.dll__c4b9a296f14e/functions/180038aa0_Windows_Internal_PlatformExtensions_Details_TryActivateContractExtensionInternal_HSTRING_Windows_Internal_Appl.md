# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x180038aa0`
- end: `0x180038d82`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001107c`

## callees

- `0x180007c78`
- `0x180025b5c`
- `0x180026418`
- `0x180026cb8`
- `0x18002719c`
- `0x180027438`
- `0x1800371a4`
- `0x1800376a4`
- `0x180038aa0`
- `0x180038dec`
- `0x180044a20`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038b7e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180038b7e`

## string_xrefs

- `0x180038b31`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180038b97`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180038c14`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180038d07`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int64 v7; // r9
  char v8; // si
  unsigned __int16 *v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rax
  int ActivationFactory; // eax
  int v14; // eax
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  const struct _GUID *v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v21)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  int v25; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v26[40]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v27[42]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING__ v28[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v25 = a2;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v27);
  v27[0] = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    (__int64)v27,
    a1,
    a2,
    (__int64)&GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4);
  v7 = v27[34] + 8LL;
  *a4 = 0;
  v8 = 0;
  v10 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(a1, v28, v9, v7, v19);
  v11 = v10;
  if ( v10 >= 0 )
  {
    if ( LOWORD(v28[0].unused) )
    {
      v22 = 0;
      v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              (Microsoft::WRL::Wrappers::HStringReference *)v26,
              (unsigned __int16 (*)[128])v28);
      ActivationFactory = RoGetActivationFactory(
                            *(_QWORD *)(v12 + 24),
                            &GUID_00000035_0000_0000_c000_000000000046,
                            &v22);
      v11 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x242,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
          (const char *)(unsigned int)ActivationFactory,
          v20);
LABEL_6:
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v22);
        goto LABEL_23;
      }
      v21 = 0;
      v23 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v22)(
             v22,
             &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
             &v23) < 0 )
      {
        v16 = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v22 + 48LL))(
                v22,
                &v21);
        v11 = v16;
        if ( v16 < 0 )
        {
          v17 = 592;
          goto LABEL_20;
        }
      }
      else
      {
        v24 = 0;
        v8 = 1;
        v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
                &v24,
                &v25);
        v11 = v14;
        if ( v14 < 0 )
        {
          v15 = 587;
LABEL_10:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
            (const char *)(unsigned int)v14,
            v20);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v24);
LABEL_11:
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v21);
          goto LABEL_6;
        }
        v14 = (*(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v23 + 48LL))(
                v23,
                a1,
                v24,
                &v21);
        v11 = v14;
        if ( v14 < 0 )
        {
          v15 = 588;
          goto LABEL_10;
        }
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v24);
      }
      if ( v21 )
      {
        v16 = (**v21)(v21, &GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4, a4);
        v11 = v16;
        if ( v16 < 0 )
        {
          v17 = 600;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
            (const char *)(unsigned int)v16,
            v20);
          goto LABEL_11;
        }
      }
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v21);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v22);
    }
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v27,
      *a4 != 0,
      v8,
      (const unsigned __int16 *)v28);
    v11 = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
    (const char *)(unsigned int)v10,
    v20);
LABEL_23:
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v27);
  return v11;
}

```

## disassembly

```asm
0x180038aa0  push    rbp
0x180038aa2  push    rbx
0x180038aa3  push    rsi
0x180038aa4  push    rdi
0x180038aa5  push    r12
0x180038aa7  push    r14
0x180038aa9  push    r15
0x180038aab  lea     rbp, [rsp-1E0h]
0x180038ab3  sub     rsp, 2E0h
0x180038aba  mov     rax, cs:__security_cookie
0x180038ac1  xor     rax, rsp
0x180038ac4  mov     [rbp+210h+var_40], rax
0x180038acb  mov     r15, rcx
0x180038ace  mov     [rsp+310h+var_2C0], edx
0x180038ad2  lea     rcx, [rbp+210h+var_290]; struct wil::details::IFailureCallback *
0x180038ad6  mov     r14, r9
0x180038ad9  mov     ebx, edx
0x180038adb  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180038ae0  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x180038ae7  mov     r8d, ebx
0x180038aea  lea     r9, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x180038af1  mov     [rbp+210h+var_290], rax
0x180038af5  mov     rdx, r15
0x180038af8  lea     rcx, [rbp+210h+var_290]
0x180038afc  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x180038b01  mov     r9, [rbp+210h+var_180]
0x180038b08  lea     rdx, [rbp+210h+var_140]; HSTRING
0x180038b0f  xor     r12d, r12d
0x180038b12  add     r9, 8; unsigned __int64
0x180038b16  mov     rcx, r15; this
0x180038b19  mov     [r14], r12
0x180038b1c  mov     sil, r12b
0x180038b1f  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x180038b24  mov     ebx, eax
0x180038b26  test    eax, eax
0x180038b28  jns     short loc_180038B4A
0x180038b2a  mov     rcx, [rbp+218h]; this
0x180038b31  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180038b38  mov     r9d, eax; char *
0x180038b3b  mov     edx, 23Eh; void *
0x180038b40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038b45  jmp     loc_180038D55
0x180038b4a  cmp     word ptr [rbp+210h+var_140.unused], r12w
0x180038b52  jz      loc_180038D39
0x180038b58  lea     rdx, [rbp+210h+var_140]; unsigned __int16 (*)[128]
0x180038b5f  mov     [rsp+310h+var_2D8], r12
0x180038b64  lea     rcx, [rsp+310h+var_2B8]; this
0x180038b69  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x180038b6e  lea     r8, [rsp+310h+var_2D8]
0x180038b73  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180038b7a  mov     rcx, [rax+18h]
0x180038b7e  call    cs:__imp_RoGetActivationFactory
0x180038b85  nop     dword ptr [rax+rax+00h]
0x180038b8a  mov     ebx, eax
0x180038b8c  test    eax, eax
0x180038b8e  jns     short loc_180038BBA
0x180038b90  mov     rcx, [rbp+218h]; this
0x180038b97  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180038b9e  mov     r9d, eax; char *
0x180038ba1  mov     edx, 242h; void *
0x180038ba6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038bab  lea     rcx, [rsp+310h+var_2D8]
0x180038bb0  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038bb5  jmp     loc_180038D55
0x180038bba  mov     rcx, [rsp+310h+var_2D8]
0x180038bbf  lea     r8, [rsp+310h+var_2D0]
0x180038bc4  mov     [rsp+310h+var_2E0], r12
0x180038bc9  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x180038bd0  mov     [rsp+310h+var_2D0], r12
0x180038bd5  mov     rax, [rcx]
0x180038bd8  mov     rax, [rax]
0x180038bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038be0  shr     eax, 1Fh
0x180038be3  test    al, al
0x180038be5  jnz     loc_180038CC3
0x180038beb  lea     rdx, [rsp+310h+var_2C0]
0x180038bf0  mov     [rsp+310h+var_2C8], r12
0x180038bf5  lea     rcx, [rsp+310h+var_2C8]
0x180038bfa  mov     sil, 1
0x180038bfd  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x180038c02  mov     ebx, eax
0x180038c04  test    eax, eax
0x180038c06  jns     short loc_180038C46
0x180038c08  mov     edx, 24Bh; void *
0x180038c0d  mov     rcx, [rbp+218h]; this
0x180038c14  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180038c1b  mov     r9d, eax; char *
0x180038c1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038c23  lea     rcx, [rsp+310h+var_2C8]
0x180038c28  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038c2d  lea     rcx, [rsp+310h+var_2D0]
0x180038c32  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038c37  lea     rcx, [rsp+310h+var_2E0]
0x180038c3c  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038c41  jmp     loc_180038BAB
0x180038c46  mov     rbx, [rsp+310h+var_2D0]
0x180038c4b  mov     rcx, [rsp+310h+var_2E0]
0x180038c50  mov     rax, [rbx]
0x180038c53  mov     rdi, [rax+30h]
0x180038c57  test    rcx, rcx
0x180038c5a  jz      short loc_180038C68
0x180038c5c  mov     r8, [rcx]
0x180038c5f  mov     rax, [r8+10h]
0x180038c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c68  mov     r8, [rsp+310h+var_2C8]
0x180038c6d  lea     r9, [rsp+310h+var_2E0]
0x180038c72  mov     rdx, r15
0x180038c75  mov     rcx, rbx
0x180038c78  mov     rax, rdi
0x180038c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038c80  mov     ebx, eax
0x180038c82  test    eax, eax
0x180038c84  jns     short loc_180038C8D
0x180038c86  mov     edx, 24Ch
0x180038c8b  jmp     short loc_180038C0D
0x180038c8d  lea     rcx, [rsp+310h+var_2C8]
0x180038c92  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038c97  mov     rcx, [rsp+310h+var_2E0]
0x180038c9c  test    rcx, rcx
0x180038c9f  jz      short loc_180038D1B
0x180038ca1  mov     rax, [rcx]
0x180038ca4  lea     rdx, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x180038cab  mov     r8, r14
0x180038cae  mov     rax, [rax]
0x180038cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cb6  mov     ebx, eax
0x180038cb8  test    eax, eax
0x180038cba  jns     short loc_180038D1B
0x180038cbc  mov     edx, 258h
0x180038cc1  jmp     short loc_180038D00
0x180038cc3  mov     rbx, [rsp+310h+var_2D8]
0x180038cc8  mov     rcx, [rsp+310h+var_2E0]
0x180038ccd  mov     rax, [rbx]
0x180038cd0  mov     rdi, [rax+30h]
0x180038cd4  test    rcx, rcx
0x180038cd7  jz      short loc_180038CE5
0x180038cd9  mov     rdx, [rcx]
0x180038cdc  mov     rax, [rdx+10h]
0x180038ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038ce5  lea     rdx, [rsp+310h+var_2E0]
0x180038cea  mov     rcx, rbx
0x180038ced  mov     rax, rdi
0x180038cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038cf5  mov     ebx, eax
0x180038cf7  test    eax, eax
0x180038cf9  jns     short loc_180038C97
0x180038cfb  mov     edx, 250h; void *
0x180038d00  mov     rcx, [rbp+218h]; this
0x180038d07  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180038d0e  mov     r9d, eax; char *
0x180038d11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038d16  jmp     loc_180038C2D
0x180038d1b  lea     rcx, [rsp+310h+var_2D0]
0x180038d20  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038d25  lea     rcx, [rsp+310h+var_2E0]
0x180038d2a  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038d2f  lea     rcx, [rsp+310h+var_2D8]
0x180038d34  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038d39  cmp     [r14], r12
0x180038d3c  lea     r9, [rbp+210h+var_140]; unsigned __int16 *
0x180038d43  mov     r8b, sil; bool
0x180038d46  lea     rcx, [rbp+210h+var_290]; this
0x180038d4a  setnz   dl; bool
0x180038d4d  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x180038d52  mov     ebx, r12d
0x180038d55  lea     rcx, [rbp+210h+var_290]; this
0x180038d59  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x180038d5e  mov     eax, ebx
0x180038d60  mov     rcx, [rbp+210h+var_40]
0x180038d67  xor     rcx, rsp; StackCookie
0x180038d6a  call    __security_check_cookie
0x180038d6f  add     rsp, 2E0h
0x180038d76  pop     r15
0x180038d78  pop     r14
0x180038d7a  pop     r12
0x180038d7c  pop     rdi
0x180038d7d  pop     rsi
0x180038d7e  pop     rbx
0x180038d7f  pop     rbp
0x180038d80  retn
```
