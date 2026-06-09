# PhoneController::_OnCallsChanged(_GUID const &,utl::vector<CallUpdate,utl::allocator<CallUpdate>> const &)

- ea: `0x180041858`
- end: `0x180042430`
- name: `?_OnCallsChanged@PhoneController@@IEAAJAEBU_GUID@@AEBV?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@@Z`
- size: `3032`
- prototype: `__int64 __fastcall(PhoneController *this, struct _GUID *)`
- caller_count: `6`
- callee_count: `41`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180025b90`
- `0x1800384bc`
- `0x180038d2c`
- `0x18003d4bc`
- `0x180042438`
- `0x180049f94`

## callees

- `0x180001348`
- `0x180003fb4`
- `0x180004130`
- `0x1800056a0`
- `0x180006e94`
- `0x18000e1a4`
- `0x18001cc00`
- `0x1800239bc`
- `0x180023a24`
- `0x18002888c`
- `0x18002c574`
- `0x18002c580`
- `0x18003541c`
- `0x180037efc`
- `0x1800380bc`
- `0x180039008`
- `0x180039148`
- `0x180039300`
- `0x180039754`
- `0x180041858`
- `0x180046620`
- `0x1800473b8`
- `0x180049000`
- `0x18004a480`
- `0x18004a5b4`
- `0x18004ad74`
- `0x18004edd4`
- `0x18004ef10`
- `0x18004f158`
- `0x18004f76c`
- `0x180051e44`
- `0x180052338`
- `0x1800524c8`
- `0x18005354c`
- `0x1800539a8`
- `0x18007177c`
- `0x18007f9ec`
- `0x18008d936`
- `0x18008d942`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041895`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800418b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041f5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041f7c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041895`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800418b9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041f5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180041f7c`

## string_xrefs

- `0x18004189b`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041c27`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041c5f`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041db5`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041e02`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041e58`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041ea3`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041f07`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041f40`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041f70`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041fb7`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180041ff8`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180042064`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180042092`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800420e6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180042137`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800422d6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180042363`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_OnCallsChanged(PhoneController *this, struct _GUID *a2, __int64 a3)
{
  __int64 v6; // rcx
  PhoneLineStorage *v7; // rcx
  int PhoneLine; // eax
  BackTraceCollection *v9; // rcx
  unsigned int v10; // ebx
  __int64 v11; // rax
  void (*v12)(void); // rax
  const void *v14; // r9
  BackTraceCollection *v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // r15
  unsigned __int64 v18; // rbx
  __int64 v19; // rdx
  char v20; // al
  size_t v21; // rbx
  const struct CallUpdate *v22; // r15
  PhoneLine *v23; // r12
  __int64 v24; // rbx
  __m128i si128; // xmm6
  PhoneCallStorage *v26; // rcx
  int v27; // r13d
  unsigned int *v28; // r15
  _BYTE *v29; // r13
  __int64 v30; // rcx
  int AllCalls; // eax
  BackTraceCollection *v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  unsigned int v35; // edi
  __int64 *v36; // rdi
  int v37; // r12d
  __int64 v38; // rcx
  unsigned int v39; // eax
  int v40; // ecx
  __int64 v41; // rdi
  struct _GUID v42; // xmm0
  int v43; // eax
  int v44; // eax
  int IsMuted; // eax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rcx
  PhoneController *v51; // rcx
  const unsigned __int16 *v52; // rax
  __int128 v53; // xmm0
  __int64 v54; // rcx
  __int64 v55; // r8
  __int64 v56; // r9
  int v57; // eax
  int v58; // eax
  __int64 v59; // rcx
  int v60; // eax
  int v61; // eax
  int v62; // eax
  __int64 v63; // rcx
  int v64; // eax
  BackTraceCollection *v65; // rcx
  unsigned int v66; // r13d
  __int64 v67; // rax
  struct CallInfo *v68; // rdi
  int v69; // eax
  BackTraceCollection *v70; // rcx
  __int64 v71; // r9
  int v72; // eax
  BackTraceCollection *v73; // rcx
  int v74; // eax
  int v75; // eax
  int v76; // eax
  __int64 v77; // rdx
  __int64 v78; // rcx
  PhoneController *v79; // rcx
  const unsigned __int16 *v80; // rax
  __int128 v81; // xmm0
  __int64 v82; // rcx
  __int64 v83; // r8
  __int64 v84; // r9
  int v85; // eax
  BackTraceCollection *v86; // rcx
  int v87; // edx
  int v88[2]; // [rsp+60h] [rbp-A0h] BYREF
  BOOL v89; // [rsp+68h] [rbp-98h]
  struct CallInfo *v90; // [rsp+70h] [rbp-90h] BYREF
  int v91[2]; // [rsp+78h] [rbp-88h] BYREF
  struct _GUID Buf1; // [rsp+80h] [rbp-80h] BYREF
  struct _GUID Buf2; // [rsp+90h] [rbp-70h] BYREF
  PhoneLine *v94; // [rsp+A0h] [rbp-60h] BYREF
  int v95; // [rsp+A8h] [rbp-58h] BYREF
  int v96; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v97; // [rsp+B0h] [rbp-50h] BYREF
  int v98; // [rsp+B4h] [rbp-4Ch] BYREF
  int v99; // [rsp+B8h] [rbp-48h] BYREF
  int v100; // [rsp+BCh] [rbp-44h] BYREF
  struct _GUID *v101; // [rsp+C0h] [rbp-40h]
  const struct CallUpdate *v102; // [rsp+C8h] [rbp-38h]
  __int128 v103; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v104; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v105; // [rsp+F0h] [rbp-10h]
  void *Block[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int16 v107; // [rsp+108h] [rbp+8h] BYREF
  __int64 v108; // [rsp+10Ah] [rbp+Ah]
  int v109; // [rsp+112h] [rbp+12h]
  __int16 v110; // [rsp+116h] [rbp+16h]
  __m128i v111; // [rsp+118h] [rbp+18h] BYREF
  __int64 v112; // [rsp+128h] [rbp+28h]

  v101 = a2;
  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v6, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1934);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  v7 = (PhoneLineStorage *)*((_QWORD *)this + 19);
  v94 = 0;
  PhoneLine = PhoneLineStorage::GetPhoneLine(v7, a2, &v94, 0);
  v10 = PhoneLine;
  if ( PhoneLine < 0 )
  {
    BackTraceCollection::Capture(v9, PhoneLine);
    Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1939);
    if ( !v94 )
      return v10;
    v11 = *(_QWORD *)v94;
LABEL_7:
    v12 = *(void (**)(void))(v11 + 16);
    goto LABEL_8;
  }
  v14 = *(const void **)a3;
  v15 = (BackTraceCollection *)(*(_QWORD *)(a3 + 8) - *(_QWORD *)a3);
  *(_QWORD *)&v104 = -1;
  v16 = -1;
  v105 = -1;
  v17 = -1;
  *((_QWORD *)&v104 + 1) = -1;
  v18 = (__int64)v15 / 3904;
  if ( !((__int64)v15 / 3904) )
    goto LABEL_17;
  if ( v18 <= 8 )
  {
    v19 = 8;
  }
  else
  {
    if ( v18 > 0x864B8A7DE6D1DLL )
    {
LABEL_32:
      v10 = -2147024882;
      BackTraceCollection::Capture(v15, -2147024882);
      Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1947);
      if ( v16 != -1 )
        operator delete((void *)v16);
      if ( !v94 )
        return v10;
      v12 = *(void (**)(void))(*(_QWORD *)v94 + 16LL);
LABEL_8:
      v12();
      return v10;
    }
    v19 = (__int64)v15 / 3904;
  }
  v20 = utl::vector<CallUpdate,utl::allocator<CallUpdate>>::_SetCapacity(&v104, v19);
  v16 = v104;
  if ( !v20 )
    goto LABEL_32;
  v14 = *(const void **)a3;
  v17 = *((_QWORD *)&v104 + 1);
LABEL_17:
  v21 = 3904 * v18;
  memcpy_0((void *)v17, v14, v21);
  v22 = (const struct CallUpdate *)(v21 + v17);
  v102 = v22;
  utl::_SortImp<utl::_ArrayIt<CallUpdate>,__int64,int (*)(CallUpdate const &,CallUpdate const &)>(
    (const struct CallUpdate *)v16,
    v22,
    0x4FBCDA3AC10C9715LL * (((__int64)v22 - v16) >> 6));
  v23 = v94;
  v24 = v16;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v89 = 0;
  while ( 1 )
  {
    v26 = (PhoneCallStorage *)*((_QWORD *)this + 12);
    if ( (const struct CallUpdate *)v24 == v22 )
      break;
    v27 = *((_DWORD *)this + 78);
    LODWORD(v90) = v27;
    v91[0] = 0;
    *(_QWORD *)&Buf1.Data1 = 0;
    PhoneCallStorage::FindCall(v26, &Buf1, v24, 0);
    v28 = *(unsigned int **)&Buf1.Data1;
    if ( *(_QWORD *)&Buf1.Data1 )
    {
      v29 = (_BYTE *)(v24 + 8);
      if ( *(_DWORD *)(*(_QWORD *)&Buf1.Data1 + 3072LL) && (*v29 & 0x40) != 0 && *(_DWORD *)(v24 + 764) == 27 )
      {
        v30 = *((_QWORD *)this + 12);
        v88[0] = *(_DWORD *)(*(_QWORD *)&Buf1.Data1 + 3068LL);
        v111 = si128;
        v112 = -1;
        AllCalls = PhoneCallStorage::GetAllCalls(v30, &v111, 0);
        v35 = AllCalls;
        if ( AllCalls < 0 )
        {
          BackTraceCollection::Capture(v32, AllCalls);
          Log_HREvent_7(v35, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 1980);
          utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v111);
          (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v28 + 16LL))(v28);
          if ( !v89 )
            PhoneController::_DisablePhoneCallAudioIfNotNeeded(this);
          if ( v16 != -1 )
            operator delete((void *)v16);
          if ( v23 )
            (*(void (__fastcall **)(PhoneLine *))(*(_QWORD *)v23 + 16LL))(v23);
          return v35;
        }
        v36 = (__int64 *)v111.m128i_i64[0];
        v37 = v88[0];
        while ( v36 != (__int64 *)v111.m128i_i64[1] )
        {
          v38 = *v36;
          if ( (unsigned int *)*v36 != v28 && *(_DWORD *)(v38 + 3072) == v28[768] )
          {
            if ( (unsigned int)dword_1800B3200 > 4 )
            {
              Buf1.Data1 = *(_DWORD *)(v38 + 3068);
              *(_QWORD *)&Buf2.Data1 = "PhoneController: Call callId";
              v88[0] = v37;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                v38,
                (int)word_1800A877A,
                v33,
                v34,
                (const unsigned __int16 **)&Buf2,
                (__int64)&Buf1,
                (__int64)v88);
            }
            *(_DWORD *)(*v36 + 5264) = 1;
          }
          ++v36;
        }
        utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>((__int64)&v111);
        v23 = v94;
      }
      if ( (*v29 & 0x20) != 0 )
      {
        v39 = *(_DWORD *)(v24 + 760);
        if ( v39 == 4 )
        {
          v28[1706] &= ~8u;
        }
        else if ( v39 <= 6 )
        {
          v40 = 73;
          if ( _bittest(&v40, v39) )
            v28[1706] &= ~0x10u;
        }
      }
      *(_QWORD *)&Buf1.Data1 = 0;
      CallInfo::GetPhoneLine((CallInfo *)v28, (struct PhoneLine **)&Buf1);
      v41 = *(_QWORD *)&Buf1.Data1;
      v42 = *(struct _GUID *)(*(_QWORD *)&Buf1.Data1 + 88LL);
      Buf1 = *(struct _GUID *)((char *)v23 + 88);
      Buf2 = v42;
      if ( memcmp_0(&Buf1, &Buf2, 0x10u) )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
        goto LABEL_118;
      }
      if ( !(_DWORD)v90 && !v28[764] )
      {
        v43 = PhoneController::_ProcessIncomingPhoneCallFilters(this, v23, (const struct CallUpdate *)v24, v91);
        if ( v43 < 0 )
          Log_HREvent_7(
            (unsigned int)v43,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            2025);
        if ( v91[0] )
          v28[770] |= 0x400u;
      }
      v44 = PhoneController::_EnforceMultiCallPolicyForExistingCall(this, v23, (const struct CallUpdate *)v24);
      if ( v44 < 0 )
        Log_HREvent_7((unsigned int)v44, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2033);
      if ( (*v29 & 0x20) != 0 )
      {
        if ( (unsigned int)dword_1800B3200 > 4 )
        {
          IsMuted = PhoneLine::IsMuted(v23);
          v46 = *(unsigned int *)(v24 + 760);
          v95 = IsMuted;
          v96 = *(_DWORD *)(v24 + 764);
          v48 = PhoneController::ConvertCallStateToString(v47, v46);
          v49 = v28[760];
          *(_QWORD *)&Buf2.Data1 = v48;
          v90 = (struct CallInfo *)PhoneController::ConvertCallStateToString(v50, v49);
          v97 = v28[767];
          Buf1 = (struct _GUID)*((_OWORD *)v23 + 7);
          v52 = PhoneController::ConvertLineTypeToString(v51, &Buf1);
          v53 = *(_OWORD *)((char *)v23 + 88);
          *(_QWORD *)&Buf1.Data1 = v52;
          *(_QWORD *)v88 = &v103;
          *(_QWORD *)v91 = "Call state changed";
          v103 = v53;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v54,
            (int)&dword_1800A86EC,
            v55,
            v56,
            (const unsigned __int16 **)v91,
            (__int64 *)v88,
            (const unsigned __int16 **)&Buf1,
            (__int64)&v97,
            (const unsigned __int16 **)&v90,
            (const unsigned __int16 **)&Buf2,
            (__int64)&v96,
            (__int64)&v95);
        }
        Buf2 = (struct _GUID)*((_OWORD *)v23 + 7);
        if ( !memcmp_0(&Buf2, &BluetoothHandsFreeLineType, 0x10u) && *(_DWORD *)(v24 + 760) == 3 && v28[760] <= 2 )
        {
          if ( (unsigned int)PhoneLine::IsMuted(v23) )
          {
            v57 = PhoneController::_ExecuteLineAction(this, v23, 2);
            if ( v57 < 0 )
              Log_HREvent_7(
                (unsigned int)v57,
                0,
                "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
                2060);
          }
        }
      }
      CallInfo::UpdateCall((CallInfo *)v28, (const struct CallUpdate *)v24, 0);
      Buf2 = (struct _GUID)*((_OWORD *)v23 + 7);
      PhoneController::_UpdateCallUpgradeState(this, &Buf2, (struct CallInfo *)v28);
      v58 = PhoneController::_UpgradeToRealTimeTextCallIfPending(this, (struct CallInfo *)v28);
      if ( v58 < 0 )
        Log_HREvent_7((unsigned int)v58, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2072);
      if ( (*(_DWORD *)(v24 + 8) & 0x1000000) != 0 && *(_DWORD *)(v24 + 2520) )
      {
        Buf2 = (struct _GUID)*((_OWORD *)v23 + 7);
        if ( memcmp_0(&Buf2, VoipLineType, 0x10u) )
        {
          Log_AssertionEvent_3(v59, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2077);
          Buf2 = (struct _GUID)*((_OWORD *)v23 + 7);
          if ( memcmp_0(&Buf2, VoipLineType, 0x10u) )
            MicrosoftTelemetryAssertTriggeredNoArgs();
        }
        v60 = PhoneController::_EndUpgradeFromCall(this, (struct CallInfo *)v28);
        if ( v60 < 0 )
          Log_HREvent_7(
            (unsigned int)v60,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            2078);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      goto LABEL_107;
    }
    v88[0] = 0;
    if ( !v27 )
    {
      v61 = PhoneController::_ProcessIncomingPhoneCallFilters(this, v23, (const struct CallUpdate *)v24, v91);
      if ( v61 < 0 )
        Log_HREvent_7((unsigned int)v61, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2090);
    }
    v62 = PhoneController::_EnforceMultiCallPolicyForNewCall(this, v23, (const struct CallUpdate *)v24, v88);
    if ( v62 < 0 )
      Log_HREvent_7((unsigned int)v62, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2098);
    if ( v88[0] )
      goto LABEL_119;
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
    {
      Log_AssertionEvent_3(v63, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3043);
      if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
        MicrosoftTelemetryAssertTriggeredNoArgs();
    }
    v90 = 0;
    v64 = CallInfo::CreateInstance(&v90);
    v66 = v64;
    if ( v64 >= 0 )
    {
      if ( (*(_DWORD *)(v24 + 8) & 0x220LL) != 0x220 )
      {
        Log_AssertionEvent_3(v65, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3048);
        if ( (*(_DWORD *)(v24 + 8) & 0x220LL) != 0x220 )
          MicrosoftTelemetryAssertTriggeredNoArgs();
      }
      v68 = v90;
      v69 = CallInfo::Initialize(v90, this, v23, v24);
      v66 = v69;
      if ( v69 >= 0 )
      {
        v72 = PhoneCallStorage::AddCall(*((PhoneCallStorage **)this + 12), v68);
        v66 = v72;
        if ( v72 >= 0 )
        {
          if ( v68 )
            (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v68 + 16LL))(v68);
          goto LABEL_97;
        }
        BackTraceCollection::Capture(v73, v72);
        v71 = 3052;
      }
      else
      {
        BackTraceCollection::Capture(v70, v69);
        v71 = 3050;
      }
      Log_HREvent_7(v66, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v71);
      if ( v68 )
      {
        v67 = *(_QWORD *)v68;
        goto LABEL_93;
      }
    }
    else
    {
      BackTraceCollection::Capture(v65, v64);
      Log_HREvent_7(v66, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 3046);
      if ( v90 )
      {
        v67 = *(_QWORD *)v90;
LABEL_93:
        (*(void (**)(void))(v67 + 16))();
      }
    }
    Log_HREvent_7(v66, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2109);
LABEL_97:
    v29 = (_BYTE *)(v24 + 8);
    if ( (*(_DWORD *)(v24 + 8) & 0x400000) != 0 )
    {
      if ( *(_DWORD *)(v24 + 2500) )
      {
        v74 = PhoneController::_AssociateCallUpgradeCalls(this, (const struct CallUpdate *)v24);
        if ( v74 < 0 )
          Log_HREvent_7(
            (unsigned int)v74,
            0,
            "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp",
            2113);
      }
    }
    v108 = 0;
    v110 = 0;
    v109 = 0;
    Block[0] = &v107;
    Block[1] = &v107;
    v107 = 0;
    v75 = GetDeviceIdsListFromCallUpdateAsString(v24, Block);
    if ( v75 < 0 )
      Log_HREvent_7((unsigned int)v75, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2117);
    if ( (unsigned int)dword_1800B3200 > 4 )
    {
      *(void **)&Buf2.Data1 = Block[0];
      v76 = PhoneLine::IsMuted(v23);
      v77 = *(unsigned int *)(v24 + 760);
      v98 = v76;
      v99 = *(_DWORD *)(v24 + 764);
      v90 = (struct CallInfo *)PhoneController::ConvertCallStateToString(v78, v77);
      v100 = *(_DWORD *)v24;
      Buf1 = (struct _GUID)*((_OWORD *)v23 + 7);
      v80 = PhoneController::ConvertLineTypeToString(v79, &Buf1);
      v81 = *(_OWORD *)((char *)v23 + 88);
      *(_QWORD *)&Buf1.Data1 = v80;
      *(_QWORD *)v88 = &v104;
      *(_QWORD *)v91 = "Call added";
      v104 = v81;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v82,
        (int)byte_1800A865D,
        v83,
        v84,
        (const unsigned __int16 **)v91,
        (__int64 *)v88,
        (const unsigned __int16 **)&Buf1,
        (__int64)&v100,
        (const unsigned __int16 **)&v90,
        (__int64)&v99,
        (__int64)&v98,
        (const unsigned __int16 **)&Buf2);
    }
    if ( Block[0] != &v107 )
      operator delete(Block[0]);
LABEL_107:
    if ( (*v29 & 0x20) != 0 && ((*(_DWORD *)(v24 + 760) - 1) & 0xFFFFFFFB) != 0 )
      v89 = (int)PhoneController::_EnablePhoneCallAudio(this, v101, 0, *(_DWORD *)(v24 + 768) == 1) >= 0;
    if ( v28 )
    {
      if ( v28[760] == 1 && v28[764] == 1 )
LABEL_116:
        *((_DWORD *)this + 68) = 1;
      if ( !v28 )
        goto LABEL_119;
LABEL_118:
      (*(void (__fastcall **)(unsigned int *))(*(_QWORD *)v28 + 16LL))(v28);
      goto LABEL_119;
    }
    if ( (*(_BYTE *)(v24 + 8) & 0x20) != 0 && *(_DWORD *)(v24 + 760) == 1 )
      goto LABEL_116;
LABEL_119:
    v22 = v102;
    v24 += 3904;
  }
  PhoneCallStorage::RemoveIdleCalls(v26, 0);
  v85 = PhoneController::_SendDeferredAudioStateChangeNotification(this);
  v10 = v85;
  if ( v85 >= 0 )
  {
    v87 = *((_DWORD *)this + 68);
    *((_DWORD *)this + 68) = 0;
    PhoneController::_UpdateControllerAndNotifyClients(this, v87);
    if ( !v89 )
      PhoneController::_DisablePhoneCallAudioIfNotNeeded(this);
    if ( v16 != -1 )
      operator delete((void *)v16);
    if ( v23 )
      (*(void (__fastcall **)(PhoneLine *))(*(_QWORD *)v23 + 16LL))(v23);
    return 0;
  }
  else
  {
    BackTraceCollection::Capture(v86, v85);
    Log_HREvent_7(v10, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 2194);
    if ( !v89 )
      PhoneController::_DisablePhoneCallAudioIfNotNeeded(this);
    if ( v16 != -1 )
      operator delete((void *)v16);
    if ( v23 )
    {
      v11 = *(_QWORD *)v23;
      goto LABEL_7;
    }
    return v10;
  }
}

```

## disassembly

```asm
0x180041858  mov     rax, rsp
0x18004185b  mov     [rax+20h], rbx
0x18004185f  push    rbp
0x180041860  push    rsi
0x180041861  push    rdi
0x180041862  push    r12
0x180041864  push    r13
0x180041866  push    r14
0x180041868  push    r15
0x18004186a  lea     rbp, [rsp-50h]
0x18004186f  sub     rsp, 150h
0x180041876  movaps  xmmword ptr [rax-48h], xmm6
0x18004187a  mov     rax, cs:__security_cookie
0x180041881  xor     rax, rsp
0x180041884  mov     [rbp+80h+var_50], rax
0x180041888  mov     rdi, r8
0x18004188b  mov     [rbp+80h+var_C0], rdx
0x18004188f  mov     rbx, rdx
0x180041892  mov     r14, rcx
0x180041895  call    cs:__imp_GetCurrentThreadId
0x18004189b  lea     r13, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800418a2  cmp     [r14+0F0h], eax
0x1800418a9  jz      short loc_1800418CD
0x1800418ab  mov     r8d, 78Eh
0x1800418b1  mov     rdx, r13
0x1800418b4  call    Log_AssertionEvent_3
0x1800418b9  call    cs:__imp_GetCurrentThreadId
0x1800418bf  cmp     [r14+0F0h], eax
0x1800418c6  jz      short loc_1800418CD
0x1800418c8  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800418cd  mov     rcx, [r14+98h]; this
0x1800418d4  lea     r8, [rbp+80h+var_E0]; struct PhoneLine **
0x1800418d8  xor     r9d, r9d; struct ISecurityToken *
0x1800418db  mov     [rbp+80h+var_E0], 0
0x1800418e3  mov     rdx, rbx; struct _GUID *
0x1800418e6  call    ?GetPhoneLine@PhoneLineStorage@@QEAAJAEBU_GUID@@PEAPEAVPhoneLine@@PEAUISecurityToken@@@Z; PhoneLineStorage::GetPhoneLine(_GUID const &,PhoneLine * *,ISecurityToken *)
0x1800418eb  mov     ebx, eax
0x1800418ed  test    eax, eax
0x1800418ef  jns     short loc_180041929
0x1800418f1  mov     edx, eax; int
0x1800418f3  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800418f8  mov     r9d, 793h
0x1800418fe  mov     r8, r13
0x180041901  mov     edx, 1
0x180041906  mov     ecx, ebx
0x180041908  call    Log_HREvent_7
0x18004190d  mov     rcx, [rbp+80h+var_E0]
0x180041911  test    rcx, rcx
0x180041914  jz      short loc_180041922
0x180041916  mov     rax, [rcx]
0x180041919  mov     rax, [rax+10h]
0x18004191d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041922  mov     eax, ebx
0x180041924  jmp     loc_180042404
0x180041929  mov     r9, [rdi]
0x18004192c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180041930  mov     rcx, [rdi+8]
0x180041934  mov     rax, 864B8A7DE6D1D609h
0x18004193e  sub     rcx, r9; this
0x180041941  mov     qword ptr [rbp+80h+var_A0], r12
0x180041945  imul    rcx
0x180041948  mov     rsi, r12
0x18004194b  mov     [rbp+80h+var_90], r12
0x18004194f  mov     r15, r12
0x180041952  mov     qword ptr [rbp+80h+var_A0+8], r12
0x180041956  lea     rbx, [rcx+rdx]
0x18004195a  sar     rbx, 0Bh
0x18004195e  mov     rax, rbx
0x180041961  shr     rax, 3Fh
0x180041965  add     rbx, rax
0x180041968  jz      short loc_1800419A9
0x18004196a  cmp     rbx, 8
0x18004196e  jbe     short loc_180041988
0x180041970  mov     rax, 864B8A7DE6D1Dh
0x18004197a  cmp     rbx, rax
0x18004197d  ja      loc_180041B29
0x180041983  mov     rdx, rbx
0x180041986  jmp     short loc_18004198D
0x180041988  mov     edx, 8
0x18004198d  lea     rcx, [rbp+80h+var_A0]
0x180041991  call    ?_SetCapacity@?$vector@UCallUpdate@@V?$allocator@UCallUpdate@@@utl@@@utl@@AEAA_N_K@Z; utl::vector<CallUpdate,utl::allocator<CallUpdate>>::_SetCapacity(unsigned __int64)
0x180041996  mov     rsi, qword ptr [rbp+80h+var_A0]
0x18004199a  test    al, al
0x18004199c  jz      loc_180041B29
0x1800419a2  mov     r9, [rdi]
0x1800419a5  mov     r15, qword ptr [rbp+80h+var_A0+8]
0x1800419a9  imul    rbx, 0F40h
0x1800419b0  mov     rdx, r9; Src
0x1800419b3  mov     rcx, r15; void *
0x1800419b6  mov     r8, rbx; Size
0x1800419b9  call    memcpy_0
0x1800419be  add     r15, rbx
0x1800419c1  mov     rax, 4FBCDA3AC10C9715h
0x1800419cb  mov     r8, r15
0x1800419ce  mov     [rbp+80h+var_B8], r15
0x1800419d2  sub     r8, rsi
0x1800419d5  mov     rdx, r15
0x1800419d8  sar     r8, 6
0x1800419dc  mov     rcx, rsi
0x1800419df  imul    r8, rax
0x1800419e3  call    ??$_SortImp@V?$_ArrayIt@UCallUpdate@@@utl@@_JP6AHAEBUCallUpdate@@0@Z@utl@@YAXV?$_ArrayIt@UCallUpdate@@@0@0_JP6AHAEBUCallUpdate@@2@Z@Z; utl::_SortImp<utl::_ArrayIt<CallUpdate>,__int64,int (*)(CallUpdate const &,CallUpdate const &)>(utl::_ArrayIt<CallUpdate>,utl::_ArrayIt<CallUpdate>,__int64,int (*)(CallUpdate const &,CallUpdate const &))
0x1800419e8  mov     r12, [rbp+80h+var_E0]
0x1800419ec  mov     rbx, rsi
0x1800419ef  movdqa  xmm6, cs:__xmm@ffffffffffffffffffffffffffffffff
0x1800419f7  mov     [rsp+180h+var_118], 0
0x1800419ff  mov     rcx, [r14+60h]; this
0x180041a03  cmp     rbx, r15
0x180041a06  jz      loc_180042341
0x180041a0c  mov     r13d, [r14+138h]
0x180041a13  lea     rdx, [rbp+80h+Buf1]
0x180041a17  xor     r9d, r9d
0x180041a1a  mov     dword ptr [rsp+180h+var_110], r13d
0x180041a1f  mov     r8, rbx
0x180041a22  mov     [rsp+180h+var_108], 0
0x180041a2a  mov     qword ptr [rbp+80h+Buf1], 0
0x180041a32  call    ?FindCall@PhoneCallStorage@@QEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneCallStorage::FindCall(uint const &,ISecurityToken *)
0x180041a37  mov     r15, qword ptr [rbp+80h+Buf1]
0x180041a3b  test    r15, r15
0x180041a3e  jz      loc_180041EDB
0x180041a44  cmp     dword ptr [r15+0C00h], 0
0x180041a4c  lea     r13, [rbx+8]
0x180041a50  jz      loc_180041B81
0x180041a56  test    byte ptr [r13+0], 40h
0x180041a5b  jz      loc_180041B81
0x180041a61  cmp     dword ptr [rbx+2FCh], 1Bh
0x180041a68  jnz     loc_180041B81
0x180041a6e  mov     eax, [r15+0BFCh]
0x180041a75  lea     rdx, [rbp+80h+var_68]
0x180041a79  mov     rcx, [r14+60h]
0x180041a7d  xor     r8d, r8d
0x180041a80  mov     [rsp+180h+var_120], eax
0x180041a84  movdqu  [rbp+80h+var_68], xmm6
0x180041a89  mov     [rbp+80h+var_58], 0FFFFFFFFFFFFFFFFh
0x180041a91  call    ?GetAllCalls@PhoneCallStorage@@QEAAJPEAV?$vector@V?$CComPtr@VCallInfo@@@ATL@@V?$allocator@V?$CComPtr@VCallInfo@@@ATL@@@utl@@@utl@@PEAUISecurityToken@@@Z; PhoneCallStorage::GetAllCalls(utl::vector<ATL::CComPtr<CallInfo>,utl::allocator<ATL::CComPtr<CallInfo>>> *,ISecurityToken *)
0x180041a96  mov     edi, eax
0x180041a98  test    eax, eax
0x180041a9a  js      loc_1800422C9
0x180041aa0  mov     rdi, qword ptr [rbp+80h+var_68]
0x180041aa4  mov     r12d, [rsp+180h+var_120]
0x180041aa9  cmp     rdi, qword ptr [rbp+80h+var_68+8]
0x180041aad  jz      loc_180041B74
0x180041ab3  mov     rcx, [rdi]
0x180041ab6  cmp     rcx, r15
0x180041ab9  jz      short loc_180041B23
0x180041abb  mov     eax, [r15+0C00h]
0x180041ac2  cmp     [rcx+0C00h], eax
0x180041ac8  jnz     short loc_180041B23
0x180041aca  mov     eax, cs:dword_1800B3200
0x180041ad0  mov     edx, [rcx+0BFCh]
0x180041ad6  cmp     eax, 4
0x180041ad9  jbe     short loc_180041B16
0x180041adb  lea     rax, aPhonecontrolle_8; "PhoneController: Call callId"
0x180041ae2  mov     dword ptr [rbp+80h+Buf1], edx
0x180041ae5  mov     qword ptr [rbp+80h+Buf2], rax
0x180041ae9  lea     rdx, word_1800A877A
0x180041af0  lea     rax, [rsp+180h+var_120]
0x180041af5  mov     [rsp+180h+var_120], r12d
0x180041afa  mov     [rsp+180h+var_150], rax
0x180041aff  lea     rax, [rbp+80h+Buf1]
0x180041b03  mov     [rsp+180h+var_158], rax
0x180041b08  lea     rax, [rbp+80h+Buf2]
0x180041b0c  mov     [rsp+180h+var_160], rax
0x180041b11  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041b16  mov     rax, [rdi]
0x180041b19  mov     dword ptr [rax+1490h], 1
0x180041b23  add     rdi, 8
0x180041b27  jmp     short loc_180041AA9
0x180041b29  mov     ebx, 8007000Eh
0x180041b2e  mov     edx, ebx; int
0x180041b30  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180041b35  mov     r9d, 79Bh
0x180041b3b  mov     r8, r13
0x180041b3e  xor     edx, edx
0x180041b40  mov     ecx, ebx
0x180041b42  call    Log_HREvent_7
0x180041b47  cmp     rsi, r12
0x180041b4a  jz      short loc_180041B5B
0x180041b4c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x180041b53  mov     rcx, rsi; Block
0x180041b56  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180041b5b  mov     rcx, [rbp+80h+var_E0]
0x180041b5f  test    rcx, rcx
0x180041b62  jz      loc_180041922
0x180041b68  mov     rdx, [rcx]
0x180041b6b  mov     rax, [rdx+10h]
0x180041b6f  jmp     loc_18004191D
0x180041b74  lea     rcx, [rbp+80h+var_68]
0x180041b78  call    ??1?$vector@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@V?$allocator@V?$CComPtr@UIPhoneServiceStateChangeSink@@@ATL@@@utl@@@utl@@QEAA@XZ; utl::vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>::~vector<ATL::CComPtr<IPhoneServiceStateChangeSink>,utl::allocator<ATL::CComPtr<IPhoneServiceStateChangeSink>>>(void)
0x180041b7d  mov     r12, [rbp+80h+var_E0]
0x180041b81  test    byte ptr [r13+0], 20h
0x180041b86  jz      short loc_180041BB4
0x180041b88  mov     eax, [rbx+2F8h]
0x180041b8e  cmp     eax, 4
0x180041b91  jnz     short loc_180041B9D
0x180041b93  and     dword ptr [r15+1AA8h], 0FFFFFFF7h
0x180041b9b  jmp     short loc_180041BB4
0x180041b9d  cmp     eax, 6
0x180041ba0  ja      short loc_180041BB4
0x180041ba2  mov     ecx, 49h ; 'I'
0x180041ba7  bt      ecx, eax
0x180041baa  jnb     short loc_180041BB4
0x180041bac  and     dword ptr [r15+1AA8h], 0FFFFFFEFh
0x180041bb4  lea     rdx, [rbp+80h+Buf1]; struct PhoneLine **
0x180041bb8  mov     qword ptr [rbp+80h+Buf1], 0
0x180041bc0  mov     rcx, r15; this
0x180041bc3  call    ?GetPhoneLine@CallInfo@@QEAAXPEAPEAVPhoneLine@@@Z; CallInfo::GetPhoneLine(PhoneLine * *)
0x180041bc8  mov     rdi, qword ptr [rbp+80h+Buf1]
0x180041bcc  lea     rdx, [rbp+80h+Buf2]; Buf2
0x180041bd0  movups  xmm1, xmmword ptr [r12+58h]
0x180041bd6  mov     r8d, 10h; Size
0x180041bdc  lea     rcx, [rbp+80h+Buf1]; Buf1
0x180041be0  movups  xmm0, xmmword ptr [rdi+58h]
0x180041be4  movdqu  [rbp+80h+Buf1], xmm1
0x180041be9  movdqu  [rbp+80h+Buf2], xmm0
0x180041bee  call    memcmp_0
0x180041bf3  test    eax, eax
0x180041bf5  jnz     loc_180041EC7
0x180041bfb  cmp     dword ptr [rsp+180h+var_110], eax
0x180041bff  jnz     short loc_180041C47
0x180041c01  cmp     [r15+0BF0h], eax
0x180041c08  jnz     short loc_180041C47
0x180041c0a  lea     r9, [rsp+180h+var_108]; int *
0x180041c0f  mov     r8, rbx; struct CallUpdate *
0x180041c12  mov     rdx, r12; struct PhoneLine *
0x180041c15  mov     rcx, r14; this
0x180041c18  call    ?_ProcessIncomingPhoneCallFilters@PhoneController@@IEAAJPEAVPhoneLine@@AEBUCallUpdate@@PEAH@Z; PhoneController::_ProcessIncomingPhoneCallFilters(PhoneLine *,CallUpdate const &,int *)
0x180041c1d  test    eax, eax
0x180041c1f  jns     short loc_180041C37
0x180041c21  mov     r9d, 7E9h
0x180041c27  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180041c2e  xor     edx, edx
0x180041c30  mov     ecx, eax
0x180041c32  call    Log_HREvent_7
0x180041c37  cmp     [rsp+180h+var_108], 0
0x180041c3c  jz      short loc_180041C47
0x180041c3e  bts     dword ptr [r15+0C08h], 0Ah
0x180041c47  mov     r8, rbx; struct CallUpdate *
0x180041c4a  mov     rdx, r12; struct PhoneLine *
0x180041c4d  mov     rcx, r14; this
0x180041c50  call    ?_EnforceMultiCallPolicyForExistingCall@PhoneController@@IEAAJPEAVPhoneLine@@AEBUCallUpdate@@@Z; PhoneController::_EnforceMultiCallPolicyForExistingCall(PhoneLine *,CallUpdate const &)
0x180041c55  test    eax, eax
0x180041c57  jns     short loc_180041C6F
0x180041c59  mov     r9d, 7F1h
0x180041c5f  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180041c66  xor     edx, edx
0x180041c68  mov     ecx, eax
0x180041c6a  call    Log_HREvent_7
0x180041c6f  test    byte ptr [r13+0], 20h
0x180041c74  jz      loc_180041DC5
0x180041c7a  mov     eax, cs:dword_1800B3200
0x180041c80  cmp     eax, 4
0x180041c83  jbe     loc_180041D56
0x180041c89  mov     rcx, r12; this
0x180041c8c  call    ?IsMuted@PhoneLine@@QEBAHXZ; PhoneLine::IsMuted(void)
0x180041c91  mov     edx, [rbx+2F8h]
0x180041c97  mov     [rbp+80h+var_D8], eax
0x180041c9a  mov     eax, [rbx+2FCh]
0x180041ca0  mov     [rbp+80h+var_D4], eax
0x180041ca3  call    ?ConvertCallStateToString@PhoneController@@AEAAPEBGW4PH_CALLSTATE@@@Z; PhoneController::ConvertCallStateToString(PH_CALLSTATE)
0x180041ca8  mov     edx, [r15+0BE0h]
0x180041caf  mov     qword ptr [rbp+80h+Buf2], rax
0x180041cb3  call    ?ConvertCallStateToString@PhoneController@@AEAAPEBGW4PH_CALLSTATE@@@Z; PhoneController::ConvertCallStateToString(PH_CALLSTATE)
0x180041cb8  mov     [rsp+180h+var_110], rax
0x180041cbd  lea     rdx, [rbp+80h+Buf1]; struct _GUID
0x180041cc1  mov     eax, [r15+0BFCh]
0x180041cc8  mov     [rbp+80h+var_D0], eax
0x180041ccb  movups  xmm0, xmmword ptr [r12+70h]
0x180041cd1  movdqu  [rbp+80h+Buf1], xmm0
0x180041cd6  call    ?ConvertLineTypeToString@PhoneController@@AEAAPEBGU_GUID@@@Z; PhoneController::ConvertLineTypeToString(_GUID)
0x180041cdb  movups  xmm0, xmmword ptr [r12+58h]
0x180041ce1  mov     qword ptr [rbp+80h+Buf1], rax
0x180041ce5  lea     rdx, dword_1800A86EC
0x180041cec  lea     rax, [rbp+80h+var_B0]
0x180041cf0  mov     qword ptr [rsp+180h+var_120], rax
0x180041cf5  lea     rax, aCallStateChang; "Call state changed"
0x180041cfc  mov     qword ptr [rsp+180h+var_108], rax
0x180041d01  lea     rax, [rbp+80h+var_D8]
0x180041d05  mov     [rsp+180h+var_128], rax
0x180041d0a  lea     rax, [rbp+80h+var_D4]
0x180041d0e  mov     [rsp+180h+var_130], rax
0x180041d13  lea     rax, [rbp+80h+Buf2]
0x180041d17  mov     [rsp+180h+var_138], rax
0x180041d1c  lea     rax, [rsp+180h+var_110]
0x180041d21  mov     [rsp+180h+var_140], rax
0x180041d26  lea     rax, [rbp+80h+var_D0]
0x180041d2a  mov     [rsp+180h+var_148], rax
0x180041d2f  lea     rax, [rbp+80h+Buf1]
0x180041d33  mov     [rsp+180h+var_150], rax
0x180041d38  lea     rax, [rsp+180h+var_120]
0x180041d3d  mov     [rsp+180h+var_158], rax
0x180041d42  lea     rax, [rsp+180h+var_108]
0x180041d47  mov     [rsp+180h+var_160], rax
0x180041d4c  movdqu  [rbp+80h+var_B0], xmm0
0x180041d51  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@5566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180041d56  movups  xmm0, xmmword ptr [r12+70h]
0x180041d5c  mov     r8d, 10h; Size
0x180041d62  lea     rdx, BluetoothHandsFreeLineType; Buf2
0x180041d69  lea     rcx, [rbp+80h+Buf2]; Buf1
0x180041d6d  movdqu  [rbp+80h+Buf2], xmm0
0x180041d72  call    memcmp_0
  ... truncated ...
```
