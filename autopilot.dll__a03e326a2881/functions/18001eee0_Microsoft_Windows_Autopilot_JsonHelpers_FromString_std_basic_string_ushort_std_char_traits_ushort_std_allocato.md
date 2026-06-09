# Microsoft::Windows::Autopilot::JsonHelpers::FromString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001eee0`
- end: `0x18001f0e3`
- name: `?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `515`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001bcf8`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800180a8`
- `0x18001eee0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ef2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001ef2d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ef6b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001ef6b`

## string_xrefs

- `0x18001ef26`: `Windows.Data.Json.JsonObject`
- `0x18001ef7e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f01e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f065`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

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
  __int64 (__fastcall *v12)(__int64, _QWORD, __int64 *, _BYTE *); // r14
  __int64 v13; // rcx
  __int64 v14; // rax
  int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rcx
  int v19; // [rsp+20h] [rbp-50h]
  _BYTE v20[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v21; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v22; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v21 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18001F0E2LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v21);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v19);
    v9 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    }
    return v8;
  }
  v20[0] = 0;
  v11 = v21;
  v12 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _BYTE *))(*(_QWORD *)v21 + 56LL);
  v13 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  if ( a1[3] > 7u )
    a1 = (_QWORD *)*a1;
  v22 = a1;
  v14 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v22);
  v15 = v12(v11, *(_QWORD *)(v14 + 24), a2, v20);
  v8 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v15,
      v19);
    v16 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v8;
  }
  if ( !v20[0] )
  {
    v8 = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x8007000DLL,
      v19);
    v17 = v21;
    if ( v21 )
    {
      v21 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v8;
  }
  v18 = v21;
  if ( v21 )
  {
    v21 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return 0;
}

```

## disassembly

```asm
0x18001eee0  mov     [rsp-18h+arg_10], rbx
0x18001eee5  mov     [rsp-18h+arg_18], rsi
0x18001eeea  push    rbp
0x18001eeeb  push    rdi
0x18001eeec  push    r14
0x18001eeee  mov     rbp, rsp
0x18001eef1  sub     rsp, 70h
0x18001eef5  mov     rax, cs:__security_cookie
0x18001eefc  xor     rax, rsp
0x18001eeff  mov     [rbp+var_8], rax
0x18001ef03  mov     rsi, rdx
0x18001ef06  mov     rdi, rcx
0x18001ef09  mov     [rbp+var_38], 0
0x18001ef11  mov     [rbp+string], 0
0x18001ef19  lea     r9, [rbp+string]; string
0x18001ef1d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001ef21  mov     edx, 1Ch; length
0x18001ef26  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001ef2d  call    cs:__imp_WindowsCreateStringReference
0x18001ef33  test    eax, eax
0x18001ef35  js      loc_18001F0DB
0x18001ef3b  mov     rbx, [rbp+string]
0x18001ef3f  mov     rcx, [rbp+var_38]
0x18001ef43  test    rcx, rcx
0x18001ef46  jz      short loc_18001EF5D
0x18001ef48  mov     [rbp+var_38], 0
0x18001ef50  mov     rax, [rcx]
0x18001ef53  mov     rax, [rax+10h]
0x18001ef57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef5c  nop
0x18001ef5d  lea     r8, [rbp+var_38]
0x18001ef61  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001ef68  mov     rcx, rbx
0x18001ef6b  call    cs:__imp_RoGetActivationFactory
0x18001ef71  mov     ebx, eax
0x18001ef73  test    eax, eax
0x18001ef75  jns     short loc_18001EFB5
0x18001ef77  mov     rcx, [rbp+18h]; this
0x18001ef7b  mov     r9d, eax; char *
0x18001ef7e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001ef85  mov     edx, 9Bh; void *
0x18001ef8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ef8f  nop
0x18001ef90  mov     rcx, [rbp+var_38]
0x18001ef94  test    rcx, rcx
0x18001ef97  jz      short loc_18001EFAE
0x18001ef99  mov     [rbp+var_38], 0
0x18001efa1  mov     rax, [rcx]
0x18001efa4  mov     rax, [rax+10h]
0x18001efa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efad  nop
0x18001efae  mov     eax, ebx
0x18001efb0  jmp     loc_18001F0BA
0x18001efb5  mov     [rbp+var_40], 0
0x18001efb9  mov     rbx, [rbp+var_38]
0x18001efbd  mov     rax, [rbx]
0x18001efc0  mov     r14, [rax+38h]
0x18001efc4  mov     rcx, [rsi]
0x18001efc7  test    rcx, rcx
0x18001efca  jz      short loc_18001EFE0
0x18001efcc  mov     qword ptr [rsi], 0
0x18001efd3  mov     rax, [rcx]
0x18001efd6  mov     rax, [rax+10h]
0x18001efda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efdf  nop
0x18001efe0  cmp     qword ptr [rdi+18h], 7
0x18001efe5  jbe     short loc_18001EFEA
0x18001efe7  mov     rdi, [rdi]
0x18001efea  mov     [rbp+var_30], rdi
0x18001efee  lea     rdx, [rbp+var_30]
0x18001eff2  lea     rcx, [rbp+hstringHeader]
0x18001eff6  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001effb  lea     r9, [rbp+var_40]
0x18001efff  mov     r8, rsi
0x18001f002  mov     rdx, [rax+18h]
0x18001f006  mov     rcx, rbx
0x18001f009  mov     rax, r14
0x18001f00c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f011  mov     ebx, eax
0x18001f013  test    eax, eax
0x18001f015  jns     short loc_18001F053
0x18001f017  mov     rcx, [rbp+18h]; this
0x18001f01b  mov     r9d, eax; char *
0x18001f01e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f025  mov     edx, 0A1h; void *
0x18001f02a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f02f  nop
0x18001f030  mov     rcx, [rbp+var_38]
0x18001f034  test    rcx, rcx
0x18001f037  jz      short loc_18001F04E
0x18001f039  mov     [rbp+var_38], 0
0x18001f041  mov     rax, [rcx]
0x18001f044  mov     rax, [rax+10h]
0x18001f048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f04d  nop
0x18001f04e  jmp     loc_18001EFAE
0x18001f053  cmp     [rbp+var_40], 0
0x18001f057  jnz     short loc_18001F09A
0x18001f059  mov     rcx, [rbp+18h]; this
0x18001f05d  mov     ebx, 8007000Dh
0x18001f062  mov     r9d, ebx; char *
0x18001f065  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f06c  mov     edx, 0A3h; void *
0x18001f071  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f076  nop
0x18001f077  mov     rcx, [rbp+var_38]
0x18001f07b  test    rcx, rcx
0x18001f07e  jz      short loc_18001F095
0x18001f080  mov     [rbp+var_38], 0
0x18001f088  mov     rdx, [rcx]
0x18001f08b  mov     rax, [rdx+10h]
0x18001f08f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f094  nop
0x18001f095  jmp     loc_18001EFAE
0x18001f09a  mov     rcx, [rbp+var_38]
0x18001f09e  test    rcx, rcx
0x18001f0a1  jz      short loc_18001F0B8
0x18001f0a3  mov     [rbp+var_38], 0
0x18001f0ab  mov     rax, [rcx]
0x18001f0ae  mov     rax, [rax+10h]
0x18001f0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0b7  nop
0x18001f0b8  xor     eax, eax
0x18001f0ba  mov     rcx, [rbp+var_8]
0x18001f0be  xor     rcx, rsp; StackCookie
0x18001f0c1  call    __security_check_cookie
0x18001f0c6  lea     r11, [rsp+70h+var_s0]
0x18001f0cb  mov     rbx, [r11+30h]
0x18001f0cf  mov     rsi, [r11+38h]
0x18001f0d3  mov     rsp, r11
0x18001f0d6  pop     r14
0x18001f0d8  pop     rdi
0x18001f0d9  pop     rbp
0x18001f0da  retn
0x18001f0db  mov     ecx, eax; this
0x18001f0dd  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
