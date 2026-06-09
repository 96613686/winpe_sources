# Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ulong)

- ea: `0x18001f28c`
- end: `0x18001f4d5`
- name: `?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBGK@Z`
- size: `585`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b430`
- `0x180027b00`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x1800185f8`
- `0x18001eed4`
- `0x18001f28c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f2d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f2d7`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f31b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f31b`

## string_xrefs

- `0x18001f2d0`: `Windows.Data.Json.JsonValue`
- `0x18001f334`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f39f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f41f`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
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
  unsigned int v11; // r8d
  struct Windows::Data::Json::IJsonValue *v12; // rcx
  __int64 v13; // rcx
  struct Windows::Data::Json::IJsonValue *v14; // rbx
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  struct Windows::Data::Json::IJsonValue *v17; // rcx
  __int64 v18; // rcx
  struct Windows::Data::Json::IJsonValue *v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-40h] BYREF
  struct Windows::Data::Json::IJsonValue *v22; // [rsp+28h] [rbp-38h] BYREF
  const WCHAR *v23; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v23 = a2;
  v21 = 0;
  string = 0;
  v3 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v3 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v3, v4, v5);
    JUMPOUT(0x18001F4D4LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v21);
  v7 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x37,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v21);
    v8 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    return v7;
  }
  v22 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v21 + 72LL))(
          v21,
          v21,
          &v22);
  v7 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v10,
      v21);
    v12 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v7;
  }
  v14 = v22;
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v23, v11);
  v16 = Microsoft::Windows::Autopilot::JsonHelpers::Append(a1, (HSTRING)v15[1].Reserved.Reserved1, v14);
  v7 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v16,
      v21);
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v7;
  }
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v19 + 16LL))(v19);
  }
  v20 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f28c  mov     [rsp-18h+arg_18], rbx
0x18001f291  push    rbp
0x18001f292  push    rsi
0x18001f293  push    rdi
0x18001f294  mov     rbp, rsp
0x18001f297  sub     rsp, 60h
0x18001f29b  mov     rax, cs:__security_cookie
0x18001f2a2  xor     rax, rsp
0x18001f2a5  mov     [rbp+var_8], rax
0x18001f2a9  mov     esi, r8d
0x18001f2ac  mov     rdi, rcx
0x18001f2af  mov     [rbp+var_30], rdx
0x18001f2b3  mov     [rbp+var_40], 0
0x18001f2bb  mov     [rbp+string], 0
0x18001f2c3  lea     r9, [rbp+string]; string
0x18001f2c7  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001f2cb  mov     edx, 1Bh; length
0x18001f2d0  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001f2d7  call    cs:__imp_WindowsCreateStringReference
0x18001f2de  nop     dword ptr [rax+rax+00h]
0x18001f2e3  test    eax, eax
0x18001f2e5  js      loc_18001F4CD
0x18001f2eb  mov     rbx, [rbp+string]
0x18001f2ef  mov     rcx, [rbp+var_40]
0x18001f2f3  test    rcx, rcx
0x18001f2f6  jz      short loc_18001F30D
0x18001f2f8  mov     [rbp+var_40], 0
0x18001f300  mov     rax, [rcx]
0x18001f303  mov     rax, [rax+10h]
0x18001f307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f30c  nop
0x18001f30d  lea     r8, [rbp+var_40]
0x18001f311  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001f318  mov     rcx, rbx
0x18001f31b  call    cs:__imp_RoGetActivationFactory
0x18001f322  nop     dword ptr [rax+rax+00h]
0x18001f327  mov     ebx, eax
0x18001f329  test    eax, eax
0x18001f32b  jns     short loc_18001F36B
0x18001f32d  mov     rcx, [rbp+18h]; this
0x18001f331  mov     r9d, eax; char *
0x18001f334  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f33b  mov     edx, 37h ; '7'; void *
0x18001f340  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f345  nop
0x18001f346  mov     rcx, [rbp+var_40]
0x18001f34a  test    rcx, rcx
0x18001f34d  jz      short loc_18001F364
0x18001f34f  mov     [rbp+var_40], 0
0x18001f357  mov     rax, [rcx]
0x18001f35a  mov     rax, [rax+10h]
0x18001f35e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f363  nop
0x18001f364  mov     eax, ebx
0x18001f366  jmp     loc_18001F4B0
0x18001f36b  mov     [rbp+var_38], 0
0x18001f373  mov     rdx, [rbp+var_40]
0x18001f377  mov     rax, [rdx]
0x18001f37a  xorps   xmm1, xmm1
0x18001f37d  cvtsi2sd xmm1, rsi
0x18001f382  lea     r8, [rbp+var_38]
0x18001f386  mov     rcx, rdx
0x18001f389  mov     rax, [rax+48h]
0x18001f38d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f392  mov     ebx, eax
0x18001f394  test    eax, eax
0x18001f396  jns     short loc_18001F3F2
0x18001f398  mov     rcx, [rbp+18h]; this
0x18001f39c  mov     r9d, eax; char *
0x18001f39f  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f3a6  mov     edx, 3Ah ; ':'; void *
0x18001f3ab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f3b0  nop
0x18001f3b1  mov     rcx, [rbp+var_38]
0x18001f3b5  test    rcx, rcx
0x18001f3b8  jz      short loc_18001F3CF
0x18001f3ba  mov     [rbp+var_38], 0
0x18001f3c2  mov     rax, [rcx]
0x18001f3c5  mov     rax, [rax+10h]
0x18001f3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3ce  nop
0x18001f3cf  mov     rcx, [rbp+var_40]
0x18001f3d3  test    rcx, rcx
0x18001f3d6  jz      short loc_18001F3ED
0x18001f3d8  mov     [rbp+var_40], 0
0x18001f3e0  mov     rax, [rcx]
0x18001f3e3  mov     rax, [rax+10h]
0x18001f3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3ec  nop
0x18001f3ed  jmp     loc_18001F364
0x18001f3f2  mov     rbx, [rbp+var_38]
0x18001f3f6  lea     rdx, [rbp+var_30]
0x18001f3fa  lea     rcx, [rbp+hstringHeader]
0x18001f3fe  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f403  mov     r8, rbx; struct Windows::Data::Json::IJsonValue *
0x18001f406  mov     rdx, [rax+18h]; HSTRING
0x18001f40a  mov     rcx, rdi; struct Windows::Data::Json::IJsonObject *
0x18001f40d  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)
0x18001f412  mov     ebx, eax
0x18001f414  test    eax, eax
0x18001f416  jns     short loc_18001F472
0x18001f418  mov     rcx, [rbp+18h]; this
0x18001f41c  mov     r9d, eax; char *
0x18001f41f  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f426  mov     edx, 3Ch ; '<'; void *
0x18001f42b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f430  nop
0x18001f431  mov     rcx, [rbp+var_38]
0x18001f435  test    rcx, rcx
0x18001f438  jz      short loc_18001F44F
0x18001f43a  mov     [rbp+var_38], 0
0x18001f442  mov     rax, [rcx]
0x18001f445  mov     rax, [rax+10h]
0x18001f449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f44e  nop
0x18001f44f  mov     rcx, [rbp+var_40]
0x18001f453  test    rcx, rcx
0x18001f456  jz      short loc_18001F46D
0x18001f458  mov     [rbp+var_40], 0
0x18001f460  mov     rax, [rcx]
0x18001f463  mov     rax, [rax+10h]
0x18001f467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f46c  nop
0x18001f46d  jmp     loc_18001F364
0x18001f472  mov     rcx, [rbp+var_38]
0x18001f476  test    rcx, rcx
0x18001f479  jz      short loc_18001F490
0x18001f47b  mov     [rbp+var_38], 0
0x18001f483  mov     rax, [rcx]
0x18001f486  mov     rax, [rax+10h]
0x18001f48a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f48f  nop
0x18001f490  mov     rcx, [rbp+var_40]
0x18001f494  test    rcx, rcx
0x18001f497  jz      short loc_18001F4AE
0x18001f499  mov     [rbp+var_40], 0
0x18001f4a1  mov     rax, [rcx]
0x18001f4a4  mov     rax, [rax+10h]
0x18001f4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4ad  nop
0x18001f4ae  xor     eax, eax
0x18001f4b0  mov     rcx, [rbp+var_8]
0x18001f4b4  xor     rcx, rsp; StackCookie
0x18001f4b7  call    __security_check_cookie
0x18001f4bc  mov     rbx, [rsp+60h+arg_18]
0x18001f4c4  add     rsp, 60h
0x18001f4c8  pop     rdi
0x18001f4c9  pop     rsi
0x18001f4ca  pop     rbp
0x18001f4cb  retn
0x18001f4cd  mov     ecx, eax; this
0x18001f4cf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
