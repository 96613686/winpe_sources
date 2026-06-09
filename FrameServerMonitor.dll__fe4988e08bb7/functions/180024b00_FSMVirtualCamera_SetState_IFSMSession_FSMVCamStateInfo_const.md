# FSMVirtualCamera::SetState(IFSMSession *,FSMVCamStateInfo const &)

- ea: `0x180024b00`
- end: `0x180025407`
- name: `?SetState@FSMVirtualCamera@@UEAAJPEAUIFSMSession@@AEBUFSMVCamStateInfo@@@Z`
- size: `2311`
- prototype: `__int64 __fastcall(FSMVirtualCamera *__hidden this, struct IFSMSession *, const struct FSMVCamStateInfo *)`
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003194`
- `0x1800056a8`
- `0x180005f98`
- `0x180006a98`
- `0x180006ae8`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18001ec2c`
- `0x18001f4dc`
- `0x18001f6a8`
- `0x180022110`
- `0x180022b18`
- `0x180022d3c`
- `0x180024b00`
- `0x180025b3c`
- `0x18002615c`
- `0x1800421fc`
- `0x180045e98`
- `0x18004633c`
- `0x18004bf50`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCleanupVirtualCameraEntries` at `0x18002534a`
- `MFSENSORGROUP!MFCleanupVirtualCameraEntries` at `0x18002534a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024bf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024d9b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024b27`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024bf2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024d9b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002511f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800252e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800253e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c3c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024c8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002511f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800252e7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800253e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800251ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180025116`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800251ca`
- `MFPlat!MFInitAttributesFromBlob` at `0x180024dcc`
- `MFPlat!MFInitAttributesFromBlob` at `0x180024dcc`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::SetState(
        FSMVirtualCamera *this,
        struct IFSMSession *a2,
        const struct FSMVCamStateInfo *a3)
{
  struct _RTL_CRITICAL_SECTION *v3; // r12
  int v7; // r8d
  char *v8; // r14
  unsigned int v9; // edi
  int v10; // eax
  const unsigned __int16 *v11; // rcx
  signed int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rax
  char v15; // al
  __int64 v16; // r8
  struct IFSMSessionIdentity *v17; // rcx
  __int64 (__fastcall *v18)(struct IFSMSession *, __int64, struct IFSMSessionIdentity **); // rdi
  int v19; // eax
  __int64 v20; // rdx
  struct IFSMSessionIdentity *v21; // rcx
  __int64 v22; // rax
  __int64 (__fastcall *v23)(struct IFSMSession *, __int64, struct IFSMSessionIdentity **); // rdi
  unsigned int v24; // edx
  bool v25; // r8
  const unsigned __int16 **v26; // r9
  const UINT8 *v27; // rdx
  HRESULT v28; // eax
  __int64 v29; // rdx
  const struct _GUID *v30; // rcx
  int FSMDeviceProperties; // eax
  __int64 v32; // rdx
  __int64 v33; // rdx
  void *v34; // rbx
  int updated; // eax
  __int64 v36; // rdx
  const struct std::nothrow_t *unique; // rax
  void *v38; // rcx
  void *v39; // rdx
  const struct std::nothrow_t *v40; // rax
  void *v41; // rcx
  unsigned int v42; // eax
  int v43; // eax
  void *v44; // rdx
  int v45; // edx
  void *v46; // rdx
  LPVOID pv; // [rsp+40h] [rbp-10h] BYREF
  __int64 v49; // [rsp+48h] [rbp-8h] BYREF
  struct IFSMCameraDeviceProperties *v50; // [rsp+90h] [rbp+40h] BYREF
  struct IFSMSessionIdentity *v51; // [rsp+98h] [rbp+48h] BYREF
  void *v52; // [rsp+A8h] [rbp+58h] BYREF

  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v8 = (char *)this - 40;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qddS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      23,
      v7,
      (_DWORD)this - 40,
      *((_DWORD *)this + 29),
      *(_DWORD *)a3,
      *((_QWORD *)v8 + 42));
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        24,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        (char *)this - 40,
        -2147024809);
    goto LABEL_122;
  }
  v10 = FSMValidateVirtualCameraStateInfo(a3);
  v9 = v10;
  if ( v10 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        (char *)this - 40,
        v10);
LABEL_122:
    if ( byte_18005E5A5 )
    {
      v45 = 51;
      goto LABEL_124;
    }
    goto LABEL_125;
  }
  if ( (unsigned int)(*(_DWORD *)a3 - 1) <= 1 )
  {
    v14 = *(_QWORD *)a2;
    v52 = 0;
    v51 = 0;
    v15 = (*(__int64 (__fastcall **)(struct IFSMSession *, __int64))(v14 + 160))(a2, 4);
    v16 = *(_QWORD *)a2;
    if ( v15 )
    {
      v17 = v51;
      v18 = *(__int64 (__fastcall **)(struct IFSMSession *, __int64, struct IFSMSessionIdentity **))(v16 + 200);
      v51 = 0;
      if ( v17 )
        (*(void (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)v17 + 16LL))(v17);
      v19 = v18(a2, 4, &v51);
      v9 = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 26;
LABEL_120:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v20,
            &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            (char *)this - 40,
            v19);
          goto LABEL_121;
        }
        goto LABEL_121;
      }
    }
    else
    {
      if ( !(*(unsigned __int8 (__fastcall **)(struct IFSMSession *, __int64))(v16 + 160))(a2, 5) )
      {
        v19 = -1072875854;
        v9 = -1072875854;
        if ( g_wppLevels )
        {
          v20 = 28;
          goto LABEL_120;
        }
        goto LABEL_121;
      }
      v21 = v51;
      v22 = *(_QWORD *)a2;
      v51 = 0;
      v23 = *(__int64 (__fastcall **)(struct IFSMSession *, __int64, struct IFSMSessionIdentity **))(v22 + 200);
      if ( v21 )
        (*(void (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)v21 + 16LL))(v21);
      v19 = v23(a2, 5, &v51);
      v9 = v19;
      if ( v19 < 0 )
      {
        if ( g_wppLevels )
        {
          v20 = 27;
          goto LABEL_120;
        }
LABEL_121:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v51);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          (wil::details **)&v52,
          v46);
        goto LABEL_122;
      }
    }
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
    if ( v8[644] )
    {
      if ( *(_DWORD *)a3 == 2 )
      {
        v28 = -2147024891;
        v9 = -2147024891;
        if ( g_wppLevels )
        {
          v29 = 45;
          goto LABEL_106;
        }
        goto LABEL_84;
      }
    }
    else
    {
      v27 = (const UINT8 *)*((_QWORD *)a3 + 1);
      if ( v27 )
      {
        v28 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 67), v27, *((_DWORD *)a3 + 4));
        v9 = v28;
        if ( v28 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 29;
LABEL_106:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v29,
              &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
              (char *)this - 40,
              v28);
            goto LABEL_84;
          }
          goto LABEL_84;
        }
        v28 = FSMVirtualCamera::AddPropertyToCollection(
                *((struct IFSMCameraDeviceProperties **)this + 62),
                &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes,
                0x1003u,
                *((const unsigned __int8 **)a3 + 1),
                *((unsigned int *)a3 + 4));
        v9 = v28;
        if ( v28 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 30;
            goto LABEL_106;
          }
LABEL_84:
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
          goto LABEL_85;
        }
        v28 = FSMVirtualCamera::AddPropertyToCollection(
                *((struct IFSMCameraDeviceProperties **)this + 61),
                &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes,
                0x1003u,
                *((const unsigned __int8 **)a3 + 1),
                *((unsigned int *)a3 + 4));
        v9 = v28;
        if ( v28 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 31;
            goto LABEL_106;
          }
          goto LABEL_84;
        }
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, const DEVPROPKEY *))(**((_QWORD **)this + 62) + 72LL))(
          *((_QWORD *)this + 62),
          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes);
        (*(void (__fastcall **)(_QWORD, const DEVPROPKEY *))(**((_QWORD **)this + 61) + 72LL))(
          *((_QWORD *)this + 61),
          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes);
      }
      if ( *((_QWORD *)a3 + 11) )
      {
        v50 = 0;
        FSMDeviceProperties = FSMCameraDeviceProperties::CreateFSMDeviceProperties(v30, (void **)&v50);
        v9 = FSMDeviceProperties;
        if ( FSMDeviceProperties < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_52:
            wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v50);
            goto LABEL_84;
          }
          v32 = 32;
LABEL_51:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v32,
            &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            (char *)this - 40,
            FSMDeviceProperties);
          goto LABEL_52;
        }
        FSMDeviceProperties = (*(__int64 (__fastcall **)(struct IFSMCameraDeviceProperties *, _QWORD, _QWORD))(*(_QWORD *)v50 + 88LL))(
                                v50,
                                *((_QWORD *)a3 + 11),
                                *((unsigned int *)a3 + 24));
        v9 = FSMDeviceProperties;
        if ( FSMDeviceProperties < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_52;
          v32 = 33;
          goto LABEL_51;
        }
        FSMDeviceProperties = FSMVirtualCamera::InternalValidatePropertyCollection(
                                (FSMVirtualCamera *)((char *)this - 40),
                                v51,
                                v50);
        v9 = FSMDeviceProperties;
        if ( FSMDeviceProperties < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_52;
          v32 = 34;
          goto LABEL_51;
        }
        FSMDeviceProperties = (*(__int64 (__fastcall **)(_QWORD, struct IFSMCameraDeviceProperties *, _QWORD))(**((_QWORD **)this + 62) + 104LL))(
                                *((_QWORD *)this + 62),
                                v50,
                                0);
        v9 = FSMDeviceProperties;
        if ( FSMDeviceProperties < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_52;
          v32 = 35;
          goto LABEL_51;
        }
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v50);
      }
      if ( *(_DWORD *)a3 == 1 )
      {
        v33 = *((_QWORD *)a3 + 3);
        LODWORD(v50) = 0;
        pv = 0;
        if ( v33 )
        {
          v28 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 61) + 88LL))(
                  *((_QWORD *)this + 61),
                  v33,
                  *((unsigned int *)a3 + 8));
          v9 = v28;
          if ( v28 < 0 )
          {
            if ( g_wppLevels )
            {
              v29 = 36;
              goto LABEL_106;
            }
            goto LABEL_84;
          }
        }
        v28 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *, struct IFSMCameraDeviceProperties **))(**((_QWORD **)this + 61)
                                                                                                + 80LL))(
                *((_QWORD *)this + 61),
                &pv,
                &v50);
        v9 = v28;
        if ( v28 < 0 )
        {
          if ( g_wppLevels )
          {
            v29 = 37;
            goto LABEL_106;
          }
          goto LABEL_84;
        }
        v34 = pv;
        updated = FSMVirtualCamera::AddPropertyToCollection(
                    *((struct IFSMCameraDeviceProperties **)this + 62),
                    &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Properties,
                    0x1003u,
                    (const unsigned __int8 *)pv,
                    (unsigned int)v50);
        v9 = updated;
        if ( updated < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_82;
          v36 = 38;
          goto LABEL_81;
        }
        updated = FSMVirtualCamera::InternalUpdateRegistryEntries(
                    (FSMVirtualCamera *)((char *)this - 40),
                    *((const unsigned __int8 **)a3 + 5),
                    *((_DWORD *)a3 + 12));
        v9 = updated;
        if ( updated < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_82;
          v36 = 39;
          goto LABEL_81;
        }
        if ( *((_QWORD *)a3 + 7) )
        {
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((char *)this + 608);
          *((_DWORD *)this + 154) = 0;
          unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(
                                                    &v49,
                                                    *((unsigned int *)a3 + 16));
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
            (void **)this + 76,
            unique);
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v49);
          v38 = (void *)*((_QWORD *)this + 76);
          if ( !v38 )
          {
            updated = -2147024882;
            v9 = -2147024882;
            if ( !g_wppLevels )
              goto LABEL_82;
            v36 = 40;
            goto LABEL_81;
          }
          memcpy_0(v38, *((const void **)a3 + 7), *((unsigned int *)a3 + 16));
          *((_DWORD *)this + 154) = *((_DWORD *)a3 + 16);
        }
        if ( *((_DWORD *)a3 + 20) )
        {
          v40 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(
                                                 &v49,
                                                 *((unsigned int *)a3 + 20));
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
            (void **)this + 80,
            v40);
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v49);
          v41 = (void *)*((_QWORD *)this + 80);
          if ( !v41 )
          {
            updated = -2147024882;
            v9 = -2147024882;
            if ( !g_wppLevels )
            {
LABEL_82:
              if ( v34 )
                CoTaskMemFree(v34);
              goto LABEL_84;
            }
            v36 = 41;
LABEL_81:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v36,
              &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
              (char *)this - 40,
              updated);
            goto LABEL_82;
          }
          v42 = *((_DWORD *)a3 + 20);
          *((_DWORD *)this + 162) = v42;
          memcpy_0(v41, *((const void **)a3 + 9), v42);
        }
        if ( v34 )
          CoTaskMemFree(v34);
      }
      v28 = FSMVirtualCamera::InternalValidatePropertyCollection(
              (FSMVirtualCamera *)((char *)this - 40),
              v51,
              *((struct IFSMCameraDeviceProperties **)this + 61));
      v9 = v28;
      if ( v28 < 0 )
      {
        if ( g_wppLevels )
        {
          v29 = 42;
          goto LABEL_106;
        }
        goto LABEL_84;
      }
      v28 = FSMVirtualCamera::InternalValidatePropertyCollection(
              (FSMVirtualCamera *)((char *)this - 40),
              v51,
              *((struct IFSMCameraDeviceProperties **)this + 62));
      v9 = v28;
      if ( v28 < 0 )
      {
        if ( g_wppLevels )
        {
          v29 = 43;
          goto LABEL_106;
        }
        goto LABEL_84;
      }
      v28 = FSMVirtualCamera::InternalAddStateFlag(
              (char *)this - 40,
              *(unsigned int *)a3,
              *((_QWORD *)this + 61),
              *((_QWORD *)this + 62));
      v9 = v28;
      if ( v28 < 0 )
      {
        if ( g_wppLevels )
        {
          v29 = 44;
          goto LABEL_106;
        }
        goto LABEL_84;
      }
    }
    if ( (int)FSMFindVCamByHash((unsigned __int8 *)this + 120, v24, v25, v26) >= 0 )
      *((_DWORD *)this + 150) = 1;
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      &v52,
      0);
    v28 = FSMVirtualCamera::InternalCreateSwDevice((FSMVirtualCamera *)((char *)this - 40), &v52);
    v9 = v28;
    if ( v28 >= 0 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      v43 = FSMVirtualCamera::InternalWaitForCompletion((FSMVirtualCamera *)((char *)this - 40), v52);
      v9 = v43;
      if ( v43 >= 0 )
      {
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v51);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          (wil::details **)&v52,
          v44);
        v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
        goto LABEL_116;
      }
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          47,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (char *)this - 40,
          v43);
LABEL_85:
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v51);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        (wil::details **)&v52,
        v39);
      v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
      goto LABEL_122;
    }
    if ( g_wppLevels )
    {
      v29 = 46;
      goto LABEL_106;
    }
    goto LABEL_84;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  v11 = (const unsigned __int16 *)*((_QWORD *)this + 57);
  if ( v11 == *((const unsigned __int16 **)this + 58) )
  {
    v12 = -1072875854;
    v9 = -1072875854;
    if ( !g_wppLevels )
    {
LABEL_15:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
      goto LABEL_122;
    }
    v13 = 48;
LABEL_14:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v13,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (char *)this - 40,
      v12);
    goto LABEL_15;
  }
  if ( v8[644] )
  {
    v12 = -2147024891;
    v9 = -2147024891;
    if ( !g_wppLevels )
      goto LABEL_15;
    v13 = 49;
    goto LABEL_14;
  }
  *((_DWORD *)this + 29) = 0;
  v12 = FSRemoveVirtualCameraByName(v11);
  v9 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_15;
    v13 = 50;
    goto LABEL_14;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
LABEL_116:
  MFCleanupVirtualCameraEntries();
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v45 = 52;
LABEL_124:
    WPP_SF_qDS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v45,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this - 40,
      v9,
      *((_QWORD *)this + 37));
  }
LABEL_125:
  LeaveCriticalSection(v3);
  return v9;
}

```

## disassembly

```asm
0x180024b00  mov     [rsp-38h+arg_10], rbx
0x180024b05  push    rbp
0x180024b06  push    rsi
0x180024b07  push    rdi
0x180024b08  push    r12
0x180024b0a  push    r13
0x180024b0c  push    r14
0x180024b0e  push    r15
0x180024b10  mov     rbp, rsp
0x180024b13  sub     rsp, 50h
0x180024b17  lea     r12, [rcx+10h]
0x180024b1b  mov     r13, rcx
0x180024b1e  mov     rcx, r12; lpCriticalSection
0x180024b21  mov     r15, r8
0x180024b24  mov     rbx, rdx
0x180024b27  call    cs:__imp_EnterCriticalSection
0x180024b2d  cmp     cs:byte_18005E5A5, 8
0x180024b34  lea     r14, [r13-28h]
0x180024b38  jb      short loc_180024B70
0x180024b3a  mov     rax, [r14+150h]
0x180024b41  mov     edx, 17h
0x180024b46  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b4d  mov     r9, r14
0x180024b50  mov     [rsp+50h+var_20], rax
0x180024b55  mov     eax, [r15]
0x180024b58  mov     dword ptr [rsp+50h+var_28], eax
0x180024b5c  mov     eax, [r13+74h]
0x180024b60  mov     rcx, [rcx+0D8h]
0x180024b67  mov     dword ptr [rsp+50h+var_30], eax
0x180024b6b  call    WPP_SF_qddS
0x180024b70  test    rbx, rbx
0x180024b73  jnz     short loc_180024BB0
0x180024b75  mov     edi, 80070057h
0x180024b7a  lea     esi, [rbx+1]
0x180024b7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024b84  jb      loc_1800253A9
0x180024b8a  lea     edx, [rbx+18h]
0x180024b8d  mov     dword ptr [rsp+50h+var_30], edi
0x180024b91  mov     rcx, cs:WPP_GLOBAL_Control
0x180024b98  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180024b9f  mov     r9, r14
0x180024ba2  mov     rcx, [rcx+10h]
0x180024ba6  call    WPP_SF_qD
0x180024bab  jmp     loc_1800253A9
0x180024bb0  mov     rcx, r15
0x180024bb3  call    FSMValidateVirtualCameraStateInfo
0x180024bb8  mov     edi, eax
0x180024bba  test    eax, eax
0x180024bbc  jns     short loc_180024BD9
0x180024bbe  mov     esi, 1
0x180024bc3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024bca  jb      loc_1800253A9
0x180024bd0  lea     edx, [rsi+18h]
0x180024bd3  mov     dword ptr [rsp+50h+var_30], eax
0x180024bd7  jmp     short loc_180024B91
0x180024bd9  mov     eax, [r15]
0x180024bdc  mov     esi, 1
0x180024be1  sub     eax, esi
0x180024be3  cmp     eax, esi
0x180024be5  jbe     loc_180024C99
0x180024beb  lea     rbx, [r13+38h]
0x180024bef  mov     rcx, rbx; lpCriticalSection
0x180024bf2  call    cs:__imp_EnterCriticalSection
0x180024bf8  mov     rcx, [r13+1C8h]; unsigned __int16 *
0x180024bff  cmp     rcx, [r13+1D0h]
0x180024c06  jnz     short loc_180024C47
0x180024c08  mov     eax, 0C00D36B2h
0x180024c0d  mov     edi, eax
0x180024c0f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024c16  jb      short loc_180024C39
0x180024c18  lea     edx, [rsi+2Fh]
0x180024c1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180024c22  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180024c29  mov     r9, r14
0x180024c2c  mov     dword ptr [rsp+50h+var_30], eax
0x180024c30  mov     rcx, [rcx+10h]
0x180024c34  call    WPP_SF_qD
0x180024c39  mov     rcx, rbx; lpCriticalSection
0x180024c3c  call    cs:__imp_LeaveCriticalSection
0x180024c42  jmp     loc_1800253A9
0x180024c47  cmp     byte ptr [r14+284h], 0
0x180024c4f  jz      short loc_180024C68
0x180024c51  mov     eax, 80070005h
0x180024c56  mov     edi, eax
0x180024c58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024c5f  jb      short loc_180024C39
0x180024c61  mov     edx, 31h ; '1'
0x180024c66  jmp     short loc_180024C1B
0x180024c68  mov     dword ptr [r13+74h], 0
0x180024c70  call    ?FSRemoveVirtualCameraByName@@YAJPEBG@Z; FSRemoveVirtualCameraByName(ushort const *)
0x180024c75  mov     edi, eax
0x180024c77  test    eax, eax
0x180024c79  jns     short loc_180024C8B
0x180024c7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024c82  jb      short loc_180024C39
0x180024c84  mov     edx, 32h ; '2'
0x180024c89  jmp     short loc_180024C1B
0x180024c8b  mov     rcx, rbx; lpCriticalSection
0x180024c8e  call    cs:__imp_LeaveCriticalSection
0x180024c94  jmp     loc_18002534A
0x180024c99  mov     rax, [rbx]
0x180024c9c  mov     edx, 4
0x180024ca1  mov     rcx, rbx
0x180024ca4  mov     [rbp+arg_18], 0
0x180024cac  mov     [rbp+arg_8], 0
0x180024cb4  mov     rax, [rax+0A0h]
0x180024cbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cc0  mov     r8, [rbx]
0x180024cc3  test    al, al
0x180024cc5  jz      short loc_180024D20
0x180024cc7  mov     rcx, [rbp+arg_8]
0x180024ccb  mov     rdi, [r8+0C8h]
0x180024cd2  mov     [rbp+arg_8], 0
0x180024cda  test    rcx, rcx
0x180024cdd  jz      short loc_180024CEB
0x180024cdf  mov     r8, [rcx]
0x180024ce2  mov     rax, [r8+10h]
0x180024ce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ceb  lea     r8, [rbp+arg_8]
0x180024cef  mov     edx, 4
0x180024cf4  mov     rcx, rbx
0x180024cf7  mov     rax, rdi
0x180024cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cff  mov     edi, eax
0x180024d01  test    eax, eax
0x180024d03  jns     loc_180024D94
0x180024d09  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024d10  jb      loc_180025397
0x180024d16  mov     edx, 1Ah
0x180024d1b  jmp     loc_180025379
0x180024d20  mov     rax, [r8+0A0h]
0x180024d27  mov     edx, 5
0x180024d2c  mov     rcx, rbx
0x180024d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d34  test    al, al
0x180024d36  jz      loc_180025364
0x180024d3c  mov     rcx, [rbp+arg_8]
0x180024d40  mov     rax, [rbx]
0x180024d43  mov     [rbp+arg_8], 0
0x180024d4b  mov     rdi, [rax+0C8h]
0x180024d52  test    rcx, rcx
0x180024d55  jz      short loc_180024D63
0x180024d57  mov     r8, [rcx]
0x180024d5a  mov     rax, [r8+10h]
0x180024d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d63  lea     r8, [rbp+arg_8]
0x180024d67  mov     edx, 5
0x180024d6c  mov     rcx, rbx
0x180024d6f  mov     rax, rdi
0x180024d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d77  mov     edi, eax
0x180024d79  test    eax, eax
0x180024d7b  jns     short loc_180024D94
0x180024d7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024d84  jb      loc_180025397
0x180024d8a  mov     edx, 1Bh
0x180024d8f  jmp     loc_180025379
0x180024d94  lea     r12, [r13+38h]
0x180024d98  mov     rcx, r12; lpCriticalSection
0x180024d9b  call    cs:__imp_EnterCriticalSection
0x180024da1  cmp     byte ptr [r14+284h], 0
0x180024da9  jnz     loc_18002525D
0x180024daf  mov     rdx, [r15+8]; pBuf
0x180024db3  mov     ebx, 1003h
0x180024db8  test    rdx, rdx
0x180024dbb  jz      loc_180024E6F
0x180024dc1  mov     r8d, [r15+10h]; cbBufSize
0x180024dc5  mov     rcx, [r13+218h]; pAttributes
0x180024dcc  call    cs:__imp_MFInitAttributesFromBlob
0x180024dd2  mov     edi, eax
0x180024dd4  test    eax, eax
0x180024dd6  jns     short loc_180024DEF
0x180024dd8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024ddf  jb      loc_18002511C
0x180024de5  mov     edx, 1Dh
0x180024dea  jmp     loc_18002527C
0x180024def  mov     eax, [r15+10h]
0x180024df3  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes; struct _DEVPROPKEY *
0x180024dfa  mov     r9, [r15+8]; unsigned __int8 *
0x180024dfe  mov     r8d, ebx; unsigned int
0x180024e01  mov     rcx, [r13+1F0h]; struct IFSMCameraDeviceProperties *
0x180024e08  mov     [rsp+50h+var_30], rax; unsigned __int64
0x180024e0d  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180024e12  mov     edi, eax
0x180024e14  test    eax, eax
0x180024e16  jns     short loc_180024E2F
0x180024e18  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024e1f  jb      loc_18002511C
0x180024e25  mov     edx, 1Eh
0x180024e2a  jmp     loc_18002527C
0x180024e2f  mov     eax, [r15+10h]
0x180024e33  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes; struct _DEVPROPKEY *
0x180024e3a  mov     r9, [r15+8]; unsigned __int8 *
0x180024e3e  mov     r8d, ebx; unsigned int
0x180024e41  mov     rcx, [r13+1E8h]; struct IFSMCameraDeviceProperties *
0x180024e48  mov     [rsp+50h+var_30], rax; unsigned __int64
0x180024e4d  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180024e52  mov     edi, eax
0x180024e54  test    eax, eax
0x180024e56  jns     short loc_180024EA3
0x180024e58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024e5f  jb      loc_18002511C
0x180024e65  mov     edx, 1Fh
0x180024e6a  jmp     loc_18002527C
0x180024e6f  mov     rcx, [r13+1F0h]
0x180024e76  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes
0x180024e7d  mov     rax, [rcx]
0x180024e80  mov     rax, [rax+48h]
0x180024e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e89  mov     rcx, [r13+1E8h]
0x180024e90  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes
0x180024e97  mov     rax, [rcx]
0x180024e9a  mov     rax, [rax+48h]
0x180024e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ea3  cmp     qword ptr [r15+58h], 0
0x180024ea8  jz      loc_180024F93
0x180024eae  lea     rdx, [rbp+arg_0]; void **
0x180024eb2  mov     [rbp+arg_0], 0
0x180024eba  call    ?CreateFSMDeviceProperties@FSMCameraDeviceProperties@@SAJAEBU_GUID@@PEAPEAX@Z; FSMCameraDeviceProperties::CreateFSMDeviceProperties(_GUID const &,void * *)
0x180024ebf  mov     edi, eax
0x180024ec1  test    eax, eax
0x180024ec3  jns     short loc_180024EFF
0x180024ec5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024ecc  jb      short loc_180024EF1
0x180024ece  mov     edx, 20h ; ' '
0x180024ed3  mov     rcx, cs:WPP_GLOBAL_Control
0x180024eda  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180024ee1  mov     r9, r14
0x180024ee4  mov     dword ptr [rsp+50h+var_30], eax
0x180024ee8  mov     rcx, [rcx+10h]
0x180024eec  call    WPP_SF_qD
0x180024ef1  lea     rcx, [rbp+arg_0]
0x180024ef5  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180024efa  jmp     loc_18002511C
0x180024eff  mov     rcx, [rbp+arg_0]
0x180024f03  mov     r8d, [r15+60h]
0x180024f07  mov     rdx, [r15+58h]
0x180024f0b  mov     rax, [rcx]
0x180024f0e  mov     rax, [rax+58h]
0x180024f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f17  mov     edi, eax
0x180024f19  test    eax, eax
0x180024f1b  jns     short loc_180024F2D
0x180024f1d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024f24  jb      short loc_180024EF1
0x180024f26  mov     edx, 21h ; '!'
0x180024f2b  jmp     short loc_180024ED3
0x180024f2d  mov     r8, [rbp+arg_0]; struct IFSMCameraDeviceProperties *
0x180024f31  mov     rcx, r14; this
0x180024f34  mov     rdx, [rbp+arg_8]; struct IFSMSessionIdentity *
0x180024f38  call    ?InternalValidatePropertyCollection@FSMVirtualCamera@@IEAAJPEAUIFSMSessionIdentity@@PEAUIFSMCameraDeviceProperties@@@Z; FSMVirtualCamera::InternalValidatePropertyCollection(IFSMSessionIdentity *,IFSMCameraDeviceProperties *)
0x180024f3d  mov     edi, eax
0x180024f3f  test    eax, eax
0x180024f41  jns     short loc_180024F53
0x180024f43  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024f4a  jb      short loc_180024EF1
0x180024f4c  mov     edx, 22h ; '"'
0x180024f51  jmp     short loc_180024ED3
0x180024f53  mov     rcx, [r13+1F0h]
0x180024f5a  xor     r8d, r8d
0x180024f5d  mov     rdx, [rbp+arg_0]
0x180024f61  mov     rax, [rcx]
0x180024f64  mov     rax, [rax+68h]
0x180024f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f6d  mov     edi, eax
0x180024f6f  test    eax, eax
0x180024f71  jns     short loc_180024F8A
0x180024f73  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024f7a  jb      loc_180024EF1
0x180024f80  mov     edx, 23h ; '#'
0x180024f85  jmp     loc_180024ED3
0x180024f8a  lea     rcx, [rbp+arg_0]
0x180024f8e  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180024f93  cmp     [r15], esi
0x180024f96  jnz     loc_1800251D0
0x180024f9c  mov     rdx, [r15+18h]
0x180024fa0  mov     dword ptr [rbp+arg_0], 0
0x180024fa7  mov     [rbp+pv], 0
0x180024faf  test    rdx, rdx
0x180024fb2  jz      short loc_180024FE8
0x180024fb4  mov     rcx, [r13+1E8h]
0x180024fbb  mov     r8d, [r15+20h]
0x180024fbf  mov     rax, [rcx]
0x180024fc2  mov     rax, [rax+58h]
0x180024fc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024fcb  mov     edi, eax
0x180024fcd  test    eax, eax
0x180024fcf  jns     short loc_180024FE8
0x180024fd1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x180024fd8  jb      loc_18002511C
0x180024fde  mov     edx, 24h ; '$'
0x180024fe3  jmp     loc_18002527C
0x180024fe8  mov     rcx, [r13+1E8h]
0x180024fef  lea     r8, [rbp+arg_0]
0x180024ff3  lea     rdx, [rbp+pv]
0x180024ff7  mov     rax, [rcx]
0x180024ffa  mov     rax, [rax+50h]
0x180024ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025003  mov     edi, eax
0x180025005  test    eax, eax
  ... truncated ...
```
