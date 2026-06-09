# Fdo::Initialize(_BTDEVICE * *)

- ea: `0x14002a5b8`
- end: `0x14002b26f`
- name: `?Initialize@Fdo@@AEAAJPEAPEAU_BTDEVICE@@@Z`
- size: `3255`
- prototype: `__int64 __fastcall(Fdo *__hidden this, struct _BTDEVICE **)`
- caller_count: `1`
- callee_count: `39`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1401bcc28`

## callees

- `0x1400043d0`
- `0x140005504`
- `0x140005690`
- `0x140005b4c`
- `0x140005c04`
- `0x14000764c`
- `0x1400102bc`
- `0x14001c5bc`
- `0x14001c6a4`
- `0x14001f3f8`
- `0x14001f59c`
- `0x14001facc`
- `0x140027c70`
- `0x140029c08`
- `0x14002a3ac`
- `0x14002a5b8`
- `0x14002b2b4`
- `0x1400719d4`
- `0x1400bbfb8`
- `0x1401489dc`
- `0x1401498ac`
- `0x14014a634`
- `0x140164690`
- `0x140165540`
- `0x140165580`
- `0x140165940`
- `0x1401b77bc`
- `0x1401b8c80`
- `0x1401b8ce0`
- `0x1401b9048`
- `0x1401bcef8`
- `0x1401de328`
- `0x1401e3f90`
- `0x1401e4bb8`
- `0x1401e4eb4`
- `0x1401e9518`
- `0x1401ef980`
- `0x1401f2974`
- `0x140206648`

## import_xrefs

- `ntoskrnl!EtwActivityIdControl` at `0x14002ada2`
- `ntoskrnl!EtwActivityIdControl` at `0x14002ada2`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14002a730`
- `ntoskrnl!IoGetDriverObjectExtension` at `0x14002a730`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14002b093`
- `ntoskrnl!PoRegisterPowerSettingCallback` at `0x14002b093`
- `ntoskrnl!ExAllocatePool2` at `0x14002addc`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae5b`
- `ntoskrnl!ExAllocatePool2` at `0x14002af75`
- `ntoskrnl!ExAllocatePool2` at `0x14002afba`
- `ntoskrnl!ExAllocatePool2` at `0x14002addc`
- `ntoskrnl!ExAllocatePool2` at `0x14002ae5b`
- `ntoskrnl!ExAllocatePool2` at `0x14002af75`
- `ntoskrnl!ExAllocatePool2` at `0x14002afba`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14002a694`
- `WppRecorder!imp_WppRecorderLogCreate` at `0x14002a694`

## pseudocode

```c
NTSTATUS __fastcall Fdo::Initialize(Fdo *this, struct _BTDEVICE **a2)
{
  const char *v2; // r8
  __int64 v5; // rdx
  __int128 *v6; // rcx
  __int64 v7; // rax
  __int128 *v8; // rax
  int v9; // edx
  NTSTATUS v10; // ebx
  int v11; // r8d
  PDEVICE_OBJECT v12; // r10
  NTSTATUS result; // eax
  struct _DRIVER_OBJECT *v14; // rax
  const struct _BTH_MINIPORT_DESCRIPTOR *DriverObjectExtension; // rsi
  struct _DEVICE_OBJECT *v16; // rdi
  struct _DEVICE_OBJECT *v17; // rbx
  struct _DEVICE_OBJECT *v18; // rax
  _QWORD *v19; // rbx
  int v20; // edx
  int v21; // edi
  int v22; // r8d
  PDEVICE_OBJECT v23; // r10
  int v24; // r8d
  int v25; // edx
  int v26; // edx
  int v27; // r8d
  __int64 v28; // rdx
  signed __int64 v29; // rax
  int v30; // edx
  int v31; // r8d
  __int64 v32; // rbx
  __int64 v33; // rdx
  struct HCI_INTERFACE *v34; // rax
  struct _SCO_INTERFACE *Pool2; // rax
  struct _SCO_INTERFACE *v36; // rbx
  struct L2CAP_INTERFACE *v37; // rax
  struct _SDP_INTERFACE *v38; // rax
  struct _SMP_INTERFACE *v39; // rax
  _SDP_DATABASE *v40; // rax
  _SDP_DATABASE *v41; // rax
  __int64 v42; // rdx
  struct _SDP_DATABASE *v43; // rcx
  int v44; // edx
  int v45; // r8d
  struct PDO_EXTENSION *v46; // rax
  int v47; // edx
  int v48; // r8d
  struct PDO_EXTENSION *v49; // rbx
  L2CAP_SERVER_INFO *v50; // rax
  int v51; // edx
  int v52; // r8d
  L2CAP_SERVER_INFO *v53; // rax
  Fdo **v54; // r8
  struct _DEVICE_OBJECT *v55; // rax
  __int64 v56; // rcx
  int Handle; // [rsp+20h] [rbp-E0h]
  __int16 v58; // [rsp+30h] [rbp-D0h]
  __int16 v59; // [rsp+30h] [rbp-D0h]
  __int64 v60; // [rsp+40h] [rbp-C0h]
  __int64 v61; // [rsp+40h] [rbp-C0h]
  char v62; // [rsp+48h] [rbp-B8h]
  char v63; // [rsp+48h] [rbp-B8h]
  _QWORD v64[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v65[18]; // [rsp+60h] [rbp-A0h] BYREF
  _OWORD v66[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v67; // [rsp+110h] [rbp+10h] BYREF
  __int64 v68; // [rsp+120h] [rbp+20h]
  GUID ActivityId; // [rsp+128h] [rbp+28h] BYREF

  v2 = "I/O";
  v68 = 0;
  v5 = 16;
  *((_QWORD *)&v66[1] + 1) = 0x1000000000LL;
  memset(v66, 0, 24);
  v6 = &v67;
  LODWORD(v66[0]) = 56;
  v67 = 0;
  LOBYTE(v67) = 0;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*v2 )
      break;
    *(_BYTE *)v6 = *v2++;
    v6 = (__int128 *)((char *)v6 + 1);
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = (__int128 *)((char *)v6 - 1);
  if ( v5 )
    v8 = v6;
  *(_BYTE *)v8 = 0;
  v68 = 0x200000002LL;
  *(_QWORD *)((char *)v66 + 4) = 0x100050485442LL;
  HIDWORD(v66[0]) = 256;
  wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&void WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::reset(
    (char *)this + 40,
    0);
  v10 = imp_WppRecorderLogCreate(WPP_GLOBAL_Control, v66, (char *)this + 40);
  if ( v10 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v9) = 0;
    v62 = v10;
    v60 = *(_QWORD *)this;
    v58 = 15;
LABEL_12:
    LOBYTE(v11) = 1;
    WPP_RECORDER_AND_TRACE_SF_qL(
      v12->AttachedDevice,
      v9,
      v11,
      *((_QWORD *)this + 4),
      2,
      1,
      v58,
      (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
      v60,
      v62);
    return v10;
  }
  v14 = (struct _DRIVER_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 944))(
                                   WdfDriverGlobals,
                                   ***((_QWORD ***)this + 3));
  DriverObjectExtension = (const struct _BTH_MINIPORT_DESCRIPTOR *)IoGetDriverObjectExtension(
                                                                     v14,
                                                                     BTHPORT_RegisterMiniport);
  v16 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 256))(
                                   WdfDriverGlobals,
                                   *(_QWORD *)this);
  v17 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 264))(
                                   WdfDriverGlobals,
                                   *(_QWORD *)this);
  v18 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 248))(
                                   WdfDriverGlobals,
                                   *(_QWORD *)this);
  result = BthInitExtension((struct DEVICE_EXTENSION *)((char *)this + 816), v18, v17, v16, DriverObjectExtension);
  if ( result >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, GUID *, _QWORD))(WdfFunctions_01031 + 616))(
            WdfDriverGlobals,
            *(_QWORD *)this,
            &GUID_BTHPORT_DEVICE_INTERFACE,
            0);
    if ( v10 < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v9) = 0;
      v62 = v10;
      v60 = *(_QWORD *)this;
      v58 = 16;
      goto LABEL_12;
    }
    if ( WdfClientVersionHigherThanFramework && (unsigned int)WdfFunctionCount <= 0x1C9 )
    {
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, WDFDRIVER__ *, _QWORD))(WdfFunctions_01031 + 3616))(
        WdfDriverGlobals,
        WdfDriverGlobals->Driver,
        0);
    }
    else
    {
      LOBYTE(Handle) = 0;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, GUID *, _QWORD, int))(WdfFunctions_01031 + 3656))(
        WdfDriverGlobals,
        *(_QWORD *)this,
        &GUID_BTHPORT_DEVICE_INTERFACE,
        0,
        Handle);
    }
    v19 = (_QWORD *)((char *)this + 800);
    if ( *((_QWORD *)this + 100) )
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS))(WdfFunctions_01031 + 1664))(WdfDriverGlobals);
    *v19 = 0;
    v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, char *))(WdfFunctions_01031 + 2464))(
            WdfDriverGlobals,
            0,
            0,
            (char *)this + 800);
    if ( v21 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v20) = 0;
      v63 = v21;
      v61 = *(_QWORD *)this;
      v59 = 17;
LABEL_31:
      LOBYTE(v22) = 1;
      WPP_RECORDER_AND_TRACE_SF_qL(
        v23->AttachedDevice,
        v20,
        v22,
        *((_QWORD *)this + 4),
        2,
        1,
        v59,
        (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
        v61,
        v63);
      return v21;
    }
    v21 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, GUID *, _QWORD, _QWORD))(WdfFunctions_01031 + 632))(
            WdfDriverGlobals,
            *(_QWORD *)this,
            &GUID_BTHPORT_DEVICE_INTERFACE,
            0,
            *v19);
    if ( v21 < 0 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v20) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v20) = 0;
      v63 = v21;
      v61 = *(_QWORD *)this;
      v59 = 18;
      goto LABEL_31;
    }
    (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, char *))(WdfFunctions_01031 + 2472))(
      WdfDriverGlobals,
      *v19,
      (char *)this + 912);
    Fdo::GetDeviceParametersKey(this, v64);
    v25 = v64[0];
    if ( v64[0] )
    {
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, const wchar_t *, _QWORD))(WdfFunctions_01031 + 1960))(
              WdfDriverGlobals,
              v64[0],
              L" \"",
              *v19);
      if ( v10 < 0 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v26) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v26) = 0;
        LOBYTE(v27) = 1;
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v26,
          v27,
          *((_QWORD *)this + 4),
          2,
          1,
          20,
          (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
          *(_QWORD *)this,
          v10);
        wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(v64);
        return v10;
      }
      wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(v64);
      result = RadioStateManager::Initialize((RadioStateManager *)this + 55);
      if ( result < 0 )
        return result;
      result = Controller::Initialize((Controller *)((char *)this + 48));
      if ( result < 0 )
        return result;
      memset(v66, 0, sizeof(v66));
      v67 = 0;
      if ( WdfClientVersionHigherThanFramework )
        LODWORD(v66[0]) = (unsigned int)WdfStructureCount <= 0xC ? -1 : *(_DWORD *)(WdfStructures + 96);
      else
        LODWORD(v66[0]) = 48;
      *((_QWORD *)&v67 + 1) = -1;
      v28 = *(_QWORD *)this;
      *(__m128i *)((char *)v66 + 4) = _mm_load_si128((const __m128i *)&_xmm);
      *(_QWORD *)((char *)&v66[1] + 4) = 0x200000002LL;
      *(_QWORD *)&v67 = 0x200000002LL;
      HIDWORD(v66[1]) = 1;
      (*(void (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _OWORD *))(WdfFunctions_01031 + 664))(
        WdfDriverGlobals,
        v28,
        v66);
      result = FdoDefaultIoQueue::Make(this, (struct FdoDefaultIoQueue **)this + 225);
      if ( result < 0 )
        return result;
      result = PowerCoordinator::Initialize((PowerCoordinator *)((char *)this + 1584));
      if ( result < 0 )
        return result;
      v29 = _InterlockedCompareExchange64(
              &qword_140197C10,
              (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 248))(
                WdfDriverGlobals,
                *(_QWORD *)this),
              0);
      if ( v29 )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v30) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v30) = 0;
        LOBYTE(v31) = 1;
        WPP_RECORDER_AND_TRACE_SF_qi(
          WPP_GLOBAL_Control->AttachedDevice,
          v30,
          v31,
          *((_QWORD *)this + 4),
          2,
          1,
          21,
          (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
          *(_QWORD *)this,
          v29);
        BthReportError((struct DEVICE_EXTENSION *)((char *)this + 816), -2147155962, 0, 0, 0);
        return -1073741823;
      }
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, _QWORD, char *))(WdfFunctions_01031 + 1336))(
              WdfDriverGlobals,
              *(_QWORD *)this,
              0,
              (char *)this + 1792);
      if ( v10 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v9) = 0;
        v62 = v10;
        v60 = *(_QWORD *)this;
        v58 = 22;
        goto LABEL_12;
      }
      memset(v65, 0, 0x88u);
      v32 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 248))(
              WdfDriverGlobals,
              *(_QWORD *)this);
      memset(v65, 0, 0x88u);
      if ( WdfClientVersionHigherThanFramework )
      {
        if ( (unsigned int)WdfStructureCount <= 0x23 )
          LODWORD(v65[0]) = -1;
        else
          LODWORD(v65[0]) = *(_DWORD *)(WdfStructures + 280);
      }
      else
      {
        LODWORD(v65[0]) = 136;
      }
      v33 = *((_QWORD *)this + 224);
      HIDWORD(v65[0]) = 1;
      v65[4] = v32;
      v10 = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, _QWORD *))(WdfFunctions_01031 + 1344))(
              WdfDriverGlobals,
              v33,
              v65);
      if ( v10 < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
          LOBYTE(v9) = 0;
        v62 = v10;
        v60 = *(_QWORD *)this;
        v58 = 23;
        goto LABEL_12;
      }
      BthRegisterFdoSleepStudy((struct DEVICE_EXTENSION *)((char *)this + 816));
      BthLogStartDeviceTelemetry((struct DEVICE_EXTENSION *)((char *)this + 816));
      *((_BYTE *)this + 1810) = 1;
      ActivityId = 0;
      EtwActivityIdControl(3u, &ActivityId);
      v34 = HCI_Create((struct DEVICE_EXTENSION *)((char *)this + 816), &ActivityId);
      *((_QWORD *)this + 148) = v34;
      if ( v34 )
      {
        Pool2 = (struct _SCO_INTERFACE *)ExAllocatePool2(64, 240, 1346917442);
        v36 = Pool2;
        if ( Pool2 )
          ScoInt_Initialize(Pool2, (struct DEVICE_EXTENSION *)((char *)this + 816));
        *((_QWORD *)this + 151) = v36;
        if ( v36 )
        {
          v37 = L2CapInt_Create();
          *((_QWORD *)this + 149) = v37;
          if ( v37 )
          {
            v38 = SdpInt_Create((struct DEVICE_EXTENSION *)((char *)this + 816));
            *((_QWORD *)this + 150) = v38;
            if ( v38 )
            {
              v39 = SMPInt_Create();
              *((_QWORD *)this + 153) = v39;
              if ( v39 )
              {
                v40 = (_SDP_DATABASE *)ExAllocatePool2(64, 208, 1346917442);
                if ( v40 )
                  v41 = _SDP_DATABASE::_SDP_DATABASE(v40);
                else
                  v41 = 0;
                v42 = *((_QWORD *)this + 108);
                v64[0] = 0;
                *((_QWORD *)this + 108) = v41;
                if ( v42 )
                  utl::default_delete<_SDP_DATABASE>::operator()();
                utl::unique_ptr<_SDP_DATABASE,utl::default_delete<_SDP_DATABASE>>::~unique_ptr<_SDP_DATABASE,utl::default_delete<_SDP_DATABASE>>(v64);
                v43 = (struct _SDP_DATABASE *)*((_QWORD *)this + 108);
                if ( v43 )
                {
                  v10 = SdpDB_Init(v43);
                  if ( v10 < 0 )
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) == 0
                      || (LOBYTE(v44) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                    {
                      LOBYTE(v44) = 0;
                    }
                    LOBYTE(v45) = 1;
                    WPP_RECORDER_AND_TRACE_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v44,
                      v45,
                      WPP_GLOBAL_Control->DeviceExtension,
                      2,
                      6,
                      24,
                      (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
                      v10);
                    return v10;
                  }
                  v10 = SdpDB_CreateAndAddDIDRecord(
                          *((struct _SDP_DATABASE **)this + 108),
                          (struct DEVICE_EXTENSION *)((char *)this + 816));
                  if ( v10 < 0 )
                  {
                    v12 = WPP_GLOBAL_Control;
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                    {
                      LOBYTE(v9) = 0;
                    }
                    v62 = v10;
                    v60 = *(_QWORD *)this;
                    v58 = 25;
                    goto LABEL_12;
                  }
                  v46 = (struct PDO_EXTENSION *)ExAllocatePool2(64, 80, 1346917442);
                  v49 = v46;
                  if ( v46 )
                  {
                    memset(v46, 0, sizeof(struct PDO_EXTENSION));
                    BthPdoInitExtension(v49, 0, *((struct _DEVICE_OBJECT **)this + 103));
                    v50 = (L2CAP_SERVER_INFO *)ExAllocatePool2(64, 104, 1346917442);
                    if ( v50 )
                    {
                      v53 = L2CAP_SERVER_INFO::L2CAP_SERVER_INFO(v50);
                      if ( v53 )
                      {
                        v53->Psm = 1;
                        v53->IndicationCallback = SdpInt_IndicationCallback;
                        v53->IndicationFlags = 0;
                        v53->IndicationContext = (void *)*((_QWORD *)this + 150);
                        v49->FakeChild = 1;
                        v49->ServerInfo = v53;
                        wil::acquire_kspin_lock(v64, (char *)this + 1088);
                        v54 = (Fdo **)*((_QWORD *)this + 135);
                        if ( *v54 != (Fdo *)((char *)this + 1072) )
                          __fastfail(3u);
                        v49->ChildListEntry.Flink = (_LIST_ENTRY *)((char *)this + 1072);
                        v49->ChildListEntry.Blink = (_LIST_ENTRY *)v54;
                        *v54 = (Fdo *)&v49->ChildListEntry;
                        *((_QWORD *)this + 135) = &v49->ChildListEntry;
                        wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v64);
                        HCI_CountAllLocalServices(*((struct HCI_INTERFACE **)this + 148));
                        v55 = (struct _DEVICE_OBJECT *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD))(WdfFunctions_01031 + 248))(
                                                         WdfDriverGlobals,
                                                         *(_QWORD *)this);
                        v10 = PoRegisterPowerSettingCallback(
                                v55,
                                &GUID_LOW_POWER_EPOCH,
                                BthConnectedStandbyCallback,
                                0,
                                (PVOID *)this + 171);
                        if ( v10 < 0 )
                        {
                          v12 = WPP_GLOBAL_Control;
                          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                            || (LOBYTE(v9) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                          {
                            LOBYTE(v9) = 0;
                          }
                          v62 = v10;
                          v60 = *(_QWORD *)this;
                          v58 = 28;
                          goto LABEL_12;
                        }
                        ErrorRecovery::Initialize(
                          (ErrorRecovery *)((char *)this + 1416),
                          (struct DEVICE_EXTENSION *)((char *)this + 816));
                        BthSetPolicyChangedCallback(EM_HandlePolicyUpdate, (char *)this + 816);
                        BthAddFdoToGlobalList(this);
                        *(_BYTE *)(*((_QWORD *)this + 148) + 4488LL) = (BthQueryRadioCompatFlags(
                                                                          v56,
                                                                          *((_QWORD *)this + 103))
                                                                      & 0x80) != 0;
                        result = 0;
                        *a2 = (struct _BTDEVICE *)((char *)this + 816);
                        return result;
                      }
                    }
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || (LOBYTE(v51) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                    {
                      LOBYTE(v51) = 0;
                    }
                    LOBYTE(v52) = 1;
                    WPP_RECORDER_AND_TRACE_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v51,
                      v52,
                      *((_QWORD *)this + 4),
                      2,
                      1,
                      27,
                      (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
                      *(_QWORD *)this);
                    BthPdoDestroyExtension(v49, 0);
                  }
                  else
                  {
                    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || (LOBYTE(v47) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
                    {
                      LOBYTE(v47) = 0;
                    }
                    LOBYTE(v48) = 1;
                    WPP_RECORDER_AND_TRACE_SF_q(
                      WPP_GLOBAL_Control->AttachedDevice,
                      v47,
                      v48,
                      *((_QWORD *)this + 4),
                      2,
                      1,
                      26,
                      (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
                      *(_QWORD *)this);
                  }
                }
              }
            }
          }
        }
      }
    }
    else
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 || (LOBYTE(v25) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
        LOBYTE(v25) = 0;
      LOBYTE(v24) = 1;
      WPP_RECORDER_AND_TRACE_SF_q(
        WPP_GLOBAL_Control->AttachedDevice,
        v25,
        v24,
        *((_QWORD *)this + 4),
        2,
        1,
        19,
        (__int64)WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids,
        *(_QWORD *)this);
      wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&void WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(v64);
    }
    return -1073741670;
  }
  return result;
}

```

## disassembly

```asm
0x14002a5b8  mov     [rsp-8+arg_10], rbx
0x14002a5bd  push    rbp
0x14002a5be  push    rsi
0x14002a5bf  push    rdi
0x14002a5c0  push    r12
0x14002a5c2  push    r13
0x14002a5c4  push    r14
0x14002a5c6  push    r15
0x14002a5c8  lea     rbp, [rsp-40h]
0x14002a5cd  sub     rsp, 140h
0x14002a5d4  mov     rax, cs:__security_cookie
0x14002a5db  xor     rax, rsp
0x14002a5de  mov     [rbp+70h+var_38], rax
0x14002a5e2  xor     eax, eax
0x14002a5e4  lea     r8, aIO; "I/O"
0x14002a5eb  xor     edi, edi
0x14002a5ed  mov     [rbp+70h+var_50], rax
0x14002a5f1  xorps   xmm0, xmm0
0x14002a5f4  mov     r14, rcx
0x14002a5f7  movups  [rbp+70h+var_70], xmm0
0x14002a5fb  lea     ecx, [rax+10h]
0x14002a5fe  mov     qword ptr [rbp+70h+var_70], rdi
0x14002a602  mov     r12, rdx
0x14002a605  mov     dword ptr [rbp+70h+var_70+0Ch], ecx
0x14002a608  mov     edx, ecx
0x14002a60a  mov     byte ptr [rbp+70h+var_70+8], dil
0x14002a60e  movups  [rbp+70h+var_80], xmm0
0x14002a612  lea     rcx, [rbp+70h+var_60]
0x14002a616  mov     dword ptr [rbp+70h+var_80], 38h ; '8'
0x14002a61d  movups  [rbp+70h+var_60], xmm0
0x14002a621  mov     byte ptr [rbp+70h+var_60], dil
0x14002a625  lea     r13d, [rdi+1]
0x14002a629  mov     eax, 7FFFFFFEh
0x14002a62e  test    rax, rax
0x14002a631  jz      short loc_14002A64C
0x14002a633  mov     r9b, [r8]
0x14002a636  test    r9b, r9b
0x14002a639  jz      short loc_14002A64C
0x14002a63b  mov     [rcx], r9b
0x14002a63e  add     r8, r13
0x14002a641  add     rcx, r13
0x14002a644  sub     rax, r13
0x14002a647  sub     rdx, r13
0x14002a64a  jnz     short loc_14002A62E
0x14002a64c  test    rdx, rdx
0x14002a64f  lea     rax, [rcx-1]
0x14002a653  mov     esi, 2
0x14002a658  cmovnz  rax, rcx
0x14002a65c  xor     edx, edx
0x14002a65e  lea     rcx, [r14+28h]
0x14002a662  mov     [rax], dil
0x14002a665  mov     dword ptr [rbp+70h+var_50], esi
0x14002a668  mov     dword ptr [rbp+70h+var_50+4], esi
0x14002a66b  mov     dword ptr [rbp+70h+var_80+4], 50485442h
0x14002a672  mov     dword ptr [rbp+70h+var_80+8], 1000h
0x14002a679  mov     dword ptr [rbp+70h+var_80+0Ch], 100h
0x14002a680  call    ?reset@?$unique_storage@U?$resource_policy@PEAURECORDER_LOG__@@P6AXPEAU1@@Z$1?WppRecorderLogCloseFunction@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAURECORDER_LOG__@@@Z; wil::details::unique_storage<wil::details::resource_policy<RECORDER_LOG__ *,void (*)(RECORDER_LOG__ *),&WppRecorderLogCloseFunction(RECORDER_LOG__ *),wistd::integral_constant<unsigned __int64,0>,RECORDER_LOG__ *,RECORDER_LOG__ *,0,std::nullptr_t>>::reset(RECORDER_LOG__ *)
0x14002a685  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a68c  lea     r8, [r14+28h]
0x14002a690  lea     rdx, [rbp+70h+var_80]
0x14002a694  call    cs:__imp_imp_WppRecorderLogCreate
0x14002a69b  nop     dword ptr [rax+rax+00h]
0x14002a6a0  mov     ebx, eax
0x14002a6a2  test    eax, eax
0x14002a6a4  jns     short loc_14002A702
0x14002a6a6  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a6ad  mov     ecx, [r10+2Ch]
0x14002a6b1  test    r13b, cl
0x14002a6b4  jz      short loc_14002A6BF
0x14002a6b6  mov     dl, r13b
0x14002a6b9  cmp     [r10+29h], sil
0x14002a6bd  jnb     short loc_14002A6C2
0x14002a6bf  mov     dl, dil
0x14002a6c2  mov     rax, [r14]
0x14002a6c5  mov     dword ptr [rsp+170h+var_128], ebx
0x14002a6c9  mov     [rsp+170h+var_130], rax
0x14002a6ce  lea     rax, WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids
0x14002a6d5  mov     [rsp+170h+var_138], rax
0x14002a6da  mov     [rsp+170h+var_140], 0Fh
0x14002a6e1  mov     [rsp+170h+var_148], r13d
0x14002a6e6  mov     byte ptr [rsp+170h+Handle], sil
0x14002a6eb  mov     r9, [r14+20h]
0x14002a6ef  mov     r8b, r13b
0x14002a6f2  mov     rcx, [r10+18h]
0x14002a6f6  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14002a6fb  mov     eax, ebx
0x14002a6fd  jmp     loc_14002B247
0x14002a702  mov     rax, [r14+18h]
0x14002a706  mov     rcx, cs:WdfDriverGlobals
0x14002a70d  mov     rdx, [rax]
0x14002a710  mov     rax, cs:WdfFunctions_01031
0x14002a717  mov     rdx, [rdx]
0x14002a71a  mov     rax, [rax+3B0h]
0x14002a721  call    _guard_dispatch_icall
0x14002a726  lea     rdx, BTHPORT_RegisterMiniport; ClientIdentificationAddress
0x14002a72d  mov     rcx, rax; DriverObject
0x14002a730  call    cs:__imp_IoGetDriverObjectExtension
0x14002a737  nop     dword ptr [rax+rax+00h]
0x14002a73c  mov     rcx, cs:WdfFunctions_01031
0x14002a743  mov     rsi, rax
0x14002a746  mov     rdx, [r14]
0x14002a749  mov     rax, [rcx+100h]
0x14002a750  mov     rcx, cs:WdfDriverGlobals
0x14002a757  call    _guard_dispatch_icall
0x14002a75c  mov     rcx, cs:WdfFunctions_01031
0x14002a763  mov     rdi, rax
0x14002a766  mov     rdx, [r14]
0x14002a769  mov     rax, [rcx+108h]
0x14002a770  mov     rcx, cs:WdfDriverGlobals
0x14002a777  call    _guard_dispatch_icall
0x14002a77c  mov     rcx, cs:WdfFunctions_01031
0x14002a783  mov     rbx, rax
0x14002a786  mov     rdx, [r14]
0x14002a789  mov     rax, [rcx+0F8h]
0x14002a790  mov     rcx, cs:WdfDriverGlobals
0x14002a797  call    _guard_dispatch_icall
0x14002a79c  lea     r15, [r14+330h]
0x14002a7a3  mov     [rsp+170h+Handle], rsi; const struct _BTH_MINIPORT_DESCRIPTOR *
0x14002a7a8  mov     rcx, r15; struct DEVICE_EXTENSION *
0x14002a7ab  mov     r9, rdi; struct _DEVICE_OBJECT *
0x14002a7ae  mov     r8, rbx; struct _DEVICE_OBJECT *
0x14002a7b1  mov     rdx, rax; struct _DEVICE_OBJECT *
0x14002a7b4  call    ?BthInitExtension@@YAJPEAUDEVICE_EXTENSION@@PEAU_DEVICE_OBJECT@@11PEBU_BTH_MINIPORT_DESCRIPTOR@@@Z; BthInitExtension(DEVICE_EXTENSION *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_DEVICE_OBJECT *,_BTH_MINIPORT_DESCRIPTOR const *)
0x14002a7b9  xor     esi, esi
0x14002a7bb  test    eax, eax
0x14002a7bd  js      loc_14002B247
0x14002a7c3  mov     rax, cs:WdfFunctions_01031
0x14002a7ca  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x14002a7d1  mov     rdx, [r14]
0x14002a7d4  xor     r9d, r9d
0x14002a7d7  mov     rcx, cs:WdfDriverGlobals
0x14002a7de  mov     rax, [rax+268h]
0x14002a7e5  call    _guard_dispatch_icall
0x14002a7ea  mov     ebx, eax
0x14002a7ec  test    eax, eax
0x14002a7ee  jns     short loc_14002A83B
0x14002a7f0  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a7f7  mov     ecx, [r10+2Ch]
0x14002a7fb  test    r13b, cl
0x14002a7fe  jz      short loc_14002A80A
0x14002a800  cmp     byte ptr [r10+29h], 2
0x14002a805  mov     dl, r13b
0x14002a808  jnb     short loc_14002A80D
0x14002a80a  mov     dl, sil
0x14002a80d  mov     rax, [r14]
0x14002a810  mov     dword ptr [rsp+170h+var_128], ebx
0x14002a814  mov     [rsp+170h+var_130], rax
0x14002a819  lea     rax, WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids
0x14002a820  mov     [rsp+170h+var_138], rax
0x14002a825  mov     [rsp+170h+var_140], 10h
0x14002a82c  mov     [rsp+170h+var_148], r13d
0x14002a831  mov     byte ptr [rsp+170h+Handle], 2
0x14002a836  jmp     loc_14002A6EB
0x14002a83b  cmp     cs:WdfClientVersionHigherThanFramework, sil
0x14002a842  jz      short loc_14002A87A
0x14002a844  mov     r9d, 1C9h
0x14002a84a  cmp     cs:WdfFunctionCount, r9d
0x14002a851  ja      short loc_14002A87A
0x14002a853  mov     rax, cs:WdfFunctions_01031
0x14002a85a  xor     r8d, r8d
0x14002a85d  mov     rcx, cs:WdfDriverGlobals
0x14002a864  mov     byte ptr [rsp+170h+Handle], sil
0x14002a869  mov     rax, [rax+0E20h]
0x14002a870  mov     rdx, [rcx]
0x14002a873  call    _guard_dispatch_icall
0x14002a878  jmp     short loc_14002A8A6
0x14002a87a  mov     rax, cs:WdfFunctions_01031
0x14002a881  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x14002a888  mov     rdx, [r14]
0x14002a88b  xor     r9d, r9d
0x14002a88e  mov     rcx, cs:WdfDriverGlobals
0x14002a895  mov     byte ptr [rsp+170h+Handle], sil
0x14002a89a  mov     rax, [rax+0E48h]
0x14002a8a1  call    _guard_dispatch_icall
0x14002a8a6  lea     rbx, [r14+320h]
0x14002a8ad  mov     rdx, [rbx]
0x14002a8b0  test    rdx, rdx
0x14002a8b3  jz      short loc_14002A8CF
0x14002a8b5  mov     rax, cs:WdfFunctions_01031
0x14002a8bc  mov     rcx, cs:WdfDriverGlobals
0x14002a8c3  mov     rax, [rax+680h]
0x14002a8ca  call    _guard_dispatch_icall
0x14002a8cf  mov     [rbx], rsi
0x14002a8d2  mov     r9, rbx
0x14002a8d5  mov     rax, cs:WdfFunctions_01031
0x14002a8dc  xor     r8d, r8d
0x14002a8df  mov     rcx, cs:WdfDriverGlobals
0x14002a8e6  xor     edx, edx
0x14002a8e8  mov     rax, [rax+9A0h]
0x14002a8ef  call    _guard_dispatch_icall
0x14002a8f4  mov     edi, eax
0x14002a8f6  test    eax, eax
0x14002a8f8  jns     short loc_14002A957
0x14002a8fa  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a901  mov     ecx, [r10+2Ch]
0x14002a905  test    r13b, cl
0x14002a908  jz      short loc_14002A914
0x14002a90a  cmp     byte ptr [r10+29h], 2
0x14002a90f  mov     dl, r13b
0x14002a912  jnb     short loc_14002A917
0x14002a914  mov     dl, sil
0x14002a917  mov     rax, [r14]
0x14002a91a  mov     dword ptr [rsp+170h+var_128], edi
0x14002a91e  mov     [rsp+170h+var_130], rax
0x14002a923  lea     rax, WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids
0x14002a92a  mov     [rsp+170h+var_138], rax
0x14002a92f  mov     [rsp+170h+var_140], 11h
0x14002a936  mov     r9, [r14+20h]
0x14002a93a  mov     r8b, r13b
0x14002a93d  mov     rcx, [r10+18h]
0x14002a941  mov     [rsp+170h+var_148], r13d
0x14002a946  mov     byte ptr [rsp+170h+Handle], 2
0x14002a94b  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14002a950  mov     eax, edi
0x14002a952  jmp     loc_14002B247
0x14002a957  mov     rcx, [rbx]
0x14002a95a  lea     r8, GUID_BTHPORT_DEVICE_INTERFACE
0x14002a961  mov     rax, cs:WdfFunctions_01031
0x14002a968  xor     r9d, r9d
0x14002a96b  mov     rdx, [r14]
0x14002a96e  mov     [rsp+170h+Handle], rcx
0x14002a973  mov     rcx, cs:WdfDriverGlobals
0x14002a97a  mov     rax, [rax+278h]
0x14002a981  call    _guard_dispatch_icall
0x14002a986  mov     edi, eax
0x14002a988  test    eax, eax
0x14002a98a  jns     short loc_14002A9CD
0x14002a98c  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002a993  mov     ecx, [r10+2Ch]
0x14002a997  test    r13b, cl
0x14002a99a  jz      short loc_14002A9A6
0x14002a99c  cmp     byte ptr [r10+29h], 2
0x14002a9a1  mov     dl, r13b
0x14002a9a4  jnb     short loc_14002A9A9
0x14002a9a6  mov     dl, sil
0x14002a9a9  mov     rax, [r14]
0x14002a9ac  mov     dword ptr [rsp+170h+var_128], edi
0x14002a9b0  mov     [rsp+170h+var_130], rax
0x14002a9b5  lea     rax, WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids
0x14002a9bc  mov     [rsp+170h+var_138], rax
0x14002a9c1  mov     [rsp+170h+var_140], 12h
0x14002a9c8  jmp     loc_14002A936
0x14002a9cd  mov     rax, cs:WdfFunctions_01031
0x14002a9d4  lea     r8, [r15+60h]
0x14002a9d8  mov     rdx, [rbx]
0x14002a9db  mov     rcx, cs:WdfDriverGlobals
0x14002a9e2  mov     rax, [rax+9A8h]
0x14002a9e9  call    _guard_dispatch_icall
0x14002a9ee  lea     rdx, [rsp+170h+var_120]
0x14002a9f3  mov     rcx, r14
0x14002a9f6  call    ?GetDeviceParametersKey@Fdo@@QEBA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUWDFKEY__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Fdo::GetDeviceParametersKey(void)
0x14002a9fb  mov     rdx, [rsp+170h+var_120]
0x14002aa00  test    rdx, rdx
0x14002aa03  jz      loc_14002B1E8
0x14002aa09  mov     rax, cs:WdfFunctions_01031
0x14002aa10  lea     r8, asc_140170930; " \""
0x14002aa17  mov     r9, [rbx]
0x14002aa1a  mov     rcx, cs:WdfDriverGlobals
0x14002aa21  mov     rax, [rax+7A8h]
0x14002aa28  call    _guard_dispatch_icall
0x14002aa2d  mov     ebx, eax
0x14002aa2f  test    eax, eax
0x14002aa31  jns     short loc_14002AA98
0x14002aa33  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002aa3a  mov     ecx, [r10+2Ch]
0x14002aa3e  test    r13b, cl
0x14002aa41  jz      short loc_14002AA4D
0x14002aa43  cmp     byte ptr [r10+29h], 2
0x14002aa48  mov     dl, r13b
0x14002aa4b  jnb     short loc_14002AA50
0x14002aa4d  mov     dl, sil
0x14002aa50  mov     rax, [r14]
0x14002aa53  mov     r8b, r13b
0x14002aa56  mov     r9, [r14+20h]
0x14002aa5a  mov     rcx, [r10+18h]
0x14002aa5e  mov     dword ptr [rsp+170h+var_128], ebx
0x14002aa62  mov     [rsp+170h+var_130], rax
0x14002aa67  lea     rax, WPP_311f3abf28d23acb4dcb40c39fbdb816_Traceguids
0x14002aa6e  mov     [rsp+170h+var_138], rax
0x14002aa73  mov     [rsp+170h+var_140], 14h
0x14002aa7a  mov     [rsp+170h+var_148], r13d
0x14002aa7f  mov     byte ptr [rsp+170h+Handle], 2
0x14002aa84  call    WPP_RECORDER_AND_TRACE_SF_qL
0x14002aa89  lea     rcx, [rsp+170h+var_120]
0x14002aa8e  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x14002aa93  jmp     loc_14002A6FB
0x14002aa98  lea     rcx, [rsp+170h+var_120]
0x14002aa9d  call    ??1?$unique_storage@U?$resource_policy@PEAUWDFSTRING__@@P6AXPEAX@Z$1?WdfObjectDelete@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<WDFSTRING__ *,void (*)(void *),&WdfObjectDelete(void *),wistd::integral_constant<unsigned __int64,0>,WDFSTRING__ *,WDFSTRING__ *,0,std::nullptr_t>>(void)
0x14002aaa2  lea     rcx, [r14+6E0h]; this
0x14002aaa9  call    ?Initialize@RadioStateManager@@QEAAJXZ; RadioStateManager::Initialize(void)
0x14002aaae  test    eax, eax
0x14002aab0  js      loc_14002B247
0x14002aab6  lea     rcx, [r14+30h]; this
0x14002aaba  call    ?Initialize@Controller@@QEAAJXZ; Controller::Initialize(void)
0x14002aabf  test    eax, eax
0x14002aac1  js      loc_14002B247
0x14002aac7  xorps   xmm0, xmm0
0x14002aaca  or      edx, 0FFFFFFFFh
0x14002aacd  cmp     cs:WdfClientVersionHigherThanFramework, sil
0x14002aad4  movups  [rbp+70h+var_80], xmm0
  ... truncated ...
```
