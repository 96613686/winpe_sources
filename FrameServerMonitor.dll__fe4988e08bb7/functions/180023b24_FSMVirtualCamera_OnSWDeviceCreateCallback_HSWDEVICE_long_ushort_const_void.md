# FSMVirtualCamera::OnSWDeviceCreateCallback(HSWDEVICE__ *,long,ushort const *,void *)

- ea: `0x180023b24`
- end: `0x180024787`
- name: `?OnSWDeviceCreateCallback@FSMVirtualCamera@@IEAAXPEAUHSWDEVICE__@@JPEBGPEAX@Z`
- size: `3171`
- prototype: `void __usercall(FSMVirtualCamera *__hidden this@<rcx>, struct HSWDEVICE__ *@<rdx>, int@<r8d>, const unsigned __int16 *@<r9>, void *)`
- caller_count: `1`
- callee_count: `28`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024a80`

## callees

- `0x180001dc0`
- `0x180002346`
- `0x180002668`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006ae8`
- `0x18000d060`
- `0x18000d594`
- `0x180011438`
- `0x180018494`
- `0x18001e848`
- `0x18001e86c`
- `0x18001ec2c`
- `0x18002257c`
- `0x180022edc`
- `0x180023b24`
- `0x180025410`
- `0x180025578`
- `0x1800255a0`
- `0x180025ce8`
- `0x180026850`
- `0x18002fa3c`
- `0x18002fa70`
- `0x18002fd04`
- `0x18003f7ec`
- `0x1800426d8`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b5f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180023b5f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024766`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024766`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002471e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002471e`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x18002415b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x1800245cf`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x18002415b`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceSetState` at `0x1800245cf`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x1800246a7`
- `api-ms-win-devices-swdevice-l1-1-0!SwMemFree` at `0x1800246a7`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x1800240a1`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x1800240d9`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x1800240a1`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfacePropertySet` at `0x1800240d9`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x180023fa8`
- `api-ms-win-devices-swdevice-l1-1-0!SwDeviceInterfaceRegister` at `0x180023fa8`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x180023c26`
- `api-ms-win-devices-swdevice-l1-1-1!SwDeviceSetLifetime` at `0x180023c26`

## pseudocode

```c
void __fastcall FSMVirtualCamera::OnSWDeviceCreateCallback(
        FSMVirtualCamera *this,
        struct HSWDEVICE__ *a2,
        char a3,
        const char *a4,
        HANDLE hEvent)
{
  _QWORD *v6; // r13
  int v10; // edx
  int v11; // r8d
  const char *v12; // rax
  unsigned __int64 v13; // rdi
  void *v14; // rax
  void *v15; // r12
  int v16; // eax
  int v17; // edi
  __int64 v18; // rdx
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall **v20)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rdi
  __int64 (__fastcall **v22)(_QWORD, GUID *, __int64 *); // rax
  const struct std::nothrow_t *v23; // rdx
  __int64 v24; // rdi
  FSString *v25; // rax
  const char *String; // rax
  int v27; // eax
  __int64 v28; // rdx
  const struct std::nothrow_t *v29; // rdx
  __int64 i; // rdi
  FSString *v31; // rax
  const char *v32; // rax
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  int v38; // eax
  const struct std::nothrow_t *v39; // rdx
  __int64 v40; // rdi
  __int64 v41; // rdi
  GuidTrace *v42; // rax
  const char *v43; // rax
  __int64 v44; // rcx
  __int64 v45; // rdx
  __int64 v46; // rdi
  int v47; // eax
  unsigned int v48; // r8d
  unsigned int v49; // r9d
  const char *v50; // rcx
  __int64 v51; // r12
  int updated; // eax
  __int64 v53; // rdx
  __int64 v54; // r12
  const char *v55; // rcx
  __int64 j; // r12
  __int64 v57; // rdx
  const struct std::nothrow_t *v58; // rdx
  _QWORD *v59; // [rsp+40h] [rbp-71h]
  unsigned int v60; // [rsp+48h] [rbp-69h] BYREF
  struct _DEVPROPERTY *v61; // [rsp+50h] [rbp-61h] BYREF
  void *v62; // [rsp+58h] [rbp-59h]
  int v63; // [rsp+60h] [rbp-51h]
  __int64 v64; // [rsp+68h] [rbp-49h] BYREF
  __int64 v65; // [rsp+70h] [rbp-41h] BYREF
  __int64 v66; // [rsp+78h] [rbp-39h] BYREF
  __int64 v67; // [rsp+80h] [rbp-31h]
  struct IMFAttributes *v68; // [rsp+88h] [rbp-29h] BYREF
  __int64 v69; // [rsp+90h] [rbp-21h]
  void *v70; // [rsp+98h] [rbp-19h] BYREF
  void *v71; // [rsp+A0h] [rbp-11h] BYREF
  _BYTE v72[88]; // [rsp+A8h] [rbp-9h] BYREF
  unsigned int v73; // [rsp+110h] [rbp+5Fh] BYREF
  struct HSWDEVICE__ *v74; // [rsp+118h] [rbp+67h]

  v74 = a2;
  v73 = 0;
  v6 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v61 = 0;
  v71 = 0;
  v60 = 0;
  v70 = 0;
  v73 = 0;
  v66 = 0;
  v65 = 0;
  v68 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v12 = L"<nullptr>";
    if ( a4 )
      v12 = a4;
    WPP_SF_qqDS(*((_QWORD *)WPP_GLOBAL_Control + 27), v10, v11, (_DWORD)this, (char)a2, a3, (__int64)v12);
  }
  v13 = 8LL * *((unsigned int *)this + 110);
  if ( !is_mul_ok(*((unsigned int *)this + 110), 8u) )
    v13 = -1;
  v14 = operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
  v15 = v14;
  if ( v14 )
  {
    memset_0(v14, 0, v13);
    memset_0(v15, 0, 8LL * *((unsigned int *)this + 110));
    v16 = SwDeviceSetLifetime(a2, 1);
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_12:
        v62 = v15;
LABEL_13:
        v6 = v15;
        goto LABEL_142;
      }
      v18 = 290;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v16);
      goto LABEL_12;
    }
    v19 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 66);
    v20 = *v19;
    v66 = 0;
    v16 = (*v20)(v19, &GUID_9257d918_c95f_42d2_8bc7_a722fad119b2, &v66);
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_12;
      v18 = 291;
      goto LABEL_11;
    }
    v21 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)this + 67);
    v22 = *v21;
    v65 = 0;
    v16 = (*v22)(v21, &GUID_9257d918_c95f_42d2_8bc7_a722fad119b2, &v65);
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_12;
      v18 = 292;
      goto LABEL_11;
    }
    v16 = (*(__int64 (__fastcall **)(__int64, struct _DEVPROPERTY **, unsigned int *))(*(_QWORD *)v66 + 96LL))(
            v66,
            &v61,
            &v60);
    v17 = v16;
    if ( v16 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_12;
      v18 = 293;
      goto LABEL_11;
    }
    wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(
      &v71,
      v61);
    v62 = v15;
    v59 = v15;
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          294,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          this,
          v60);
      v24 = 0;
      if ( v60 )
      {
        do
        {
          if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          {
            LODWORD(v6) = (unsigned int)v6 | 1;
            v25 = DevPropTrace::DevPropTrace((DevPropTrace *)v72, &v61[v24]);
            String = FSString::GetString(v25);
            WPP_SF_qDs(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              295,
              (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
              (_DWORD)this,
              v24,
              (__int64)String);
          }
          if ( ((unsigned __int8)v6 & 1) != 0 )
          {
            LODWORD(v6) = (unsigned int)v6 & 0xFFFFFFFE;
            FSString::~FSString((FSString *)v72, v23);
          }
          v24 = (unsigned int)(v24 + 1);
        }
        while ( (unsigned int)v24 < v60 );
      }
      else
      {
        v59 = v15;
        v62 = v15;
      }
    }
    v61 = 0;
    v27 = (*(__int64 (__fastcall **)(__int64, struct _DEVPROPERTY **, unsigned int *))(*(_QWORD *)v65 + 96LL))(
            v65,
            &v61,
            &v73);
    v17 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_38:
        v6 = v59;
        goto LABEL_142;
      }
      v28 = 296;
LABEL_37:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v27);
      goto LABEL_38;
    }
    wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(
      &v70,
      v61);
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          297,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          this,
          v73);
      for ( i = 0; (unsigned int)i < v73; i = (unsigned int)(i + 1) )
      {
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        {
          LODWORD(v6) = (unsigned int)v6 | 2;
          v31 = DevPropTrace::DevPropTrace((DevPropTrace *)v72, &v61[i]);
          v32 = FSString::GetString(v31);
          WPP_SF_qDs(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            298,
            (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            (_DWORD)this,
            i,
            (__int64)v32);
        }
        if ( ((unsigned __int8)v6 & 2) != 0 )
        {
          LODWORD(v6) = (unsigned int)v6 & 0xFFFFFFFD;
          FSString::~FSString((FSString *)v72, v29);
        }
      }
    }
    v33 = 0;
    v61 = 0;
    v63 = 0;
    if ( *((_DWORD *)this + 110) )
    {
      v15 = v59;
      while ( 1 )
      {
        v34 = *((_QWORD *)this + 54);
        v67 = v33;
        v35 = 16 * v33;
        v36 = 16 * v33 + v34;
        v37 = *((_DWORD *)this + 160);
        v69 = v35;
        v64 = 0;
        v38 = SwDeviceInterfaceRegister(v74, v36, L"{FCEBBA03-9D13-4C13-9940-CC84FCD132D1}", 0, 0, v37, &v64);
        v17 = v38;
        if ( v38 < 0 )
          break;
        v40 = v67;
        v59[v67] = v64;
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        {
          LODWORD(v6) = (unsigned int)v6 | 4;
          v41 = v64;
          v42 = GuidTrace::GuidTrace((GuidTrace *)v72, (const struct _GUID *)(*((_QWORD *)this + 54) + v69));
          v43 = GuidTrace::GetString(v42);
          WPP_SF_qsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v43, v41);
          v40 = v67;
        }
        if ( ((unsigned __int8)v6 & 4) != 0 )
        {
          LODWORD(v6) = (unsigned int)v6 & 0xFFFFFFFB;
          FSString::~FSString((FSString *)v72, v39);
        }
        if ( !v63
          && !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                 (char *)this + 464,
                                 v64) )
        {
          v38 = -2147024882;
          v17 = -2147024882;
          if ( !g_wppLevels )
            goto LABEL_38;
          v45 = 301;
          goto LABEL_95;
        }
        v44 = *((_QWORD *)this + 54);
        if ( *(_QWORD *)(v69 + v44) == *(_QWORD *)&GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8.Data1
          && *(_QWORD *)(v69 + v44 + 8) == *(_QWORD *)GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8.Data4 )
        {
          if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                   (char *)this + 496,
                                   v64) )
          {
            v38 = -2147024882;
            v17 = -2147024882;
            if ( !g_wppLevels )
              goto LABEL_38;
            v45 = 302;
            goto LABEL_95;
          }
          if ( v73 )
          {
            v38 = SwDeviceInterfacePropertySet(v74, v59[v40], v73, v70);
            v17 = v38;
            if ( v38 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_38;
              v45 = 303;
              goto LABEL_95;
            }
          }
        }
        else if ( v60 )
        {
          v38 = SwDeviceInterfacePropertySet(v74, v59[v40], v60, v71);
          v17 = v38;
          if ( v38 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_38;
            v45 = 304;
            goto LABEL_95;
          }
        }
        v46 = v67;
        v47 = FSMVirtualCamera::InternalWriteRegistryEntriesToInterface(this, (const unsigned __int16 *)v59[v67]);
        if ( v47 < 0 && (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            305,
            (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            (_DWORD)this,
            v47,
            v64);
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl'::`2'::impl) )
        {
          v38 = SwDeviceInterfaceSetState(v74, v59[v46], *((_DWORD *)this + 39) == 1);
          v17 = v38;
          if ( v38 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_38;
            v45 = 306;
            goto LABEL_95;
          }
          if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          {
            v50 = "enable";
            if ( *((_DWORD *)this + 39) != 1 )
              v50 = "disable";
            WPP_SF_qsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v50, v59[v67]);
          }
          if ( *((_DWORD *)this + 39) == 1 )
          {
            v38 = FSMVCamWaitForInterfaceArrivalByInstanceId(
                    (const unsigned __int16 *)this + 96,
                    (struct _GUID *)(*((_QWORD *)this + 54) + v69),
                    v48,
                    v49);
            v17 = v38;
            if ( v38 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_38;
              v45 = 308;
              goto LABEL_95;
            }
          }
        }
        v33 = (unsigned int)(v63 + 1);
        v63 = v33;
        if ( (unsigned int)v33 >= *((_DWORD *)this + 110) )
          goto LABEL_78;
      }
      if ( !g_wppLevels )
        goto LABEL_38;
      v45 = 299;
LABEL_95:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v38);
      goto LABEL_13;
    }
LABEL_78:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl'::`2'::impl) )
      wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::reset(
        (char *)this + 584,
        0);
    if ( *((_QWORD *)this + 62) == *((_QWORD *)this + 63) )
    {
      v27 = -1072875845;
      v17 = -1072875845;
      if ( !g_wppLevels )
        goto LABEL_38;
      v28 = 309;
      goto LABEL_37;
    }
    if ( *((_QWORD *)this + 58) == *((_QWORD *)this + 59) )
    {
      v27 = -1072875845;
      v17 = -1072875845;
      if ( !g_wppLevels )
        goto LABEL_38;
      v28 = 310;
      goto LABEL_37;
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(**((_QWORD **)this + 72) + 200LL))(
            *((_QWORD *)this + 72),
            &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
            *((_QWORD *)this + 42));
    v17 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v28 = 311;
      goto LABEL_37;
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD, const IID *, _QWORD))(**((_QWORD **)this + 72) + 200LL))(
            *((_QWORD *)this + 72),
            &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
            *((_QWORD *)this + 58));
    v17 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v28 = 312;
      goto LABEL_37;
    }
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v68);
    v27 = FSCloneAttributes(*((struct IMFAttributes **)this + 72), &v68);
    v17 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_38;
      v28 = 313;
      goto LABEL_37;
    }
    v6 = v59;
    if ( *((_QWORD *)this + 81) && *((_DWORD *)this + 164) && (v51 = 0, *((_DWORD *)this + 110)) )
    {
      while ( 1 )
      {
        updated = FSMVirtualCamera::InternalUpdateSensorGroupProperties(this, (const unsigned __int16 *)v59[v51], v68);
        v17 = updated;
        if ( updated < 0 )
          break;
        v51 = (unsigned int)(v51 + 1);
        if ( (unsigned int)v51 >= *((_DWORD *)this + 110) )
          goto LABEL_113;
      }
      if ( !g_wppLevels )
        goto LABEL_38;
      v53 = 314;
    }
    else
    {
LABEL_113:
      updated = FSSetDeviceInterfaceProperty(
                  *((const unsigned __int16 **)this + 62),
                  &DEVPKEY_DeviceInterface_FSM_VirtualCamera_SymbolicName,
                  0x12u,
                  *((unsigned __int8 *const *)this + 58),
                  2 * (unsigned int)((__int64)(*((_QWORD *)this + 59) - *((_QWORD *)this + 58)) >> 1) + 2);
      v17 = updated;
      if ( updated >= 0 )
      {
        updated = FSMVirtualCamera::AddPropertyToCollection(
                    *((struct IFSMCameraDeviceProperties **)this + 67),
                    &DEVPKEY_DeviceInterface_FSM_VirtualCamera_SymbolicName,
                    0x12u,
                    *((const unsigned __int8 **)this + 58),
                    2 * ((__int64)(*((_QWORD *)this + 59) - *((_QWORD *)this + 58)) >> 1) + 2);
        v17 = updated;
        if ( updated >= 0 )
        {
          updated = FSSetDeviceInterfaceProperty(
                      *((const unsigned __int16 **)this + 62),
                      &DEVPKEY_DeviceInterface_FSM_VirtualCamera_InternalAlias,
                      0x12u,
                      *((unsigned __int8 *const *)this + 62),
                      2 * (unsigned int)((__int64)(*((_QWORD *)this + 63) - *((_QWORD *)this + 62)) >> 1) + 2);
          v17 = updated;
          if ( updated >= 0 )
          {
            updated = FSMVirtualCamera::AddPropertyToCollection(
                        *((struct IFSMCameraDeviceProperties **)this + 67),
                        &DEVPKEY_DeviceInterface_FSM_VirtualCamera_InternalAlias,
                        0x12u,
                        *((const unsigned __int8 **)this + 62),
                        2 * ((__int64)(*((_QWORD *)this + 63) - *((_QWORD *)this + 62)) >> 1) + 2);
            v17 = updated;
            if ( updated >= 0 )
            {
              if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2505>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_MediaQI2505>::GetImpl'::`2'::impl) )
                goto LABEL_38;
              v54 = 0;
              if ( !*((_DWORD *)this + 110) )
                goto LABEL_38;
              while ( 1 )
              {
                updated = SwDeviceInterfaceSetState(v74, v59[v54], *((_DWORD *)this + 39) == 1);
                v17 = updated;
                if ( updated < 0 )
                  break;
                if ( (unsigned __int8)byte_18005E5A5 >= 8u )
                {
                  v55 = "enable";
                  if ( *((_DWORD *)this + 39) != 1 )
                    v55 = "disable";
                  WPP_SF_qsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v55, v59[v54]);
                }
                v54 = (unsigned int)(v54 + 1);
                if ( (unsigned int)v54 >= *((_DWORD *)this + 110) )
                  goto LABEL_142;
              }
              if ( !g_wppLevels )
                goto LABEL_38;
              v53 = 319;
            }
            else
            {
              if ( !g_wppLevels )
                goto LABEL_38;
              v53 = 318;
            }
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_38;
            v53 = 317;
          }
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_38;
          v53 = 316;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_38;
        v53 = 315;
      }
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v53, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, updated);
  }
  else
  {
    v17 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        289,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        this,
        -2147024882);
    v62 = 0;
  }
LABEL_142:
  for ( j = 0; (unsigned int)j < *((_DWORD *)this + 110); j = (unsigned int)(j + 1) )
  {
    if ( v6[j] )
    {
      SwMemFree();
      v6[j] = 0;
    }
  }
  if ( v17 >= 0 )
  {
    if ( (unsigned __int8)byte_18005E5A5 < 8u )
      goto LABEL_152;
    v57 = 322;
  }
  else
  {
    *((_DWORD *)this + 156) = v17;
    if ( !byte_18005E5A5 )
      goto LABEL_152;
    v57 = 321;
  }
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v57, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v17);
LABEL_152:
  wil::details::unique_storage<wil::details::resource_policy<HSWDEVICE__ *,void (*)(HSWDEVICE__ *),&void SwDeviceClose(HSWDEVICE__ *),wistd::integral_constant<unsigned __int64,0>,HSWDEVICE__ *,HSWDEVICE__ *,0,std::nullptr_t>>::reset(
    (char *)this + 584,
    0);
  if ( hEvent )
    SetEvent(hEvent);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v68);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v65);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v66);
  wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v70);
  wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v71);
  if ( v62 )
    operator delete(v62, v58);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
}

```

## disassembly

```asm
0x180023b24  mov     [rsp-8+arg_10], rbx
0x180023b29  mov     [rsp-8+arg_8], rdx
0x180023b2e  push    rbp
0x180023b2f  push    rsi
0x180023b30  push    rdi
0x180023b31  push    r12
0x180023b33  push    r13
0x180023b35  push    r14
0x180023b37  push    r15
0x180023b39  lea     rbp, [rsp-1Fh]
0x180023b3e  sub     rsp, 0D0h
0x180023b45  xor     r12d, r12d
0x180023b48  mov     rsi, rcx
0x180023b4b  add     rcx, 60h ; '`'; lpCriticalSection
0x180023b4f  mov     [rbp+4Fh+arg_0], r12d
0x180023b53  mov     r13d, r12d
0x180023b56  mov     rdi, r9
0x180023b59  mov     r14d, r8d
0x180023b5c  mov     r15, rdx
0x180023b5f  call    cs:__imp_EnterCriticalSection
0x180023b65  mov     [rbp+4Fh+var_B0], r12
0x180023b69  mov     [rbp+4Fh+var_60], r12
0x180023b6d  mov     [rbp+4Fh+var_B8], r12d
0x180023b71  mov     [rbp+4Fh+var_68], r12
0x180023b75  mov     [rbp+4Fh+arg_0], r12d
0x180023b79  mov     [rbp+4Fh+var_88], r12
0x180023b7d  mov     [rbp+4Fh+var_90], r12
0x180023b81  mov     [rbp+4Fh+var_78], r12
0x180023b85  cmp     cs:byte_18005E5A5, 8
0x180023b8c  jb      short loc_180023BC1
0x180023b8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180023b95  lea     rax, aNullptr; "<nullptr>"
0x180023b9c  test    rdi, rdi
0x180023b9f  mov     r9, rsi
0x180023ba2  cmovnz  rax, rdi
0x180023ba6  mov     rcx, [rcx+0D8h]
0x180023bad  mov     [rsp+100h+var_D0], rax
0x180023bb2  mov     dword ptr [rsp+100h+var_D8], r14d
0x180023bb7  mov     qword ptr [rsp+100h+var_E0], r15
0x180023bbc  call    WPP_SF_qqDS
0x180023bc1  mov     ecx, [rsi+1B8h]
0x180023bc7  mov     eax, 8
0x180023bcc  mul     rcx
0x180023bcf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180023bd6  mov     rdi, rax
0x180023bd9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180023be0  cmovb   rdi, rax
0x180023be4  mov     rcx, rdi; unsigned __int64
0x180023be7  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180023bec  mov     r12, rax
0x180023bef  test    rax, rax
0x180023bf2  jz      loc_18002464F
0x180023bf8  mov     r8, rdi; Size
0x180023bfb  xor     edx, edx; Val
0x180023bfd  mov     rcx, rax; void *
0x180023c00  call    memset_0
0x180023c05  mov     r8d, [rsi+1B8h]
0x180023c0c  xor     edx, edx; Val
0x180023c0e  shl     r8, 3; Size
0x180023c12  mov     rcx, r12; void *
0x180023c15  call    memset_0
0x180023c1a  mov     r14d, 1
0x180023c20  mov     rcx, r15
0x180023c23  mov     edx, r14d
0x180023c26  call    cs:__imp_SwDeviceSetLifetime
0x180023c2c  mov     edi, eax
0x180023c2e  test    eax, eax
0x180023c30  jns     short loc_180023C6D
0x180023c32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180023c39  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180023c40  jb      short loc_180023C61
0x180023c42  mov     edx, 122h
0x180023c47  mov     rcx, cs:WPP_GLOBAL_Control
0x180023c4e  mov     r9, rsi
0x180023c51  mov     r8, r15
0x180023c54  mov     [rsp+100h+var_E0], eax
0x180023c58  mov     rcx, [rcx+10h]
0x180023c5c  call    WPP_SF_qD
0x180023c61  mov     [rbp+4Fh+var_A8], r12
0x180023c65  mov     r13, r12
0x180023c68  jmp     loc_180024691
0x180023c6d  mov     rcx, [rbp+4Fh+var_88]
0x180023c71  mov     rdi, [rsi+210h]
0x180023c78  mov     rax, [rdi]
0x180023c7b  mov     [rbp+4Fh+var_88], r13
0x180023c7f  mov     r15, [rax]
0x180023c82  test    rcx, rcx
0x180023c85  jz      short loc_180023C93
0x180023c87  mov     rdx, [rcx]
0x180023c8a  mov     rax, [rdx+10h]
0x180023c8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c93  lea     r8, [rbp+4Fh+var_88]
0x180023c97  mov     rcx, rdi
0x180023c9a  lea     rdx, _GUID_9257d918_c95f_42d2_8bc7_a722fad119b2
0x180023ca1  mov     rax, r15
0x180023ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023ca9  mov     edi, eax
0x180023cab  test    eax, eax
0x180023cad  jns     short loc_180023CC6
0x180023caf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180023cb6  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180023cbd  jb      short loc_180023C61
0x180023cbf  mov     edx, 123h
0x180023cc4  jmp     short loc_180023C47
0x180023cc6  mov     rcx, [rbp+4Fh+var_90]
0x180023cca  mov     rdi, [rsi+218h]
0x180023cd1  mov     rax, [rdi]
0x180023cd4  mov     [rbp+4Fh+var_90], r13
0x180023cd8  mov     r15, [rax]
0x180023cdb  test    rcx, rcx
0x180023cde  jz      short loc_180023CEC
0x180023ce0  mov     r8, [rcx]
0x180023ce3  mov     rax, [r8+10h]
0x180023ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cec  lea     r8, [rbp+4Fh+var_90]
0x180023cf0  mov     rcx, rdi
0x180023cf3  lea     rdx, _GUID_9257d918_c95f_42d2_8bc7_a722fad119b2
0x180023cfa  mov     rax, r15
0x180023cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d02  mov     edi, eax
0x180023d04  test    eax, eax
0x180023d06  jns     short loc_180023D26
0x180023d08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180023d0f  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180023d16  jb      loc_180023C61
0x180023d1c  mov     edx, 124h
0x180023d21  jmp     loc_180023C47
0x180023d26  mov     rcx, [rbp+4Fh+var_88]
0x180023d2a  lea     r8, [rbp+4Fh+var_B8]
0x180023d2e  lea     rdx, [rbp+4Fh+var_B0]
0x180023d32  mov     rax, [rcx]
0x180023d35  mov     rax, [rax+60h]
0x180023d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d3e  mov     edi, eax
0x180023d40  test    eax, eax
0x180023d42  jns     short loc_180023D62
0x180023d44  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180023d4b  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180023d52  jb      loc_180023C61
0x180023d58  mov     edx, 125h
0x180023d5d  jmp     loc_180023C47
0x180023d62  mov     rdx, [rbp+4Fh+var_B0]
0x180023d66  lea     rcx, [rbp+4Fh+var_60]
0x180023d6a  call    ??$reset@PEAU_DEVPROPERTY@@@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVPROPERTY@@@Z; wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(_DEVPROPERTY *)
0x180023d6f  mov     cl, cs:byte_18005E5A5
0x180023d75  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180023d7c  mov     [rbp+4Fh+var_A8], r12
0x180023d80  mov     [rbp+4Fh+var_C0], r12
0x180023d84  cmp     cl, 10h
0x180023d87  jb      loc_180023E32
0x180023d8d  cmp     cl, 8
0x180023d90  jb      short loc_180023DB7
0x180023d92  mov     rcx, cs:WPP_GLOBAL_Control
0x180023d99  mov     edx, 126h
0x180023d9e  mov     eax, [rbp+4Fh+var_B8]
0x180023da1  mov     r9, rsi
0x180023da4  mov     r8, r15
0x180023da7  mov     [rsp+100h+var_E0], eax
0x180023dab  mov     rcx, [rcx+0D8h]
0x180023db2  call    WPP_SF_qD
0x180023db7  xor     edi, edi
0x180023db9  cmp     [rbp+4Fh+var_B8], edi
0x180023dbc  jbe     short loc_180023E2A
0x180023dbe  cmp     cs:byte_18005E5A5, 8
0x180023dc5  jb      short loc_180023E0E
0x180023dc7  lea     rdx, [rdi+rdi*2]
0x180023dcb  or      r13d, r14d
0x180023dce  shl     rdx, 4
0x180023dd2  lea     rcx, [rbp+4Fh+var_58]; this
0x180023dd6  add     rdx, [rbp+4Fh+var_B0]; struct _DEVPROPERTY *
0x180023dda  call    ??0DevPropTrace@@QEAA@AEBU_DEVPROPERTY@@@Z; DevPropTrace::DevPropTrace(_DEVPROPERTY const &)
0x180023ddf  mov     rcx, rax; this
0x180023de2  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180023de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180023dee  mov     edx, 127h
0x180023df3  mov     [rsp+100h+var_D8], rax
0x180023df8  mov     r9, rsi
0x180023dfb  mov     r8, r15
0x180023dfe  mov     [rsp+100h+var_E0], edi
0x180023e02  mov     rcx, [rcx+0D8h]
0x180023e09  call    WPP_SF_qDs
0x180023e0e  test    r14b, r13b
0x180023e11  jz      short loc_180023E20
0x180023e13  and     r13d, 0FFFFFFFEh
0x180023e17  lea     rcx, [rbp+4Fh+var_58]; this
0x180023e1b  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180023e20  add     edi, r14d
0x180023e23  cmp     edi, [rbp+4Fh+var_B8]
0x180023e26  jb      short loc_180023DBE
0x180023e28  jmp     short loc_180023E32
0x180023e2a  mov     [rbp+4Fh+var_C0], r12
0x180023e2e  mov     [rbp+4Fh+var_A8], r12
0x180023e32  mov     rcx, [rbp+4Fh+var_90]
0x180023e36  lea     r8, [rbp+4Fh+arg_0]
0x180023e3a  mov     [rbp+4Fh+var_B0], 0
0x180023e42  lea     rdx, [rbp+4Fh+var_B0]
0x180023e46  mov     rax, [rcx]
0x180023e49  mov     rax, [rax+60h]
0x180023e4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023e52  mov     edi, eax
0x180023e54  test    eax, eax
0x180023e56  jns     short loc_180023E89
0x180023e58  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x180023e5f  jb      short loc_180023E80
0x180023e61  mov     edx, 128h
0x180023e66  mov     rcx, cs:WPP_GLOBAL_Control
0x180023e6d  mov     r9, rsi
0x180023e70  mov     r8, r15
0x180023e73  mov     [rsp+100h+var_E0], eax
0x180023e77  mov     rcx, [rcx+10h]
0x180023e7b  call    WPP_SF_qD
0x180023e80  mov     r13, [rbp+4Fh+var_C0]
0x180023e84  jmp     loc_180024691
0x180023e89  mov     rdx, [rbp+4Fh+var_B0]
0x180023e8d  lea     rcx, [rbp+4Fh+var_68]
0x180023e91  call    ??$reset@PEAU_DEVPROPERTY@@@?$unique_ptr@$$BY0A@U_DEVPROPERTY@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_DEVPROPERTY@@@Z; wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(_DEVPROPERTY *)
0x180023e96  mov     al, cs:byte_18005E5A5
0x180023e9c  cmp     al, 10h
0x180023e9e  jb      loc_180023F40
0x180023ea4  cmp     al, 8
0x180023ea6  jb      short loc_180023ECD
0x180023ea8  mov     rcx, cs:WPP_GLOBAL_Control
0x180023eaf  mov     edx, 129h
0x180023eb4  mov     eax, [rbp+4Fh+arg_0]
0x180023eb7  mov     r9, rsi
0x180023eba  mov     r8, r15
0x180023ebd  mov     [rsp+100h+var_E0], eax
0x180023ec1  mov     rcx, [rcx+0D8h]
0x180023ec8  call    WPP_SF_qD
0x180023ecd  xor     edi, edi
0x180023ecf  cmp     [rbp+4Fh+arg_0], edi
0x180023ed2  jbe     short loc_180023F40
0x180023ed4  cmp     cs:byte_18005E5A5, 8
0x180023edb  jb      short loc_180023F25
0x180023edd  lea     rdx, [rdi+rdi*2]
0x180023ee1  or      r13d, 2
0x180023ee5  shl     rdx, 4
0x180023ee9  lea     rcx, [rbp+4Fh+var_58]; this
0x180023eed  add     rdx, [rbp+4Fh+var_B0]; struct _DEVPROPERTY *
0x180023ef1  call    ??0DevPropTrace@@QEAA@AEBU_DEVPROPERTY@@@Z; DevPropTrace::DevPropTrace(_DEVPROPERTY const &)
0x180023ef6  mov     rcx, rax; this
0x180023ef9  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180023efe  mov     rcx, cs:WPP_GLOBAL_Control
0x180023f05  mov     edx, 12Ah
0x180023f0a  mov     [rsp+100h+var_D8], rax
0x180023f0f  mov     r9, rsi
0x180023f12  mov     r8, r15
0x180023f15  mov     [rsp+100h+var_E0], edi
0x180023f19  mov     rcx, [rcx+0D8h]
0x180023f20  call    WPP_SF_qDs
0x180023f25  test    r13b, 2
0x180023f29  jz      short loc_180023F38
0x180023f2b  and     r13d, 0FFFFFFFDh
0x180023f2f  lea     rcx, [rbp+4Fh+var_58]; this
0x180023f33  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180023f38  add     edi, r14d
0x180023f3b  cmp     edi, [rbp+4Fh+arg_0]
0x180023f3e  jb      short loc_180023ED4
0x180023f40  xor     eax, eax
0x180023f42  mov     [rbp+4Fh+var_B0], 0
0x180023f4a  mov     [rbp+4Fh+var_A0], eax
0x180023f4d  cmp     [rsi+1B8h], eax
0x180023f53  jbe     loc_1800241FC
0x180023f59  mov     r12, [rbp+4Fh+var_C0]
0x180023f5d  mov     rdx, [rsi+1B0h]
0x180023f64  lea     r8, aFcebba039d134c; "{FCEBBA03-9D13-4C13-9940-CC84FCD132D1}"
0x180023f6b  mov     rcx, rax
0x180023f6e  mov     [rbp+4Fh+var_80], rax
0x180023f72  shl     rcx, 4
0x180023f76  lea     rax, [rbp+4Fh+var_98]
0x180023f7a  mov     [rsp+100h+var_D0], rax
0x180023f7f  add     rdx, rcx
0x180023f82  mov     eax, [rsi+280h]
0x180023f88  xor     r9d, r9d
0x180023f8b  mov     [rbp+4Fh+var_70], rcx
0x180023f8f  mov     rcx, [rbp+4Fh+arg_8]
0x180023f93  mov     dword ptr [rsp+100h+var_D8], eax
0x180023f97  mov     qword ptr [rsp+100h+var_E0], 0
0x180023fa0  mov     [rbp+4Fh+var_98], 0
0x180023fa8  call    cs:__imp_SwDeviceInterfaceRegister
0x180023fae  mov     edi, eax
0x180023fb0  test    eax, eax
0x180023fb2  js      loc_1800242BE
0x180023fb8  mov     rdi, [rbp+4Fh+var_80]
0x180023fbc  mov     rax, [rbp+4Fh+var_98]
0x180023fc0  mov     [r12+rdi*8], rax
0x180023fc4  cmp     cs:byte_18005E5A5, 8
0x180023fcb  jb      short loc_18002401D
0x180023fcd  mov     rdx, [rbp+4Fh+var_70]
0x180023fd1  lea     rcx, [rbp+4Fh+var_58]; this
0x180023fd5  add     rdx, [rsi+1B0h]; struct _GUID *
0x180023fdc  or      r13d, 4
0x180023fe0  mov     rdi, [rbp+4Fh+var_98]
0x180023fe4  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x180023fe9  mov     rcx, rax; this
0x180023fec  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x180023ff1  mov     rcx, cs:WPP_GLOBAL_Control
0x180023ff8  mov     edx, 12Ch
0x180023ffd  mov     [rsp+100h+var_D8], rdi; __int64
0x180024002  mov     r9, rsi
  ... truncated ...
```
