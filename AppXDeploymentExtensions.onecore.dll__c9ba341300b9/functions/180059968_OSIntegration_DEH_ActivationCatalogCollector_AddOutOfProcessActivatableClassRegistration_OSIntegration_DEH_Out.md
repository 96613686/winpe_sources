# OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(OSIntegration::DEH::OutOfProcessActivatableClassRegistration *)

- ea: `0x180059968`
- end: `0x180059bb3`
- name: `?AddOutOfProcessActivatableClassRegistration@ActivationCatalogCollector@DEH@OSIntegration@@QEAAJPEAUOutOfProcessActivatableClassRegistration@23@@Z`
- size: `587`
- prototype: `__int64 __fastcall(OSIntegration::DEH::ActivationCatalogCollector *__hidden this, struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180037f64`

## callees

- `0x18000b3bc`
- `0x18003a300`
- `0x180059968`
- `0x180059bbc`
- `0x180059c00`
- `0x18009aff4`
- `0x1800fc0ec`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800599b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x1800599b2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800599d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800599e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059b2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800599d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800599e5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059aa5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059aef`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059b2f`

## string_xrefs

- `0x180059ac2`: `RegistryMapFactory< IExeServerActivatableClassRegistration * >::RegistryMap::Make(&_outOfProcessActivatableClasses)`
- `0x180059b02`: `acid.Initialize(activatableClass->get_ActivatableClassId())`
- `0x180059b7f`: `_outOfProcessActivatableClasses->Insert(acid.Get(), static_cast<IExeServerActivatableClassRegistration*>(activatableClass), &replaced)`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(
        OSIntegration::DEH::ActivationCatalogCollector *this,
        struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *a2)
{
  HSTRING v4; // rbx
  HSTRING *v5; // rax
  HRESULT v6; // edi
  HSTRING v7; // rsi
  void *v8; // rax
  _BYTE *v9; // rdi
  int v10; // esi
  __int64 v11; // rax
  int v12; // eax
  char *v14; // [rsp+28h] [rbp-40h]
  HSTRING string[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+68h] [rbp+0h]
  char v17; // [rsp+78h] [rbp+10h] BYREF
  HSTRING newString; // [rsp+80h] [rbp+18h] BYREF
  HSTRING v19; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  v19 = 0;
  if ( !a2 )
  {
    LODWORD(v14) = -2147024809;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
      "activatableClass",
      v14,
      (int)string[0]);
    return 2147942487LL;
  }
  v5 = (HSTRING *)(*(__int64 (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *, HSTRING *))(*(_QWORD *)a2 + 88LL))(
                    a2,
                    string);
  newString = 0;
  v6 = WindowsDuplicateString(*v5, &newString);
  v7 = 0;
  if ( v6 >= 0 )
  {
    v4 = newString;
    v19 = newString;
    v7 = newString;
    WindowsDeleteString(0);
  }
  if ( string[0] )
    WindowsDeleteString(string[0]);
  if ( v6 < 0 )
  {
    LODWORD(v14) = v6;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
      "acid.Initialize(activatableClass->get_ActivatableClassId())",
      v14,
      (int)string[0]);
    if ( v7 )
      WindowsDeleteString(v4);
    return (unsigned int)v6;
  }
  if ( *((_QWORD *)this + 6) )
  {
LABEL_17:
    v17 = 0;
    v12 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, char *, char *))(**((_QWORD **)this + 6) + 80LL))(
            *((_QWORD *)this + 6),
            v4,
            (char *)a2 + 16,
            &v17);
    v6 = v12;
    if ( v12 >= 0 )
    {
      if ( v4 )
        WindowsDeleteString(v4);
      return 0;
    }
    LODWORD(v14) = v12;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->Insert(acid.Get(), static_cast<IExeServerActivatableClassRegistration*>(activatab"
      "leClass), &replaced)",
      v14,
      (int)string[0]);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(&v19);
    return (unsigned int)v6;
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v8 = operator new(0xA0u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v8 )
  {
    v9 = 0;
LABEL_10:
    v10 = -2147024882;
    goto LABEL_14;
  }
  v11 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(v8);
  v9 = (_BYTE *)v11;
  if ( !v11 )
    goto LABEL_10;
  v10 = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(v11 + 144));
  if ( v10 >= 0 )
  {
    v9[152] = 1;
    *((_QWORD *)this + 6) = v9;
    v9 = 0;
  }
LABEL_14:
  if ( v9 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( v10 >= 0 )
    goto LABEL_17;
  LODWORD(v14) = v10;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x51,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
    "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
    "RegistryMapFactory< IExeServerActivatableClassRegistration * >::RegistryMap::Make(&_outOfProcessActivatableClasses)",
    v14,
    (int)string[0]);
  if ( v4 )
    WindowsDeleteString(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180059968  mov     rax, rsp
0x18005996b  push    rbx
0x18005996c  push    rsi
0x18005996d  push    rdi
0x18005996e  push    r14
0x180059970  push    r15
0x180059972  sub     rsp, 40h
0x180059976  mov     r15, rdx
0x180059979  mov     r14, rcx
0x18005997c  xor     ebx, ebx
0x18005997e  mov     [rax+20h], rbx
0x180059982  test    rdx, rdx
0x180059985  jz      loc_180059B3C
0x18005998b  mov     rax, [rdx]
0x18005998e  lea     rdx, [rsp+68h+string]
0x180059993  mov     rcx, r15
0x180059996  mov     rax, [rax+58h]
0x18005999a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005999f  mov     [rsp+68h+newString], rbx
0x1800599a7  lea     rdx, [rsp+68h+newString]; newString
0x1800599af  mov     rcx, [rax]; string
0x1800599b2  call    cs:__imp_WindowsDuplicateString
0x1800599b8  mov     edi, eax
0x1800599ba  xor     esi, esi
0x1800599bc  test    eax, eax
0x1800599be  js      short loc_1800599DB
0x1800599c0  mov     rbx, [rsp+68h+newString]
0x1800599c8  mov     [rsp+68h+arg_18], rbx
0x1800599d0  mov     rsi, rbx
0x1800599d3  xor     ecx, ecx; string
0x1800599d5  call    cs:__imp_WindowsDeleteString
0x1800599db  mov     rcx, [rsp+68h+string]; string
0x1800599e0  test    rcx, rcx
0x1800599e3  jz      short loc_1800599EB
0x1800599e5  call    cs:__imp_WindowsDeleteString
0x1800599eb  test    edi, edi
0x1800599ed  js      loc_180059AF9
0x1800599f3  cmp     qword ptr [r14+30h], 0
0x1800599f8  jnz     short loc_180059A72
0x1800599fa  lea     rcx, [r14+30h]
0x1800599fe  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180059a03  mov     qword ptr [r14+30h], 0
0x180059a0b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180059a12  mov     ecx, 0A0h; unsigned __int64
0x180059a17  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180059a1c  test    rax, rax
0x180059a1f  jnz     short loc_180059A2A
0x180059a21  xor     edi, edi
0x180059a23  mov     esi, 8007000Eh
0x180059a28  jmp     short loc_180059A59
0x180059a2a  mov     rcx, rax
0x180059a2d  call    ??0?$HashMap@PEAUHSTRING__@@PEAUIExeServerActivatableClassRegistration@Foundation@Windows@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultLifetimeTraits@PEAUIExeServerActivatableClassRegistration@Foundation@Windows@@@9Collections@34@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIExeServerActivatableClassRegistration@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@@9Collections@34@@Internal@Collections@Foundation@Windows@@QEAA@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@6@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission)
0x180059a32  mov     rdi, rax
0x180059a35  test    rax, rax
0x180059a38  jz      short loc_180059A23
0x180059a3a  lea     rcx, [rax+90h]; this
0x180059a41  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x180059a46  mov     esi, eax
0x180059a48  test    eax, eax
0x180059a4a  js      short loc_180059A59
0x180059a4c  mov     byte ptr [rdi+98h], 1
0x180059a53  mov     [r14+30h], rdi
0x180059a57  xor     edi, edi
0x180059a59  test    rdi, rdi
0x180059a5c  jz      short loc_180059A6E
0x180059a5e  mov     rax, [rdi]
0x180059a61  mov     rcx, rdi
0x180059a64  mov     rax, [rax+10h]
0x180059a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a6d  nop
0x180059a6e  test    esi, esi
0x180059a70  js      short loc_180059AB9
0x180059a72  mov     [rsp+68h+arg_8], 0
0x180059a77  mov     rcx, [r14+30h]
0x180059a7b  mov     rax, [rcx]
0x180059a7e  lea     r8, [r15+10h]
0x180059a82  lea     r9, [rsp+68h+arg_8]
0x180059a87  mov     rdx, rbx
0x180059a8a  mov     rax, [rax+50h]
0x180059a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059a93  mov     edi, eax
0x180059a95  test    eax, eax
0x180059a97  js      loc_180059B76
0x180059a9d  test    rbx, rbx
0x180059aa0  jz      short loc_180059AAB
0x180059aa2  mov     rcx, rbx; string
0x180059aa5  call    cs:__imp_WindowsDeleteString
0x180059aab  xor     eax, eax
0x180059aad  add     rsp, 40h
0x180059ab1  pop     r15
0x180059ab3  pop     r14
0x180059ab5  pop     rdi
0x180059ab6  pop     rsi
0x180059ab7  pop     rbx
0x180059ab8  retn
0x180059ab9  mov     rcx, [rsp+68h]; this
0x180059abe  mov     dword ptr [rsp+68h+var_40], esi; char *
0x180059ac2  lea     rax, aRegistrymapfac_1; "RegistryMapFactory< IExeServerActivatab"...
0x180059ac9  mov     [rsp+68h+var_48], rax; char *
0x180059ace  lea     r9, aOsintegrationD_482; "OSIntegration::DEH::ActivationCatalogCo"...
0x180059ad5  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180059adc  mov     edx, 51h ; 'Q'; void *
0x180059ae1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180059ae6  nop
0x180059ae7  test    rbx, rbx
0x180059aea  jz      short loc_180059AF5
0x180059aec  mov     rcx, rbx; string
0x180059aef  call    cs:__imp_WindowsDeleteString
0x180059af5  mov     eax, esi
0x180059af7  jmp     short loc_180059AAD
0x180059af9  mov     rcx, [rsp+68h]; this
0x180059afe  mov     dword ptr [rsp+68h+var_40], edi; char *
0x180059b02  lea     rax, aAcidInitialize; "acid.Initialize(activatableClass->get_A"...
0x180059b09  mov     [rsp+68h+var_48], rax; char *
0x180059b0e  lea     r9, aOsintegrationD_482; "OSIntegration::DEH::ActivationCatalogCo"...
0x180059b15  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180059b1c  mov     edx, 4Eh ; 'N'; void *
0x180059b21  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180059b26  nop
0x180059b27  test    rsi, rsi
0x180059b2a  jz      short loc_180059B35
0x180059b2c  mov     rcx, rbx; string
0x180059b2f  call    cs:__imp_WindowsDeleteString
0x180059b35  mov     eax, edi
0x180059b37  jmp     loc_180059AAD
0x180059b3c  mov     rcx, [rsp+68h]; this
0x180059b41  mov     ebx, 80070057h
0x180059b46  mov     dword ptr [rsp+68h+var_40], ebx; char *
0x180059b4a  lea     rdx, aActivatablecla_3; "activatableClass"
0x180059b51  mov     [rsp+68h+var_48], rdx; char *
0x180059b56  lea     r9, aOsintegrationD_482; "OSIntegration::DEH::ActivationCatalogCo"...
0x180059b5d  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180059b64  mov     edx, 4Ch ; 'L'; void *
0x180059b69  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180059b6e  nop
0x180059b6f  mov     eax, ebx
0x180059b71  jmp     loc_180059AAD
0x180059b76  mov     rcx, [rsp+68h]; this
0x180059b7b  mov     dword ptr [rsp+68h+var_40], edi; char *
0x180059b7f  lea     rax, aOutofprocessac_5; "_outOfProcessActivatableClasses->Insert"...
0x180059b86  mov     [rsp+68h+var_48], rax; char *
0x180059b8b  lea     r9, aOsintegrationD_482; "OSIntegration::DEH::ActivationCatalogCo"...
0x180059b92  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180059b99  mov     edx, 57h ; 'W'; void *
0x180059b9e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180059ba3  nop
0x180059ba4  lea     rcx, [rsp+68h+arg_18]
0x180059bac  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>(void)
0x180059bb1  jmp     short loc_180059B35
```
