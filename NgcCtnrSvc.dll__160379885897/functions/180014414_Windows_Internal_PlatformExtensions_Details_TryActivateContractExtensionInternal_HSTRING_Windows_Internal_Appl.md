# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x180014414`
- end: `0x18001470d`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180021e88`
- `0x180022f7c`

## callees

- `0x18000c688`
- `0x180014414`
- `0x180014714`
- `0x180014838`
- `0x18001cf08`
- `0x180023278`
- `0x180024698`
- `0x180024948`
- `0x18002c640`
- `0x180034950`
- `0x180034bbc`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800144f4`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800144f4`

## string_xrefs

- `0x1800144a7`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180014510`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18001457d`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180014686`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int16 *v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  char v10; // di
  __int64 v11; // rax
  int ActivationFactory; // eax
  int v13; // eax
  __int64 v14; // rdx
  __int64 (__fastcall *v15)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)); // rdi
  int v16; // eax
  __int64 v17; // rdx
  __int64 (__fastcall *v18)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)); // rsi
  const struct _GUID *v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v22)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v28[42]; // [rsp+80h] [rbp-80h] BYREF
  HSTRING__ sourceString[64]; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v26 = a2;
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v28);
  v28[0] = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    (__int64)v28,
    a1,
    a2,
    (__int64)&GUID_dff85587_911b_4c34_abfe_9c21380107da);
  *a4 = 0;
  v8 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
         a1,
         sourceString,
         v7,
         v28[34] + 8LL,
         v20);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v10 = 0;
    if ( LOWORD(sourceString[0].unused) )
    {
      v23 = 0;
      v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, (PCWSTR)sourceString);
      ActivationFactory = RoGetActivationFactory(
                            *(_QWORD *)(v11 + 24),
                            &GUID_00000035_0000_0000_c000_000000000046,
                            &v23);
      v9 = ActivationFactory;
      if ( ActivationFactory < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x242,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)ActivationFactory,
          v21);
LABEL_6:
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v23);
        goto LABEL_23;
      }
      v22 = 0;
      v24 = 0;
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v23)(
             v23,
             &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
             &v24) < 0 )
      {
        v18 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v23 + 48LL);
        v22 = 0;
        v16 = v18(v23, &v22);
        v9 = v16;
        if ( v16 < 0 )
        {
          v17 = 592;
          goto LABEL_20;
        }
      }
      else
      {
        v25 = 0;
        v13 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
                &v25,
                &v26);
        v9 = v13;
        if ( v13 < 0 )
        {
          v14 = 587;
LABEL_10:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v14,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
            (const char *)(unsigned int)v13,
            v21);
          wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v25);
LABEL_11:
          wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v24);
          wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v22);
          goto LABEL_6;
        }
        v15 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v24 + 48LL);
        v22 = 0;
        v13 = v15(v24, a1, v25, &v22);
        v9 = v13;
        if ( v13 < 0 )
        {
          v14 = 588;
          goto LABEL_10;
        }
        v10 = 1;
        wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v25);
      }
      if ( v22 )
      {
        v16 = (**v22)(v22, &GUID_dff85587_911b_4c34_abfe_9c21380107da, a4);
        v9 = v16;
        if ( v16 < 0 )
        {
          v17 = 600;
LABEL_20:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v17,
            (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
            (const char *)(unsigned int)v16,
            v21);
          goto LABEL_11;
        }
      }
      wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v24);
      wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>((__int64 *)&v22);
      wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(&v23);
    }
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
      (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v28,
      *a4 != 0,
      v10,
      (const unsigned __int16 *)sourceString);
    v9 = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23E,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v8,
    v21);
LABEL_23:
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v28);
  return v9;
}

```

## disassembly

```asm
0x180014414  mov     [rsp-8+arg_10], rbx
0x180014419  push    rbp
0x18001441a  push    rsi
0x18001441b  push    rdi
0x18001441c  push    r14
0x18001441e  push    r15
0x180014420  lea     rbp, [rsp-1E0h]
0x180014428  sub     rsp, 2E0h
0x18001442f  mov     rax, cs:__security_cookie
0x180014436  xor     rax, rsp
0x180014439  mov     [rbp+200h+var_30], rax
0x180014440  mov     r14, r9
0x180014443  mov     ebx, edx
0x180014445  mov     rsi, rcx
0x180014448  mov     [rsp+300h+var_2B0], edx
0x18001444c  lea     rcx, [rbp+200h+var_280]; struct wil::details::IFailureCallback *
0x180014450  call    ??0?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180014455  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x18001445c  mov     [rbp+200h+var_280], rax
0x180014460  lea     r9, _GUID_dff85587_911b_4c34_abfe_9c21380107da
0x180014467  mov     r8d, ebx
0x18001446a  mov     rdx, rsi
0x18001446d  lea     rcx, [rbp+200h+var_280]
0x180014471  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x180014476  nop
0x180014477  xor     r15d, r15d
0x18001447a  mov     [r14], r15
0x18001447d  mov     r9, [rbp+200h+var_170]
0x180014484  add     r9, 8; unsigned __int64
0x180014488  lea     rdx, [rbp+200h+sourceString]; HSTRING
0x18001448f  mov     rcx, rsi; this
0x180014492  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x180014497  mov     ebx, eax
0x180014499  test    eax, eax
0x18001449b  jns     short loc_1800144BD
0x18001449d  mov     rcx, [rbp+208h]; this
0x1800144a4  mov     r9d, eax; char *
0x1800144a7  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x1800144ae  mov     edx, 23Eh; void *
0x1800144b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800144b8  jmp     loc_1800146DB
0x1800144bd  mov     dil, r15b
0x1800144c0  cmp     [rbp+200h+sourceString], r15w
0x1800144c8  jz      loc_1800146BF
0x1800144ce  mov     [rsp+300h+var_2C8], r15
0x1800144d3  lea     rdx, [rbp+200h+sourceString]; sourceString
0x1800144da  lea     rcx, [rsp+300h+hstringHeader]; hstringHeader
0x1800144df  call    ??$?0$0IA@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEAY0IA@G@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort (&)[128])
0x1800144e4  lea     r8, [rsp+300h+var_2C8]
0x1800144e9  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x1800144f0  mov     rcx, [rax+18h]
0x1800144f4  call    cs:__imp_RoGetActivationFactory
0x1800144fb  nop     dword ptr [rax+rax+00h]
0x180014500  mov     ebx, eax
0x180014502  test    eax, eax
0x180014504  jns     short loc_180014530
0x180014506  mov     rcx, [rbp+208h]; this
0x18001450d  mov     r9d, eax; char *
0x180014510  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180014517  mov     edx, 242h; void *
0x18001451c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014521  lea     rcx, [rsp+300h+var_2C8]
0x180014526  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001452b  jmp     loc_1800146DB
0x180014530  mov     [rsp+300h+var_2D0], r15
0x180014535  mov     [rsp+300h+var_2C0], r15
0x18001453a  mov     rcx, [rsp+300h+var_2C8]
0x18001453f  mov     rax, [rcx]
0x180014542  lea     r8, [rsp+300h+var_2C0]
0x180014547  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x18001454e  mov     rax, [rax]
0x180014551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014556  test    eax, eax
0x180014558  js      loc_180014643
0x18001455e  mov     [rsp+300h+var_2B8], r15
0x180014563  lea     rdx, [rsp+300h+var_2B0]
0x180014568  lea     rcx, [rsp+300h+var_2B8]
0x18001456d  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x180014572  mov     ebx, eax
0x180014574  test    eax, eax
0x180014576  jns     short loc_1800145B6
0x180014578  mov     edx, 24Bh; void *
0x18001457d  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180014584  mov     r9d, eax; char *
0x180014587  mov     rcx, [rbp+208h]; this
0x18001458e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014593  lea     rcx, [rsp+300h+var_2B8]
0x180014598  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x18001459d  lea     rcx, [rsp+300h+var_2C0]
0x1800145a2  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800145a7  lea     rcx, [rsp+300h+var_2D0]
0x1800145ac  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800145b1  jmp     loc_180014521
0x1800145b6  mov     rbx, [rsp+300h+var_2C0]
0x1800145bb  mov     rax, [rbx]
0x1800145be  mov     rdi, [rax+30h]
0x1800145c2  mov     rcx, [rsp+300h+var_2D0]
0x1800145c7  mov     [rsp+300h+var_2D0], r15
0x1800145cc  test    rcx, rcx
0x1800145cf  jz      short loc_1800145DE
0x1800145d1  mov     r8, [rcx]
0x1800145d4  mov     rax, [r8+10h]
0x1800145d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145dd  nop
0x1800145de  lea     r9, [rsp+300h+var_2D0]
0x1800145e3  mov     r8, [rsp+300h+var_2B8]
0x1800145e8  mov     rdx, rsi
0x1800145eb  mov     rcx, rbx
0x1800145ee  mov     rax, rdi
0x1800145f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145f6  mov     ebx, eax
0x1800145f8  test    eax, eax
0x1800145fa  jns     short loc_180014606
0x1800145fc  mov     edx, 24Ch
0x180014601  jmp     loc_18001457D
0x180014606  mov     dil, 1
0x180014609  lea     rcx, [rsp+300h+var_2B8]
0x18001460e  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x180014613  mov     rcx, [rsp+300h+var_2D0]
0x180014618  test    rcx, rcx
0x18001461b  jz      loc_1800146A1
0x180014621  mov     rax, [rcx]
0x180014624  mov     r8, r14
0x180014627  lea     rdx, _GUID_dff85587_911b_4c34_abfe_9c21380107da
0x18001462e  mov     rax, [rax]
0x180014631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014636  mov     ebx, eax
0x180014638  test    eax, eax
0x18001463a  jns     short loc_1800146A1
0x18001463c  mov     edx, 258h
0x180014641  jmp     short loc_180014686
0x180014643  mov     rbx, [rsp+300h+var_2C8]
0x180014648  mov     rax, [rbx]
0x18001464b  mov     rsi, [rax+30h]
0x18001464f  mov     rcx, [rsp+300h+var_2D0]
0x180014654  mov     [rsp+300h+var_2D0], r15
0x180014659  test    rcx, rcx
0x18001465c  jz      short loc_18001466B
0x18001465e  mov     rdx, [rcx]
0x180014661  mov     rax, [rdx+10h]
0x180014665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001466a  nop
0x18001466b  lea     rdx, [rsp+300h+var_2D0]
0x180014670  mov     rcx, rbx
0x180014673  mov     rax, rsi
0x180014676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001467b  mov     ebx, eax
0x18001467d  test    eax, eax
0x18001467f  jns     short loc_180014613
0x180014681  mov     edx, 250h; void *
0x180014686  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18001468d  mov     r9d, eax; char *
0x180014690  mov     rcx, [rbp+208h]; this
0x180014697  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001469c  jmp     loc_18001459D
0x1800146a1  lea     rcx, [rsp+300h+var_2C0]
0x1800146a6  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800146ab  lea     rcx, [rsp+300h+var_2D0]
0x1800146b0  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800146b5  lea     rcx, [rsp+300h+var_2C8]
0x1800146ba  call    ??1?$com_ptr_t@UINgcCtnrContainer@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>::~com_ptr_t<INgcCtnrContainer,wil::err_exception_policy>(void)
0x1800146bf  cmp     [r14], r15
0x1800146c2  setnz   dl; bool
0x1800146c5  lea     r9, [rbp+200h+sourceString]; unsigned __int16 *
0x1800146cc  mov     r8b, dil; bool
0x1800146cf  lea     rcx, [rbp+200h+var_280]; this
0x1800146d3  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x1800146d8  mov     ebx, r15d
0x1800146db  lea     rcx, [rbp+200h+var_280]; this
0x1800146df  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x1800146e4  mov     eax, ebx
0x1800146e6  mov     rcx, [rbp+200h+var_30]
0x1800146ed  xor     rcx, rsp; StackCookie
0x1800146f0  call    __security_check_cookie
0x1800146f5  mov     rbx, [rsp+300h+arg_10]
0x1800146fd  add     rsp, 2E0h
0x180014704  pop     r15
0x180014706  pop     r14
0x180014708  pop     rdi
0x180014709  pop     rsi
0x18001470a  pop     rbp
0x18001470b  retn
```
