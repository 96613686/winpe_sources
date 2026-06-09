# Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &,void * *)

- ea: `0x18002c538`
- end: `0x18002cabd`
- name: `?TryActivateContractExtensionInternal@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@34@AEBU_GUID@@PEAPEAX@Z`
- size: `1413`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022b18`

## callees

- `0x1800049a0`
- `0x180005858`
- `0x18000c964`
- `0x18001e61c`
- `0x180020728`
- `0x1800228c8`
- `0x18002a990`
- `0x18002b3f4`
- `0x18002c538`
- `0x18002d124`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c6bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c6bf`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c6de`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002c6de`

## string_xrefs

- `0x18002c654`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18002c6f4`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18002c774`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18002c83a`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18002c8ff`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18002c9b2`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x18002c582`: `TryActivateContractExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::TryActivateContractExtensionInternal(
        HSTRING a1,
        unsigned int a2,
        __int64 a3,
        _QWORD *a4)
{
  unsigned __int16 *v7; // r8
  int v8; // eax
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  bool v11; // di
  unsigned __int64 v12; // rdx
  HRESULT v13; // eax
  int v14; // edx
  unsigned int v15; // r8d
  int ActivationFactory; // eax
  int v17; // eax
  __int64 (__fastcall *v18)(__int64, HSTRING, __int64, __int64 *); // rsi
  __int64 v19; // rbx
  int v20; // eax
  int v21; // edi
  __int64 v22; // r9
  int v23; // eax
  __int64 (__fastcall *v25)(__int64, __int64 *); // rsi
  int v26; // eax
  const struct _GUID *v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+20h] [rbp-E0h]
  __int64 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+70h] [rbp-90h] BYREF
  void **v36; // [rsp+80h] [rbp-80h] BYREF
  int v37; // [rsp+88h] [rbp-78h] BYREF
  char v38; // [rsp+8Ch] [rbp-74h]
  int v39; // [rsp+B0h] [rbp-50h] BYREF
  const char *v40; // [rsp+B8h] [rbp-48h]
  __int64 v41; // [rsp+C0h] [rbp-40h]
  char v42; // [rsp+C8h] [rbp-38h]
  int v43; // [rsp+D0h] [rbp-30h]
  _BYTE v44[152]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v45; // [rsp+170h] [rbp+70h]
  int v46; // [rsp+180h] [rbp+80h]
  __int64 v47; // [rsp+188h] [rbp+88h]
  int *v48; // [rsp+190h] [rbp+90h]
  __int64 v49; // [rsp+198h] [rbp+98h]
  __int64 v50; // [rsp+1A0h] [rbp+A0h]
  void ***v51; // [rsp+1A8h] [rbp+A8h]
  __int64 v52; // [rsp+1B0h] [rbp+B0h]
  int v53; // [rsp+1B8h] [rbp+B8h]
  int *v54; // [rsp+1C0h] [rbp+C0h]
  char v55; // [rsp+1C8h] [rbp+C8h]
  HSTRING__ sourceString; // [rsp+1D0h] [rbp+D0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v32 = a2;
  v37 = 0;
  v38 = 0;
  v42 = 0;
  v39 = 0;
  v40 = "TryActivateContractExtension";
  v41 = 0;
  v43 = 0;
  v45 = 0;
  memset_0(v44, 0, sizeof(v44));
  v46 = 1;
  v47 = 0;
  v48 = &v37;
  v49 = 0;
  v50 = 0;
  v51 = &v36;
  v52 = 0;
  v53 = 0;
  v54 = &v39;
  v55 = 0;
  v36 = &Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable';
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(
    &v36,
    a1,
    a2,
    &GUID_30b590d9_f894_4572_a394_99378a14d7d8);
  *a4 = 0;
  v8 = Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(
         a1,
         &sourceString,
         v7,
         (unsigned __int64)(v48 + 2),
         v27);
  v10 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23E,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
      (const char *)(unsigned int)v8,
      v28);
LABEL_42:
    Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)&v36);
    return v10;
  }
  v11 = 0;
  if ( LOWORD(sourceString.unused) )
  {
    v30 = 0;
    v12 = -1;
    do
      ++v12;
    while ( *((_WORD *)&sourceString.unused + v12) );
    if ( v12 > 0xFFFFFFFF )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v12, v9);
      __debugbreak();
    }
    if ( (int)v12 + 1 < (unsigned int)v12 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)0x80070216LL, v12, v9);
      JUMPOUT(0x18002CABCLL);
    }
    v13 = WindowsCreateStringReference((PCWSTR)&sourceString, v12, &hstringHeader, &string);
    if ( v13 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v13, v14, v15);
      __debugbreak();
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_00000035_0000_0000_c000_000000000046, &v30);
    v10 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x242,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
        (const char *)(unsigned int)ActivationFactory,
        v28);
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      goto LABEL_42;
    }
    v29 = 0;
    v31 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v30)(
           v30,
           &GUID_da805a35_961f_4194_a4bb_e9e86347d589,
           &v31) < 0 )
    {
      v25 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 48LL);
      v29 = 0;
      v26 = v25(v30, &v29);
      v10 = v26;
      if ( v26 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x250,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v26,
          v28);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        goto LABEL_42;
      }
    }
    else
    {
      v33 = 0;
      v17 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(
              &v33,
              &v32);
      v10 = v17;
      if ( v17 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24B,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v17,
          v28);
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        goto LABEL_42;
      }
      v18 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, __int64 *))(*(_QWORD *)v31 + 48LL);
      v29 = 0;
      v19 = v33;
      v20 = v18(v31, a1, v33, &v29);
      v21 = v20;
      if ( v20 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x24C,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v20,
          v28);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        v10 = v21;
        goto LABEL_42;
      }
      v11 = 1;
      if ( v19 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v22 = v29;
    if ( v29 )
    {
      v23 = (**(__int64 (__fastcall ***)(__int64, GUID *, _QWORD *))v29)(
              v29,
              &GUID_30b590d9_f894_4572_a394_99378a14d7d8,
              a4);
      v10 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x258,
          (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
          (const char *)(unsigned int)v23,
          v28);
        if ( v31 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v29 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
        if ( v30 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        goto LABEL_42;
      }
      v22 = v29;
    }
    if ( v31 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      v22 = v29;
    }
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  }
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::Stop(
    (Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)&v36,
    *a4 != 0,
    v11,
    (const unsigned __int16 *)&sourceString);
  Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension((Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension *)&v36);
  return 0;
}

```

## disassembly

```asm
0x18002c538  push    rbp
0x18002c53a  push    rbx
0x18002c53b  push    rsi
0x18002c53c  push    rdi
0x18002c53d  push    r12
0x18002c53f  push    r14
0x18002c541  push    r15
0x18002c543  lea     rbp, [rsp-1E0h]
0x18002c54b  sub     rsp, 2E0h
0x18002c552  mov     rax, cs:__security_cookie
0x18002c559  xor     rax, rsp
0x18002c55c  mov     [rbp+210h+var_40], rax
0x18002c563  mov     r14, r9
0x18002c566  mov     ebx, edx
0x18002c568  mov     r15, rcx
0x18002c56b  mov     [rsp+310h+var_2C8], edx
0x18002c56f  xor     r12d, r12d
0x18002c572  mov     [rbp+210h+var_288], r12d
0x18002c576  mov     [rbp+210h+var_284], r12b
0x18002c57a  mov     [rbp+210h+var_248], r12b
0x18002c57e  mov     [rbp+210h+var_260], r12d
0x18002c582  lea     rax, aTryactivatecon; "TryActivateContractExtension"
0x18002c589  mov     [rbp+210h+var_258], rax
0x18002c58d  mov     [rbp+210h+var_250], r12
0x18002c591  mov     [rbp+210h+var_240], r12d
0x18002c595  xorps   xmm0, xmm0
0x18002c598  movdqa  [rbp+210h+var_1A0], xmm0
0x18002c59d  xor     edx, edx; Val
0x18002c59f  mov     r8d, 98h; Size
0x18002c5a5  lea     rcx, [rbp+210h+var_238]; void *
0x18002c5a9  call    memset_0
0x18002c5ae  mov     [rbp+210h+var_190], 1
0x18002c5b8  xor     eax, eax
0x18002c5ba  mov     [rbp+210h+var_188], rax
0x18002c5c1  lea     rax, [rbp+210h+var_288]
0x18002c5c5  mov     [rbp+210h+var_180], rax
0x18002c5cc  mov     [rbp+210h+var_178], r12
0x18002c5d3  mov     [rbp+210h+var_170], r12
0x18002c5da  lea     rax, [rbp+210h+var_290]
0x18002c5de  mov     [rbp+210h+var_168], rax
0x18002c5e5  mov     [rbp+210h+var_160], r12
0x18002c5ec  mov     [rbp+210h+var_158], r12d
0x18002c5f3  lea     rax, [rbp+210h+var_260]
0x18002c5f7  mov     [rbp+210h+var_150], rax
0x18002c5fe  mov     [rbp+210h+var_148], r12b
0x18002c605  lea     rax, ??_7TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@6B@; const Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::`vftable'
0x18002c60c  mov     [rbp+210h+var_290], rax
0x18002c610  lea     r9, _GUID_30b590d9_f894_4572_a394_99378a14d7d8
0x18002c617  mov     r8d, ebx
0x18002c61a  mov     rdx, r15
0x18002c61d  lea     rcx, [rbp+210h+var_290]
0x18002c621  call    ?StartActivity@TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAAXPEAUHSTRING__@@UWindowId@WindowManagement@ApplicationModel@56@AEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::StartActivity(HSTRING__ *,Windows::Internal::ApplicationModel::WindowManagement::WindowId,_GUID const &)
0x18002c626  nop
0x18002c627  mov     [r14], r12
0x18002c62a  mov     r9, [rbp+210h+var_180]
0x18002c631  add     r9, 8; unsigned __int64
0x18002c635  lea     rdx, [rbp+210h+sourceString]; HSTRING
0x18002c63c  mov     rcx, r15; string
0x18002c63f  call    ?TryLookupExtensionPointImplementationAcid@Details@PlatformExtensions@Internal@Windows@@YAJPEAUHSTRING__@@PEAG_KPEBU_GUID@@@Z; Windows::Internal::PlatformExtensions::Details::TryLookupExtensionPointImplementationAcid(HSTRING__ *,ushort *,unsigned __int64,_GUID const *)
0x18002c644  mov     ebx, eax
0x18002c646  test    eax, eax
0x18002c648  jns     short loc_18002C66A
0x18002c64a  mov     rcx, [rbp+218h]; this
0x18002c651  mov     r9d, eax; char *
0x18002c654  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002c65b  mov     edx, 23Eh; void *
0x18002c660  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c665  jmp     loc_18002C956
0x18002c66a  mov     dil, r12b
0x18002c66d  cmp     word ptr [rbp+210h+sourceString.unused], r12w
0x18002c675  jz      loc_18002CA5A
0x18002c67b  mov     [rsp+310h+var_2D8], r12
0x18002c680  lea     rax, [rbp+210h+sourceString]
0x18002c687  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18002c68b  inc     rdx; int
0x18002c68e  cmp     [rax+rdx*2], r12w
0x18002c693  jnz     short loc_18002C68B
0x18002c695  mov     eax, 0FFFFFFFFh
0x18002c69a  cmp     rdx, rax
0x18002c69d  ja      loc_18002CAA7
0x18002c6a3  lea     eax, [rdx+1]
0x18002c6a6  cmp     eax, edx
0x18002c6a8  jb      loc_18002CAB2
0x18002c6ae  lea     r9, [rsp+310h+string]; string
0x18002c6b3  lea     r8, [rsp+310h+hstringHeader]; hstringHeader
0x18002c6b8  lea     rcx, [rbp+210h+sourceString]; sourceString
0x18002c6bf  call    cs:__imp_WindowsCreateStringReference
0x18002c6c5  test    eax, eax
0x18002c6c7  js      loc_18002CA9F
0x18002c6cd  lea     r8, [rsp+310h+var_2D8]
0x18002c6d2  lea     rdx, _GUID_00000035_0000_0000_c000_000000000046
0x18002c6d9  mov     rcx, [rsp+310h+string]
0x18002c6de  call    cs:__imp_RoGetActivationFactory
0x18002c6e4  mov     ebx, eax
0x18002c6e6  test    eax, eax
0x18002c6e8  jns     short loc_18002C722
0x18002c6ea  mov     rcx, [rbp+218h]; this
0x18002c6f1  mov     r9d, eax; char *
0x18002c6f4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002c6fb  mov     edx, 242h; void *
0x18002c700  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c705  nop
0x18002c706  mov     rcx, [rsp+310h+var_2D8]
0x18002c70b  test    rcx, rcx
0x18002c70e  jz      short loc_18002C71D
0x18002c710  mov     rax, [rcx]
0x18002c713  mov     rax, [rax+10h]
0x18002c717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c71c  nop
0x18002c71d  jmp     loc_18002C956
0x18002c722  mov     [rsp+310h+var_2E0], r12
0x18002c727  mov     [rsp+310h+var_2D0], r12
0x18002c72c  mov     rcx, [rsp+310h+var_2D8]
0x18002c731  mov     rax, [rcx]
0x18002c734  lea     r8, [rsp+310h+var_2D0]
0x18002c739  lea     rdx, _GUID_da805a35_961f_4194_a4bb_e9e86347d589
0x18002c740  mov     rax, [rax]
0x18002c743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c748  test    eax, eax
0x18002c74a  js      loc_18002C966
0x18002c750  mov     [rsp+310h+var_2C0], r12
0x18002c755  lea     rdx, [rsp+310h+var_2C8]
0x18002c75a  lea     rcx, [rsp+310h+var_2C0]
0x18002c75f  call    ??$MakeAndInitialize@VActivationFactoryContractRedirectorContext@Details@PlatformExtensions@Internal@Windows@@UIActivationFactoryContractRedirectorContext@Contracts@Foundation@45@AEAUWindowId@WindowManagement@ApplicationModel@45@@Details@WRL@Microsoft@@YAJPEAPEAUIActivationFactoryContractRedirectorContext@Contracts@Foundation@Internal@Windows@@AEAUWindowId@WindowManagement@ApplicationModel@67@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::PlatformExtensions::Details::ActivationFactoryContractRedirectorContext,Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext,Windows::Internal::ApplicationModel::WindowManagement::WindowId &>(Windows::Internal::Foundation::Contracts::IActivationFactoryContractRedirectorContext * *,Windows::Internal::ApplicationModel::WindowManagement::WindowId &)
0x18002c764  mov     ebx, eax
0x18002c766  test    eax, eax
0x18002c768  jns     short loc_18002C7E7
0x18002c76a  mov     rcx, [rbp+218h]; this
0x18002c771  mov     r9d, eax; char *
0x18002c774  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002c77b  mov     edx, 24Bh; void *
0x18002c780  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c785  nop
0x18002c786  mov     rcx, [rsp+310h+var_2C0]
0x18002c78b  test    rcx, rcx
0x18002c78e  jz      short loc_18002C79D
0x18002c790  mov     rax, [rcx]
0x18002c793  mov     rax, [rax+10h]
0x18002c797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c79c  nop
0x18002c79d  mov     rcx, [rsp+310h+var_2D0]
0x18002c7a2  test    rcx, rcx
0x18002c7a5  jz      short loc_18002C7B4
0x18002c7a7  mov     rax, [rcx]
0x18002c7aa  mov     rax, [rax+10h]
0x18002c7ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7b3  nop
0x18002c7b4  mov     rcx, [rsp+310h+var_2E0]
0x18002c7b9  test    rcx, rcx
0x18002c7bc  jz      short loc_18002C7CB
0x18002c7be  mov     rax, [rcx]
0x18002c7c1  mov     rax, [rax+10h]
0x18002c7c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7ca  nop
0x18002c7cb  mov     rcx, [rsp+310h+var_2D8]
0x18002c7d0  test    rcx, rcx
0x18002c7d3  jz      short loc_18002C7E2
0x18002c7d5  mov     rax, [rcx]
0x18002c7d8  mov     rax, [rax+10h]
0x18002c7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c7e1  nop
0x18002c7e2  jmp     loc_18002C956
0x18002c7e7  mov     rdi, [rsp+310h+var_2D0]
0x18002c7ec  mov     rax, [rdi]
0x18002c7ef  mov     rsi, [rax+30h]
0x18002c7f3  mov     rcx, [rsp+310h+var_2E0]
0x18002c7f8  mov     [rsp+310h+var_2E0], r12
0x18002c7fd  test    rcx, rcx
0x18002c800  jz      short loc_18002C80F
0x18002c802  mov     rax, [rcx]
0x18002c805  mov     rax, [rax+10h]
0x18002c809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c80e  nop
0x18002c80f  lea     r9, [rsp+310h+var_2E0]
0x18002c814  mov     rbx, [rsp+310h+var_2C0]
0x18002c819  mov     r8, rbx
0x18002c81c  mov     rdx, r15
0x18002c81f  mov     rcx, rdi
0x18002c822  mov     rax, rsi
0x18002c825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c82a  mov     edi, eax
0x18002c82c  test    eax, eax
0x18002c82e  jns     short loc_18002C8AD
0x18002c830  mov     rcx, [rbp+218h]; this
0x18002c837  mov     r9d, eax; char *
0x18002c83a  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002c841  mov     edx, 24Ch; void *
0x18002c846  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c84b  nop
0x18002c84c  test    rbx, rbx
0x18002c84f  jz      short loc_18002C861
0x18002c851  mov     rax, [rbx]
0x18002c854  mov     rcx, rbx
0x18002c857  mov     rax, [rax+10h]
0x18002c85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c860  nop
0x18002c861  mov     rcx, [rsp+310h+var_2D0]
0x18002c866  test    rcx, rcx
0x18002c869  jz      short loc_18002C878
0x18002c86b  mov     rax, [rcx]
0x18002c86e  mov     rax, [rax+10h]
0x18002c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c877  nop
0x18002c878  mov     rcx, [rsp+310h+var_2E0]
0x18002c87d  test    rcx, rcx
0x18002c880  jz      short loc_18002C88F
0x18002c882  mov     rax, [rcx]
0x18002c885  mov     rax, [rax+10h]
0x18002c889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c88e  nop
0x18002c88f  mov     rcx, [rsp+310h+var_2D8]
0x18002c894  test    rcx, rcx
0x18002c897  jz      short loc_18002C8A6
0x18002c899  mov     rax, [rcx]
0x18002c89c  mov     rax, [rax+10h]
0x18002c8a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8a5  nop
0x18002c8a6  mov     ebx, edi
0x18002c8a8  jmp     loc_18002C956
0x18002c8ad  mov     dil, 1
0x18002c8b0  test    rbx, rbx
0x18002c8b3  jz      short loc_18002C8C5
0x18002c8b5  mov     rax, [rbx]
0x18002c8b8  mov     rcx, rbx
0x18002c8bb  mov     rax, [rax+10h]
0x18002c8bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8c4  nop
0x18002c8c5  mov     r9, [rsp+310h+var_2E0]
0x18002c8ca  test    r9, r9
0x18002c8cd  jz      loc_18002CA13
0x18002c8d3  mov     rax, [r9]
0x18002c8d6  mov     r8, r14
0x18002c8d9  lea     rdx, _GUID_30b590d9_f894_4572_a394_99378a14d7d8
0x18002c8e0  mov     rcx, r9
0x18002c8e3  mov     rax, [rax]
0x18002c8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c8eb  mov     ebx, eax
0x18002c8ed  test    eax, eax
0x18002c8ef  jns     loc_18002CA0E
0x18002c8f5  mov     rcx, [rbp+218h]; this
0x18002c8fc  mov     r9d, eax; char *
0x18002c8ff  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002c906  mov     edx, 258h; void *
0x18002c90b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c910  nop
0x18002c911  mov     rcx, [rsp+310h+var_2D0]
0x18002c916  test    rcx, rcx
0x18002c919  jz      short loc_18002C928
0x18002c91b  mov     rax, [rcx]
0x18002c91e  mov     rax, [rax+10h]
0x18002c922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c927  nop
0x18002c928  mov     rcx, [rsp+310h+var_2E0]
0x18002c92d  test    rcx, rcx
0x18002c930  jz      short loc_18002C93F
0x18002c932  mov     rax, [rcx]
0x18002c935  mov     rax, [rax+10h]
0x18002c939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c93e  nop
0x18002c93f  mov     rcx, [rsp+310h+var_2D8]
0x18002c944  test    rcx, rcx
0x18002c947  jz      short loc_18002C956
0x18002c949  mov     rax, [rcx]
0x18002c94c  mov     rax, [rax+10h]
0x18002c950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c955  nop
0x18002c956  lea     rcx, [rbp+210h+var_290]; this
0x18002c95a  call    ??1TryActivateContractExtension@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@QEAA@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::TryActivateContractExtension::~TryActivateContractExtension(void)
0x18002c95f  mov     eax, ebx
0x18002c961  jmp     loc_18002CA7E
0x18002c966  mov     rbx, [rsp+310h+var_2D8]
0x18002c96b  mov     rax, [rbx]
0x18002c96e  mov     rsi, [rax+30h]
0x18002c972  mov     rcx, [rsp+310h+var_2E0]
0x18002c977  mov     [rsp+310h+var_2E0], r12
0x18002c97c  test    rcx, rcx
0x18002c97f  jz      short loc_18002C98E
0x18002c981  mov     rdx, [rcx]
0x18002c984  mov     rax, [rdx+10h]
0x18002c988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c98d  nop
0x18002c98e  lea     rdx, [rsp+310h+var_2E0]
0x18002c993  mov     rcx, rbx
0x18002c996  mov     rax, rsi
0x18002c999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c99e  mov     ebx, eax
0x18002c9a0  test    eax, eax
0x18002c9a2  jns     loc_18002C8C5
0x18002c9a8  mov     rcx, [rbp+218h]; this
0x18002c9af  mov     r9d, eax; char *
0x18002c9b2  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18002c9b9  mov     edx, 250h; void *
0x18002c9be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002c9c3  nop
0x18002c9c4  mov     rcx, [rsp+310h+var_2D0]
0x18002c9c9  test    rcx, rcx
0x18002c9cc  jz      short loc_18002C9DB
0x18002c9ce  mov     rax, [rcx]
0x18002c9d1  mov     rax, [rax+10h]
0x18002c9d5  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
