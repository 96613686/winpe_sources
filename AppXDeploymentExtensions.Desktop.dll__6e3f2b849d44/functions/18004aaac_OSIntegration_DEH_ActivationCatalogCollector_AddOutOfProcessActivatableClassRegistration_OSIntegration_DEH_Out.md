# OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(OSIntegration::DEH::OutOfProcessActivatableClassRegistration *)

- ea: `0x18004aaac`
- end: `0x18004ad07`
- name: `?AddOutOfProcessActivatableClassRegistration@ActivationCatalogCollector@DEH@OSIntegration@@QEAAJPEAUOutOfProcessActivatableClassRegistration@23@@Z`
- size: `603`
- prototype: `__int64 __fastcall(OSIntegration::DEH::ActivationCatalogCollector *__hidden this, struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800390dc`

## callees

- `0x180006970`
- `0x180036e58`
- `0x18004a448`
- `0x18004aaac`
- `0x18006a4c8`
- `0x180081d70`
- `0x1800ba02c`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004ab2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18004ab2b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ab54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ab6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004abb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ac7c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ab54`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ab6a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004abb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004ac7c`

## string_xrefs

- `0x18004ac4f`: `RegistryMapFactory< IExeServerActivatableClassRegistration * >::RegistryMap::Make(&_outOfProcessActivatableClasses)`
- `0x18004acbc`: `_outOfProcessActivatableClasses->Insert(acid.Get(), static_cast<IExeServerActivatableClassRegistration*>(activatableClass), &replaced)`
- `0x18004ab83`: `acid.Initialize(activatableClass->get_ActivatableClassId())`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration(
        OSIntegration::DEH::ActivationCatalogCollector *this,
        struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *a2)
{
  HSTRING v4; // rbx
  unsigned int v5; // ebx
  HSTRING *v6; // rax
  HRESULT v7; // edi
  HSTRING v8; // rsi
  bool v9; // zf
  void *v11; // rax
  __int64 v12; // rax
  _BYTE *v13; // rdi
  int v14; // esi
  int v15; // eax
  char *v16; // [rsp+28h] [rbp-40h]
  HSTRING string[7]; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+68h] [rbp+0h]
  char v19; // [rsp+78h] [rbp+10h] BYREF
  HSTRING newString; // [rsp+80h] [rbp+18h] BYREF
  HSTRING v21; // [rsp+88h] [rbp+20h] BYREF

  v4 = 0;
  v21 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
    LODWORD(v16) = -2147024809;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x4C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
      "activatableClass",
      v16,
      (int)string[0]);
LABEL_28:
    Windows::Internal::String::~String((Windows::Internal::String *)&v21);
    return v5;
  }
  v6 = (HSTRING *)(*(__int64 (__fastcall **)(struct OSIntegration::DEH::OutOfProcessActivatableClassRegistration *, HSTRING *))(*(_QWORD *)a2 + 88LL))(
                    a2,
                    string);
  newString = 0;
  v7 = WindowsDuplicateString(*v6, &newString);
  v8 = 0;
  if ( v7 >= 0 )
  {
    v4 = newString;
    v21 = newString;
    v8 = newString;
    WindowsDeleteString(0);
  }
  if ( string[0] )
    WindowsDeleteString(string[0]);
  if ( v7 < 0 )
  {
    LODWORD(v16) = v7;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
      "acid.Initialize(activatableClass->get_ActivatableClassId())",
      v16,
      (int)string[0]);
    v9 = v8 == 0;
LABEL_9:
    if ( !v9 )
      WindowsDeleteString(v4);
    return (unsigned int)v7;
  }
  if ( *((_QWORD *)this + 6) )
  {
LABEL_25:
    v19 = 0;
    v15 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, char *, char *))(**((_QWORD **)this + 6) + 80LL))(
            *((_QWORD *)this + 6),
            v4,
            (char *)a2 + 16,
            &v19);
    v7 = v15;
    if ( v15 >= 0 )
    {
      v5 = 0;
      goto LABEL_28;
    }
    LODWORD(v16) = v15;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x57,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
      "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
      "_outOfProcessActivatableClasses->Insert(acid.Get(), static_cast<IExeServerActivatableClassRegistration*>(activatab"
      "leClass), &replaced)",
      v16,
      (int)string[0]);
    v9 = v4 == 0;
    goto LABEL_9;
  }
  Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease((char *)this + 48);
  *((_QWORD *)this + 6) = 0;
  v11 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v11 )
  {
    v13 = 0;
    goto LABEL_18;
  }
  v12 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(v11);
  v13 = (_BYTE *)v12;
  if ( !v12 )
  {
LABEL_18:
    v14 = -2147024882;
    goto LABEL_19;
  }
  v14 = XWinRT::SecureVersionTag::TagManager::Initialize((XWinRT::SecureVersionTag::TagManager *)(v12 + 144));
  if ( v14 >= 0 )
  {
    v13[152] = 1;
    *((_QWORD *)this + 6) = v13;
    v13 = 0;
  }
LABEL_19:
  if ( v13 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v13 + 16LL))(v13);
  if ( v14 >= 0 )
    goto LABEL_25;
  LODWORD(v16) = v14;
  wil::details::in1diag5::Return_Hr(
    retaddr,
    (void *)0x51,
    (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\activationcatalogverifier.cpp",
    "OSIntegration::DEH::ActivationCatalogCollector::AddOutOfProcessActivatableClassRegistration",
    "RegistryMapFactory< IExeServerActivatableClassRegistration * >::RegistryMap::Make(&_outOfProcessActivatableClasses)",
    v16,
    (int)string[0]);
  if ( v4 )
    WindowsDeleteString(v4);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18004aaac  mov     rax, rsp
0x18004aaaf  push    rbx
0x18004aab0  push    rsi
0x18004aab1  push    rdi
0x18004aab2  push    r14
0x18004aab4  push    r15
0x18004aab6  sub     rsp, 40h
0x18004aaba  mov     r15, rdx
0x18004aabd  mov     r14, rcx
0x18004aac0  xor     ebx, ebx
0x18004aac2  mov     [rax+20h], rbx
0x18004aac6  test    rdx, rdx
0x18004aac9  jnz     short loc_18004AB00
0x18004aacb  mov     rcx, [rsp+68h]; this
0x18004aad0  mov     ebx, 80070057h
0x18004aad5  mov     [rax-40h], ebx
0x18004aad8  lea     rax, aActivatablecla_1; "activatableClass"
0x18004aadf  mov     [rsp+68h+var_48], rax; char *
0x18004aae4  lea     r9, aOsintegrationD_349; "OSIntegration::DEH::ActivationCatalogCo"...
0x18004aaeb  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18004aaf2  lea     edx, [r15+4Ch]; void *
0x18004aaf6  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004aafb  jmp     loc_18004ACEB
0x18004ab00  mov     rax, [rdx]
0x18004ab03  lea     rdx, [rsp+68h+string]
0x18004ab08  mov     rcx, r15
0x18004ab0b  mov     rax, [rax+58h]
0x18004ab0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab14  mov     [rsp+68h+newString], 0
0x18004ab20  lea     rdx, [rsp+68h+newString]; newString
0x18004ab28  mov     rcx, [rax]; string
0x18004ab2b  call    cs:__imp_WindowsDuplicateString
0x18004ab32  nop     dword ptr [rax+rax+00h]
0x18004ab37  mov     edi, eax
0x18004ab39  xor     esi, esi
0x18004ab3b  test    eax, eax
0x18004ab3d  js      short loc_18004AB60
0x18004ab3f  mov     rbx, [rsp+68h+newString]
0x18004ab47  mov     [rsp+68h+arg_18], rbx
0x18004ab4f  mov     rsi, rbx
0x18004ab52  xor     ecx, ecx; string
0x18004ab54  call    cs:__imp_WindowsDeleteString
0x18004ab5b  nop     dword ptr [rax+rax+00h]
0x18004ab60  mov     rcx, [rsp+68h+string]; string
0x18004ab65  test    rcx, rcx
0x18004ab68  jz      short loc_18004AB76
0x18004ab6a  call    cs:__imp_WindowsDeleteString
0x18004ab71  nop     dword ptr [rax+rax+00h]
0x18004ab76  test    edi, edi
0x18004ab78  jns     short loc_18004ABC3
0x18004ab7a  mov     rcx, [rsp+68h]; this
0x18004ab7f  mov     dword ptr [rsp+68h+var_40], edi; char *
0x18004ab83  lea     rax, aAcidInitialize; "acid.Initialize(activatableClass->get_A"...
0x18004ab8a  mov     [rsp+68h+var_48], rax; char *
0x18004ab8f  lea     r9, aOsintegrationD_349; "OSIntegration::DEH::ActivationCatalogCo"...
0x18004ab96  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18004ab9d  mov     edx, 4Eh ; 'N'; void *
0x18004aba2  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004aba7  nop
0x18004aba8  test    rsi, rsi
0x18004abab  jz      short loc_18004ABBC
0x18004abad  mov     rcx, rbx; string
0x18004abb0  call    cs:__imp_WindowsDeleteString
0x18004abb7  nop     dword ptr [rax+rax+00h]
0x18004abbc  mov     eax, edi
0x18004abbe  jmp     loc_18004ACFA
0x18004abc3  cmp     qword ptr [r14+30h], 0
0x18004abc8  jnz     loc_18004AC8C
0x18004abce  lea     rcx, [r14+30h]
0x18004abd2  call    ?InternalRelease@?$ComPtr@UIComProxyStubRegistration@DEH@OSIntegration@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<OSIntegration::DEH::IComProxyStubRegistration>::InternalRelease(void)
0x18004abd7  mov     qword ptr [r14+30h], 0
0x18004abdf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18004abe6  mov     ecx, 0A0h; unsigned __int64
0x18004abeb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004abf0  test    rax, rax
0x18004abf3  jz      short loc_18004AC26
0x18004abf5  mov     rcx, rax
0x18004abf8  call    ??0?$HashMap@PEAUHSTRING__@@PEAUIExeServerActivatableClassRegistration@Foundation@Windows@@URegistryNameHashFunction@RegistryMapDetails@@URegistryNameEqualityPredicate@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@U?$DefaultLifetimeTraits@PEAUIExeServerActivatableClassRegistration@Foundation@Windows@@@9Collections@34@U?$DefaultHashMapOptions@PEAUHSTRING__@@PEAUIExeServerActivatableClassRegistration@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@34@@9Collections@34@@Internal@Collections@Foundation@Windows@@QEAA@AEBURegistryNameHashFunction@RegistryMapDetails@@AEBURegistryNameEqualityPredicate@6@Upermission@01234@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>(RegistryMapDetails::RegistryNameHashFunction const &,RegistryMapDetails::RegistryNameEqualityPredicate const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,RegistryMapDetails::RegistryNameHashFunction,RegistryMapDetails::RegistryNameEqualityPredicate,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Foundation::IExeServerActivatableClassRegistration *>,Windows::Foundation::Collections::Internal::DefaultHashMapOptions<HSTRING__ *,Windows::Foundation::IExeServerActivatableClassRegistration *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>>>::permission)
0x18004abfd  mov     rdi, rax
0x18004ac00  test    rax, rax
0x18004ac03  jz      short loc_18004AC28
0x18004ac05  lea     rcx, [rax+90h]; this
0x18004ac0c  call    ?Initialize@TagManager@SecureVersionTag@XWinRT@@QEAAJXZ; XWinRT::SecureVersionTag::TagManager::Initialize(void)
0x18004ac11  mov     esi, eax
0x18004ac13  test    eax, eax
0x18004ac15  js      short loc_18004AC2D
0x18004ac17  mov     byte ptr [rdi+98h], 1
0x18004ac1e  mov     [r14+30h], rdi
0x18004ac22  xor     edi, edi
0x18004ac24  jmp     short loc_18004AC2D
0x18004ac26  xor     edi, edi
0x18004ac28  mov     esi, 8007000Eh
0x18004ac2d  test    rdi, rdi
0x18004ac30  jz      short loc_18004AC42
0x18004ac32  mov     rax, [rdi]
0x18004ac35  mov     rcx, rdi
0x18004ac38  mov     rax, [rax+10h]
0x18004ac3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac41  nop
0x18004ac42  test    esi, esi
0x18004ac44  jns     short loc_18004AC8C
0x18004ac46  mov     rcx, [rsp+68h]; this
0x18004ac4b  mov     dword ptr [rsp+68h+var_40], esi; char *
0x18004ac4f  lea     rax, aRegistrymapfac_0; "RegistryMapFactory< IExeServerActivatab"...
0x18004ac56  mov     [rsp+68h+var_48], rax; char *
0x18004ac5b  lea     r9, aOsintegrationD_349; "OSIntegration::DEH::ActivationCatalogCo"...
0x18004ac62  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18004ac69  mov     edx, 51h ; 'Q'; void *
0x18004ac6e  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004ac73  nop
0x18004ac74  test    rbx, rbx
0x18004ac77  jz      short loc_18004AC88
0x18004ac79  mov     rcx, rbx; string
0x18004ac7c  call    cs:__imp_WindowsDeleteString
0x18004ac83  nop     dword ptr [rax+rax+00h]
0x18004ac88  mov     eax, esi
0x18004ac8a  jmp     short loc_18004ACFA
0x18004ac8c  mov     [rsp+68h+arg_8], 0
0x18004ac91  mov     rcx, [r14+30h]
0x18004ac95  mov     rax, [rcx]
0x18004ac98  lea     r8, [r15+10h]
0x18004ac9c  lea     r9, [rsp+68h+arg_8]
0x18004aca1  mov     rdx, rbx
0x18004aca4  mov     rax, [rax+50h]
0x18004aca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acad  mov     edi, eax
0x18004acaf  test    eax, eax
0x18004acb1  jns     short loc_18004ACE9
0x18004acb3  mov     rcx, [rsp+68h]; this
0x18004acb8  mov     dword ptr [rsp+68h+var_40], eax; char *
0x18004acbc  lea     rax, aOutofprocessac_2; "_outOfProcessActivatableClasses->Insert"...
0x18004acc3  mov     [rsp+68h+var_48], rax; char *
0x18004acc8  lea     r9, aOsintegrationD_349; "OSIntegration::DEH::ActivationCatalogCo"...
0x18004accf  lea     r8, aOnecoreAdminAp_86; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18004acd6  mov     edx, 57h ; 'W'; void *
0x18004acdb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004ace0  nop
0x18004ace1  test    rbx, rbx
0x18004ace4  jmp     loc_18004ABAB
0x18004ace9  xor     ebx, ebx
0x18004aceb  lea     rcx, [rsp+68h+arg_18]; this
0x18004acf3  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18004acf8  mov     eax, ebx
0x18004acfa  add     rsp, 40h
0x18004acfe  pop     r15
0x18004ad00  pop     r14
0x18004ad02  pop     rdi
0x18004ad03  pop     rsi
0x18004ad04  pop     rbx
0x18004ad05  retn
```
