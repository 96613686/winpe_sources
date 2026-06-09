# Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,ushort const *,ushort const *)

- ea: `0x18001f030`
- end: `0x18001f286`
- name: `?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEBG1@Z`
- size: `598`
- prototype: `__int64 __fastcall(struct Windows::Data::Json::IJsonObject *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a510`
- `0x18001a8b4`
- `0x18001ab2c`
- `0x18001b220`
- `0x18001b430`
- `0x180025958`
- `0x180027b00`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x1800185f8`
- `0x18001eed4`
- `0x18001f030`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f07c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f07c`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f0c0`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f0c0`

## string_xrefs

- `0x18001f075`: `Windows.Data.Json.JsonValue`
- `0x18001f0d9`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f150`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f1d0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::Append(
        struct Windows::Data::Json::IJsonObject *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, PVOID, struct Windows::Data::Json::IJsonValue **); // rbx
  HSTRING_HEADER *v14; // rax
  int v15; // eax
  unsigned int v16; // r8d
  struct Windows::Data::Json::IJsonValue *v17; // rcx
  __int64 v18; // rcx
  struct Windows::Data::Json::IJsonValue *v19; // rbx
  HSTRING_HEADER *v20; // rax
  int v21; // eax
  struct Windows::Data::Json::IJsonValue *v22; // rcx
  __int64 v23; // rcx
  struct Windows::Data::Json::IJsonValue *v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // [rsp+20h] [rbp-50h] BYREF
  struct Windows::Data::Json::IJsonValue *v27; // [rsp+28h] [rbp-48h] BYREF
  const WCHAR *v28; // [rsp+30h] [rbp-40h] BYREF
  const WCHAR *v29; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v29 = a2;
  v28 = a3;
  v26 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonValue", 0x1Bu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18001F285LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c, &v26);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v26);
    v10 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v9;
  }
  v27 = 0;
  v12 = v26;
  v13 = *(__int64 (__fastcall **)(__int64, PVOID, struct Windows::Data::Json::IJsonValue **))(*(_QWORD *)v26 + 80LL);
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v28, v8);
  v15 = v13(v12, v14[1].Reserved.Reserved1, &v27);
  v9 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v15,
      v26);
    v17 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v17 + 16LL))(v17);
    }
    v18 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v9;
  }
  v19 = v27;
  v20 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v29, v16);
  v21 = Microsoft::Windows::Autopilot::JsonHelpers::Append(a1, (HSTRING)v20[1].Reserved.Reserved1, v19);
  v9 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2F,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v21,
      v26);
    v22 = v27;
    if ( v27 )
    {
      v27 = 0;
      (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    v23 = v26;
    if ( v26 )
    {
      v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    return v9;
  }
  v24 = v27;
  if ( v27 )
  {
    v27 = 0;
    (*(void (__fastcall **)(struct Windows::Data::Json::IJsonValue *))(*(_QWORD *)v24 + 16LL))(v24);
  }
  v25 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f030  mov     [rsp-18h+arg_18], rbx
0x18001f035  push    rbp
0x18001f036  push    rsi
0x18001f037  push    rdi
0x18001f038  mov     rbp, rsp
0x18001f03b  sub     rsp, 70h
0x18001f03f  mov     rax, cs:__security_cookie
0x18001f046  xor     rax, rsp
0x18001f049  mov     [rbp+var_10], rax
0x18001f04d  mov     rsi, rcx
0x18001f050  mov     [rbp+var_38], rdx
0x18001f054  mov     [rbp+var_40], r8
0x18001f058  mov     [rbp+var_50], 0
0x18001f060  mov     [rbp+string], 0
0x18001f068  lea     r9, [rbp+string]; string
0x18001f06c  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001f070  mov     edx, 1Bh; length
0x18001f075  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonValue@@3QBGB; "Windows.Data.Json.JsonValue"
0x18001f07c  call    cs:__imp_WindowsCreateStringReference
0x18001f083  nop     dword ptr [rax+rax+00h]
0x18001f088  test    eax, eax
0x18001f08a  js      loc_18001F27E
0x18001f090  mov     rbx, [rbp+string]
0x18001f094  mov     rcx, [rbp+var_50]
0x18001f098  test    rcx, rcx
0x18001f09b  jz      short loc_18001F0B2
0x18001f09d  mov     [rbp+var_50], 0
0x18001f0a5  mov     rax, [rcx]
0x18001f0a8  mov     rax, [rax+10h]
0x18001f0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b1  nop
0x18001f0b2  lea     r8, [rbp+var_50]
0x18001f0b6  lea     rdx, _GUID_5f6b544a_2f53_48e1_91a3_f78b50a6345c
0x18001f0bd  mov     rcx, rbx
0x18001f0c0  call    cs:__imp_RoGetActivationFactory
0x18001f0c7  nop     dword ptr [rax+rax+00h]
0x18001f0cc  mov     ebx, eax
0x18001f0ce  test    eax, eax
0x18001f0d0  jns     short loc_18001F110
0x18001f0d2  mov     rcx, [rbp+18h]; this
0x18001f0d6  mov     r9d, eax; char *
0x18001f0d9  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f0e0  mov     edx, 2Ah ; '*'; void *
0x18001f0e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f0ea  nop
0x18001f0eb  mov     rcx, [rbp+var_50]
0x18001f0ef  test    rcx, rcx
0x18001f0f2  jz      short loc_18001F109
0x18001f0f4  mov     [rbp+var_50], 0
0x18001f0fc  mov     rax, [rcx]
0x18001f0ff  mov     rax, [rax+10h]
0x18001f103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f108  nop
0x18001f109  mov     eax, ebx
0x18001f10b  jmp     loc_18001F261
0x18001f110  mov     [rbp+var_48], 0
0x18001f118  mov     rdi, [rbp+var_50]
0x18001f11c  mov     rax, [rdi]
0x18001f11f  mov     rbx, [rax+50h]
0x18001f123  lea     rdx, [rbp+var_40]
0x18001f127  lea     rcx, [rbp+hstringHeader]
0x18001f12b  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f130  lea     r8, [rbp+var_48]
0x18001f134  mov     rdx, [rax+18h]
0x18001f138  mov     rcx, rdi
0x18001f13b  mov     rax, rbx
0x18001f13e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f143  mov     ebx, eax
0x18001f145  test    eax, eax
0x18001f147  jns     short loc_18001F1A3
0x18001f149  mov     rcx, [rbp+18h]; this
0x18001f14d  mov     r9d, eax; char *
0x18001f150  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f157  mov     edx, 2Dh ; '-'; void *
0x18001f15c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f161  nop
0x18001f162  mov     rcx, [rbp+var_48]
0x18001f166  test    rcx, rcx
0x18001f169  jz      short loc_18001F180
0x18001f16b  mov     [rbp+var_48], 0
0x18001f173  mov     rax, [rcx]
0x18001f176  mov     rax, [rax+10h]
0x18001f17a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f17f  nop
0x18001f180  mov     rcx, [rbp+var_50]
0x18001f184  test    rcx, rcx
0x18001f187  jz      short loc_18001F19E
0x18001f189  mov     [rbp+var_50], 0
0x18001f191  mov     rax, [rcx]
0x18001f194  mov     rax, [rax+10h]
0x18001f198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f19d  nop
0x18001f19e  jmp     loc_18001F109
0x18001f1a3  mov     rbx, [rbp+var_48]
0x18001f1a7  lea     rdx, [rbp+var_38]
0x18001f1ab  lea     rcx, [rbp+hstringHeader]
0x18001f1af  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f1b4  mov     r8, rbx; struct Windows::Data::Json::IJsonValue *
0x18001f1b7  mov     rdx, [rax+18h]; HSTRING
0x18001f1bb  mov     rcx, rsi; struct Windows::Data::Json::IJsonObject *
0x18001f1be  call    ?Append@JsonHelpers@Autopilot@Windows@Microsoft@@SAJPEAUIJsonObject@Json@Data@3@PEAUHSTRING__@@PEAUIJsonValue@673@@Z; Microsoft::Windows::Autopilot::JsonHelpers::Append(Windows::Data::Json::IJsonObject *,HSTRING__ *,Windows::Data::Json::IJsonValue *)
0x18001f1c3  mov     ebx, eax
0x18001f1c5  test    eax, eax
0x18001f1c7  jns     short loc_18001F223
0x18001f1c9  mov     rcx, [rbp+18h]; this
0x18001f1cd  mov     r9d, eax; char *
0x18001f1d0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f1d7  mov     edx, 2Fh ; '/'; void *
0x18001f1dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f1e1  nop
0x18001f1e2  mov     rcx, [rbp+var_48]
0x18001f1e6  test    rcx, rcx
0x18001f1e9  jz      short loc_18001F200
0x18001f1eb  mov     [rbp+var_48], 0
0x18001f1f3  mov     rax, [rcx]
0x18001f1f6  mov     rax, [rax+10h]
0x18001f1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1ff  nop
0x18001f200  mov     rcx, [rbp+var_50]
0x18001f204  test    rcx, rcx
0x18001f207  jz      short loc_18001F21E
0x18001f209  mov     [rbp+var_50], 0
0x18001f211  mov     rax, [rcx]
0x18001f214  mov     rax, [rax+10h]
0x18001f218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f21d  nop
0x18001f21e  jmp     loc_18001F109
0x18001f223  mov     rcx, [rbp+var_48]
0x18001f227  test    rcx, rcx
0x18001f22a  jz      short loc_18001F241
0x18001f22c  mov     [rbp+var_48], 0
0x18001f234  mov     rax, [rcx]
0x18001f237  mov     rax, [rax+10h]
0x18001f23b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f240  nop
0x18001f241  mov     rcx, [rbp+var_50]
0x18001f245  test    rcx, rcx
0x18001f248  jz      short loc_18001F25F
0x18001f24a  mov     [rbp+var_50], 0
0x18001f252  mov     rax, [rcx]
0x18001f255  mov     rax, [rax+10h]
0x18001f259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f25e  nop
0x18001f25f  xor     eax, eax
0x18001f261  mov     rcx, [rbp+var_10]
0x18001f265  xor     rcx, rsp; StackCookie
0x18001f268  call    __security_check_cookie
0x18001f26d  mov     rbx, [rsp+70h+arg_18]
0x18001f275  add     rsp, 70h
0x18001f279  pop     rdi
0x18001f27a  pop     rsi
0x18001f27b  pop     rbp
0x18001f27c  retn
0x18001f27e  mov     ecx, eax; this
0x18001f280  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
