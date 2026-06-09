# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x1800380c0`
- end: `0x1800383a2`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `738`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180010f3c`

## callees

- `0x180007c78`
- `0x18002719c`
- `0x180027988`
- `0x180028228`
- `0x18002870c`
- `0x1800289a8`
- `0x1800367c4`
- `0x180036cc4`
- `0x1800380c0`
- `0x18003840c`
- `0x180042950`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003819e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18003819e`

## string_xrefs

- `0x180038151`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x1800381b7`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180038234`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`
- `0x180038327`: `onecoreuap\internal\shell\inc\PlatformExtensionTools.h`

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
0x1800380c0  push    rbp
0x1800380c2  push    rbx
0x1800380c3  push    rsi
0x1800380c4  push    rdi
0x1800380c5  push    r12
0x1800380c7  push    r14
0x1800380c9  push    r15
0x1800380cb  lea     rbp, [rsp-1E0h]
0x1800380d3  sub     rsp, 2E0h
0x1800380da  mov     rax, cs:__security_cookie
0x1800380e1  xor     rax, rsp
0x1800380e4  mov     [rbp+210h+var_40], rax
0x1800380eb  mov     r15, rcx
0x1800380ee  mov     [rsp+310h+var_2C0], edx
0x1800380f2  lea     rcx, [rbp+210h+var_290]; struct wil::details::IFailureCallback *
0x1800380f6  mov     r14, r9
0x1800380f9  mov     ebx, edx
0x1800380fb  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180038100  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x180038107  mov     r8d, ebx
0x18003810a  lea     r9, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x180038111  mov     [rbp+210h+var_290], rax
0x180038115  mov     rdx, r15
0x180038118  lea     rcx, [rbp+210h+var_290]
0x18003811c  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x180038121  mov     r9, [rbp+210h+var_180]
0x180038128  lea     rdx, [rbp+210h+var_140]; HSTRING
0x18003812f  xor     r12d, r12d
0x180038132  add     r9, 8; unsigned __int64
0x180038136  mov     rcx, r15; this
0x180038139  mov     [r14], r12
0x18003813c  mov     sil, r12b
0x18003813f  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x180038144  mov     ebx, eax
0x180038146  test    eax, eax
0x180038148  jns     short loc_18003816A
0x18003814a  mov     rcx, [rbp+218h]; this
0x180038151  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x180038158  mov     r9d, eax; char *
0x18003815b  mov     edx, 23Eh; void *
0x180038160  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038165  jmp     loc_180038375
0x18003816a  cmp     word ptr [rbp+210h+var_140.unused], r12w
0x180038172  jz      loc_180038359
0x180038178  lea     rdx, [rbp+210h+var_140]; unsigned __int16 (*)[128]
0x18003817f  mov     [rsp+310h+var_2D8], r12
0x180038184  lea     rcx, [rsp+310h+var_2B8]; this
0x180038189  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x18003818e  lea     r8, [rsp+310h+var_2D8]
0x180038193  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18003819a  mov     rcx, [rax+18h]
0x18003819e  call    cs:__imp_RoGetActivationFactory
0x1800381a5  nop     dword ptr [rax+rax+00h]
0x1800381aa  mov     ebx, eax
0x1800381ac  test    eax, eax
0x1800381ae  jns     short loc_1800381DA
0x1800381b0  mov     rcx, [rbp+218h]; this
0x1800381b7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x1800381be  mov     r9d, eax; char *
0x1800381c1  mov     edx, 242h; void *
0x1800381c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800381cb  lea     rcx, [rsp+310h+var_2D8]
0x1800381d0  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800381d5  jmp     loc_180038375
0x1800381da  mov     rcx, [rsp+310h+var_2D8]
0x1800381df  lea     r8, [rsp+310h+var_2D0]
0x1800381e4  mov     [rsp+310h+var_2E0], r12
0x1800381e9  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x1800381f0  mov     [rsp+310h+var_2D0], r12
0x1800381f5  mov     rax, [rcx]
0x1800381f8  mov     rax, [rax]
0x1800381fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038200  shr     eax, 1Fh
0x180038203  test    al, al
0x180038205  jnz     loc_1800382E3
0x18003820b  lea     rdx, [rsp+310h+var_2C0]
0x180038210  mov     [rsp+310h+var_2C8], r12
0x180038215  lea     rcx, [rsp+310h+var_2C8]
0x18003821a  mov     sil, 1
0x18003821d  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x180038222  mov     ebx, eax
0x180038224  test    eax, eax
0x180038226  jns     short loc_180038266
0x180038228  mov     edx, 24Bh; void *
0x18003822d  mov     rcx, [rbp+218h]; this
0x180038234  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003823b  mov     r9d, eax; char *
0x18003823e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038243  lea     rcx, [rsp+310h+var_2C8]
0x180038248  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003824d  lea     rcx, [rsp+310h+var_2D0]
0x180038252  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038257  lea     rcx, [rsp+310h+var_2E0]
0x18003825c  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038261  jmp     loc_1800381CB
0x180038266  mov     rbx, [rsp+310h+var_2D0]
0x18003826b  mov     rcx, [rsp+310h+var_2E0]
0x180038270  mov     rax, [rbx]
0x180038273  mov     rdi, [rax+30h]
0x180038277  test    rcx, rcx
0x18003827a  jz      short loc_180038288
0x18003827c  mov     r8, [rcx]
0x18003827f  mov     rax, [r8+10h]
0x180038283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038288  mov     r8, [rsp+310h+var_2C8]
0x18003828d  lea     r9, [rsp+310h+var_2E0]
0x180038292  mov     rdx, r15
0x180038295  mov     rcx, rbx
0x180038298  mov     rax, rdi
0x18003829b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382a0  mov     ebx, eax
0x1800382a2  test    eax, eax
0x1800382a4  jns     short loc_1800382AD
0x1800382a6  mov     edx, 24Ch
0x1800382ab  jmp     short loc_18003822D
0x1800382ad  lea     rcx, [rsp+310h+var_2C8]
0x1800382b2  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x1800382b7  mov     rcx, [rsp+310h+var_2E0]
0x1800382bc  test    rcx, rcx
0x1800382bf  jz      short loc_18003833B
0x1800382c1  mov     rax, [rcx]
0x1800382c4  lea     rdx, _GUID_b0df66ae_f278_4dbb_a262_cdaf6af8feb4
0x1800382cb  mov     r8, r14
0x1800382ce  mov     rax, [rax]
0x1800382d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800382d6  mov     ebx, eax
0x1800382d8  test    eax, eax
0x1800382da  jns     short loc_18003833B
0x1800382dc  mov     edx, 258h
0x1800382e1  jmp     short loc_180038320
0x1800382e3  mov     rbx, [rsp+310h+var_2D8]
0x1800382e8  mov     rcx, [rsp+310h+var_2E0]
0x1800382ed  mov     rax, [rbx]
0x1800382f0  mov     rdi, [rax+30h]
0x1800382f4  test    rcx, rcx
0x1800382f7  jz      short loc_180038305
0x1800382f9  mov     rdx, [rcx]
0x1800382fc  mov     rax, [rdx+10h]
0x180038300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038305  lea     rdx, [rsp+310h+var_2E0]
0x18003830a  mov     rcx, rbx
0x18003830d  mov     rax, rdi
0x180038310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038315  mov     ebx, eax
0x180038317  test    eax, eax
0x180038319  jns     short loc_1800382B7
0x18003831b  mov     edx, 250h; void *
0x180038320  mov     rcx, [rbp+218h]; this
0x180038327  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\Platf"...
0x18003832e  mov     r9d, eax; char *
0x180038331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180038336  jmp     loc_18003824D
0x18003833b  lea     rcx, [rsp+310h+var_2D0]
0x180038340  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038345  lea     rcx, [rsp+310h+var_2E0]
0x18003834a  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x18003834f  lea     rcx, [rsp+310h+var_2D8]
0x180038354  call    ??1?$com_ptr_t@U?$IAsyncOperation@PEAVUserSelectionResult@UserSelection@PlatformExtensions@Internal@Windows@@@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::PlatformExtensions::UserSelection::UserSelectionResult *>,wil::err_returncode_policy>(void)
0x180038359  cmp     [r14], r12
0x18003835c  lea     r9, [rbp+210h+var_140]; unsigned __int16 *
0x180038363  mov     r8b, sil; bool
0x180038366  lea     rcx, [rbp+210h+var_290]; this
0x18003836a  setnz   dl; bool
0x18003836d  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x180038372  mov     ebx, r12d
0x180038375  lea     rcx, [rbp+210h+var_290]; this
0x180038379  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x18003837e  mov     eax, ebx
0x180038380  mov     rcx, [rbp+210h+var_40]
0x180038387  xor     rcx, rsp; StackCookie
0x18003838a  call    __security_check_cookie
0x18003838f  add     rsp, 2E0h
0x180038396  pop     r15
0x180038398  pop     r14
0x18003839a  pop     r12
0x18003839c  pop     rdi
0x18003839d  pop     rsi
0x18003839e  pop     rbx
0x18003839f  pop     rbp
0x1800383a0  retn
```
