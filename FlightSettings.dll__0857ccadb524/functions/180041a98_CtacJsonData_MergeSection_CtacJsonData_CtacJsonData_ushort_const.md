# CtacJsonData::MergeSection(CtacJsonData *,CtacJsonData *,ushort const *)

- ea: `0x180041a98`
- end: `0x180041c3e`
- name: `?MergeSection@CtacJsonData@@CAJPEAV1@0PEBG@Z`
- size: `422`
- prototype: `static int(struct CtacJsonData *, struct CtacJsonData *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180041c68`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x1800349c0`
- `0x180040c20`
- `0x1800417e8`
- `0x180041938`
- `0x180041a98`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041b07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041b9c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041b07`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180041b9c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041bb0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041b1b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180041bb0`

## string_xrefs

- `0x180041b42`: `onecore\base\flighting\flightsettings\broker\libs\ctac\ctacjsondata.cpp`
- `0x180041bd7`: `onecore\base\flighting\flightsettings\broker\libs\ctac\ctacjsondata.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CtacJsonData::MergeSection(
        struct Windows::Data::Json::IJsonObject **a1,
        struct Windows::Data::Json::IJsonObject **a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  int JsonNamedObjectIfExists; // eax
  unsigned int v9; // ebx
  int JsonNamedObjectOrCreate; // eax
  __int64 v11; // rax
  UINT32 length; // [rsp+20h] [rbp-40h] BYREF
  int v14; // [rsp+24h] [rbp-3Ch] BYREF
  struct Windows::Data::Json::IJsonObject *v15; // [rsp+28h] [rbp-38h] BYREF
  struct Windows::Data::Json::IJsonObject *v16; // [rsp+30h] [rbp-30h] BYREF
  HSTRING string; // [rsp+38h] [rbp-28h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v14 = 0;
  v16 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  length = 0;
  v6 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(a3, length, &hstringHeader, &string);
  JsonNamedObjectIfExists = CtacJsonData::GetJsonNamedObjectIfExists(a1[2], string, &v16);
  v9 = JsonNamedObjectIfExists;
  v14 = JsonNamedObjectIfExists;
  if ( JsonNamedObjectIfExists >= 0 )
  {
    if ( JsonNamedObjectIfExists )
    {
      v9 = 0;
    }
    else
    {
      v15 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
      length = 0;
      do
        ++v6;
      while ( a3[v6] );
      if ( (int)ULongLongToUInt(v6, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(a3, length, &hstringHeader, &string);
      JsonNamedObjectOrCreate = CtacJsonData::GetJsonNamedObjectOrCreate(a2[2], string, &v15);
      v9 = JsonNamedObjectOrCreate;
      v14 = JsonNamedObjectOrCreate;
      if ( JsonNamedObjectOrCreate >= 0 )
      {
        v11 = _lambda_af06e9d9b41286567a29afe0dcb44c45_::_lambda_af06e9d9b41286567a29afe0dcb44c45_(&string, &v14, &v15);
        v9 = FoundationCollectionHelper::ForEachKvp_HSTRING_____Windows::Data::Json::IJsonValue____lambda_d9b0dbee15ce54bbc14ce5e319bfae88___(
               v16,
               v11);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x168,
          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\ctacjsondata.cpp",
          (const char *)(unsigned int)JsonNamedObjectOrCreate,
          length);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v15);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15B,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\ctacjsondata.cpp",
      (const char *)(unsigned int)JsonNamedObjectIfExists,
      length);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v16);
  return v9;
}

```

## disassembly

```asm
0x180041a98  mov     [rsp-28h+arg_18], rbx
0x180041a9d  push    rbp
0x180041a9e  push    rsi
0x180041a9f  push    rdi
0x180041aa0  push    r14
0x180041aa2  push    r15
0x180041aa4  mov     rbp, rsp
0x180041aa7  sub     rsp, 60h
0x180041aab  mov     rax, cs:__security_cookie
0x180041ab2  xor     rax, rsp
0x180041ab5  mov     [rbp+var_8], rax
0x180041ab9  mov     rsi, r8
0x180041abc  mov     r14, rdx
0x180041abf  mov     rbx, rcx
0x180041ac2  xor     r15d, r15d
0x180041ac5  mov     [rbp+var_3C], r15d
0x180041ac9  mov     [rbp+var_30], r15
0x180041acd  lea     rcx, [rbp+var_30]
0x180041ad1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041ad6  mov     [rbp+length], r15d
0x180041ada  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180041ade  mov     rcx, rdi
0x180041ae1  inc     rcx; unsigned __int64
0x180041ae4  cmp     [rsi+rcx*2], r15w
0x180041ae9  jnz     short loc_180041AE1
0x180041aeb  lea     rdx, [rbp+length]; unsigned int *
0x180041aef  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180041af4  test    eax, eax
0x180041af6  jns     short loc_180041B0D
0x180041af8  xor     r9d, r9d; lpArguments
0x180041afb  xor     r8d, r8d; nNumberOfArguments
0x180041afe  lea     edx, [r9+1]; dwExceptionFlags
0x180041b02  mov     ecx, 0C000000Dh; dwExceptionCode
0x180041b07  call    cs:__imp_RaiseException
0x180041b0d  lea     r9, [rbp+string]; string
0x180041b11  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180041b15  mov     edx, [rbp+length]; length
0x180041b18  mov     rcx, rsi; sourceString
0x180041b1b  call    cs:__imp_WindowsCreateStringReference
0x180041b21  lea     r8, [rbp+var_30]; struct Windows::Data::Json::IJsonObject **
0x180041b25  mov     rdx, [rbp+string]; HSTRING
0x180041b29  mov     rcx, [rbx+10h]; struct Windows::Data::Json::IJsonObject *
0x180041b2d  call    ?GetJsonNamedObjectIfExists@CtacJsonData@@CAJPEAUIJsonObject@Json@Data@Windows@@PEAUHSTRING__@@PEAPEAU2345@@Z; CtacJsonData::GetJsonNamedObjectIfExists(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180041b32  mov     ebx, eax
0x180041b34  mov     [rbp+var_3C], eax
0x180041b37  test    eax, eax
0x180041b39  jns     short loc_180041B58
0x180041b3b  mov     rcx, [rbp+28h]; this
0x180041b3f  mov     r9d, eax; char *
0x180041b42  lea     r8, aOnecoreBaseFli_83; "onecore\\base\\flighting\\flightsetting"...
0x180041b49  mov     edx, 15Bh; void *
0x180041b4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041b53  jmp     loc_180041C13
0x180041b58  jz      short loc_180041B62
0x180041b5a  mov     ebx, r15d
0x180041b5d  jmp     loc_180041C13
0x180041b62  mov     [rbp+var_38], r15
0x180041b66  lea     rcx, [rbp+var_38]
0x180041b6a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041b6f  mov     [rbp+length], r15d
0x180041b73  inc     rdi
0x180041b76  cmp     [rsi+rdi*2], r15w
0x180041b7b  jnz     short loc_180041B73
0x180041b7d  lea     rdx, [rbp+length]; unsigned int *
0x180041b81  mov     rcx, rdi; unsigned __int64
0x180041b84  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180041b89  test    eax, eax
0x180041b8b  jns     short loc_180041BA2
0x180041b8d  xor     r9d, r9d; lpArguments
0x180041b90  xor     r8d, r8d; nNumberOfArguments
0x180041b93  lea     edx, [r9+1]; dwExceptionFlags
0x180041b97  mov     ecx, 0C000000Dh; dwExceptionCode
0x180041b9c  call    cs:__imp_RaiseException
0x180041ba2  lea     r9, [rbp+string]; string
0x180041ba6  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180041baa  mov     edx, [rbp+length]; length
0x180041bad  mov     rcx, rsi; sourceString
0x180041bb0  call    cs:__imp_WindowsCreateStringReference
0x180041bb6  lea     r8, [rbp+var_38]; struct Windows::Data::Json::IJsonObject **
0x180041bba  mov     rdx, [rbp+string]; HSTRING
0x180041bbe  mov     rcx, [r14+10h]; struct Windows::Data::Json::IJsonObject *
0x180041bc2  call    ?GetJsonNamedObjectOrCreate@CtacJsonData@@CAJPEAUIJsonObject@Json@Data@Windows@@PEAUHSTRING__@@PEAPEAU2345@@Z; CtacJsonData::GetJsonNamedObjectOrCreate(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180041bc7  mov     ebx, eax
0x180041bc9  mov     [rbp+var_3C], eax
0x180041bcc  test    eax, eax
0x180041bce  jns     short loc_180041BEA
0x180041bd0  mov     rcx, [rbp+28h]; this
0x180041bd4  mov     r9d, eax; char *
0x180041bd7  lea     r8, aOnecoreBaseFli_83; "onecore\\base\\flighting\\flightsetting"...
0x180041bde  mov     edx, 168h; void *
0x180041be3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180041be8  jmp     short loc_180041C09
0x180041bea  lea     r8, [rbp+var_38]
0x180041bee  lea     rdx, [rbp+var_3C]
0x180041bf2  lea     rcx, [rbp+string]
0x180041bf6  call    ??0_lambda_af06e9d9b41286567a29afe0dcb44c45_@@QEAA@PEAV?$SimpleVectorIterator@UPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@Internal@Windows@@V?$Vector@UPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@Internal@Windows@@UPreviewFeatureUpdateEquality@@UPodLifetimeTraits@XWinRT@@U?$DefaultVectorOptions@UPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@Internal@Windows@@@4Collections@Foundation@5@@4Collections@Foundation@5@UPodLifetimeTraits@XWinRT@@UIntVersionTag@XWinRT@@$0A@@Internal@Collections@Foundation@Windows@@AEAPEAUPreviewFeatureConfigurationUpdate@FeatureConfiguration@Flighting@25@@Z; _lambda_af06e9d9b41286567a29afe0dcb44c45_::_lambda_af06e9d9b41286567a29afe0dcb44c45_(Windows::Foundation::Collections::Internal::SimpleVectorIterator<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate,Windows::Foundation::Collections::Internal::Vector<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate,PreviewFeatureUpdateEquality,XWinRT::PodLifetimeTraits,Windows::Foundation::Collections::Internal::DefaultVectorOptions<Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate>>,XWinRT::PodLifetimeTraits,XWinRT::IntVersionTag,0> *,Windows::Internal::Flighting::FeatureConfiguration::PreviewFeatureConfigurationUpdate * &)
0x180041bfb  mov     rdx, rax
0x180041bfe  mov     rcx, [rbp+var_30]
0x180041c02  call    FoundationCollectionHelper__ForEachKvp_HSTRING_____Windows__Data__Json__IJsonValue____lambda_d9b0dbee15ce54bbc14ce5e319bfae88___
0x180041c07  mov     ebx, eax
0x180041c09  lea     rcx, [rbp+var_38]
0x180041c0d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041c12  nop
0x180041c13  lea     rcx, [rbp+var_30]
0x180041c17  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180041c1c  mov     eax, ebx
0x180041c1e  mov     rcx, [rbp+var_8]
0x180041c22  xor     rcx, rsp; StackCookie
0x180041c25  call    __security_check_cookie
0x180041c2a  mov     rbx, [rsp+60h+arg_18]
0x180041c32  add     rsp, 60h
0x180041c36  pop     r15
0x180041c38  pop     r14
0x180041c3a  pop     rdi
0x180041c3b  pop     rsi
0x180041c3c  pop     rbp
0x180041c3d  retn
```
