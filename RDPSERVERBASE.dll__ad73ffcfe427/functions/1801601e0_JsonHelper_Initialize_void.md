# JsonHelper::Initialize(void)

- ea: `0x1801601e0`
- end: `0x18016045d`
- name: `?Initialize@JsonHelper@@UEAAJXZ`
- size: `637`
- prototype: `__int64 __fastcall(JsonHelper *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180076090`
- `0x18007e9e0`
- `0x1800e91ac`
- `0x18015ee60`
- `0x18015ef50`
- `0x1801601e0`
- `0x180160464`
- `0x1801615b8`

## import_xrefs

- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160256`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18016029c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160312`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160389`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160407`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160256`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x18016029c`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160312`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160389`
- `RDPBASE!RdpX_GetActivityIdPrefix` at `0x180160407`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801603dc`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1801603dc`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180160203`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180160203`

## string_xrefs

- `0x1801603af`: `Windows.Data.Json.JsonValue`
- `0x1801602be`: `Windows.Data.Json.JsonObject`
- `0x180160339`: `Windows.Data.Json.JsonObject`
- `0x180160394`: `GetActivationFactory(JsonObject) failed!`
- `0x18016031b`: `ActivateInstance: JsonObject`
- `0x180160412`: `GetActivationFactory: JsonValue`

## pseudocode

```c
__int64 __fastcall JsonHelper::Initialize(JsonHelper *this)
{
  int ActivationFactory; // ebx
  __int64 v3; // rdx
  int ActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 v10; // rdx
  int v12; // [rsp+28h] [rbp-40h]
  HSTRING_HEADER hstringHeader; // [rsp+30h] [rbp-38h] BYREF
  __int64 v14; // [rsp+48h] [rbp-20h]

  ActivationFactory = RoInitialize(0);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetImpl'::`2'::impl) )
  {
    if ( ActivationFactory == -2147417850 )
      goto LABEL_15;
    if ( ActivationFactory < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3);
        v5 = 17;
LABEL_8:
        v6 = "Windows::Foundation::Initialize failed!";
LABEL_30:
        v12 = ActivationFactory;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v5,
          (unsigned int)WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids,
          ActivityIdPrefix,
          (__int64)v6,
          v12);
        return (unsigned int)ActivationFactory;
      }
      return (unsigned int)ActivationFactory;
    }
LABEL_14:
    *((_BYTE *)this + 64) = 1;
LABEL_15:
    v14 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Data.Json.JsonObject",
      0x1Du,
      0x1Cu);
    ActivationFactory = ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(
                          v14,
                          (char *)this + 40);
    if ( ActivationFactory >= 0 )
    {
      v14 = 0;
      Microsoft::WRL::Wrappers::HStringReference::CreateReference(
        &hstringHeader,
        L"Windows.Data.Json.JsonObject",
        0x1Du,
        0x1Cu);
      ActivationFactory = ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(
                            v14,
                            (char *)this + 48);
      if ( ActivationFactory >= 0 )
      {
        v14 = 0;
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"Windows.Data.Json.JsonValue",
          0x1Cu,
          0x1Bu);
        v9 = v14;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease((char *)this + 56);
        ActivationFactory = RoGetActivationFactory(v9, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, (char *)this + 56);
        if ( ActivationFactory < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v10);
          v5 = 21;
          v6 = "GetActivationFactory: JsonValue";
          goto LABEL_30;
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v8);
        v5 = 20;
        v6 = "GetActivationFactory(JsonObject) failed!";
        goto LABEL_30;
      }
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v7);
      v5 = 19;
      v6 = "ActivateInstance: JsonObject";
      goto LABEL_30;
    }
    return (unsigned int)ActivationFactory;
  }
  if ( ActivationFactory >= 0 )
    goto LABEL_14;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    ActivityIdPrefix = RdpX_GetActivityIdPrefix(WPP_GLOBAL_Control, v3);
    v5 = 18;
    goto LABEL_8;
  }
  return (unsigned int)ActivationFactory;
}

```

## disassembly

```asm
0x1801601e0  mov     [rsp+arg_8], rbx
0x1801601e5  mov     [rsp+arg_10], rsi
0x1801601ea  push    rdi
0x1801601eb  sub     rsp, 60h
0x1801601ef  mov     rax, cs:__security_cookie
0x1801601f6  xor     rax, rsp
0x1801601f9  mov     [rsp+68h+var_18], rax
0x1801601fe  mov     rsi, rcx
0x180160201  xor     ecx, ecx
0x180160203  call    cs:__imp_RoInitialize
0x180160209  mov     ebx, eax
0x18016020b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA> `wil::Feature<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::GetImpl(void)'::`2'::impl
0x180160212  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixJsonHelperCannotBeUsedInMTA>::__private_IsEnabled(void)
0x180160217  test    al, al
0x180160219  jz      short loc_18016026D
0x18016021b  cmp     ebx, 80010106h
0x180160221  jz      loc_1801602AD
0x180160227  test    ebx, ebx
0x180160229  jns     short loc_1801602A9
0x18016022b  mov     rcx, cs:WPP_GLOBAL_Control
0x180160232  lea     rax, WPP_GLOBAL_Control
0x180160239  cmp     rcx, rax
0x18016023c  jz      loc_18016043C
0x180160242  test    byte ptr [rcx+1Ch], 8
0x180160246  jz      loc_18016043C
0x18016024c  cmp     byte ptr [rcx+19h], 2
0x180160250  jb      loc_18016043C
0x180160256  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18016025c  mov     edx, 11h
0x180160261  lea     rcx, aWindowsFoundat; "Windows::Foundation::Initialize failed!"
0x180160268  jmp     loc_180160419
0x18016026d  test    ebx, ebx
0x18016026f  jns     short loc_1801602A9
0x180160271  mov     rcx, cs:WPP_GLOBAL_Control
0x180160278  lea     rax, WPP_GLOBAL_Control
0x18016027f  cmp     rcx, rax
0x180160282  jz      loc_18016043C
0x180160288  test    byte ptr [rcx+1Ch], 8
0x18016028c  jz      loc_18016043C
0x180160292  cmp     byte ptr [rcx+19h], 2
0x180160296  jb      loc_18016043C
0x18016029c  call    cs:__imp_RdpX_GetActivityIdPrefix
0x1801602a2  mov     edx, 12h
0x1801602a7  jmp     short loc_180160261
0x1801602a9  mov     byte ptr [rsi+40h], 1
0x1801602ad  mov     edi, 1Ch
0x1801602b2  mov     [rsp+68h+var_20], 0
0x1801602bb  mov     r9d, edi; unsigned int
0x1801602be  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x1801602c5  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1801602ca  lea     r8d, [rdi+1]; unsigned int
0x1801602ce  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801602d3  mov     rcx, [rsp+68h+var_20]
0x1801602d8  lea     rdx, [rsi+28h]
0x1801602dc  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1801602e1  mov     ebx, eax
0x1801602e3  test    eax, eax
0x1801602e5  jns     short loc_180160327
0x1801602e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1801602ee  lea     rax, WPP_GLOBAL_Control
0x1801602f5  cmp     rcx, rax
0x1801602f8  jz      loc_18016043C
0x1801602fe  test    byte ptr [rcx+1Ch], 8
0x180160302  jz      loc_18016043C
0x180160308  cmp     byte ptr [rcx+19h], 2
0x18016030c  jb      loc_18016043C
0x180160312  call    cs:__imp_RdpX_GetActivityIdPrefix
0x180160318  lea     edx, [rdi-9]
0x18016031b  lea     rcx, aActivateinstan; "ActivateInstance: JsonObject"
0x180160322  jmp     loc_180160419
0x180160327  mov     r9d, edi; unsigned int
0x18016032a  mov     [rsp+68h+var_20], 0
0x180160333  mov     r8d, 1Dh; unsigned int
0x180160339  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180160340  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180160345  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18016034a  mov     rcx, [rsp+68h+var_20]
0x18016034f  lea     rdx, [rsi+30h]
0x180160353  call    ??$GetActivationFactory@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@ABI@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObjectStatics@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; ABI::Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObjectStatics>>)
0x180160358  mov     ebx, eax
0x18016035a  test    eax, eax
0x18016035c  jns     short loc_18016039D
0x18016035e  mov     rcx, cs:WPP_GLOBAL_Control
0x180160365  lea     rax, WPP_GLOBAL_Control
0x18016036c  cmp     rcx, rax
0x18016036f  jz      loc_18016043C
0x180160375  test    byte ptr [rcx+1Ch], 8
0x180160379  jz      loc_18016043C
0x18016037f  cmp     byte ptr [rcx+19h], 2
0x180160383  jb      loc_18016043C
0x180160389  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18016038f  mov     edx, 14h
0x180160394  lea     rcx, aGetactivationf_0; "GetActivationFactory(JsonObject) failed"...
0x18016039b  jmp     short loc_180160419
0x18016039d  mov     r9d, 1Bh; unsigned int
0x1801603a3  mov     [rsp+68h+var_20], 0
0x1801603ac  mov     r8d, edi; unsigned int
0x1801603af  lea     rdx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x1801603b6  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x1801603bb  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1801603c0  mov     rdi, [rsp+68h+var_20]
0x1801603c5  lea     rcx, [rsi+38h]
0x1801603c9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUIJsonValue@Json@Data@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<Windows::Data::Json::IJsonValue *>>::InternalRelease(void)
0x1801603ce  lea     r8, [rsi+38h]
0x1801603d2  mov     rcx, rdi
0x1801603d5  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x1801603dc  call    cs:__imp_RoGetActivationFactory
0x1801603e2  mov     ebx, eax
0x1801603e4  test    eax, eax
0x1801603e6  jns     short loc_18016043C
0x1801603e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1801603ef  lea     rax, WPP_GLOBAL_Control
0x1801603f6  cmp     rcx, rax
0x1801603f9  jz      short loc_18016043C
0x1801603fb  test    byte ptr [rcx+1Ch], 8
0x1801603ff  jz      short loc_18016043C
0x180160401  cmp     byte ptr [rcx+19h], 2
0x180160405  jb      short loc_18016043C
0x180160407  call    cs:__imp_RdpX_GetActivityIdPrefix
0x18016040d  mov     edx, 15h
0x180160412  lea     rcx, aGetactivationf_1; "GetActivationFactory: JsonValue"
0x180160419  mov     [rsp+68h+var_40], ebx
0x18016041d  lea     r8, WPP_7988be81cbd83a4b56cd906cafb5d8b0_Traceguids
0x180160424  mov     [rsp+68h+var_48], rcx
0x180160429  mov     r9d, eax
0x18016042c  mov     rcx, cs:WPP_GLOBAL_Control
0x180160433  mov     rcx, [rcx+10h]
0x180160437  call    WPP_SF_DsD
0x18016043c  mov     eax, ebx
0x18016043e  mov     rcx, [rsp+68h+var_18]
0x180160443  xor     rcx, rsp; StackCookie
0x180160446  call    __security_check_cookie
0x18016044b  lea     r11, [rsp+68h+var_8]
0x180160450  mov     rbx, [r11+18h]
0x180160454  mov     rsi, [r11+20h]
0x180160458  mov     rsp, r11
0x18016045b  pop     rdi
0x18016045c  retn
```
