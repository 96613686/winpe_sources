# SRGetAllUupProductsForPackageFullName

- ea: `0x18000d7d0`
- end: `0x18000db23`
- name: `SRGetAllUupProductsForPackageFullName`
- size: `851`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002980`
- `0x180003630`
- `0x1800075e4`
- `0x180008b4c`
- `0x1800092b8`
- `0x180009350`
- `0x1800094f4`
- `0x18000b348`
- `0x18000c504`
- `0x18000d7d0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d839`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000d839`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000dac3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d91a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d91a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d9c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18000d9c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d81e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000d81e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d99b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da6b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d99b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000d9f8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000da6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d85a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000d85a`

## pseudocode

```c
__int64 __fastcall SRGetAllUupProductsForPackageFullName(__int64 a1, unsigned int *a2, HSTRING *a3)
{
  HSTRING v5; // rbx
  int ActivationFactory; // eax
  int v7; // ebx
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int64, __int64 *); // rbx
  __int64 v10; // rax
  int v11; // eax
  unsigned __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  HSTRING v15; // rax
  HSTRING v16; // rsi
  size_t v17; // rax
  unsigned int v18; // ecx
  unsigned int v19; // r14d
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  __int64 v30; // rcx
  int v31; // [rsp+20h] [rbp-49h]
  __int64 v32; // [rsp+30h] [rbp-39h] BYREF
  __int64 v33; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v34; // [rsp+40h] [rbp-29h] BYREF
  HSTRING v35; // [rsp+48h] [rbp-21h] BYREF
  __int64 v36; // [rsp+50h] [rbp-19h] BYREF
  __int64 v37; // [rsp+58h] [rbp-11h] BYREF
  HSTRING string; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v37 = a1;
  v36 = 0;
  if ( WindowsCreateStringReference(L"Windows.Internal.StateRepository.UupProduct", 0x2Bu, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v5 = string;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v36);
  ActivationFactory = RoGetActivationFactory(v5, &GUID_434b0aec_ee5d_4e88_bfee_23bd385d89c2, &v36);
  v7 = ActivationFactory;
  if ( ActivationFactory >= 0 )
  {
    v8 = v36;
    v32 = 0;
    v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v36 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
    v10 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&string, &v37);
    v11 = v9(v8, *(_QWORD *)(v10 + 24), 1, &v32);
    v7 = v11;
    if ( v11 >= 0 )
    {
      v34 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 56LL))(v32, &v34);
      v7 = v14;
      if ( v14 >= 0 )
      {
        v37 = 0;
        if ( is_mul_ok(v34, 8u) )
        {
          v15 = (HSTRING)CoTaskMemAlloc(8LL * v34);
          v16 = v15;
          if ( v15 )
          {
            v17 = CTCoAllocPolicy::_CoTaskMemSize(v15);
            memset_0(v16, 0, v17);
            v7 = 0;
          }
          else
          {
            v7 = -2147024882;
          }
          if ( v7 >= 0 )
          {
            v18 = v34;
            v19 = 0;
            string = v16;
            hstringHeader.Reserved.Reserved1 = (PVOID)v34;
            if ( !v34 )
            {
LABEL_21:
              *a3 = v16;
              *a2 = v18;
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
              Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v36);
              return 0;
            }
            while ( 1 )
            {
              v33 = 0;
              v20 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 48LL))(v32, v19, &v33);
              v7 = v20;
              if ( v20 < 0 )
                break;
              v21 = v33;
              v35 = 0;
              v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 80LL);
              WindowsDeleteString(0);
              v35 = 0;
              v23 = v22(v21, &v35);
              v7 = v23;
              if ( v23 < 0 )
              {
                v29 = (unsigned int)v23;
                v28 = 607;
                goto LABEL_23;
              }
              StringRawBuffer = WindowsGetStringRawBuffer(v35, 0);
              wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
                &v37,
                StringRawBuffer);
              v25 = v37;
              v37 = 0;
              *((_QWORD *)v16 + v19) = v25;
              wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v37);
              if ( !*((_QWORD *)v16 + v19) )
              {
                v7 = -2147024882;
                v28 = 610;
                v29 = 2147942414LL;
LABEL_23:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v28,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
                  (const char *)v29,
                  v31);
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
              v18 = v34;
              if ( ++v19 >= v34 )
                goto LABEL_21;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x25C,
              (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
              (const char *)(unsigned int)v20,
              v31);
LABEL_26:
            v30 = v33;
            if ( v33 )
            {
              v33 = 0;
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
            }
            if ( v16 )
            {
              wil::unique_any_array_ptr<unsigned short *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(&string);
              CoTaskMemFree(v16);
            }
            goto LABEL_33;
          }
        }
        else
        {
          v7 = -2147024362;
        }
        v12 = (unsigned int)v7;
        v13 = 598;
      }
      else
      {
        v12 = (unsigned int)v14;
        v13 = 595;
      }
    }
    else
    {
      v12 = (unsigned int)v11;
      v13 = 592;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
      (const char *)v12,
      v31);
LABEL_33:
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v32);
    goto LABEL_34;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24D,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\winrt\\inproc\\lib\\apiset.cpp",
    (const char *)(unsigned int)ActivationFactory,
    v31);
LABEL_34:
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(&v36);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000d7d0  mov     [rsp-8+arg_18], rbx
0x18000d7d5  push    rbp
0x18000d7d6  push    rsi
0x18000d7d7  push    rdi
0x18000d7d8  push    r12
0x18000d7da  push    r13
0x18000d7dc  push    r14
0x18000d7de  push    r15
0x18000d7e0  lea     rbp, [rsp-27h]
0x18000d7e5  sub     rsp, 90h
0x18000d7ec  mov     rax, cs:__security_cookie
0x18000d7f3  xor     rax, rsp
0x18000d7f6  mov     [rbp+57h+var_40], rax
0x18000d7fa  xor     r13d, r13d
0x18000d7fd  mov     [rbp+57h+var_68], rcx
0x18000d801  mov     r12, r8
0x18000d804  mov     [rbp+57h+var_70], r13
0x18000d808  mov     r15, rdx
0x18000d80b  lea     r9, [rbp+57h+string]; string
0x18000d80f  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000d813  lea     edx, [r13+2Bh]; length
0x18000d817  lea     rcx, ?RuntimeClass_Windows_Internal_StateRepository_UupProduct@@3QBGB; "Windows.Internal.StateRepository.UupPro"...
0x18000d81e  call    cs:__imp_WindowsCreateStringReference
0x18000d824  lea     esi, [r13+1]
0x18000d828  test    eax, eax
0x18000d82a  jns     short loc_18000D83F
0x18000d82c  xor     r9d, r9d; lpArguments
0x18000d82f  xor     r8d, r8d; nNumberOfArguments
0x18000d832  mov     edx, esi; dwExceptionFlags
0x18000d834  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000d839  call    cs:__imp_RaiseException
0x18000d83f  mov     rbx, [rbp+57h+string]
0x18000d843  lea     rcx, [rbp+57h+var_70]
0x18000d847  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d84c  lea     r8, [rbp+57h+var_70]
0x18000d850  mov     rcx, rbx
0x18000d853  lea     rdx, _GUID_434b0aec_ee5d_4e88_bfee_23bd385d89c2
0x18000d85a  call    cs:__imp_RoGetActivationFactory
0x18000d860  mov     ebx, eax
0x18000d862  test    eax, eax
0x18000d864  jns     short loc_18000D883
0x18000d866  mov     rcx, [rbp+5Fh]; this
0x18000d86a  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000d871  mov     r9d, eax; char *
0x18000d874  mov     edx, 24Dh; void *
0x18000d879  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d87e  jmp     loc_18000DAF1
0x18000d883  mov     rdi, [rbp+57h+var_70]
0x18000d887  lea     rcx, [rbp+57h+var_90]
0x18000d88b  mov     [rbp+57h+var_90], r13
0x18000d88f  mov     rax, [rdi]
0x18000d892  mov     rbx, [rax+90h]
0x18000d899  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000d89e  lea     rdx, [rbp+57h+var_68]
0x18000d8a2  lea     rcx, [rbp+57h+string]
0x18000d8a6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18000d8ab  lea     r9, [rbp+57h+var_90]
0x18000d8af  mov     r8d, esi
0x18000d8b2  mov     rcx, rdi
0x18000d8b5  mov     rdx, [rax+18h]
0x18000d8b9  mov     rax, rbx
0x18000d8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8c1  mov     ebx, eax
0x18000d8c3  test    eax, eax
0x18000d8c5  jns     short loc_18000D8D4
0x18000d8c7  mov     r9d, eax
0x18000d8ca  mov     edx, 250h
0x18000d8cf  jmp     loc_18000DAD8
0x18000d8d4  mov     rcx, [rbp+57h+var_90]
0x18000d8d8  lea     rdx, [rbp+57h+var_80]
0x18000d8dc  mov     [rbp+57h+var_80], r13d
0x18000d8e0  mov     rax, [rcx]
0x18000d8e3  mov     rax, [rax+38h]
0x18000d8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ec  mov     ebx, eax
0x18000d8ee  test    eax, eax
0x18000d8f0  jns     short loc_18000D8FF
0x18000d8f2  mov     r9d, eax
0x18000d8f5  mov     edx, 253h
0x18000d8fa  jmp     loc_18000DAD8
0x18000d8ff  mov     ecx, [rbp+57h+var_80]
0x18000d902  mov     eax, 8
0x18000d907  mul     rcx
0x18000d90a  mov     [rbp+57h+var_68], r13
0x18000d90e  test    rdx, rdx
0x18000d911  jnz     loc_18000DACB
0x18000d917  mov     rcx, rax; cb
0x18000d91a  call    cs:__imp_CoTaskMemAlloc
0x18000d920  mov     rsi, rax
0x18000d923  test    rax, rax
0x18000d926  jz      short loc_18000D942
0x18000d928  mov     rcx, rax; void *
0x18000d92b  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000d930  mov     r8, rax; Size
0x18000d933  xor     edx, edx; Val
0x18000d935  mov     rcx, rsi; void *
0x18000d938  call    memset_0
0x18000d93d  mov     ebx, r13d
0x18000d940  jmp     short loc_18000D947
0x18000d942  mov     ebx, 8007000Eh
0x18000d947  test    ebx, ebx
0x18000d949  js      loc_18000DAD0
0x18000d94f  mov     ecx, [rbp+57h+var_80]
0x18000d952  mov     r14d, r13d
0x18000d955  mov     [rbp+57h+string], rsi
0x18000d959  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rcx
0x18000d95d  test    ecx, ecx
0x18000d95f  jz      loc_18000DA2A
0x18000d965  mov     rcx, [rbp+57h+var_90]
0x18000d969  lea     r8, [rbp+57h+var_88]
0x18000d96d  mov     [rbp+57h+var_88], r13
0x18000d971  mov     edx, r14d
0x18000d974  mov     rax, [rcx]
0x18000d977  mov     rax, [rax+30h]
0x18000d97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d980  mov     ebx, eax
0x18000d982  test    eax, eax
0x18000d984  js      loc_18000DA81
0x18000d98a  mov     rdi, [rbp+57h+var_88]
0x18000d98e  xor     ecx, ecx; string
0x18000d990  mov     [rbp+57h+var_78], r13
0x18000d994  mov     rax, [rdi]
0x18000d997  mov     rbx, [rax+50h]
0x18000d99b  call    cs:__imp_WindowsDeleteString
0x18000d9a1  lea     rdx, [rbp+57h+var_78]
0x18000d9a5  mov     [rbp+57h+var_78], r13
0x18000d9a9  mov     rcx, rdi
0x18000d9ac  mov     rax, rbx
0x18000d9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d9b4  mov     ebx, eax
0x18000d9b6  test    eax, eax
0x18000d9b8  js      loc_18000DA77
0x18000d9be  mov     rcx, [rbp+57h+var_78]; string
0x18000d9c2  xor     edx, edx; length
0x18000d9c4  call    cs:__imp_WindowsGetStringRawBuffer
0x18000d9ca  mov     rdx, rax
0x18000d9cd  lea     rcx, [rbp+57h+var_68]
0x18000d9d1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000d9d6  mov     rax, [rbp+57h+var_68]
0x18000d9da  lea     rcx, [rbp+57h+var_68]
0x18000d9de  mov     ebx, r14d
0x18000d9e1  mov     [rbp+57h+var_68], r13
0x18000d9e5  mov     [rsi+rbx*8], rax
0x18000d9e9  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000d9ee  cmp     [rsi+rbx*8], r13
0x18000d9f2  jz      short loc_18000DA4A
0x18000d9f4  mov     rcx, [rbp+57h+var_78]; string
0x18000d9f8  call    cs:__imp_WindowsDeleteString
0x18000d9fe  mov     rcx, [rbp+57h+var_88]
0x18000da02  mov     [rbp+57h+var_78], r13
0x18000da06  test    rcx, rcx
0x18000da09  jz      short loc_18000DA1B
0x18000da0b  mov     [rbp+57h+var_88], r13
0x18000da0f  mov     rax, [rcx]
0x18000da12  mov     rax, [rax+10h]
0x18000da16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da1b  mov     ecx, [rbp+57h+var_80]
0x18000da1e  inc     r14d
0x18000da21  cmp     r14d, ecx
0x18000da24  jb      loc_18000D965
0x18000da2a  mov     [r12], rsi
0x18000da2e  mov     [r15], ecx
0x18000da31  lea     rcx, [rbp+57h+var_90]
0x18000da35  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000da3a  lea     rcx, [rbp+57h+var_70]
0x18000da3e  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000da43  xor     eax, eax
0x18000da45  jmp     loc_18000DAFC
0x18000da4a  mov     ebx, 8007000Eh
0x18000da4f  mov     edx, 262h; void *
0x18000da54  mov     r9d, ebx; char *
0x18000da57  mov     rcx, [rbp+5Fh]; this
0x18000da5b  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000da62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da67  mov     rcx, [rbp+57h+var_78]; string
0x18000da6b  call    cs:__imp_WindowsDeleteString
0x18000da71  mov     [rbp+57h+var_78], r13
0x18000da75  jmp     short loc_18000DA99
0x18000da77  mov     r9d, eax
0x18000da7a  mov     edx, 25Fh
0x18000da7f  jmp     short loc_18000DA57
0x18000da81  mov     rcx, [rbp+5Fh]; this
0x18000da85  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000da8c  mov     r9d, eax; char *
0x18000da8f  mov     edx, 25Ch; void *
0x18000da94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000da99  mov     rcx, [rbp+57h+var_88]
0x18000da9d  test    rcx, rcx
0x18000daa0  jz      short loc_18000DAB2
0x18000daa2  mov     [rbp+57h+var_88], r13
0x18000daa6  mov     rax, [rcx]
0x18000daa9  mov     rax, [rax+10h]
0x18000daad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dab2  test    rsi, rsi
0x18000dab5  jz      short loc_18000DAE8
0x18000dab7  lea     rcx, [rbp+57h+string]
0x18000dabb  call    ??$reset_array@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@?$unique_any_array_ptr@PEAGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@AEAAXAEBU?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@1@@Z; wil::unique_any_array_ptr<ushort *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>,unsigned __int64>::reset_array<wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)
0x18000dac0  mov     rcx, rsi; pv
0x18000dac3  call    cs:__imp_CoTaskMemFree
0x18000dac9  jmp     short loc_18000DAE8
0x18000dacb  mov     ebx, 80070216h
0x18000dad0  mov     r9d, ebx; char *
0x18000dad3  mov     edx, 256h; void *
0x18000dad8  mov     rcx, [rbp+5Fh]; this
0x18000dadc  lea     r8, aOnecoreBaseApp_28; "onecore\\base\\appmodel\\staterepositor"...
0x18000dae3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dae8  lea     rcx, [rbp+57h+var_90]
0x18000daec  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000daf1  lea     rcx, [rbp+57h+var_70]
0x18000daf5  call    ?InternalRelease@?$ComPtr@UISecondaryTileUserChangedEventArgsStatics@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::ISecondaryTileUserChangedEventArgsStatics>::InternalRelease(void)
0x18000dafa  mov     eax, ebx
0x18000dafc  mov     rcx, [rbp+57h+var_40]
0x18000db00  xor     rcx, rsp; StackCookie
0x18000db03  call    __security_check_cookie
0x18000db08  mov     rbx, [rsp+0C0h+arg_18]
0x18000db10  add     rsp, 90h
0x18000db17  pop     r15
0x18000db19  pop     r14
0x18000db1b  pop     r13
0x18000db1d  pop     r12
0x18000db1f  pop     rdi
0x18000db20  pop     rsi
0x18000db21  pop     rbp
0x18000db22  retn
```
