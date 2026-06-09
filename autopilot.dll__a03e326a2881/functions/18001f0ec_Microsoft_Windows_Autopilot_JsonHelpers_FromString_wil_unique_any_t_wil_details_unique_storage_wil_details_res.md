# Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001f0ec`
- end: `0x18001f2d3`
- name: `?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `487`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800185c0`
- `0x1800227dc`
- `0x180023cb0`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x18001f0ec`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f139`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f139`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f177`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f177`

## string_xrefs

- `0x18001f132`: `Windows.Data.Json.JsonObject`
- `0x18001f18a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f20e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f255`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    JUMPOUT(0x18001F2D2LL);
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
0x18001f0ec  mov     [rsp-18h+arg_10], rbx
0x18001f0f1  mov     [rsp-18h+arg_18], rsi
0x18001f0f6  push    rbp
0x18001f0f7  push    rdi
0x18001f0f8  push    r14
0x18001f0fa  mov     rbp, rsp
0x18001f0fd  sub     rsp, 70h
0x18001f101  mov     rax, cs:__security_cookie
0x18001f108  xor     rax, rsp
0x18001f10b  mov     [rbp+var_10], rax
0x18001f10f  mov     rdi, rdx
0x18001f112  mov     r14, rcx
0x18001f115  mov     [rbp+var_38], 0
0x18001f11d  mov     [rbp+string], 0
0x18001f125  lea     r9, [rbp+string]; string
0x18001f129  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001f12d  mov     edx, 1Ch; length
0x18001f132  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001f139  call    cs:__imp_WindowsCreateStringReference
0x18001f13f  test    eax, eax
0x18001f141  js      loc_18001F2CB
0x18001f147  mov     rbx, [rbp+string]
0x18001f14b  mov     rcx, [rbp+var_38]
0x18001f14f  test    rcx, rcx
0x18001f152  jz      short loc_18001F169
0x18001f154  mov     [rbp+var_38], 0
0x18001f15c  mov     rax, [rcx]
0x18001f15f  mov     rax, [rax+10h]
0x18001f163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f168  nop
0x18001f169  lea     r8, [rbp+var_38]
0x18001f16d  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001f174  mov     rcx, rbx
0x18001f177  call    cs:__imp_RoGetActivationFactory
0x18001f17d  mov     ebx, eax
0x18001f17f  test    eax, eax
0x18001f181  jns     short loc_18001F1C1
0x18001f183  mov     rcx, [rbp+18h]; this
0x18001f187  mov     r9d, eax; char *
0x18001f18a  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f191  mov     edx, 8Bh; void *
0x18001f196  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f19b  nop
0x18001f19c  mov     rcx, [rbp+var_38]
0x18001f1a0  test    rcx, rcx
0x18001f1a3  jz      short loc_18001F1BA
0x18001f1a5  mov     [rbp+var_38], 0
0x18001f1ad  mov     rax, [rcx]
0x18001f1b0  mov     rax, [rax+10h]
0x18001f1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1b9  nop
0x18001f1ba  mov     eax, ebx
0x18001f1bc  jmp     loc_18001F2AA
0x18001f1c1  mov     [rbp+var_40], 0
0x18001f1c5  mov     rbx, [rbp+var_38]
0x18001f1c9  mov     rax, [rbx]
0x18001f1cc  mov     rsi, [rax+38h]
0x18001f1d0  mov     rcx, [rdi]
0x18001f1d3  test    rcx, rcx
0x18001f1d6  jz      short loc_18001F1EC
0x18001f1d8  mov     qword ptr [rdi], 0
0x18001f1df  mov     r9, [rcx]
0x18001f1e2  mov     rax, [r9+10h]
0x18001f1e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1eb  nop
0x18001f1ec  lea     r9, [rbp+var_40]
0x18001f1f0  mov     r8, rdi
0x18001f1f3  mov     rdx, [r14]
0x18001f1f6  mov     rcx, rbx
0x18001f1f9  mov     rax, rsi
0x18001f1fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f201  mov     ebx, eax
0x18001f203  test    eax, eax
0x18001f205  jns     short loc_18001F243
0x18001f207  mov     rcx, [rbp+18h]; this
0x18001f20b  mov     r9d, eax; char *
0x18001f20e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f215  mov     edx, 91h; void *
0x18001f21a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f21f  nop
0x18001f220  mov     rcx, [rbp+var_38]
0x18001f224  test    rcx, rcx
0x18001f227  jz      short loc_18001F23E
0x18001f229  mov     [rbp+var_38], 0
0x18001f231  mov     rax, [rcx]
0x18001f234  mov     rax, [rax+10h]
0x18001f238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f23d  nop
0x18001f23e  jmp     loc_18001F1BA
0x18001f243  cmp     [rbp+var_40], 0
0x18001f247  jnz     short loc_18001F28A
0x18001f249  mov     rcx, [rbp+18h]; this
0x18001f24d  mov     ebx, 8007000Dh
0x18001f252  mov     r9d, ebx; char *
0x18001f255  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f25c  mov     edx, 93h; void *
0x18001f261  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f266  nop
0x18001f267  mov     rcx, [rbp+var_38]
0x18001f26b  test    rcx, rcx
0x18001f26e  jz      short loc_18001F285
0x18001f270  mov     [rbp+var_38], 0
0x18001f278  mov     rdx, [rcx]
0x18001f27b  mov     rax, [rdx+10h]
0x18001f27f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f284  nop
0x18001f285  jmp     loc_18001F1BA
0x18001f28a  mov     rcx, [rbp+var_38]
0x18001f28e  test    rcx, rcx
0x18001f291  jz      short loc_18001F2A8
0x18001f293  mov     [rbp+var_38], 0
0x18001f29b  mov     rax, [rcx]
0x18001f29e  mov     rax, [rax+10h]
0x18001f2a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2a7  nop
0x18001f2a8  xor     eax, eax
0x18001f2aa  mov     rcx, [rbp+var_10]
0x18001f2ae  xor     rcx, rsp; StackCookie
0x18001f2b1  call    __security_check_cookie
0x18001f2b6  lea     r11, [rsp+70h+var_s0]
0x18001f2bb  mov     rbx, [r11+30h]
0x18001f2bf  mov     rsi, [r11+38h]
0x18001f2c3  mov     rsp, r11
0x18001f2c6  pop     r14
0x18001f2c8  pop     rdi
0x18001f2c9  pop     rbp
0x18001f2ca  retn
0x18001f2cb  mov     ecx, eax; this
0x18001f2cd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
