# Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001f98c`
- end: `0x18001fb80`
- name: `?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `500`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018b38`
- `0x1800232dc`
- `0x180024878`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x18001f98c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f9d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f9d9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fa1d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001fa1d`

## string_xrefs

- `0x18001f9d2`: `Windows.Data.Json.JsonObject`
- `0x18001fa36`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001faba`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001fb01`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::FromString(_QWORD *a1, __int64 *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v9; // rcx
  __int64 v11; // rbx
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *, _BYTE *); // rsi
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-50h]
  _BYTE v19[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v20; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  HSTRING string; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v20 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18001FB7FLL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v20);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v18);
    v9 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v19[0] = 0;
  v11 = v20;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v20 + 56LL);
  v13 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  v14 = v12(v11, *a1, a2, v19);
  v8 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v14,
      v18);
    v15 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    }
    return v8;
  }
  if ( !v19[0] )
  {
    v8 = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x93,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x8007000DLL,
      v18);
    v16 = v20;
    if ( v20 )
    {
      v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  v17 = v20;
  if ( v20 )
  {
    v20 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f98c  mov     [rsp-18h+arg_10], rbx
0x18001f991  mov     [rsp-18h+arg_18], rsi
0x18001f996  push    rbp
0x18001f997  push    rdi
0x18001f998  push    r14
0x18001f99a  mov     rbp, rsp
0x18001f99d  sub     rsp, 70h
0x18001f9a1  mov     rax, cs:__security_cookie
0x18001f9a8  xor     rax, rsp
0x18001f9ab  mov     [rbp+var_10], rax
0x18001f9af  mov     rdi, rdx
0x18001f9b2  mov     r14, rcx
0x18001f9b5  mov     [rbp+var_38], 0
0x18001f9bd  mov     [rbp+string], 0
0x18001f9c5  lea     r9, [rbp+string]; string
0x18001f9c9  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001f9cd  mov     edx, 1Ch; length
0x18001f9d2  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001f9d9  call    cs:__imp_WindowsCreateStringReference
0x18001f9e0  nop     dword ptr [rax+rax+00h]
0x18001f9e5  test    eax, eax
0x18001f9e7  js      loc_18001FB78
0x18001f9ed  mov     rbx, [rbp+string]
0x18001f9f1  mov     rcx, [rbp+var_38]
0x18001f9f5  test    rcx, rcx
0x18001f9f8  jz      short loc_18001FA0F
0x18001f9fa  mov     [rbp+var_38], 0
0x18001fa02  mov     rax, [rcx]
0x18001fa05  mov     rax, [rax+10h]
0x18001fa09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa0e  nop
0x18001fa0f  lea     r8, [rbp+var_38]
0x18001fa13  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001fa1a  mov     rcx, rbx
0x18001fa1d  call    cs:__imp_RoGetActivationFactory
0x18001fa24  nop     dword ptr [rax+rax+00h]
0x18001fa29  mov     ebx, eax
0x18001fa2b  test    eax, eax
0x18001fa2d  jns     short loc_18001FA6D
0x18001fa2f  mov     rcx, [rbp+18h]; this
0x18001fa33  mov     r9d, eax; char *
0x18001fa36  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fa3d  mov     edx, 8Bh; void *
0x18001fa42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fa47  nop
0x18001fa48  mov     rcx, [rbp+var_38]
0x18001fa4c  test    rcx, rcx
0x18001fa4f  jz      short loc_18001FA66
0x18001fa51  mov     [rbp+var_38], 0
0x18001fa59  mov     rax, [rcx]
0x18001fa5c  mov     rax, [rax+10h]
0x18001fa60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa65  nop
0x18001fa66  mov     eax, ebx
0x18001fa68  jmp     loc_18001FB56
0x18001fa6d  mov     [rbp+var_40], 0
0x18001fa71  mov     rbx, [rbp+var_38]
0x18001fa75  mov     rax, [rbx]
0x18001fa78  mov     rsi, [rax+38h]
0x18001fa7c  mov     rcx, [rdi]
0x18001fa7f  test    rcx, rcx
0x18001fa82  jz      short loc_18001FA98
0x18001fa84  mov     qword ptr [rdi], 0
0x18001fa8b  mov     r9, [rcx]
0x18001fa8e  mov     rax, [r9+10h]
0x18001fa92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa97  nop
0x18001fa98  lea     r9, [rbp+var_40]
0x18001fa9c  mov     r8, rdi
0x18001fa9f  mov     rdx, [r14]
0x18001faa2  mov     rcx, rbx
0x18001faa5  mov     rax, rsi
0x18001faa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001faad  mov     ebx, eax
0x18001faaf  test    eax, eax
0x18001fab1  jns     short loc_18001FAEF
0x18001fab3  mov     rcx, [rbp+18h]; this
0x18001fab7  mov     r9d, eax; char *
0x18001faba  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fac1  mov     edx, 91h; void *
0x18001fac6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001facb  nop
0x18001facc  mov     rcx, [rbp+var_38]
0x18001fad0  test    rcx, rcx
0x18001fad3  jz      short loc_18001FAEA
0x18001fad5  mov     [rbp+var_38], 0
0x18001fadd  mov     rax, [rcx]
0x18001fae0  mov     rax, [rax+10h]
0x18001fae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fae9  nop
0x18001faea  jmp     loc_18001FA66
0x18001faef  cmp     [rbp+var_40], 0
0x18001faf3  jnz     short loc_18001FB36
0x18001faf5  mov     rcx, [rbp+18h]; this
0x18001faf9  mov     ebx, 8007000Dh
0x18001fafe  mov     r9d, ebx; char *
0x18001fb01  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001fb08  mov     edx, 93h; void *
0x18001fb0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb12  nop
0x18001fb13  mov     rcx, [rbp+var_38]
0x18001fb17  test    rcx, rcx
0x18001fb1a  jz      short loc_18001FB31
0x18001fb1c  mov     [rbp+var_38], 0
0x18001fb24  mov     rdx, [rcx]
0x18001fb27  mov     rax, [rdx+10h]
0x18001fb2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb30  nop
0x18001fb31  jmp     loc_18001FA66
0x18001fb36  mov     rcx, [rbp+var_38]
0x18001fb3a  test    rcx, rcx
0x18001fb3d  jz      short loc_18001FB54
0x18001fb3f  mov     [rbp+var_38], 0
0x18001fb47  mov     rax, [rcx]
0x18001fb4a  mov     rax, [rax+10h]
0x18001fb4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fb53  nop
0x18001fb54  xor     eax, eax
0x18001fb56  mov     rcx, [rbp+var_10]
0x18001fb5a  xor     rcx, rsp; StackCookie
0x18001fb5d  call    __security_check_cookie
0x18001fb62  lea     r11, [rsp+70h+var_s0]
0x18001fb67  mov     rbx, [r11+30h]
0x18001fb6b  mov     rsi, [r11+38h]
0x18001fb6f  mov     rsp, r11
0x18001fb72  pop     r14
0x18001fb74  pop     rdi
0x18001fb75  pop     rbp
0x18001fb76  retn
0x18001fb78  mov     ecx, eax; this
0x18001fb7a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
