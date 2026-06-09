# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x18003b4c4`
- end: `0x18003b7af`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `747`
- prototype: `__int64 __fastcall(HSTRING, unsigned int, __int64, _QWORD *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000d974`

## callees

- `0x18000720c`
- `0x180029c9c`
- `0x18002a4b8`
- `0x18002ab64`
- `0x18002af7c`
- `0x18002b1ec`
- `0x180039900`
- `0x18003a098`
- `0x18003b4c4`
- `0x18003b818`
- `0x180046e50`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003b5a3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003b5a3`

## string_xrefs

- `0x18003b553`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18003b5b6`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18003b62d`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x18003b730`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int64 v7; // r9
  unsigned __int16 *v8; // r8
  int v9; // eax
  unsigned int v10; // ebx
  bool v11; // di
  __int64 v12; // rax
  int ActivationFactory; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rdx
  int (__fastcall **v19)(_QWORD *, GUID *, __int64 **); // rax
  const struct _GUID *v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v23)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v25; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v27; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v28[40]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v29[42]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING__ v30[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v27 = a2;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v29);
  v29[0] = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    v29,
    a1,
    a2,
    &GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4);
  v7 = v29[34] + 8LL;
  *a4 = 0;
  v9 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(a1, v30, v8, v7, v21);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v11 = 0;
    if ( LOWORD(v30[0].unused) )
    {
      v24 = 0;
      v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
              (Microsoft::WRL::Wrappers::HStringReference *)v28,
              (unsigned __int16 (*)[128])v30);
      ActivationFactory = RoGetActivationFactory(
                            *(_QWORD *)(v12 + 24),
                            &GUID_00000035_0000_0000_c000_000000000046,
                            &v24);
      v10 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x242,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
          (const char *)(unsigned int)ActivationFactory,
          v22);
LABEL_6:
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v24);
        goto LABEL_23;
      }
      v23 = 0;
      v25 = 0;
      if ( (*(int (__fastcall **)(_QWORD *, GUID *, __int64 **))*v24)(
             v24,
             &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
             &v25) < 0 )
      {
        v19 = (int (__fastcall **)(_QWORD *, GUID *, __int64 **))*v24;
        v23 = 0;
        v17 = ((__int64 (__fastcall *)(_QWORD *, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))v19[6])(v24, &v23);
        v10 = v17;
        if ( v17 < 0 )
        {
          v18 = 592;
          goto LABEL_20;
        }
      }
      else
      {
        v26 = 0;
        v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
                &v26,
                &v27);
        v10 = v14;
        if ( v14 < 0 )
        {
          v15 = 587;
LABEL_10:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
            (const char *)(unsigned int)v14,
            v22);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
LABEL_11:
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v25);
          wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
          goto LABEL_6;
        }
        v16 = *v25;
        v23 = 0;
        v14 = (*(__int64 (__fastcall **)(__int64 *, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(v16 + 48))(
                v25,
                a1,
                v26,
                &v23);
        v10 = v14;
        if ( v14 < 0 )
        {
          v15 = 588;
          goto LABEL_10;
        }
        v11 = 1;
        wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v26);
      }
      if ( v23 )
      {
        v17 = (**v23)(v23, &GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4, a4);
        v10 = v17;
        if ( v17 < 0 )
        {
          v18 = 600;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
            (const char *)(unsigned int)v17,
            v22);
          goto LABEL_11;
        }
      }
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v25);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v23);
      wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(&v24);
    }
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v29,
      *a4 != 0,
      v11,
      (const unsigned __int16 *)v30);
    v10 = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\PlatformExtensionTools.h",
    (const char *)(unsigned int)v9,
    v22);
LABEL_23:
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v29);
  return v10;
}

```

## disassembly

```asm
0x18003b4c4  mov     [rsp-8+arg_10], rbx
0x18003b4c9  push    rbp
0x18003b4ca  push    rsi
0x18003b4cb  push    rdi
0x18003b4cc  push    r14
0x18003b4ce  push    r15
0x18003b4d0  lea     rbp, [rsp-1E0h]
0x18003b4d8  sub     rsp, 2E0h
0x18003b4df  mov     rax, cs:__security_cookie
0x18003b4e6  xor     rax, rsp
0x18003b4e9  mov     [rbp+200h+var_30], rax
0x18003b4f0  mov     rsi, rcx
0x18003b4f3  mov     [rsp+300h+var_2B0], edx
0x18003b4f7  lea     rcx, [rbp+200h+var_280]; struct wil::details::IFailureCallback *
0x18003b4fb  mov     r14, r9
0x18003b4fe  mov     ebx, edx
0x18003b500  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003b505  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x18003b50c  mov     r8d, ebx
0x18003b50f  lea     r9, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x18003b516  mov     [rbp+200h+var_280], rax
0x18003b51a  mov     rdx, rsi
0x18003b51d  lea     rcx, [rbp+200h+var_280]
0x18003b521  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x18003b526  mov     r9, [rbp+200h+var_170]
0x18003b52d  lea     rdx, [rbp+200h+var_130]; HSTRING
0x18003b534  xor     r15d, r15d
0x18003b537  add     r9, 8; unsigned __int64
0x18003b53b  mov     rcx, rsi; this
0x18003b53e  mov     [r14], r15
0x18003b541  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x18003b546  mov     ebx, eax
0x18003b548  test    eax, eax
0x18003b54a  jns     short loc_18003B56C
0x18003b54c  mov     rcx, [rbp+208h]; this
0x18003b553  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003b55a  mov     r9d, eax; char *
0x18003b55d  mov     edx, 23Eh; void *
0x18003b562  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b567  jmp     loc_18003B77E
0x18003b56c  mov     dil, r15b
0x18003b56f  cmp     word ptr [rbp+200h+var_130.unused], r15w
0x18003b577  jz      loc_18003B762
0x18003b57d  lea     rdx, [rbp+200h+var_130]; unsigned __int16 (*)[128]
0x18003b584  mov     [rsp+300h+var_2C8], r15
0x18003b589  lea     rcx, [rsp+300h+var_2A8]; this
0x18003b58e  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x18003b593  lea     r8, [rsp+300h+var_2C8]
0x18003b598  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18003b59f  mov     rcx, [rax+18h]
0x18003b5a3  call    cs:__imp_RoGetActivationFactory
0x18003b5a9  mov     ebx, eax
0x18003b5ab  test    eax, eax
0x18003b5ad  jns     short loc_18003B5D9
0x18003b5af  mov     rcx, [rbp+208h]; this
0x18003b5b6  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003b5bd  mov     r9d, eax; char *
0x18003b5c0  mov     edx, 242h; void *
0x18003b5c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b5ca  lea     rcx, [rsp+300h+var_2C8]
0x18003b5cf  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b5d4  jmp     loc_18003B77E
0x18003b5d9  mov     rcx, [rsp+300h+var_2C8]
0x18003b5de  lea     r8, [rsp+300h+var_2C0]
0x18003b5e3  mov     [rsp+300h+var_2D0], r15
0x18003b5e8  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x18003b5ef  mov     [rsp+300h+var_2C0], r15
0x18003b5f4  mov     rax, [rcx]
0x18003b5f7  mov     rax, [rax]
0x18003b5fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b5ff  test    eax, eax
0x18003b601  js      loc_18003B6E7
0x18003b607  lea     rdx, [rsp+300h+var_2B0]
0x18003b60c  mov     [rsp+300h+var_2B8], r15
0x18003b611  lea     rcx, [rsp+300h+var_2B8]
0x18003b616  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x18003b61b  mov     ebx, eax
0x18003b61d  test    eax, eax
0x18003b61f  jns     short loc_18003B65F
0x18003b621  mov     edx, 24Bh; void *
0x18003b626  mov     rcx, [rbp+208h]; this
0x18003b62d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003b634  mov     r9d, eax; char *
0x18003b637  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b63c  lea     rcx, [rsp+300h+var_2B8]
0x18003b641  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b646  lea     rcx, [rsp+300h+var_2C0]
0x18003b64b  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b650  lea     rcx, [rsp+300h+var_2D0]
0x18003b655  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b65a  jmp     loc_18003B5CA
0x18003b65f  mov     rcx, [rsp+300h+var_2D0]
0x18003b664  mov     rbx, [rsp+300h+var_2C0]
0x18003b669  mov     rax, [rbx]
0x18003b66c  mov     [rsp+300h+var_2D0], r15
0x18003b671  mov     rdi, [rax+30h]
0x18003b675  test    rcx, rcx
0x18003b678  jz      short loc_18003B686
0x18003b67a  mov     r8, [rcx]
0x18003b67d  mov     rax, [r8+10h]
0x18003b681  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b686  mov     r8, [rsp+300h+var_2B8]
0x18003b68b  lea     r9, [rsp+300h+var_2D0]
0x18003b690  mov     rdx, rsi
0x18003b693  mov     rcx, rbx
0x18003b696  mov     rax, rdi
0x18003b699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b69e  mov     ebx, eax
0x18003b6a0  test    eax, eax
0x18003b6a2  jns     short loc_18003B6AE
0x18003b6a4  mov     edx, 24Ch
0x18003b6a9  jmp     loc_18003B626
0x18003b6ae  lea     rcx, [rsp+300h+var_2B8]
0x18003b6b3  mov     dil, 1
0x18003b6b6  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b6bb  mov     rcx, [rsp+300h+var_2D0]
0x18003b6c0  test    rcx, rcx
0x18003b6c3  jz      short loc_18003B744
0x18003b6c5  mov     rax, [rcx]
0x18003b6c8  lea     rdx, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x18003b6cf  mov     r8, r14
0x18003b6d2  mov     rax, [rax]
0x18003b6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6da  mov     ebx, eax
0x18003b6dc  test    eax, eax
0x18003b6de  jns     short loc_18003B744
0x18003b6e0  mov     edx, 258h
0x18003b6e5  jmp     short loc_18003B729
0x18003b6e7  mov     rcx, [rsp+300h+var_2D0]
0x18003b6ec  mov     rbx, [rsp+300h+var_2C8]
0x18003b6f1  mov     rax, [rbx]
0x18003b6f4  mov     [rsp+300h+var_2D0], r15
0x18003b6f9  mov     rsi, [rax+30h]
0x18003b6fd  test    rcx, rcx
0x18003b700  jz      short loc_18003B70E
0x18003b702  mov     rdx, [rcx]
0x18003b705  mov     rax, [rdx+10h]
0x18003b709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b70e  lea     rdx, [rsp+300h+var_2D0]
0x18003b713  mov     rcx, rbx
0x18003b716  mov     rax, rsi
0x18003b719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b71e  mov     ebx, eax
0x18003b720  test    eax, eax
0x18003b722  jns     short loc_18003B6BB
0x18003b724  mov     edx, 250h; void *
0x18003b729  mov     rcx, [rbp+208h]; this
0x18003b730  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003b737  mov     r9d, eax; char *
0x18003b73a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b73f  jmp     loc_18003B646
0x18003b744  lea     rcx, [rsp+300h+var_2C0]
0x18003b749  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b74e  lea     rcx, [rsp+300h+var_2D0]
0x18003b753  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b758  lea     rcx, [rsp+300h+var_2C8]
0x18003b75d  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003b762  cmp     [r14], r15
0x18003b765  lea     r9, [rbp+200h+var_130]; unsigned __int16 *
0x18003b76c  mov     r8b, dil; bool
0x18003b76f  lea     rcx, [rbp+200h+var_280]; this
0x18003b773  setnz   dl; bool
0x18003b776  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x18003b77b  mov     ebx, r15d
0x18003b77e  lea     rcx, [rbp+200h+var_280]; this
0x18003b782  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x18003b787  mov     eax, ebx
0x18003b789  mov     rcx, [rbp+200h+var_30]
0x18003b790  xor     rcx, rsp; StackCookie
0x18003b793  call    __security_check_cookie
0x18003b798  mov     rbx, [rsp+300h+arg_10]
0x18003b7a0  add     rsp, 2E0h
0x18003b7a7  pop     r15
0x18003b7a9  pop     r14
0x18003b7ab  pop     rdi
0x18003b7ac  pop     rsi
0x18003b7ad  pop     rbp
0x18003b7ae  retn
```
