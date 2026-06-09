# GetInstalledWorkflowPackageForFamily(ushort const *,Windows::Internal::StateRepository::IPackage * *,Windows::Internal::StateRepository::IApplicationExtension * *)

- ea: `0x18002220c`
- end: `0x1800228b8`
- name: `?GetInstalledWorkflowPackageForFamily@@YAJPEBGPEAPEAUIPackage@StateRepository@Internal@Windows@@PEAPEAUIApplicationExtension@234@@Z`
- size: `1708`
- prototype: `__int64 __fastcall(struct Windows::Internal::StateRepository::IApplicationExtension *, struct Windows::Internal::StateRepository::IPackage **, struct Windows::Internal::StateRepository::IApplicationExtension **)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800217a4`

## callees

- `0x180003ca0`
- `0x1800127a4`
- `0x1800147fc`
- `0x18001cce8`
- `0x18001da30`
- `0x18002220c`
- `0x180023378`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800226d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022488`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022609`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800226d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002228b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022343`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022425`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18002228b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022343`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180022425`

## string_xrefs

- `0x1800227a9`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x1800227be`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x1800227d3`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x1800227e8`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x1800227fc`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180022813`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180022828`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002283d`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180022852`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180022867`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002287b`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180022890`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x1800228a5`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
__int64 __fastcall GetInstalledWorkflowPackageForFamily(
        struct Windows::Internal::StateRepository::IApplicationExtension *a1,
        struct Windows::Internal::StateRepository::IPackage **a2,
        struct Windows::Internal::StateRepository::IApplicationExtension **a3)
{
  int ActivationFactory; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, __int64 *); // rbx
  __int64 v8; // rax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  const char *v14; // r9
  unsigned int i; // esi
  int v16; // eax
  struct Windows::Internal::StateRepository::IPackage *v17; // rdi
  __int64 (__fastcall *v18)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *); // rbx
  int v19; // eax
  int v20; // eax
  int v21; // eax
  unsigned int j; // ebx
  int v23; // eax
  int WorkflowExtensionForApplication; // eax
  struct Windows::Internal::StateRepository::IApplicationExtension *v25; // rax
  struct Windows::Internal::StateRepository::IPackage *v26; // rcx
  __int64 result; // rax
  int v28; // [rsp+20h] [rbp-128h]
  unsigned int v29; // [rsp+30h] [rbp-118h] BYREF
  struct Windows::Internal::StateRepository::IPackage *v30; // [rsp+38h] [rbp-110h] BYREF
  __int64 v31; // [rsp+40h] [rbp-108h] BYREF
  __int64 v32; // [rsp+48h] [rbp-100h] BYREF
  __int64 v33; // [rsp+50h] [rbp-F8h] BYREF
  unsigned int v34; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-E8h] BYREF
  HSTRING string; // [rsp+68h] [rbp-E0h] BYREF
  __int64 v37; // [rsp+70h] [rbp-D8h] BYREF
  struct Windows::Internal::StateRepository::IApplicationExtension *v38; // [rsp+78h] [rbp-D0h] BYREF
  struct Windows::Internal::StateRepository::IApplication *v39; // [rsp+80h] [rbp-C8h] BYREF
  __int64 v40; // [rsp+88h] [rbp-C0h] BYREF
  HSTRING_HEADER v41; // [rsp+90h] [rbp-B8h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-A0h]
  HSTRING_HEADER hstringHeader; // [rsp+B0h] [rbp-98h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-80h]
  HSTRING_HEADER v45; // [rsp+D0h] [rbp-78h] BYREF
  __int64 v46; // [rsp+E8h] [rbp-60h]
  char v47[32]; // [rsp+F0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+0h]

  v38 = a1;
  v33 = 0;
  v46 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &v45,
    L"Windows.Internal.StateRepository.PackageFamily",
    0x2Fu,
    0x2Eu);
  ActivationFactory = RoGetActivationFactory(v46, &GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426, &v33);
  try
  {
    if ( ActivationFactory < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v28);
    v40 = 0;
    v6 = v33;
    v7 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 128LL);
    v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v47, &v38);
    v9 = v7(v6, *(_QWORD *)(v8 + 24), &v40);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x14C,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v9,
        v28);
    v32 = 0;
    v44 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.StateRepository.Package",
      0x29u,
      0x28u);
    v10 = RoGetActivationFactory(v44, &GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419, &v32);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x151,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v10,
        v28);
    v37 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v32 + 400LL))(v32, 0, v40, &v37);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x155,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v11,
        v28);
    v34 = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v37 + 56LL))(v37, &v34);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x159,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v12,
        v28);
    if ( !v34 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15A,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)0x80070490LL,
        v28);
    v31 = 0;
    v42 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v41,
      L"Windows.Internal.StateRepository.Application",
      0x2Du,
      0x2Cu);
    v13 = RoGetActivationFactory(v42, &GUID_07adcc9a_e505_48c2_b471_45af8561f6af, &v31);
    if ( v13 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x15F,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
        (const char *)(unsigned int)v13,
        v28);
    for ( i = 0; i < v34; ++i )
    {
      v30 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IPackage **))(*(_QWORD *)v37 + 48LL))(
              v37,
              i,
              &v30);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x165,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
          (const char *)(unsigned int)v16,
          v28);
      string = 0;
      v17 = v30;
      v18 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, HSTRING *))(*(_QWORD *)v30 + 112LL);
      WindowsDeleteString(0);
      string = 0;
      v19 = v18(v17, &string);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x169,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
          (const char *)(unsigned int)v19,
          v28);
      v35 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, HSTRING, __int64 *))(*(_QWORD *)v31 + 312LL))(
              v31,
              0,
              string,
              &v35);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x16D,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
          (const char *)(unsigned int)v20,
          v28);
      v29 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v35 + 56LL))(v35, &v29);
      if ( v21 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x171,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
          (const char *)(unsigned int)v21,
          v28);
      for ( j = 0; j < v29; ++j )
      {
        v39 = 0;
        v23 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Internal::StateRepository::IApplication **))(*(_QWORD *)v35 + 48LL))(
                v35,
                j,
                &v39);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x177,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
            (const char *)(unsigned int)v23,
            v28);
        v38 = 0;
        WorkflowExtensionForApplication = GetWorkflowExtensionForApplication(v39, &v38);
        if ( WorkflowExtensionForApplication < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x17A,
            (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
            (const char *)(unsigned int)WorkflowExtensionForApplication,
            v28);
        v25 = v38;
        if ( v38 )
        {
          v26 = v30;
          if ( v30 )
          {
            (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *))(*(_QWORD *)v30 + 8LL))(v30);
            v26 = v30;
            v25 = v38;
          }
          *a2 = v26;
          if ( v25 )
          {
            (*(void (__fastcall **)(struct Windows::Internal::StateRepository::IApplicationExtension *))(*(_QWORD *)v25 + 8LL))(v25);
            v25 = v38;
          }
          *a3 = v25;
          if ( v25 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v38);
          if ( v39 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v39);
          if ( v35 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v35);
          WindowsDeleteString(string);
          string = 0;
          if ( v30 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v30);
          v42 = 0;
          if ( v31 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v31);
          if ( v37 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v37);
          v44 = 0;
          if ( v32 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v32);
          if ( v40 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v40);
          v46 = 0;
          if ( v33 )
            winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v33);
          return 0;
        }
        if ( v39 )
          winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v39);
      }
      if ( v35 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v35);
      WindowsDeleteString(string);
      string = 0;
      if ( v30 )
        winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v30);
    }
    v42 = 0;
    if ( v31 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v31);
    if ( v37 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v37);
    v44 = 0;
    if ( v32 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v32);
    if ( v40 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v40);
    v46 = 0;
    if ( v33 )
      winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(&v33);
    result = 1;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x18C,
                           (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18002220c  mov     r11, rsp
0x18002220f  mov     [r11+20h], rbx
0x180022213  push    rsi
0x180022214  push    rdi
0x180022215  push    r12
0x180022217  push    r14
0x180022219  push    r15
0x18002221b  sub     rsp, 120h
0x180022222  mov     rax, cs:__security_cookie
0x180022229  xor     rax, rsp
0x18002222c  mov     [rsp+148h+var_38], rax
0x180022234  mov     r14, r8
0x180022237  mov     r15, rdx
0x18002223a  mov     [rsp+148h+var_D0], rcx
0x18002223f  xor     r12d, r12d
0x180022242  mov     [rsp+148h+var_F8], r12
0x180022247  mov     [r11-60h], r12
0x18002224b  lea     r9d, [r12+2Eh]; unsigned int
0x180022250  lea     r8d, [r12+2Fh]; unsigned int
0x180022255  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_PackageFamily@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18002225c  lea     rcx, [r11-78h]; hstringHeader
0x180022260  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180022265  nop
0x180022266  cmp     [rsp+148h+var_F8], r12
0x18002226b  jz      short loc_180022277
0x18002226d  lea     rcx, [rsp+148h+var_F8]
0x180022272  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022277  lea     r8, [rsp+148h+var_F8]
0x18002227c  lea     rdx, _GUID_86f5b0ee_9560_4d76_a06a_ca4c8bfe4426
0x180022283  mov     rcx, [rsp+148h+var_60]
0x18002228b  call    cs:__imp_RoGetActivationFactory
0x180022291  mov     rcx, [rsp+148h]; this
0x180022299  test    eax, eax
0x18002229b  js      loc_1800227A6
0x1800222a1  mov     [rsp+148h+var_C0], r12
0x1800222a9  mov     rdi, [rsp+148h+var_F8]
0x1800222ae  mov     rax, [rdi]
0x1800222b1  mov     rbx, [rax+80h]
0x1800222b8  lea     rdx, [rsp+148h+var_D0]
0x1800222bd  lea     rcx, [rsp+148h+var_58]
0x1800222c5  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800222ca  nop
0x1800222cb  lea     r8, [rsp+148h+var_C0]
0x1800222d3  mov     rdx, [rax+18h]
0x1800222d7  mov     rcx, rdi
0x1800222da  mov     rax, rbx
0x1800222dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222e2  mov     rcx, [rsp+148h]; this
0x1800222ea  test    eax, eax
0x1800222ec  js      loc_1800227BB
0x1800222f2  mov     [rsp+148h+var_100], r12
0x1800222f7  mov     [rsp+148h+var_80], r12
0x1800222ff  mov     r9d, 28h ; '('; unsigned int
0x180022305  lea     r8d, [r9+1]; unsigned int
0x180022309  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Package@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x180022310  lea     rcx, [rsp+148h+hstringHeader]; hstringHeader
0x180022318  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18002231d  nop
0x18002231e  cmp     [rsp+148h+var_100], r12
0x180022323  jz      short loc_18002232F
0x180022325  lea     rcx, [rsp+148h+var_100]
0x18002232a  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002232f  lea     r8, [rsp+148h+var_100]
0x180022334  lea     rdx, _GUID_0450ce77_af0d_40ac_93fd_1e5d48c89419
0x18002233b  mov     rcx, [rsp+148h+var_80]
0x180022343  call    cs:__imp_RoGetActivationFactory
0x180022349  mov     rcx, [rsp+148h]; this
0x180022351  test    eax, eax
0x180022353  js      loc_1800227D0
0x180022359  mov     [rsp+148h+var_D8], r12
0x18002235e  mov     rcx, [rsp+148h+var_100]
0x180022363  mov     rax, [rcx]
0x180022366  lea     r9, [rsp+148h+var_D8]
0x18002236b  mov     r8, [rsp+148h+var_C0]
0x180022373  xor     edx, edx
0x180022375  mov     rax, [rax+190h]
0x18002237c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022381  mov     rcx, [rsp+148h]; this
0x180022389  test    eax, eax
0x18002238b  js      loc_1800227E5
0x180022391  mov     [rsp+148h+var_F0], r12d
0x180022396  mov     rcx, [rsp+148h+var_D8]
0x18002239b  mov     rax, [rcx]
0x18002239e  lea     rdx, [rsp+148h+var_F0]
0x1800223a3  mov     rax, [rax+38h]
0x1800223a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800223ac  mov     rcx, [rsp+148h]; this
0x1800223b4  test    eax, eax
0x1800223b6  js      loc_1800227F9
0x1800223bc  cmp     [rsp+148h+var_F0], r12d
0x1800223c1  setnbe  al
0x1800223c4  mov     rcx, [rsp+148h]; this
0x1800223cc  test    al, al
0x1800223ce  jz      loc_18002280D
0x1800223d4  mov     [rsp+148h+var_108], r12
0x1800223d9  mov     [rsp+148h+var_A0], r12
0x1800223e1  mov     r9d, 2Ch ; ','; unsigned int
0x1800223e7  lea     r8d, [r9+1]; unsigned int
0x1800223eb  lea     rdx, ?RuntimeClass_Windows_Internal_StateRepository_Application@@3QBGB; "Windows.Internal.StateRepository.Applic"...
0x1800223f2  lea     rcx, [rsp+148h+var_B8]; hstringHeader
0x1800223fa  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800223ff  nop
0x180022400  cmp     [rsp+148h+var_108], r12
0x180022405  jz      short loc_180022411
0x180022407  lea     rcx, [rsp+148h+var_108]
0x18002240c  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022411  lea     r8, [rsp+148h+var_108]
0x180022416  lea     rdx, _GUID_07adcc9a_e505_48c2_b471_45af8561f6af
0x18002241d  mov     rcx, [rsp+148h+var_A0]
0x180022425  call    cs:__imp_RoGetActivationFactory
0x18002242b  mov     rcx, [rsp+148h]; this
0x180022433  test    eax, eax
0x180022435  js      loc_180022825
0x18002243b  mov     esi, r12d
0x18002243e  cmp     esi, [rsp+148h+var_F0]
0x180022442  jnb     loc_1800226FC
0x180022448  mov     [rsp+148h+var_110], r12
0x18002244d  mov     rcx, [rsp+148h+var_D8]
0x180022452  mov     rax, [rcx]
0x180022455  lea     r8, [rsp+148h+var_110]
0x18002245a  mov     edx, esi
0x18002245c  mov     rax, [rax+30h]
0x180022460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022465  mov     rcx, [rsp+148h]; this
0x18002246d  test    eax, eax
0x18002246f  js      loc_18002283A
0x180022475  mov     [rsp+148h+string], r12
0x18002247a  mov     rdi, [rsp+148h+var_110]
0x18002247f  mov     rax, [rdi]
0x180022482  mov     rbx, [rax+70h]
0x180022486  xor     ecx, ecx; string
0x180022488  call    cs:__imp_WindowsDeleteString
0x18002248e  mov     [rsp+148h+string], r12
0x180022493  lea     rdx, [rsp+148h+string]
0x180022498  mov     rcx, rdi
0x18002249b  mov     rax, rbx
0x18002249e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224a3  mov     rcx, [rsp+148h]; this
0x1800224ab  test    eax, eax
0x1800224ad  js      loc_18002284F
0x1800224b3  mov     [rsp+148h+var_E8], r12
0x1800224b8  mov     rcx, [rsp+148h+var_108]
0x1800224bd  mov     rax, [rcx]
0x1800224c0  lea     r9, [rsp+148h+var_E8]
0x1800224c5  mov     r8, [rsp+148h+string]
0x1800224ca  xor     edx, edx
0x1800224cc  mov     rax, [rax+138h]
0x1800224d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224d8  mov     rcx, [rsp+148h]; this
0x1800224e0  test    eax, eax
0x1800224e2  js      loc_180022864
0x1800224e8  mov     [rsp+148h+var_118], r12d
0x1800224ed  mov     rcx, [rsp+148h+var_E8]
0x1800224f2  mov     rax, [rcx]
0x1800224f5  lea     rdx, [rsp+148h+var_118]
0x1800224fa  mov     rax, [rax+38h]
0x1800224fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022503  mov     rcx, [rsp+148h]; this
0x18002250b  test    eax, eax
0x18002250d  js      loc_180022878
0x180022513  mov     ebx, r12d
0x180022516  cmp     ebx, [rsp+148h+var_118]
0x18002251a  jnb     loc_1800226C2
0x180022520  mov     [rsp+148h+var_C8], r12
0x180022528  mov     rcx, [rsp+148h+var_E8]
0x18002252d  mov     rax, [rcx]
0x180022530  lea     r8, [rsp+148h+var_C8]
0x180022538  mov     edx, ebx
0x18002253a  mov     rax, [rax+30h]
0x18002253e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022543  mov     rcx, [rsp+148h]; this
0x18002254b  test    eax, eax
0x18002254d  js      loc_18002288D
0x180022553  mov     [rsp+148h+var_D0], r12
0x180022558  lea     rdx, [rsp+148h+var_D0]; struct Windows::Internal::StateRepository::IApplicationExtension **
0x18002255d  mov     rcx, [rsp+148h+var_C8]; struct Windows::Internal::StateRepository::IApplication *
0x180022565  call    ?GetWorkflowExtensionForApplication@@YAJPEAUIApplication@StateRepository@Internal@Windows@@PEAPEAUIApplicationExtension@234@@Z; GetWorkflowExtensionForApplication(Windows::Internal::StateRepository::IApplication *,Windows::Internal::StateRepository::IApplicationExtension * *)
0x18002256a  mov     rcx, [rsp+148h]; this
0x180022572  test    eax, eax
0x180022574  js      loc_1800228A2
0x18002257a  mov     rax, [rsp+148h+var_D0]
0x18002257f  test    rax, rax
0x180022582  jz      loc_1800226A4
0x180022588  mov     rcx, [rsp+148h+var_110]
0x18002258d  test    rcx, rcx
0x180022590  jz      short loc_1800225A8
0x180022592  mov     rax, [rcx]
0x180022595  mov     rax, [rax+8]
0x180022599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002259e  mov     rcx, [rsp+148h+var_110]
0x1800225a3  mov     rax, [rsp+148h+var_D0]
0x1800225a8  mov     [r15], rcx
0x1800225ab  test    rax, rax
0x1800225ae  jz      short loc_1800225C7
0x1800225b0  mov     rcx, [rax]
0x1800225b3  mov     rdx, [rcx+8]
0x1800225b7  mov     rcx, rax
0x1800225ba  mov     rax, rdx
0x1800225bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800225c2  mov     rax, [rsp+148h+var_D0]
0x1800225c7  mov     [r14], rax
0x1800225ca  test    rax, rax
0x1800225cd  jz      short loc_1800225DA
0x1800225cf  lea     rcx, [rsp+148h+var_D0]
0x1800225d4  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800225d9  nop
0x1800225da  cmp     [rsp+148h+var_C8], r12
0x1800225e2  jz      short loc_1800225F2
0x1800225e4  lea     rcx, [rsp+148h+var_C8]
0x1800225ec  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800225f1  nop
0x1800225f2  cmp     [rsp+148h+var_E8], r12
0x1800225f7  jz      short loc_180022604
0x1800225f9  lea     rcx, [rsp+148h+var_E8]
0x1800225fe  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022603  nop
0x180022604  mov     rcx, [rsp+148h+string]; string
0x180022609  call    cs:__imp_WindowsDeleteString
0x18002260f  mov     [rsp+148h+string], r12
0x180022614  cmp     [rsp+148h+var_110], r12
0x180022619  jz      short loc_180022626
0x18002261b  lea     rcx, [rsp+148h+var_110]
0x180022620  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022625  nop
0x180022626  mov     [rsp+148h+var_A0], r12
0x18002262e  cmp     [rsp+148h+var_108], r12
0x180022633  jz      short loc_180022640
0x180022635  lea     rcx, [rsp+148h+var_108]
0x18002263a  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002263f  nop
0x180022640  cmp     [rsp+148h+var_D8], r12
0x180022645  jz      short loc_180022652
0x180022647  lea     rcx, [rsp+148h+var_D8]
0x18002264c  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022651  nop
0x180022652  mov     [rsp+148h+var_80], r12
0x18002265a  cmp     [rsp+148h+var_100], r12
0x18002265f  jz      short loc_18002266C
0x180022661  lea     rcx, [rsp+148h+var_100]
0x180022666  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002266b  nop
0x18002266c  cmp     [rsp+148h+var_C0], r12
0x180022674  jz      short loc_180022684
0x180022676  lea     rcx, [rsp+148h+var_C0]
0x18002267e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022683  nop
0x180022684  mov     [rsp+148h+var_60], r12
0x18002268c  cmp     [rsp+148h+var_F8], r12
0x180022691  jz      short loc_18002269D
0x180022693  lea     rcx, [rsp+148h+var_F8]
0x180022698  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x18002269d  xor     eax, eax
0x18002269f  jmp     loc_18002277E
0x1800226a4  cmp     [rsp+148h+var_C8], r12
0x1800226ac  jz      short loc_1800226BB
0x1800226ae  lea     rcx, [rsp+148h+var_C8]
0x1800226b6  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800226bb  inc     ebx
0x1800226bd  jmp     loc_180022516
0x1800226c2  cmp     [rsp+148h+var_E8], r12
0x1800226c7  jz      short loc_1800226D4
0x1800226c9  lea     rcx, [rsp+148h+var_E8]
0x1800226ce  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800226d3  nop
0x1800226d4  mov     rcx, [rsp+148h+string]; string
0x1800226d9  call    cs:__imp_WindowsDeleteString
0x1800226df  mov     [rsp+148h+string], r12
0x1800226e4  cmp     [rsp+148h+var_110], r12
0x1800226e9  jz      short loc_1800226F5
0x1800226eb  lea     rcx, [rsp+148h+var_110]
0x1800226f0  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x1800226f5  inc     esi
0x1800226f7  jmp     loc_18002243E
0x1800226fc  mov     [rsp+148h+var_A0], r12
0x180022704  cmp     [rsp+148h+var_108], r12
0x180022709  jz      short loc_180022716
0x18002270b  lea     rcx, [rsp+148h+var_108]
0x180022710  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022715  nop
0x180022716  cmp     [rsp+148h+var_D8], r12
0x18002271b  jz      short loc_180022728
0x18002271d  lea     rcx, [rsp+148h+var_D8]
0x180022722  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022727  nop
0x180022728  mov     [rsp+148h+var_80], r12
0x180022730  cmp     [rsp+148h+var_100], r12
0x180022735  jz      short loc_180022742
0x180022737  lea     rcx, [rsp+148h+var_100]
0x18002273c  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022741  nop
0x180022742  cmp     [rsp+148h+var_C0], r12
0x18002274a  jz      short loc_18002275A
0x18002274c  lea     rcx, [rsp+148h+var_C0]
0x180022754  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
0x180022759  nop
0x18002275a  mov     [rsp+148h+var_60], r12
0x180022762  cmp     [rsp+148h+var_F8], r12
0x180022767  jz      short loc_180022773
0x180022769  lea     rcx, [rsp+148h+var_F8]
0x18002276e  call    ?unconditional_release_ref@?$com_ptr@VProtocolActivatedEventArgsImpl@@@winrt@@AEAAXXZ; winrt::com_ptr<ProtocolActivatedEventArgsImpl>::unconditional_release_ref(void)
  ... truncated ...
```
