# FSStream::DeliverSampleToSubscribers(IMFSample *,FSMediaTypeInfo const &,bool)

- ea: `0x1800a7f0c`
- end: `0x1800a8954`
- name: `?DeliverSampleToSubscribers@FSStream@@IEAAJPEAUIMFSample@@AEBUFSMediaTypeInfo@@_N@Z`
- size: `2632`
- prototype: `__int64 __fastcall(FSStream *this, struct IMFAttributes *, const struct FSMediaTypeInfo *, char)`
- caller_count: `2`
- callee_count: `23`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800ae23c`
- `0x1800af2d8`

## callees

- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x18000a460`
- `0x1800176b4`
- `0x1800198f4`
- `0x180019a9c`
- `0x18002b498`
- `0x18004d714`
- `0x18004d748`
- `0x18004da70`
- `0x18004fcac`
- `0x18004fcf4`
- `0x18004fd3c`
- `0x18004ff00`
- `0x18005017c`
- `0x180065e54`
- `0x180065ee8`
- `0x1800a7f0c`
- `0x1800b2b40`
- `0x1800ba2bc`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8010`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800a8010`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a86fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8733`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a86fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a8733`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a889e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a8333`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a889e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a80d9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800a80d9`

## pseudocode

```c
__int64 __fastcall FSStream::DeliverSampleToSubscribers(
        FSStream *this,
        struct IMFAttributes *a2,
        const struct FSMediaTypeInfo *a3,
        char a4)
{
  const struct FSMediaTypeInfo *v4; // r13
  struct IMFAttributes *v5; // r14
  FSStream *v6; // rsi
  char v7; // r15
  HRESULT (__stdcall *v8)(IMFAttributes *, const GUID *const, UINT32 *); // rbx
  int (__fastcall ***v9)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v10)(_QWORD, GUID *, __int64 **); // rbx
  HANDLE EventW; // rbx
  __int64 v12; // rax
  int v13; // eax
  unsigned int v14; // edi
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  HRESULT (__stdcall *GetUINT32)(IMFAttributes *, const GUID *const, UINT32 *); // rbx
  int (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // rdi
  int (__fastcall *v21)(_QWORD, GUID *, __int64 **); // rbx
  __int64 v22; // rax
  int v23; // eax
  struct _RTL_CRITICAL_SECTION *v24; // rbx
  unsigned int v25; // r12d
  GuidTrace *v26; // rax
  const char *v27; // r13
  FSString *v28; // rax
  const char *v29; // r12
  char v30; // r15
  char v31; // r14
  char v32; // al
  int v33; // edi
  char v34; // bl
  int v35; // esi
  char v36; // al
  bool v37; // zf
  __int64 Sent; // rax
  GuidTrace *v39; // rax
  const char *String; // r13
  FSString *v41; // rax
  const char *v42; // r12
  char Drop; // r15
  char v44; // r14
  char Recv; // al
  int v46; // edi
  char v47; // bl
  int v48; // esi
  char v49; // al
  __int64 v50; // rcx
  __int64 v51; // rcx
  void (*v52)(void); // rax
  __int64 v53; // rcx
  int v54; // eax
  __int64 v55; // rdx
  unsigned int v56; // edi
  __int64 v57; // rbx
  __int64 v58; // r15
  int v59; // eax
  unsigned int v60; // r15d
  int v61; // eax
  __int64 v62; // rdi
  __int64 v63; // rbx
  int v64; // eax
  __int64 v65; // r9
  char v67; // [rsp+30h] [rbp-E8h]
  char v68; // [rsp+30h] [rbp-E8h]
  __int64 v69; // [rsp+60h] [rbp-B8h]
  __int64 v70; // [rsp+60h] [rbp-B8h]
  char v71[8]; // [rsp+98h] [rbp-80h] BYREF
  char v72[8]; // [rsp+A0h] [rbp-78h] BYREF
  unsigned int v73; // [rsp+A8h] [rbp-70h]
  __int64 *v74; // [rsp+B0h] [rbp-68h] BYREF
  int (__fastcall ***v75)(_QWORD, GUID *, __int64 **); // [rsp+B8h] [rbp-60h] BYREF
  char v76[4]; // [rsp+C0h] [rbp-58h]
  char v77[4]; // [rsp+C4h] [rbp-54h]
  char v78[8]; // [rsp+C8h] [rbp-50h]
  struct CFSFrameSource *v79; // [rsp+D0h] [rbp-48h] BYREF
  __int64 v80; // [rsp+D8h] [rbp-40h] BYREF
  unsigned int v81; // [rsp+E0h] [rbp-38h]
  __int64 v82; // [rsp+E4h] [rbp-34h]
  __int64 v83; // [rsp+F0h] [rbp-28h] BYREF
  unsigned int v84; // [rsp+F8h] [rbp-20h]
  __int64 v85; // [rsp+FCh] [rbp-1Ch]
  _BYTE v86[24]; // [rsp+108h] [rbp-10h] BYREF
  _BYTE v87[104]; // [rsp+120h] [rbp+8h] BYREF

  v4 = a3;
  *(_DWORD *)v71 = 0;
  v5 = a2;
  v79 = 0;
  v6 = this;
  v75 = 0;
  v7 = 0;
  v74 = 0;
  v83 = 0;
  v85 = 0;
  v84 = 0;
  v80 = 0;
  v82 = 0;
  v81 = 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerDX12Support>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FrameServerDX12Support>::GetImpl'::`2'::impl) )
  {
    if ( !v5 )
      goto LABEL_33;
    GetUINT32 = v5->lpVtbl[1].GetUINT32;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
    if ( ((int (__fastcall *)(struct IMFAttributes *, _QWORD, _QWORD))GetUINT32)(v5, 0, &v75) < 0 )
      goto LABEL_33;
    v20 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
    v21 = **v75;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v74);
    if ( v21(v20, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v74) < 0 )
      goto LABEL_33;
    *(_QWORD *)v72 = 0;
    *(_QWORD *)v71 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(*v74 + 24))(
            v74,
            &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
            v72);
    v14 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_19;
      v17 = 231;
      goto LABEL_18;
    }
    v22 = **(_QWORD **)v72;
    *(_QWORD *)v71 = 0;
    (*(void (__fastcall **)(_QWORD, char *))(v22 + 24))(*(_QWORD *)v72, v71);
    v16 = FSHelper_WaitOnDeviceEnqueueSetEvent(*(_QWORD *)v71);
    v14 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_19;
      v17 = 232;
      goto LABEL_18;
    }
LABEL_32:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v71);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v72);
    goto LABEL_33;
  }
  if ( !v5 )
    goto LABEL_33;
  v8 = v5->lpVtbl[1].GetUINT32;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
  if ( ((int (__fastcall *)(struct IMFAttributes *, _QWORD, _QWORD))v8)(v5, 0, &v75) < 0 )
    goto LABEL_33;
  v9 = (int (__fastcall ***)(_QWORD, _QWORD, _QWORD))v75;
  v10 = **v75;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v74);
  if ( v10(v9, &GUID_e7174cfa_1c9e_48b1_8866_626226bfc258, &v74) < 0 )
    goto LABEL_33;
  *(_QWORD *)v71 = 0;
  if ( !(unsigned __int8)FSHelper_IsCrossAdapterBuffer(v75, &GUID_00000000_0000_0000_0000_000000000000, 0) )
  {
    *(_QWORD *)v72 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64 *, GUID *, char *))(*v74 + 24))(
            v74,
            &GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c,
            v72);
    v14 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_19:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v71);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v72);
        goto LABEL_97;
      }
      v17 = 229;
LABEL_18:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, v6, v16);
      goto LABEL_19;
    }
    v18 = **(_QWORD **)v72;
    *(_QWORD *)v71 = 0;
    (*(void (__fastcall **)(_QWORD, char *))(v18 + 24))(*(_QWORD *)v72, v71);
    v16 = FSHelper_WaitOnDeviceEnqueueSetEvent(*(_QWORD *)v71);
    v14 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_19;
      v17 = 230;
      goto LABEL_18;
    }
    goto LABEL_32;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)v72 = EventW;
  v12 = *v74;
  *(_QWORD *)v71 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64 *, __int64 *, GUID *, char *))(v12 + 40))(
          v74,
          MF_D3D12_SYNCHRONIZATION_OBJECT,
          &GUID_09d0f835_92ff_4e53_8efa_40faa551f233,
          v71);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_10:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v72);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v71);
      goto LABEL_97;
    }
    v15 = 227;
LABEL_9:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, v6, v13);
    goto LABEL_10;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, HANDLE))(**(_QWORD **)v71 + 40LL))(*(_QWORD *)v71, EventW);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_10;
    v15 = 228;
    goto LABEL_9;
  }
  WaitForSingleObject(EventW, 0xFFFFFFFF);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v72);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v71);
LABEL_33:
  v23 = CFSFrameSource::CreateFSFrame(
          v5,
          v4,
          _InterlockedCompareExchange((volatile signed __int32 *)v6 + 101, 0, 0) != 0,
          &v79);
  v73 = v23;
  v14 = v23;
  if ( v23 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 233, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, v6, v23);
    goto LABEL_97;
  }
  v24 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 408);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 408));
  v25 = *((_DWORD *)v6 + 23) | 0x80000000;
  if ( !a4 )
    v25 = *((_DWORD *)v6 + 23);
  *(_DWORD *)v78 = v25;
  FSStatTracker::IncSent((FSStream *)((char *)v6 + 568));
  if ( (unsigned __int8)byte_18010EC53 < 0x10u )
  {
    Sent = FSStatTracker::GetSent((FSStream *)((char *)v6 + 568));
    if ( Sent != 10 * (Sent / 10) )
      goto LABEL_52;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      *(_DWORD *)v71 = *((_DWORD *)v4 + 9);
      *(_DWORD *)v72 = *((_DWORD *)v4 + 8);
      v39 = GuidTrace::GuidTrace((GuidTrace *)v87, (const struct _GUID *)v4 + 1);
      String = GuidTrace::GetString(v39);
      *(_DWORD *)v77 = *((_DWORD *)a3 + 1);
      *(_DWORD *)v76 = *(_DWORD *)a3;
      v41 = SampleTrace::SampleTrace((SampleTrace *)v86, (struct IMFSample *)v5);
      v42 = FSString::GetString(v41);
      Drop = FSStatTracker::GetDrop((FSStream *)((char *)v6 + 568));
      v44 = FSStatTracker::GetSent((FSStream *)((char *)v6 + 568));
      Recv = FSStatTracker::GetRecv((FSStream *)((char *)v6 + 568));
      v46 = *((_DWORD *)v6 + 40);
      v47 = Recv;
      v48 = *((_DWORD *)v6 + 22);
      v49 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42));
      v70 = (__int64)v42;
      v25 = *(_DWORD *)v78;
      v68 = v48;
      v6 = this;
      WPP_SF_qdDDdiiisdDsdd(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        v49,
        v68,
        v78[0],
        v46,
        v47,
        v44,
        Drop,
        v70,
        v76[0],
        v77[0],
        (__int64)String,
        v72[0],
        v71[0]);
      v5 = a2;
      v24 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 408);
      v4 = a3;
      v7 = 12;
    }
    if ( (v7 & 8) != 0 )
    {
      v7 &= ~8u;
      FSString::~FSString((FSString *)v86);
    }
    v37 = (v7 & 4) == 0;
  }
  else
  {
    if ( (unsigned __int8)byte_18010EC53 >= 8u )
    {
      *(_DWORD *)v76 = *((_DWORD *)v4 + 9);
      *(_DWORD *)v77 = *((_DWORD *)v4 + 8);
      v26 = GuidTrace::GuidTrace((GuidTrace *)v87, (const struct _GUID *)v4 + 1);
      v27 = GuidTrace::GetString(v26);
      *(_DWORD *)v72 = *((_DWORD *)a3 + 1);
      *(_DWORD *)v71 = *(_DWORD *)a3;
      v28 = SampleTrace::SampleTrace((SampleTrace *)v86, (struct IMFSample *)v5);
      v29 = FSString::GetString(v28);
      v30 = FSStatTracker::GetDrop((FSStream *)((char *)v6 + 568));
      v31 = FSStatTracker::GetSent((FSStream *)((char *)v6 + 568));
      v32 = FSStatTracker::GetRecv((FSStream *)((char *)v6 + 568));
      v33 = *((_DWORD *)v6 + 40);
      v34 = v32;
      v35 = *((_DWORD *)v6 + 22);
      v36 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 42) + 24LL))(*((_QWORD *)this + 42));
      v69 = (__int64)v29;
      v25 = *(_DWORD *)v78;
      v67 = v35;
      v6 = this;
      WPP_SF_qdDDdiiisdDsdd(
        *((_QWORD *)WPP_GLOBAL_Control + 57),
        v36,
        v67,
        v78[0],
        v33,
        v34,
        v31,
        v30,
        v69,
        v71[0],
        v72[0],
        (__int64)v27,
        v77[0],
        v76[0]);
      v5 = a2;
      v24 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 408);
      v4 = a3;
      v7 = 3;
    }
    if ( (v7 & 2) != 0 )
    {
      v7 &= ~2u;
      FSString::~FSString((FSString *)v86);
    }
    v37 = (v7 & 1) == 0;
  }
  if ( !v37 )
    FSString::~FSString((FSString *)v87);
LABEL_52:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CameraTelemetryTracking>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CameraTelemetryTracking>::GetImpl'::`2'::impl) )
    goto LABEL_61;
  *(_QWORD *)v71 = 0;
  if ( v5 )
    ((void (__fastcall *)(struct IMFAttributes *, char *))v5->lpVtbl[1].Release)(v5, v71);
  v50 = *((_QWORD *)v6 + 93);
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 48LL))(v50);
    v53 = *((_QWORD *)v6 + 94);
    if ( !v53 )
      goto LABEL_61;
    v52 = *(void (**)(void))(*(_QWORD *)v53 + 40LL);
  }
  else
  {
    v51 = *((_QWORD *)v6 + 94);
    if ( !v51 )
      goto LABEL_61;
    v52 = *(void (**)(void))(*(_QWORD *)v51 + 48LL);
  }
  v52();
LABEL_61:
  if ( !(unsigned int)CTUnkArray<FSCallback<IFSSourceMediaEventCallback,unsigned __int64,enum __MIDL___MIDL_itf_fsclienttypes_0000_0000_0001>>::Add(
                        &v80,
                        (char *)v6 + 472) )
  {
    v54 = -2147024882;
    v14 = -2147024882;
    if ( g_wppLevels )
    {
      v55 = 236;
LABEL_64:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v55, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, v6, v54);
      goto LABEL_65;
    }
    goto LABEL_65;
  }
  if ( !(unsigned int)CTUnkArray<FSCallback<IFSSourceMediaEventCallback,unsigned __int64,enum __MIDL___MIDL_itf_fsclienttypes_0000_0000_0001>>::Add(
                        &v83,
                        (char *)v6 + 448) )
  {
    v54 = -2147024882;
    v14 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_65;
    v55 = 237;
    goto LABEL_64;
  }
  LeaveCriticalSection(v24);
  v56 = v81;
  v57 = 0;
  if ( v81 )
  {
    v58 = v80;
    do
    {
      v59 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, struct IMFAttributes *))(**(_QWORD **)(*(_QWORD *)(v58 + 8 * v57) + 16LL)
                                                                                      + 24LL))(
              *(_QWORD *)(*(_QWORD *)(v58 + 8 * v57) + 16LL),
              *((unsigned int *)v6 + 23),
              *(_QWORD *)(*(_QWORD *)(v58 + 8 * v57) + 24LL),
              v5);
      v73 = v59;
      if ( v59 < 0 )
      {
        if ( byte_18010EC4D )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            238,
            &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
            v6,
            v59);
        v73 = 0;
      }
      v57 = (unsigned int)(v57 + 1);
    }
    while ( (unsigned int)v57 < v56 );
  }
  v60 = v84;
  if ( !v84 )
  {
LABEL_88:
    if ( !v5 || !*((_QWORD *)v6 + 90) )
    {
      v14 = v73;
      goto LABEL_97;
    }
    v24 = (struct _RTL_CRITICAL_SECTION *)((char *)v6 + 24);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v6 + 24));
    if ( *((_DWORD *)v6 + 53) )
    {
      v14 = -1072873851;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          241,
          &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
          v6,
          -1072873851);
      goto LABEL_65;
    }
    LOBYTE(v65) = a4;
    v54 = (*(__int64 (__fastcall **)(_QWORD, struct IMFAttributes *, const struct FSMediaTypeInfo *, __int64))(**((_QWORD **)v6 + 90) + 96LL))(
            *((_QWORD *)v6 + 90),
            v5,
            v4,
            v65);
    v14 = v54;
    if ( v54 < 0 && g_wppLevels )
    {
      v55 = 242;
      goto LABEL_64;
    }
LABEL_65:
    LeaveCriticalSection(v24);
    goto LABEL_97;
  }
  *(_QWORD *)v71 = 0;
  v61 = (**(__int64 (__fastcall ***)(struct CFSFrameSource *, GUID *, char *))v79)(
          v79,
          &GUID_85fff18a_bc91_40e6_ab35_4d97f658fe22,
          v71);
  v14 = v61;
  if ( v61 >= 0 )
  {
    v62 = v83;
    v63 = 0;
    do
    {
      v64 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)(*(_QWORD *)(v62 + 8 * v63) + 16LL)
                                                                      + 24LL))(
              *(_QWORD *)(*(_QWORD *)(v62 + 8 * v63) + 16LL),
              v25,
              *(_QWORD *)(*(_QWORD *)(v62 + 8 * v63) + 24LL),
              *(_QWORD *)v71);
      v73 = v64;
      if ( v64 < 0 )
      {
        if ( byte_18010EC4D )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            240,
            &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids,
            v6,
            v64);
        v73 = 0;
      }
      v63 = (unsigned int)(v63 + 1);
    }
    while ( (unsigned int)v63 < v60 );
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v71);
    goto LABEL_88;
  }
  if ( g_wppLevels )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids, v6, v61);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v71);
LABEL_97:
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v80);
  CTUnkArray<SensorTransformContextStream>::~CTUnkArray<SensorTransformContextStream>(&v83);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v74);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v79);
  return v14;
}

```

## disassembly

```asm
0x1800a7f0c  mov     rax, rsp
0x1800a7f0f  mov     [rax+20h], r9b
0x1800a7f13  mov     [rax+18h], r8
0x1800a7f17  mov     [rax+10h], rdx
0x1800a7f1b  mov     [rax+8], rcx
0x1800a7f1f  push    rbp
0x1800a7f20  push    rbx
0x1800a7f21  push    rsi
0x1800a7f22  push    rdi
0x1800a7f23  push    r12
0x1800a7f25  push    r13
0x1800a7f27  push    r14
0x1800a7f29  push    r15
0x1800a7f2b  lea     rbp, [rax-78h]
0x1800a7f2f  sub     rsp, 148h
0x1800a7f36  xor     r12d, r12d
0x1800a7f39  mov     r13, r8
0x1800a7f3c  mov     dword ptr [rbp+70h+var_F0], r12d
0x1800a7f40  mov     r14, rdx
0x1800a7f43  mov     [rbp+70h+var_B8], r12
0x1800a7f47  mov     rsi, rcx
0x1800a7f4a  mov     [rbp+70h+var_D0], r12
0x1800a7f4e  mov     r15d, r12d
0x1800a7f51  mov     [rbp+70h+var_D8], r12
0x1800a7f55  mov     [rbp+70h+var_98], r12
0x1800a7f59  mov     [rbp+70h+var_8C], r12
0x1800a7f5d  mov     [rbp+70h+var_90], r12d
0x1800a7f61  mov     [rbp+70h+var_B0], r12
0x1800a7f65  mov     [rbp+70h+var_A4], r12
0x1800a7f69  mov     [rbp+70h+var_A8], r12d
0x1800a7f6d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FrameServerDX12Support@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerDX12Support@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerDX12Support> `wil::Feature<__WilFeatureTraits_Feature_FrameServerDX12Support>::GetImpl(void)'::`2'::impl
0x1800a7f74  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FrameServerDX12Support@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FrameServerDX12Support>::__private_IsEnabled(void)
0x1800a7f79  test    al, al
0x1800a7f7b  jz      loc_1800A81B7
0x1800a7f81  test    r14, r14
0x1800a7f84  jz      loc_1800A82C8
0x1800a7f8a  mov     rax, [r14]
0x1800a7f8d  lea     rcx, [rbp+70h+var_D0]
0x1800a7f91  mov     rbx, [rax+140h]
0x1800a7f98  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a7f9d  lea     r8, [rbp+70h+var_D0]
0x1800a7fa1  xor     edx, edx
0x1800a7fa3  mov     rcx, r14
0x1800a7fa6  mov     rax, rbx
0x1800a7fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7fae  test    eax, eax
0x1800a7fb0  js      loc_1800A82C8
0x1800a7fb6  mov     rdi, [rbp+70h+var_D0]
0x1800a7fba  lea     rcx, [rbp+70h+var_D8]
0x1800a7fbe  mov     rax, [rdi]
0x1800a7fc1  mov     rbx, [rax]
0x1800a7fc4  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a7fc9  lea     r8, [rbp+70h+var_D8]
0x1800a7fcd  mov     rcx, rdi
0x1800a7fd0  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x1800a7fd7  mov     rax, rbx
0x1800a7fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7fdf  test    eax, eax
0x1800a7fe1  js      loc_1800A82C8
0x1800a7fe7  mov     rcx, [rbp+70h+var_D0]
0x1800a7feb  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x1800a7ff2  xor     r8d, r8d
0x1800a7ff5  call    FSHelper_IsCrossAdapterBuffer
0x1800a7ffa  mov     qword ptr [rbp+70h+var_F0], r12
0x1800a7ffe  test    al, al
0x1800a8000  jz      loc_1800A80F6
0x1800a8006  xor     r9d, r9d; lpName
0x1800a8009  xor     r8d, r8d; bInitialState
0x1800a800c  xor     edx, edx; bManualReset
0x1800a800e  xor     ecx, ecx; lpEventAttributes
0x1800a8010  call    cs:__imp_CreateEventW
0x1800a8016  mov     rcx, qword ptr [rbp+70h+var_F0]
0x1800a801a  mov     rbx, rax
0x1800a801d  mov     rdi, [rbp+70h+var_D8]
0x1800a8021  mov     qword ptr [rbp+70h+var_E8], rax
0x1800a8025  mov     rax, [rdi]
0x1800a8028  mov     qword ptr [rbp+70h+var_F0], r15
0x1800a802c  mov     r12, [rax+28h]
0x1800a8030  test    rcx, rcx
0x1800a8033  jz      short loc_1800A8041
0x1800a8035  mov     rdx, [rcx]
0x1800a8038  mov     rax, [rdx+10h]
0x1800a803c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8041  lea     r9, [rbp+70h+var_F0]
0x1800a8045  mov     rcx, rdi
0x1800a8048  lea     r8, _GUID_09d0f835_92ff_4e53_8efa_40faa551f233
0x1800a804f  mov     rax, r12
0x1800a8052  lea     rdx, MF_D3D12_SYNCHRONIZATION_OBJECT
0x1800a8059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a805e  xor     r12d, r12d
0x1800a8061  mov     edi, eax
0x1800a8063  test    eax, eax
0x1800a8065  jns     short loc_1800A80AA
0x1800a8067  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a806e  jb      short loc_1800A8093
0x1800a8070  mov     edx, 0E3h
0x1800a8075  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a807c  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a8083  mov     r9, rsi
0x1800a8086  mov     dword ptr [rsp+180h+var_160], eax
0x1800a808a  mov     rcx, [rcx+10h]
0x1800a808e  call    WPP_SF_qD
0x1800a8093  lea     rcx, [rbp+70h+var_E8]
0x1800a8097  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a809c  lea     rcx, [rbp+70h+var_F0]; void *
0x1800a80a0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a80a5  jmp     loc_1800A8911
0x1800a80aa  mov     rcx, qword ptr [rbp+70h+var_F0]
0x1800a80ae  mov     rdx, rbx
0x1800a80b1  mov     rax, [rcx]
0x1800a80b4  mov     rax, [rax+28h]
0x1800a80b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a80bd  mov     edi, eax
0x1800a80bf  test    eax, eax
0x1800a80c1  jns     short loc_1800A80D3
0x1800a80c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a80ca  jb      short loc_1800A8093
0x1800a80cc  mov     edx, 0E4h
0x1800a80d1  jmp     short loc_1800A8075
0x1800a80d3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800a80d6  mov     rcx, rbx; hHandle
0x1800a80d9  call    cs:__imp_WaitForSingleObject
0x1800a80df  lea     rcx, [rbp+70h+var_E8]
0x1800a80e3  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a80e8  lea     rcx, [rbp+70h+var_F0]; void *
0x1800a80ec  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a80f1  jmp     loc_1800A82C8
0x1800a80f6  mov     rcx, [rbp+70h+var_D8]
0x1800a80fa  lea     r8, [rbp+70h+var_E8]
0x1800a80fe  mov     qword ptr [rbp+70h+var_E8], r12
0x1800a8102  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800a8109  mov     rax, [rcx]
0x1800a810c  mov     rax, [rax+18h]
0x1800a8110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8115  mov     edi, eax
0x1800a8117  test    eax, eax
0x1800a8119  jns     short loc_1800A815E
0x1800a811b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a8122  jb      short loc_1800A8147
0x1800a8124  mov     edx, 0E5h
0x1800a8129  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8130  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a8137  mov     r9, rsi
0x1800a813a  mov     dword ptr [rsp+180h+var_160], eax
0x1800a813e  mov     rcx, [rcx+10h]
0x1800a8142  call    WPP_SF_qD
0x1800a8147  lea     rcx, [rbp+70h+var_F0]; void *
0x1800a814b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a8150  lea     rcx, [rbp+70h+var_E8]; void *
0x1800a8154  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a8159  jmp     loc_1800A8911
0x1800a815e  mov     rcx, qword ptr [rbp+70h+var_F0]
0x1800a8162  mov     rbx, qword ptr [rbp+70h+var_E8]
0x1800a8166  mov     rax, [rbx]
0x1800a8169  mov     qword ptr [rbp+70h+var_F0], r12
0x1800a816d  mov     rdi, [rax+18h]
0x1800a8171  test    rcx, rcx
0x1800a8174  jz      short loc_1800A8182
0x1800a8176  mov     rdx, [rcx]
0x1800a8179  mov     rax, [rdx+10h]
0x1800a817d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8182  lea     rdx, [rbp+70h+var_F0]
0x1800a8186  mov     rcx, rbx
0x1800a8189  mov     rax, rdi
0x1800a818c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8191  mov     rcx, qword ptr [rbp+70h+var_F0]
0x1800a8195  call    FSHelper_WaitOnDeviceEnqueueSetEvent
0x1800a819a  mov     edi, eax
0x1800a819c  test    eax, eax
0x1800a819e  jns     loc_1800A82B6
0x1800a81a4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a81ab  jb      short loc_1800A8147
0x1800a81ad  mov     edx, 0E6h
0x1800a81b2  jmp     loc_1800A8129
0x1800a81b7  test    r14, r14
0x1800a81ba  jz      loc_1800A82C8
0x1800a81c0  mov     rax, [r14]
0x1800a81c3  lea     rcx, [rbp+70h+var_D0]
0x1800a81c7  mov     rbx, [rax+140h]
0x1800a81ce  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a81d3  lea     r8, [rbp+70h+var_D0]
0x1800a81d7  xor     edx, edx
0x1800a81d9  mov     rcx, r14
0x1800a81dc  mov     rax, rbx
0x1800a81df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a81e4  test    eax, eax
0x1800a81e6  js      loc_1800A82C8
0x1800a81ec  mov     rdi, [rbp+70h+var_D0]
0x1800a81f0  lea     rcx, [rbp+70h+var_D8]
0x1800a81f4  mov     rax, [rdi]
0x1800a81f7  mov     rbx, [rax]
0x1800a81fa  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800a81ff  lea     r8, [rbp+70h+var_D8]
0x1800a8203  mov     rcx, rdi
0x1800a8206  lea     rdx, _GUID_e7174cfa_1c9e_48b1_8866_626226bfc258
0x1800a820d  mov     rax, rbx
0x1800a8210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8215  test    eax, eax
0x1800a8217  js      loc_1800A82C8
0x1800a821d  mov     rcx, [rbp+70h+var_D8]
0x1800a8221  lea     r8, [rbp+70h+var_E8]
0x1800a8225  mov     qword ptr [rbp+70h+var_E8], r12
0x1800a8229  lea     rdx, _GUID_6f15aaf2_d208_4e89_9ab4_489535d34f9c
0x1800a8230  mov     qword ptr [rbp+70h+var_F0], r12
0x1800a8234  mov     rax, [rcx]
0x1800a8237  mov     rax, [rax+18h]
0x1800a823b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8240  mov     edi, eax
0x1800a8242  test    eax, eax
0x1800a8244  jns     short loc_1800A825D
0x1800a8246  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a824d  jb      loc_1800A8147
0x1800a8253  mov     edx, 0E7h
0x1800a8258  jmp     loc_1800A8129
0x1800a825d  mov     rcx, qword ptr [rbp+70h+var_F0]
0x1800a8261  mov     rbx, qword ptr [rbp+70h+var_E8]
0x1800a8265  mov     rax, [rbx]
0x1800a8268  mov     qword ptr [rbp+70h+var_F0], r12
0x1800a826c  mov     rdi, [rax+18h]
0x1800a8270  test    rcx, rcx
0x1800a8273  jz      short loc_1800A8281
0x1800a8275  mov     rdx, [rcx]
0x1800a8278  mov     rax, [rdx+10h]
0x1800a827c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8281  lea     rdx, [rbp+70h+var_F0]
0x1800a8285  mov     rcx, rbx
0x1800a8288  mov     rax, rdi
0x1800a828b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a8290  mov     rcx, qword ptr [rbp+70h+var_F0]
0x1800a8294  call    FSHelper_WaitOnDeviceEnqueueSetEvent
0x1800a8299  mov     edi, eax
0x1800a829b  test    eax, eax
0x1800a829d  jns     short loc_1800A82B6
0x1800a829f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a82a6  jb      loc_1800A8147
0x1800a82ac  mov     edx, 0E8h
0x1800a82b1  jmp     loc_1800A8129
0x1800a82b6  lea     rcx, [rbp+70h+var_F0]; void *
0x1800a82ba  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a82bf  lea     rcx, [rbp+70h+var_E8]; void *
0x1800a82c3  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800a82c8  mov     ecx, r12d
0x1800a82cb  xor     eax, eax
0x1800a82cd  lock cmpxchg [rsi+194h], ecx
0x1800a82d5  mov     r8d, r12d
0x1800a82d8  lea     r9, [rbp+70h+var_B8]; struct CFSFrameSource **
0x1800a82dc  setnz   r8b; int
0x1800a82e0  mov     rdx, r13; struct FSMediaTypeInfo *
0x1800a82e3  mov     rcx, r14; struct IMFSample *
0x1800a82e6  call    ?CreateFSFrame@CFSFrameSource@@SAJPEAUIMFSample@@AEBUFSMediaTypeInfo@@HPEAPEAV1@@Z; CFSFrameSource::CreateFSFrame(IMFSample *,FSMediaTypeInfo const &,int,CFSFrameSource * *)
0x1800a82eb  mov     [rbp+70h+var_E0], eax
0x1800a82ee  mov     edi, eax
0x1800a82f0  test    eax, eax
0x1800a82f2  jns     short loc_1800A8329
0x1800a82f4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a82fb  jb      loc_1800A8911
0x1800a8301  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a8308  lea     r8, WPP_3d71de32a114311081fd3756ca56d7b5_Traceguids
0x1800a830f  mov     edx, 0E9h
0x1800a8314  mov     dword ptr [rsp+180h+var_160], eax
0x1800a8318  mov     r9, rsi
0x1800a831b  mov     rcx, [rcx+10h]
0x1800a831f  call    WPP_SF_qD
0x1800a8324  jmp     loc_1800A8911
0x1800a8329  lea     rbx, [rsi+198h]
0x1800a8330  mov     rcx, rbx; lpCriticalSection
0x1800a8333  call    cs:__imp_EnterCriticalSection
0x1800a8339  mov     r12d, [rsi+5Ch]
0x1800a833d  lea     rdi, [rsi+238h]
0x1800a8344  bts     r12d, 1Fh
0x1800a8349  mov     rcx, rdi; this
0x1800a834c  cmp     [rbp+70h+arg_18], r15b
0x1800a8353  cmovz   r12d, [rsi+5Ch]
0x1800a8358  mov     dword ptr [rbp+70h+var_C0], r12d
0x1800a835c  call    ?IncSent@FSStatTracker@@QEAA_JXZ; FSStatTracker::IncSent(void)
0x1800a8361  mov     al, cs:byte_18010EC53
0x1800a8367  cmp     al, 10h
0x1800a8369  jb      loc_1800A84B0
0x1800a836f  cmp     al, 8
0x1800a8371  jb      loc_1800A8494
0x1800a8377  mov     eax, [r13+24h]
0x1800a837b  lea     rdx, [r13+10h]; struct _GUID *
0x1800a837f  mov     dword ptr [rbp+70h+var_C8], eax
0x1800a8382  lea     rcx, [rbp+70h+var_68]; this
0x1800a8386  mov     eax, [r13+20h]
0x1800a838a  mov     dword ptr [rbp+70h+var_C4], eax
0x1800a838d  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800a8392  mov     rcx, rax; this
0x1800a8395  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800a839a  mov     rcx, [rbp+70h+arg_10]
0x1800a83a1  mov     r13, rax
0x1800a83a4  mov     rdx, r14; struct IMFSample *
0x1800a83a7  mov     eax, [rcx+4]
0x1800a83aa  mov     dword ptr [rbp+70h+var_E8], eax
0x1800a83ad  mov     eax, [rcx]
0x1800a83af  lea     rcx, [rbp+70h+var_80]; this
0x1800a83b3  mov     dword ptr [rbp+70h+var_F0], eax
0x1800a83b6  call    ??0SampleTrace@@QEAA@PEAUIMFSample@@@Z; SampleTrace::SampleTrace(IMFSample *)
0x1800a83bb  mov     rcx, rax; this
0x1800a83be  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
  ... truncated ...
```
