# CheckBus(IPnpDevnode *,int *,int *,int *,int *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)

- ea: `0x18000796c`
- end: `0x180008026`
- name: `?CheckBus@@YAJPEAUIPnpDevnode@@PEAH111AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `1722`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _DWORD *, _DWORD *, _DWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d094`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x1800076f0`
- `0x18000796c`
- `0x180008404`
- `0x180009650`
- `0x18000fb60`
- `0x180010da8`
- `0x180034c5c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007bc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007be2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c05`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c6e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007d57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007ede`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007b9e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007bc1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007be2`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c05`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c28`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c4b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007c6e`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007d57`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180007ede`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e56`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ef1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007fa1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ff1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e40`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e4b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007e56`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ef1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f83`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007f8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007fa1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180007ff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007eb7`

## string_xrefs

- `0x180007a21`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180007f6b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180007fb3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180007fdc`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CheckBus(__int64 a1, _DWORD *a2, _DWORD *a3, _DWORD *a4, _DWORD *a5, _QWORD *a6)
{
  _DWORD *v10; // r12
  _QWORD *v11; // r15
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rdi
  int v16; // eax
  __int64 v17; // rbx
  __int64 (__fastcall *v18)(__int64, _QWORD, _DWORD **); // rdi
  __int64 v19; // rcx
  __int64 v20; // rcx
  int v21; // eax
  __int64 i; // rbx
  const WCHAR *v23; // rdi
  int v24; // eax
  __int64 v25; // rbx
  __int64 (__fastcall *v26)(__int64, PROPVARIANT, __int64 *); // rdi
  __int64 v27; // rcx
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rdx
  BOOL bIgnoreCase; // [rsp+20h] [rbp-60h]
  LPVOID pv; // [rsp+30h] [rbp-50h] BYREF
  LPCWCH lpString1[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v35; // [rsp+48h] [rbp-38h]
  PROPVARIANT v36[2]; // [rsp+50h] [rbp-30h] BYREF
  __int64 v37; // [rsp+60h] [rbp-20h]
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-18h] BYREF
  __int64 v39; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  __int64 v41; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v42; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v43; // [rsp+D8h] [rbp+58h] BYREF

  v43 = 0;
  v41 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
  }
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  v10 = a5;
  *a5 = 0;
  v11 = a6;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    a6,
    0);
  v12 = v43;
  v43 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  v13 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v12, &v43);
  v14 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x176,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v13,
      bIgnoreCase);
LABEL_90:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
    return v14;
  }
  v15 = v41;
  v41 = a1;
  if ( a1 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    a1 = v41;
  }
  if ( v15 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    a1 = v41;
  }
  while ( 1 )
  {
    if ( !a1 )
      goto LABEL_72;
    a5 = 0;
    *(_OWORD *)lpString1 = 0;
    v35 = 0;
    v42 = 0;
    v16 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))a1)(
            a1,
            &GUID_d666063f_1587_4e43_81f1_b948e807363f,
            &v42);
    v14 = v16;
    if ( v16 < 0 )
    {
      v30 = 390;
      goto LABEL_87;
    }
    v17 = v42;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, _DWORD **))(*(_QWORD *)v42 + 32LL);
    v19 = (__int64)a5;
    a5 = 0;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v16 = v18(v17, 0, &a5);
    v14 = v16;
    if ( v16 < 0 )
    {
      v30 = 392;
      goto LABEL_87;
    }
    v20 = v41;
    v41 = 0;
    if ( v20 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    v16 = (*(__int64 (__fastcall **)(_DWORD *, const PROPERTYKEY *, LPCWCH *))(*(_QWORD *)a5 + 40LL))(
            a5,
            &PKEY_Device_EnumeratorName,
            lpString1);
    v14 = v16;
    if ( v16 < 0 )
    {
      v30 = 399;
LABEL_87:
      v29 = (unsigned int)v16;
      goto LABEL_88;
    }
    if ( LOWORD(lpString1[0]) == 31 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, lpString1[1]);
      }
      if ( CompareStringOrdinal(lpString1[1], -1, L"APXENUM", -1, 1) == 2 )
        *v10 = 1;
      if ( CompareStringOrdinal(lpString1[1], -1, L"USB", -1, 1) == 2 )
        *a4 = 1;
      if ( CompareStringOrdinal(lpString1[1], -1, L"HDAUDIO", -1, 1) == 2
        || CompareStringOrdinal(lpString1[1], -1, L"PCI", -1, 1) == 2 )
      {
        goto LABEL_71;
      }
      if ( CompareStringOrdinal(lpString1[1], -1, L"BTHENUM", -1, 1) == 2
        || CompareStringOrdinal(lpString1[1], -1, L"BTHHFENUM", -1, 1) == 2
        || CompareStringOrdinal(lpString1[1], -1, L"BTHLE", -1, 1) == 2 )
      {
        wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
          &pv,
          lpString1[1],
          -1);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
          v11,
          &pv);
        if ( pv )
          CoTaskMemFree(pv);
        if ( *v11 )
        {
          *a2 = 1;
          if ( CompareStringOrdinal(lpString1[1], -1, L"BTHHFENUM", -1, 1) == 2 )
            *a3 = 1;
          goto LABEL_71;
        }
        v14 = -2147024882;
        v29 = 2147942414LL;
        v30 = 430;
LABEL_88:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)v29,
          bIgnoreCase);
LABEL_89:
        PropVariantClear((PROPVARIANT *)lpString1);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a5);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
        goto LABEL_90;
      }
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    *(_OWORD *)v36 = 0;
    v37 = 0;
    v21 = (*(__int64 (__fastcall **)(_DWORD *, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)a5 + 40LL))(
            a5,
            &DEVPKEY_Device_CompatibleIds,
            v36);
    v14 = v21;
    if ( v21 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v21,
        bIgnoreCase);
      goto LABEL_80;
    }
    if ( LOWORD(v36[0]) == 4127 )
    {
      for ( i = 0; (unsigned int)i < LODWORD(v36[1]); i = (unsigned int)(i + 1) )
      {
        v23 = *(const WCHAR **)(v37 + 8 * i);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            13,
            WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids,
            *(_QWORD *)(v37 + 8 * i));
        }
        if ( CompareStringOrdinal(v23, -1, L"USB\\Class_E0&SubClass_01&Prot_01", -1, 1) == 2 )
        {
          *a2 = 1;
          *a4 = 0;
          break;
        }
      }
      if ( *a2 )
        break;
    }
    if ( *a4 )
      break;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
    }
    *(_OWORD *)pvar = 0;
    v39 = 0;
    v24 = (*(__int64 (__fastcall **)(_DWORD *, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)a5 + 40LL))(
            a5,
            &DEVPKEY_Device_Parent,
            pvar);
    v14 = v24;
    if ( v24 < 0 )
    {
      v31 = 485;
      goto LABEL_79;
    }
    if ( LOWORD(pvar[0]) == 31 )
    {
      v25 = v43;
      v26 = *(__int64 (__fastcall **)(__int64, PROPVARIANT, __int64 *))(*(_QWORD *)v43 + 64LL);
      v27 = v41;
      v41 = 0;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v24 = v26(v25, pvar[1], &v41);
      v14 = v24;
      if ( v24 < 0 )
      {
        v31 = 489;
LABEL_79:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v31,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v24,
          bIgnoreCase);
        PropVariantClear(pvar);
LABEL_80:
        PropVariantClear(v36);
        goto LABEL_89;
      }
    }
    PropVariantClear(pvar);
    PropVariantClear(v36);
    PropVariantClear((PROPVARIANT *)lpString1);
    if ( a5 )
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)a5 + 16LL))(a5);
    if ( v42 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    a1 = v41;
  }
  PropVariantClear(v36);
LABEL_71:
  PropVariantClear((PROPVARIANT *)lpString1);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&a5);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  a1 = v41;
LABEL_72:
  if ( a1 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  return 0;
}

```

## disassembly

```asm
0x18000796c  mov     [rsp-38h+arg_0], rbx
0x180007971  push    rbp
0x180007972  push    rsi
0x180007973  push    rdi
0x180007974  push    r12
0x180007976  push    r13
0x180007978  push    r14
0x18000797a  push    r15
0x18000797c  mov     rbp, rsp
0x18000797f  sub     rsp, 80h
0x180007986  mov     rsi, r9
0x180007989  mov     r13, r8
0x18000798c  mov     r14, rdx
0x18000798f  mov     rbx, rcx
0x180007992  xor     edi, edi
0x180007994  mov     [rbp+arg_18], rdi
0x180007998  mov     [rbp+arg_8], rdi
0x18000799c  lea     rax, WPP_GLOBAL_Control
0x1800079a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800079aa  cmp     rcx, rax
0x1800079ad  jz      short loc_1800079D1
0x1800079af  test    dword ptr [rcx+1Ch], 80000h
0x1800079b6  jz      short loc_1800079D1
0x1800079b8  cmp     byte ptr [rcx+19h], 4
0x1800079bc  jb      short loc_1800079D1
0x1800079be  lea     edx, [rdi+0Ah]
0x1800079c1  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x1800079c8  mov     rcx, [rcx+10h]
0x1800079cc  call    WPP_SF_
0x1800079d1  mov     [r14], edi
0x1800079d4  mov     [r13+0], edi
0x1800079d8  mov     [rsi], edi
0x1800079da  mov     r12, [rbp+arg_20]
0x1800079de  mov     [r12], edi
0x1800079e2  xor     edx, edx
0x1800079e4  mov     r15, [rbp+arg_28]
0x1800079e8  mov     rcx, r15
0x1800079eb  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800079f0  nop
0x1800079f1  mov     rcx, [rbp+arg_18]
0x1800079f5  mov     [rbp+arg_18], rdi
0x1800079f9  test    rcx, rcx
0x1800079fc  jz      short loc_180007A0B
0x1800079fe  mov     rax, [rcx]
0x180007a01  mov     rax, [rax+10h]
0x180007a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a0a  nop
0x180007a0b  lea     rdx, [rbp+arg_18]
0x180007a0f  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x180007a14  mov     edi, eax
0x180007a16  test    eax, eax
0x180007a18  jns     short loc_180007A37
0x180007a1a  mov     rcx, [rbp+38h]; this
0x180007a1e  mov     r9d, eax; char *
0x180007a21  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180007a28  mov     edx, 176h; void *
0x180007a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a32  jmp     loc_18000800C
0x180007a37  mov     rdi, [rbp+arg_8]
0x180007a3b  mov     [rbp+arg_8], rbx
0x180007a3f  test    rbx, rbx
0x180007a42  jz      short loc_180007A57
0x180007a44  mov     rax, [rbx]
0x180007a47  mov     rcx, rbx
0x180007a4a  mov     rax, [rax+8]
0x180007a4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a53  mov     rbx, [rbp+arg_8]
0x180007a57  test    rdi, rdi
0x180007a5a  jz      short loc_180007A6F
0x180007a5c  mov     rax, [rdi]
0x180007a5f  mov     rcx, rdi
0x180007a62  mov     rax, [rax+10h]
0x180007a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a6b  mov     rbx, [rbp+arg_8]
0x180007a6f  test    rbx, rbx
0x180007a72  jz      loc_180007F0F
0x180007a78  mov     [rbp+arg_20], 0
0x180007a80  xorps   xmm0, xmm0
0x180007a83  xor     eax, eax
0x180007a85  movups  xmmword ptr [rbp+lpString1], xmm0
0x180007a89  mov     [rbp+var_38], rax
0x180007a8d  mov     [rbp+arg_10], rax
0x180007a91  mov     rax, [rbx]
0x180007a94  lea     r8, [rbp+arg_10]
0x180007a98  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x180007a9f  mov     rcx, rbx
0x180007aa2  mov     rax, [rax]
0x180007aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aaa  mov     edi, eax
0x180007aac  test    eax, eax
0x180007aae  js      loc_180007FD4
0x180007ab4  mov     rbx, [rbp+arg_10]
0x180007ab8  mov     rax, [rbx]
0x180007abb  mov     rdi, [rax+20h]
0x180007abf  mov     rcx, [rbp+arg_20]
0x180007ac3  mov     [rbp+arg_20], 0
0x180007acb  test    rcx, rcx
0x180007ace  jz      short loc_180007ADD
0x180007ad0  mov     rdx, [rcx]
0x180007ad3  mov     rax, [rdx+10h]
0x180007ad7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007adc  nop
0x180007add  lea     r8, [rbp+arg_20]
0x180007ae1  xor     edx, edx
0x180007ae3  mov     rcx, rbx
0x180007ae6  mov     rax, rdi
0x180007ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aee  mov     edi, eax
0x180007af0  test    eax, eax
0x180007af2  js      loc_180007FCD
0x180007af8  mov     rcx, [rbp+arg_8]
0x180007afc  mov     [rbp+arg_8], 0
0x180007b04  test    rcx, rcx
0x180007b07  jz      short loc_180007B16
0x180007b09  mov     rax, [rcx]
0x180007b0c  mov     rax, [rax+10h]
0x180007b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b15  nop
0x180007b16  mov     rcx, [rbp+arg_20]
0x180007b1a  mov     rax, [rcx]
0x180007b1d  lea     r8, [rbp+lpString1]
0x180007b21  lea     rdx, PKEY_Device_EnumeratorName
0x180007b28  mov     rax, [rax+28h]
0x180007b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b31  mov     edi, eax
0x180007b33  test    eax, eax
0x180007b35  js      loc_180007FC6
0x180007b3b  cmp     word ptr [rbp+lpString1], 1Fh
0x180007b40  jnz     loc_180007C7D
0x180007b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180007b4d  lea     rax, WPP_GLOBAL_Control
0x180007b54  cmp     rcx, rax
0x180007b57  jz      short loc_180007B81
0x180007b59  test    dword ptr [rcx+1Ch], 80000h
0x180007b60  jz      short loc_180007B81
0x180007b62  cmp     byte ptr [rcx+19h], 5
0x180007b66  jb      short loc_180007B81
0x180007b68  mov     edx, 0Bh
0x180007b6d  mov     r9, [rbp+lpString1+8]
0x180007b71  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180007b78  mov     rcx, [rcx+10h]
0x180007b7c  call    WPP_SF_S
0x180007b81  mov     edi, 1
0x180007b86  mov     [rsp+80h+bIgnoreCase], edi; bIgnoreCase
0x180007b8a  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007b8e  mov     r9d, ebx; cchCount2
0x180007b91  lea     r8, String2; "APXENUM"
0x180007b98  mov     edx, ebx; cchCount1
0x180007b9a  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007b9e  call    cs:__imp_CompareStringOrdinal
0x180007ba4  cmp     eax, 2
0x180007ba7  jnz     short loc_180007BAD
0x180007ba9  mov     [r12], edi
0x180007bad  mov     [rsp+80h+bIgnoreCase], edi; bIgnoreCase
0x180007bb1  mov     r9d, ebx; cchCount2
0x180007bb4  lea     r8, Enumerator; "USB"
0x180007bbb  mov     edx, ebx; cchCount1
0x180007bbd  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007bc1  call    cs:__imp_CompareStringOrdinal
0x180007bc7  cmp     eax, 2
0x180007bca  jnz     short loc_180007BCE
0x180007bcc  mov     [rsi], edi
0x180007bce  mov     [rsp+80h+bIgnoreCase], edi; bIgnoreCase
0x180007bd2  mov     r9d, ebx; cchCount2
0x180007bd5  lea     r8, aHdaudio; "HDAUDIO"
0x180007bdc  mov     edx, ebx; cchCount1
0x180007bde  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007be2  call    cs:__imp_CompareStringOrdinal
0x180007be8  cmp     eax, 2
0x180007beb  jz      loc_180007EED
0x180007bf1  mov     [rsp+80h+bIgnoreCase], edi; bIgnoreCase
0x180007bf5  mov     r9d, ebx; cchCount2
0x180007bf8  lea     r8, aPci; "PCI"
0x180007bff  mov     edx, ebx; cchCount1
0x180007c01  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007c05  call    cs:__imp_CompareStringOrdinal
0x180007c0b  cmp     eax, 2
0x180007c0e  jz      loc_180007EED
0x180007c14  mov     [rsp+80h+bIgnoreCase], edi; bIgnoreCase
0x180007c18  mov     r9d, ebx; cchCount2
0x180007c1b  lea     r8, aBthenum; "BTHENUM"
0x180007c22  mov     edx, ebx; cchCount1
0x180007c24  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007c28  call    cs:__imp_CompareStringOrdinal
0x180007c2e  cmp     eax, 2
0x180007c31  jz      loc_180007E92
0x180007c37  mov     [rsp+80h+bIgnoreCase], edi; bIgnoreCase
0x180007c3b  mov     r9d, ebx; cchCount2
0x180007c3e  lea     r8, aBthhfenum; "BTHHFENUM"
0x180007c45  mov     edx, ebx; cchCount1
0x180007c47  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007c4b  call    cs:__imp_CompareStringOrdinal
0x180007c51  cmp     eax, 2
0x180007c54  jz      loc_180007E92
0x180007c5a  mov     [rsp+80h+bIgnoreCase], edi; int
0x180007c5e  mov     r9d, ebx; cchCount2
0x180007c61  lea     r8, aBthle; "BTHLE"
0x180007c68  mov     edx, ebx; cchCount1
0x180007c6a  mov     rcx, [rbp+lpString1+8]; lpString1
0x180007c6e  call    cs:__imp_CompareStringOrdinal
0x180007c74  cmp     eax, 2
0x180007c77  jz      loc_180007E92
0x180007c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c84  lea     rbx, WPP_GLOBAL_Control
0x180007c8b  cmp     rcx, rbx
0x180007c8e  jz      short loc_180007CB4
0x180007c90  test    dword ptr [rcx+1Ch], 80000h
0x180007c97  jz      short loc_180007CB4
0x180007c99  cmp     byte ptr [rcx+19h], 5
0x180007c9d  jb      short loc_180007CB4
0x180007c9f  mov     edx, 0Ch
0x180007ca4  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180007cab  mov     rcx, [rcx+10h]
0x180007caf  call    WPP_SF_
0x180007cb4  xorps   xmm0, xmm0
0x180007cb7  xor     eax, eax
0x180007cb9  movups  xmmword ptr [rbp+var_30], xmm0
0x180007cbd  mov     [rbp+var_20], rax
0x180007cc1  mov     rcx, [rbp+arg_20]
0x180007cc5  mov     rax, [rcx]
0x180007cc8  lea     r8, [rbp+var_30]
0x180007ccc  lea     rdx, DEVPKEY_Device_CompatibleIds
0x180007cd3  mov     rax, [rax+28h]
0x180007cd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cdc  mov     edi, eax
0x180007cde  test    eax, eax
0x180007ce0  js      loc_180007FAC
0x180007ce6  mov     eax, 101Fh
0x180007ceb  cmp     word ptr [rbp+var_30], ax
0x180007cef  jnz     loc_180007D84
0x180007cf5  xor     ebx, ebx
0x180007cf7  cmp     ebx, dword ptr [rbp+var_30+8]
0x180007cfa  jnb     short loc_180007D73
0x180007cfc  mov     rax, [rbp+var_20]
0x180007d00  mov     rdi, [rax+rbx*8]
0x180007d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d0b  lea     rax, WPP_GLOBAL_Control
0x180007d12  cmp     rcx, rax
0x180007d15  jz      short loc_180007D3E
0x180007d17  test    dword ptr [rcx+1Ch], 80000h
0x180007d1e  jz      short loc_180007D3E
0x180007d20  cmp     byte ptr [rcx+19h], 5
0x180007d24  jb      short loc_180007D3E
0x180007d26  mov     edx, 0Dh
0x180007d2b  mov     r9, rdi
0x180007d2e  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180007d35  mov     rcx, [rcx+10h]
0x180007d39  call    WPP_SF_S
0x180007d3e  mov     [rsp+80h+bIgnoreCase], 1; int
0x180007d46  or      r9d, 0FFFFFFFFh; cchCount2
0x180007d4a  lea     r8, aUsbClassE0Subc; "USB\\Class_E0&SubClass_01&Prot_01"
0x180007d51  or      edx, r9d; cchCount1
0x180007d54  mov     rcx, rdi; lpString1
0x180007d57  call    cs:__imp_CompareStringOrdinal
0x180007d5d  cmp     eax, 2
0x180007d60  jz      short loc_180007D66
0x180007d62  inc     ebx
0x180007d64  jmp     short loc_180007CF7
0x180007d66  mov     dword ptr [r14], 1
0x180007d6d  mov     dword ptr [rsi], 0
0x180007d73  cmp     dword ptr [r14], 0
0x180007d77  jnz     loc_180007F9D
0x180007d7d  lea     rbx, WPP_GLOBAL_Control
0x180007d84  cmp     dword ptr [rsi], 0
0x180007d87  jnz     loc_180007F9D
0x180007d8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180007d94  cmp     rcx, rbx
0x180007d97  jz      short loc_180007DBD
0x180007d99  test    dword ptr [rcx+1Ch], 80000h
0x180007da0  jz      short loc_180007DBD
0x180007da2  cmp     byte ptr [rcx+19h], 5
0x180007da6  jb      short loc_180007DBD
0x180007da8  mov     edx, 0Eh
0x180007dad  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180007db4  mov     rcx, [rcx+10h]
0x180007db8  call    WPP_SF_
0x180007dbd  xorps   xmm0, xmm0
0x180007dc0  xor     eax, eax
0x180007dc2  movups  xmmword ptr [rbp+pvar], xmm0
0x180007dc6  mov     [rbp+var_8], rax
0x180007dca  mov     rcx, [rbp+arg_20]
0x180007dce  mov     rax, [rcx]
0x180007dd1  lea     r8, [rbp+pvar]
0x180007dd5  lea     rdx, DEVPKEY_Device_Parent
0x180007ddc  mov     rax, [rax+28h]
0x180007de0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de5  mov     edi, eax
0x180007de7  test    eax, eax
0x180007de9  js      loc_180007F96
0x180007def  cmp     word ptr [rbp+pvar], 1Fh
0x180007df4  jnz     short loc_180007E3C
0x180007df6  mov     rbx, [rbp+arg_18]
0x180007dfa  mov     rax, [rbx]
0x180007dfd  mov     rdi, [rax+40h]
0x180007e01  mov     rcx, [rbp+arg_8]
0x180007e05  mov     [rbp+arg_8], 0
0x180007e0d  test    rcx, rcx
0x180007e10  jz      short loc_180007E1F
0x180007e12  mov     rdx, [rcx]
0x180007e15  mov     rax, [rdx+10h]
  ... truncated ...
```
