# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x180015d0c`
- end: `0x180016040`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `820`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000ccf8`
- `0x18000cd44`
- `0x180012f30`
- `0x180016050`
- `0x180016370`

## callees

- `0x180002e60`
- `0x18000907c`
- `0x18000b7bc`
- `0x18000c34c`
- `0x18000ddc4`
- `0x18000e154`
- `0x18000ea2c`
- `0x18000f7b4`
- `0x1800150e4`
- `0x180015d0c`
- `0x180017520`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016039`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016039`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015e0f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180015e0f`

## string_xrefs

- `0x180015d91`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180015e25`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180015e88`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180015f3a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int16 *v7; // r8
  int v8; // eax
  unsigned int v9; // ebx
  char v10; // di
  unsigned __int64 v11; // rbx
  UINT32 v12; // eax
  int ActivationFactory; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 (__fastcall *v16)(__int64, HSTRING, HSTRING, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)); // rdi
  int v17; // eax
  __int64 v18; // rdx
  __int64 (__fastcall *v20)(__int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)); // rsi
  const struct _GUID *v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+20h] [rbp-E0h]
  __int64 (__fastcall ***v23)(_QWORD, __int64, _QWORD *); // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h]
  struct tagComCallData v30[17]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v31; // [rsp+190h] [rbp+90h]
  HSTRING__ sourceString; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v26 = a1;
  v27 = a2;
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::TryActivateContractExtension(
    (__int64)v30,
    a2,
    &v26,
    (unsigned int *)&v27,
    a3);
  *a4 = 0;
  v8 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
         a1,
         &sourceString,
         v7,
         v31 + 8,
         v21);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v8,
      v22);
LABEL_22:
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(v30);
    return v9;
  }
  v10 = 0;
  if ( LOWORD(sourceString.unused) )
  {
    v24 = 0;
    v11 = -1;
    do
      ++v11;
    while ( *((_WORD *)&sourceString.unused + v11) );
    if ( v11 > 0xFFFFFFFF )
    {
      RaiseException(0x80070216, 1u, 0, 0);
      JUMPOUT(0x18001603FLL);
    }
    v12 = Microsoft::WRL::Wrappers::HStringReference::AddOne(v11);
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, (PCWSTR)&sourceString, v12, v11);
    ActivationFactory = RoGetActivationFactory(v29, &GUID_00000035_0000_0000_c000_000000000046, &v24);
    v9 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)ActivationFactory,
        v22);
LABEL_21:
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v24);
      goto LABEL_22;
    }
    v23 = 0;
    v25 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v24)(
           v24,
           &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
           &v25) < 0 )
    {
      v20 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(*(_QWORD *)v24 + 48LL);
      v23 = 0;
      v17 = v20(v24, &v23);
      v9 = v17;
      if ( v17 < 0 )
      {
        v18 = 592;
        goto LABEL_19;
      }
    }
    else
    {
      v26 = 0;
      v14 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
              &v26,
              &v27);
      v9 = v14;
      if ( v14 < 0 )
      {
        v15 = 587;
LABEL_12:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v14,
          v22);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v26);
LABEL_20:
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v25);
        wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v23);
        goto LABEL_21;
      }
      v16 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64 (__fastcall ****)(_QWORD, __int64, _QWORD *)))(*(_QWORD *)v25 + 48LL);
      v23 = 0;
      v14 = v16(v25, a1, v26, &v23);
      v9 = v14;
      if ( v14 < 0 )
      {
        v15 = 588;
        goto LABEL_12;
      }
      v10 = 1;
      wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v26);
    }
    if ( v23 )
    {
      v17 = (**v23)(v23, a3, a4);
      v9 = v17;
      if ( v17 < 0 )
      {
        v18 = 600;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v18,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v17,
          v22);
        goto LABEL_20;
      }
    }
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v25);
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>((__int64 *)&v23);
    wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(&v24);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)v30,
    *a4 != 0,
    v10,
    (const unsigned __int16 *)&sourceString);
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(v30);
  return 0;
}

```

## disassembly

```asm
0x180015d0c  push    rbp
0x180015d0e  push    rbx
0x180015d0f  push    rsi
0x180015d10  push    rdi
0x180015d11  push    r12
0x180015d13  push    r14
0x180015d15  push    r15
0x180015d17  lea     rbp, [rsp-1E0h]
0x180015d1f  sub     rsp, 2E0h
0x180015d26  mov     rax, cs:__security_cookie
0x180015d2d  xor     rax, rsp
0x180015d30  mov     [rbp+210h+var_40], rax
0x180015d37  mov     r14, r9
0x180015d3a  mov     r15, r8
0x180015d3d  mov     rsi, rcx
0x180015d40  mov     [rsp+310h+var_2C8], rcx
0x180015d45  mov     [rsp+310h+var_2C0], edx
0x180015d49  mov     [rsp+310h+var_2F0], r8; int
0x180015d4e  lea     r9, [rsp+310h+var_2C0]
0x180015d53  lea     r8, [rsp+310h+var_2C8]
0x180015d58  lea     rcx, [rbp+210h+var_290]
0x180015d5c  call    ??$?0AEAPEAUHSTRING__@@AEAUWindowId@WindowManagement@ApplicationModel@Internal@Windows@@AEBU_GUID@@@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@AEAA@U?$integral_constant@D$0A@@wistd@@AEAPEAUHSTRING__@@AEAUWindowId@WindowManagement@ApplicationModel@45@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::TryActivateContractExtension(wistd::integral_constant<char,0>,HSTRING__ * &,Windows::Internal::ApplicationModel::WindowManagement::WindowId &,_GUID const &)
0x180015d61  xor     r12d, r12d
0x180015d64  mov     [r14], r12
0x180015d67  mov     r9, [rbp+210h+var_180]
0x180015d6e  add     r9, 8; unsigned __int64
0x180015d72  lea     rdx, [rbp+210h+sourceString]; HSTRING
0x180015d79  mov     rcx, rsi; this
0x180015d7c  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x180015d81  mov     ebx, eax
0x180015d83  test    eax, eax
0x180015d85  jns     short loc_180015DA7
0x180015d87  mov     rcx, [rbp+218h]; this
0x180015d8e  mov     r9d, eax; char *
0x180015d91  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180015d98  mov     edx, 23Eh; void *
0x180015d9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015da2  jmp     loc_180015F6B
0x180015da7  mov     dil, r12b
0x180015daa  cmp     word ptr [rbp+210h+sourceString.unused], r12w
0x180015db2  jz      loc_180015FE5
0x180015db8  mov     [rsp+310h+var_2D8], r12
0x180015dbd  lea     rax, [rbp+210h+sourceString]
0x180015dc4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015dc8  inc     rbx
0x180015dcb  cmp     [rax+rbx*2], r12w
0x180015dd0  jnz     short loc_180015DC8
0x180015dd2  mov     eax, 0FFFFFFFFh
0x180015dd7  cmp     rbx, rax
0x180015dda  ja      loc_18001602A
0x180015de0  mov     ecx, ebx; unsigned int
0x180015de2  call    ?AddOne@HStringReference@Wrappers@WRL@Microsoft@@CAII@Z; Microsoft::WRL::Wrappers::HStringReference::AddOne(uint)
0x180015de7  mov     r9d, ebx; unsigned int
0x180015dea  mov     r8d, eax; unsigned int
0x180015ded  lea     rdx, [rbp+210h+sourceString]; sourceString
0x180015df4  lea     rcx, [rsp+310h+hstringHeader]; hstringHeader
0x180015df9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015dfe  lea     r8, [rsp+310h+var_2D8]
0x180015e03  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x180015e0a  mov     rcx, [rsp+310h+var_2A0]
0x180015e0f  call    cs:__imp_RoGetActivationFactory
0x180015e15  mov     ebx, eax
0x180015e17  test    eax, eax
0x180015e19  jns     short loc_180015E3B
0x180015e1b  mov     rcx, [rbp+218h]; this
0x180015e22  mov     r9d, eax; char *
0x180015e25  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180015e2c  mov     edx, 242h; void *
0x180015e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e36  jmp     loc_180015F61
0x180015e3b  mov     [rsp+310h+var_2E0], r12
0x180015e40  mov     [rsp+310h+var_2D0], r12
0x180015e45  mov     rcx, [rsp+310h+var_2D8]
0x180015e4a  mov     rax, [rcx]
0x180015e4d  lea     r8, [rsp+310h+var_2D0]
0x180015e52  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x180015e59  mov     rax, [rax]
0x180015e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e61  test    eax, eax
0x180015e63  js      loc_180015F7B
0x180015e69  mov     [rsp+310h+var_2C8], r12
0x180015e6e  lea     rdx, [rsp+310h+var_2C0]
0x180015e73  lea     rcx, [rsp+310h+var_2C8]
0x180015e78  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x180015e7d  mov     ebx, eax
0x180015e7f  test    eax, eax
0x180015e81  jns     short loc_180015EAD
0x180015e83  mov     edx, 24Bh; void *
0x180015e88  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180015e8f  mov     r9d, eax; char *
0x180015e92  mov     rcx, [rbp+218h]; this
0x180015e99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015e9e  lea     rcx, [rsp+310h+var_2C8]
0x180015ea3  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015ea8  jmp     loc_180015F4D
0x180015ead  mov     rbx, [rsp+310h+var_2D0]
0x180015eb2  mov     rax, [rbx]
0x180015eb5  mov     rdi, [rax+30h]
0x180015eb9  mov     rcx, [rsp+310h+var_2E0]
0x180015ebe  mov     [rsp+310h+var_2E0], r12
0x180015ec3  test    rcx, rcx
0x180015ec6  jz      short loc_180015ED5
0x180015ec8  mov     r8, [rcx]
0x180015ecb  mov     rax, [r8+10h]
0x180015ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ed4  nop
0x180015ed5  lea     r9, [rsp+310h+var_2E0]
0x180015eda  mov     r8, [rsp+310h+var_2C8]
0x180015edf  mov     rdx, rsi
0x180015ee2  mov     rcx, rbx
0x180015ee5  mov     rax, rdi
0x180015ee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eed  mov     ebx, eax
0x180015eef  test    eax, eax
0x180015ef1  jns     short loc_180015EFA
0x180015ef3  mov     edx, 24Ch
0x180015ef8  jmp     short loc_180015E88
0x180015efa  mov     edi, 1
0x180015eff  lea     rcx, [rsp+310h+var_2C8]
0x180015f04  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015f09  mov     rcx, [rsp+310h+var_2E0]
0x180015f0e  test    rcx, rcx
0x180015f11  jz      loc_180015FC7
0x180015f17  mov     rax, [rcx]
0x180015f1a  mov     r8, r14
0x180015f1d  mov     rdx, r15
0x180015f20  mov     rax, [rax]
0x180015f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f28  mov     ebx, eax
0x180015f2a  test    eax, eax
0x180015f2c  jns     loc_180015FC7
0x180015f32  mov     edx, 258h; void *
0x180015f37  mov     r9d, eax; char *
0x180015f3a  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180015f41  mov     rcx, [rbp+218h]; this
0x180015f48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f4d  lea     rcx, [rsp+310h+var_2D0]
0x180015f52  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015f57  lea     rcx, [rsp+310h+var_2E0]
0x180015f5c  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015f61  lea     rcx, [rsp+310h+var_2D8]
0x180015f66  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015f6b  lea     rcx, [rbp+210h+var_290]; this
0x180015f6f  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x180015f74  mov     eax, ebx
0x180015f76  jmp     loc_180016009
0x180015f7b  mov     rbx, [rsp+310h+var_2D8]
0x180015f80  mov     rax, [rbx]
0x180015f83  mov     rsi, [rax+30h]
0x180015f87  mov     rcx, [rsp+310h+var_2E0]
0x180015f8c  mov     [rsp+310h+var_2E0], r12
0x180015f91  test    rcx, rcx
0x180015f94  jz      short loc_180015FA3
0x180015f96  mov     rdx, [rcx]
0x180015f99  mov     rax, [rdx+10h]
0x180015f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fa2  nop
0x180015fa3  lea     rdx, [rsp+310h+var_2E0]
0x180015fa8  mov     rcx, rbx
0x180015fab  mov     rax, rsi
0x180015fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fb3  mov     ebx, eax
0x180015fb5  test    eax, eax
0x180015fb7  jns     loc_180015F09
0x180015fbd  mov     edx, 250h
0x180015fc2  jmp     loc_180015F37
0x180015fc7  lea     rcx, [rsp+310h+var_2D0]
0x180015fcc  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015fd1  lea     rcx, [rsp+310h+var_2E0]
0x180015fd6  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015fdb  lea     rcx, [rsp+310h+var_2D8]
0x180015fe0  call    ??1?$com_ptr_t@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>::~com_ptr_t<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_returncode_policy>(void)
0x180015fe5  cmp     [r14], r12
0x180015fe8  setnz   dl; bool
0x180015feb  lea     r9, [rbp+210h+sourceString]; unsigned __int16 *
0x180015ff2  mov     r8b, dil; bool
0x180015ff5  lea     rcx, [rbp+210h+var_290]; this
0x180015ff9  call    ?Stop@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAX_N0PEBG@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(bool,bool,ushort const *)
0x180015ffe  lea     rcx, [rbp+210h+var_290]; this
0x180016002  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x180016007  xor     eax, eax
0x180016009  mov     rcx, [rbp+210h+var_40]
0x180016010  xor     rcx, rsp; StackCookie
0x180016013  call    __security_check_cookie
0x180016018  add     rsp, 2E0h
0x18001601f  pop     r15
0x180016021  pop     r14
0x180016023  pop     r12
0x180016025  pop     rdi
0x180016026  pop     rsi
0x180016027  pop     rbx
0x180016028  pop     rbp
0x180016029  retn
0x18001602a  xor     r9d, r9d; lpArguments
0x18001602d  xor     r8d, r8d; nNumberOfArguments
0x180016030  lea     edx, [r9+1]; dwExceptionFlags
0x180016034  mov     ecx, 80070216h; dwExceptionCode
0x180016039  call    cs:__imp_RaiseException
```
