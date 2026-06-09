# CAvEndpointBuilder::ReadAudioControllerProperties(IPropertyStore *,ENDPOINT_DESCRIPTOR &)

- ea: `0x18000899c`
- end: `0x180008ead`
- name: `?ReadAudioControllerProperties@CAvEndpointBuilder@@AEAAJPEAUIPropertyStore@@AEAUENDPOINT_DESCRIPTOR@@@Z`
- size: `1297`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IPropertyStore *, struct ENDPOINT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002d094`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x180008404`
- `0x18000899c`
- `0x18000fb60`
- `0x180010da8`
- `0x180021030`
- `0x180024d54`
- `0x180034c5c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008bf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008d4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e43`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e8e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008bf6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008c01`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008d4d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e43`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e4e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e59`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008e8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d24`

## string_xrefs

- `0x1800089f3`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180008a6d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180008b34`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180008bde`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180008d0e`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CAvEndpointBuilder::ReadAudioControllerProperties(
        CAvEndpointBuilder *this,
        struct IPropertyStore *a2,
        struct ENDPOINT_DESCRIPTOR *a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  void *v6; // rcx
  int v7; // eax
  __int64 v8; // rbx
  int (__fastcall *v9)(__int64, PROPVARIANT, CAvEndpointBuilder **); // rdi
  CAvEndpointBuilder *v10; // rcx
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rbx
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rdi
  __int64 v15; // rcx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  CAvEndpointBuilder *v19; // rdi
  __int64 (__fastcall *v20)(CAvEndpointBuilder *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  int v21; // eax
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, LPVOID *); // rbx
  LPVOID v27; // rax
  __int64 v29; // [rsp+20h] [rbp-59h] BYREF
  __int64 v30; // [rsp+28h] [rbp-51h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-49h] BYREF
  __int64 v32; // [rsp+38h] [rbp-41h] BYREF
  __int64 (__fastcall ***v33)(_QWORD, GUID *, __int64 *); // [rsp+40h] [rbp-39h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v35; // [rsp+58h] [rbp-21h]
  PROPVARIANT v36[2]; // [rsp+60h] [rbp-19h] BYREF
  __int64 v37; // [rsp+70h] [rbp-9h]
  PROPVARIANT v38[2]; // [rsp+78h] [rbp-1h] BYREF
  __int64 v39; // [rsp+88h] [rbp+Fh]
  PROPVARIANT v40[2]; // [rsp+90h] [rbp+17h] BYREF
  __int64 v41; // [rsp+A0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  CAvEndpointBuilder *v43; // [rsp+E0h] [rbp+67h] BYREF
  __int64 v44; // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v45; // [rsp+F8h] [rbp+7Fh] BYREF

  v43 = this;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  v4 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))a2->lpVtbl->GetValue)(
         a2,
         DEVPKEY_KsAudio_Controller_DeviceInterface_Path,
         v40);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( LOWORD(v40[0]) != 31 )
    {
LABEL_60:
      v5 = 0;
      goto LABEL_61;
    }
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 104, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v40[1]);
    }
    v43 = 0;
    v45 = 0;
    v7 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v6, &v45);
    v5 = v7;
    if ( v7 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2CE7,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v7,
        v29);
LABEL_10:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
      goto LABEL_61;
    }
    v8 = v45;
    v9 = *(int (__fastcall **)(__int64, PROPVARIANT, CAvEndpointBuilder **))(*(_QWORD *)v45 + 40LL);
    v10 = v43;
    v43 = 0;
    if ( v10 )
      (*(void (__fastcall **)(CAvEndpointBuilder *))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v9(v8, v40[1], &v43) < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids);
      }
      goto LABEL_59;
    }
    v44 = 0;
    v29 = 0;
    v11 = wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(&v43, &v29);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = 11507;
LABEL_20:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v11,
        v29);
LABEL_21:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
      goto LABEL_10;
    }
    v13 = v29;
    v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v29 + 32LL);
    v15 = v44;
    v44 = 0;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v11 = v14(v13, 0, &v44);
    v5 = v11;
    if ( v11 < 0 )
    {
      v12 = 11509;
      goto LABEL_20;
    }
    *(_OWORD *)v36 = 0;
    v37 = 0;
    *(_OWORD *)pvar = 0;
    v35 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v44 + 40LL))(
            v44,
            DEVPKEY_AudioEndpoint_Category,
            v36);
    v5 = v16;
    if ( v16 < 0 )
    {
      v17 = 11516;
LABEL_28:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v16,
        v29);
LABEL_29:
      PropVariantClear(pvar);
      PropVariantClear(v36);
      goto LABEL_21;
    }
    if ( LOWORD(v36[0]) == 72 )
      *(_OWORD *)((char *)a3 + 20) = *(_OWORD *)v36[1];
    v16 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v44 + 40LL))(
            v44,
            DEVPKEY_AudioEndpoint_InterfaceClass,
            pvar);
    v5 = v16;
    if ( v16 < 0 )
    {
      v17 = 11523;
      goto LABEL_28;
    }
    if ( LOWORD(pvar[0]) == 72 )
      *((_OWORD *)a3 + 17) = *(_OWORD *)pvar[1];
    *(_OWORD *)v38 = 0;
    v39 = 0;
    if ( (*(int (__fastcall **)(__int64, __int128 *, PROPVARIANT *))(*(_QWORD *)v44 + 40LL))(
           v44,
           &DEVPKEY_Bluetooth_ServiceGUID,
           v38) >= 0
      && LOWORD(v38[0]) == 72
      && !*((_DWORD *)a3 + 59) )
    {
      v18 = *(_QWORD *)v38[1] - *(_QWORD *)&AudioSinkServiceClass_UUID.Data1;
      if ( *(_QWORD *)v38[1] == *(_QWORD *)&AudioSinkServiceClass_UUID.Data1 )
        v18 = *((_QWORD *)v38[1] + 1) - *(_QWORD *)AudioSinkServiceClass_UUID.Data4;
      if ( !v18 )
      {
        v33 = 0;
        v32 = 0;
        v30 = 0;
        pv = 0;
        v19 = v43;
        v20 = *(__int64 (__fastcall **)(CAvEndpointBuilder *, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v43 + 24LL);
        wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v33);
        v21 = v20(v19, &v33);
        v5 = v21;
        if ( v21 < 0 )
        {
          v22 = 11548;
LABEL_44:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v22,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v21,
            v29);
          if ( pv )
            CoTaskMemFree(pv);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
          PropVariantClear(v38);
          goto LABEL_29;
        }
        v23 = v32;
        v32 = 0;
        if ( v23 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        v21 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v23, &v32);
        v5 = v21;
        if ( v21 < 0 )
        {
          v22 = 11549;
          goto LABEL_44;
        }
        v24 = v30;
        v30 = 0;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v21 = (**v33)(v33, &GUID_d666063f_1587_4e43_81f1_b948e807363f, &v30);
        v5 = v21;
        if ( v21 < 0 )
        {
          v22 = 11550;
          goto LABEL_44;
        }
        v25 = v30;
        v26 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v30 + 40LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v21 = v26(v25, &pv);
        v5 = v21;
        if ( v21 < 0 )
        {
          v22 = 11551;
          goto LABEL_44;
        }
        *((_DWORD *)a3 + 59) = 1;
        *((_DWORD *)a3 + 62) = 1;
        v27 = pv;
        pv = 0;
        *((_QWORD *)a3 + 6) = v27;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
      }
    }
    PropVariantClear(v38);
    PropVariantClear(pvar);
    PropVariantClear(v36);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v29);
LABEL_59:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
    goto LABEL_60;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2CDF,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v4,
    v29);
LABEL_61:
  PropVariantClear(v40);
  return v5;
}

```

## disassembly

```asm
0x18000899c  mov     [rsp-8+arg_10], rbx
0x1800089a1  mov     [rsp-8+arg_0], rcx
0x1800089a6  push    rbp
0x1800089a7  push    rsi
0x1800089a8  push    rdi
0x1800089a9  push    r12
0x1800089ab  push    r14
0x1800089ad  lea     rbp, [rsp-37h]
0x1800089b2  sub     rsp, 0B0h
0x1800089b9  mov     rsi, r8
0x1800089bc  mov     rcx, rdx
0x1800089bf  xorps   xmm0, xmm0
0x1800089c2  xor     eax, eax
0x1800089c4  movups  xmmword ptr [rbp+57h+var_40], xmm0
0x1800089c8  mov     [rbp+57h+var_30], rax
0x1800089cc  mov     rax, [rdx]
0x1800089cf  lea     r8, [rbp+57h+var_40]
0x1800089d3  lea     rdx, DEVPKEY_KsAudio_Controller_DeviceInterface_Path
0x1800089da  mov     rax, [rax+28h]
0x1800089de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089e3  mov     ebx, eax
0x1800089e5  xor     r14d, r14d
0x1800089e8  test    eax, eax
0x1800089ea  jns     short loc_180008A09
0x1800089ec  mov     rcx, [rbp+5Fh]; this
0x1800089f0  mov     r9d, eax; char *
0x1800089f3  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800089fa  mov     edx, 2CDFh; void *
0x1800089ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a04  jmp     loc_180008E8A
0x180008a09  cmp     word ptr [rbp+57h+var_40], 1Fh
0x180008a0e  jnz     loc_180008E87
0x180008a14  lea     r12, WPP_GLOBAL_Control
0x180008a1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a22  cmp     rcx, r12
0x180008a25  jz      short loc_180008A4F
0x180008a27  test    dword ptr [rcx+1Ch], 80000h
0x180008a2e  jz      short loc_180008A4F
0x180008a30  cmp     byte ptr [rcx+19h], 4
0x180008a34  jb      short loc_180008A4F
0x180008a36  mov     edx, 68h ; 'h'
0x180008a3b  mov     r9, [rbp+57h+var_40+8]
0x180008a3f  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180008a46  mov     rcx, [rcx+10h]
0x180008a4a  call    WPP_SF_S
0x180008a4f  mov     [rbp+57h+arg_0], r14
0x180008a53  mov     [rbp+57h+arg_18], r14
0x180008a57  lea     rdx, [rbp+57h+arg_18]
0x180008a5b  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x180008a60  mov     ebx, eax
0x180008a62  test    eax, eax
0x180008a64  jns     short loc_180008A97
0x180008a66  mov     rcx, [rbp+5Fh]; this
0x180008a6a  mov     r9d, eax; char *
0x180008a6d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180008a74  mov     edx, 2CE7h; void *
0x180008a79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008a7e  nop
0x180008a7f  lea     rcx, [rbp+57h+arg_18]
0x180008a83  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008a88  nop
0x180008a89  lea     rcx, [rbp+57h+arg_0]
0x180008a8d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008a92  jmp     loc_180008E8A
0x180008a97  mov     rbx, [rbp+57h+arg_18]
0x180008a9b  mov     rax, [rbx]
0x180008a9e  mov     rdi, [rax+28h]
0x180008aa2  mov     rcx, [rbp+57h+arg_0]
0x180008aa6  mov     [rbp+57h+arg_0], r14
0x180008aaa  test    rcx, rcx
0x180008aad  jz      short loc_180008ABC
0x180008aaf  mov     rdx, [rcx]
0x180008ab2  mov     rax, [rdx+10h]
0x180008ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008abb  nop
0x180008abc  lea     r8, [rbp+57h+arg_0]
0x180008ac0  mov     rdx, [rbp+57h+var_40+8]
0x180008ac4  mov     rcx, rbx
0x180008ac7  mov     rax, rdi
0x180008aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008acf  test    eax, eax
0x180008ad1  jns     short loc_180008B14
0x180008ad3  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ada  cmp     rcx, r12
0x180008add  jz      loc_180008E74
0x180008ae3  test    dword ptr [rcx+1Ch], 80000h
0x180008aea  jz      loc_180008E74
0x180008af0  cmp     byte ptr [rcx+19h], 4
0x180008af4  jb      loc_180008E74
0x180008afa  mov     edx, 69h ; 'i'
0x180008aff  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180008b06  mov     rcx, [rcx+10h]
0x180008b0a  call    WPP_SF_
0x180008b0f  jmp     loc_180008E74
0x180008b14  mov     [rbp+57h+arg_8], r14
0x180008b18  mov     [rbp+57h+var_B0], r14
0x180008b1c  lea     rdx, [rbp+57h+var_B0]
0x180008b20  lea     rcx, [rbp+57h+arg_0]
0x180008b24  call    ??$com_query_to_nothrow@UIMMDevice@@AEAPEAUIPnpDevnode@@@wil@@YAJAEAPEAUIPnpDevnode@@PEAPEAUIMMDevice@@@Z; wil::com_query_to_nothrow<IMMDevice,IPnpDevnode * &>(IPnpDevnode * &,IMMDevice * *)
0x180008b29  mov     ebx, eax
0x180008b2b  test    eax, eax
0x180008b2d  jns     short loc_180008B60
0x180008b2f  mov     edx, 2CF3h; void *
0x180008b34  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180008b3b  mov     r9d, eax; char *
0x180008b3e  mov     rcx, [rbp+5Fh]; this
0x180008b42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008b47  nop
0x180008b48  lea     rcx, [rbp+57h+arg_8]
0x180008b4c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008b51  nop
0x180008b52  lea     rcx, [rbp+57h+var_B0]
0x180008b56  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008b5b  jmp     loc_180008A7F
0x180008b60  mov     rbx, [rbp+57h+var_B0]
0x180008b64  mov     rax, [rbx]
0x180008b67  mov     rdi, [rax+20h]
0x180008b6b  mov     rcx, [rbp+57h+arg_8]
0x180008b6f  mov     [rbp+57h+arg_8], r14
0x180008b73  test    rcx, rcx
0x180008b76  jz      short loc_180008B85
0x180008b78  mov     rdx, [rcx]
0x180008b7b  mov     rax, [rdx+10h]
0x180008b7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b84  nop
0x180008b85  lea     r8, [rbp+57h+arg_8]
0x180008b89  xor     edx, edx
0x180008b8b  mov     rcx, rbx
0x180008b8e  mov     rax, rdi
0x180008b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b96  mov     ebx, eax
0x180008b98  test    eax, eax
0x180008b9a  jns     short loc_180008BA3
0x180008b9c  mov     edx, 2CF5h
0x180008ba1  jmp     short loc_180008B34
0x180008ba3  xorps   xmm0, xmm0
0x180008ba6  xor     eax, eax
0x180008ba8  movups  xmmword ptr [rbp+57h+var_70], xmm0
0x180008bac  mov     [rbp+57h+var_60], rax
0x180008bb0  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180008bb4  mov     [rbp+57h+var_78], rax
0x180008bb8  mov     rcx, [rbp+57h+arg_8]
0x180008bbc  mov     rax, [rcx]
0x180008bbf  lea     r8, [rbp+57h+var_70]
0x180008bc3  lea     rdx, DEVPKEY_AudioEndpoint_Category
0x180008bca  mov     rax, [rax+28h]
0x180008bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bd3  mov     ebx, eax
0x180008bd5  test    eax, eax
0x180008bd7  jns     short loc_180008C0C
0x180008bd9  mov     edx, 2CFCh; void *
0x180008bde  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180008be5  mov     r9d, eax; char *
0x180008be8  mov     rcx, [rbp+5Fh]; this
0x180008bec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008bf1  nop
0x180008bf2  lea     rcx, [rbp+57h+pvar]; pvar
0x180008bf6  call    cs:__imp_PropVariantClear
0x180008bfc  nop
0x180008bfd  lea     rcx, [rbp+57h+var_70]; pvar
0x180008c01  call    cs:__imp_PropVariantClear
0x180008c07  jmp     loc_180008B48
0x180008c0c  cmp     word ptr [rbp+57h+var_70], 48h ; 'H'
0x180008c11  jnz     short loc_180008C1F
0x180008c13  mov     rax, [rbp+57h+var_70+8]
0x180008c17  movups  xmm0, xmmword ptr [rax]
0x180008c1a  movdqu  xmmword ptr [rsi+14h], xmm0
0x180008c1f  mov     rcx, [rbp+57h+arg_8]
0x180008c23  mov     rax, [rcx]
0x180008c26  lea     r8, [rbp+57h+pvar]
0x180008c2a  lea     rdx, DEVPKEY_AudioEndpoint_InterfaceClass
0x180008c31  mov     rax, [rax+28h]
0x180008c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c3a  mov     ebx, eax
0x180008c3c  test    eax, eax
0x180008c3e  jns     short loc_180008C47
0x180008c40  mov     edx, 2D03h
0x180008c45  jmp     short loc_180008BDE
0x180008c47  cmp     word ptr [rbp+57h+pvar], 48h ; 'H'
0x180008c4c  jnz     short loc_180008C5D
0x180008c4e  mov     rax, [rbp+57h+pvar+8]
0x180008c52  movups  xmm0, xmmword ptr [rax]
0x180008c55  movdqu  xmmword ptr [rsi+110h], xmm0
0x180008c5d  xorps   xmm0, xmm0
0x180008c60  xor     eax, eax
0x180008c62  movups  xmmword ptr [rbp+57h+var_58], xmm0
0x180008c66  mov     [rbp+57h+var_48], rax
0x180008c6a  mov     rcx, [rbp+57h+arg_8]
0x180008c6e  mov     rax, [rcx]
0x180008c71  lea     r8, [rbp+57h+var_58]
0x180008c75  lea     rdx, DEVPKEY_Bluetooth_ServiceGUID
0x180008c7c  mov     rax, [rax+28h]
0x180008c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c85  test    eax, eax
0x180008c87  js      loc_180008E3F
0x180008c8d  cmp     word ptr [rbp+57h+var_58], 48h ; 'H'
0x180008c92  jnz     loc_180008E3F
0x180008c98  cmp     [rsi+0ECh], r14d
0x180008c9f  jnz     loc_180008E3F
0x180008ca5  mov     rcx, [rbp+57h+var_58+8]
0x180008ca9  mov     rax, [rcx]
0x180008cac  sub     rax, qword ptr cs:AudioSinkServiceClass_UUID.Data1
0x180008cb3  jnz     short loc_180008CC0
0x180008cb5  mov     rax, [rcx+8]
0x180008cb9  sub     rax, qword ptr cs:AudioSinkServiceClass_UUID.Data4
0x180008cc0  test    rax, rax
0x180008cc3  jnz     loc_180008E3F
0x180008cc9  mov     [rbp+57h+var_90], r14
0x180008ccd  mov     [rbp+57h+var_98], r14
0x180008cd1  mov     [rbp+57h+var_A8], r14
0x180008cd5  mov     [rbp+57h+pv], r14
0x180008cd9  mov     rdi, [rbp+57h+arg_0]
0x180008cdd  mov     rax, [rdi]
0x180008ce0  mov     rbx, [rax+18h]
0x180008ce4  lea     rcx, [rbp+57h+var_90]
0x180008ce8  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180008ced  lea     rdx, [rbp+57h+var_90]
0x180008cf1  mov     rcx, rdi
0x180008cf4  mov     rax, rbx
0x180008cf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cfc  mov     ebx, eax
0x180008cfe  test    eax, eax
0x180008d00  jns     short loc_180008D58
0x180008d02  mov     edx, 2D1Ch; void *
0x180008d07  mov     rcx, [rbp+5Fh]; this
0x180008d0b  mov     r9d, eax; char *
0x180008d0e  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180008d15  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d1a  nop
0x180008d1b  mov     rcx, [rbp+57h+pv]; pv
0x180008d1f  test    rcx, rcx
0x180008d22  jz      short loc_180008D2B
0x180008d24  call    cs:__imp_CoTaskMemFree
0x180008d2a  nop
0x180008d2b  lea     rcx, [rbp+57h+var_A8]
0x180008d2f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008d34  nop
0x180008d35  lea     rcx, [rbp+57h+var_98]
0x180008d39  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008d3e  nop
0x180008d3f  lea     rcx, [rbp+57h+var_90]
0x180008d43  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180008d48  nop
0x180008d49  lea     rcx, [rbp+57h+var_58]; pvar
0x180008d4d  call    cs:__imp_PropVariantClear
0x180008d53  jmp     loc_180008BF2
0x180008d58  mov     rcx, [rbp+57h+var_98]
0x180008d5c  mov     [rbp+57h+var_98], r14
0x180008d60  test    rcx, rcx
0x180008d63  jz      short loc_180008D72
0x180008d65  mov     rax, [rcx]
0x180008d68  mov     rax, [rax+10h]
0x180008d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d71  nop
0x180008d72  lea     rdx, [rbp+57h+var_98]
0x180008d76  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x180008d7b  mov     ebx, eax
0x180008d7d  test    eax, eax
0x180008d7f  jns     short loc_180008D8B
0x180008d81  mov     edx, 2D1Dh
0x180008d86  jmp     loc_180008D07
0x180008d8b  mov     rcx, [rbp+57h+var_A8]
0x180008d8f  mov     [rbp+57h+var_A8], r14
0x180008d93  test    rcx, rcx
0x180008d96  jz      short loc_180008DA5
0x180008d98  mov     rax, [rcx]
0x180008d9b  mov     rax, [rax+10h]
0x180008d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008da4  nop
0x180008da5  mov     rcx, [rbp+57h+var_90]
0x180008da9  mov     rax, [rcx]
0x180008dac  lea     r8, [rbp+57h+var_A8]
0x180008db0  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x180008db7  mov     rax, [rax]
0x180008dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbf  mov     ebx, eax
0x180008dc1  test    eax, eax
0x180008dc3  jns     short loc_180008DCF
0x180008dc5  mov     edx, 2D1Eh
0x180008dca  jmp     loc_180008D07
0x180008dcf  mov     rdi, [rbp+57h+var_A8]
0x180008dd3  mov     rax, [rdi]
0x180008dd6  mov     rbx, [rax+28h]
0x180008dda  xor     edx, edx
0x180008ddc  lea     rcx, [rbp+57h+pv]
0x180008de0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180008de5  lea     rdx, [rbp+57h+pv]
0x180008de9  mov     rcx, rdi
0x180008dec  mov     rax, rbx
0x180008def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df4  mov     ebx, eax
0x180008df6  test    eax, eax
0x180008df8  jns     short loc_180008E04
0x180008dfa  mov     edx, 2D1Fh
0x180008dff  jmp     loc_180008D07
0x180008e04  mov     eax, 1
0x180008e09  mov     [rsi+0ECh], eax
0x180008e0f  mov     [rsi+0F8h], eax
0x180008e15  mov     rax, [rbp+57h+pv]
0x180008e19  mov     [rbp+57h+pv], r14
  ... truncated ...
```
