# Windows::Storage::FileProperties::GeotagHelper::GetGeotagAsync(Windows::Storage::IStorageFile *,Windows::Foundation::IAsyncOperation<Windows::Devices::Geolocation::Geopoint *> * *)

- ea: `0x1800469a0`
- end: `0x180046aab`
- name: `?GetGeotagAsync@GeotagHelper@FileProperties@Storage@Windows@@UEAAJPEAUIStorageFile@34@PEAPEAU?$IAsyncOperation@PEAVGeopoint@Geolocation@Devices@Windows@@@Foundation@4@@Z`
- size: `267`
- prototype: ``
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
- `0x18003f960`
- `0x180040188`
- `0x180041bd8`
- `0x1800469a0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800469f9`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800469f9`

## string_xrefs

- `0x180046a03`: `avcore\mf\photography\components\geotag\lib\geotag.cpp`

## pseudocode

```c
__int64 __fastcall Windows::Storage::FileProperties::GeotagHelper::GetGeotagAsync(__int64 a1, __int64 a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  __int64 v6; // rax
  __int64 v7; // r8
  __int64 v9; // [rsp+20h] [rbp-50h] BYREF
  __int64 v10; // [rsp+28h] [rbp-48h] BYREF
  int v11; // [rsp+30h] [rbp-40h] BYREF
  __int64 v12; // [rsp+34h] [rbp-3Ch]
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  __int64 v14; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+8h]

  *a3 = 0;
  if ( a2 )
  {
    v9 = a2;
    Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(&v9);
    Microsoft::WRL::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>(
      &v10,
      a1 - 40);
    v6 = lambda_26653df6241fa8643682b7a55d0c27f0_::_lambda_26653df6241fa8643682b7a55d0c27f0_(&hstringHeader, &v10, &v9);
    v11 = 3;
    v12 = 128;
    v5 = Windows::Internal::MakeAsyncOperation_Windows::Internal::CMarshaledInterfaceResult_Windows::Devices::Geolocation::IGeopoint__Windows::Devices::Geolocation::Geopoint___Windows::Internal::ComTaskPoolHandler__lambda_26653df6241fa8643682b7a55d0c27f0___(
           &v11,
           a3,
           v7,
           v6);
    lambda_26653df6241fa8643682b7a55d0c27f0_::__lambda_26653df6241fa8643682b7a55d0c27f0_(&hstringHeader);
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v9);
  }
  else
  {
    v14 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"Invalid file parameter", 0x17u, 0x16u);
    v5 = -2147467261;
    RoOriginateError(2147500035LL, v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x383,
      (unsigned int)"avcore\\mf\\photography\\components\\geotag\\lib\\geotag.cpp",
      (const char *)0x80004003LL,
      v9);
  }
  return v5;
}

```

## disassembly

```asm
0x1800469a0  mov     [rsp-8+arg_8], rbx
0x1800469a5  mov     [rsp-8+arg_18], rdi
0x1800469aa  push    rbp
0x1800469ab  mov     rbp, rsp
0x1800469ae  sub     rsp, 70h
0x1800469b2  mov     rax, cs:__security_cookie
0x1800469b9  xor     rax, rsp
0x1800469bc  mov     [rbp+var_10], rax
0x1800469c0  mov     qword ptr [r8], 0
0x1800469c7  mov     rbx, r8
0x1800469ca  mov     rdi, rcx
0x1800469cd  test    rdx, rdx
0x1800469d0  jnz     short loc_180046A19
0x1800469d2  mov     [rbp+var_18], rdx
0x1800469d6  lea     r9d, [rdx+16h]; unsigned int
0x1800469da  lea     r8d, [rdx+17h]; unsigned int
0x1800469de  lea     rdx, aInvalidFilePar; "Invalid file parameter"
0x1800469e5  lea     rcx, [rbp+hstringHeader]; hstringHeader
0x1800469e9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800469ee  mov     rdx, [rbp+var_18]
0x1800469f2  mov     ebx, 80004003h
0x1800469f7  mov     ecx, ebx
0x1800469f9  call    cs:__imp_RoOriginateError
0x1800469ff  mov     rcx, [rbp+8]; this
0x180046a03  lea     r8, aAvcoreMfPhotog; "avcore\\mf\\photography\\components\\ge"...
0x180046a0a  mov     r9d, ebx; char *
0x180046a0d  mov     edx, 383h; void *
0x180046a12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180046a17  jmp     short loc_180046A8B
0x180046a19  lea     rcx, [rbp+var_50]
0x180046a1d  mov     [rbp+var_50], rdx
0x180046a21  call    ?InternalAddRef@?$ComPtr@UIAsyncFireCompletion@Internal@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Internal::IAsyncFireCompletion>::InternalAddRef(void)
0x180046a26  lea     rdx, [rdi-28h]
0x180046a2a  lea     rcx, [rbp+var_48]
0x180046a2e  call    ??$?0VGeotagHelper@FileProperties@Storage@Windows@@@?$ComPtr@UIGeotagHelperStatics@FileProperties@Storage@Windows@@@WRL@Microsoft@@QEAA@PEAVGeotagHelper@FileProperties@Storage@Windows@@@Z; Microsoft::WRL::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>::ComPtr<Windows::Storage::FileProperties::IGeotagHelperStatics>(Windows::Storage::FileProperties::GeotagHelper *)
0x180046a33  lea     r8, [rbp+var_50]
0x180046a37  lea     rdx, [rbp+var_48]
0x180046a3b  lea     rcx, [rbp+hstringHeader]
0x180046a3f  call    _lambda_26653df6241fa8643682b7a55d0c27f0____lambda_26653df6241fa8643682b7a55d0c27f0_
0x180046a44  mov     r9, rax
0x180046a47  mov     [rbp+var_40], 3
0x180046a4e  mov     rdx, rbx
0x180046a51  mov     [rbp+var_3C], 80h
0x180046a59  lea     rcx, [rbp+var_40]
0x180046a5d  call    Windows__Internal__MakeAsyncOperation_Windows__Internal__CMarshaledInterfaceResult_Windows__Devices__Geolocation__IGeopoint__Windows__Devices__Geolocation__Geopoint___Windows__Internal__ComTaskPoolHandler__lambda_26653df6241fa8643682b7a55d0c27f0___
0x180046a62  lea     rcx, [rbp+hstringHeader]
0x180046a66  mov     ebx, eax
0x180046a68  call    _lambda_26653df6241fa8643682b7a55d0c27f0_____lambda_26653df6241fa8643682b7a55d0c27f0_
0x180046a6d  mov     rcx, [rbp+var_48]
0x180046a71  test    rcx, rcx
0x180046a74  jz      short loc_180046A82
0x180046a76  mov     rdx, [rcx]
0x180046a79  mov     rax, [rdx+10h]
0x180046a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180046a82  lea     rcx, [rbp+var_50]
0x180046a86  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180046a8b  mov     eax, ebx
0x180046a8d  mov     rcx, [rbp+var_10]
0x180046a91  xor     rcx, rsp; StackCookie
0x180046a94  call    __security_check_cookie
0x180046a99  lea     r11, [rsp+70h+var_s0]
0x180046a9e  mov     rbx, [r11+18h]
0x180046aa2  mov     rdi, [r11+28h]
0x180046aa6  mov     rsp, r11
0x180046aa9  pop     rbp
0x180046aaa  retn
```
