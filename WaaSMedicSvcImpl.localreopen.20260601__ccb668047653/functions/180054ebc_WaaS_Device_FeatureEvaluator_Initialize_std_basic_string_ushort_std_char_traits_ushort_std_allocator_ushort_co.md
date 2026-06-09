# WaaS::Device::FeatureEvaluator::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180054ebc`
- end: `0x1800550cb`
- name: `?Initialize@FeatureEvaluator@Device@WaaS@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `527`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18004ff6c`

## callees

- `0x1800050a0`
- `0x18000bbd4`
- `0x180024360`
- `0x180024e48`
- `0x18004a150`
- `0x180054ebc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054f11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054f11`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180054f2e`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180054f2e`

## string_xrefs

- `0x180054f0a`: `Windows.Data.Json.JsonObject`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WaaS::Device::FeatureEvaluator::Initialize(__int64 a1, _QWORD *a2)
{
  HRESULT v4; // eax
  int v5; // edx
  unsigned int v6; // r8d
  int ActivationFactory; // eax
  unsigned int v8; // ebx
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64 **); // r14
  __int64 v12; // rax
  int v13; // eax
  int DeviceFeatureObject; // eax
  __int64 *v15; // [rsp+20h] [rbp-40h] BYREF
  __int64 v16; // [rsp+28h] [rbp-38h] BYREF
  _QWORD *v17; // [rsp+30h] [rbp-30h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  v16 = 0;
  v15 = 0;
  string = 0;
  v4 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &hstringHeader, &string);
  if ( v4 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v4, v5, v6);
    JUMPOUT(0x1800550CALL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_2289f159_54de_45d8_abcc_22603fa066a0, &v16);
  v8 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x182,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)ActivationFactory,
      (int)v15);
    if ( v15 )
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return v8;
  }
  v10 = v16;
  v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 **))(*(_QWORD *)v16 + 48LL);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  v17 = a2;
  v12 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v17);
  v13 = v11(v10, *(_QWORD *)(v12 + 24), &v15);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x183,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)v13,
      (int)v15);
    if ( v15 )
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return v8;
  }
  DeviceFeatureObject = WaaS::Device::FeatureEvaluator::CreateDeviceFeatureObject(
                          a1,
                          v15,
                          (void (__fastcall ****)(_QWORD, __int64))(a1 + 16));
  v8 = DeviceFeatureObject;
  if ( DeviceFeatureObject < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x184,
      (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator.h",
      (const char *)(unsigned int)DeviceFeatureObject,
      (int)v15);
    if ( v15 )
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    return v8;
  }
  *(_BYTE *)(a1 + 8) = 1;
  if ( v15 )
    (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  return 0;
}

```

## disassembly

```asm
0x180054ebc  mov     [rsp-18h+arg_10], rbx
0x180054ec1  mov     [rsp-18h+arg_18], rsi
0x180054ec6  push    rbp
0x180054ec7  push    rdi
0x180054ec8  push    r14
0x180054eca  mov     rbp, rsp
0x180054ecd  sub     rsp, 60h
0x180054ed1  mov     rax, cs:__security_cookie
0x180054ed8  xor     rax, rsp
0x180054edb  mov     [rbp+var_8], rax
0x180054edf  mov     rdi, rdx
0x180054ee2  mov     rsi, rcx
0x180054ee5  mov     [rbp+var_38], 0
0x180054eed  mov     [rbp+var_40], 0
0x180054ef5  mov     [rbp+string], 0
0x180054efd  lea     r9, [rbp+string]; string
0x180054f01  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180054f05  mov     edx, 1Ch; length
0x180054f0a  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180054f11  call    cs:__imp_WindowsCreateStringReference
0x180054f17  test    eax, eax
0x180054f19  js      loc_1800550C3
0x180054f1f  lea     r8, [rbp+var_38]
0x180054f23  lea     rdx, _GUID_2289f159_54de_45d8_abcc_22603fa066a0
0x180054f2a  mov     rcx, [rbp+string]
0x180054f2e  call    cs:__imp_RoGetActivationFactory
0x180054f34  mov     ebx, eax
0x180054f36  test    eax, eax
0x180054f38  jns     short loc_180054F86
0x180054f3a  mov     rcx, [rbp+18h]; this
0x180054f3e  mov     r9d, eax; char *
0x180054f41  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180054f48  mov     edx, 182h; void *
0x180054f4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054f52  nop
0x180054f53  mov     rcx, [rbp+var_40]
0x180054f57  test    rcx, rcx
0x180054f5a  jz      short loc_180054F69
0x180054f5c  mov     rax, [rcx]
0x180054f5f  mov     rax, [rax+10h]
0x180054f63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f68  nop
0x180054f69  mov     rcx, [rbp+var_38]
0x180054f6d  test    rcx, rcx
0x180054f70  jz      short loc_180054F7F
0x180054f72  mov     rax, [rcx]
0x180054f75  mov     rax, [rax+10h]
0x180054f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054f7e  nop
0x180054f7f  mov     eax, ebx
0x180054f81  jmp     loc_1800550A2
0x180054f86  mov     rbx, [rbp+var_38]
0x180054f8a  mov     rax, [rbx]
0x180054f8d  mov     r14, [rax+30h]
0x180054f91  cmp     qword ptr [rdi+18h], 7
0x180054f96  jbe     short loc_180054F9B
0x180054f98  mov     rdi, [rdi]
0x180054f9b  mov     [rbp+var_30], rdi
0x180054f9f  lea     rdx, [rbp+var_30]
0x180054fa3  lea     rcx, [rbp+hstringHeader]
0x180054fa7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180054fac  nop
0x180054fad  lea     r8, [rbp+var_40]
0x180054fb1  mov     rdx, [rax+18h]
0x180054fb5  mov     rcx, rbx
0x180054fb8  mov     rax, r14
0x180054fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054fc0  mov     ebx, eax
0x180054fc2  test    eax, eax
0x180054fc4  jns     short loc_180055010
0x180054fc6  mov     rcx, [rbp+18h]; this
0x180054fca  mov     r9d, eax; char *
0x180054fcd  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180054fd4  mov     edx, 183h; void *
0x180054fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180054fde  nop
0x180054fdf  mov     rcx, [rbp+var_40]
0x180054fe3  test    rcx, rcx
0x180054fe6  jz      short loc_180054FF5
0x180054fe8  mov     rax, [rcx]
0x180054feb  mov     rax, [rax+10h]
0x180054fef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054ff4  nop
0x180054ff5  mov     rcx, [rbp+var_38]
0x180054ff9  test    rcx, rcx
0x180054ffc  jz      short loc_18005500B
0x180054ffe  mov     rax, [rcx]
0x180055001  mov     rax, [rax+10h]
0x180055005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005500a  nop
0x18005500b  jmp     loc_180054F7F
0x180055010  lea     r8, [rsi+10h]
0x180055014  mov     rdx, [rbp+var_40]
0x180055018  mov     rcx, rsi
0x18005501b  call    ?CreateDeviceFeatureObject@FeatureEvaluator@Device@WaaS@@AEAAJPEAUIJsonObject@Json@Data@Windows@@AEAV?$unique_ptr@VDeviceFeature@Device@WaaS@@U?$default_delete@VDeviceFeature@Device@WaaS@@@std@@@std@@@Z; WaaS::Device::FeatureEvaluator::CreateDeviceFeatureObject(Windows::Data::Json::IJsonObject *,std::unique_ptr<WaaS::Device::DeviceFeature> &)
0x180055020  mov     ebx, eax
0x180055022  test    eax, eax
0x180055024  jns     short loc_180055070
0x180055026  mov     rcx, [rbp+18h]; this
0x18005502a  mov     r9d, eax; char *
0x18005502d  lea     r8, aOnecoreInterna_0; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x180055034  mov     edx, 184h; void *
0x180055039  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005503e  nop
0x18005503f  mov     rcx, [rbp+var_40]
0x180055043  test    rcx, rcx
0x180055046  jz      short loc_180055055
0x180055048  mov     rax, [rcx]
0x18005504b  mov     rax, [rax+10h]
0x18005504f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055054  nop
0x180055055  mov     rcx, [rbp+var_38]
0x180055059  test    rcx, rcx
0x18005505c  jz      short loc_18005506B
0x18005505e  mov     rax, [rcx]
0x180055061  mov     rax, [rax+10h]
0x180055065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005506a  nop
0x18005506b  jmp     loc_180054F7F
0x180055070  mov     byte ptr [rsi+8], 1
0x180055074  mov     rcx, [rbp+var_40]
0x180055078  test    rcx, rcx
0x18005507b  jz      short loc_18005508A
0x18005507d  mov     rax, [rcx]
0x180055080  mov     rax, [rax+10h]
0x180055084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055089  nop
0x18005508a  mov     rcx, [rbp+var_38]
0x18005508e  test    rcx, rcx
0x180055091  jz      short loc_1800550A0
0x180055093  mov     rax, [rcx]
0x180055096  mov     rax, [rax+10h]
0x18005509a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005509f  nop
0x1800550a0  xor     eax, eax
0x1800550a2  mov     rcx, [rbp+var_8]
0x1800550a6  xor     rcx, rsp; StackCookie
0x1800550a9  call    __security_check_cookie
0x1800550ae  lea     r11, [rsp+60h+var_s0]
0x1800550b3  mov     rbx, [r11+30h]
0x1800550b7  mov     rsi, [r11+38h]
0x1800550bb  mov     rsp, r11
0x1800550be  pop     r14
0x1800550c0  pop     rdi
0x1800550c1  pop     rbp
0x1800550c2  retn
0x1800550c3  mov     ecx, eax; this
0x1800550c5  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
