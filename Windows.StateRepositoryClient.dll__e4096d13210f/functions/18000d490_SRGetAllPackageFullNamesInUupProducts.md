# SRGetAllPackageFullNamesInUupProducts

- ea: `0x18000d490`
- end: `0x18000d7c8`
- name: `SRGetAllPackageFullNamesInUupProducts`
- size: `824`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x1800092b8`
- `0x180009350`
- `0x1800094f4`
- `0x18000b348`
- `0x18000c504`
- `0x18000d490`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d4f3`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d4f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d768`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d5bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d669`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d4d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d4d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d69d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d640`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d69d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d710`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d514`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d514`

## pseudocode

```c
__int64 __fastcall SRGetAllPackageFullNamesInUupProducts(unsigned int *a1, HSTRING *a2)
{
  HSTRING v4; // rbx
  int ActivationFactory; // eax
  int v6; // ebx
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, __int64, __int64 *); // rbx
  int v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  int v12; // eax
  HSTRING v13; // rax
  HSTRING v14; // rsi
  size_t v15; // rax
  unsigned int v16; // ecx
  unsigned int v17; // r14d
  int v18; // eax
  __int64 v19; // rdi
  __int64 (__fastcall *v20)(__int64, HSTRING *); // rbx
  int v21; // eax
  char *StringRawBuffer; // rax
  __int64 v23; // r8
  const char *v24; // r9
  void *v25; // rax
  __int64 v26; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // [rsp+20h] [rbp-60h] BYREF
  __int64 v33; // [rsp+28h] [rbp-58h] BYREF
  unsigned int v34; // [rsp+30h] [rbp-50h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-48h] BYREF
  __int64 v36; // [rsp+40h] [rbp-40h] BYREF
  void *v37; // [rsp+48h] [rbp-38h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v36 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.PackageIdentity", 0x30u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v36);
  ActivationFactory = RoGetActivationFactory(v4, &GUID_84485035_7d09_4684_8440_e8eb94f59919, &v36);
  v6 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v7 = v36;
    v32 = 0;
    v8 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v36 + 120LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
    v9 = v8(v7, 1, &v32);
    v6 = v9;
    if ( v9 >= 0 )
    {
      v34 = 0;
      v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v34);
      v6 = v12;
      if ( v12 >= 0 )
      {
        v37 = 0;
        if ( is_mul_ok(v34, 8u) )
        {
          v13 = (HSTRING)CoTaskMemAlloc(8LL * v34);
          v14 = v13;
          if ( v13 )
          {
            v15 = CTCoAllocPolicy::_CoTaskMemSize(v13);
            memset_0(v14, 0, v15);
            v6 = 0;
          }
          else
          {
            v6 = -2147024882;
          }
          if ( v6 >= 0 )
          {
            v16 = v34;
            v17 = 0;
            string = v14;
            hstringHeader.Reserved.Reserved1 = (PVOID)v34;
            if ( !v34 )
            {
LABEL_21:
              *a2 = v14;
              *a1 = v16;
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v36);
              return 0;
            }
            while ( 1 )
            {
              v33 = 0;
              v18 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, v17, &v33);
              v6 = v18;
              if ( v18 < 0 )
                break;
              v19 = v33;
              v35 = 0;
              v20 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 80LL);
              WindowsDeleteString(0);
              v35 = 0;
              v21 = v20(v19, &v35);
              v6 = v21;
              if ( v21 < 0 )
              {
                v29 = (unsigned int)v21;
                v28 = 570;
                goto LABEL_23;
              }
              StringRawBuffer = (char *)WindowsGetStringRawBuffer(v35, 0);
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v37,
                StringRawBuffer,
                v23,
                v24);
              v25 = v37;
              v37 = 0;
              *((_QWORD *)v14 + v17) = v25;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
              if ( !*((_QWORD *)v14 + v17) )
              {
                v6 = -2147024882;
                v28 = 573;
                v29 = 2147942414LL;
LABEL_23:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v28,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
                  (const char *)v29,
                  v32);
                WindowsDeleteString(v35);
                v35 = 0;
                goto LABEL_26;
              }
              WindowsDeleteString(v35);
              v26 = v33;
              v35 = 0;
              if ( v33 )
              {
                v33 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
              }
              v16 = v34;
              if ( ++v17 >= v34 )
                goto LABEL_21;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x237,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
              (const char *)(unsigned int)v18,
              v32);
LABEL_26:
            v31 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
            }
            if ( v14 )
            {
              wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
                (__int64)&string,
                v30);
              CoTaskMemFree(v14);
            }
            goto LABEL_33;
          }
        }
        else
        {
          v6 = -2147024362;
        }
        v10 = (unsigned int)v6;
        v11 = 561;
      }
      else
      {
        v10 = (unsigned int)v12;
        v11 = 558;
      }
    }
    else
    {
      v10 = (unsigned int)v9;
      v11 = 555;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)v10,
      v32);
LABEL_33:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x228,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v32);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v36);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000d490  mov     [rsp-38h+arg_10], rbx
0x18000d495  push    rbp
0x18000d496  push    rsi
0x18000d497  push    rdi
0x18000d498  push    r12
0x18000d49a  push    r13
0x18000d49c  push    r14
0x18000d49e  push    r15
0x18000d4a0  mov     rbp, rsp
0x18000d4a3  sub     rsp, 80h
0x18000d4aa  mov     rax, cs:__security_cookie
0x18000d4b1  xor     rax, rsp
0x18000d4b4  mov     [rbp+var_10], rax
0x18000d4b8  xor     r13d, r13d
0x18000d4bb  lea     r9, [rbp+string]; string
0x18000d4bf  mov     r12, rdx
0x18000d4c2  mov     [rbp+var_40], r13
0x18000d4c6  mov     r15, rcx
0x18000d4c9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000d4cd  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_PackageIdentity@@3QBGB; "Windows.Internal.StateRepository.Packag"...
0x18000d4d4  lea     edx, [r13+30h]; length
0x18000d4d8  call    cs:__imp_WindowsCreateStringReference
0x18000d4de  lea     esi, [r13+1]
0x18000d4e2  test    eax, eax
0x18000d4e4  jns     short loc_18000D4F9
0x18000d4e6  xor     r9d, r9d; lpArguments
0x18000d4e9  xor     r8d, r8d; nNumberOfArguments
0x18000d4ec  mov     edx, esi; dwExceptionFlags
0x18000d4ee  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000d4f3  call    cs:__imp_RaiseException
0x18000d4f9  mov     rbx, [rbp+string]
0x18000d4fd  lea     rcx, [rbp+var_40]
0x18000d501  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d506  lea     r8, [rbp+var_40]
0x18000d50a  mov     rcx, rbx
0x18000d50d  lea     rdx, _GUID_84485035_7d09_4684_8440_e8eb94f59919
0x18000d514  call    cs:__imp_RoGetActivationFactory
0x18000d51a  mov     ebx, eax
0x18000d51c  test    eax, eax
0x18000d51e  jns     short loc_18000D53D
0x18000d520  mov     rcx, [rbp+38h]; this
0x18000d524  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d52b  mov     r9d, eax; char *
0x18000d52e  mov     edx, 228h; void *
0x18000d533  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d538  jmp     loc_18000D796
0x18000d53d  mov     rdi, [rbp+var_40]
0x18000d541  lea     rcx, [rbp+var_60]
0x18000d545  mov     [rbp+var_60], r13
0x18000d549  mov     rax, [rdi]
0x18000d54c  mov     rbx, [rax+78h]
0x18000d550  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d555  lea     r8, [rbp+var_60]
0x18000d559  mov     edx, esi
0x18000d55b  mov     rcx, rdi
0x18000d55e  mov     rax, rbx
0x18000d561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d566  mov     ebx, eax
0x18000d568  test    eax, eax
0x18000d56a  jns     short loc_18000D579
0x18000d56c  mov     r9d, eax
0x18000d56f  mov     edx, 22Bh
0x18000d574  jmp     loc_18000D77D
0x18000d579  mov     rcx, [rbp+var_60]
0x18000d57d  lea     rdx, [rbp+var_50]
0x18000d581  mov     [rbp+var_50], r13d
0x18000d585  mov     rax, [rcx]
0x18000d588  mov     rax, [rax+38h]
0x18000d58c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d591  mov     ebx, eax
0x18000d593  test    eax, eax
0x18000d595  jns     short loc_18000D5A4
0x18000d597  mov     r9d, eax
0x18000d59a  mov     edx, 22Eh
0x18000d59f  jmp     loc_18000D77D
0x18000d5a4  mov     ecx, [rbp+var_50]
0x18000d5a7  mov     eax, 8
0x18000d5ac  mul     rcx
0x18000d5af  mov     [rbp+var_38], r13
0x18000d5b3  test    rdx, rdx
0x18000d5b6  jnz     loc_18000D770
0x18000d5bc  mov     rcx, rax; cb
0x18000d5bf  call    cs:__imp_CoTaskMemAlloc
0x18000d5c5  mov     rsi, rax
0x18000d5c8  test    rax, rax
0x18000d5cb  jz      short loc_18000D5E7
0x18000d5cd  mov     rcx, rax; void *
0x18000d5d0  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000d5d5  mov     r8, rax; Size
0x18000d5d8  xor     edx, edx; Val
0x18000d5da  mov     rcx, rsi; void *
0x18000d5dd  call    memset_0
0x18000d5e2  mov     ebx, r13d
0x18000d5e5  jmp     short loc_18000D5EC
0x18000d5e7  mov     ebx, 8007000Eh
0x18000d5ec  test    ebx, ebx
0x18000d5ee  js      loc_18000D775
0x18000d5f4  mov     ecx, [rbp+var_50]
0x18000d5f7  mov     r14d, r13d
0x18000d5fa  mov     [rbp+string], rsi
0x18000d5fe  mov     qword ptr [rbp+hstringHeader.Reserved], rcx
0x18000d602  test    ecx, ecx
0x18000d604  jz      loc_18000D6CF
0x18000d60a  mov     rcx, [rbp+var_60]
0x18000d60e  lea     r8, [rbp+var_58]
0x18000d612  mov     [rbp+var_58], r13
0x18000d616  mov     edx, r14d
0x18000d619  mov     rax, [rcx]
0x18000d61c  mov     rax, [rax+30h]
0x18000d620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d625  mov     ebx, eax
0x18000d627  test    eax, eax
0x18000d629  js      loc_18000D726
0x18000d62f  mov     rdi, [rbp+var_58]
0x18000d633  xor     ecx, ecx; string
0x18000d635  mov     [rbp+var_48], r13
0x18000d639  mov     rax, [rdi]
0x18000d63c  mov     rbx, [rax+50h]
0x18000d640  call    cs:__imp_WindowsDeleteString
0x18000d646  lea     rdx, [rbp+var_48]
0x18000d64a  mov     [rbp+var_48], r13
0x18000d64e  mov     rcx, rdi
0x18000d651  mov     rax, rbx
0x18000d654  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d659  mov     ebx, eax
0x18000d65b  test    eax, eax
0x18000d65d  js      loc_18000D71C
0x18000d663  mov     rcx, [rbp+var_48]; string
0x18000d667  xor     edx, edx; length
0x18000d669  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d66f  mov     rdx, rax
0x18000d672  lea     rcx, [rbp+var_38]
0x18000d676  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000d67b  mov     rax, [rbp+var_38]
0x18000d67f  lea     rcx, [rbp+var_38]
0x18000d683  mov     ebx, r14d
0x18000d686  mov     [rbp+var_38], r13
0x18000d68a  mov     [rsi+rbx*8], rax
0x18000d68e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000d693  cmp     [rsi+rbx*8], r13
0x18000d697  jz      short loc_18000D6EF
0x18000d699  mov     rcx, [rbp+var_48]; string
0x18000d69d  call    cs:__imp_WindowsDeleteString
0x18000d6a3  mov     rcx, [rbp+var_58]
0x18000d6a7  mov     [rbp+var_48], r13
0x18000d6ab  test    rcx, rcx
0x18000d6ae  jz      short loc_18000D6C0
0x18000d6b0  mov     [rbp+var_58], r13
0x18000d6b4  mov     rax, [rcx]
0x18000d6b7  mov     rax, [rax+10h]
0x18000d6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6c0  mov     ecx, [rbp+var_50]
0x18000d6c3  inc     r14d
0x18000d6c6  cmp     r14d, ecx
0x18000d6c9  jb      loc_18000D60A
0x18000d6cf  mov     [r12], rsi
0x18000d6d3  mov     [r15], ecx
0x18000d6d6  lea     rcx, [rbp+var_60]
0x18000d6da  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d6df  lea     rcx, [rbp+var_40]
0x18000d6e3  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d6e8  xor     eax, eax
0x18000d6ea  jmp     loc_18000D7A1
0x18000d6ef  mov     ebx, 8007000Eh
0x18000d6f4  mov     edx, 23Dh; void *
0x18000d6f9  mov     r9d, ebx; char *
0x18000d6fc  mov     rcx, [rbp+38h]; this
0x18000d700  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d70c  mov     rcx, [rbp+var_48]; string
0x18000d710  call    cs:__imp_WindowsDeleteString
0x18000d716  mov     [rbp+var_48], r13
0x18000d71a  jmp     short loc_18000D73E
0x18000d71c  mov     r9d, eax
0x18000d71f  mov     edx, 23Ah
0x18000d724  jmp     short loc_18000D6FC
0x18000d726  mov     rcx, [rbp+38h]; this
0x18000d72a  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d731  mov     r9d, eax; char *
0x18000d734  mov     edx, 237h; void *
0x18000d739  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d73e  mov     rcx, [rbp+var_58]
0x18000d742  test    rcx, rcx
0x18000d745  jz      short loc_18000D757
0x18000d747  mov     [rbp+var_58], r13
0x18000d74b  mov     rax, [rcx]
0x18000d74e  mov     rax, [rax+10h]
0x18000d752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d757  test    rsi, rsi
0x18000d75a  jz      short loc_18000D78D
0x18000d75c  lea     rcx, [rbp+string]
0x18000d760  call    ??$reset_array@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@AEAAXAEBU?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@1@@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x18000d765  mov     rcx, rsi; pv
0x18000d768  call    cs:__imp_CoTaskMemFree
0x18000d76e  jmp     short loc_18000D78D
0x18000d770  mov     ebx, 80070216h
0x18000d775  mov     r9d, ebx; char *
0x18000d778  mov     edx, 231h; void *
0x18000d77d  mov     rcx, [rbp+38h]; this
0x18000d781  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d788  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d78d  lea     rcx, [rbp+var_60]
0x18000d791  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d796  lea     rcx, [rbp+var_40]
0x18000d79a  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d79f  mov     eax, ebx
0x18000d7a1  mov     rcx, [rbp+var_10]
0x18000d7a5  xor     rcx, rsp; StackCookie
0x18000d7a8  call    __security_check_cookie
0x18000d7ad  mov     rbx, [rsp+80h+arg_10]
0x18000d7b5  add     rsp, 80h
0x18000d7bc  pop     r15
0x18000d7be  pop     r14
0x18000d7c0  pop     r13
0x18000d7c2  pop     r12
0x18000d7c4  pop     rdi
0x18000d7c5  pop     rsi
0x18000d7c6  pop     rbp
0x18000d7c7  retn
```
