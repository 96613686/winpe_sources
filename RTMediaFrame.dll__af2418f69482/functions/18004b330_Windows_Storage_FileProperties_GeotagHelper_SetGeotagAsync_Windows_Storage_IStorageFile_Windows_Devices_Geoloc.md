# Windows::Storage::FileProperties::GeotagHelper::SetGeotagAsync(Windows::Storage::IStorageFile *,Windows::Devices::Geolocation::IGeopoint *,Windows::Foundation::IAsyncAction * *)

- ea: `0x18004b330`
- end: `0x18004b48f`
- name: `?SetGeotagAsync@GeotagHelper@FileProperties@Storage@Windows@@UEAAJPEAUIStorageFile@34@PEAUIGeopoint@Geolocation@Devices@4@PEAPEAUIAsyncAction@Foundation@4@@Z`
- size: `351`
- prototype: `__int64 __fastcall(Windows::Storage::FileProperties::GeotagHelper *__hidden this, struct Windows::Storage::IStorageFile *, struct Windows::Devices::Geolocation::IGeopoint *, struct Windows::Foundation::IAsyncAction **)`
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
- `0x18003f46c`
- `0x180040438`
- `0x180041ca0`
- `0x18004b330`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b389`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b3d8`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b389`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x18004b3d8`

## string_xrefs

- `0x18004b398`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::FileProperties::GeotagHelper::SetGeotagAsync(
        Windows::Storage::FileProperties::GeotagHelper *this,
        struct Windows::Storage::IStorageFile *a2,
        struct Windows::Devices::Geolocation::IGeopoint *a3,
        struct Windows::Foundation::IAsyncAction **a4)
{
  unsigned int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r8
  struct Windows::Devices::Geolocation::IGeopoint *v12; // [rsp+20h] [rbp-50h] BYREF
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
    v8 = 966;
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
      L"Invalid geopoint parameter",
      0x1Bu,
      0x1Au);
    v7 = -2147467261;
    RoOriginateError(2147500035LL, v18);
    v8 = 971;
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
         &v14,
         &v13,
         &v12);
  v15 = 3;
  v16 = 128;
  v7 = Windows::Internal::MakeAsyncAction_Microsoft::WRL::AsyncCausalityOptions__GeotagHelper_SetGeotagAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows::Internal::ComTaskPoolHandler__lambda_95bd74e9ed3ef8465653a0dee8963aa1___(
         &v15,
         a4,
         v10,
         v9);
  lambda_95bd74e9ed3ef8465653a0dee8963aa1_::__lambda_95bd74e9ed3ef8465653a0dee8963aa1_(&hstringHeader);
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v12);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v13);
  return v7;
}

```

## disassembly

```asm
0x18004b330  mov     [rsp-18h+arg_8], rbx
0x18004b335  push    rbp
0x18004b336  push    rsi
0x18004b337  push    rdi
0x18004b338  mov     rbp, rsp
0x18004b33b  sub     rsp, 70h
0x18004b33f  mov     rax, cs:__security_cookie
0x18004b346  xor     rax, rsp
0x18004b349  mov     [rbp+var_8], rax
0x18004b34d  mov     qword ptr [r9], 0
0x18004b354  mov     rdi, r9
0x18004b357  mov     rbx, r8
0x18004b35a  mov     rsi, rcx
0x18004b35d  test    rdx, rdx
0x18004b360  jnz     short loc_18004B3AC
0x18004b362  mov     [rbp+var_10], rdx
0x18004b366  lea     r9d, [rdx+16h]; unsigned int
0x18004b36a  lea     r8d, [rdx+17h]; unsigned int
0x18004b36e  lea     rdx, aInvalidFilePar; "Invalid file parameter"
0x18004b375  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004b379  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b37e  mov     rdx, [rbp+var_10]
0x18004b382  mov     ebx, 80004003h
0x18004b387  mov     ecx, ebx
0x18004b389  call    cs:__imp_RoOriginateError
0x18004b38f  mov     edx, 3C6h; void *
0x18004b394  mov     rcx, [rbp+18h]; this
0x18004b398  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x18004b39f  mov     r9d, ebx; char *
0x18004b3a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b3a7  jmp     loc_18004B471
0x18004b3ac  test    rbx, rbx
0x18004b3af  jnz     short loc_18004B3E5
0x18004b3b1  lea     r9d, [rbx+1Ah]; unsigned int
0x18004b3b5  mov     [rbp+var_10], rbx
0x18004b3b9  lea     r8d, [rbx+1Bh]; unsigned int
0x18004b3bd  lea     rdx, aInvalidGeopoin; "Invalid geopoint parameter"
0x18004b3c4  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x18004b3c8  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004b3cd  mov     rdx, [rbp+var_10]
0x18004b3d1  mov     ebx, 80004003h
0x18004b3d6  mov     ecx, ebx
0x18004b3d8  call    cs:__imp_RoOriginateError
0x18004b3de  mov     edx, 3CBh
0x18004b3e3  jmp     short loc_18004B394
0x18004b3e5  lea     rcx, [rbp+var_48]
0x18004b3e9  mov     [rbp+var_48], rdx
0x18004b3ed  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18004b3f2  lea     rcx, [rbp+var_50]
0x18004b3f6  mov     [rbp+var_50], rbx
0x18004b3fa  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x18004b3ff  lea     rdx, [rsi-28h]
0x18004b403  lea     rcx, [rbp+var_40]
0x18004b407  call    ??$?0VGeotagHelper@FileProperties@Storage@Windows@@@?$ComPtr@UIGeotagHelperStatics@FileProperties@Storage@Windows@@@WRL@Microsoft@@QEAA@PEAVGeotagHelper@FileProperties@Storage@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>(Windows::Storage::FileProperties::GeotagHelper *)
0x18004b40c  lea     r9, [rbp+var_50]
0x18004b410  lea     r8, [rbp+var_48]
0x18004b414  lea     rdx, [rbp+var_40]
0x18004b418  lea     rcx, [rbp+hstringHeader]
0x18004b41c  call    _lambda_e08e98234ae019a0c8fcd31c7fd9887a____lambda_e08e98234ae019a0c8fcd31c7fd9887a_
0x18004b421  mov     r9, rax
0x18004b424  mov     [rbp+var_38], 3
0x18004b42b  mov     rdx, rdi
0x18004b42e  mov     [rbp+var_34], 80h
0x18004b436  lea     rcx, [rbp+var_38]
0x18004b43a  call    Windows__Internal__MakeAsyncAction_Microsoft__WRL__AsyncCausalityOptions__GeotagHelper_SetGeotagAsync__GUID_CAUSALITY_WINDOWS_PLATFORM_ID_2__Windows__Internal__ComTaskPoolHandler__lambda_95bd74e9ed3ef8465653a0dee8963aa1___
0x18004b43f  lea     rcx, [rbp+hstringHeader]
0x18004b443  mov     ebx, eax
0x18004b445  call    _lambda_95bd74e9ed3ef8465653a0dee8963aa1_____lambda_95bd74e9ed3ef8465653a0dee8963aa1_
0x18004b44a  mov     rcx, [rbp+var_40]
0x18004b44e  test    rcx, rcx
0x18004b451  jz      short loc_18004B45F
0x18004b453  mov     rdx, [rcx]
0x18004b456  mov     rax, [rdx+10h]
0x18004b45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b45f  lea     rcx, [rbp+var_50]
0x18004b463  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b468  lea     rcx, [rbp+var_48]
0x18004b46c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004b471  mov     eax, ebx
0x18004b473  mov     rcx, [rbp+var_8]
0x18004b477  xor     rcx, rsp; StackCookie
0x18004b47a  call    __security_check_cookie
0x18004b47f  mov     rbx, [rsp+70h+arg_8]
0x18004b487  add     rsp, 70h
0x18004b48b  pop     rdi
0x18004b48c  pop     rsi
0x18004b48d  pop     rbp
0x18004b48e  retn
```
