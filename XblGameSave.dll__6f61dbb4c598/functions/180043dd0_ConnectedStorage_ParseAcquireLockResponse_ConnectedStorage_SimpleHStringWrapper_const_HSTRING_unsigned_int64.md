# ConnectedStorage::ParseAcquireLockResponse(ConnectedStorage::SimpleHStringWrapper const &,HSTRING__ * *,unsigned __int64 *)

- ea: `0x180043dd0`
- end: `0x180043fae`
- name: `?ParseAcquireLockResponse@ConnectedStorage@@YAXAEBVSimpleHStringWrapper@1@PEAPEAUHSTRING__@@PEA_K@Z`
- size: `478`
- prototype: `void __fastcall(ConnectedStorage *__hidden this, const struct ConnectedStorage::SimpleHStringWrapper *, HSTRING *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003fa60`

## callees

- `0x180003c70`
- `0x18000a040`
- `0x18000aae4`
- `0x180011c0c`
- `0x18002a6a8`
- `0x18003c1ac`
- `0x180043dd0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043f5a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043edb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043f5a`

## string_xrefs

- `0x180043e24`: `Windows.Data.Json.JsonObject`
- `0x180043e48`: `GetActivationFactory( HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), &jsonObjectStatics)`
- `0x180043e8c`: `jsonObjectStatics->Parse( json.Get(), &jsonObject)`
- `0x180043f64`: `jsonObject->GetNamedString( SimpleHStringWrapper(L"ownerChangeId").Get(), ownerChangeId)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ConnectedStorage::ParseAcquireLockResponse(
        ConnectedStorage *this,
        const struct ConnectedStorage::SimpleHStringWrapper *a2,
        HSTRING *a3,
        unsigned __int64 *a4)
{
  int v7; // eax
  const unsigned __int16 *v8; // r8
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rbx
  int v11; // eax
  const unsigned __int16 *v12; // r8
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, HSTRING, double *); // rdi
  HSTRING *v15; // rax
  unsigned __int64 v16; // rcx
  double v17; // xmm0_8
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 (__fastcall *v20)(__int64, HSTRING, const struct ConnectedStorage::SimpleHStringWrapper *); // rdi
  HSTRING *v21; // rax
  int v22; // ebx
  const unsigned __int16 *v23; // r8
  __int64 v24; // [rsp+20h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+28h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+30h] [rbp-A8h] BYREF
  double v27; // [rsp+38h] [rbp-A0h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-98h] BYREF
  __int64 v29; // [rsp+58h] [rbp-80h]
  _BYTE v30[64]; // [rsp+60h] [rbp-78h] BYREF

  *a3 = 0;
  *(_QWORD *)a2 = 0;
  v25 = 0;
  v29 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Data.Json.JsonObject",
    0x1Du,
    0x1Cu);
  v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
         v29,
         (__int64)&v25);
  try
  {
    if ( v7 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v7,
        (int)L"GetActivationFactory( HStringReference(RuntimeClass_Windows_Data_Json_JsonObject).Get(), &jsonObjectStatics)",
        v8);
    v24 = 0;
    v9 = v25;
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v25 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    v11 = v10(v9, *(_QWORD *)this, &v24);
    if ( v11 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v11,
        (int)L"jsonObjectStatics->Parse( json.Get(), &jsonObject)",
        v12);
    v27 = 0.0;
    v13 = v24;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING, double *))(*(_QWORD *)v24 + 88LL);
    v15 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"quotaBytes");
    LODWORD(v13) = v14(v13, *v15, &v27);
    WindowsDeleteString(string);
    if ( (int)v13 < 0 )
    {
      v18 = 0x10000000;
    }
    else
    {
      v16 = 0;
      v17 = v27;
      if ( v27 >= 9.223372036854776e18 )
      {
        v17 = v27 - 9.223372036854776e18;
        if ( v27 - 9.223372036854776e18 < 9.223372036854776e18 )
          v16 = 0x8000000000000000uLL;
      }
      v18 = v16 + (unsigned int)(int)v17;
    }
    *a3 = (HSTRING)v18;
    v19 = v24;
    v20 = *(__int64 (__fastcall **)(__int64, HSTRING, const struct ConnectedStorage::SimpleHStringWrapper *))(*(_QWORD *)v24 + 80LL);
    v21 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, L"ownerChangeId");
    v22 = v20(v19, *v21, a2);
    WindowsDeleteString(string);
    if ( v22 < 0 )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)(unsigned int)v22,
        (int)L"jsonObject->GetNamedString( SimpleHStringWrapper(L\"ownerChangeId\").Get(), ownerChangeId)",
        v23);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v24);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v25);
  }
  catch ( ConnectedStorage::ComError v30 )
  {
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v30);
    return;
  }
  catch ( std::bad_alloc )
  {
    return;
  }
  catch ( ... )
  {
  }
}

```

## disassembly

```asm
0x180043dd0  push    rbx
0x180043dd2  push    rsi
0x180043dd3  push    rdi
0x180043dd4  push    r14
0x180043dd6  push    r15
0x180043dd8  sub     rsp, 0B0h
0x180043ddf  mov     rax, cs:__security_cookie
0x180043de6  xor     rax, rsp
0x180043de9  mov     [rsp+0D8h+var_38], rax
0x180043df1  mov     rsi, r8
0x180043df4  mov     r15, rdx
0x180043df7  mov     r14, rcx
0x180043dfa  mov     qword ptr [r8], 0
0x180043e01  mov     qword ptr [rdx], 0
0x180043e08  mov     [rsp+0D8h+var_B0], 0
0x180043e11  mov     [rsp+0D8h+var_80], 0
0x180043e1a  mov     r9d, 1Ch; unsigned int
0x180043e20  lea     r8d, [r9+1]; unsigned int
0x180043e24  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180043e2b  lea     rcx, [rsp+0D8h+hstringHeader]; hstringHeader
0x180043e30  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180043e35  lea     rdx, [rsp+0D8h+var_B0]
0x180043e3a  mov     rcx, [rsp+0D8h+var_80]
0x180043e3f  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180043e44  test    eax, eax
0x180043e46  jns     short loc_180043E56
0x180043e48  lea     rdx, aGetactivationf_2; "GetActivationFactory( HStringReference("...
0x180043e4f  mov     ecx, eax; this
0x180043e51  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180043e56  mov     [rsp+0D8h+var_B8], 0
0x180043e5f  mov     rdi, [rsp+0D8h+var_B0]
0x180043e64  mov     rax, [rdi]
0x180043e67  mov     rbx, [rax+30h]
0x180043e6b  lea     rcx, [rsp+0D8h+var_B8]
0x180043e70  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180043e75  lea     r8, [rsp+0D8h+var_B8]
0x180043e7a  mov     rdx, [r14]
0x180043e7d  mov     rcx, rdi
0x180043e80  mov     rax, rbx
0x180043e83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043e88  test    eax, eax
0x180043e8a  jns     short loc_180043E9A
0x180043e8c  lea     rdx, aJsonobjectstat_0; "jsonObjectStatics->Parse( json.Get(), &"...
0x180043e93  mov     ecx, eax; this
0x180043e95  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180043e9a  xorps   xmm0, xmm0
0x180043e9d  movsd   [rsp+0D8h+var_A0], xmm0
0x180043ea3  mov     rbx, [rsp+0D8h+var_B8]
0x180043ea8  mov     rax, [rbx]
0x180043eab  mov     rdi, [rax+58h]
0x180043eaf  lea     rdx, aQuotabytes; "quotaBytes"
0x180043eb6  lea     rcx, [rsp+0D8h+string]; string
0x180043ebb  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180043ec0  nop
0x180043ec1  lea     r8, [rsp+0D8h+var_A0]
0x180043ec6  mov     rdx, [rax]
0x180043ec9  mov     rcx, rbx
0x180043ecc  mov     rax, rdi
0x180043ecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043ed4  mov     ebx, eax
0x180043ed6  mov     rcx, [rsp+0D8h+string]; string
0x180043edb  call    cs:__imp_WindowsDeleteString
0x180043ee1  test    ebx, ebx
0x180043ee3  js      short loc_180043F1C
0x180043ee5  xor     ecx, ecx
0x180043ee7  movsd   xmm0, [rsp+0D8h+var_A0]
0x180043eed  movsd   xmm1, cs:__real@43e0000000000000
0x180043ef5  comisd  xmm0, xmm1
0x180043ef9  jb      short loc_180043F12
0x180043efb  subsd   xmm0, xmm1
0x180043eff  comisd  xmm0, xmm1
0x180043f03  jnb     short loc_180043F12
0x180043f05  mov     rax, 8000000000000000h
0x180043f0f  mov     rcx, rax
0x180043f12  cvttsd2si rax, xmm0
0x180043f17  add     rax, rcx
0x180043f1a  jmp     short loc_180043F21
0x180043f1c  mov     eax, 10000000h
0x180043f21  mov     [rsi], rax
0x180043f24  mov     rbx, [rsp+0D8h+var_B8]
0x180043f29  mov     rax, [rbx]
0x180043f2c  mov     rdi, [rax+50h]
0x180043f30  lea     rdx, aOwnerchangeid; "ownerChangeId"
0x180043f37  lea     rcx, [rsp+0D8h+string]; string
0x180043f3c  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x180043f41  nop
0x180043f42  mov     r8, r15
0x180043f45  mov     rdx, [rax]
0x180043f48  mov     rcx, rbx
0x180043f4b  mov     rax, rdi
0x180043f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043f53  mov     ebx, eax
0x180043f55  mov     rcx, [rsp+0D8h+string]; string
0x180043f5a  call    cs:__imp_WindowsDeleteString
0x180043f60  test    ebx, ebx
0x180043f62  jns     short loc_180043F73
0x180043f64  lea     rdx, aJsonobjectGetn_0; "jsonObject->GetNamedString( SimpleHStri"...
0x180043f6b  mov     ecx, ebx; this
0x180043f6d  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x180043f73  lea     rcx, [rsp+0D8h+var_B8]
0x180043f78  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180043f7d  nop
0x180043f7e  lea     rcx, [rsp+0D8h+var_B0]
0x180043f83  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180043f88  nop
0x180043f89  jmp     short loc_180043F8F
0x180043f8b  jmp     short loc_180043F8F
0x180043f8d  jmp     short $+2
0x180043f8f  mov     rcx, [rsp+0D8h+var_38]
0x180043f97  xor     rcx, rsp; StackCookie
0x180043f9a  call    __security_check_cookie
0x180043f9f  add     rsp, 0B0h
0x180043fa6  pop     r15
0x180043fa8  pop     r14
0x180043faa  pop     rdi
0x180043fab  pop     rsi
0x180043fac  pop     rbx
0x180043fad  retn
```
