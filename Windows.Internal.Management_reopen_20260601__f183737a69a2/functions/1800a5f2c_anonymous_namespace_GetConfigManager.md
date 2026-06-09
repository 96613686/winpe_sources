# _anonymous_namespace_::GetConfigManager

- ea: `0x1800a5f2c`
- end: `0x1800a629c`
- name: `_anonymous_namespace_::GetConfigManager`
- size: `880`
- prototype: `__int64 __fastcall(int, OLECHAR *psz)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a531c`
- `0x1800a55d4`

## callees

- `0x180009be4`
- `0x1800179f8`
- `0x1800187d4`
- `0x18002335c`
- `0x18003e5d4`
- `0x1800700ac`
- `0x1800a2688`
- `0x1800a5f2c`
- `0x1800a62d8`
- `0x1800a63f0`
- `0x1800a9360`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a61a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a61a5`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a615e`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a6189`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a615e`
- `DMCmnUtils!DmGetActiveUserSid` at `0x1800a6189`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a5f8a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800a5f8a`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a5fc7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a6096`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a61bd`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a5fc7`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a6096`
- `OLEAUT32!__imp_SysAllocString` at `0x1800a61bd`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5fb7`
- `OLEAUT32!__imp_VariantInit` at `0x1800a5fb7`
- `OLEAUT32!__imp_VariantClear` at `0x1800a626b`
- `OLEAUT32!__imp_VariantClear` at `0x1800a626b`

## string_xrefs

- `0x1800a6200`: `OMADM::TargetedUserSID`

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
0x1800a5f2c  mov     rax, rsp
0x1800a5f2f  mov     [rax+10h], rbx
0x1800a5f33  mov     [rax+8], rcx
0x1800a5f37  push    rbp
0x1800a5f38  push    rsi
0x1800a5f39  push    rdi
0x1800a5f3a  push    r12
0x1800a5f3c  push    r14
0x1800a5f3e  lea     rbp, [rax-5Fh]
0x1800a5f42  sub     rsp, 0A0h
0x1800a5f49  movaps  xmmword ptr [rax-38h], xmm6
0x1800a5f4d  movaps  xmmword ptr [rax-48h], xmm7
0x1800a5f51  mov     r14, rdx
0x1800a5f54  mov     rsi, rcx
0x1800a5f57  mov     [rbp+57h+var_90], 0
0x1800a5f5e  mov     qword ptr [rcx], 0
0x1800a5f65  mov     ebx, 1
0x1800a5f6a  mov     [rbp+57h+var_90], ebx
0x1800a5f6d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800a5f72  mov     qword ptr [rsp+0C0h+ppv], rsi; int
0x1800a5f77  lea     r9, _GUID_56a4bdd5_835a_4dd5_95b5_44805ca37db0; riid
0x1800a5f7e  mov     r8d, ebx; dwClsContext
0x1800a5f81  xor     edx, edx; pUnkOuter
0x1800a5f83  lea     rcx, _GUID_66d0db14_5638_475f_a386_629522d8c461; rclsid
0x1800a5f8a  call    cs:__imp_CoCreateInstance
0x1800a5f91  nop     dword ptr [rax+rax+00h]
0x1800a5f96  mov     rcx, [rbp+5Fh]; this
0x1800a5f9a  test    eax, eax
0x1800a5f9c  jns     short loc_1800A5FB3
0x1800a5f9e  mov     r9d, eax; char *
0x1800a5fa1  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5fa8  mov     edx, 9Ch; void *
0x1800a5fad  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a5fb3  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800a5fb7  call    cs:__imp_VariantInit
0x1800a5fbe  nop     dword ptr [rax+rax+00h]
0x1800a5fc3  nop
0x1800a5fc4  mov     rcx, r14; psz
0x1800a5fc7  call    cs:__imp_SysAllocString
0x1800a5fce  nop     dword ptr [rax+rax+00h]
0x1800a5fd3  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800a5fd7  mov     rcx, [rbp+5Fh]; this
0x1800a5fdb  test    rax, rax
0x1800a5fde  jnz     short loc_1800A5FF2
0x1800a5fe0  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a5fe7  mov     edx, 0A0h; void *
0x1800a5fec  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a5ff2  mov     r12d, 8
0x1800a5ff8  mov     word ptr [rbp+57h+pvarg], r12w
0x1800a5ffd  mov     rdi, [rsi]
0x1800a6000  mov     rax, [rdi]
0x1800a6003  mov     rbx, [rax+68h]
0x1800a6007  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800a600b  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800a6010  lea     rdx, aOmadmAccountid; "OMADM::AccountID"
0x1800a6017  lea     rcx, [rbp+57h+arg_18]
0x1800a601b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800a6020  nop
0x1800a6021  movaps  [rbp+57h+var_60], xmm6
0x1800a6025  movsd   [rbp+57h+var_50], xmm7
0x1800a602a  lea     r8, [rbp+57h+var_60]
0x1800a602e  mov     rdx, [rax]
0x1800a6031  mov     rcx, rdi
0x1800a6034  mov     rax, rbx
0x1800a6037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a603c  mov     rcx, [rbp+5Fh]; this
0x1800a6040  test    eax, eax
0x1800a6042  jns     short loc_1800A6059
0x1800a6044  mov     r9d, eax; char *
0x1800a6047  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a604e  mov     edx, 0A2h; void *
0x1800a6053  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a6059  lea     rcx, [rbp+57h+arg_18]
0x1800a605d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6062  lea     rcx, [rbp+57h+pvarg]
0x1800a6066  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1800a606b  mov     [rbp+57h+psz], 0
0x1800a6073  xor     edx, edx
0x1800a6075  lea     rcx, [rbp+57h+psz]
0x1800a6079  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a607e  lea     rdx, [rbp+57h+psz]
0x1800a6082  mov     rcx, r14
0x1800a6085  call    _anonymous_namespace___GetEnrollmentProvider
0x1800a608a  test    eax, eax
0x1800a608c  js      loc_1800A612B
0x1800a6092  mov     rcx, [rbp+57h+psz]; psz
0x1800a6096  call    cs:__imp_SysAllocString
0x1800a609d  nop     dword ptr [rax+rax+00h]
0x1800a60a2  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800a60a6  mov     rcx, [rbp+5Fh]; this
0x1800a60aa  test    rax, rax
0x1800a60ad  jnz     short loc_1800A60C1
0x1800a60af  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a60b6  mov     edx, 0A9h; void *
0x1800a60bb  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a60c1  mov     word ptr [rbp+57h+pvarg], r12w
0x1800a60c6  mov     rdi, [rsi]
0x1800a60c9  mov     rax, [rdi]
0x1800a60cc  mov     rbx, [rax+68h]
0x1800a60d0  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800a60d4  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800a60d9  lea     rdx, aOmadmServerid; "OMADM::ServerID"
0x1800a60e0  lea     rcx, [rbp+57h+arg_18]
0x1800a60e4  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800a60e9  nop
0x1800a60ea  movaps  [rbp+57h+var_60], xmm6
0x1800a60ee  movsd   [rbp+57h+var_50], xmm7
0x1800a60f3  lea     r8, [rbp+57h+var_60]
0x1800a60f7  mov     rdx, [rax]
0x1800a60fa  mov     rcx, rdi
0x1800a60fd  mov     rax, rbx
0x1800a6100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6105  mov     rcx, [rbp+5Fh]; this
0x1800a6109  test    eax, eax
0x1800a610b  jns     short loc_1800A6122
0x1800a610d  mov     r9d, eax; char *
0x1800a6110  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a6117  mov     edx, 0ACh; void *
0x1800a611c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a6122  lea     rcx, [rbp+57h+arg_18]
0x1800a6126  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a612b  lea     rcx, [rbp+57h+pvarg]
0x1800a612f  call    ?reset@?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAXXZ; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::reset(void)
0x1800a6134  xor     edx, edx
0x1800a6136  lea     rcx, [rbp+57h+psz]
0x1800a613a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a613f  lea     rdx, [rbp+57h+psz]
0x1800a6143  mov     rcx, r14
0x1800a6146  call    _anonymous_namespace___GetEnrollmentSid
0x1800a614b  test    eax, eax
0x1800a614d  jns     short loc_1800A6172
0x1800a614f  xor     edx, edx
0x1800a6151  lea     rcx, [rbp+57h+psz]
0x1800a6155  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a615a  lea     rcx, [rbp+57h+psz]
0x1800a615e  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a6165  nop     dword ptr [rax+rax+00h]
0x1800a616a  test    eax, eax
0x1800a616c  js      loc_1800A625D
0x1800a6172  mov     [rbp+57h+arg_18], 0
0x1800a617a  xor     edx, edx
0x1800a617c  lea     rcx, [rbp+57h+arg_18]
0x1800a6180  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800a6185  lea     rcx, [rbp+57h+arg_18]
0x1800a6189  call    cs:__imp_?DmGetActiveUserSid@@YAJPEAPEAG@Z; DmGetActiveUserSid(ushort * *)
0x1800a6190  nop     dword ptr [rax+rax+00h]
0x1800a6195  test    eax, eax
0x1800a6197  js      loc_1800A6253
0x1800a619d  mov     rdx, [rbp+57h+psz]
0x1800a61a1  mov     rcx, [rbp+57h+arg_18]
0x1800a61a5  call    cs:__imp__o__wcsicmp
0x1800a61ac  nop     dword ptr [rax+rax+00h]
0x1800a61b1  test    eax, eax
0x1800a61b3  jnz     loc_1800A6253
0x1800a61b9  mov     rcx, [rbp+57h+psz]; psz
0x1800a61bd  call    cs:__imp_SysAllocString
0x1800a61c4  nop     dword ptr [rax+rax+00h]
0x1800a61c9  mov     qword ptr [rbp+57h+pvarg+8], rax
0x1800a61cd  mov     rcx, [rbp+5Fh]; this
0x1800a61d1  test    rax, rax
0x1800a61d4  jnz     short loc_1800A61E8
0x1800a61d6  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a61dd  mov     edx, 0B7h; void *
0x1800a61e2  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800a61e8  mov     word ptr [rbp+57h+pvarg], r12w
0x1800a61ed  mov     rdi, [rsi]
0x1800a61f0  mov     rax, [rdi]
0x1800a61f3  mov     rbx, [rax+68h]
0x1800a61f7  movups  xmm6, xmmword ptr [rbp+57h+pvarg]
0x1800a61fb  movsd   xmm7, qword ptr [rbp+57h+pvarg+10h]
0x1800a6200  lea     rdx, aOmadmTargetedu; "OMADM::TargetedUserSID"
0x1800a6207  lea     rcx, [rbp+57h+var_88]
0x1800a620b  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x1800a6210  nop
0x1800a6211  movaps  [rbp+57h+var_60], xmm6
0x1800a6215  movsd   [rbp+57h+var_50], xmm7
0x1800a621a  lea     r8, [rbp+57h+var_60]
0x1800a621e  mov     rdx, [rax]
0x1800a6221  mov     rcx, rdi
0x1800a6224  mov     rax, rbx
0x1800a6227  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a622c  mov     rcx, [rbp+5Fh]; this
0x1800a6230  test    eax, eax
0x1800a6232  jns     short loc_1800A6249
0x1800a6234  mov     r9d, eax; char *
0x1800a6237  lea     r8, aOnecoreuapAdmi_36; "onecoreuap\\admin\\enterprisemgmt\\firs"...
0x1800a623e  mov     edx, 0BAh; void *
0x1800a6243  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800a6249  lea     rcx, [rbp+57h+var_88]
0x1800a624d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(ushort *),&SysFreeString(ushort *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6252  nop
0x1800a6253  lea     rcx, [rbp+57h+arg_18]
0x1800a6257  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a625c  nop
0x1800a625d  lea     rcx, [rbp+57h+psz]
0x1800a6261  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800a6266  nop
0x1800a6267  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800a626b  call    cs:__imp_VariantClear
0x1800a6272  nop     dword ptr [rax+rax+00h]
0x1800a6277  mov     rax, rsi
0x1800a627a  lea     r11, [rsp+0C0h+var_20]
0x1800a6282  mov     rbx, [r11+38h]
0x1800a6286  movaps  xmm6, xmmword ptr [r11-10h]
0x1800a628b  movaps  xmm7, xmmword ptr [r11-20h]
0x1800a6290  mov     rsp, r11
0x1800a6293  pop     r14
0x1800a6295  pop     r12
0x1800a6297  pop     rdi
0x1800a6298  pop     rsi
0x1800a6299  pop     rbp
0x1800a629a  retn
```
