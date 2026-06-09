# CAudStreamSink::FinishOnClockSetRate(__int64,float)

- ea: `0x180174680`
- end: `0x18017528a`
- name: `?FinishOnClockSetRate@CAudStreamSink@@UEAAJ_JM@Z`
- size: `3082`
- prototype: `__int64 __fastcall(CAudStreamSink *__hidden this, __int64, float)`
- caller_count: `0`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18001616c`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180045dbc`
- `0x18004cbfc`
- `0x18004d118`
- `0x18004e910`
- `0x18004f098`
- `0x18004fb98`
- `0x180050d6c`
- `0x18006b388`
- `0x1800858b0`
- `0x1800859b0`
- `0x1800b4238`
- `0x1800b4f18`
- `0x1800b5c48`
- `0x1800ec0e0`
- `0x180174680`
- `0x1801f4bec`
- `0x180258480`
- `0x18031cedc`
- `0x18031e048`
- `0x18031ec0c`
- `0x180324758`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180174a23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180174a37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180175188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017519b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180174a23`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180174a37`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180175188`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18017519b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017498d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180174a88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180174aa9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18017498d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180174a88`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180174aa9`

## string_xrefs

- `0x180174736`: `CAudStreamSink::FinishOnClockSetRate`
- `0x1801749e3`: `CAudStreamSink::FinishOnClockSetRate`
- `0x180174a43`: `CAudStreamSink::FinishOnClockSetRate`
- `0x180174cba`: `CAudStreamSink::FinishOnClockSetRate`
- `0x180174d2c`: `CAudStreamSink::FinishOnClockSetRate`
- `0x180174ecb`: `CAudStreamSink::FinishOnClockSetRate`
- `0x180174f40`: `CAudStreamSink::FinishOnClockSetRate`
- `0x180174fe6`: `CAudStreamSink::FinishOnClockSetRate`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::FinishOnClockSetRate(CAudStreamSink *this, int a2, float a3)
{
  float v3; // xmm9_4
  int v6; // edx
  int v7; // ecx
  float v8; // xmm8_4
  int v9; // r15d
  CallStackTracing *v10; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v12; // ebx
  __int128 *v13; // rax
  __int128 v14; // xmm0
  unsigned __int32 v15; // xmm1_4
  int v16; // eax
  int PositionWrapper; // ebx
  struct CallStackContext *v18; // rax
  __int64 v19; // rdx
  struct CallStackContext *v20; // rax
  CallStackTracing *v21; // rcx
  struct CallStackContext *v22; // rax
  unsigned __int64 *v23; // r8
  CallStackTracing *v24; // rcx
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  unsigned __int64 v27; // r12
  unsigned __int64 v28; // r14
  __int64 v29; // rdx
  __int64 v30; // r8
  unsigned __int64 v31; // r13
  __int64 v32; // rax
  unsigned __int8 v33; // al
  __int64 v34; // r8
  CallStackTracing *v35; // rcx
  struct CallStackContext *v36; // rax
  CallStackTracing *v37; // rcx
  struct CallStackContext *v38; // rax
  unsigned __int8 v39; // al
  __int64 v40; // r9
  struct _RTL_CRITICAL_SECTION *v41; // rcx
  CallStackTracing *v42; // rcx
  struct CallStackContext *v43; // rax
  CallStackTracing *v44; // rcx
  struct CallStackContext *v45; // rax
  CallStackTracing *v46; // rcx
  struct CallStackContext *v47; // rax
  float v48; // xmm0_4
  __int64 v49; // rax
  __int64 v50; // rcx
  struct CallStackContext *v51; // rax
  _BYTE v53[8]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v54; // [rsp+60h] [rbp-51h] BYREF
  unsigned __int64 v55; // [rsp+68h] [rbp-49h] BYREF
  unsigned __int64 v56[2]; // [rsp+70h] [rbp-41h] BYREF

  v3 = *((float *)this + 1828);
  if ( v3 <= 0.0 )
    v3 = FLOAT_8_0;
  CAudStreamSink::ResetDejitterer(this);
  v8 = *((float *)this + 1829);
  if ( v8 <= 0.0 )
    v8 = FLOAT_1_0;
  v9 = 0;
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pit_EventWriteTransfer(v7, v6, (_DWORD)this, a2, a3 == 0.0);
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v53, "CAudStreamSink::FinishOnClockSetRate", 4944);
  v10 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 825) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v12 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 825) + 296LL))(*((_QWORD *)this + 825));
    v13 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, unsigned __int64 *))(**((_QWORD **)this + 825) + 280LL))(
                        *((_QWORD *)this + 825),
                        v56);
    v10 = CallStackTracing::s_wpInstance;
    v14 = *v13;
    *((_DWORD *)ThreadRelativeContext + 504) = v12;
    *((_OWORD *)ThreadRelativeContext + 125) = v14;
  }
  if ( (unsigned __int8)byte_1803CECE9 >= 8u )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 330, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this, a3);
    v10 = CallStackTracing::s_wpInstance;
  }
  v15 = _mm_load_si128((const __m128i *)&_xmm).m128i_u32[0];
  if ( a3 != 0.0 && (COERCE_FLOAT(LODWORD(a3) & v15) < 0.125 || v3 < COERCE_FLOAT(LODWORD(a3) & v15)) )
  {
    PositionWrapper = -2147024809;
    if ( !v10 )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v51 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v51 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v51, "CAudStreamSink::FinishOnClockSetRate", 4950, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_158;
    v19 = 331;
    goto LABEL_157;
  }
  if ( a3 == *((float *)this + 1335) || *((_DWORD *)this + 64) || *((_DWORD *)this + 1354) )
  {
    PositionWrapper = 0;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 332, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    goto LABEL_138;
  }
  if ( a3 == 0.0 )
  {
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 337, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    *((_DWORD *)this + 1338) = 1;
    goto LABEL_56;
  }
  if ( *((_QWORD *)this + 100) )
  {
    v16 = *((_DWORD *)this + 1294);
    if ( !v16 )
      goto LABEL_41;
    if ( v8 == 1.0 )
    {
      if ( 1.0 != a3 )
      {
        PositionWrapper = -2147024809;
        if ( !v10 )
        {
          CallStackTracing::InitInstance();
          v10 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v10 + 8) )
        {
          v18 = CallStackTracing::GetThreadRelativeContext(v10);
          if ( *((_DWORD *)v18 + 499) != -2147024809 )
            CallStackContext::TraceFailure(v18, "CAudStreamSink::FinishOnClockSetRate", 4974, -2147024809);
        }
        if ( !g_wppLevels )
          goto LABEL_158;
        v19 = 333;
        goto LABEL_157;
      }
LABEL_41:
      if ( *((_QWORD *)this + 660) && !v16 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 5288));
        PositionWrapper = CAudTransform::SetSpeedup(*((CAudTransform **)this + 660), COERCE_FLOAT(LODWORD(a3) & _xmm));
        if ( PositionWrapper < 0 )
        {
          v21 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            CallStackTracing::InitInstance();
            v21 = CallStackTracing::s_wpInstance;
          }
          if ( *((_BYTE *)v21 + 8) )
          {
            v22 = CallStackTracing::GetThreadRelativeContext(v21);
            if ( *((_DWORD *)v22 + 499) != PositionWrapper )
              CallStackContext::TraceFailure(v22, "CAudStreamSink::FinishOnClockSetRate", 4989, PositionWrapper);
          }
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              335,
              &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
              this,
              PositionWrapper);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 5288));
          goto LABEL_158;
        }
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 5288));
      }
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 336, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
      *((_DWORD *)this + 1338) = 0;
      goto LABEL_56;
    }
    if ( COERCE_FLOAT(LODWORD(a3) & v15) <= v8 )
      goto LABEL_41;
    PositionWrapper = -2147024809;
    if ( !v10 )
    {
      CallStackTracing::InitInstance();
      v10 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v10 + 8) )
    {
      v20 = CallStackTracing::GetThreadRelativeContext(v10);
      if ( *((_DWORD *)v20 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v20, "CAudStreamSink::FinishOnClockSetRate", 4978, -2147024809);
    }
    if ( !g_wppLevels )
      goto LABEL_158;
    v19 = 334;
LABEL_157:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      -2147024809);
    goto LABEL_158;
  }
LABEL_56:
  CAudStreamSink::LockAudioSamplePump((CAudStreamSink *)((char *)this + 656));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 5192));
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 392));
  *((_DWORD *)this + 175) = 0;
  v55 = 0;
  v56[0] = 0;
  PositionWrapper = CAudStreamSink::GetPositionWrapper(this, &v55, v23, v56, 0, 1);
  if ( PositionWrapper < 0 )
  {
    v24 = CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      CallStackTracing::InitInstance();
      v24 = CallStackTracing::s_wpInstance;
    }
    if ( *((_BYTE *)v24 + 8) )
    {
      v25 = CallStackTracing::GetThreadRelativeContext(v24);
      if ( *((_DWORD *)v25 + 499) != PositionWrapper )
        CallStackContext::TraceFailure(v25, "CAudStreamSink::FinishOnClockSetRate", 5021, PositionWrapper);
    }
    if ( !g_wppLevels )
      goto LABEL_149;
    v26 = 338;
LABEL_93:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
      this,
      PositionWrapper);
LABEL_149:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + *(int *)(*((_QWORD *)this + 47) + 4LL) + 392));
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 5192));
    CAudStreamSink::UnlockAudioSamplePump((CAudStreamSink *)((char *)this + 656));
    goto LABEL_158;
  }
  v54 = 0;
  v27 = 0;
  v28 = 0;
  CAudStreamSink::InternalGetTime(this, &v54, 0, 0, 0);
  v31 = v55;
  if ( (a3 == 0.0 || *((float *)this + 1335) == 0.0 || !*(_DWORD *)(*((_QWORD *)this + 648) + 1504LL))
    && (*((float *)this + 1335) != 0.0 || *((float *)this + 1336) == a3) )
  {
    v32 = *((_QWORD *)this + 648);
    if ( *(_DWORD *)(v32 + 1504) || *(_DWORD *)(v32 + 1336) )
    {
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 350, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
    }
    else
    {
      v33 = (unsigned __int8)byte_1803CECE9;
      if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 346, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
        v33 = (unsigned __int8)byte_1803CECE9;
      }
      v28 = v31;
      if ( v33 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 347, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
      v34 = *((_QWORD *)this + 100);
      LOBYTE(v9) = a3 < 0.0;
      if ( v34 )
        CDevClock::Reset(*((LPCRITICAL_SECTION *)this + 666), v54, *(_DWORD *)(v34 + 8), v9);
      PositionWrapper = CDevClock::AddSampleMapping(*((LPCRITICAL_SECTION *)this + 666), 1, v31, v54, 0, 0, 0);
      if ( PositionWrapper < 0 )
      {
        v35 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v35 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v35 + 8) )
        {
          v36 = CallStackTracing::GetThreadRelativeContext(v35);
          if ( *((_DWORD *)v36 + 499) != PositionWrapper )
            CallStackContext::TraceFailure(v36, "CAudStreamSink::FinishOnClockSetRate", 5105, PositionWrapper);
        }
        if ( !g_wppLevels )
          goto LABEL_149;
        v26 = 348;
        goto LABEL_93;
      }
      v27 = v56[0];
      PositionWrapper = CAudStreamSink::SetInitialPosMatchRatio(this, v56[0], v31, a3);
      if ( PositionWrapper < 0 )
      {
        v37 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v37 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v37 + 8) )
        {
          v38 = CallStackTracing::GetThreadRelativeContext(v37);
          if ( *((_DWORD *)v38 + 499) != PositionWrapper )
            CallStackContext::TraceFailure(v38, "CAudStreamSink::FinishOnClockSetRate", 5113, PositionWrapper);
        }
        if ( !g_wppLevels )
          goto LABEL_149;
        v26 = 349;
        goto LABEL_93;
      }
      CDevClock::CleanupBefore(*((LPCRITICAL_SECTION *)this + 666), v31, 0, v9);
    }
    *((_DWORD *)this + 1336) = *((_DWORD *)this + 1335);
  }
  else
  {
    v39 = (unsigned __int8)byte_1803CECE9;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 339, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
      v39 = (unsigned __int8)byte_1803CECE9;
    }
    if ( *((_DWORD *)this + 1820) )
    {
      if ( v39 >= 0x10u )
      {
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 340, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
        v39 = (unsigned __int8)byte_1803CECE9;
      }
      v27 = *((_QWORD *)this + 656);
      v28 = *((_QWORD *)this + 655);
      if ( *((__int64 *)this + 657) > 0 && v39 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 341, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
      v40 = v54;
      v41 = (struct _RTL_CRITICAL_SECTION *)*((_QWORD *)this + 666);
      *((_QWORD *)this + 657) = 0;
      PositionWrapper = CDevClock::AddSampleMapping(v41, 1, v28, v40, 0, 0, 1);
      if ( PositionWrapper < 0 )
      {
        v42 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v42 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v42 + 8) )
        {
          v43 = CallStackTracing::GetThreadRelativeContext(v42);
          if ( *((_DWORD *)v43 + 499) != PositionWrapper )
            CallStackContext::TraceFailure(v43, "CAudStreamSink::FinishOnClockSetRate", 5062, PositionWrapper);
        }
        if ( !g_wppLevels )
          goto LABEL_149;
        v26 = 342;
        goto LABEL_93;
      }
      PositionWrapper = CAudStreamSink::SetInitialPosMatchRatio(this, v27, v28, a3);
      if ( PositionWrapper < 0 )
      {
        v44 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v44 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v44 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext(v44);
          if ( *((_DWORD *)v45 + 499) != PositionWrapper )
            CallStackContext::TraceFailure(v45, "CAudStreamSink::FinishOnClockSetRate", 5066, PositionWrapper);
        }
        if ( !g_wppLevels )
          goto LABEL_149;
        v26 = 343;
        goto LABEL_93;
      }
    }
    else
    {
      if ( v39 >= 0x10u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 344, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
      v55 = 0x7FFFFFFFFFFFFFFFLL;
      v56[0] = 0x7FFFFFFFFFFFFFFFLL;
      PositionWrapper = CAudStreamSink::GetExactTime(this, (__int64 *)&v55, (__int64 *)v56);
      if ( PositionWrapper < 0 )
      {
        v46 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v46 = CallStackTracing::s_wpInstance;
        }
        if ( *((_BYTE *)v46 + 8) )
        {
          v47 = CallStackTracing::GetThreadRelativeContext(v46);
          if ( *((_DWORD *)v47 + 499) != PositionWrapper )
            CallStackContext::TraceFailure(v47, "CAudStreamSink::FinishOnClockSetRate", 5075, PositionWrapper);
        }
        if ( !g_wppLevels )
          goto LABEL_149;
        v26 = 345;
        goto LABEL_93;
      }
      CAudStreamSink::SetStreamInvalidationEventInfo(this, 7);
      *((_DWORD *)this + 175) = 1;
    }
  }
  v9 = 1;
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_qgiiii(*((_QWORD *)WPP_GLOBAL_Control + 7), v29, v30, this, a3, v28, v27, *((_QWORD *)this + 655), v31);
LABEL_138:
  if ( *((float *)this + 1335) != 0.0 )
    goto LABEL_142;
  if ( a3 != 0.0 )
  {
    *((_DWORD *)this + 1337) = 1;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 352, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
LABEL_142:
    if ( a3 != 0.0 )
      goto LABEL_146;
  }
  v48 = *((float *)this + 1335);
  if ( v48 != 0.0 )
  {
    *((float *)this + 1336) = v48;
    *((_DWORD *)this + 1337) = 0;
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), 353, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, this);
  }
LABEL_146:
  v49 = *((_QWORD *)this + 47);
  *((float *)this + 1335) = a3;
  v50 = *(_QWORD *)((char *)this + *(int *)(v49 + 4) + 384);
  if ( v50 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 32LL))(v50);
  if ( v9 )
    goto LABEL_149;
LABEL_158:
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0pq_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_FinishOnClockSetRate_Exit,
      this,
      (unsigned int)PositionWrapper);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v53);
  return (unsigned int)PositionWrapper;
}

```

## disassembly

```asm
0x180174680  mov     rax, rsp
0x180174683  mov     [rax+20h], rbx
0x180174687  push    rbp
0x180174688  push    rsi
0x180174689  push    rdi
0x18017468a  push    r12
0x18017468c  push    r13
0x18017468e  push    r14
0x180174690  push    r15
0x180174692  lea     rbp, [rax-5Fh]
0x180174696  sub     rsp, 0D0h
0x18017469d  movaps  xmmword ptr [rax-48h], xmm6
0x1801746a1  movaps  xmmword ptr [rax-58h], xmm7
0x1801746a5  movaps  xmmword ptr [rax-68h], xmm8
0x1801746aa  movaps  xmmword ptr [rax-78h], xmm9
0x1801746af  movaps  xmmword ptr [rax-88h], xmm10
0x1801746b7  mov     rax, cs:__security_cookie
0x1801746be  xor     rax, rsp
0x1801746c1  mov     [rbp+57h+var_88], rax
0x1801746c5  movss   xmm9, dword ptr [rcx+1C90h]
0x1801746ce  xorps   xmm7, xmm7
0x1801746d1  comiss  xmm9, xmm7
0x1801746d5  mov     rbx, rdx
0x1801746d8  mov     rsi, rcx
0x1801746db  movaps  xmm6, xmm2
0x1801746de  ja      short loc_1801746E9
0x1801746e0  movss   xmm9, cs:__real@41000000
0x1801746e9  call    ?ResetDejitterer@CAudStreamSink@@IEAAXXZ; CAudStreamSink::ResetDejitterer(void)
0x1801746ee  movss   xmm8, dword ptr [rsi+1C94h]
0x1801746f7  comiss  xmm8, xmm7
0x1801746fb  movss   xmm10, cs:__real@3f800000
0x180174704  ja      short loc_18017470A
0x180174706  movaps  xmm8, xmm10
0x18017470a  xor     r15d, r15d
0x18017470d  lea     r13d, [r15+1]
0x180174711  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, r13b
0x180174718  jz      short loc_180174736
0x18017471a  ucomiss xmm6, xmm7
0x18017471d  jp      short loc_180174724
0x18017471f  mov     eax, r13d
0x180174722  jz      short loc_180174727
0x180174724  mov     eax, r15d
0x180174727  mov     r9, rbx
0x18017472a  mov     dword ptr [rsp+100h+var_E0], eax
0x18017472e  mov     r8, rsi
0x180174731  call    McTemplateU0pit_EventWriteTransfer
0x180174736  lea     r14, aCaudstreamsink_15; "CAudStreamSink::FinishOnClockSetRate"
0x18017473d  mov     r8d, 1350h; int
0x180174743  mov     rdx, r14; char *
0x180174746  lea     rcx, [rbp+57h+var_B0]; this
0x18017474a  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18017474f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180174756  cmp     [rcx+8], r15b
0x18017475a  jz      short loc_1801747B9
0x18017475c  cmp     [rsi+19C8h], r15
0x180174763  jz      short loc_1801747B9
0x180174765  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18017476a  mov     rcx, [rsi+19C8h]
0x180174771  mov     rdi, rax
0x180174774  mov     rdx, [rcx]
0x180174777  mov     rax, [rdx+128h]
0x18017477e  call    cs:__guard_dispatch_icall_fptr
0x180174784  mov     rcx, [rsi+19C8h]
0x18017478b  mov     ebx, eax
0x18017478d  mov     rdx, [rcx]
0x180174790  mov     rax, [rdx+118h]
0x180174797  lea     rdx, [rbp+57h+var_98]
0x18017479b  call    cs:__guard_dispatch_icall_fptr
0x1801747a1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801747a8  movups  xmm0, xmmword ptr [rax]
0x1801747ab  mov     [rdi+7E0h], ebx
0x1801747b1  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1801747b9  cmp     cs:byte_1803CECE9, 8
0x1801747c0  lea     r12, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x1801747c7  jb      short loc_1801747F8
0x1801747c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1801747d0  xorps   xmm0, xmm0
0x1801747d3  cvtss2sd xmm0, xmm6
0x1801747d7  mov     edx, 14Ah
0x1801747dc  mov     r9, rsi
0x1801747df  mov     r8, r12
0x1801747e2  mov     rcx, [rcx+38h]
0x1801747e6  movsd   [rsp+100h+var_E0], xmm0
0x1801747ec  call    WPP_SF_qq
0x1801747f1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801747f8  ucomiss xmm6, xmm7
0x1801747fb  movdqa  xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff
0x180174803  jp      short loc_180174807
0x180174805  jz      short loc_180174824
0x180174807  movaps  xmm0, xmm6
0x18017480a  andps   xmm0, xmm1
0x18017480d  comiss  xmm0, cs:__real@3e000000
0x180174814  jb      loc_1801751B5
0x18017481a  comiss  xmm9, xmm0
0x18017481e  jb      loc_1801751B5
0x180174824  ucomiss xmm6, dword ptr [rsi+14DCh]
0x18017482b  jp      short loc_180174833
0x18017482d  jz      loc_180175087
0x180174833  cmp     [rsi+100h], r15d
0x18017483a  jnz     loc_180175087
0x180174840  cmp     [rsi+1528h], r15d
0x180174847  jnz     loc_180175087
0x18017484d  ucomiss xmm6, xmm7
0x180174850  mov     dil, 10h
0x180174853  jp      short loc_180174887
0x180174855  jnz     short loc_180174887
0x180174857  cmp     cs:byte_1803CECE9, dil
0x18017485e  jb      short loc_18017487B
0x180174860  mov     rcx, cs:WPP_GLOBAL_Control
0x180174867  mov     edx, 151h
0x18017486c  mov     r9, rsi
0x18017486f  mov     r8, r12
0x180174872  mov     rcx, [rcx+38h]
0x180174876  call    WPP_SF_q
0x18017487b  mov     [rsi+14E8h], r13d
0x180174882  jmp     loc_180174A75
0x180174887  cmp     [rsi+320h], r15
0x18017488e  jz      loc_180174A75
0x180174894  mov     eax, [rsi+1438h]
0x18017489a  test    eax, eax
0x18017489c  jz      loc_18017496E
0x1801748a2  ucomiss xmm8, xmm10
0x1801748a6  jp      short loc_18017490C
0x1801748a8  jnz     short loc_18017490C
0x1801748aa  ucomiss xmm10, xmm6
0x1801748ae  jp      short loc_1801748B6
0x1801748b0  jz      loc_18017496E
0x1801748b6  mov     edi, 80070057h
0x1801748bb  mov     ebx, edi
0x1801748bd  test    rcx, rcx
0x1801748c0  jnz     short loc_1801748CE
0x1801748c2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1801748c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801748ce  cmp     [rcx+8], r15b
0x1801748d2  jz      short loc_1801748F5
0x1801748d4  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801748d9  cmp     [rax+7CCh], edi
0x1801748df  jz      short loc_1801748F5
0x1801748e1  mov     r9d, edi; int
0x1801748e4  mov     r8d, 136Eh; int
0x1801748ea  mov     rdx, r14; char *
0x1801748ed  mov     rcx, rax; this
0x1801748f0  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801748f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1801748fc  jb      loc_18017521C
0x180174902  mov     edx, 14Dh
0x180174907  jmp     loc_180175202
0x18017490c  movaps  xmm0, xmm6
0x18017490f  andps   xmm0, xmm1
0x180174912  comiss  xmm0, xmm8
0x180174916  jbe     short loc_18017496E
0x180174918  mov     edi, 80070057h
0x18017491d  mov     ebx, edi
0x18017491f  test    rcx, rcx
0x180174922  jnz     short loc_180174930
0x180174924  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180174929  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180174930  cmp     [rcx+8], r15b
0x180174934  jz      short loc_180174957
0x180174936  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18017493b  cmp     [rax+7CCh], edi
0x180174941  jz      short loc_180174957
0x180174943  mov     r9d, edi; int
0x180174946  mov     r8d, 1372h; int
0x18017494c  mov     rdx, r14; char *
0x18017494f  mov     rcx, rax; this
0x180174952  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180174957  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x18017495e  jb      loc_18017521C
0x180174964  mov     edx, 14Eh
0x180174969  jmp     loc_180175202
0x18017496e  cmp     [rsi+14A0h], r15
0x180174975  jz      loc_180174A4A
0x18017497b  test    eax, eax
0x18017497d  jnz     loc_180174A4A
0x180174983  lea     r14, [rsi+14A8h]
0x18017498a  mov     rcx, r14; lpCriticalSection
0x18017498d  call    cs:__imp_EnterCriticalSection
0x180174994  nop     dword ptr [rax+rax+00h]
0x180174999  mov     rcx, [rsi+14A0h]; this
0x1801749a0  movaps  xmm1, xmm6
0x1801749a3  andps   xmm1, cs:__xmm@7fffffff7fffffff7fffffff7fffffff; float
0x1801749aa  call    ?SetSpeedup@CAudTransform@@QEAAJM@Z; CAudTransform::SetSpeedup(float)
0x1801749af  mov     ebx, eax
0x1801749b1  test    eax, eax
0x1801749b3  jns     short loc_180174A34
0x1801749b5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1801749bc  test    rcx, rcx
0x1801749bf  jnz     short loc_1801749CD
0x1801749c1  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x1801749c6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1801749cd  cmp     [rcx+8], r15b
0x1801749d1  jz      short loc_1801749F8
0x1801749d3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1801749d8  cmp     [rax+7CCh], ebx
0x1801749de  jz      short loc_1801749F8
0x1801749e0  mov     r9d, ebx; int
0x1801749e3  lea     rdx, aCaudstreamsink_15; "CAudStreamSink::FinishOnClockSetRate"
0x1801749ea  mov     r8d, 137Dh; int
0x1801749f0  mov     rcx, rax; this
0x1801749f3  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1801749f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x1801749ff  jb      short loc_180174A20
0x180174a01  mov     rcx, cs:WPP_GLOBAL_Control
0x180174a08  mov     edx, 14Fh
0x180174a0d  mov     r9, rsi
0x180174a10  mov     dword ptr [rsp+100h+var_E0], ebx
0x180174a14  mov     r8, r12
0x180174a17  mov     rcx, [rcx+10h]
0x180174a1b  call    WPP_SF_qD
0x180174a20  mov     rcx, r14; lpCriticalSection
0x180174a23  call    cs:__imp_LeaveCriticalSection
0x180174a2a  nop     dword ptr [rax+rax+00h]
0x180174a2f  jmp     loc_18017521C
0x180174a34  mov     rcx, r14; lpCriticalSection
0x180174a37  call    cs:__imp_LeaveCriticalSection
0x180174a3e  nop     dword ptr [rax+rax+00h]
0x180174a43  lea     r14, aCaudstreamsink_15; "CAudStreamSink::FinishOnClockSetRate"
0x180174a4a  cmp     cs:byte_1803CECE9, dil
0x180174a51  jb      short loc_180174A6E
0x180174a53  mov     rcx, cs:WPP_GLOBAL_Control
0x180174a5a  mov     edx, 150h
0x180174a5f  mov     r9, rsi
0x180174a62  mov     r8, r12
0x180174a65  mov     rcx, [rcx+38h]
0x180174a69  call    WPP_SF_q
0x180174a6e  mov     [rsi+14E8h], r15d
0x180174a75  lea     rcx, [rsi+290h]; this
0x180174a7c  call    ?LockAudioSamplePump@CAudStreamSink@@UEAAJXZ; CAudStreamSink::LockAudioSamplePump(void)
0x180174a81  lea     rcx, [rsi+1448h]; lpCriticalSection
0x180174a88  call    cs:__imp_EnterCriticalSection
0x180174a8f  nop     dword ptr [rax+rax+00h]
0x180174a94  mov     rax, [rsi+178h]
0x180174a9b  movsxd  rcx, dword ptr [rax+4]
0x180174a9f  add     rcx, 188h
0x180174aa6  add     rcx, rsi; lpCriticalSection
0x180174aa9  call    cs:__imp_EnterCriticalSection
0x180174ab0  nop     dword ptr [rax+rax+00h]
0x180174ab5  lea     r9, [rbp+57h+var_98]; unsigned __int64 *
0x180174ab9  mov     [rsp+100h+var_D8], r13d; int
0x180174abe  lea     rdx, [rbp+57h+var_A0]; unsigned __int64 *
0x180174ac2  mov     [rsi+2BCh], r15d
0x180174ac9  mov     rcx, rsi; this
0x180174acc  mov     [rbp+57h+var_A0], r15
0x180174ad0  mov     [rbp+57h+var_98], r15
0x180174ad4  mov     [rsp+100h+var_E0], r15; __int64 *
0x180174ad9  call    ?GetPositionWrapper@CAudStreamSink@@IEAAJPEA_K00PEA_JH@Z; CAudStreamSink::GetPositionWrapper(unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,__int64 *,int)
0x180174ade  mov     ebx, eax
0x180174ae0  test    eax, eax
0x180174ae2  jns     short loc_180174B3D
0x180174ae4  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180174aeb  test    rcx, rcx
0x180174aee  jnz     short loc_180174AFC
0x180174af0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180174af5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180174afc  cmp     [rcx+8], r15b
0x180174b00  jz      short loc_180174B23
0x180174b02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180174b07  cmp     [rax+7CCh], ebx
0x180174b0d  jz      short loc_180174B23
0x180174b0f  mov     r9d, ebx; int
0x180174b12  mov     r8d, 139Dh; int
0x180174b18  mov     rdx, r14; char *
0x180174b1b  mov     rcx, rax; this
0x180174b1e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180174b23  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180174b2a  jb      loc_180175173
0x180174b30  mov     edx, 152h
0x180174b35  mov     r8, r12
0x180174b38  jmp     loc_180174D5A
0x180174b3d  xor     r9d, r9d; unsigned __int64 *
0x180174b40  mov     [rbp+57h+var_A8], r15
0x180174b44  xor     r8d, r8d; __int64 *
0x180174b47  mov     [rsp+100h+var_E0], r15; unsigned __int64 *
0x180174b4c  lea     rdx, [rbp+57h+var_A8]; __int64 *
0x180174b50  mov     rcx, rsi; this
0x180174b53  mov     r12, r15
0x180174b56  mov     r14, r15
0x180174b59  call    ?InternalGetTime@CAudStreamSink@@IEAAJPEA_J0PEA_K1@Z; CAudStreamSink::InternalGetTime(__int64 *,__int64 *,unsigned __int64 *,unsigned __int64 *)
0x180174b5e  ucomiss xmm6, xmm7
0x180174b61  mov     r13, [rbp+57h+var_A0]
0x180174b65  jp      short loc_180174B69
0x180174b67  jz      short loc_180174B8C
0x180174b69  movss   xmm0, dword ptr [rsi+14DCh]
0x180174b71  ucomiss xmm0, xmm7
0x180174b74  jp      short loc_180174B78
0x180174b76  jz      short loc_180174B8C
0x180174b78  mov     rax, [rsi+1440h]
0x180174b7f  cmp     [rax+5E0h], r15d
0x180174b86  jnz     loc_180174DC6
0x180174b8c  movss   xmm0, dword ptr [rsi+14DCh]
0x180174b94  ucomiss xmm0, xmm7
0x180174b97  jp      short loc_180174BB2
0x180174b99  jnz     short loc_180174BB2
0x180174b9b  movss   xmm0, dword ptr [rsi+14E0h]
0x180174ba3  ucomiss xmm0, xmm6
0x180174ba6  jp      loc_180174DC6
0x180174bac  jnz     loc_180174DC6
0x180174bb2  mov     rax, [rsi+1440h]
0x180174bb9  cmp     [rax+5E0h], r15d
  ... truncated ...
```
