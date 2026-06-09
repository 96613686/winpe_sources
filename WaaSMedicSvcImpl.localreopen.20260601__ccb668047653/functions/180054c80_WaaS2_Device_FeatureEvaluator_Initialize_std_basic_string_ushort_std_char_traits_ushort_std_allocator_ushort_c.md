# WaaS2::Device::FeatureEvaluator::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180054c80`
- end: `0x180054eb6`
- name: `?Initialize@FeatureEvaluator@Device@WaaS2@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ef58`

## callees

- `0x1800050a0`
- `0x18000bbd4`
- `0x180024360`
- `0x180024e48`
- `0x18004caa8`
- `0x180054c80`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054cf6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054cf6`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180054d15`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180054d15`

## string_xrefs

- `0x180054cef`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5 #try_helpers=1
__int64 __fastcall WaaS2::Device::FeatureEvaluator::Initialize(_BYTE *a1, _QWORD *a2)
{
  _QWORD *v2; // rbx
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  int ActivationFactory; // eax
  unsigned int v9; // edi
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 *); // r14
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  unsigned int v16; // ebx
  int v17[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v18; // [rsp+28h] [rbp-50h] BYREF
  _QWORD *v19; // [rsp+30h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-40h] BYREF
  HSTRING string; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = a2;
  if ( a2[2] )
  {
    *(_QWORD *)v17 = 0;
    string = 0;
    v5 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
    if ( v5 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
      JUMPOUT(0x180054EB4LL);
    }
    ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, v17);
    v9 = ActivationFactory;
    if ( ActivationFactory >= 0 )
    {
      v18 = 0;
      v10 = *(_QWORD *)v17;
      v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v17 + 48LL);
      if ( v2[3] > 7u )
        v2 = (_QWORD *)*v2;
      v19 = v2;
      v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v19);
      v13 = v11(v10, *(_QWORD *)(v12 + 24), &v18);
      v14 = v13;
      if ( v13 >= 0 )
      {
        v15 = WaaS2::Device::DeviceFeature::Deserialize(v18, a1 + 8);
        v16 = v15;
        if ( v15 >= 0 )
        {
          *a1 = 1;
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          if ( *(_QWORD *)v17 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x100F,
            (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
            (const char *)(unsigned int)v15,
            v17[0]);
          if ( v18 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
          if ( *(_QWORD *)v17 )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
          return v16;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x100D,
          (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
          (const char *)(unsigned int)v13,
          v17[0]);
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
        if ( *(_QWORD *)v17 )
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
        return v14;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x100A,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)ActivationFactory,
        v17[0]);
      if ( *(_QWORD *)v17 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v17 + 16LL))(*(_QWORD *)v17);
      return v9;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1007,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
      (const char *)0x80070057LL,
      v17[0]);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180054c80  mov     [rsp+arg_10], rbx
0x180054c85  push    rsi
0x180054c86  push    rdi
0x180054c87  push    r14
0x180054c89  sub     rsp, 60h
0x180054c8d  mov     rax, cs:__security_cookie
0x180054c94  xor     rax, rsp
0x180054c97  mov     [rsp+78h+var_20], rax
0x180054c9c  mov     rbx, rdx
0x180054c9f  mov     rsi, rcx
0x180054ca2  cmp     qword ptr [rdx+10h], 0
0x180054ca7  jnz     short loc_180054CCE
0x180054ca9  mov     rcx, [rsp+78h]; this
0x180054cae  mov     ebx, 80070057h
0x180054cb3  mov     r9d, ebx; char *
0x180054cb6  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180054cbd  mov     edx, 1007h; void *
0x180054cc2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054cc7  mov     eax, ebx
0x180054cc9  jmp     loc_180054E8F
0x180054cce  mov     qword ptr [rsp+78h+var_58], 0; int
0x180054cd7  mov     [rsp+78h+string], 0
0x180054ce0  lea     r9, [rsp+78h+string]; string
0x180054ce5  lea     r8, [rsp+78h+hstringHeader]; hstringHeader
0x180054cea  mov     edx, 1Ch; length
0x180054cef  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180054cf6  call    cs:__imp_WindowsCreateStringReference
0x180054cfc  test    eax, eax
0x180054cfe  js      loc_180054EAD
0x180054d04  lea     r8, [rsp+78h+var_58]
0x180054d09  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180054d10  mov     rcx, [rsp+78h+string]
0x180054d15  call    cs:__imp_RoGetActivationFactory
0x180054d1b  mov     edi, eax
0x180054d1d  test    eax, eax
0x180054d1f  jns     short loc_180054D59
0x180054d21  mov     rcx, [rsp+78h]; this
0x180054d26  mov     r9d, eax; char *
0x180054d29  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180054d30  mov     edx, 100Ah; void *
0x180054d35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054d3a  nop
0x180054d3b  mov     rcx, qword ptr [rsp+78h+var_58]
0x180054d40  test    rcx, rcx
0x180054d43  jz      short loc_180054D52
0x180054d45  mov     rax, [rcx]
0x180054d48  mov     rax, [rax+10h]
0x180054d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054d51  nop
0x180054d52  mov     eax, edi
0x180054d54  jmp     loc_180054E8F
0x180054d59  mov     [rsp+78h+var_50], 0
0x180054d62  mov     rdi, qword ptr [rsp+78h+var_58]
0x180054d67  mov     rax, [rdi]
0x180054d6a  mov     r14, [rax+30h]
0x180054d6e  cmp     qword ptr [rbx+18h], 7
0x180054d73  jbe     short loc_180054D78
0x180054d75  mov     rbx, [rbx]
0x180054d78  mov     [rsp+78h+var_48], rbx
0x180054d7d  lea     rdx, [rsp+78h+var_48]
0x180054d82  lea     rcx, [rsp+78h+hstringHeader]
0x180054d87  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180054d8c  nop
0x180054d8d  lea     r8, [rsp+78h+var_50]
0x180054d92  mov     rdx, [rax+18h]
0x180054d96  mov     rcx, rdi
0x180054d99  mov     rax, r14
0x180054d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054da1  mov     ebx, eax
0x180054da3  test    eax, eax
0x180054da5  jns     short loc_180054DF6
0x180054da7  mov     rcx, [rsp+78h]; this
0x180054dac  mov     r9d, eax; char *
0x180054daf  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180054db6  mov     edx, 100Dh; void *
0x180054dbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054dc0  nop
0x180054dc1  mov     rcx, [rsp+78h+var_50]
0x180054dc6  test    rcx, rcx
0x180054dc9  jz      short loc_180054DD8
0x180054dcb  mov     rax, [rcx]
0x180054dce  mov     rax, [rax+10h]
0x180054dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054dd7  nop
0x180054dd8  mov     rcx, qword ptr [rsp+78h+var_58]
0x180054ddd  test    rcx, rcx
0x180054de0  jz      short loc_180054DEF
0x180054de2  mov     rax, [rcx]
0x180054de5  mov     rax, [rax+10h]
0x180054de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054dee  nop
0x180054def  mov     eax, ebx
0x180054df1  jmp     loc_180054E8F
0x180054df6  lea     rdx, [rsi+8]
0x180054dfa  mov     rcx, [rsp+78h+var_50]
0x180054dff  call    ?Deserialize@DeviceFeature@Device@WaaS2@@SAJPEAUIJsonObject@Json@Data@Windows@@AEAV?$unique_ptr@VDeviceFeature@Device@WaaS2@@U?$default_delete@VDeviceFeature@Device@WaaS2@@@std@@@std@@@Z; WaaS2::Device::DeviceFeature::Deserialize(Windows::Data::Json::IJsonObject *,std::unique_ptr<WaaS2::Device::DeviceFeature> &)
0x180054e04  mov     ebx, eax
0x180054e06  test    eax, eax
0x180054e08  jns     short loc_180054E56
0x180054e0a  mov     rcx, [rsp+78h]; this
0x180054e0f  mov     r9d, eax; char *
0x180054e12  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180054e19  mov     edx, 100Fh; void *
0x180054e1e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054e23  nop
0x180054e24  mov     rcx, [rsp+78h+var_50]
0x180054e29  test    rcx, rcx
0x180054e2c  jz      short loc_180054E3B
0x180054e2e  mov     rax, [rcx]
0x180054e31  mov     rax, [rax+10h]
0x180054e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e3a  nop
0x180054e3b  mov     rcx, qword ptr [rsp+78h+var_58]
0x180054e40  test    rcx, rcx
0x180054e43  jz      short loc_180054E52
0x180054e45  mov     rax, [rcx]
0x180054e48  mov     rax, [rax+10h]
0x180054e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e51  nop
0x180054e52  mov     eax, ebx
0x180054e54  jmp     short loc_180054E8F
0x180054e56  mov     byte ptr [rsi], 1
0x180054e59  mov     rcx, [rsp+78h+var_50]
0x180054e5e  test    rcx, rcx
0x180054e61  jz      short loc_180054E70
0x180054e63  mov     rax, [rcx]
0x180054e66  mov     rax, [rax+10h]
0x180054e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e6f  nop
0x180054e70  mov     rcx, qword ptr [rsp+78h+var_58]
0x180054e75  test    rcx, rcx
0x180054e78  jz      short loc_180054E87
0x180054e7a  mov     rax, [rcx]
0x180054e7d  mov     rax, [rax+10h]
0x180054e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054e86  nop
0x180054e87  xor     eax, eax
0x180054e89  jmp     short loc_180054E8F
0x180054e8b  mov     eax, [rsp+78h+var_58]
0x180054e8f  mov     rcx, [rsp+78h+var_20]
0x180054e94  xor     rcx, rsp; StackCookie
0x180054e97  call    __security_check_cookie
0x180054e9c  mov     rbx, [rsp+78h+arg_10]
0x180054ea4  add     rsp, 60h
0x180054ea8  pop     r14
0x180054eaa  pop     rdi
0x180054eab  pop     rsi
0x180054eac  retn
0x180054ead  mov     ecx, eax; this
0x180054eaf  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
