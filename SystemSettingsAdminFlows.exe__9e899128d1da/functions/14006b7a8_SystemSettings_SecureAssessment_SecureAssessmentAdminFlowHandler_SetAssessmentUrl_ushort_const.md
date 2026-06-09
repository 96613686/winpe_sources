# SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetAssessmentUrl(ushort const *)

- ea: `0x14006b7a8`
- end: `0x14006ba70`
- name: `?SetAssessmentUrl@SecureAssessmentAdminFlowHandler@SecureAssessment@SystemSettings@@SAJPEBG@Z`
- size: `712`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140020120`
- `0x14006a94c`

## callees

- `0x14001a2a0`
- `0x14002a2c0`
- `0x140062ac4`
- `0x140063e9c`
- `0x140069e70`
- `0x140069f24`
- `0x14006b7a8`
- `0x14007d010`

## import_xrefs

- `ole32!CoUninitialize` at `0x14006ba4d`
- `ole32!CoUninitialize` at `0x14006ba4d`
- `ole32!CoInitializeEx` at `0x14006b7bc`
- `ole32!CoInitializeEx` at `0x14006b7bc`
- `ole32!CoCreateInstance` at `0x14006b824`
- `ole32!CoCreateInstance` at `0x14006b824`
- `OLEAUT32!__imp_VariantInit` at `0x14006b949`
- `OLEAUT32!__imp_VariantInit` at `0x14006b949`

## string_xrefs

- `0x14006b8d2`: `./Vendor/MSFT/SecureAssessment/LaunchURI`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::SecureAssessment::SecureAssessmentAdminFlowHandler::SetAssessmentUrl(
        const unsigned __int16 *a1)
{
  HRESULT v2; // eax
  HRESULT v3; // eax
  const unsigned __int16 *v4; // rdx
  int v5; // eax
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, __int64, __int64 *); // rbx
  int v8; // eax
  LONGLONG v9; // rax
  int v10; // eax
  int v11; // eax
  const char *v12; // r9
  __int64 result; // rax
  int ppv; // [rsp+20h] [rbp-88h]
  int ppva; // [rsp+20h] [rbp-88h]
  LONGLONG v16; // [rsp+30h] [rbp-78h] BYREF
  __int64 v17; // [rsp+38h] [rbp-70h] BYREF
  __int64 v18; // [rsp+40h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-60h] BYREF
  VARIANTARG v20; // [rsp+60h] [rbp-48h] BYREF
  VARIANTARG v21; // [rsp+80h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  LPVOID v23; // [rsp+C0h] [rbp+18h] BYREF
  __int64 v24; // [rsp+C8h] [rbp+20h] BYREF

  v2 = CoInitializeEx(0, 0);
  try
  {
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x61,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v2,
        ppv);
    v23 = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    v3 = CoCreateInstance(
           &GUID_66d0db14_5638_475f_a386_629522d8c461,
           0,
           1u,
           &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
           &v23);
    if ( v3 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x68,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v3,
        ppva);
    wil::make_bstr(&v18, L"OMADM::AccountID");
    _variant_t::_variant_t((_variant_t *)&v21, v4);
    v20 = v21;
    v5 = (*(__int64 (__fastcall **)(LPVOID, __int64, VARIANTARG *))(*(_QWORD *)v23 + 104LL))(v23, v18, &v20);
    if ( v5 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x6D,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v5,
        ppva);
    wil::make_bstr(&v16, a1);
    wil::make_bstr(&v17, L"./Vendor/MSFT/SecureAssessment/LaunchURI");
    v24 = 0;
    v6 = v23;
    v7 = *(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v23 + 80LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    v8 = v7(v6, v17, &v24);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v8,
        ppva);
    VariantInit(&pvarg);
    pvarg.vt = 8;
    v9 = v16;
    v16 = 0;
    pvarg.llVal = v9;
    v20 = pvarg;
    v10 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *, __int64))(*(_QWORD *)v24 + 96LL))(v24, &v20, 1);
    if ( v10 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7A,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v10,
        ppva);
    v11 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 24LL))(v23);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureassessmentadminflowhandler.cpp",
        (const char *)(unsigned int)v11,
        ppva);
    _variant_t::~_variant_t((_variant_t *)&pvarg);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v17);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v16);
    _variant_t::~_variant_t((_variant_t *)&v21);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v18);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v23);
    CoUninitialize();
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x81,
                           (unsigned int)"admin\\edu\\secureassessment\\ux\\secureassessmenthandlers\\adminflow\\secureas"
                                         "sessmentadminflowhandler.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x14006b7a8  mov     [rsp+arg_0], rbx
0x14006b7ad  push    rdi
0x14006b7ae  sub     rsp, 0A0h
0x14006b7b5  mov     rbx, rcx
0x14006b7b8  xor     edx, edx; dwCoInit
0x14006b7ba  xor     ecx, ecx; pvReserved
0x14006b7bc  call    cs:__imp_CoInitializeEx
0x14006b7c2  mov     rcx, [rsp+0A8h]; this
0x14006b7ca  test    eax, eax
0x14006b7cc  jns     short loc_14006B7E2
0x14006b7ce  mov     r9d, eax; char *
0x14006b7d1  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b7d8  mov     edx, 61h ; 'a'; void *
0x14006b7dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b7e2  mov     [rsp+0A8h+arg_9], 1
0x14006b7ea  mov     [rsp+0A8h+arg_10], 0
0x14006b7f6  lea     rcx, [rsp+0A8h+arg_10]
0x14006b7fe  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006b803  lea     rax, [rsp+0A8h+arg_10]
0x14006b80b  mov     qword ptr [rsp+0A8h+ppv], rax; int
0x14006b810  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x14006b817  xor     edx, edx; pUnkOuter
0x14006b819  lea     r8d, [rdx+1]; dwClsContext
0x14006b81d  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x14006b824  call    cs:__imp_CoCreateInstance
0x14006b82a  mov     rcx, [rsp+0A8h]; this
0x14006b832  test    eax, eax
0x14006b834  jns     short loc_14006B84A
0x14006b836  mov     r9d, eax; char *
0x14006b839  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b840  mov     edx, 68h ; 'h'; void *
0x14006b845  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b84a  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x14006b851  lea     rcx, [rsp+0A8h+var_68]
0x14006b856  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006b85b  nop
0x14006b85c  lea     rcx, [rsp+0A8h+var_28]; this
0x14006b864  call    ??0_variant_t@@QEAA@PEBG@Z; _variant_t::_variant_t(ushort const *)
0x14006b869  nop
0x14006b86a  mov     rcx, [rsp+0A8h+arg_10]
0x14006b872  movups  xmm0, [rsp+0A8h+var_28]
0x14006b87a  movsd   xmm1, [rsp+0A8h+var_18]
0x14006b883  movaps  [rsp+0A8h+var_48], xmm0
0x14006b888  movsd   [rsp+0A8h+var_38], xmm1
0x14006b88e  mov     rax, [rcx]
0x14006b891  lea     r8, [rsp+0A8h+var_48]
0x14006b896  mov     rdx, [rsp+0A8h+var_68]
0x14006b89b  mov     rax, [rax+68h]
0x14006b89f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b8a4  mov     rcx, [rsp+0A8h]; this
0x14006b8ac  test    eax, eax
0x14006b8ae  jns     short loc_14006B8C4
0x14006b8b0  mov     r9d, eax; char *
0x14006b8b3  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b8ba  mov     edx, 6Dh ; 'm'; void *
0x14006b8bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b8c4  mov     rdx, rbx
0x14006b8c7  lea     rcx, [rsp+0A8h+var_78]
0x14006b8cc  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006b8d1  nop
0x14006b8d2  lea     rdx, aVendorMsftSecu_1; "./Vendor/MSFT/SecureAssessment/LaunchUR"...
0x14006b8d9  lea     rcx, [rsp+0A8h+var_70]
0x14006b8de  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x14006b8e3  nop
0x14006b8e4  mov     [rsp+0A8h+arg_18], 0
0x14006b8f0  mov     rdi, [rsp+0A8h+arg_10]
0x14006b8f8  mov     rax, [rdi]
0x14006b8fb  mov     rbx, [rax+50h]
0x14006b8ff  lea     rcx, [rsp+0A8h+arg_18]
0x14006b907  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006b90c  lea     r8, [rsp+0A8h+arg_18]
0x14006b914  mov     rdx, [rsp+0A8h+var_70]
0x14006b919  mov     rcx, rdi
0x14006b91c  mov     rax, rbx
0x14006b91f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b924  mov     rcx, [rsp+0A8h]; this
0x14006b92c  test    eax, eax
0x14006b92e  jns     short loc_14006B944
0x14006b930  mov     r9d, eax; char *
0x14006b933  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b93a  mov     edx, 74h ; 't'; void *
0x14006b93f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b944  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x14006b949  call    cs:__imp_VariantInit
0x14006b94f  nop
0x14006b950  mov     eax, 8
0x14006b955  mov     word ptr [rsp+0A8h+pvarg], ax
0x14006b95a  mov     rax, [rsp+0A8h+var_78]
0x14006b95f  mov     [rsp+0A8h+var_78], 0
0x14006b968  mov     qword ptr [rsp+0A8h+pvarg+8], rax
0x14006b96d  mov     rcx, [rsp+0A8h+arg_18]
0x14006b975  movups  xmm0, xmmword ptr [rsp+0A8h+pvarg]
0x14006b97a  movaps  [rsp+0A8h+var_48], xmm0
0x14006b97f  movsd   xmm1, qword ptr [rsp+0A8h+pvarg+10h]
0x14006b985  movsd   [rsp+0A8h+var_38], xmm1
0x14006b98b  mov     rax, [rcx]
0x14006b98e  mov     r8d, 1
0x14006b994  lea     rdx, [rsp+0A8h+var_48]
0x14006b999  mov     rax, [rax+60h]
0x14006b99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b9a2  mov     rcx, [rsp+0A8h]; this
0x14006b9aa  test    eax, eax
0x14006b9ac  jns     short loc_14006B9C2
0x14006b9ae  mov     r9d, eax; char *
0x14006b9b1  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b9b8  mov     edx, 7Ah ; 'z'; void *
0x14006b9bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b9c2  mov     rcx, [rsp+0A8h+arg_10]
0x14006b9ca  mov     rax, [rcx]
0x14006b9cd  mov     rax, [rax+18h]
0x14006b9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b9d6  mov     rcx, [rsp+0A8h]; this
0x14006b9de  test    eax, eax
0x14006b9e0  jns     short loc_14006B9F7
0x14006b9e2  mov     r9d, eax; char *
0x14006b9e5  lea     r8, aAdminEduSecure; "admin\\edu\\secureassessment\\ux\\secur"...
0x14006b9ec  mov     edx, 7Dh ; '}'; void *
0x14006b9f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x14006b9f7  lea     rcx, [rsp+0A8h+pvarg]; this
0x14006b9fc  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14006ba01  nop
0x14006ba02  lea     rcx, [rsp+0A8h+arg_18]
0x14006ba0a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006ba0f  nop
0x14006ba10  lea     rcx, [rsp+0A8h+var_70]
0x14006ba15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006ba1a  nop
0x14006ba1b  lea     rcx, [rsp+0A8h+var_78]
0x14006ba20  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006ba25  nop
0x14006ba26  lea     rcx, [rsp+0A8h+var_28]; this
0x14006ba2e  call    ??1_variant_t@@QEAA@XZ; _variant_t::~_variant_t(void)
0x14006ba33  nop
0x14006ba34  lea     rcx, [rsp+0A8h+var_68]
0x14006ba39  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x14006ba3e  nop
0x14006ba3f  lea     rcx, [rsp+0A8h+arg_10]
0x14006ba47  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14006ba4c  nop
0x14006ba4d  call    cs:__imp_CoUninitialize
0x14006ba53  xor     eax, eax
0x14006ba55  jmp     short loc_14006BA5E
0x14006ba57  mov     eax, [rsp+0B8h]
0x14006ba5e  mov     rbx, [rsp+0A8h+arg_0]
0x14006ba66  add     rsp, 0A0h
0x14006ba6d  pop     rdi
0x14006ba6e  retn
```
