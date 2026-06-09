# Windows::Networking::UX::Internal::WlanInterface::_GetNLMNetwork(INetworkPrivate * *,_GUID *)

- ea: `0x180049cc4`
- end: `0x18004a1a9`
- name: `?_GetNLMNetwork@WlanInterface@Internal@UX@Networking@Windows@@IEAAJPEAPEAUINetworkPrivate@@PEAU_GUID@@@Z`
- size: `1253`
- prototype: `__int64 __fastcall(Windows::Networking::UX::Internal::WlanInterface *__hidden this, struct INetworkPrivate **, struct _GUID *)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003e80c`
- `0x180044fc4`

## callees

- `0x180008e30`
- `0x1800097b4`
- `0x18000de4c`
- `0x1800127d8`
- `0x18001d4d4`
- `0x1800289dc`
- `0x18002a40c`
- `0x18002bb4c`
- `0x18003a070`
- `0x18003ae48`
- `0x180049cc4`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180049e6f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180049f2f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180049e6f`
- `api-ms-win-core-com-l1-1-0!StringFromIID` at `0x180049f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a190`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a0fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a190`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049daa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180049daa`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180049e05`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x180049e05`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::_GetNLMNetwork(
        Windows::Networking::UX::Internal::WlanInterface *this,
        struct INetworkPrivate **a2,
        struct _GUID *a3)
{
  char v6; // r12
  _QWORD *v7; // rbx
  int v8; // ebx
  unsigned __int64 v9; // r9
  __int64 v10; // rdx
  HRESULT v11; // eax
  HRESULT v12; // edi
  __int64 v13; // rdx
  __int64 v14; // r8
  _QWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rbx
  LPVOID v19; // rdi
  int AgileReference; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  HRESULT v23; // eax
  __int64 v24; // rax
  int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // r8
  PVOID *v28; // rcx
  HRESULT v29; // eax
  unsigned __int64 v30; // r9
  __int64 v31; // rdx
  __int64 v32; // rax
  struct _GUID *v33; // rsi
  struct _GUID *v34; // r14
  LPVOID v35; // rdi
  int (__fastcall *v36)(LPVOID, struct _GUID *, struct INetworkPrivate **); // rbx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  void *v40; // rcx
  struct INetworkPrivate *v42; // rax
  void *v43; // rcx
  int ppv; // [rsp+20h] [rbp-48h]
  LPVOID v45; // [rsp+30h] [rbp-38h] BYREF
  struct INetworkPrivate *v46; // [rsp+38h] [rbp-30h] BYREF
  LPVOID *p_pv; // [rsp+40h] [rbp-28h] BYREF
  __int64 v48; // [rsp+48h] [rbp-20h] BYREF
  char v49; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  unsigned int v51; // [rsp+B0h] [rbp+48h] BYREF
  char *v52; // [rsp+B8h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp+58h] BYREF
  LPOLESTR lpsz; // [rsp+C8h] [rbp+60h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 91, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  v6 = 0;
  if ( a2 )
    *a2 = 0;
  if ( a3 )
    *a3 = GUID_NULL;
  v45 = 0;
  v7 = (_QWORD *)((char *)this + 816);
  if ( *((_QWORD *)this + 102) )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45, a2, a3);
    v45 = 0;
    if ( *v7 )
      v8 = (*(__int64 (__fastcall **)(_QWORD, GUID *, LPVOID *))(*(_QWORD *)*v7 + 24LL))(
             *v7,
             &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
             &v45);
    else
      v8 = 0;
    if ( v8 < 0 )
    {
      v9 = (unsigned int)v8;
      v10 = 1060;
LABEL_19:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)v9,
        ppv);
      goto LABEL_61;
    }
  }
  else
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45, a2, a3);
    v11 = CoCreateInstance(&CLSID_CNetworkListManager, 0, 0x17u, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, &v45);
    v12 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41F,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)(unsigned int)v11,
        ppv);
      v8 = v12;
      goto LABEL_61;
    }
    v52 = (char *)this + 816;
    v15 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v52);
    v18 = v15;
    v19 = v45;
    if ( v45 )
    {
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v15, v16, v17);
      AgileReference = RoGetAgileReference(0, &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b, v19, v18);
      v8 = AgileReference;
      if ( AgileReference < 0 )
      {
        v9 = (unsigned int)AgileReference;
        v10 = 1056;
        goto LABEL_19;
      }
    }
    else
    {
      v46 = 0;
      v52 = (char *)*v15;
      *v15 = 0;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52, v16, v17);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46, v21, v22);
    }
  }
  lpsz = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &lpsz,
    0);
  v23 = StringFromIID((const IID *const)((char *)this + 1204), &lpsz);
  v8 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x428,
      (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
      (const char *)(unsigned int)v23,
      ppv);
LABEL_60:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
    goto LABEL_61;
  }
  v51 = 0;
  pv = 0;
  v24 = *(_QWORD *)v45;
  p_pv = &pv;
  v48 = 0;
  v49 = 1;
  v25 = (*(__int64 (__fastcall **)(LPVOID, LPOLESTR, unsigned int *, __int64 *))(v24 + 104))(v45, lpsz, &v51, &v48);
  wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
  if ( v25 < 0 )
  {
    v28 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
        (unsigned int)v25);
      v28 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( !*((_BYTE *)this + 1186) )
      goto LABEL_34;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &lpsz,
      0);
    v29 = StringFromIID((const IID *const)((char *)this + 1188), &lpsz);
    v8 = v29;
    if ( v29 < 0 )
    {
      v30 = (unsigned int)v29;
      v31 = 1072;
      goto LABEL_30;
    }
    v32 = *(_QWORD *)v45;
    p_pv = &pv;
    v48 = 0;
    v49 = 1;
    v8 = (*(__int64 (__fastcall **)(LPVOID, LPOLESTR, unsigned int *, __int64 *))(v32 + 104))(v45, lpsz, &v51, &v48);
    wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&p_pv);
    if ( v8 < 0 )
    {
      v30 = (unsigned int)v8;
      v31 = 1073;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecoreuap\\net\\ux\\wlanmediamanager\\lib\\wlaninterface.cpp",
        (const char *)v30,
        ppv);
LABEL_58:
      v40 = pv;
      pv = 0;
      if ( v40 )
        CoTaskMemFree(v40);
      goto LABEL_60;
    }
  }
  v28 = (PVOID *)WPP_GLOBAL_Control;
LABEL_34:
  if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 8) != 0 )
  {
    WPP_SF_d(v28[2], 94, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, v51);
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  v33 = (struct _GUID *)pv;
  v34 = (struct _GUID *)((char *)pv + 16 * v51);
  while ( 1 )
  {
    if ( v33 == v34 )
    {
      v8 = -2147023728;
      if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 0x40) != 0 )
        WPP_SF_d(v28[2], 98, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 2147943568LL);
      goto LABEL_58;
    }
    if ( v28 != &WPP_GLOBAL_Control && (*((_BYTE *)v28 + 28) & 8) != 0 )
      WPP_SF__guid_(v28[2], 95, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
    v46 = 0;
    if ( a2 || v51 > 1 )
      v6 = 1;
    v35 = v45;
    v36 = *(int (__fastcall **)(LPVOID, struct _GUID *, struct INetworkPrivate **))(*(_QWORD *)v45 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46, v26, v27);
    if ( v36(v35, v33, &v46) >= 0 || !v6 )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 96, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
    v6 = 0;
LABEL_53:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46, v37, v39);
    ++v33;
    v28 = (PVOID *)WPP_GLOBAL_Control;
  }
  v6 = 0;
  LODWORD(v52) = 0;
  if ( v51 != 1
    && ((int)Windows::Networking::UX::Internal::WlanInterface::_GetNLMNetwork_::_2_::_lambda_1_::operator()(
               v38,
               &v46,
               &v52) < 0
     || (_DWORD)v52 != 2) )
  {
    goto LABEL_53;
  }
  if ( a2 )
  {
    v42 = v46;
    v46 = 0;
    *a2 = v42;
  }
  if ( a3 )
    *a3 = *v33;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 97, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids, 0);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v46, v37, v39);
  v43 = pv;
  pv = 0;
  if ( v43 )
    CoTaskMemFree(v43);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&lpsz);
  v8 = 0;
LABEL_61:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v45, v13, v14);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180049cc4  push    rbp
0x180049cc6  push    rbx
0x180049cc7  push    rsi
0x180049cc8  push    rdi
0x180049cc9  push    r12
0x180049ccb  push    r13
0x180049ccd  push    r14
0x180049ccf  push    r15
0x180049cd1  mov     rbp, rsp
0x180049cd4  sub     rsp, 68h
0x180049cd8  mov     r13, r8
0x180049cdb  mov     r15, rdx
0x180049cde  mov     rsi, rcx
0x180049ce1  lea     rdi, WPP_GLOBAL_Control
0x180049ce8  lea     r14, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180049cef  mov     rcx, cs:WPP_GLOBAL_Control
0x180049cf6  cmp     rcx, rdi
0x180049cf9  jz      short loc_180049D12
0x180049cfb  test    byte ptr [rcx+1Ch], 40h
0x180049cff  jz      short loc_180049D12
0x180049d01  mov     edx, 5Bh ; '['
0x180049d06  mov     r8, r14
0x180049d09  mov     rcx, [rcx+10h]
0x180049d0d  call    WPP_SF_
0x180049d12  xor     r12d, r12d
0x180049d15  test    r15, r15
0x180049d18  jz      short loc_180049D1D
0x180049d1a  mov     [r15], r12
0x180049d1d  test    r13, r13
0x180049d20  jz      short loc_180049D2F
0x180049d22  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180049d29  movdqu  xmmword ptr [r13+0], xmm0
0x180049d2f  mov     [rbp+var_38], r12
0x180049d33  lea     rbx, [rsi+330h]
0x180049d3a  lea     rcx, [rbp+var_38]
0x180049d3e  cmp     [rbx], r12
0x180049d41  jz      short loc_180049D88
0x180049d43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049d48  nop
0x180049d49  mov     [rbp+var_38], r12
0x180049d4d  mov     rcx, [rbx]
0x180049d50  test    rcx, rcx
0x180049d53  jnz     short loc_180049D5A
0x180049d55  mov     ebx, r12d
0x180049d58  jmp     short loc_180049D73
0x180049d5a  mov     rax, [rcx]
0x180049d5d  lea     r8, [rbp+var_38]
0x180049d61  lea     rdx, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x180049d68  mov     rax, [rax+18h]
0x180049d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d71  mov     ebx, eax
0x180049d73  test    ebx, ebx
0x180049d75  jns     loc_180049E55
0x180049d7b  mov     r9d, ebx
0x180049d7e  mov     edx, 424h
0x180049d83  jmp     loc_180049E19
0x180049d88  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049d8d  lea     rax, [rbp+var_38]
0x180049d91  mov     qword ptr [rsp+68h+ppv], rax; int
0x180049d96  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180049d9d  xor     edx, edx; pUnkOuter
0x180049d9f  lea     r8d, [rdx+17h]; dwClsContext
0x180049da3  lea     rcx, CLSID_CNetworkListManager; rclsid
0x180049daa  call    cs:__imp_CoCreateInstance
0x180049db0  mov     edi, eax
0x180049db2  test    eax, eax
0x180049db4  jns     short loc_180049DD5
0x180049db6  mov     rcx, [rbp+40h]; this
0x180049dba  mov     r9d, eax; char *
0x180049dbd  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180049dc4  mov     edx, 41Fh; void *
0x180049dc9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049dce  mov     ebx, edi
0x180049dd0  jmp     loc_18004A10D
0x180049dd5  mov     [rbp+arg_8], rbx
0x180049dd9  lea     rcx, [rbp+arg_8]
0x180049ddd  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180049de2  mov     rbx, rax
0x180049de5  mov     rdi, [rbp+var_38]
0x180049de9  test    rdi, rdi
0x180049dec  jz      short loc_180049E2E
0x180049dee  mov     rcx, rax
0x180049df1  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049df6  mov     r9, rbx
0x180049df9  mov     r8, rdi
0x180049dfc  lea     rdx, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b
0x180049e03  xor     ecx, ecx
0x180049e05  call    cs:__imp_RoGetAgileReference
0x180049e0b  mov     ebx, eax
0x180049e0d  test    eax, eax
0x180049e0f  jns     short loc_180049E4E
0x180049e11  mov     r9d, eax; char *
0x180049e14  mov     edx, 420h; void *
0x180049e19  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180049e20  mov     rcx, [rbp+40h]; this
0x180049e24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e29  jmp     loc_18004A10D
0x180049e2e  mov     [rbp+var_30], r12
0x180049e32  mov     rax, [rax]
0x180049e35  mov     [rbp+arg_8], rax
0x180049e39  mov     [rbx], r12
0x180049e3c  lea     rcx, [rbp+arg_8]
0x180049e40  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049e45  lea     rcx, [rbp+var_30]
0x180049e49  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180049e4e  lea     rdi, WPP_GLOBAL_Control
0x180049e55  mov     [rbp+lpsz], r12
0x180049e59  xor     edx, edx
0x180049e5b  lea     rcx, [rbp+lpsz]
0x180049e5f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180049e64  lea     rcx, [rsi+4B4h]; rclsid
0x180049e6b  lea     rdx, [rbp+lpsz]; lplpsz
0x180049e6f  call    cs:__imp_StringFromIID
0x180049e75  mov     ebx, eax
0x180049e77  test    eax, eax
0x180049e79  jns     short loc_180049E98
0x180049e7b  mov     rcx, [rbp+40h]; this
0x180049e7f  mov     r9d, eax; char *
0x180049e82  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180049e89  mov     edx, 428h; void *
0x180049e8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049e93  jmp     loc_18004A103
0x180049e98  mov     [rbp+arg_0], r12d
0x180049e9c  mov     [rbp+pv], r12
0x180049ea0  mov     rcx, [rbp+var_38]
0x180049ea4  mov     rax, [rcx]
0x180049ea7  lea     rdx, [rbp+pv]
0x180049eab  mov     [rbp+var_28], rdx
0x180049eaf  mov     [rbp+var_20], r12
0x180049eb3  mov     [rbp+var_18], 1
0x180049eb7  lea     r9, [rbp+var_20]
0x180049ebb  lea     r8, [rbp+arg_0]
0x180049ebf  mov     rdx, [rbp+lpsz]
0x180049ec3  mov     rax, [rax+68h]
0x180049ec7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ecc  mov     ebx, eax
0x180049ece  lea     rcx, [rbp+var_28]
0x180049ed2  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180049ed7  test    ebx, ebx
0x180049ed9  jns     loc_180049F9D
0x180049edf  mov     rcx, cs:WPP_GLOBAL_Control
0x180049ee6  cmp     rcx, rdi
0x180049ee9  jz      short loc_180049F0C
0x180049eeb  test    byte ptr [rcx+1Ch], 2
0x180049eef  jz      short loc_180049F0C
0x180049ef1  mov     edx, 5Ch ; '\'
0x180049ef6  mov     r9d, ebx
0x180049ef9  mov     r8, r14
0x180049efc  mov     rcx, [rcx+10h]
0x180049f00  call    WPP_SF_d
0x180049f05  mov     rcx, cs:WPP_GLOBAL_Control
0x180049f0c  cmp     [rsi+4A2h], r12b
0x180049f13  jz      loc_180049FA4
0x180049f19  xor     edx, edx
0x180049f1b  lea     rcx, [rbp+lpsz]
0x180049f1f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180049f24  lea     rcx, [rsi+4A4h]; rclsid
0x180049f2b  lea     rdx, [rbp+lpsz]; lplpsz
0x180049f2f  call    cs:__imp_StringFromIID
0x180049f35  mov     ebx, eax
0x180049f37  test    eax, eax
0x180049f39  jns     short loc_180049F58
0x180049f3b  mov     r9d, eax; char *
0x180049f3e  mov     edx, 430h; void *
0x180049f43  lea     r8, aOnecoreuapNetU_20; "onecoreuap\\net\\ux\\wlanmediamanager\\"...
0x180049f4a  mov     rcx, [rbp+40h]; this
0x180049f4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f53  jmp     loc_18004A0EF
0x180049f58  mov     rcx, [rbp+var_38]
0x180049f5c  mov     rax, [rcx]
0x180049f5f  lea     rdx, [rbp+pv]
0x180049f63  mov     [rbp+var_28], rdx
0x180049f67  mov     [rbp+var_20], r12
0x180049f6b  mov     [rbp+var_18], 1
0x180049f6f  lea     r9, [rbp+var_20]
0x180049f73  lea     r8, [rbp+arg_0]
0x180049f77  mov     rdx, [rbp+lpsz]
0x180049f7b  mov     rax, [rax+68h]
0x180049f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049f84  mov     ebx, eax
0x180049f86  lea     rcx, [rbp+var_28]
0x180049f8a  call    ??1?$out_param_t@V?$unique_ptr@U_L2_UI_RESPONSE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<_L2_UI_RESPONSE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180049f8f  test    ebx, ebx
0x180049f91  jns     short loc_180049F9D
0x180049f93  mov     r9d, ebx
0x180049f96  mov     edx, 431h
0x180049f9b  jmp     short loc_180049F43
0x180049f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fa4  cmp     rcx, rdi
0x180049fa7  jz      short loc_180049FCB
0x180049fa9  test    byte ptr [rcx+1Ch], 8
0x180049fad  jz      short loc_180049FCB
0x180049faf  mov     edx, 5Eh ; '^'
0x180049fb4  mov     r9d, [rbp+arg_0]
0x180049fb8  mov     r8, r14
0x180049fbb  mov     rcx, [rcx+10h]
0x180049fbf  call    WPP_SF_d
0x180049fc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180049fcb  mov     rsi, [rbp+pv]
0x180049fcf  mov     r14d, [rbp+arg_0]
0x180049fd3  shl     r14, 4
0x180049fd7  add     r14, rsi
0x180049fda  jmp     loc_18004A0BD
0x180049fdf  cmp     rcx, rdi
0x180049fe2  jz      short loc_18004A002
0x180049fe4  test    byte ptr [rcx+1Ch], 8
0x180049fe8  jz      short loc_18004A002
0x180049fea  mov     edx, 5Fh ; '_'
0x180049fef  mov     r9, rsi
0x180049ff2  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x180049ff9  mov     rcx, [rcx+10h]
0x180049ffd  call    WPP_SF__guid_
0x18004a002  mov     [rbp+var_30], r12
0x18004a006  test    r15, r15
0x18004a009  jnz     short loc_18004A011
0x18004a00b  cmp     [rbp+arg_0], 1
0x18004a00f  jbe     short loc_18004A014
0x18004a011  mov     r12b, 1
0x18004a014  mov     rdi, [rbp+var_38]
0x18004a018  mov     rax, [rdi]
0x18004a01b  mov     rbx, [rax+30h]
0x18004a01f  lea     rcx, [rbp+var_30]
0x18004a023  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a028  lea     r8, [rbp+var_30]
0x18004a02c  mov     rdx, rsi
0x18004a02f  mov     rcx, rdi
0x18004a032  mov     rax, rbx
0x18004a035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a03a  test    eax, eax
0x18004a03c  jns     short loc_18004A076
0x18004a03e  test    r12b, r12b
0x18004a041  jz      short loc_18004A076
0x18004a043  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a04a  lea     rdi, WPP_GLOBAL_Control
0x18004a051  cmp     rcx, rdi
0x18004a054  jz      short loc_18004A071
0x18004a056  test    byte ptr [rcx+1Ch], 4
0x18004a05a  jz      short loc_18004A071
0x18004a05c  mov     edx, 60h ; '`'
0x18004a061  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a068  mov     rcx, [rcx+10h]
0x18004a06c  call    WPP_SF_
0x18004a071  xor     r12d, r12d
0x18004a074  jmp     short loc_18004A0A9
0x18004a076  xor     r12d, r12d
0x18004a079  mov     dword ptr [rbp+arg_8], r12d
0x18004a07d  cmp     [rbp+arg_0], 1
0x18004a081  jz      loc_18004A129
0x18004a087  lea     r8, [rbp+arg_8]
0x18004a08b  lea     rdx, [rbp+var_30]
0x18004a08f  call    _Windows__Networking__UX__Internal__WlanInterface___GetNLMNetwork____2____lambda_1___operator__
0x18004a094  test    eax, eax
0x18004a096  js      short loc_18004A0A2
0x18004a098  cmp     dword ptr [rbp+arg_8], 2
0x18004a09c  jz      loc_18004A129
0x18004a0a2  lea     rdi, WPP_GLOBAL_Control
0x18004a0a9  lea     rcx, [rbp+var_30]
0x18004a0ad  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a0b2  add     rsi, 10h
0x18004a0b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a0bd  cmp     rsi, r14
0x18004a0c0  jnz     loc_180049FDF
0x18004a0c6  mov     ebx, 80070490h
0x18004a0cb  cmp     rcx, rdi
0x18004a0ce  jz      short loc_18004A0EF
0x18004a0d0  test    byte ptr [rcx+1Ch], 40h
0x18004a0d4  jz      short loc_18004A0EF
0x18004a0d6  mov     edx, 62h ; 'b'
0x18004a0db  mov     r9d, ebx
0x18004a0de  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18004a0e5  mov     rcx, [rcx+10h]
0x18004a0e9  call    WPP_SF_d
0x18004a0ee  nop
0x18004a0ef  mov     rcx, [rbp+pv]; pv
0x18004a0f3  mov     [rbp+pv], r12
0x18004a0f7  test    rcx, rcx
0x18004a0fa  jz      short loc_18004A103
0x18004a0fc  call    cs:__imp_CoTaskMemFree
0x18004a102  nop
0x18004a103  lea     rcx, [rbp+lpsz]
0x18004a107  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18004a10c  nop
0x18004a10d  lea     rcx, [rbp+var_38]
0x18004a111  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18004a116  mov     eax, ebx
0x18004a118  add     rsp, 68h
0x18004a11c  pop     r15
0x18004a11e  pop     r14
0x18004a120  pop     r13
0x18004a122  pop     r12
0x18004a124  pop     rdi
0x18004a125  pop     rsi
0x18004a126  pop     rbx
0x18004a127  pop     rbp
0x18004a128  retn
0x18004a129  test    r15, r15
0x18004a12c  jz      short loc_18004A139
0x18004a12e  mov     rax, [rbp+var_30]
0x18004a132  mov     [rbp+var_30], r12
0x18004a136  mov     [r15], rax
  ... truncated ...
```
