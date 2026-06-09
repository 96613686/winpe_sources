# FSClientContext::GetNetworkCamAtribs(IMFAttributes *,IMFAttributes * *)

- ea: `0x18006b09c`
- end: `0x18006b743`
- name: `?GetNetworkCamAtribs@FSClientContext@@IEAAJPEAUIMFAttributes@@PEAPEAU2@@Z`
- size: `1703`
- prototype: `__int64 __fastcall(FSClientContext *__hidden this, struct IMFAttributes *, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180071470`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a648`
- `0x180024200`
- `0x180024308`
- `0x18006b09c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b1ea`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006b1ea`
- `MFPlat!MFCreateAttributes` at `0x18006b26f`
- `MFPlat!MFCreateAttributes` at `0x18006b26f`

## pseudocode

```c
__int64 __fastcall FSClientContext::GetNetworkCamAtribs(
        FSClientContext *this,
        struct IMFAttributes *a2,
        struct IMFAttributes **a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  struct IMFAttributesVtbl *lpVtbl; // rax
  LPVOID v9; // rcx
  HRESULT v10; // eax
  __int64 v11; // rdx
  HRESULT v12; // eax
  __int64 v13; // rdx
  struct IMFAttributesVtbl *v14; // rax
  struct IMFAttributesVtbl *v15; // rax
  struct IMFAttributesVtbl *v16; // rax
  __int64 v17; // rax
  unsigned int v18; // ebx
  __int64 v19; // rax
  unsigned int v20; // ebx
  __int64 v21; // rax
  unsigned int v22; // ebx
  __int64 v23; // rax
  unsigned int v24; // ebx
  __int64 v25; // rax
  unsigned int v26; // ebx
  __int64 v27; // rax
  unsigned int v28; // ebx
  IMFAttributes *v29; // rdi
  HRESULT (__stdcall *SetUINT32)(IMFAttributes *, const GUID *const, UINT32); // rbx
  unsigned int v31; // eax
  void **v33; // [rsp+30h] [rbp-39h] BYREF
  __int64 v34; // [rsp+38h] [rbp-31h] BYREF
  char v35; // [rsp+40h] [rbp-29h]
  LPVOID ppv; // [rsp+48h] [rbp-21h] BYREF
  void *v37; // [rsp+50h] [rbp-19h] BYREF
  void *v38; // [rsp+58h] [rbp-11h] BYREF
  void *v39; // [rsp+60h] [rbp-9h] BYREF
  void *v40; // [rsp+68h] [rbp-1h] BYREF
  void *v41; // [rsp+70h] [rbp+7h] BYREF
  void *v42; // [rsp+78h] [rbp+Fh] BYREF
  void *v43; // [rsp+80h] [rbp+17h] BYREF
  void *v44; // [rsp+88h] [rbp+1Fh] BYREF
  void *v45; // [rsp+90h] [rbp+27h] BYREF
  void *v46; // [rsp+98h] [rbp+2Fh] BYREF
  int v47; // [rsp+D8h] [rbp+6Fh] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+E8h] [rbp+7Fh] BYREF

  v37 = 0;
  v46 = 0;
  v45 = 0;
  v44 = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  v38 = 0;
  ppv = 0;
  v47 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( g_wppLevels )
    {
      v7 = 39;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, this, v6);
      goto LABEL_62;
    }
    goto LABEL_62;
  }
  if ( a3 )
  {
    *a3 = 0;
    v33 = &v37;
    lpVtbl = a2->lpVtbl;
    v34 = 0;
    v35 = 1;
    v6 = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, __int64 *, int *))lpVtbl->GetAllocatedString)(
           a2,
           MF_SOURCE_AepId,
           &v34,
           &v47);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
    if ( v6 < 0 )
    {
      if ( g_wppLevels )
      {
        v7 = 41;
        goto LABEL_4;
      }
      goto LABEL_62;
    }
    v9 = ppv;
    ppv = 0;
    if ( v9 )
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    v10 = CoCreateInstance(&CLSID_NetworkCameraMetadata, 0, 1u, &GUID_4dab71dc_ad96_460b_a556_b30d52c6c4e3, &ppv);
    v6 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_62;
      v11 = 42;
      goto LABEL_17;
    }
    if ( (unsigned int)MFGetAttributeUINT32(a2, MF_SOURCE_RemoveAuth, 0) == 1 )
    {
      v10 = (*(__int64 (__fastcall **)(LPVOID, void *))(*(_QWORD *)ppv + 88LL))(ppv, v37);
      v6 = v10;
      if ( v10 >= 0 || !g_wppLevels )
        goto LABEL_62;
      v11 = 43;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, this, v10);
      goto LABEL_62;
    }
    ppMFAttributes = 0;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v12 = MFCreateAttributes(&ppMFAttributes, 6u);
    v6 = v12;
    if ( v12 >= 0 )
    {
      v34 = 0;
      v33 = &v46;
      v14 = a2->lpVtbl;
      v35 = 1;
      v6 = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, __int64 *, int *))v14->GetAllocatedString)(
             a2,
             MF_SOURCE_XAddress,
             &v34,
             &v47);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
      if ( v6 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, this, v6);
        goto LABEL_61;
      }
      v34 = 0;
      v33 = &v45;
      v15 = a2->lpVtbl;
      v35 = 1;
      ((void (__fastcall *)(struct IMFAttributes *, __int64 *, __int64 *, int *))v15->GetAllocatedString)(
        a2,
        MF_SOURCE_Username,
        &v34,
        &v47);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
      v34 = 0;
      v33 = &v44;
      v16 = a2->lpVtbl;
      v35 = 1;
      ((void (__fastcall *)(struct IMFAttributes *, __int64 *, __int64 *, int *))v16->GetAllocatedString)(
        a2,
        MF_SOURCE_Password,
        &v34,
        &v47);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
      v12 = (*(__int64 (__fastcall **)(LPVOID, void *, void *, void *, void *))(*(_QWORD *)ppv + 24LL))(
              ppv,
              v37,
              v46,
              v45,
              v44);
      v6 = v12;
      if ( v12 >= 0 )
      {
        v17 = *(_QWORD *)ppv;
        v33 = &v38;
        v34 = 0;
        v35 = 1;
        v18 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(v17 + 32))(ppv, &v34) >> 31;
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
        if ( (unsigned __int8)v18 != 1
          && (v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *))ppMFAttributes->lpVtbl->SetString)(
                      ppMFAttributes,
                      MF_SOURCE_HostName,
                      v38),
              v6 = v12,
              v12 < 0) )
        {
          if ( g_wppLevels )
          {
            v13 = 47;
            goto LABEL_25;
          }
        }
        else
        {
          v19 = *(_QWORD *)ppv;
          v33 = &v43;
          v34 = 0;
          v35 = 1;
          v20 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(v19 + 40))(ppv, &v34) >> 31;
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
          if ( (unsigned __int8)v20 != 1
            && (v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *))ppMFAttributes->lpVtbl->SetString)(
                        ppMFAttributes,
                        MF_SOURCE_SerialNum,
                        v43),
                v6 = v12,
                v12 < 0) )
          {
            if ( g_wppLevels )
            {
              v13 = 48;
              goto LABEL_25;
            }
          }
          else
          {
            v21 = *(_QWORD *)ppv;
            v33 = &v42;
            v34 = 0;
            v35 = 1;
            v22 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(v21 + 48))(ppv, &v34) >> 31;
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
            if ( (unsigned __int8)v22 != 1
              && (v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *))ppMFAttributes->lpVtbl->SetString)(
                          ppMFAttributes,
                          MF_SOURCE_Manufacturer,
                          v42),
                  v6 = v12,
                  v12 < 0) )
            {
              if ( g_wppLevels )
              {
                v13 = 49;
                goto LABEL_25;
              }
            }
            else
            {
              v23 = *(_QWORD *)ppv;
              v33 = &v41;
              v34 = 0;
              v35 = 1;
              v24 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(v23 + 56))(ppv, &v34) >> 31;
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
              if ( (unsigned __int8)v24 != 1
                && (v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *))ppMFAttributes->lpVtbl->SetString)(
                            ppMFAttributes,
                            MF_SOURCE_Model,
                            v41),
                    v6 = v12,
                    v12 < 0) )
              {
                if ( g_wppLevels )
                {
                  v13 = 50;
                  goto LABEL_25;
                }
              }
              else
              {
                v25 = *(_QWORD *)ppv;
                v33 = &v40;
                v34 = 0;
                v35 = 1;
                v26 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(v25 + 64))(ppv, &v34) >> 31;
                wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
                if ( (unsigned __int8)v26 != 1
                  && (v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *))ppMFAttributes->lpVtbl->SetString)(
                              ppMFAttributes,
                              MF_SOURCE_Firmware,
                              v40),
                      v6 = v12,
                      v12 < 0) )
                {
                  if ( g_wppLevels )
                  {
                    v13 = 51;
                    goto LABEL_25;
                  }
                }
                else
                {
                  v27 = *(_QWORD *)ppv;
                  v33 = &v39;
                  v34 = 0;
                  v35 = 1;
                  v28 = (*(unsigned int (__fastcall **)(LPVOID, __int64 *))(v27 + 72))(ppv, &v34) >> 31;
                  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&v33);
                  if ( (unsigned __int8)v28 != 1
                    && (v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void *))ppMFAttributes->lpVtbl->SetString)(
                                ppMFAttributes,
                                MF_SOURCE_HwId,
                                v39),
                        v6 = v12,
                        v12 < 0) )
                  {
                    if ( g_wppLevels )
                    {
                      v13 = 52;
                      goto LABEL_25;
                    }
                  }
                  else
                  {
                    v29 = ppMFAttributes;
                    SetUINT32 = ppMFAttributes->lpVtbl->SetUINT32;
                    v31 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 80LL))(ppv);
                    v12 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, _QWORD))SetUINT32)(
                            v29,
                            MF_SOURCE_RequiresAuth,
                            v31);
                    v6 = v12;
                    if ( v12 >= 0 )
                    {
                      *a3 = ppMFAttributes;
                      ppMFAttributes = 0;
                    }
                    else if ( g_wppLevels )
                    {
                      v13 = 53;
                      goto LABEL_25;
                    }
                  }
                }
              }
            }
          }
        }
      }
      else if ( g_wppLevels )
      {
        v13 = 46;
        goto LABEL_25;
      }
    }
    else if ( g_wppLevels )
    {
      v13 = 44;
LABEL_25:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, this, v12);
    }
LABEL_61:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
    goto LABEL_62;
  }
  v6 = -2147467261;
  if ( g_wppLevels )
  {
    v7 = 40;
    goto LABEL_4;
  }
LABEL_62:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&ppv);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v38);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v39);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v40);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v41);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v42);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v43);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v44);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v45);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v46);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v37);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18006b09c  mov     [rsp-8+arg_0], rbx
0x18006b0a1  mov     [rsp-8+arg_10], rsi
0x18006b0a6  push    rbp
0x18006b0a7  push    rdi
0x18006b0a8  push    r12
0x18006b0aa  push    r14
0x18006b0ac  push    r15
0x18006b0ae  lea     rbp, [rsp-37h]
0x18006b0b3  sub     rsp, 0A0h
0x18006b0ba  xor     r12d, r12d
0x18006b0bd  mov     r15, r8
0x18006b0c0  mov     [rbp+57h+var_70], r12
0x18006b0c4  mov     rdi, rdx
0x18006b0c7  mov     [rbp+57h+var_28], r12
0x18006b0cb  mov     r14, rcx
0x18006b0ce  mov     [rbp+57h+var_30], r12
0x18006b0d2  mov     [rbp+57h+var_38], r12
0x18006b0d6  mov     [rbp+57h+var_40], r12
0x18006b0da  mov     [rbp+57h+var_48], r12
0x18006b0de  mov     [rbp+57h+var_50], r12
0x18006b0e2  mov     [rbp+57h+var_58], r12
0x18006b0e6  mov     [rbp+57h+var_60], r12
0x18006b0ea  mov     [rbp+57h+var_68], r12
0x18006b0ee  mov     [rbp+57h+var_78], r12
0x18006b0f2  mov     [rbp+57h+arg_8], r12d
0x18006b0f6  test    rdx, rdx
0x18006b0f9  jnz     short loc_18006B136
0x18006b0fb  mov     ebx, 80070057h
0x18006b100  lea     esi, [rdx+1]
0x18006b103  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b10a  jb      loc_18006B6C2
0x18006b110  lea     edx, [rdi+27h]
0x18006b113  mov     dword ptr [rsp+0C0h+ppv], ebx
0x18006b117  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b11e  lea     r8, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x18006b125  mov     r9, r14
0x18006b128  mov     rcx, [rcx+10h]
0x18006b12c  call    WPP_SF_qD
0x18006b131  jmp     loc_18006B6C2
0x18006b136  test    r15, r15
0x18006b139  jnz     short loc_18006B156
0x18006b13b  mov     ebx, 80004003h
0x18006b140  lea     esi, [r15+1]
0x18006b144  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b14b  jb      loc_18006B6C2
0x18006b151  lea     edx, [rsi+27h]
0x18006b154  jmp     short loc_18006B113
0x18006b156  mov     [r8], r12
0x18006b159  lea     rax, [rbp+57h+var_70]
0x18006b15d  mov     [rbp+57h+var_90], rax
0x18006b161  lea     r9, [rbp+57h+arg_8]
0x18006b165  mov     rax, [rdx]
0x18006b168  lea     r8, [rbp+57h+var_88]
0x18006b16c  mov     esi, 1
0x18006b171  mov     [rbp+57h+var_88], r12
0x18006b175  lea     rdx, MF_SOURCE_AepId
0x18006b17c  mov     [rbp+57h+var_80], sil
0x18006b180  mov     rcx, rdi
0x18006b183  mov     rax, [rax+68h]
0x18006b187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b18c  lea     rcx, [rbp+57h+var_90]
0x18006b190  mov     ebx, eax
0x18006b192  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b197  mov     eax, ebx
0x18006b199  shr     eax, 1Fh
0x18006b19c  test    al, al
0x18006b19e  jz      short loc_18006B1B5
0x18006b1a0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b1a7  jb      loc_18006B6C2
0x18006b1ad  lea     edx, [rsi+28h]
0x18006b1b0  jmp     loc_18006B113
0x18006b1b5  mov     rcx, [rbp+57h+var_78]
0x18006b1b9  mov     [rbp+57h+var_78], r12
0x18006b1bd  test    rcx, rcx
0x18006b1c0  jz      short loc_18006B1CE
0x18006b1c2  mov     rax, [rcx]
0x18006b1c5  mov     rax, [rax+10h]
0x18006b1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b1ce  lea     rax, [rbp+57h+var_78]
0x18006b1d2  mov     r8d, esi; dwClsContext
0x18006b1d5  lea     r9, _GUID_4dab71dc_ad96_460b_a556_b30d52c6c4e3; riid
0x18006b1dc  mov     [rsp+0C0h+ppv], rax; ppv
0x18006b1e1  xor     edx, edx; pUnkOuter
0x18006b1e3  lea     rcx, CLSID_NetworkCameraMetadata; rclsid
0x18006b1ea  call    cs:__imp_CoCreateInstance
0x18006b1f0  mov     ebx, eax
0x18006b1f2  test    eax, eax
0x18006b1f4  jns     short loc_18006B211
0x18006b1f6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b1fd  jb      loc_18006B6C2
0x18006b203  mov     edx, 2Ah ; '*'
0x18006b208  mov     dword ptr [rsp+0C0h+ppv], eax
0x18006b20c  jmp     loc_18006B117
0x18006b211  xor     r8d, r8d
0x18006b214  lea     rdx, MF_SOURCE_RemoveAuth
0x18006b21b  mov     rcx, rdi
0x18006b21e  call    MFGetAttributeUINT32
0x18006b223  cmp     eax, esi
0x18006b225  jnz     short loc_18006B259
0x18006b227  mov     rcx, [rbp+57h+var_78]
0x18006b22b  mov     rdx, [rbp+57h+var_70]
0x18006b22f  mov     rax, [rcx]
0x18006b232  mov     rax, [rax+58h]
0x18006b236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b23b  mov     ebx, eax
0x18006b23d  test    eax, eax
0x18006b23f  jns     loc_18006B6C2
0x18006b245  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b24c  jb      loc_18006B6C2
0x18006b252  mov     edx, 2Bh ; '+'
0x18006b257  jmp     short loc_18006B208
0x18006b259  lea     rcx, [rbp+57h+ppMFAttributes]
0x18006b25d  mov     [rbp+57h+ppMFAttributes], r12
0x18006b261  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18006b266  mov     edx, 6; cInitialSize
0x18006b26b  lea     rcx, [rbp+57h+ppMFAttributes]; ppMFAttributes
0x18006b26f  call    cs:__imp_MFCreateAttributes
0x18006b275  mov     ebx, eax
0x18006b277  test    eax, eax
0x18006b279  jns     short loc_18006B2B0
0x18006b27b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b282  jb      loc_18006B6B9
0x18006b288  mov     edx, 2Ch ; ','
0x18006b28d  mov     dword ptr [rsp+0C0h+ppv], eax
0x18006b291  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b298  lea     r8, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x18006b29f  mov     r9, r14
0x18006b2a2  mov     rcx, [rcx+10h]
0x18006b2a6  call    WPP_SF_qD
0x18006b2ab  jmp     loc_18006B6B9
0x18006b2b0  lea     rax, [rbp+57h+var_28]
0x18006b2b4  mov     [rbp+57h+var_88], r12
0x18006b2b8  mov     [rbp+57h+var_90], rax
0x18006b2bc  lea     r9, [rbp+57h+arg_8]
0x18006b2c0  mov     rax, [rdi]
0x18006b2c3  lea     r8, [rbp+57h+var_88]
0x18006b2c7  lea     rdx, MF_SOURCE_XAddress
0x18006b2ce  mov     [rbp+57h+var_80], sil
0x18006b2d2  mov     rcx, rdi
0x18006b2d5  mov     rax, [rax+68h]
0x18006b2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b2de  lea     rcx, [rbp+57h+var_90]
0x18006b2e2  mov     ebx, eax
0x18006b2e4  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b2e9  mov     eax, ebx
0x18006b2eb  shr     eax, 1Fh
0x18006b2ee  test    al, al
0x18006b2f0  jz      short loc_18006B30A
0x18006b2f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b2f9  jb      loc_18006B6B9
0x18006b2ff  mov     edx, 2Dh ; '-'
0x18006b304  mov     dword ptr [rsp+0C0h+ppv], ebx
0x18006b308  jmp     short loc_18006B291
0x18006b30a  lea     rax, [rbp+57h+var_30]
0x18006b30e  mov     [rbp+57h+var_88], r12
0x18006b312  mov     [rbp+57h+var_90], rax
0x18006b316  lea     r9, [rbp+57h+arg_8]
0x18006b31a  mov     rax, [rdi]
0x18006b31d  lea     r8, [rbp+57h+var_88]
0x18006b321  lea     rdx, MF_SOURCE_Username
0x18006b328  mov     [rbp+57h+var_80], sil
0x18006b32c  mov     rcx, rdi
0x18006b32f  mov     rax, [rax+68h]
0x18006b333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b338  lea     rcx, [rbp+57h+var_90]
0x18006b33c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b341  lea     rax, [rbp+57h+var_38]
0x18006b345  mov     [rbp+57h+var_88], r12
0x18006b349  mov     [rbp+57h+var_90], rax
0x18006b34d  lea     r9, [rbp+57h+arg_8]
0x18006b351  mov     rax, [rdi]
0x18006b354  lea     r8, [rbp+57h+var_88]
0x18006b358  lea     rdx, MF_SOURCE_Password
0x18006b35f  mov     [rbp+57h+var_80], sil
0x18006b363  mov     rcx, rdi
0x18006b366  mov     rax, [rax+68h]
0x18006b36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b36f  lea     rcx, [rbp+57h+var_90]
0x18006b373  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b378  mov     rcx, [rbp+57h+var_78]
0x18006b37c  mov     r10, [rbp+57h+var_38]
0x18006b380  mov     r9, [rbp+57h+var_30]
0x18006b384  mov     r8, [rbp+57h+var_28]
0x18006b388  mov     rax, [rcx]
0x18006b38b  mov     rdx, [rbp+57h+var_70]
0x18006b38f  mov     [rsp+0C0h+ppv], r10
0x18006b394  mov     rax, [rax+18h]
0x18006b398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b39d  mov     ebx, eax
0x18006b39f  test    eax, eax
0x18006b3a1  jns     short loc_18006B3BA
0x18006b3a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b3aa  jb      loc_18006B6B9
0x18006b3b0  mov     edx, 2Eh ; '.'
0x18006b3b5  jmp     loc_18006B28D
0x18006b3ba  mov     rcx, [rbp+57h+var_78]
0x18006b3be  lea     rdx, [rbp+57h+var_68]
0x18006b3c2  mov     rax, [rcx]
0x18006b3c5  mov     [rbp+57h+var_90], rdx
0x18006b3c9  lea     rdx, [rbp+57h+var_88]
0x18006b3cd  mov     [rbp+57h+var_88], r12
0x18006b3d1  mov     [rbp+57h+var_80], sil
0x18006b3d5  mov     rax, [rax+20h]
0x18006b3d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b3de  mov     ebx, eax
0x18006b3e0  lea     rcx, [rbp+57h+var_90]
0x18006b3e4  shr     ebx, 1Fh
0x18006b3e7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b3ec  xor     bl, sil
0x18006b3ef  jz      short loc_18006B42C
0x18006b3f1  mov     rcx, [rbp+57h+ppMFAttributes]
0x18006b3f5  lea     rdx, MF_SOURCE_HostName
0x18006b3fc  mov     r8, [rbp+57h+var_68]
0x18006b400  mov     rax, [rcx]
0x18006b403  mov     rax, [rax+0C8h]
0x18006b40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b40f  mov     ebx, eax
0x18006b411  test    eax, eax
0x18006b413  jns     short loc_18006B42C
0x18006b415  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b41c  jb      loc_18006B6B9
0x18006b422  mov     edx, 2Fh ; '/'
0x18006b427  jmp     loc_18006B28D
0x18006b42c  mov     rcx, [rbp+57h+var_78]
0x18006b430  lea     rdx, [rbp+57h+var_40]
0x18006b434  mov     rax, [rcx]
0x18006b437  mov     [rbp+57h+var_90], rdx
0x18006b43b  lea     rdx, [rbp+57h+var_88]
0x18006b43f  mov     [rbp+57h+var_88], r12
0x18006b443  mov     [rbp+57h+var_80], sil
0x18006b447  mov     rax, [rax+28h]
0x18006b44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b450  mov     ebx, eax
0x18006b452  lea     rcx, [rbp+57h+var_90]
0x18006b456  shr     ebx, 1Fh
0x18006b459  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b45e  xor     bl, sil
0x18006b461  jz      short loc_18006B49E
0x18006b463  mov     rcx, [rbp+57h+ppMFAttributes]
0x18006b467  lea     rdx, MF_SOURCE_SerialNum
0x18006b46e  mov     r8, [rbp+57h+var_40]
0x18006b472  mov     rax, [rcx]
0x18006b475  mov     rax, [rax+0C8h]
0x18006b47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b481  mov     ebx, eax
0x18006b483  test    eax, eax
0x18006b485  jns     short loc_18006B49E
0x18006b487  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b48e  jb      loc_18006B6B9
0x18006b494  mov     edx, 30h ; '0'
0x18006b499  jmp     loc_18006B28D
0x18006b49e  mov     rcx, [rbp+57h+var_78]
0x18006b4a2  lea     rdx, [rbp+57h+var_48]
0x18006b4a6  mov     rax, [rcx]
0x18006b4a9  mov     [rbp+57h+var_90], rdx
0x18006b4ad  lea     rdx, [rbp+57h+var_88]
0x18006b4b1  mov     [rbp+57h+var_88], r12
0x18006b4b5  mov     [rbp+57h+var_80], sil
0x18006b4b9  mov     rax, [rax+30h]
0x18006b4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4c2  mov     ebx, eax
0x18006b4c4  lea     rcx, [rbp+57h+var_90]
0x18006b4c8  shr     ebx, 1Fh
0x18006b4cb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b4d0  xor     bl, sil
0x18006b4d3  jz      short loc_18006B510
0x18006b4d5  mov     rcx, [rbp+57h+ppMFAttributes]
0x18006b4d9  lea     rdx, MF_SOURCE_Manufacturer
0x18006b4e0  mov     r8, [rbp+57h+var_48]
0x18006b4e4  mov     rax, [rcx]
0x18006b4e7  mov     rax, [rax+0C8h]
0x18006b4ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b4f3  mov     ebx, eax
0x18006b4f5  test    eax, eax
0x18006b4f7  jns     short loc_18006B510
0x18006b4f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x18006b500  jb      loc_18006B6B9
0x18006b506  mov     edx, 31h ; '1'
0x18006b50b  jmp     loc_18006B28D
0x18006b510  mov     rcx, [rbp+57h+var_78]
0x18006b514  lea     rdx, [rbp+57h+var_50]
0x18006b518  mov     rax, [rcx]
0x18006b51b  mov     [rbp+57h+var_90], rdx
0x18006b51f  lea     rdx, [rbp+57h+var_88]
0x18006b523  mov     [rbp+57h+var_88], r12
0x18006b527  mov     [rbp+57h+var_80], sil
0x18006b52b  mov     rax, [rax+38h]
0x18006b52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b534  mov     ebx, eax
0x18006b536  lea     rcx, [rbp+57h+var_90]
0x18006b53a  shr     ebx, 1Fh
0x18006b53d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18006b542  xor     bl, sil
0x18006b545  jz      short loc_18006B582
0x18006b547  mov     rcx, [rbp+57h+ppMFAttributes]
0x18006b54b  lea     rdx, MF_SOURCE_Model
0x18006b552  mov     r8, [rbp+57h+var_50]
0x18006b556  mov     rax, [rcx]
0x18006b559  mov     rax, [rax+0C8h]
0x18006b560  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
