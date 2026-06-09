# FSClientContext::Initialize(void *,IUnknown *,ulong,IMFAttributes *,IMFAttributes *,IUnknown *,_GUID const &,__MIDL___MIDL_itf_fsserviceapi_0000_0000_0008,unsigned __int64 *)

- ea: `0x18006bf9c`
- end: `0x18006cbd9`
- name: `?Initialize@FSClientContext@@IEAAJPEAXPEAUIUnknown@@KPEAUIMFAttributes@@21AEBU_GUID@@T__MIDL___MIDL_itf_fsserviceapi_0000_0000_0008@@PEA_K@Z`
- size: `3133`
- prototype: ``
- caller_count: `1`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800693a8`

## callees

- `0x18000162c`
- `0x180001860`
- `0x180003e20`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x18000a648`
- `0x18000a880`
- `0x180014f08`
- `0x180017ab8`
- `0x180017d34`
- `0x1800198f4`
- `0x18001c444`
- `0x180024200`
- `0x18004d714`
- `0x18004d748`
- `0x18004da70`
- `0x18004f37c`
- `0x18006133c`
- `0x180067b00`
- `0x18006bf9c`
- `0x18006e58c`
- `0x180073610`
- `0x180073f90`
- `0x1800742dc`
- `0x180074374`
- `0x180076828`
- `0x180080e34`
- `0x1800d1e0c`
- `0x1800e9240`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cba9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006cba9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c006`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006c006`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c80e`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006c629`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18006c629`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006c804`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18006c804`
- `MFPlat!MFGetSystemTime` at `0x18006cad0`
- `MFPlat!MFGetSystemTime` at `0x18006cad0`
- `MFPlat!MFCreateAttributes` at `0x18006c506`
- `MFPlat!MFCreateAttributes` at `0x18006c506`

## pseudocode

```c
__int64 __fastcall FSClientContext::Initialize(
        __int64 a1,
        __int64 a2,
        __int64 (__fastcall ***a3)(_QWORD, GUID *, __int64),
        int a4,
        struct IMFAttributes *a5,
        GUID *a6,
        __int64 (__fastcall ***a7)(_QWORD, GUID *, __int64),
        _OWORD *a8,
        int a9,
        __int64 a10)
{
  char v11; // r12
  __int64 v13; // rdx
  __int64 v14; // r8
  signed int v15; // r15d
  __int64 v16; // rdx
  _QWORD *v17; // rsi
  __int64 (__fastcall *v18)(_QWORD, GUID *, __int64); // rsi
  HRESULT FSClientContextInfo; // eax
  __int64 v20; // rdx
  struct IFSClientContextInfo **v21; // r14
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // r15
  __int64 (__fastcall *v24)(_QWORD, GUID *, __int64); // rsi
  __int64 v25; // r14
  void (__fastcall *v26)(__int64, __int64); // rsi
  __int64 v27; // rax
  IMFAttributes **v28; // r15
  __int64 v29; // rcx
  int v30; // eax
  IMFAttributes *v31; // rcx
  GUID *v32; // rsi
  int v33; // eax
  struct IFSClientContextInfo *v34; // rcx
  GUID v35; // xmm0
  __int64 v36; // rdx
  __int64 v37; // rcx
  int v38; // r12d
  GuidTrace *v39; // rax
  const char *v40; // r15
  GuidTrace *v41; // rax
  const char *v42; // r14
  char v43; // si
  char v44; // al
  FSString *v45; // rax
  const char *String; // r14
  int v47; // esi
  GuidTrace *v48; // rax
  const char *v49; // rax
  struct IFSClientContextInfo *v50; // rcx
  bool v51; // al
  __int64 v52; // rax
  struct IFSClientContextInfo *v53; // rcx
  __int64 v54; // r9
  __int64 v55; // rdx
  __int64 v56; // rdx
  int Handle; // eax
  signed int LastError; // eax
  __int64 v59; // r14
  int (__fastcall *v60)(__int64, void *, HANDLE *, struct IMFAttributes **); // rsi
  int v61; // r8d
  int v62; // r9d
  __int64 v63; // rdx
  __int64 v64; // rcx
  unsigned int v65; // esi
  MFTIME v66; // rax
  __int64 v67; // rcx
  __int64 v69; // [rsp+60h] [rbp-99h] BYREF
  HANDLE hDevice; // [rsp+68h] [rbp-91h] BYREF
  int v71; // [rsp+70h] [rbp-89h] BYREF
  struct IMFAttributes *v72; // [rsp+78h] [rbp-81h] BYREF
  int v73; // [rsp+80h] [rbp-79h] BYREF
  DWORD BytesReturned; // [rsp+84h] [rbp-75h] BYREF
  __int64 v75; // [rsp+88h] [rbp-71h] BYREF
  __int64 (__fastcall ***v76)(_QWORD, GUID *, __int64); // [rsp+90h] [rbp-69h] BYREF
  GUID *p_Buf1; // [rsp+98h] [rbp-61h] BYREF
  struct _GUID v78; // [rsp+A0h] [rbp-59h] BYREF
  _BYTE v79[32]; // [rsp+C0h] [rbp-39h] BYREF
  GUID Buf1; // [rsp+E0h] [rbp-19h] BYREF

  v11 = 0;
  v69 = a10;
  v71 = a4;
  v75 = a2;
  v72 = a5;
  p_Buf1 = a6;
  v76 = a7;
  LODWORD(hDevice) = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  BytesReturned = 0;
  v73 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
    WPP_SF_qqqDqqL(*((_QWORD *)WPP_GLOBAL_Control + 27), v13, v14, a1, v75, a3, v71, a5, a6, a9);
  if ( !a3 )
  {
    v15 = -2147024809;
    if ( g_wppLevels )
    {
      v16 = 19;
LABEL_103:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v15);
      goto LABEL_104;
    }
    goto LABEL_104;
  }
  v17 = (_QWORD *)v69;
  if ( v69 )
  {
    *(_QWORD *)v69 = 0;
    v18 = **a3;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 24);
    FSClientContextInfo = v18(a3, &GUID_8d4a34c8_16ca_4698_861a_46421c72c817, a1 + 24);
    v15 = FSClientContextInfo;
    if ( FSClientContextInfo < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_104;
      v20 = 21;
LABEL_12:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v20,
        &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
        a1,
        FSClientContextInfo);
      goto LABEL_104;
    }
    FSClientContextInfo = (*(__int64 (__fastcall **)(_QWORD, GUID *, int *))(**(_QWORD **)(a1 + 24) + 64LL))(
                            *(_QWORD *)(a1 + 24),
                            &Buf1,
                            &v73);
    v15 = FSClientContextInfo;
    if ( FSClientContextInfo < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_104;
      v20 = 22;
      goto LABEL_12;
    }
    v21 = (struct IFSClientContextInfo **)(a1 + 856);
    v22 = *(_QWORD *)(a1 + 856);
    *(_QWORD *)(a1 + 856) = 0;
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    FSClientContextInfo = FSClientContextInfo::CreateFSClientContextInfo(
                            *(struct IDeviceAccessHandler **)(a1 + 24),
                            v72,
                            (struct IFSCCInfoConfiguration **)(a1 + 856));
    v15 = FSClientContextInfo;
    if ( FSClientContextInfo < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_104;
      v20 = 23;
      goto LABEL_12;
    }
    v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v76;
    if ( v76 )
    {
      v24 = **v76;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 1296);
      FSClientContextInfo = v24(v23, &GUID_82fc34df_7f60_4751_bffd_2aa1f8b269fc, a1 + 1296);
      v15 = FSClientContextInfo;
      if ( FSClientContextInfo < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_104;
        v20 = 24;
        goto LABEL_12;
      }
      v25 = *(_QWORD *)(a1 + 1296);
      v26 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v25 + 40LL);
      v27 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 120LL))(*(_QWORD *)(a1 + 24));
      v26(v25, v27);
      v21 = (struct IFSClientContextInfo **)(a1 + 856);
    }
    wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(a1 + 960, p_Buf1);
    v28 = (IMFAttributes **)(a1 + 792);
    wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(a1 + 792, v72);
    v29 = *(_QWORD *)(a1 + 792);
    *(_DWORD *)(a1 + 96) = v71;
    *(_OWORD *)(a1 + 32) = *a8;
    if ( !v29 )
    {
LABEL_54:
      if ( (*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)*v21 + 80LL))(*v21) )
      {
        if ( !*v28 )
        {
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(v28);
          FSClientContextInfo = MFCreateAttributes(v28, 1u);
          v15 = FSClientContextInfo;
          if ( FSClientContextInfo < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_104;
            v20 = 28;
            goto LABEL_12;
          }
          v28 = (IMFAttributes **)(a1 + 792);
        }
        FSClientContextInfo = ((__int64 (__fastcall *)(IMFAttributes *, void *, __int64))(*v28)->lpVtbl->SetUINT32)(
                                *v28,
                                &FS_CLIENTCONTEXT_SETTINGS_PAGE_APP,
                                1);
        v15 = FSClientContextInfo;
        if ( FSClientContextInfo < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_104;
          v20 = 29;
          goto LABEL_12;
        }
      }
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v45 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)&v78, *v21);
        String = FSString::GetString(v45);
        v47 = *(_DWORD *)(a1 + 844);
        v11 |= 0x18u;
        v48 = GuidTrace::GuidTrace((GuidTrace *)v79, (const struct _GUID *)(a1 + 828));
        v49 = GuidTrace::GetString(v48);
        WPP_SF_qsds(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v49, v47, (__int64)String);
        v21 = (struct IFSClientContextInfo **)(a1 + 856);
      }
      if ( (v11 & 0x10) != 0 )
      {
        v11 &= ~0x10u;
        FSString::~FSString((FSString *)v79);
      }
      if ( (v11 & 8) != 0 )
        FSString::~FSString((FSString *)&v78);
      if ( *(_QWORD *)(a1 + 812) == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
        && *(_QWORD *)(a1 + 820) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
      {
        CoCreateGuid((GUID *)(a1 + 812));
      }
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_FrameServerErrorTelemetry>::GetImpl'::`2'::impl) )
        (*(void (__fastcall **)(struct IFSClientContextInfo *, __int64))(*(_QWORD *)*v21 + 296LL))(*v21, a1 + 812);
      if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 24) + 32LL))(*(_QWORD *)(a1 + 24)) )
      {
        v15 = -2147024891;
        if ( g_wppLevels )
        {
          v16 = 31;
          goto LABEL_103;
        }
LABEL_104:
        v17 = (_QWORD *)v69;
        goto LABEL_105;
      }
      v50 = *v21;
      v51 = v73 != 0;
      *(_QWORD *)(a1 + 776) = 0;
      *(_BYTE *)(a1 + 984) = v51;
      v52 = (*(__int64 (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v50 + 128LL))(v50);
      v53 = *v21;
      *(_QWORD *)(a1 + 768) = v52;
      *(_QWORD *)(a1 + 760) = (*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v53 + 136LL))(v53);
      *(_DWORD *)(a1 + 752) = 1;
      *(_QWORD *)(a1 + 776) = 0;
      *(_QWORD *)(a1 + 712) = 0;
      if ( !*(_QWORD *)(a1 + 304) )
      {
        *(_DWORD *)(a1 + 312) = 20;
        *(_QWORD *)(a1 + 304) = a1 + 320;
        v54 = 0;
        *(_QWORD *)(a1 + 320) = 0;
        do
        {
          v55 = v54 + 2 * v54 + 1;
          ++v54;
          v56 = *(_QWORD *)(a1 + 304) + 8 * v55;
          *(_QWORD *)(v56 + 8) = *(_QWORD *)(a1 + 296);
          *(_QWORD *)(a1 + 296) = v56;
        }
        while ( v54 != 16 );
      }
      if ( !memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
      {
        hDevice = (HANDLE)-1LL;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hDevice,
          -1);
        Handle = MSKSSrv_GetHandle(&hDevice);
        v15 = Handle;
        if ( Handle < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              32,
              &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
              a1,
              Handle);
LABEL_84:
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
          goto LABEL_104;
        }
        if ( !DeviceIoControl(hDevice, 0x2F0400u, (LPVOID)(a1 + 752), 0x20u, 0, 0, &BytesReturned, 0) )
        {
          LastError = GetLastError();
          v15 = LastError;
          if ( LastError > 0 )
            v15 = (unsigned __int16)LastError | 0x80070000;
          if ( v15 < 0 )
          {
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                33,
                &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
                a1,
                v15);
            goto LABEL_84;
          }
        }
        v72 = *(struct IMFAttributes **)(a1 + 744);
        *(_QWORD *)(a1 + 744) = -1;
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          a1 + 744,
          &hDevice);
        wil::unique_any_t<wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::operator=(
          &hDevice,
          &v72);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v72);
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hDevice);
      }
      else
      {
        v64 = *(_QWORD *)(a1 + 864);
        *(_QWORD *)(a1 + 864) = 0;
        if ( v64 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
        v65 = (*(__int64 (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)*v21 + 136LL))(*v21);
        v66 = MFGetSystemTime();
        v78 = Buf1;
        FSClientContextInfo = FSVMServerContextSession::CreateFSVMServerContextSession(
                                &v78,
                                v66,
                                v65,
                                (struct IFSVMServerContextSession **)(a1 + 864));
        v15 = FSClientContextInfo;
        if ( FSClientContextInfo < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_104;
          v20 = 34;
          goto LABEL_12;
        }
        if ( !*(_BYTE *)(a1 + 984) )
        {
          v67 = *(_QWORD *)(a1 + 968);
          *(_QWORD *)(a1 + 968) = 0;
          if ( v67 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
          FSClientContextInfo = CFSContainerReference::CreateInstance(
                                  &Buf1,
                                  (struct IFSContainerReference **)(a1 + 968));
          v15 = FSClientContextInfo;
          if ( FSClientContextInfo < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_104;
            v20 = 35;
            goto LABEL_12;
          }
        }
      }
      *(_QWORD *)v69 = *(_QWORD *)(a1 + 768);
      if ( *(_QWORD *)(a1 + 960)
        && !(*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)*v21 + 96LL))(*v21) )
      {
        v59 = *(_QWORD *)(a1 + 960);
        hDevice = 0;
        LODWORD(v72) = 0;
        v60 = *(int (__fastcall **)(__int64, void *, HANDLE *, struct IMFAttributes **))(*(_QWORD *)v59 + 128LL);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
          &hDevice,
          0);
        if ( v60(v59, &FRAMESERVER_DEVICECONFIGURATION_ENTRIES, &hDevice, &v72) >= 0
          && (int)FSClientContext::ProcessDeviceConfiguration(
                    (FSClientContext *)a1,
                    (unsigned __int8 *)hDevice,
                    (unsigned int)v72) < 0 )
        {
          CTUnkArray<IFSMemStream>::RemoveAll(a1 + 896);
          CTUnkArray<IFSMemStream>::RemoveAll(a1 + 928);
          *(_DWORD *)(a1 + 920) = 0;
          *(_DWORD *)(a1 + 952) = 0;
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hDevice);
        v21 = (struct IFSClientContextInfo **)(a1 + 856);
      }
      if ( (a9 & 2) == 0
        && ((a9 & 1) == 0
         || !(*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)*v21 + 184LL))(*v21)) )
      {
        goto LABEL_104;
      }
      v15 = -2147024114;
      if ( !g_wppLevels )
        goto LABEL_104;
      v16 = 36;
      goto LABEL_103;
    }
    (*(void (__fastcall **)(__int64, void *, __int64))(*(_QWORD *)v29 + 80LL))(
      v29,
      &MEDIA_TELEMETRY_SESSION_ID,
      a1 + 812);
    v30 = MFGetAttributeUINT32(*v28, &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE_INDEX, 0);
    v31 = *v28;
    *(_DWORD *)(a1 + 844) = v30;
    v32 = (GUID *)(a1 + 1256);
    *(_DWORD *)(a1 + 1272) = v30;
    v33 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, __int64))v31->lpVtbl->GetGUID)(
            v31,
            &MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE,
            a1 + 828);
    v34 = *v21;
    if ( v33 >= 0 )
    {
      *v32 = *(GUID *)(a1 + 828);
      if ( !(*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v34 + 96LL))(v34) )
      {
LABEL_37:
        v37 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
        v36 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
LABEL_38:
        if ( *(_QWORD *)&v32->Data1 == *(_QWORD *)&GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1
          && *(_QWORD *)(a1 + 1264) == *(_QWORD *)GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data4 )
        {
          if ( (unsigned __int8)byte_18010EC4D >= 8u )
          {
            v38 = *(_DWORD *)(a1 + 1272);
            v39 = GuidTrace::GuidTrace((GuidTrace *)v79, (const struct _GUID *)(a1 + 1256));
            v40 = GuidTrace::GetString(v39);
            v41 = GuidTrace::GuidTrace((GuidTrace *)&v78, &Buf1);
            v42 = GuidTrace::GetString(v41);
            v43 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 856) + 120LL))(*(_QWORD *)(a1 + 856));
            v44 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 856) + 136LL))(*(_QWORD *)(a1 + 856));
            WPP_SF_qdDssd(*((_QWORD *)WPP_GLOBAL_Control + 27), v44, v43, (__int64)v42, (__int64)v40, v38);
            v11 = 3;
            v32 = (GUID *)(a1 + 1256);
            v21 = (struct IFSClientContextInfo **)(a1 + 856);
            v28 = (IMFAttributes **)(a1 + 792);
          }
          if ( (v11 & 2) != 0 )
          {
            v11 &= ~2u;
            FSString::~FSString((FSString *)&v78);
          }
          if ( (v11 & 1) != 0 )
          {
            v11 &= ~1u;
            FSString::~FSString((FSString *)v79);
          }
          FSClientContextInfo = ((__int64 (__fastcall *)(IMFAttributes *, void *, GUID *, __int64))(*v28)->lpVtbl->SetBlob)(
                                  *v28,
                                  &FS_CLIENTCONTEXT_SELECTED_PROFILE,
                                  v32,
                                  24);
          v15 = FSClientContextInfo;
          if ( FSClientContextInfo < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_104;
            v20 = 26;
            goto LABEL_12;
          }
          v37 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
          v28 = (IMFAttributes **)(a1 + 792);
          v36 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
        }
        if ( *(_QWORD *)(a1 + 828) == v36 && *(_QWORD *)(a1 + 836) == v37 )
        {
          *(_DWORD *)(a1 + 844) = 0;
          *(GUID *)(a1 + 828) = GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e;
        }
        (*(void (__fastcall **)(struct IFSClientContextInfo *, __int64))(*(_QWORD *)*v21 + 360LL))(*v21, a1 + 828);
        goto LABEL_54;
      }
      if ( *(_QWORD *)&v32->Data1 != *(_QWORD *)&GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data1
        || *(_QWORD *)(a1 + 1264) != *(_QWORD *)GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data4 )
      {
        v36 = *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
        v37 = *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
        if ( *(_QWORD *)&v32->Data1 != *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
          || *(_QWORD *)(a1 + 1264) != *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
        {
          goto LABEL_38;
        }
      }
    }
    else
    {
      *(GUID *)(a1 + 828) = GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e;
      if ( !(*(unsigned int (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v34 + 96LL))(v34) )
      {
        v35 = GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e;
LABEL_36:
        *v32 = v35;
        goto LABEL_37;
      }
    }
    v35 = GUID_81361b22_700b_4546_a2d4_c52e907bfc27;
    goto LABEL_36;
  }
  v15 = -2147467261;
  if ( g_wppLevels )
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(v69 + 20),
      &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
      a1,
      -2147467261);
LABEL_105:
  if ( (v71 & 1) != 0 && dword_18010C208 && (unsigned __int8)tlgKeywordOn(&dword_18010C208, 0x400000000000LL) )
  {
    LODWORD(v72) = a9;
    p_Buf1 = &Buf1;
    v71 = *(_DWORD *)(a1 + 844);
    v75 = a1 + 812;
    *(_QWORD *)&v78.Data1 = a8;
    v76 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))(a1 + 828);
    LODWORD(hDevice) = v15;
    v69 = 50333696;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      a1 + 828,
      (unsigned int)&unk_180102DBF,
      v61,
      v62,
      (__int64)&v78,
      (__int64)&v69,
      (__int64)&hDevice,
      (__int64)&v75,
      (__int64)&v76,
      (__int64)&v71,
      (__int64)&p_Buf1,
      (__int64)&v72);
  }
  if ( v15 >= 0 )
  {
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v63 = 38;
      goto LABEL_125;
    }
  }
  else if ( byte_18010EC4D )
  {
    v63 = 37;
LABEL_125:
    WPP_SF_qdq(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v63,
      &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
      a1,
      v15,
      *v17);
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 56));
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18006bf9c  mov     [rsp-8+arg_18], rbx
0x18006bfa1  push    rbp
0x18006bfa2  push    rsi
0x18006bfa3  push    rdi
0x18006bfa4  push    r12
0x18006bfa6  push    r13
0x18006bfa8  push    r14
0x18006bfaa  push    r15
0x18006bfac  lea     rbp, [rsp-7]
0x18006bfb1  sub     rsp, 100h
0x18006bfb8  mov     rax, cs:__security_cookie
0x18006bfbf  xor     rax, rsp
0x18006bfc2  mov     [rbp+37h+var_40], rax
0x18006bfc6  mov     rax, [rbp+37h+arg_30]
0x18006bfca  mov     r13, rcx
0x18006bfcd  mov     rcx, [rbp+37h+arg_48]
0x18006bfd4  xor     r12d, r12d
0x18006bfd7  mov     rsi, [rbp+37h+arg_20]
0x18006bfdb  mov     r14, r8
0x18006bfde  mov     r15, [rbp+37h+arg_28]
0x18006bfe2  mov     [rsp+130h+var_D0], rcx
0x18006bfe7  lea     rcx, [r13+38h]; lpCriticalSection
0x18006bfeb  mov     [rsp+130h+var_C0], r9d
0x18006bff0  mov     [rbp+37h+var_A8], rdx
0x18006bff4  mov     [rsp+130h+var_B8], rsi
0x18006bff9  mov     [rbp+37h+var_98], r15
0x18006bffd  mov     [rbp+37h+var_A0], rax
0x18006c001  mov     dword ptr [rsp+130h+hDevice], r12d
0x18006c006  call    cs:__imp_EnterCriticalSection
0x18006c00c  movaps  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006c013  movdqa  [rbp+37h+Buf1], xmm0
0x18006c018  mov     [rbp+37h+BytesReturned], r12d
0x18006c01c  mov     [rbp+37h+var_B0], r12d
0x18006c020  cmp     cs:byte_18010EC4D, 8
0x18006c027  mov     ebx, [rbp+37h+arg_40]
0x18006c02d  jb      short loc_18006C069
0x18006c02f  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c036  mov     r9, r13
0x18006c039  mov     eax, [rsp+130h+var_C0]
0x18006c03d  mov     dword ptr [rsp+130h+var_E8], ebx
0x18006c041  mov     qword ptr [rsp+130h+var_F0], r15
0x18006c046  mov     rcx, [rcx+0D8h]
0x18006c04d  mov     [rsp+130h+lpOverlapped], rsi
0x18006c052  mov     dword ptr [rsp+130h+lpBytesReturned], eax
0x18006c056  mov     rax, [rbp+37h+var_A8]
0x18006c05a  mov     qword ptr [rsp+130h+nOutBufferSize], r14
0x18006c05f  mov     [rsp+130h+lpOutBuffer], rax
0x18006c064  call    WPP_SF_qqqDqqL
0x18006c069  test    r14, r14
0x18006c06c  jnz     short loc_18006C08A
0x18006c06e  mov     r15d, 80070057h
0x18006c074  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c07b  jb      loc_18006C9A7
0x18006c081  lea     edx, [r14+13h]
0x18006c085  jmp     loc_18006C988
0x18006c08a  mov     rsi, [rsp+130h+var_D0]
0x18006c08f  test    rsi, rsi
0x18006c092  jnz     short loc_18006C0CE
0x18006c094  mov     r15d, 80004003h
0x18006c09a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c0a1  jb      loc_18006C9AC
0x18006c0a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c0ae  lea     edx, [rsi+14h]
0x18006c0b1  mov     r9, r13
0x18006c0b4  mov     dword ptr [rsp+130h+lpOutBuffer], r15d
0x18006c0b9  lea     r8, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x18006c0c0  mov     rcx, [rcx+10h]
0x18006c0c4  call    WPP_SF_qD
0x18006c0c9  jmp     loc_18006C9AC
0x18006c0ce  mov     [rsi], r12
0x18006c0d1  lea     rcx, [r13+18h]
0x18006c0d5  mov     rax, [r14]
0x18006c0d8  mov     rsi, [rax]
0x18006c0db  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18006c0e0  lea     r8, [r13+18h]
0x18006c0e4  mov     rcx, r14
0x18006c0e7  lea     rdx, _GUID_8d4a34c8_16ca_4698_861a_46421c72c817
0x18006c0ee  mov     rax, rsi
0x18006c0f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c0f6  mov     r15d, eax
0x18006c0f9  test    eax, eax
0x18006c0fb  jns     short loc_18006C118
0x18006c0fd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c104  jb      loc_18006C9A7
0x18006c10a  mov     edx, 15h
0x18006c10f  mov     dword ptr [rsp+130h+lpOutBuffer], eax
0x18006c113  jmp     loc_18006C98D
0x18006c118  mov     rcx, [r13+18h]
0x18006c11c  lea     r8, [rbp+37h+var_B0]
0x18006c120  lea     rdx, [rbp+37h+Buf1]
0x18006c124  mov     rax, [rcx]
0x18006c127  mov     rax, [rax+40h]
0x18006c12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c130  mov     r15d, eax
0x18006c133  test    eax, eax
0x18006c135  jns     short loc_18006C14B
0x18006c137  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c13e  jb      loc_18006C9A7
0x18006c144  mov     edx, 16h
0x18006c149  jmp     short loc_18006C10F
0x18006c14b  lea     r14, [r13+358h]
0x18006c152  mov     rcx, [r14]
0x18006c155  mov     [r14], r12
0x18006c158  test    rcx, rcx
0x18006c15b  jz      short loc_18006C169
0x18006c15d  mov     rax, [rcx]
0x18006c160  mov     rax, [rax+10h]
0x18006c164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c169  mov     rdx, [rsp+130h+var_B8]; struct IMFAttributes *
0x18006c16e  mov     r8, r14; struct IFSCCInfoConfiguration **
0x18006c171  mov     rcx, [r13+18h]; struct IDeviceAccessHandler *
0x18006c175  call    ?CreateFSClientContextInfo@FSClientContextInfo@@SAJPEAUIDeviceAccessHandler@@PEAUIMFAttributes@@PEAPEAUIFSCCInfoConfiguration@@@Z; FSClientContextInfo::CreateFSClientContextInfo(IDeviceAccessHandler *,IMFAttributes *,IFSCCInfoConfiguration * *)
0x18006c17a  mov     r15d, eax
0x18006c17d  test    eax, eax
0x18006c17f  jns     short loc_18006C198
0x18006c181  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c188  jb      loc_18006C9A7
0x18006c18e  mov     edx, 17h
0x18006c193  jmp     loc_18006C10F
0x18006c198  mov     r15, [rbp+37h+var_A0]
0x18006c19c  test    r15, r15
0x18006c19f  jz      short loc_18006C218
0x18006c1a1  mov     rax, [r15]
0x18006c1a4  lea     r14, [r13+510h]
0x18006c1ab  mov     rcx, r14
0x18006c1ae  mov     rsi, [rax]
0x18006c1b1  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18006c1b6  mov     r8, r14
0x18006c1b9  lea     rdx, _GUID_82fc34df_7f60_4751_bffd_2aa1f8b269fc
0x18006c1c0  mov     rcx, r15
0x18006c1c3  mov     rax, rsi
0x18006c1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c1cb  mov     r15d, eax
0x18006c1ce  test    eax, eax
0x18006c1d0  jns     short loc_18006C1E9
0x18006c1d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c1d9  jb      loc_18006C9A7
0x18006c1df  mov     edx, 18h
0x18006c1e4  jmp     loc_18006C10F
0x18006c1e9  mov     r14, [r14]
0x18006c1ec  mov     rcx, [r13+18h]
0x18006c1f0  mov     rax, [r14]
0x18006c1f3  mov     rdx, [rcx]
0x18006c1f6  mov     rsi, [rax+28h]
0x18006c1fa  mov     rax, [rdx+78h]
0x18006c1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c203  mov     rdx, rax
0x18006c206  mov     rcx, r14
0x18006c209  mov     rax, rsi
0x18006c20c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c211  lea     r14, [r13+358h]
0x18006c218  mov     rdx, [rbp+37h+var_98]
0x18006c21c  lea     rcx, [r13+3C0h]
0x18006c223  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x18006c228  mov     rdx, [rsp+130h+var_B8]
0x18006c22d  lea     r15, [r13+318h]
0x18006c234  mov     rcx, r15
0x18006c237  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x18006c23c  mov     eax, [rsp+130h+var_C0]
0x18006c240  mov     rcx, [r15]
0x18006c243  mov     [r13+60h], eax
0x18006c247  mov     rax, [rbp+37h+arg_38]
0x18006c24b  movups  xmm0, xmmword ptr [rax]
0x18006c24e  movdqu  xmmword ptr [r13+20h], xmm0
0x18006c254  test    rcx, rcx
0x18006c257  jz      loc_18006C4DD
0x18006c25d  mov     rax, [rcx]
0x18006c260  lea     r8, [r13+32Ch]
0x18006c267  lea     rdx, MEDIA_TELEMETRY_SESSION_ID
0x18006c26e  mov     rax, [rax+50h]
0x18006c272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c277  mov     rcx, [r15]
0x18006c27a  lea     rdx, MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE_INDEX
0x18006c281  xor     r8d, r8d
0x18006c284  call    MFGetAttributeUINT32
0x18006c289  mov     rcx, [r15]
0x18006c28c  lea     rdx, [r13+33Ch]
0x18006c293  mov     [rdx+10h], eax
0x18006c296  lea     rsi, [r13+4E8h]
0x18006c29d  mov     [rsi+10h], eax
0x18006c2a0  mov     r8, rdx
0x18006c2a3  lea     rdx, MF_CAPTURE_ENGINE_SELECTEDCAMERAPROFILE
0x18006c2aa  mov     rax, [rcx]
0x18006c2ad  mov     rax, [rax+50h]
0x18006c2b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c2b6  mov     rcx, [r14]
0x18006c2b9  test    eax, eax
0x18006c2bb  jns     short loc_18006C2E6
0x18006c2bd  movups  xmm0, xmmword ptr cs:_GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data1
0x18006c2c4  movdqu  xmmword ptr [r13+33Ch], xmm0
0x18006c2cd  mov     rax, [rcx]
0x18006c2d0  mov     rax, [rax+60h]
0x18006c2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c2d9  test    eax, eax
0x18006c2db  jnz     short loc_18006C334
0x18006c2dd  movups  xmm0, xmmword ptr cs:_GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data1
0x18006c2e4  jmp     short loc_18006C33B
0x18006c2e6  movups  xmm0, xmmword ptr [r13+33Ch]
0x18006c2ee  movdqu  xmmword ptr [rsi], xmm0
0x18006c2f2  mov     rax, [rcx]
0x18006c2f5  mov     rax, [rax+60h]
0x18006c2f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c2fe  test    eax, eax
0x18006c300  jz      short loc_18006C33F
0x18006c302  mov     rax, [rsi]
0x18006c305  cmp     rax, qword ptr cs:_GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data1
0x18006c30c  jnz     short loc_18006C31B
0x18006c30e  mov     rax, [rsi+8]
0x18006c312  cmp     rax, qword ptr cs:_GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data4
0x18006c319  jz      short loc_18006C334
0x18006c31b  mov     rdx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006c322  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18006c329  cmp     [rsi], rdx
0x18006c32c  jnz     short loc_18006C34D
0x18006c32e  cmp     [rsi+8], rcx
0x18006c332  jnz     short loc_18006C34D
0x18006c334  movups  xmm0, xmmword ptr cs:_GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1
0x18006c33b  movdqu  xmmword ptr [rsi], xmm0
0x18006c33f  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18006c346  mov     rdx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006c34d  mov     rax, [rsi]
0x18006c350  cmp     rax, qword ptr cs:_GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data1
0x18006c357  jnz     loc_18006C49F
0x18006c35d  mov     rax, [rsi+8]
0x18006c361  cmp     rax, qword ptr cs:_GUID_81361b22_700b_4546_a2d4_c52e907bfc27.Data4
0x18006c368  jnz     loc_18006C49F
0x18006c36e  cmp     cs:byte_18010EC4D, 8
0x18006c375  jb      loc_18006C424
0x18006c37b  mov     r12d, [r13+4F8h]
0x18006c382  lea     rcx, [rbp+37h+var_70]; this
0x18006c386  mov     rdx, rsi; struct _GUID *
0x18006c389  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18006c38e  mov     rcx, rax; this
0x18006c391  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18006c396  lea     rcx, [rbp+37h+var_90]; this
0x18006c39a  mov     r15, rax
0x18006c39d  lea     rdx, [rbp+37h+Buf1]; struct _GUID *
0x18006c3a1  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18006c3a6  mov     rcx, rax; this
0x18006c3a9  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18006c3ae  mov     rcx, [r13+358h]
0x18006c3b5  mov     r14, rax
0x18006c3b8  mov     rdx, [rcx]
0x18006c3bb  mov     rax, [rdx+78h]
0x18006c3bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c3c4  mov     rcx, [r13+358h]
0x18006c3cb  mov     esi, eax
0x18006c3cd  mov     rdx, [rcx]
0x18006c3d0  mov     rax, [rdx+88h]
0x18006c3d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18006c3e3  mov     r9, r13
0x18006c3e6  mov     dword ptr [rsp+130h+var_F0], r12d; char
0x18006c3eb  mov     [rsp+130h+lpOverlapped], r15; __int64
0x18006c3f0  mov     [rsp+130h+lpBytesReturned], r14; __int64
0x18006c3f5  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18006c3fc  mov     [rsp+130h+nOutBufferSize], esi; char
0x18006c400  mov     dword ptr [rsp+130h+lpOutBuffer], eax; char
0x18006c404  call    WPP_SF_qdDssd
0x18006c409  mov     r12d, 3
0x18006c40f  lea     rsi, [r13+4E8h]
0x18006c416  lea     r14, [r13+358h]
0x18006c41d  lea     r15, [r13+318h]
0x18006c424  test    r12b, 2
0x18006c428  jz      short loc_18006C437
0x18006c42a  and     r12d, 0FFFFFFFDh
0x18006c42e  lea     rcx, [rbp+37h+var_90]; this
0x18006c432  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18006c437  test    r12b, 1
0x18006c43b  jz      short loc_18006C44A
0x18006c43d  and     r12d, 0FFFFFFFEh
0x18006c441  lea     rcx, [rbp+37h+var_70]; this
0x18006c445  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18006c44a  mov     rcx, [r15]
0x18006c44d  lea     rdx, FS_CLIENTCONTEXT_SELECTED_PROFILE
0x18006c454  mov     r9d, 18h
0x18006c45a  mov     r8, rsi
0x18006c45d  mov     rax, [rcx]
0x18006c460  mov     rax, [rax+0D0h]
0x18006c467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c46c  mov     r15d, eax
0x18006c46f  test    eax, eax
0x18006c471  jns     short loc_18006C48A
0x18006c473  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18006c47a  jb      loc_18006C9A7
0x18006c480  mov     edx, 1Ah
0x18006c485  jmp     loc_18006C10F
0x18006c48a  mov     rcx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x18006c491  lea     r15, [r13+318h]
0x18006c498  mov     rdx, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18006c49f  lea     r8, [r13+33Ch]
0x18006c4a6  cmp     [r8], rdx
0x18006c4a9  jnz     short loc_18006C4C8
0x18006c4ab  cmp     [r8+8], rcx
0x18006c4af  jnz     short loc_18006C4C8
0x18006c4b1  movups  xmm0, xmmword ptr cs:_GUID_b4894d81_62b7_4eec_8740_80658c4a9d3e.Data1
0x18006c4b8  mov     dword ptr [r13+34Ch], 0
0x18006c4c3  movdqu  xmmword ptr [r8], xmm0
0x18006c4c8  mov     rcx, [r14]
0x18006c4cb  mov     rdx, r8
  ... truncated ...
```
