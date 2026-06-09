# _anonymous_namespace_::GetConfigManager

- ea: `0x1800a2b9c`
- end: `0x1800a2ed6`
- name: `_anonymous_namespace_::GetConfigManager`
- size: `826`
- prototype: `__int64 __fastcall(int, OLECHAR *psz)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a2030`
- `0x1800a22d8`

## callees

- `0x18000992c`
- `0x180017204`
- `0x180019fb8`
- `0x180024cd0`
- `0x18003ec00`
- `0x18006ec38`
- `0x18009f5e8`
- `0x1800a2b9c`
- `0x1800a2f10`
- `0x1800a3020`
- `0x1800a5f28`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a2df1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a2df1`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a2db6`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a2ddb`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a2db6`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a2ddb`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2bfa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a2bfa`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a2c2b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a2cf4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a2e03`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a2c2b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a2cf4`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a2e03`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2c21`
- `OLEAUT32!__imp_VariantInit` at `0x1800a2c21`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2eab`
- `OLEAUT32!__imp_VariantClear` at `0x1800a2eab`

## string_xrefs

- `0x1800a2e40`: `OMADM::TargetedUserSID`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LPVOID *__fastcall anonymous_namespace_::GetConfigManager(LPVOID *a1, OLECHAR *psz)
{
  HRESULT Instance; // eax
  const char *v5; // r9
  LPVOID v6; // rdi
  __int64 (__fastcall *v7)(LPVOID, _QWORD, __int128 *); // rbx
  __int128 v8; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  _QWORD *bstr; // rax
  int v11; // eax
  const char *v12; // r9
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, _QWORD, __int128 *); // rbx
  __int128 v15; // xmm6
  IRecordInfo *v16; // xmm7_8
  _QWORD *v17; // rax
  int v18; // eax
  const char *v19; // r9
  LPVOID v20; // rdi
  __int64 (__fastcall *v21)(LPVOID, _QWORD, __int128 *); // rbx
  __int128 v22; // xmm6
  IRecordInfo *v23; // xmm7_8
  _QWORD *v24; // rax
  int v25; // eax
  int ppv; // [rsp+28h] [rbp-49h]
  _BYTE v28[8]; // [rsp+40h] [rbp-31h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-29h] BYREF
  __int128 v30; // [rsp+68h] [rbp-9h] BYREF
  IRecordInfo *v31; // [rsp+78h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+D0h] [rbp+5Fh]
  OLECHAR *psza; // [rsp+E8h] [rbp+77h] BYREF
  unsigned __int16 *v34; // [rsp+F0h] [rbp+7Fh] BYREF

  *a1 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(a1);
  Instance = CoCreateInstance(
               &GUID_66d0db14_5638_475f_a386_629522d8c461,
               0,
               1u,
               &GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0,
               a1);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  VariantInit(&pvarg);
  pvarg.llVal = (LONGLONG)SysAllocString(psz);
  if ( !pvarg.llVal )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      v5);
  pvarg.vt = 8;
  v6 = *a1;
  v7 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)*a1 + 104LL);
  v8 = *(_OWORD *)&pvarg.vt;
  pRecInfo = pvarg.pRecInfo;
  bstr = (_QWORD *)wil::make_bstr(&v34, L"OMADM::AccountID");
  v30 = v8;
  v31 = pRecInfo;
  v11 = v7(v6, *bstr, &v30);
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
      (const char *)(unsigned int)v11,
      ppv);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
  wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(&pvarg);
  psza = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &psza,
    0);
  if ( (int)anonymous_namespace_::GetEnrollmentProvider(psz, &psza) >= 0 )
  {
    pvarg.llVal = (LONGLONG)SysAllocString(psza);
    if ( !pvarg.llVal )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        v12);
    pvarg.vt = 8;
    v13 = *a1;
    v14 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)*a1 + 104LL);
    v15 = *(_OWORD *)&pvarg.vt;
    v16 = pvarg.pRecInfo;
    v17 = (_QWORD *)wil::make_bstr(&v34, L"OMADM::ServerID");
    v30 = v15;
    v31 = v16;
    v18 = v14(v13, *v17, &v30);
    if ( v18 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAC,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
        (const char *)(unsigned int)v18,
        ppv);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
  }
  wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::reset(&pvarg);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &psza,
    0);
  if ( (int)anonymous_namespace_::GetEnrollmentSid(psz, &psza) >= 0
    || (wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &psza,
          0),
        (int)DmGetActiveUserSid(&psza) >= 0) )
  {
    v34 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v34,
      0);
    if ( (int)DmGetActiveUserSid(&v34) >= 0 && !(unsigned int)_o__wcsicmp(v34, psza) )
    {
      pvarg.llVal = (LONGLONG)SysAllocString(psza);
      if ( !pvarg.llVal )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
          v19);
      pvarg.vt = 8;
      v20 = *a1;
      v21 = *(__int64 (__fastcall **)(LPVOID, _QWORD, __int128 *))(*(_QWORD *)*a1 + 104LL);
      v22 = *(_OWORD *)&pvarg.vt;
      v23 = pvarg.pRecInfo;
      v24 = (_QWORD *)wil::make_bstr(v28, L"OMADM::TargetedUserSID");
      v30 = v22;
      v31 = v23;
      v25 = v21(v20, *v24, &v30);
      if ( v25 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xBA,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\firstsync\\firstsynctracking.cpp",
          (const char *)(unsigned int)v25,
          ppv);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(unsigned short *),&void SysFreeString(unsigned short *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v28);
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v34);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&psza);
  VariantClear(&pvarg);
  return a1;
}

```

## disassembly

```asm
0x1800a2b9c  mov     rax, rsp
0x1800a2b9f  mov     [rax+10h], rbx
0x1800a2ba3  mov     [rax+8], rcx
0x1800a2ba7  push    rbp
0x1800a2ba8  push    rsi
0x1800a2ba9  push    rdi
0x1800a2baa  push    r12
0x1800a2bac  push    r14
0x1800a2bae  lea     rbp, [rax-5Fh]
0x1800a2bb2  sub     rsp, 0A0h
0x1800a2bb9  movaps  xmmword ptr [rax-38h], xmm6
0x1800a2bbd  movaps  xmmword ptr [rax-48h], xmm7
0x1800a2bc1  mov     r14, rdx
0x1800a2bc4  mov     rsi, rcx
0x1800a2bc7  mov     [rbp+57h+var_90], 0
0x1800a2bce  mov     qword ptr [rcx], 0
0x1800a2bd5  mov     ebx, 1
0x1800a2bda  mov     [rbp+57h+var_90], ebx
0x1800a2bdd  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a2be2  mov     qword ptr [rsp+0C0h+ppv], rsi; int
0x1800a2be7  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800a2bee  mov     r8d, ebx; dwClsContext
0x1800a2bf1  xor     edx, edx; pUnkOuter
0x1800a2bf3  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800a2bfa  call    cs:__imp_CoCreateInstance
0x1800a2c00  mov     rcx, [rbp+5Fh]; this
0x1800a2c04  test    eax, eax
0x1800a2c06  jns     short loc_1800A2C1D
0x1800a2c08  mov     r9d, eax; char *
0x1800a2c0b  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2c12  mov     edx, 9Ch; void *
0x1800a2c17  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2c1d  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800a2c21  call    cs:__imp_VariantInit
0x1800a2c27  nop
0x1800a2c28  mov     rcx, r14; psz
0x1800a2c2b  call    cs:__imp_SysAllocString
0x1800a2c31  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800a2c35  mov     rcx, [rbp+5Fh]; this
0x1800a2c39  test    rax, rax
0x1800a2c3c  jnz     short loc_1800A2C50
0x1800a2c3e  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2c45  mov     edx, 0A0h; void *
0x1800a2c4a  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a2c50  mov     r12d, 8
0x1800a2c56  mov     word ptr [rbp+57h+pvarg], r12w
0x1800a2c5b  mov     rdi, [rsi]
0x1800a2c5e  mov     rax, [rdi]
0x1800a2c61  mov     rbx, [rax+68h]
0x1800a2c65  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800a2c69  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800a2c6e  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x1800a2c75  lea     rcx, [rbp+57h+arg_18]
0x1800a2c79  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800a2c7e  nop
0x1800a2c7f  movaps  [rbp+57h+var_60], xmm6
0x1800a2c83  movsd   [rbp+57h+var_50], xmm7
0x1800a2c88  lea     r8, [rbp+57h+var_60]
0x1800a2c8c  mov     rdx, [rax]
0x1800a2c8f  mov     rcx, rdi
0x1800a2c92  mov     rax, rbx
0x1800a2c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2c9a  mov     rcx, [rbp+5Fh]; this
0x1800a2c9e  test    eax, eax
0x1800a2ca0  jns     short loc_1800A2CB7
0x1800a2ca2  mov     r9d, eax; char *
0x1800a2ca5  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2cac  mov     edx, 0A2h; void *
0x1800a2cb1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2cb7  lea     rcx, [rbp+57h+arg_18]
0x1800a2cbb  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2cc0  lea     rcx, [rbp+57h+pvarg]
0x1800a2cc4  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1800a2cc9  mov     [rbp+57h+psz], 0
0x1800a2cd1  xor     edx, edx
0x1800a2cd3  lea     rcx, [rbp+57h+psz]
0x1800a2cd7  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a2cdc  lea     rdx, [rbp+57h+psz]
0x1800a2ce0  mov     rcx, r14
0x1800a2ce3  call    _anonymous_namespace___GetEnrollmentProvider
0x1800a2ce8  test    eax, eax
0x1800a2cea  js      loc_1800A2D83
0x1800a2cf0  mov     rcx, [rbp+57h+psz]; psz
0x1800a2cf4  call    cs:__imp_SysAllocString
0x1800a2cfa  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800a2cfe  mov     rcx, [rbp+5Fh]; this
0x1800a2d02  test    rax, rax
0x1800a2d05  jnz     short loc_1800A2D19
0x1800a2d07  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2d0e  mov     edx, 0A9h; void *
0x1800a2d13  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a2d19  mov     word ptr [rbp+57h+pvarg], r12w
0x1800a2d1e  mov     rdi, [rsi]
0x1800a2d21  mov     rax, [rdi]
0x1800a2d24  mov     rbx, [rax+68h]
0x1800a2d28  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800a2d2c  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800a2d31  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x1800a2d38  lea     rcx, [rbp+57h+arg_18]
0x1800a2d3c  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800a2d41  nop
0x1800a2d42  movaps  [rbp+57h+var_60], xmm6
0x1800a2d46  movsd   [rbp+57h+var_50], xmm7
0x1800a2d4b  lea     r8, [rbp+57h+var_60]
0x1800a2d4f  mov     rdx, [rax]
0x1800a2d52  mov     rcx, rdi
0x1800a2d55  mov     rax, rbx
0x1800a2d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2d5d  mov     rcx, [rbp+5Fh]; this
0x1800a2d61  test    eax, eax
0x1800a2d63  jns     short loc_1800A2D7A
0x1800a2d65  mov     r9d, eax; char *
0x1800a2d68  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2d6f  mov     edx, 0ACh; void *
0x1800a2d74  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2d7a  lea     rcx, [rbp+57h+arg_18]
0x1800a2d7e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2d83  lea     rcx, [rbp+57h+pvarg]
0x1800a2d87  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1800a2d8c  xor     edx, edx
0x1800a2d8e  lea     rcx, [rbp+57h+psz]
0x1800a2d92  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a2d97  lea     rdx, [rbp+57h+psz]
0x1800a2d9b  mov     rcx, r14
0x1800a2d9e  call    _anonymous_namespace___GetEnrollmentSid
0x1800a2da3  test    eax, eax
0x1800a2da5  jns     short loc_1800A2DC4
0x1800a2da7  xor     edx, edx
0x1800a2da9  lea     rcx, [rbp+57h+psz]
0x1800a2dad  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a2db2  lea     rcx, [rbp+57h+psz]
0x1800a2db6  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a2dbc  test    eax, eax
0x1800a2dbe  js      loc_1800A2E9D
0x1800a2dc4  mov     [rbp+57h+arg_18], 0
0x1800a2dcc  xor     edx, edx
0x1800a2dce  lea     rcx, [rbp+57h+arg_18]
0x1800a2dd2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a2dd7  lea     rcx, [rbp+57h+arg_18]
0x1800a2ddb  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a2de1  test    eax, eax
0x1800a2de3  js      loc_1800A2E93
0x1800a2de9  mov     rdx, [rbp+57h+psz]
0x1800a2ded  mov     rcx, [rbp+57h+arg_18]
0x1800a2df1  call    cs:__imp__o__wcsicmp
0x1800a2df7  test    eax, eax
0x1800a2df9  jnz     loc_1800A2E93
0x1800a2dff  mov     rcx, [rbp+57h+psz]; psz
0x1800a2e03  call    cs:__imp_SysAllocString
0x1800a2e09  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800a2e0d  mov     rcx, [rbp+5Fh]; this
0x1800a2e11  test    rax, rax
0x1800a2e14  jnz     short loc_1800A2E28
0x1800a2e16  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2e1d  mov     edx, 0B7h; void *
0x1800a2e22  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a2e28  mov     word ptr [rbp+57h+pvarg], r12w
0x1800a2e2d  mov     rdi, [rsi]
0x1800a2e30  mov     rax, [rdi]
0x1800a2e33  mov     rbx, [rax+68h]
0x1800a2e37  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800a2e3b  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800a2e40  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x1800a2e47  lea     rcx, [rbp+57h+var_88]
0x1800a2e4b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800a2e50  nop
0x1800a2e51  movaps  [rbp+57h+var_60], xmm6
0x1800a2e55  movsd   [rbp+57h+var_50], xmm7
0x1800a2e5a  lea     r8, [rbp+57h+var_60]
0x1800a2e5e  mov     rdx, [rax]
0x1800a2e61  mov     rcx, rdi
0x1800a2e64  mov     rax, rbx
0x1800a2e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2e6c  mov     rcx, [rbp+5Fh]; this
0x1800a2e70  test    eax, eax
0x1800a2e72  jns     short loc_1800A2E89
0x1800a2e74  mov     r9d, eax; char *
0x1800a2e77  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a2e7e  mov     edx, 0BAh; void *
0x1800a2e83  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a2e89  lea     rcx, [rbp+57h+var_88]
0x1800a2e8d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2e92  nop
0x1800a2e93  lea     rcx, [rbp+57h+arg_18]
0x1800a2e97  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2e9c  nop
0x1800a2e9d  lea     rcx, [rbp+57h+psz]
0x1800a2ea1  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a2ea6  nop
0x1800a2ea7  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800a2eab  call    cs:__imp_VariantClear
0x1800a2eb1  mov     rax, rsi
0x1800a2eb4  lea     r11, [rsp+0C0h+var_20]
0x1800a2ebc  mov     rbx, [r11+38h]
0x1800a2ec0  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a2ec5  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a2eca  mov     rsp, r11
0x1800a2ecd  pop     r14
0x1800a2ecf  pop     r12
0x1800a2ed1  pop     rdi
0x1800a2ed2  pop     rsi
0x1800a2ed3  pop     rbp
0x1800a2ed4  retn
```
