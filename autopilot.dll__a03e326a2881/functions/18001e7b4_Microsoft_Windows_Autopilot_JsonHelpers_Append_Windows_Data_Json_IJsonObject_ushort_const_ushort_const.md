# Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)

- ea: `0x18001e7b4`
- end: `0x18001e9fd`
- name: `?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z`
- size: `585`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019ef0`
- `0x18001a280`
- `0x18001a4e4`
- `0x18001ab88`
- `0x18001ada0`
- `0x180024c34`
- `0x180026b60`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800180a8`
- `0x18001e658`
- `0x18001e7b4`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e800`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001e800`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e83e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001e83e`

## string_xrefs

- `0x18001e7f9`: `Windows.Data.Json.JsonValue`
- `0x18001e851`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001e8c8`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001e948`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::Append(
        struct Windows::Data::Json::IJsonObject *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, struct Windows::Data::Json::IJsonValue **); // rbx
  __int64 v13; // rax
  int v14; // eax
  struct Windows::Data::Json::IJsonValue *v15; // rcx
  __int64 v16; // rcx
  struct Windows::Data::Json::IJsonValue *v17; // rbx
  __int64 v18; // rax
  int v19; // eax
  struct Windows::Data::Json::IJsonValue *v20; // rcx
  __int64 v21; // rcx
  struct Windows::Data::Json::IJsonValue *v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // [rsp+20h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v25; // [rsp+28h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+30h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v27 = a2;
  v26 = a3;
  v24 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18001E9FCLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v24);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v24);
    v9 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v25 = 0;
  v11 = v24;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v24 + 80LL);
  v13 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v26);
  v14 = v12(v11, *(_QWORD *)(v13 + 24), &v25);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v14,
      v24);
    v15 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  v17 = v25;
  v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v27);
  v19 = Microsoft::Windows::Autopilot::JsonHelpers::Append(a1, *(HSTRING *)(v18 + 24), v17);
  v8 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v19,
      v24);
    v20 = v25;
    if ( v25 )
    {
      v25 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v20 + 16LL))(v20);
    }
    v21 = v24;
    if ( v24 )
    {
      v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    return v8;
  }
  v22 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v22 + 16LL))(v22);
  }
  v23 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  }
  return 0;
}

```

## disassembly

```asm
0x18001e7b4  mov     [rsp-18h+arg_18], rbx
0x18001e7b9  push    rbp
0x18001e7ba  push    rsi
0x18001e7bb  push    rdi
0x18001e7bc  mov     rbp, rsp
0x18001e7bf  sub     rsp, 70h
0x18001e7c3  mov     rax, cs:__security_cookie
0x18001e7ca  xor     rax, rsp
0x18001e7cd  mov     [rbp+var_10], rax
0x18001e7d1  mov     rsi, rcx
0x18001e7d4  mov     [rbp+var_38], rdx
0x18001e7d8  mov     [rbp+var_40], r8
0x18001e7dc  mov     [rbp+var_50], 0
0x18001e7e4  mov     [rbp+string], 0
0x18001e7ec  lea     r9, [rbp+string]; string
0x18001e7f0  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001e7f4  mov     edx, 1Bh; length
0x18001e7f9  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001e800  call    cs:__imp_WindowsCreateStringReference
0x18001e806  test    eax, eax
0x18001e808  js      loc_18001E9F5
0x18001e80e  mov     rbx, [rbp+string]
0x18001e812  mov     rcx, [rbp+var_50]
0x18001e816  test    rcx, rcx
0x18001e819  jz      short loc_18001E830
0x18001e81b  mov     [rbp+var_50], 0
0x18001e823  mov     rax, [rcx]
0x18001e826  mov     rax, [rax+10h]
0x18001e82a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e82f  nop
0x18001e830  lea     r8, [rbp+var_50]
0x18001e834  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001e83b  mov     rcx, rbx
0x18001e83e  call    cs:__imp_RoGetActivationFactory
0x18001e844  mov     ebx, eax
0x18001e846  test    eax, eax
0x18001e848  jns     short loc_18001E888
0x18001e84a  mov     rcx, [rbp+18h]; this
0x18001e84e  mov     r9d, eax; char *
0x18001e851  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e858  mov     edx, 2Ah ; '*'; void *
0x18001e85d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e862  nop
0x18001e863  mov     rcx, [rbp+var_50]
0x18001e867  test    rcx, rcx
0x18001e86a  jz      short loc_18001E881
0x18001e86c  mov     [rbp+var_50], 0
0x18001e874  mov     rax, [rcx]
0x18001e877  mov     rax, [rax+10h]
0x18001e87b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e880  nop
0x18001e881  mov     eax, ebx
0x18001e883  jmp     loc_18001E9D9
0x18001e888  mov     [rbp+var_48], 0
0x18001e890  mov     rdi, [rbp+var_50]
0x18001e894  mov     rax, [rdi]
0x18001e897  mov     rbx, [rax+50h]
0x18001e89b  lea     rdx, [rbp+var_40]
0x18001e89f  lea     rcx, [rbp+hstringHeader]
0x18001e8a3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e8a8  lea     r8, [rbp+var_48]
0x18001e8ac  mov     rdx, [rax+18h]
0x18001e8b0  mov     rcx, rdi
0x18001e8b3  mov     rax, rbx
0x18001e8b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8bb  mov     ebx, eax
0x18001e8bd  test    eax, eax
0x18001e8bf  jns     short loc_18001E91B
0x18001e8c1  mov     rcx, [rbp+18h]; this
0x18001e8c5  mov     r9d, eax; char *
0x18001e8c8  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e8cf  mov     edx, 2Dh ; '-'; void *
0x18001e8d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8d9  nop
0x18001e8da  mov     rcx, [rbp+var_48]
0x18001e8de  test    rcx, rcx
0x18001e8e1  jz      short loc_18001E8F8
0x18001e8e3  mov     [rbp+var_48], 0
0x18001e8eb  mov     rax, [rcx]
0x18001e8ee  mov     rax, [rax+10h]
0x18001e8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8f7  nop
0x18001e8f8  mov     rcx, [rbp+var_50]
0x18001e8fc  test    rcx, rcx
0x18001e8ff  jz      short loc_18001E916
0x18001e901  mov     [rbp+var_50], 0
0x18001e909  mov     rax, [rcx]
0x18001e90c  mov     rax, [rax+10h]
0x18001e910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e915  nop
0x18001e916  jmp     loc_18001E881
0x18001e91b  mov     rbx, [rbp+var_48]
0x18001e91f  lea     rdx, [rbp+var_38]
0x18001e923  lea     rcx, [rbp+hstringHeader]
0x18001e927  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001e92c  mov     r8, rbx; struct Windows::Data::Json::IJsonValue *
0x18001e92f  mov     rdx, [rax+18h]; HSTRING
0x18001e933  mov     rcx, rsi; struct Windows::Data::Json::IJsonObject *
0x18001e936  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)
0x18001e93b  mov     ebx, eax
0x18001e93d  test    eax, eax
0x18001e93f  jns     short loc_18001E99B
0x18001e941  mov     rcx, [rbp+18h]; this
0x18001e945  mov     r9d, eax; char *
0x18001e948  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001e94f  mov     edx, 2Fh ; '/'; void *
0x18001e954  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e959  nop
0x18001e95a  mov     rcx, [rbp+var_48]
0x18001e95e  test    rcx, rcx
0x18001e961  jz      short loc_18001E978
0x18001e963  mov     [rbp+var_48], 0
0x18001e96b  mov     rax, [rcx]
0x18001e96e  mov     rax, [rax+10h]
0x18001e972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e977  nop
0x18001e978  mov     rcx, [rbp+var_50]
0x18001e97c  test    rcx, rcx
0x18001e97f  jz      short loc_18001E996
0x18001e981  mov     [rbp+var_50], 0
0x18001e989  mov     rax, [rcx]
0x18001e98c  mov     rax, [rax+10h]
0x18001e990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e995  nop
0x18001e996  jmp     loc_18001E881
0x18001e99b  mov     rcx, [rbp+var_48]
0x18001e99f  test    rcx, rcx
0x18001e9a2  jz      short loc_18001E9B9
0x18001e9a4  mov     [rbp+var_48], 0
0x18001e9ac  mov     rax, [rcx]
0x18001e9af  mov     rax, [rax+10h]
0x18001e9b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9b8  nop
0x18001e9b9  mov     rcx, [rbp+var_50]
0x18001e9bd  test    rcx, rcx
0x18001e9c0  jz      short loc_18001E9D7
0x18001e9c2  mov     [rbp+var_50], 0
0x18001e9ca  mov     rax, [rcx]
0x18001e9cd  mov     rax, [rax+10h]
0x18001e9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9d6  nop
0x18001e9d7  xor     eax, eax
0x18001e9d9  mov     rcx, [rbp+var_10]
0x18001e9dd  xor     rcx, rsp; StackCookie
0x18001e9e0  call    __security_check_cookie
0x18001e9e5  mov     rbx, [rsp+70h+arg_18]
0x18001e9ed  add     rsp, 70h
0x18001e9f1  pop     rdi
0x18001e9f2  pop     rsi
0x18001e9f3  pop     rbp
0x18001e9f4  retn
0x18001e9f5  mov     ecx, eax; this
0x18001e9f7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
