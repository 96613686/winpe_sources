# DeviceAccessHandler::InternalLoadDeviceConfiguration(IFSService *,ushort const *,ushort const *,ushort const *,IMFAttributes * *)

- ea: `0x18007e94c`
- end: `0x18007ef68`
- name: `?InternalLoadDeviceConfiguration@DeviceAccessHandler@@AEAAJPEAUIFSService@@PEBG11PEAPEAUIMFAttributes@@@Z`
- size: `1564`
- prototype: `__int64 __fastcall(DeviceAccessHandler *__hidden this, struct IFSService *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, struct IMFAttributes **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18007d914`

## callees

- `0x180003e20`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18002db74`
- `0x1800347e4`
- `0x1800351a8`
- `0x18007e94c`
- `0x18007ef70`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ea67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ea7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ecc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ed66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ed79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ed8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ea67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ea7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ecc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ed66`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ed79`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18007ed8c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007eb9d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007ed0f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007eb9d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18007ed0f`
- `MFPlat!MFCreateAttributes` at `0x18007ead4`
- `MFPlat!MFCreateAttributes` at `0x18007ee5f`
- `MFPlat!MFCreateAttributes` at `0x18007ef0d`
- `MFPlat!MFCreateAttributes` at `0x18007ead4`
- `MFPlat!MFCreateAttributes` at `0x18007ee5f`
- `MFPlat!MFCreateAttributes` at `0x18007ef0d`

## pseudocode

```c
__int64 __fastcall DeviceAccessHandler::InternalLoadDeviceConfiguration(
        DeviceAccessHandler *this,
        struct IFSService *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        struct IMFAttributes **a6)
{
  HRESULT v10; // eax
  int v11; // ebx
  __int64 v12; // rdx
  void *v13; // rcx
  void *v14; // rcx
  UINT32 v15; // ebx
  unsigned int v16; // edi
  int v17; // eax
  struct IMFAttributesVtbl *lpVtbl; // rax
  __int64 v19; // rax
  void *v20; // rcx
  __int64 v21; // rdx
  int v22; // eax
  void *v23; // rcx
  void *v24; // rcx
  void *v25; // rcx
  HRESULT v27; // eax
  __int64 v28; // rdx
  UINT32 v29; // ebx
  UINT32 v30; // ebx
  LPVOID pv; // [rsp+30h] [rbp-79h] BYREF
  LPVOID v32; // [rsp+38h] [rbp-71h] BYREF
  UINT32 cInitialSize; // [rsp+40h] [rbp-69h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-61h] BYREF
  unsigned int v35; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v36; // [rsp+58h] [rbp-51h] BYREF
  struct IMFAttributes *v37; // [rsp+60h] [rbp-49h] BYREF
  PROPVARIANT pvar[2]; // [rsp+68h] [rbp-41h] BYREF
  __int64 v39; // [rsp+78h] [rbp-31h]
  unsigned int v40; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v41; // [rsp+84h] [rbp-25h] BYREF
  unsigned int v42; // [rsp+88h] [rbp-21h] BYREF
  LPVOID v43[2]; // [rsp+90h] [rbp-19h] BYREF

  v37 = 0;
  v36 = 0;
  *a6 = 0;
  ppMFAttributes = 0;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v37);
  DeviceAccessHandler::InternalLoadDeviceConfiguration_CameraStudioEffects_Enabled(this, a2, a3, a4, a5, &v37);
  if ( !*((_BYTE *)this + 292) )
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v36);
    FSLoadGlobalConfigurationByName(a3);
  }
  if ( !v37 )
  {
    v11 = 0;
    if ( !v36 )
      goto LABEL_49;
    cInitialSize = 0;
    v27 = (*(__int64 (__fastcall **)(__int64 *, UINT32 *))(*v36 + 240))(v36, &cInitialSize);
    v11 = v27;
    if ( v27 >= 0 )
    {
      v30 = cInitialSize;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v27 = MFCreateAttributes(&ppMFAttributes, v30);
      v11 = v27;
      if ( v27 >= 0 )
      {
        v27 = (*(__int64 (__fastcall **)(__int64 *, IMFAttributes *))(*v36 + 256))(v36, ppMFAttributes);
        v11 = v27;
        if ( v27 >= 0 )
          goto LABEL_49;
        if ( !g_wppLevels )
          goto LABEL_50;
        v28 = 109;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_50;
        v28 = 108;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v28 = 107;
    }
    goto LABEL_56;
  }
  if ( !v36 )
  {
    cInitialSize = 0;
    v27 = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))v37->lpVtbl->GetCount)(v37, &cInitialSize);
    v11 = v27;
    if ( v27 >= 0 )
    {
      v29 = cInitialSize;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
      v27 = MFCreateAttributes(&ppMFAttributes, v29);
      v11 = v27;
      if ( v27 >= 0 )
      {
        v27 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))v37->lpVtbl->CopyAllItems)(
                v37,
                ppMFAttributes);
        v11 = v27;
        if ( v27 >= 0 )
          goto LABEL_49;
        if ( !g_wppLevels )
          goto LABEL_50;
        v28 = 106;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_50;
        v28 = 105;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_50;
      v28 = 104;
    }
LABEL_56:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v27);
    goto LABEL_50;
  }
  v40 = 0;
  v35 = 0;
  v32 = 0;
  v42 = 0;
  pv = 0;
  v41 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v36 + 240))(v36, &v40);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v10 = ((__int64 (__fastcall *)(struct IMFAttributes *, unsigned int *))v37->lpVtbl->GetCount)(v37, &v35);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_9;
      v12 = 96;
      goto LABEL_8;
    }
    v15 = v40 + v35;
    if ( v40 + v35 < v40 )
    {
      v11 = -2147024362;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          97,
          &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
          this,
          -2147024362);
      goto LABEL_9;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
    v10 = MFCreateAttributes(&ppMFAttributes, v15);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_9;
      v12 = 98;
      goto LABEL_8;
    }
    v10 = (*(__int64 (__fastcall **)(__int64 *, IMFAttributes *))(*v36 + 256))(v36, ppMFAttributes);
    v11 = v10;
    if ( v10 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_9;
      v12 = 99;
      goto LABEL_8;
    }
    v16 = 0;
    if ( v35 )
    {
      while ( 1 )
      {
        v39 = 0;
        *(_OWORD *)pvar = 0;
        *(GUID *)v43 = GUID_00000000_0000_0000_0000_000000000000;
        v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, _QWORD, LPVOID *, PROPVARIANT *))v37->lpVtbl->GetItemByIndex)(
                v37,
                v16,
                v43,
                pvar);
        v11 = v17;
        if ( v17 < 0 )
          break;
        v17 = ((__int64 (__fastcall *)(IMFAttributes *, LPVOID *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                ppMFAttributes,
                v43,
                pvar);
        v11 = v17;
        if ( v17 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_39;
          v21 = 101;
          goto LABEL_38;
        }
        PropVariantClear(pvar);
        if ( ++v16 >= v35 )
          goto LABEL_27;
      }
      if ( !g_wppLevels )
        goto LABEL_39;
      v21 = 100;
LABEL_38:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v17);
LABEL_39:
      PropVariantClear(pvar);
      goto LABEL_9;
    }
LABEL_27:
    lpVtbl = v37->lpVtbl;
    pvar[0] = &v32;
    pvar[1] = 0;
    LOBYTE(v39) = 1;
    ((void (__fastcall *)(struct IMFAttributes *, void *, PROPVARIANT *, unsigned int *))lpVtbl->GetAllocatedBlob)(
      v37,
      &FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
      &pvar[1],
      &v42);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvar);
    v19 = *v36;
    pvar[0] = &pv;
    pvar[1] = 0;
    LOBYTE(v39) = 1;
    (*(void (__fastcall **)(__int64 *, void *, PROPVARIANT *, unsigned int *))(v19 + 128))(
      v36,
      &FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
      &pvar[1],
      &v41);
    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvar);
    if ( v32 && pv )
    {
      pvar[0] = v43;
      v43[0] = 0;
      cInitialSize = 0;
      pvar[1] = 0;
      LOBYTE(v39) = 1;
      v11 = FSMergeConfigurationBlob((__int64)v32, v42, (__int64)pv, v41, &pvar[1], &cInitialSize);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(pvar);
      if ( v11 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            102,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v11);
LABEL_32:
        v20 = v43[0];
        v43[0] = 0;
        if ( v20 )
          CoTaskMemFree(v20);
        goto LABEL_9;
      }
      v22 = ((__int64 (__fastcall *)(IMFAttributes *, void *, LPVOID, _QWORD))ppMFAttributes->lpVtbl->SetBlob)(
              ppMFAttributes,
              &FRAMESERVER_DEVICECONFIGURATION_ENTRIES,
              v43[0],
              cInitialSize);
      v11 = v22;
      if ( v22 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            103,
            &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids,
            this,
            v22);
        goto LABEL_32;
      }
      v23 = v43[0];
      v43[0] = 0;
      if ( v23 )
        CoTaskMemFree(v23);
    }
    v24 = pv;
    pv = 0;
    if ( v24 )
      CoTaskMemFree(v24);
    v25 = v32;
    v32 = 0;
    if ( v25 )
      CoTaskMemFree(v25);
LABEL_49:
    *a6 = ppMFAttributes;
    ppMFAttributes = 0;
    goto LABEL_50;
  }
  if ( g_wppLevels )
  {
    v12 = 95;
LABEL_8:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v12, &WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids, this, v10);
  }
LABEL_9:
  v13 = pv;
  pv = 0;
  if ( v13 )
    CoTaskMemFree(v13);
  v14 = v32;
  v32 = 0;
  if ( v14 )
    CoTaskMemFree(v14);
LABEL_50:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v36);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v37);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18007e94c  push    rbp
0x18007e94e  push    rbx
0x18007e94f  push    rsi
0x18007e950  push    rdi
0x18007e951  push    r12
0x18007e953  push    r13
0x18007e955  push    r14
0x18007e957  push    r15
0x18007e959  lea     rbp, [rsp-0Fh]
0x18007e95e  sub     rsp, 0B8h
0x18007e965  mov     rax, cs:__security_cookie
0x18007e96c  xor     rax, rsp
0x18007e96f  mov     [rbp+47h+var_50], rax
0x18007e973  mov     r12, [rbp+47h+arg_28]
0x18007e977  xor     r13d, r13d
0x18007e97a  mov     rbx, [rbp+47h+arg_20]
0x18007e97e  mov     r14, rcx
0x18007e981  lea     rcx, [rbp+47h+var_90]
0x18007e985  mov     [rbp+47h+var_90], r13
0x18007e989  mov     rsi, r9
0x18007e98c  mov     [rbp+47h+var_98], r13
0x18007e990  mov     [r12], r13
0x18007e994  mov     r15, r8
0x18007e997  mov     rdi, rdx
0x18007e99a  mov     [rbp+47h+ppMFAttributes], r13
0x18007e99e  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007e9a3  lea     rax, [rbp+47h+var_90]
0x18007e9a7  mov     r9, rsi; unsigned __int16 *
0x18007e9aa  mov     [rsp+0F0h+var_C8], rax; struct IMFAttributes **
0x18007e9af  mov     r8, r15; unsigned __int16 *
0x18007e9b2  mov     rdx, rdi; struct IFSService *
0x18007e9b5  mov     [rsp+0F0h+var_D0], rbx; unsigned __int16 *
0x18007e9ba  mov     rcx, r14; this
0x18007e9bd  call    ?InternalLoadDeviceConfiguration_CameraStudioEffects_Enabled@DeviceAccessHandler@@AEAAJPEAUIFSService@@PEBG11PEAPEAUIMFAttributes@@@Z; DeviceAccessHandler::InternalLoadDeviceConfiguration_CameraStudioEffects_Enabled(IFSService *,ushort const *,ushort const *,ushort const *,IMFAttributes * *)
0x18007e9c2  cmp     [r14+124h], r13b
0x18007e9c9  jnz     short loc_18007E9E0
0x18007e9cb  lea     rcx, [rbp+47h+var_98]
0x18007e9cf  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007e9d4  lea     r9, [rbp+47h+var_98]
0x18007e9d8  mov     rcx, r15; unsigned __int16 *
0x18007e9db  call    FSLoadGlobalConfigurationByName
0x18007e9e0  mov     rcx, [rbp+47h+var_90]
0x18007e9e4  test    rcx, rcx
0x18007e9e7  jz      loc_18007EEB7
0x18007e9ed  mov     r8, [rbp+47h+var_98]
0x18007e9f1  test    r8, r8
0x18007e9f4  jz      loc_18007EDFB
0x18007e9fa  mov     [rbp+47h+var_70], r13d
0x18007e9fe  lea     rdx, [rbp+47h+var_70]
0x18007ea02  mov     [rbp+47h+var_A0], r13d
0x18007ea06  mov     rcx, r8
0x18007ea09  mov     [rbp+47h+var_B8], r13
0x18007ea0d  mov     [rbp+47h+var_68], r13d
0x18007ea11  mov     [rbp+47h+pv], r13
0x18007ea15  mov     [rbp+47h+var_6C], r13d
0x18007ea19  mov     rax, [r8]
0x18007ea1c  mov     rax, [rax+0F0h]
0x18007ea23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ea28  mov     ebx, eax
0x18007ea2a  test    eax, eax
0x18007ea2c  jns     short loc_18007EA89
0x18007ea2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ea35  jb      short loc_18007EA5A
0x18007ea37  mov     edx, 5Fh ; '_'
0x18007ea3c  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18007ea40  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ea47  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007ea4e  mov     r9, r14
0x18007ea51  mov     rcx, [rcx+10h]
0x18007ea55  call    WPP_SF_qD
0x18007ea5a  mov     rcx, [rbp+47h+pv]; pv
0x18007ea5e  mov     [rbp+47h+pv], r13
0x18007ea62  test    rcx, rcx
0x18007ea65  jz      short loc_18007EA6D
0x18007ea67  call    cs:__imp_CoTaskMemFree
0x18007ea6d  mov     rcx, [rbp+47h+var_B8]; pv
0x18007ea71  mov     [rbp+47h+var_B8], r13
0x18007ea75  test    rcx, rcx
0x18007ea78  jz      loc_18007ED9E
0x18007ea7e  call    cs:__imp_CoTaskMemFree
0x18007ea84  jmp     loc_18007ED9E
0x18007ea89  mov     rcx, [rbp+47h+var_90]
0x18007ea8d  lea     rdx, [rbp+47h+var_A0]
0x18007ea91  mov     rax, [rcx]
0x18007ea94  mov     rax, [rax+0F0h]
0x18007ea9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eaa0  mov     ebx, eax
0x18007eaa2  test    eax, eax
0x18007eaa4  jns     short loc_18007EAB6
0x18007eaa6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007eaad  jb      short loc_18007EA5A
0x18007eaaf  mov     edx, 60h ; '`'
0x18007eab4  jmp     short loc_18007EA3C
0x18007eab6  mov     ebx, [rbp+47h+var_A0]
0x18007eab9  add     ebx, [rbp+47h+var_70]
0x18007eabc  cmp     ebx, [rbp+47h+var_70]
0x18007eabf  jb      loc_18007EDDB
0x18007eac5  lea     rcx, [rbp+47h+ppMFAttributes]
0x18007eac9  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007eace  mov     edx, ebx; cInitialSize
0x18007ead0  lea     rcx, [rbp+47h+ppMFAttributes]; ppMFAttributes
0x18007ead4  call    cs:__imp_MFCreateAttributes
0x18007eada  mov     ebx, eax
0x18007eadc  test    eax, eax
0x18007eade  jns     short loc_18007EAF7
0x18007eae0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007eae7  jb      loc_18007EA5A
0x18007eaed  mov     edx, 62h ; 'b'
0x18007eaf2  jmp     loc_18007EA3C
0x18007eaf7  mov     rcx, [rbp+47h+var_98]
0x18007eafb  mov     rdx, [rbp+47h+ppMFAttributes]
0x18007eaff  mov     rax, [rcx]
0x18007eb02  mov     rax, [rax+100h]
0x18007eb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb0e  mov     ebx, eax
0x18007eb10  test    eax, eax
0x18007eb12  jns     short loc_18007EB2B
0x18007eb14  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007eb1b  jb      loc_18007EA5A
0x18007eb21  mov     edx, 63h ; 'c'
0x18007eb26  jmp     loc_18007EA3C
0x18007eb2b  mov     edi, r13d
0x18007eb2e  cmp     [rbp+47h+var_A0], r13d
0x18007eb32  jbe     short loc_18007EBAA
0x18007eb34  mov     rcx, [rbp+47h+var_90]
0x18007eb38  lea     r9, [rbp+47h+pvar]
0x18007eb3c  movaps  xmm1, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18007eb43  lea     r8, [rbp+47h+var_60]
0x18007eb47  xor     eax, eax
0x18007eb49  xorps   xmm0, xmm0
0x18007eb4c  mov     [rbp+47h+var_78], rax
0x18007eb50  mov     edx, edi
0x18007eb52  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18007eb56  movdqu  xmmword ptr [rbp+47h+var_60], xmm1
0x18007eb5b  mov     rax, [rcx]
0x18007eb5e  mov     rax, [rax+0F8h]
0x18007eb65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb6a  mov     ebx, eax
0x18007eb6c  test    eax, eax
0x18007eb6e  js      loc_18007ECDF
0x18007eb74  mov     rcx, [rbp+47h+ppMFAttributes]
0x18007eb78  lea     r8, [rbp+47h+pvar]
0x18007eb7c  lea     rdx, [rbp+47h+var_60]
0x18007eb80  mov     rax, [rcx]
0x18007eb83  mov     rax, [rax+90h]
0x18007eb8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007eb8f  mov     ebx, eax
0x18007eb91  test    eax, eax
0x18007eb93  js      loc_18007ECCF
0x18007eb99  lea     rcx, [rbp+47h+pvar]; pvar
0x18007eb9d  call    cs:__imp_PropVariantClear
0x18007eba3  inc     edi
0x18007eba5  cmp     edi, [rbp+47h+var_A0]
0x18007eba8  jb      short loc_18007EB34
0x18007ebaa  mov     rcx, [rbp+47h+var_90]
0x18007ebae  lea     rdx, [rbp+47h+var_B8]
0x18007ebb2  lea     rdi, FRAMESERVER_DEVICECONFIGURATION_ENTRIES
0x18007ebb9  lea     r9, [rbp+47h+var_68]
0x18007ebbd  lea     r8, [rbp+47h+pvar+8]
0x18007ebc1  mov     rax, [rcx]
0x18007ebc4  mov     [rbp+47h+pvar], rdx
0x18007ebc8  mov     rdx, rdi
0x18007ebcb  mov     [rbp+47h+pvar+8], r13
0x18007ebcf  mov     byte ptr [rbp+47h+var_78], 1
0x18007ebd3  mov     rax, [rax+80h]
0x18007ebda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ebdf  lea     rcx, [rbp+47h+pvar]
0x18007ebe3  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007ebe8  mov     rcx, [rbp+47h+var_98]
0x18007ebec  lea     rdx, [rbp+47h+pv]
0x18007ebf0  lea     r9, [rbp+47h+var_6C]
0x18007ebf4  lea     r8, [rbp+47h+pvar+8]
0x18007ebf8  mov     rax, [rcx]
0x18007ebfb  mov     [rbp+47h+pvar], rdx
0x18007ebff  mov     rdx, rdi
0x18007ec02  mov     [rbp+47h+pvar+8], r13
0x18007ec06  mov     byte ptr [rbp+47h+var_78], 1
0x18007ec0a  mov     rax, [rax+80h]
0x18007ec11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ec16  lea     rcx, [rbp+47h+pvar]
0x18007ec1a  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007ec1f  mov     rcx, [rbp+47h+var_B8]
0x18007ec23  test    rcx, rcx
0x18007ec26  jz      loc_18007ED6C
0x18007ec2c  mov     r8, [rbp+47h+pv]
0x18007ec30  test    r8, r8
0x18007ec33  jz      loc_18007ED6C
0x18007ec39  mov     r9d, [rbp+47h+var_6C]
0x18007ec3d  lea     rax, [rbp+47h+var_60]
0x18007ec41  mov     edx, [rbp+47h+var_68]
0x18007ec44  mov     [rbp+47h+pvar], rax
0x18007ec48  lea     rax, [rbp+47h+cInitialSize]
0x18007ec4c  mov     [rsp+0F0h+var_C8], rax
0x18007ec51  lea     rax, [rbp+47h+pvar+8]
0x18007ec55  mov     [rsp+0F0h+var_D0], rax
0x18007ec5a  mov     [rbp+47h+var_60], r13
0x18007ec5e  mov     [rbp+47h+cInitialSize], r13d
0x18007ec62  mov     [rbp+47h+pvar+8], r13
0x18007ec66  mov     byte ptr [rbp+47h+var_78], 1
0x18007ec6a  call    FSMergeConfigurationBlob
0x18007ec6f  lea     rcx, [rbp+47h+pvar]
0x18007ec73  mov     ebx, eax
0x18007ec75  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<uchar [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x18007ec7a  mov     eax, ebx
0x18007ec7c  shr     eax, 1Fh
0x18007ec7f  test    al, al
0x18007ec81  jz      loc_18007ED1A
0x18007ec87  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ec8e  jb      short loc_18007ECB3
0x18007ec90  mov     edx, 66h ; 'f'
0x18007ec95  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18007ec99  mov     rcx, cs:WPP_GLOBAL_Control
0x18007eca0  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007eca7  mov     r9, r14
0x18007ecaa  mov     rcx, [rcx+10h]
0x18007ecae  call    WPP_SF_qD
0x18007ecb3  mov     rcx, [rbp+47h+var_60]; pv
0x18007ecb7  mov     [rbp+47h+var_60], r13
0x18007ecbb  test    rcx, rcx
0x18007ecbe  jz      loc_18007EA5A
0x18007ecc4  call    cs:__imp_CoTaskMemFree
0x18007ecca  jmp     loc_18007EA5A
0x18007eccf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ecd6  jb      short loc_18007ED0B
0x18007ecd8  mov     edx, 65h ; 'e'
0x18007ecdd  jmp     short loc_18007ECED
0x18007ecdf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ece6  jb      short loc_18007ED0B
0x18007ece8  mov     edx, 64h ; 'd'
0x18007eced  mov     rcx, cs:WPP_GLOBAL_Control
0x18007ecf4  lea     r8, WPP_0624fae52b0938a3be09ac660a5d0b65_Traceguids
0x18007ecfb  mov     r9, r14
0x18007ecfe  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18007ed02  mov     rcx, [rcx+10h]
0x18007ed06  call    WPP_SF_qD
0x18007ed0b  lea     rcx, [rbp+47h+pvar]; pvar
0x18007ed0f  call    cs:__imp_PropVariantClear
0x18007ed15  jmp     loc_18007EA5A
0x18007ed1a  mov     rcx, [rbp+47h+ppMFAttributes]
0x18007ed1e  mov     rdx, rdi
0x18007ed21  mov     r9d, [rbp+47h+cInitialSize]
0x18007ed25  mov     r8, [rbp+47h+var_60]
0x18007ed29  mov     rax, [rcx]
0x18007ed2c  mov     rax, [rax+0D0h]
0x18007ed33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007ed38  mov     ebx, eax
0x18007ed3a  test    eax, eax
0x18007ed3c  jns     short loc_18007ED59
0x18007ed3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ed45  jb      loc_18007ECB3
0x18007ed4b  mov     edx, 67h ; 'g'
0x18007ed50  mov     dword ptr [rsp+0F0h+var_D0], eax
0x18007ed54  jmp     loc_18007EC99
0x18007ed59  mov     rcx, [rbp+47h+var_60]; pv
0x18007ed5d  mov     [rbp+47h+var_60], r13
0x18007ed61  test    rcx, rcx
0x18007ed64  jz      short loc_18007ED6C
0x18007ed66  call    cs:__imp_CoTaskMemFree
0x18007ed6c  mov     rcx, [rbp+47h+pv]; pv
0x18007ed70  mov     [rbp+47h+pv], r13
0x18007ed74  test    rcx, rcx
0x18007ed77  jz      short loc_18007ED7F
0x18007ed79  call    cs:__imp_CoTaskMemFree
0x18007ed7f  mov     rcx, [rbp+47h+var_B8]; pv
0x18007ed83  mov     [rbp+47h+var_B8], r13
0x18007ed87  test    rcx, rcx
0x18007ed8a  jz      short loc_18007ED92
0x18007ed8c  call    cs:__imp_CoTaskMemFree
0x18007ed92  mov     rax, [rbp+47h+ppMFAttributes]
0x18007ed96  mov     [r12], rax
0x18007ed9a  mov     [rbp+47h+ppMFAttributes], r13
0x18007ed9e  lea     rcx, [rbp+47h+ppMFAttributes]; void *
0x18007eda2  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007eda7  lea     rcx, [rbp+47h+var_98]; void *
0x18007edab  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007edb0  lea     rcx, [rbp+47h+var_90]; void *
0x18007edb4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007edb9  mov     eax, ebx
0x18007edbb  mov     rcx, [rbp+47h+var_50]
0x18007edbf  xor     rcx, rsp; StackCookie
0x18007edc2  call    __security_check_cookie
0x18007edc7  add     rsp, 0B8h
0x18007edce  pop     r15
0x18007edd0  pop     r14
0x18007edd2  pop     r13
0x18007edd4  pop     r12
0x18007edd6  pop     rdi
0x18007edd7  pop     rsi
0x18007edd8  pop     rbx
0x18007edd9  pop     rbp
0x18007edda  retn
0x18007eddb  mov     ebx, 80070216h
0x18007ede0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007ede7  jb      loc_18007EA5A
0x18007eded  mov     edx, 61h ; 'a'
0x18007edf2  mov     dword ptr [rsp+0F0h+var_D0], ebx
0x18007edf6  jmp     loc_18007EA40
0x18007edfb  mov     [rbp+47h+cInitialSize], r13d
0x18007edff  lea     rdx, [rbp+47h+cInitialSize]
0x18007ee03  mov     rax, [rcx]
  ... truncated ...
```
