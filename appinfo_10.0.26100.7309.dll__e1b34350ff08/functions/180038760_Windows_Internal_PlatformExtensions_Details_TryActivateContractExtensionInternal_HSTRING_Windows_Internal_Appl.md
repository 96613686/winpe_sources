# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x180038760`
- end: `0x180038a42`
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
- `0x180026348`
- `0x180026be8`
- `0x1800270cc`
- `0x180027368`
- `0x180036e64`
- `0x180037364`
- `0x180038760`
- `0x180038aac`
- `0x1800444e0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003883e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003883e`

## string_xrefs

- `0x1800387f1`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180038857`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x1800388d4`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x1800389c7`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

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
0x180038760  push    rbp
0x180038762  push    rbx
0x180038763  push    rsi
0x180038764  push    rdi
0x180038765  push    r12
0x180038767  push    r14
0x180038769  push    r15
0x18003876b  lea     rbp, [rsp-1E0h]
0x180038773  sub     rsp, 2E0h
0x18003877a  mov     rax, cs:__security_cookie
0x180038781  xor     rax, rsp
0x180038784  mov     [rbp+210h+var_40], rax
0x18003878b  mov     r15, rcx
0x18003878e  mov     [rsp+310h+var_2C0], edx
0x180038792  lea     rcx, [rbp+210h+var_290]; struct wil::details::IFailureCallback *
0x180038796  mov     r14, r9
0x180038799  mov     ebx, edx
0x18003879b  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800387a0  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x1800387a7  mov     r8d, ebx
0x1800387aa  lea     r9, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x1800387b1  mov     [rbp+210h+var_290], rax
0x1800387b5  mov     rdx, r15
0x1800387b8  lea     rcx, [rbp+210h+var_290]
0x1800387bc  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x1800387c1  mov     r9, [rbp+210h+var_180]
0x1800387c8  lea     rdx, [rbp+210h+var_140]; HSTRING
0x1800387cf  xor     r12d, r12d
0x1800387d2  add     r9, 8; unsigned __int64
0x1800387d6  mov     rcx, r15; this
0x1800387d9  mov     [r14], r12
0x1800387dc  mov     sil, r12b
0x1800387df  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x1800387e4  mov     ebx, eax
0x1800387e6  test    eax, eax
0x1800387e8  jns     short loc_18003880A
0x1800387ea  mov     rcx, [rbp+218h]; this
0x1800387f1  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800387f8  mov     r9d, eax; char *
0x1800387fb  mov     edx, 23Eh; void *
0x180038800  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038805  jmp     loc_180038A15
0x18003880a  cmp     word ptr [rbp+210h+var_140.unused], r12w
0x180038812  jz      loc_1800389F9
0x180038818  lea     rdx, [rbp+210h+var_140]; unsigned __int16 (*)[128]
0x18003881f  mov     [rsp+310h+var_2D8], r12
0x180038824  lea     rcx, [rsp+310h+var_2B8]; this
0x180038829  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x18003882e  lea     r8, [rsp+310h+var_2D8]
0x180038833  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18003883a  mov     rcx, [rax+18h]
0x18003883e  call    cs:__imp_RoGetActivationFactory
0x180038845  nop     dword ptr [rax+rax+00h]
0x18003884a  mov     ebx, eax
0x18003884c  test    eax, eax
0x18003884e  jns     short loc_18003887A
0x180038850  mov     rcx, [rbp+218h]; this
0x180038857  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003885e  mov     r9d, eax; char *
0x180038861  mov     edx, 242h; void *
0x180038866  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003886b  lea     rcx, [rsp+310h+var_2D8]
0x180038870  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038875  jmp     loc_180038A15
0x18003887a  mov     rcx, [rsp+310h+var_2D8]
0x18003887f  lea     r8, [rsp+310h+var_2D0]
0x180038884  mov     [rsp+310h+var_2E0], r12
0x180038889  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x180038890  mov     [rsp+310h+var_2D0], r12
0x180038895  mov     rax, [rcx]
0x180038898  mov     rax, [rax]
0x18003889b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800388a0  shr     eax, 1Fh
0x1800388a3  test    al, al
0x1800388a5  jnz     loc_180038983
0x1800388ab  lea     rdx, [rsp+310h+var_2C0]
0x1800388b0  mov     [rsp+310h+var_2C8], r12
0x1800388b5  lea     rcx, [rsp+310h+var_2C8]
0x1800388ba  mov     sil, 1
0x1800388bd  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x1800388c2  mov     ebx, eax
0x1800388c4  test    eax, eax
0x1800388c6  jns     short loc_180038906
0x1800388c8  mov     edx, 24Bh; void *
0x1800388cd  mov     rcx, [rbp+218h]; this
0x1800388d4  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800388db  mov     r9d, eax; char *
0x1800388de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800388e3  lea     rcx, [rsp+310h+var_2C8]
0x1800388e8  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800388ed  lea     rcx, [rsp+310h+var_2D0]
0x1800388f2  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800388f7  lea     rcx, [rsp+310h+var_2E0]
0x1800388fc  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038901  jmp     loc_18003886B
0x180038906  mov     rbx, [rsp+310h+var_2D0]
0x18003890b  mov     rcx, [rsp+310h+var_2E0]
0x180038910  mov     rax, [rbx]
0x180038913  mov     rdi, [rax+30h]
0x180038917  test    rcx, rcx
0x18003891a  jz      short loc_180038928
0x18003891c  mov     r8, [rcx]
0x18003891f  mov     rax, [r8+10h]
0x180038923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038928  mov     r8, [rsp+310h+var_2C8]
0x18003892d  lea     r9, [rsp+310h+var_2E0]
0x180038932  mov     rdx, r15
0x180038935  mov     rcx, rbx
0x180038938  mov     rax, rdi
0x18003893b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038940  mov     ebx, eax
0x180038942  test    eax, eax
0x180038944  jns     short loc_18003894D
0x180038946  mov     edx, 24Ch
0x18003894b  jmp     short loc_1800388CD
0x18003894d  lea     rcx, [rsp+310h+var_2C8]
0x180038952  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038957  mov     rcx, [rsp+310h+var_2E0]
0x18003895c  test    rcx, rcx
0x18003895f  jz      short loc_1800389DB
0x180038961  mov     rax, [rcx]
0x180038964  lea     rdx, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x18003896b  mov     r8, r14
0x18003896e  mov     rax, [rax]
0x180038971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038976  mov     ebx, eax
0x180038978  test    eax, eax
0x18003897a  jns     short loc_1800389DB
0x18003897c  mov     edx, 258h
0x180038981  jmp     short loc_1800389C0
0x180038983  mov     rbx, [rsp+310h+var_2D8]
0x180038988  mov     rcx, [rsp+310h+var_2E0]
0x18003898d  mov     rax, [rbx]
0x180038990  mov     rdi, [rax+30h]
0x180038994  test    rcx, rcx
0x180038997  jz      short loc_1800389A5
0x180038999  mov     rdx, [rcx]
0x18003899c  mov     rax, [rdx+10h]
0x1800389a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389a5  lea     rdx, [rsp+310h+var_2E0]
0x1800389aa  mov     rcx, rbx
0x1800389ad  mov     rax, rdi
0x1800389b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800389b5  mov     ebx, eax
0x1800389b7  test    eax, eax
0x1800389b9  jns     short loc_180038957
0x1800389bb  mov     edx, 250h; void *
0x1800389c0  mov     rcx, [rbp+218h]; this
0x1800389c7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800389ce  mov     r9d, eax; char *
0x1800389d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800389d6  jmp     loc_1800388ED
0x1800389db  lea     rcx, [rsp+310h+var_2D0]
0x1800389e0  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800389e5  lea     rcx, [rsp+310h+var_2E0]
0x1800389ea  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800389ef  lea     rcx, [rsp+310h+var_2D8]
0x1800389f4  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800389f9  cmp     [r14], r12
0x1800389fc  lea     r9, [rbp+210h+var_140]; unsigned __int16 *
0x180038a03  mov     r8b, sil; bool
0x180038a06  lea     rcx, [rbp+210h+var_290]; this
0x180038a0a  setnz   dl; bool
0x180038a0d  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x180038a12  mov     ebx, r12d
0x180038a15  lea     rcx, [rbp+210h+var_290]; this
0x180038a19  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x180038a1e  mov     eax, ebx
0x180038a20  mov     rcx, [rbp+210h+var_40]
0x180038a27  xor     rcx, rsp; StackCookie
0x180038a2a  call    __security_check_cookie
0x180038a2f  add     rsp, 2E0h
0x180038a36  pop     r15
0x180038a38  pop     r14
0x180038a3a  pop     r12
0x180038a3c  pop     rdi
0x180038a3d  pop     rsi
0x180038a3e  pop     rbx
0x180038a3f  pop     rbp
0x180038a40  retn
```
