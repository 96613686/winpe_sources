# Microsoft::Windows::Autopilot::JsonHelpers::FromString(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x18001f774`
- end: `0x18001f984`
- name: `?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z`
- size: `528`
- prototype: `__int64 __fastcall(const WCHAR *, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c448`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x1800185f8`
- `0x18001f774`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f7c1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18001f7c1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f805`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18001f805`

## string_xrefs

- `0x18001f7ba`: `Windows.Data.Json.JsonObject`
- `0x18001f81e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f8be`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`
- `0x18001f905`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\jsonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::JsonHelpers::FromString(const WCHAR *a1, __int64 *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // r8d
  unsigned int v9; // ebx
  __int64 v10; // rcx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, PVOID, __int64 *, _BYTE *); // r14
  __int64 v14; // rcx
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  int v20; // [rsp+20h] [rbp-50h]
  _BYTE v21[8]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v22; // [rsp+38h] [rbp-38h] BYREF
  const WCHAR *v23; // [rsp+40h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+48h] [rbp-28h] BYREF
  HSTRING string; // [rsp+60h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  v22 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x18001F983LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v22);
  v9 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9B,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v20);
    v10 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v9;
  }
  v21[0] = 0;
  v12 = v22;
  v13 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 *, _BYTE *))(*(_QWORD *)v22 + 56LL);
  v14 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(const WCHAR **)a1;
  v23 = a1;
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v23, v8);
  v16 = v13(v12, v15[1].Reserved.Reserved1, a2, v21);
  v9 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA1,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)(unsigned int)v16,
      v20);
    v17 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    return v9;
  }
  if ( !v21[0] )
  {
    v9 = -2147024883;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA3,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\jsonhelpers.cpp",
      (const char *)0x8007000DLL,
      v20);
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    return v9;
  }
  v19 = v22;
  if ( v22 )
  {
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  return 0;
}

```

## disassembly

```asm
0x18001f774  mov     [rsp-18h+arg_10], rbx
0x18001f779  mov     [rsp-18h+arg_18], rsi
0x18001f77e  push    rbp
0x18001f77f  push    rdi
0x18001f780  push    r14
0x18001f782  mov     rbp, rsp
0x18001f785  sub     rsp, 70h
0x18001f789  mov     rax, cs:__security_cookie
0x18001f790  xor     rax, rsp
0x18001f793  mov     [rbp+var_8], rax
0x18001f797  mov     rsi, rdx
0x18001f79a  mov     rdi, rcx
0x18001f79d  mov     [rbp+var_38], 0
0x18001f7a5  mov     [rbp+string], 0
0x18001f7ad  lea     r9, [rbp+string]; string
0x18001f7b1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18001f7b5  mov     edx, 1Ch; length
0x18001f7ba  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x18001f7c1  call    cs:__imp_WindowsCreateStringReference
0x18001f7c8  nop     dword ptr [rax+rax+00h]
0x18001f7cd  test    eax, eax
0x18001f7cf  js      loc_18001F97C
0x18001f7d5  mov     rbx, [rbp+string]
0x18001f7d9  mov     rcx, [rbp+var_38]
0x18001f7dd  test    rcx, rcx
0x18001f7e0  jz      short loc_18001F7F7
0x18001f7e2  mov     [rbp+var_38], 0
0x18001f7ea  mov     rax, [rcx]
0x18001f7ed  mov     rax, [rax+10h]
0x18001f7f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7f6  nop
0x18001f7f7  lea     r8, [rbp+var_38]
0x18001f7fb  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x18001f802  mov     rcx, rbx
0x18001f805  call    cs:__imp_RoGetActivationFactory
0x18001f80c  nop     dword ptr [rax+rax+00h]
0x18001f811  mov     ebx, eax
0x18001f813  test    eax, eax
0x18001f815  jns     short loc_18001F855
0x18001f817  mov     rcx, [rbp+18h]; this
0x18001f81b  mov     r9d, eax; char *
0x18001f81e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f825  mov     edx, 9Bh; void *
0x18001f82a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f82f  nop
0x18001f830  mov     rcx, [rbp+var_38]
0x18001f834  test    rcx, rcx
0x18001f837  jz      short loc_18001F84E
0x18001f839  mov     [rbp+var_38], 0
0x18001f841  mov     rax, [rcx]
0x18001f844  mov     rax, [rax+10h]
0x18001f848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84d  nop
0x18001f84e  mov     eax, ebx
0x18001f850  jmp     loc_18001F95A
0x18001f855  mov     [rbp+var_40], 0
0x18001f859  mov     rbx, [rbp+var_38]
0x18001f85d  mov     rax, [rbx]
0x18001f860  mov     r14, [rax+38h]
0x18001f864  mov     rcx, [rsi]
0x18001f867  test    rcx, rcx
0x18001f86a  jz      short loc_18001F880
0x18001f86c  mov     qword ptr [rsi], 0
0x18001f873  mov     rax, [rcx]
0x18001f876  mov     rax, [rax+10h]
0x18001f87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f87f  nop
0x18001f880  cmp     qword ptr [rdi+18h], 7
0x18001f885  jbe     short loc_18001F88A
0x18001f887  mov     rdi, [rdi]
0x18001f88a  mov     [rbp+var_30], rdi
0x18001f88e  lea     rdx, [rbp+var_30]
0x18001f892  lea     rcx, [rbp+hstringHeader]
0x18001f896  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001f89b  lea     r9, [rbp+var_40]
0x18001f89f  mov     r8, rsi
0x18001f8a2  mov     rdx, [rax+18h]
0x18001f8a6  mov     rcx, rbx
0x18001f8a9  mov     rax, r14
0x18001f8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8b1  mov     ebx, eax
0x18001f8b3  test    eax, eax
0x18001f8b5  jns     short loc_18001F8F3
0x18001f8b7  mov     rcx, [rbp+18h]; this
0x18001f8bb  mov     r9d, eax; char *
0x18001f8be  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f8c5  mov     edx, 0A1h; void *
0x18001f8ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f8cf  nop
0x18001f8d0  mov     rcx, [rbp+var_38]
0x18001f8d4  test    rcx, rcx
0x18001f8d7  jz      short loc_18001F8EE
0x18001f8d9  mov     [rbp+var_38], 0
0x18001f8e1  mov     rax, [rcx]
0x18001f8e4  mov     rax, [rax+10h]
0x18001f8e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8ed  nop
0x18001f8ee  jmp     loc_18001F84E
0x18001f8f3  cmp     [rbp+var_40], 0
0x18001f8f7  jnz     short loc_18001F93A
0x18001f8f9  mov     rcx, [rbp+18h]; this
0x18001f8fd  mov     ebx, 8007000Dh
0x18001f902  mov     r9d, ebx; char *
0x18001f905  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001f90c  mov     edx, 0A3h; void *
0x18001f911  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f916  nop
0x18001f917  mov     rcx, [rbp+var_38]
0x18001f91b  test    rcx, rcx
0x18001f91e  jz      short loc_18001F935
0x18001f920  mov     [rbp+var_38], 0
0x18001f928  mov     rdx, [rcx]
0x18001f92b  mov     rax, [rdx+10h]
0x18001f92f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f934  nop
0x18001f935  jmp     loc_18001F84E
0x18001f93a  mov     rcx, [rbp+var_38]
0x18001f93e  test    rcx, rcx
0x18001f941  jz      short loc_18001F958
0x18001f943  mov     [rbp+var_38], 0
0x18001f94b  mov     rax, [rcx]
0x18001f94e  mov     rax, [rax+10h]
0x18001f952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f957  nop
0x18001f958  xor     eax, eax
0x18001f95a  mov     rcx, [rbp+var_8]
0x18001f95e  xor     rcx, rsp; StackCookie
0x18001f961  call    __security_check_cookie
0x18001f966  lea     r11, [rsp+70h+var_s0]
0x18001f96b  mov     rbx, [r11+30h]
0x18001f96f  mov     rsi, [r11+38h]
0x18001f973  mov     rsp, r11
0x18001f976  pop     r14
0x18001f978  pop     rdi
0x18001f979  pop     rbp
0x18001f97a  retn
0x18001f97c  mov     ecx, eax; this
0x18001f97e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
