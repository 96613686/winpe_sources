# LocationCapabilityHandler::AccessChanged(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000f530`
- end: `0x18000f750`
- name: `?AccessChanged@LocationCapabilityHandler@@UEAAJPEBG0000K@Z`
- size: `544`
- prototype: `__int64 __fastcall(LocationCapabilityHandler *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004c70`
- `0x1800090f4`
- `0x18000f530`
- `0x18000f758`
- `0x18000f784`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f594`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f626`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f594`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000f626`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f639`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f57b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000f639`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000f5b5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000f5b5`

## string_xrefs

- `0x18000f574`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`

## pseudocode

```c
__int64 __fastcall LocationCapabilityHandler::AccessChanged(
        LocationCapabilityHandler *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6)
{
  HSTRING v6; // rbx
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, HSTRING, __int64 *); // r14
  unsigned __int64 v11; // rbx
  int v12; // eax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, __int64 *); // rbx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v18; // [rsp+20h] [rbp-58h] BYREF
  __int64 v19; // [rsp+28h] [rbp-50h] BYREF
  int v20; // [rsp+30h] [rbp-48h] BYREF
  __int64 v21; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+40h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]

  if ( !a3 && !a6 )
  {
    v21 = 0;
    if ( WindowsCreateStringReference(
           L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
           0x45u,
           &hstringHeader,
           &string) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    v6 = string;
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v21);
    ActivationFactory = RoGetActivationFactory(v6, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v21);
    v8 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\base\\devices\\cam\\handler\\location\\locationcapabilityhandler.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v18);
LABEL_21:
      Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v21);
      return v8;
    }
    v9 = v21;
    v18 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v21 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v18);
    v11 = -1;
    do
      ++v11;
    while ( c_szCapabilityLocation[v11] );
    if ( v11 > 0xFFFFFFFF )
    {
      LODWORD(v11) = -1;
      RaiseException(0xC000000D, 1u, 0, 0);
    }
    WindowsCreateStringReference(c_szCapabilityLocation, v11, &hstringHeader, &string);
    v12 = v10(v9, string, &v18);
    v8 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecore\\base\\devices\\cam\\handler\\location\\locationcapabilityhandler.cpp",
        (const char *)(unsigned int)v12,
        v18);
LABEL_20:
      Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v18);
      goto LABEL_21;
    }
    v13 = v18;
    v19 = 0;
    v14 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v19);
    v15 = v14(v13, &v19);
    v8 = v15;
    if ( v15 < 0 )
    {
      v16 = 42;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\base\\devices\\cam\\handler\\location\\locationcapabilityhandler.cpp",
        (const char *)(unsigned int)v15,
        v18);
      Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v19);
      goto LABEL_20;
    }
    v20 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v19 + 88LL))(v19, &v20);
    v8 = v15;
    if ( v15 < 0 )
    {
      v16 = 45;
      goto LABEL_19;
    }
    v15 = LocationCapabilityHandler::SetLegacySensorSystemGlobalConsent(v20 == 1);
    v8 = v15;
    if ( v15 < 0 )
    {
      v16 = 49;
      goto LABEL_19;
    }
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v19);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v18);
    Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(&v21);
  }
  return 0;
}

```

## disassembly

```asm
0x18000f530  push    rbp
0x18000f532  push    rbx
0x18000f533  push    rsi
0x18000f534  push    rdi
0x18000f535  push    r14
0x18000f537  push    r15
0x18000f539  mov     rbp, rsp
0x18000f53c  sub     rsp, 78h
0x18000f540  mov     rax, cs:__security_cookie
0x18000f547  xor     rax, rsp
0x18000f54a  mov     [rbp+var_18], rax
0x18000f54e  xor     r15d, r15d
0x18000f551  test    r8, r8
0x18000f554  jnz     loc_18000F735
0x18000f55a  cmp     [rbp+arg_28], r15
0x18000f55e  jnz     loc_18000F735
0x18000f564  lea     r9, [rbp+string]; string
0x18000f568  mov     [rbp+var_40], r15
0x18000f56c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f570  lea     edx, [r15+45h]; length
0x18000f574  lea     rcx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x18000f57b  call    cs:__imp_WindowsCreateStringReference
0x18000f581  test    eax, eax
0x18000f583  jns     short loc_18000F59A
0x18000f585  xor     r9d, r9d; lpArguments
0x18000f588  lea     edx, [r15+1]; dwExceptionFlags
0x18000f58c  xor     r8d, r8d; nNumberOfArguments
0x18000f58f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000f594  call    cs:__imp_RaiseException
0x18000f59a  mov     rbx, [rbp+string]
0x18000f59e  lea     rcx, [rbp+var_40]
0x18000f5a2  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f5a7  lea     r8, [rbp+var_40]
0x18000f5ab  mov     rcx, rbx
0x18000f5ae  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x18000f5b5  call    cs:__imp_RoGetActivationFactory
0x18000f5bb  mov     ebx, eax
0x18000f5bd  test    eax, eax
0x18000f5bf  jns     short loc_18000F5DE
0x18000f5c1  mov     rcx, [rbp+30h]; this
0x18000f5c5  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\handler\\l"...
0x18000f5cc  mov     r9d, eax; char *
0x18000f5cf  mov     edx, 24h ; '$'; void *
0x18000f5d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f5d9  jmp     loc_18000F70D
0x18000f5de  mov     rsi, [rbp+var_40]
0x18000f5e2  lea     rcx, [rbp+var_58]
0x18000f5e6  mov     [rbp+var_58], r15
0x18000f5ea  mov     rax, [rsi]
0x18000f5ed  mov     r14, [rax+30h]
0x18000f5f1  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f5f6  mov     rdi, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x18000f5fd  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000f601  inc     rbx
0x18000f604  cmp     [rdi+rbx*2], r15w
0x18000f609  jnz     short loc_18000F601
0x18000f60b  mov     eax, 0FFFFFFFFh
0x18000f610  cmp     rbx, rax
0x18000f613  jbe     short loc_18000F62C
0x18000f615  xor     r9d, r9d; lpArguments
0x18000f618  xor     r8d, r8d; nNumberOfArguments
0x18000f61b  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000f620  mov     ebx, eax
0x18000f622  lea     edx, [r9+1]; dwExceptionFlags
0x18000f626  call    cs:__imp_RaiseException
0x18000f62c  lea     r9, [rbp+string]; string
0x18000f630  mov     edx, ebx; length
0x18000f632  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000f636  mov     rcx, rdi; sourceString
0x18000f639  call    cs:__imp_WindowsCreateStringReference
0x18000f63f  mov     rdx, [rbp+string]
0x18000f643  lea     r8, [rbp+var_58]
0x18000f647  mov     rcx, rsi
0x18000f64a  mov     rax, r14
0x18000f64d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f652  mov     ebx, eax
0x18000f654  test    eax, eax
0x18000f656  jns     short loc_18000F675
0x18000f658  mov     rcx, [rbp+30h]; this
0x18000f65c  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\handler\\l"...
0x18000f663  mov     r9d, eax; char *
0x18000f666  mov     edx, 27h ; '''; void *
0x18000f66b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f670  jmp     loc_18000F704
0x18000f675  mov     rdi, [rbp+var_58]
0x18000f679  lea     rcx, [rbp+var_50]
0x18000f67d  mov     [rbp+var_50], r15
0x18000f681  mov     rax, [rdi]
0x18000f684  mov     rbx, [rax+30h]
0x18000f688  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f68d  lea     rdx, [rbp+var_50]
0x18000f691  mov     rcx, rdi
0x18000f694  mov     rax, rbx
0x18000f697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f69c  mov     ebx, eax
0x18000f69e  test    eax, eax
0x18000f6a0  jns     short loc_18000F6A9
0x18000f6a2  mov     edx, 2Ah ; '*'
0x18000f6a7  jmp     short loc_18000F6E8
0x18000f6a9  mov     rcx, [rbp+var_50]
0x18000f6ad  lea     rdx, [rbp+var_48]
0x18000f6b1  mov     [rbp+var_48], r15d
0x18000f6b5  mov     rax, [rcx]
0x18000f6b8  mov     rax, [rax+58h]
0x18000f6bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6c1  mov     ebx, eax
0x18000f6c3  test    eax, eax
0x18000f6c5  jns     short loc_18000F6CE
0x18000f6c7  mov     edx, 2Dh ; '-'
0x18000f6cc  jmp     short loc_18000F6E8
0x18000f6ce  cmp     [rbp+var_48], 1
0x18000f6d2  mov     ecx, r15d
0x18000f6d5  setz    cl; int
0x18000f6d8  call    ?SetLegacySensorSystemGlobalConsent@LocationCapabilityHandler@@CAJH@Z; LocationCapabilityHandler::SetLegacySensorSystemGlobalConsent(int)
0x18000f6dd  mov     ebx, eax
0x18000f6df  test    eax, eax
0x18000f6e1  jns     short loc_18000F71A
0x18000f6e3  mov     edx, 31h ; '1'; void *
0x18000f6e8  mov     rcx, [rbp+30h]; this
0x18000f6ec  lea     r8, aOnecoreBaseDev_3; "onecore\\base\\devices\\cam\\handler\\l"...
0x18000f6f3  mov     r9d, eax; char *
0x18000f6f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6fb  lea     rcx, [rbp+var_50]
0x18000f6ff  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f704  lea     rcx, [rbp+var_58]
0x18000f708  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f70d  lea     rcx, [rbp+var_40]
0x18000f711  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f716  mov     eax, ebx
0x18000f718  jmp     short loc_18000F737
0x18000f71a  lea     rcx, [rbp+var_50]
0x18000f71e  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f723  lea     rcx, [rbp+var_58]
0x18000f727  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f72c  lea     rcx, [rbp+var_40]
0x18000f730  call    ?InternalRelease@?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>::InternalRelease(void)
0x18000f735  xor     eax, eax
0x18000f737  mov     rcx, [rbp+var_18]
0x18000f73b  xor     rcx, rsp; StackCookie
0x18000f73e  call    __security_check_cookie
0x18000f743  add     rsp, 78h
0x18000f747  pop     r15
0x18000f749  pop     r14
0x18000f74b  pop     rdi
0x18000f74c  pop     rsi
0x18000f74d  pop     rbx
0x18000f74e  pop     rbp
0x18000f74f  retn
```
