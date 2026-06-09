# Windows::Internal::WiFiCloudStore::TriggerTask(ushort const *)

- ea: `0x18002931c`
- end: `0x18002962f`
- name: `?TriggerTask@WiFiCloudStore@Internal@Windows@@YAJPEBG@Z`
- size: `787`
- prototype: `__int64 __fastcall(OLECHAR *psz, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003c8a4`

## callees

- `0x180006b88`
- `0x18002931c`
- `0x180029638`
- `0x18002e2d0`
- `0x18003ca7c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029363`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029363`
- `OLEAUT32!__imp_SysAllocString` at `0x18002943b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800294c3`
- `OLEAUT32!__imp_SysAllocString` at `0x180029551`
- `OLEAUT32!__imp_SysAllocString` at `0x18002943b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800294c3`
- `OLEAUT32!__imp_SysAllocString` at `0x180029551`
- `OLEAUT32!__imp_VariantInit` at `0x18002938e`
- `OLEAUT32!__imp_VariantInit` at `0x18002938e`
- `OLEAUT32!__imp_VariantClear` at `0x1800295fb`
- `OLEAUT32!__imp_VariantClear` at `0x1800295fb`

## string_xrefs

- `0x180029378`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180029423`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800294ab`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x180029533`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x1800295b2`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::WiFiCloudStore::TriggerTask(OLECHAR *psz, const unsigned __int16 *a2)
{
  HRESULT v3; // eax
  int v4; // eax
  BSTR v5; // rbx
  unsigned int v6; // r8d
  const char *v7; // r9
  LPVOID v8; // rsi
  __int64 (__fastcall *v9)(LPVOID, BSTR, __int64 *); // rdi
  int v10; // eax
  BSTR v11; // rbx
  unsigned int v12; // r8d
  const char *v13; // r9
  __int64 v14; // rsi
  __int64 (__fastcall *v15)(__int64, BSTR, __int64 *); // rdi
  int v16; // eax
  unsigned int v17; // r8d
  const char *v18; // r9
  int v19; // eax
  const char *v20; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-D8h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-C8h] BYREF
  BSTR v24; // [rsp+48h] [rbp-B0h] BYREF
  BSTR v25[2]; // [rsp+50h] [rbp-A8h] BYREF
  VARIANTARG v26; // [rsp+60h] [rbp-98h] BYREF
  VARIANTARG v27; // [rsp+80h] [rbp-78h] BYREF
  VARIANTARG v28; // [rsp+A0h] [rbp-58h] BYREF
  VARIANTARG v29; // [rsp+C0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  LPVOID v31; // [rsp+108h] [rbp+10h] BYREF
  __int64 v32; // [rsp+110h] [rbp+18h] BYREF
  __int64 v33; // [rsp+118h] [rbp+20h] BYREF

  v31 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v3 = CoCreateInstance(&CLSID_TaskScheduler, 0, 1u, &GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85, &v31);
  try
  {
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x30,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v3,
        ppv);
    VariantInit(&pvarg);
    v27 = pvarg;
    v28 = pvarg;
    v29 = pvarg;
    v26 = pvarg;
    v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, VARIANTARG *, VARIANTARG *))(*(_QWORD *)v31 + 80LL))(
           v31,
           &v26,
           &v29,
           &v28);
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v4,
        (int)&v27);
    v5 = SysAllocString(L"\\Microsoft\\Windows\\WlanSvc");
    v25[0] = v5;
    if ( !v5 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x36, v6, v7);
    v33 = 0;
    v8 = v31;
    v9 = *(__int64 (__fastcall **)(LPVOID, BSTR, __int64 *))(*(_QWORD *)v31 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    v10 = v9(v8, v5, &v33);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x39,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v10,
        (int)&v27);
    v11 = SysAllocString(L"CDSSync");
    v24 = v11;
    if ( !v11 )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x3C, v12, v13);
    v32 = 0;
    v14 = v33;
    v15 = *(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v33 + 104LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    v16 = v15(v14, v11, &v32);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3F,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v16,
        (int)&v27);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    if ( !pvarg.llVal )
      wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x43, v17, v18);
    v26 = pvarg;
    v19 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, _QWORD))(*(_QWORD *)v32 + 96LL))(v32, &v26, 0);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
        (const char *)(unsigned int)v19,
        (int)&v27);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v32);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v33);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v25);
    VariantClear(&pvarg);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v31) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x48,
                     (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                     v20);
    return (unsigned int)v31;
  }
  return result;
}

```

## disassembly

```asm
0x18002931c  mov     rax, rsp
0x18002931f  mov     [rax+8], rbx
0x180029323  push    rsi
0x180029324  push    rdi
0x180029325  push    r14
0x180029327  sub     rsp, 0E0h
0x18002932e  mov     r14, rcx
0x180029331  mov     qword ptr [rax+10h], 0
0x180029339  lea     rcx, [rax+10h]
0x18002933d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029342  lea     rax, [rsp+0F8h+arg_8]
0x18002934a  mov     qword ptr [rsp+0F8h+ppv], rax; int
0x18002934f  lea     r9, _GUID_2faba4c7_4da9_4013_9697_20cc3fd40f85; riid
0x180029356  xor     edx, edx; pUnkOuter
0x180029358  lea     r8d, [rdx+1]; dwClsContext
0x18002935c  lea     rcx, CLSID_TaskScheduler; rclsid
0x180029363  call    cs:__imp_CoCreateInstance
0x180029369  mov     rcx, [rsp+0F8h]; this
0x180029371  test    eax, eax
0x180029373  jns     short loc_180029389
0x180029375  mov     r9d, eax; char *
0x180029378  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18002937f  mov     edx, 30h ; '0'; void *
0x180029384  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029389  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x18002938e  call    cs:__imp_VariantInit
0x180029394  nop
0x180029395  mov     rcx, [rsp+0F8h+arg_8]
0x18002939d  movups  xmm1, xmmword ptr [rsp+0F8h+pvarg]
0x1800293a2  movaps  xmmword ptr [rsp+0F8h+var_78], xmm1
0x1800293aa  movsd   xmm0, qword ptr [rsp+0F8h+pvarg+10h]
0x1800293b0  movsd   [rsp+0F8h+var_68], xmm0
0x1800293b9  movaps  [rsp+0F8h+var_58], xmm1
0x1800293c1  movsd   [rsp+0F8h+var_48], xmm0
0x1800293ca  movaps  [rsp+0F8h+var_38], xmm1
0x1800293d2  movsd   [rsp+0F8h+var_28], xmm0
0x1800293db  movaps  [rsp+0F8h+var_98], xmm1
0x1800293e0  movsd   [rsp+0F8h+var_88], xmm0
0x1800293e6  mov     rax, [rcx]
0x1800293e9  lea     rdx, [rsp+0F8h+var_78]
0x1800293f1  mov     qword ptr [rsp+0F8h+ppv], rdx; int
0x1800293f6  lea     r9, [rsp+0F8h+var_58]
0x1800293fe  lea     r8, [rsp+0F8h+var_38]
0x180029406  lea     rdx, [rsp+0F8h+var_98]
0x18002940b  mov     rax, [rax+50h]
0x18002940f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029414  mov     rcx, [rsp+0F8h]; this
0x18002941c  test    eax, eax
0x18002941e  jns     short loc_180029434
0x180029420  mov     r9d, eax; char *
0x180029423  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18002942a  mov     edx, 33h ; '3'; void *
0x18002942f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029434  lea     rcx, psz; "\\Microsoft\\Windows\\WlanSvc"
0x18002943b  call    cs:__imp_SysAllocString
0x180029441  mov     rbx, rax
0x180029444  mov     [rsp+0F8h+var_A8], rax
0x180029449  mov     rcx, [rsp+0F8h]; this
0x180029451  test    rax, rax
0x180029454  jnz     short loc_18002945E
0x180029456  lea     edx, [rax+36h]; void *
0x180029459  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18002945e  mov     [rsp+0F8h+arg_18], 0
0x18002946a  mov     rsi, [rsp+0F8h+arg_8]
0x180029472  mov     rax, [rsi]
0x180029475  mov     rdi, [rax+38h]
0x180029479  lea     rcx, [rsp+0F8h+arg_18]
0x180029481  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180029486  lea     r8, [rsp+0F8h+arg_18]
0x18002948e  mov     rdx, rbx
0x180029491  mov     rcx, rsi
0x180029494  mov     rax, rdi
0x180029497  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002949c  mov     rcx, [rsp+0F8h]; this
0x1800294a4  test    eax, eax
0x1800294a6  jns     short loc_1800294BC
0x1800294a8  mov     r9d, eax; char *
0x1800294ab  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x1800294b2  mov     edx, 39h ; '9'; void *
0x1800294b7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800294bc  lea     rcx, aCdssync; "CDSSync"
0x1800294c3  call    cs:__imp_SysAllocString
0x1800294c9  mov     rbx, rax
0x1800294cc  mov     [rsp+0F8h+var_B0], rax
0x1800294d1  mov     rcx, [rsp+0F8h]; this
0x1800294d9  test    rax, rax
0x1800294dc  jnz     short loc_1800294E6
0x1800294de  lea     edx, [rax+3Ch]; void *
0x1800294e1  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800294e6  mov     [rsp+0F8h+arg_10], 0
0x1800294f2  mov     rsi, [rsp+0F8h+arg_18]
0x1800294fa  mov     rax, [rsi]
0x1800294fd  mov     rdi, [rax+68h]
0x180029501  lea     rcx, [rsp+0F8h+arg_10]
0x180029509  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002950e  lea     r8, [rsp+0F8h+arg_10]
0x180029516  mov     rdx, rbx
0x180029519  mov     rcx, rsi
0x18002951c  mov     rax, rdi
0x18002951f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029524  mov     rcx, [rsp+0F8h]; this
0x18002952c  test    eax, eax
0x18002952e  jns     short loc_180029544
0x180029530  mov     r9d, eax; char *
0x180029533  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18002953a  mov     edx, 3Fh ; '?'; void *
0x18002953f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180029544  mov     eax, 8
0x180029549  mov     word ptr [rsp+0F8h+pvarg], ax
0x18002954e  mov     rcx, r14; psz
0x180029551  call    cs:__imp_SysAllocString
0x180029557  mov     qword ptr [rsp+0F8h+pvarg+8], rax
0x18002955c  mov     rcx, [rsp+0F8h]; this
0x180029564  test    rax, rax
0x180029567  jnz     short loc_180029571
0x180029569  lea     edx, [rax+43h]; void *
0x18002956c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180029571  mov     rcx, [rsp+0F8h+arg_10]
0x180029579  movups  xmm0, xmmword ptr [rsp+0F8h+pvarg]
0x18002957e  movaps  [rsp+0F8h+var_98], xmm0
0x180029583  movsd   xmm1, qword ptr [rsp+0F8h+pvarg+10h]
0x180029589  movsd   [rsp+0F8h+var_88], xmm1
0x18002958f  mov     rax, [rcx]
0x180029592  xor     r8d, r8d
0x180029595  lea     rdx, [rsp+0F8h+var_98]
0x18002959a  mov     rax, [rax+60h]
0x18002959e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800295a3  mov     rcx, [rsp+0F8h]; this
0x1800295ab  test    eax, eax
0x1800295ad  jns     short loc_1800295C4
0x1800295af  mov     r9d, eax; char *
0x1800295b2  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x1800295b9  mov     edx, 45h ; 'E'; void *
0x1800295be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800295c4  lea     rcx, [rsp+0F8h+arg_10]
0x1800295cc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800295d1  nop
0x1800295d2  lea     rcx, [rsp+0F8h+var_B0]
0x1800295d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800295dc  nop
0x1800295dd  lea     rcx, [rsp+0F8h+arg_18]
0x1800295e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800295ea  nop
0x1800295eb  lea     rcx, [rsp+0F8h+var_A8]
0x1800295f0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800295f5  nop
0x1800295f6  lea     rcx, [rsp+0F8h+pvarg]; pvarg
0x1800295fb  call    cs:__imp_VariantClear
0x180029601  nop
0x180029602  lea     rcx, [rsp+0F8h+arg_8]
0x18002960a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002960f  xor     eax, eax
0x180029611  jmp     short loc_18002961A
0x180029613  mov     eax, dword ptr [rsp+0F8h+arg_8]
0x18002961a  mov     rbx, [rsp+0F8h+arg_0]
0x180029622  add     rsp, 0E0h
0x180029629  pop     r14
0x18002962b  pop     rdi
0x18002962c  pop     rsi
0x18002962d  retn
```
