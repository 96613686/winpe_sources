# Windows::Storage::FileProperties::GeotagHelper::SetGeotagFromGeolocatorAsync(Windows::Storage::IStorageFile *,Windows::Devices::Geolocation::IGeolocator *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004b4a0`
- end: `0x18004b5ff`
- name: `?SetGeotagFromGeolocatorAsync@GeotagHelper@FileProperties@Storage@Windows@@UEAAJPEAUIStorageFile@34@PEAUIGeolocator@Geolocation@Devices@4@PEAPEAUIAsyncAction@Foundation@4@@Z`
- size: `351`
- prototype: `__int64 __fastcall(Windows::Storage::FileProperties::GeotagHelper *__hidden this, struct Windows::Storage::IStorageFile *, struct Windows::Devices::Geolocation::IGeolocator *, struct Windows::Foundation::IAsyncAction **)`
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180018160`
- `0x1800204c4`
- `0x1800204e8`
- `0x180020c48`
- `0x180026920`
- `0x18003e760`
- `0x18003f4cc`
- `0x180040438`
- `0x180041d20`
- `0x18004b4a0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b4f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b548`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b4f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b548`

## string_xrefs

- `0x18004b508`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::FileProperties::GeotagHelper::SetGeotagFromGeolocatorAsync(
        Windows::Storage::FileProperties::GeotagHelper *this,
        struct Windows::Storage::IStorageFile *a2,
        struct Windows::Devices::Geolocation::IGeolocator *a3,
        struct Windows::Foundation::IAsyncAction **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r8
  struct Windows::Devices::Geolocation::IGeolocator *v12; // [rsp+20h] [rbp-50h] BYREF
  struct Windows::Storage::IStorageFile *v13; // [rsp+28h] [rbp-48h] BYREF
  __int64 v14; // [rsp+30h] [rbp-40h] BYREF
  int v15; // [rsp+38h] [rbp-38h] BYREF
  __int64 v16; // [rsp+3Ch] [rbp-34h]
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  __int64 v18; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  *a4 = 0;
  if ( !a2 )
  {
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Invalid file parameter", 0x17u, 0x16u);
    v7 = -2147467261;
    RoOriginateError(2147500035LL, v18);
    v8 = 1052;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
      (const char *)0x80004003LL,
      (int)v12);
    return v7;
  }
  if ( !a3 )
  {
    v18 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Invalid geolocator parameter",
      0x1Du,
      0x1Cu);
    v7 = -2147467261;
    RoOriginateError(2147500035LL, v18);
    v8 = 1057;
    goto LABEL_3;
  }
  v13 = a2;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v13);
  v12 = a3;
  Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v12);
  Microsoft::WRL::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>(
    &v14,
    (char *)this - 40);
  v9 = lambda_e08e98234ae019a0c8fcd31c7fd9887a_::_lambda_e08e98234ae019a0c8fcd31c7fd9887a_(
         &hstringHeader,
         &v13,
         &v12,
         &v14);
  v15 = 3;
  v16 = 128;
  v7 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__GeotagHelper_SetGeotagFromGeolocatorAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_e08e98234ae019a0c8fcd31c7fd9887a___(
         &v15,
         a4,
         v10,
         v9);
  lambda_e08e98234ae019a0c8fcd31c7fd9887a_::__lambda_e08e98234ae019a0c8fcd31c7fd9887a_(&hstringHeader);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  return v7;
}

```

## disassembly

```asm
0x18004b4a0  mov     [rsp-18h+arg_8], rbx
0x18004b4a5  push    rbp
0x18004b4a6  push    rsi
0x18004b4a7  push    rdi
0x18004b4a8  mov     rbp, rsp
0x18004b4ab  sub     rsp, 70h
0x18004b4af  mov     rax, cs:__security_cookie
0x18004b4b6  xor     rax, rsp
0x18004b4b9  mov     [rbp+var_8], rax
0x18004b4bd  mov     qword ptr [r9], 0
0x18004b4c4  mov     rdi, r9
0x18004b4c7  mov     rbx, r8
0x18004b4ca  mov     rsi, rcx
0x18004b4cd  test    rdx, rdx
0x18004b4d0  jnz     short loc_18004B51C
0x18004b4d2  mov     [rbp+var_10], rdx
0x18004b4d6  lea     r9d, [rdx+16h]; unsigned int
0x18004b4da  lea     r8d, [rdx+17h]; unsigned int
0x18004b4de  lea     rdx, aInvalidFilePar; "Invalid file parameter"
0x18004b4e5  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004b4e9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b4ee  mov     rdx, [rbp+var_10]
0x18004b4f2  mov     ebx, 80004003h
0x18004b4f7  mov     ecx, ebx
0x18004b4f9  call    cs:__imp_RoOriginateError
0x18004b4ff  mov     edx, 41Ch; void *
0x18004b504  mov     rcx, [rbp+18h]; this
0x18004b508  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x18004b50f  mov     r9d, ebx; char *
0x18004b512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b517  jmp     loc_18004B5E1
0x18004b51c  test    rbx, rbx
0x18004b51f  jnz     short loc_18004B555
0x18004b521  lea     r9d, [rbx+1Ch]; unsigned int
0x18004b525  mov     [rbp+var_10], rbx
0x18004b529  lea     r8d, [rbx+1Dh]; unsigned int
0x18004b52d  lea     rdx, aInvalidGeoloca; "Invalid geolocator parameter"
0x18004b534  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004b538  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b53d  mov     rdx, [rbp+var_10]
0x18004b541  mov     ebx, 80004003h
0x18004b546  mov     ecx, ebx
0x18004b548  call    cs:__imp_RoOriginateError
0x18004b54e  mov     edx, 421h
0x18004b553  jmp     short loc_18004B504
0x18004b555  lea     rcx, [rbp+var_48]
0x18004b559  mov     [rbp+var_48], rdx
0x18004b55d  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18004b562  lea     rcx, [rbp+var_50]
0x18004b566  mov     [rbp+var_50], rbx
0x18004b56a  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18004b56f  lea     rdx, [rsi-28h]
0x18004b573  lea     rcx, [rbp+var_40]
0x18004b577  call    ??$?0VGeotagHelper@FileProperties@Storage@Windows@@@?$ComPtr@UIGeotagHelperStatics@FileProperties@Storage@Windows@@@WRL@Microsoft@@QEAA@PEAVGeotagHelper@FileProperties@Storage@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>(Windows::Storage::FileProperties::GeotagHelper *)
0x18004b57c  lea     r9, [rbp+var_40]
0x18004b580  lea     r8, [rbp+var_50]
0x18004b584  lea     rdx, [rbp+var_48]
0x18004b588  lea     rcx, [rbp+hstringHeader]
0x18004b58c  call    _lambda_e08e98234ae019a0c8fcd31c7fd9887a____lambda_e08e98234ae019a0c8fcd31c7fd9887a_
0x18004b591  mov     r9, rax
0x18004b594  mov     [rbp+var_38], 3
0x18004b59b  mov     rdx, rdi
0x18004b59e  mov     [rbp+var_34], 80h
0x18004b5a6  lea     rcx, [rbp+var_38]
0x18004b5aa  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__GeotagHelper_SetGeotagFromGeolocatorAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_e08e98234ae019a0c8fcd31c7fd9887a___
0x18004b5af  lea     rcx, [rbp+hstringHeader]
0x18004b5b3  mov     ebx, eax
0x18004b5b5  call    _lambda_e08e98234ae019a0c8fcd31c7fd9887a_____lambda_e08e98234ae019a0c8fcd31c7fd9887a_
0x18004b5ba  mov     rcx, [rbp+var_40]
0x18004b5be  test    rcx, rcx
0x18004b5c1  jz      short loc_18004B5CF
0x18004b5c3  mov     rdx, [rcx]
0x18004b5c6  mov     rax, [rdx+10h]
0x18004b5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b5cf  lea     rcx, [rbp+var_50]
0x18004b5d3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b5d8  lea     rcx, [rbp+var_48]
0x18004b5dc  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b5e1  mov     eax, ebx
0x18004b5e3  mov     rcx, [rbp+var_8]
0x18004b5e7  xor     rcx, rsp; StackCookie
0x18004b5ea  call    __security_check_cookie
0x18004b5ef  mov     rbx, [rsp+70h+arg_8]
0x18004b5f7  add     rsp, 70h
0x18004b5fb  pop     rdi
0x18004b5fc  pop     rsi
0x18004b5fd  pop     rbp
0x18004b5fe  retn
```
