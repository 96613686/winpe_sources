# Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)

- ea: `0x18001ea04`
- end: `0x18001ec40`
- name: `?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z`
- size: `572`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ada0`
- `0x180026b60`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800180a8`
- `0x18001e658`
- `0x18001ea04`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ea4f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ea4f`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea8d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ea8d`

## string_xrefs

- `0x18001ea48`: `Windows.Data.Json.JsonValue`
- `0x18001eaa0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001eb0b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001eb8b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::Append(
        struct Windows::Data::Json::IJsonObject *a1,
        const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // edx
  unsigned int v5; // r8d
  int ActivationFactory; // eax
  unsigned int v7; // ebx
  __int64 v8; // rcx
  int v10; // eax
  struct Windows::Data::Json::IJsonValue *v11; // rcx
  __int64 v12; // rcx
  struct Windows::Data::Json::IJsonValue *v13; // rbx
  __int64 v14; // rax
  int v15; // eax
  struct Windows::Data::Json::IJsonValue *v16; // rcx
  __int64 v17; // rcx
  struct Windows::Data::Json::IJsonValue *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // [rsp+20h] [rbp-40h] BYREF
  struct Windows::Data::Json::IJsonValue *v21; // [rsp+28h] [rbp-38h] BYREF
  const unsigned __int16 *v22; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v22 = a2;
  v20 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18001EC3FLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v20);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v20);
    v8 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v21 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v20 + 72LL))(
          v20,
          v20,
          &v21);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v10,
      v20);
    v11 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v11 + 16LL))(v11);
    }
    v12 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    return v7;
  }
  v13 = v21;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v22);
  v15 = Microsoft::Windows::Autopilot::JsonHelpers::Append(a1, *(HSTRING *)(v14 + 24), v13);
  v7 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v15,
      v20);
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    v17 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v7;
  }
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v18 + 16LL))(v18);
  }
  v19 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18001ea04  mov     [rsp-18h+arg_18], rbx
0x18001ea09  push    rbp
0x18001ea0a  push    rsi
0x18001ea0b  push    rdi
0x18001ea0c  mov     rbp, rsp
0x18001ea0f  sub     rsp, 60h
0x18001ea13  mov     rax, cs:__security_cookie
0x18001ea1a  xor     rax, rsp
0x18001ea1d  mov     [rbp+var_8], rax
0x18001ea21  mov     esi, r8d
0x18001ea24  mov     rdi, rcx
0x18001ea27  mov     [rbp+var_30], rdx
0x18001ea2b  mov     [rbp+var_40], 0
0x18001ea33  mov     [rbp+string], 0
0x18001ea3b  lea     r9, [rbp+string]; string
0x18001ea3f  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001ea43  mov     edx, 1Bh; length
0x18001ea48  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001ea4f  call    cs:__imp_WindowsCreateStringReference
0x18001ea55  test    eax, eax
0x18001ea57  js      loc_18001EC38
0x18001ea5d  mov     rbx, [rbp+string]
0x18001ea61  mov     rcx, [rbp+var_40]
0x18001ea65  test    rcx, rcx
0x18001ea68  jz      short loc_18001EA7F
0x18001ea6a  mov     [rbp+var_40], 0
0x18001ea72  mov     rax, [rcx]
0x18001ea75  mov     rax, [rax+10h]
0x18001ea79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea7e  nop
0x18001ea7f  lea     r8, [rbp+var_40]
0x18001ea83  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001ea8a  mov     rcx, rbx
0x18001ea8d  call    cs:__imp_RoGetActivationFactory
0x18001ea93  mov     ebx, eax
0x18001ea95  test    eax, eax
0x18001ea97  jns     short loc_18001EAD7
0x18001ea99  mov     rcx, [rbp+18h]; this
0x18001ea9d  mov     r9d, eax; char *
0x18001eaa0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001eaa7  mov     edx, 37h ; '7'; void *
0x18001eaac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eab1  nop
0x18001eab2  mov     rcx, [rbp+var_40]
0x18001eab6  test    rcx, rcx
0x18001eab9  jz      short loc_18001EAD0
0x18001eabb  mov     [rbp+var_40], 0
0x18001eac3  mov     rax, [rcx]
0x18001eac6  mov     rax, [rax+10h]
0x18001eaca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eacf  nop
0x18001ead0  mov     eax, ebx
0x18001ead2  jmp     loc_18001EC1C
0x18001ead7  mov     [rbp+var_38], 0
0x18001eadf  mov     rdx, [rbp+var_40]
0x18001eae3  mov     rax, [rdx]
0x18001eae6  xorps   xmm1, xmm1
0x18001eae9  cvtsi2sd xmm1, rsi
0x18001eaee  lea     r8, [rbp+var_38]
0x18001eaf2  mov     rcx, rdx
0x18001eaf5  mov     rax, [rax+48h]
0x18001eaf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eafe  mov     ebx, eax
0x18001eb00  test    eax, eax
0x18001eb02  jns     short loc_18001EB5E
0x18001eb04  mov     rcx, [rbp+18h]; this
0x18001eb08  mov     r9d, eax; char *
0x18001eb0b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001eb12  mov     edx, 3Ah ; ':'; void *
0x18001eb17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb1c  nop
0x18001eb1d  mov     rcx, [rbp+var_38]
0x18001eb21  test    rcx, rcx
0x18001eb24  jz      short loc_18001EB3B
0x18001eb26  mov     [rbp+var_38], 0
0x18001eb2e  mov     rax, [rcx]
0x18001eb31  mov     rax, [rax+10h]
0x18001eb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb3a  nop
0x18001eb3b  mov     rcx, [rbp+var_40]
0x18001eb3f  test    rcx, rcx
0x18001eb42  jz      short loc_18001EB59
0x18001eb44  mov     [rbp+var_40], 0
0x18001eb4c  mov     rax, [rcx]
0x18001eb4f  mov     rax, [rax+10h]
0x18001eb53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb58  nop
0x18001eb59  jmp     loc_18001EAD0
0x18001eb5e  mov     rbx, [rbp+var_38]
0x18001eb62  lea     rdx, [rbp+var_30]
0x18001eb66  lea     rcx, [rbp+hstringHeader]
0x18001eb6a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001eb6f  mov     r8, rbx; struct Windows::Data::Json::IJsonValue *
0x18001eb72  mov     rdx, [rax+18h]; HSTRING
0x18001eb76  mov     rcx, rdi; struct Windows::Data::Json::IJsonObject *
0x18001eb79  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)
0x18001eb7e  mov     ebx, eax
0x18001eb80  test    eax, eax
0x18001eb82  jns     short loc_18001EBDE
0x18001eb84  mov     rcx, [rbp+18h]; this
0x18001eb88  mov     r9d, eax; char *
0x18001eb8b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001eb92  mov     edx, 3Ch ; '<'; void *
0x18001eb97  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eb9c  nop
0x18001eb9d  mov     rcx, [rbp+var_38]
0x18001eba1  test    rcx, rcx
0x18001eba4  jz      short loc_18001EBBB
0x18001eba6  mov     [rbp+var_38], 0
0x18001ebae  mov     rax, [rcx]
0x18001ebb1  mov     rax, [rax+10h]
0x18001ebb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebba  nop
0x18001ebbb  mov     rcx, [rbp+var_40]
0x18001ebbf  test    rcx, rcx
0x18001ebc2  jz      short loc_18001EBD9
0x18001ebc4  mov     [rbp+var_40], 0
0x18001ebcc  mov     rax, [rcx]
0x18001ebcf  mov     rax, [rax+10h]
0x18001ebd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebd8  nop
0x18001ebd9  jmp     loc_18001EAD0
0x18001ebde  mov     rcx, [rbp+var_38]
0x18001ebe2  test    rcx, rcx
0x18001ebe5  jz      short loc_18001EBFC
0x18001ebe7  mov     [rbp+var_38], 0
0x18001ebef  mov     rax, [rcx]
0x18001ebf2  mov     rax, [rax+10h]
0x18001ebf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebfb  nop
0x18001ebfc  mov     rcx, [rbp+var_40]
0x18001ec00  test    rcx, rcx
0x18001ec03  jz      short loc_18001EC1A
0x18001ec05  mov     [rbp+var_40], 0
0x18001ec0d  mov     rax, [rcx]
0x18001ec10  mov     rax, [rax+10h]
0x18001ec14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec19  nop
0x18001ec1a  xor     eax, eax
0x18001ec1c  mov     rcx, [rbp+var_8]
0x18001ec20  xor     rcx, rsp; StackCookie
0x18001ec23  call    __security_check_cookie
0x18001ec28  mov     rbx, [rsp+60h+arg_18]
0x18001ec30  add     rsp, 60h
0x18001ec34  pop     rdi
0x18001ec35  pop     rsi
0x18001ec36  pop     rbp
0x18001ec37  retn
0x18001ec38  mov     ecx, eax; this
0x18001ec3a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
