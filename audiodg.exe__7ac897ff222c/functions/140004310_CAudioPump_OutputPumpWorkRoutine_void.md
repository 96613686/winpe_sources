# CAudioPump::OutputPumpWorkRoutine(void *)

- ea: `0x140004310`
- end: `0x140004de5`
- name: `?OutputPumpWorkRoutine@CAudioPump@@CAKPEAX@Z`
- size: `2773`
- prototype: `unsigned int __fastcall(CAudioPump *this)`
- caller_count: `0`
- callee_count: `20`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003c30`
- `0x140003ca0`
- `0x140003d00`
- `0x140004310`
- `0x140004df0`
- `0x140004e50`
- `0x140005860`
- `0x140005ac0`
- `0x140005b40`
- `0x140005b6c`
- `0x140005c6c`
- `0x140005d00`
- `0x140005d84`
- `0x140005df4`
- `0x14000619c`
- `0x14000f3f8`
- `0x1400121a0`
- `0x14003a164`
- `0x14005d0e0`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004c70`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140004c70`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000449f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004b40`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000449f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004a36`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140004b40`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004467`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004484`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004467`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140004484`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400044a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400044a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004494`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400043c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400043c1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400047fc`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400047fc`
- `ntdll!EtwEventActivityIdControl` at `0x140004364`
- `ntdll!EtwEventActivityIdControl` at `0x140004a0b`
- `ntdll!EtwEventActivityIdControl` at `0x140004364`
- `ntdll!EtwEventActivityIdControl` at `0x140004a0b`
- `RTWorkQ!RtwqSetLongRunning` at `0x140004ace`
- `RTWorkQ!RtwqSetLongRunning` at `0x140004ace`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAudioPump::OutputPumpWorkRoutine(CAudioPump *this)
{
  __int64 v2; // rcx
  void *v3; // rdx
  __int64 v4; // rsi
  void (__fastcall *v5)(__int64, HANDLE, char *); // rbx
  HANDLE CurrentThread; // rax
  bool v7; // r12
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // r15d
  DWORD LastError; // ebx
  signed __int32 v12; // eax
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // rbx
  LARGE_INTEGER *v19; // rax
  __int64 *v20; // rdx
  __int64 v21; // rax
  __int64 v22; // rcx
  __int64 v23; // rcx
  void (__fastcall *v24)(__int64, __int64); // rax
  void *v25; // rdx
  __int64 v26; // r8
  unsigned __int64 v27; // rcx
  double v28; // xmm0_8
  double v29; // xmm0_8
  unsigned __int64 v30; // rcx
  double v31; // xmm1_8
  double v32; // xmm0_8
  __int64 v33; // rbx
  __int64 v34; // rcx
  __int64 v35; // r8
  __int64 v36; // rcx
  __int64 v37; // r8
  __int64 v38; // rcx
  __int64 v39; // r8
  int v41; // eax
  int v42; // eax
  int v43; // eax
  int v44; // ebx
  CAudioPump *v45; // rcx
  void *v46; // rdx
  wil::details *v47; // rcx
  __int64 v48; // rcx
  void *v49; // rax
  wil::details *v50; // rcx
  __int64 v51; // rcx
  int v52; // eax
  int v53; // [rsp+20h] [rbp-E0h]
  const char *v54; // [rsp+28h] [rbp-D8h]
  CAudioPump *v55; // [rsp+30h] [rbp-D0h] BYREF
  CAudioPump *v56; // [rsp+38h] [rbp-C8h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v58; // [rsp+48h] [rbp-B8h] BYREF
  LARGE_INTEGER v59; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v60; // [rsp+58h] [rbp-A8h] BYREF
  BOOL v61; // [rsp+60h] [rbp-A0h]
  __int64 v62; // [rsp+68h] [rbp-98h] BYREF
  __int128 v63; // [rsp+70h] [rbp-90h] BYREF
  __int128 v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+90h] [rbp-70h]
  __int128 v66; // [rsp+98h] [rbp-68h]
  _QWORD v67[3]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v68[16]; // [rsp+C0h] [rbp-40h] BYREF
  CAudioPump **v69; // [rsp+D0h] [rbp-30h]
  __int64 v70; // [rsp+D8h] [rbp-28h]
  CAudioPump **p_PerformanceCount; // [rsp+E0h] [rbp-20h]
  __int64 v72; // [rsp+E8h] [rbp-18h]
  CAudioPump **v73; // [rsp+F0h] [rbp-10h]
  __int64 v74; // [rsp+F8h] [rbp-8h]
  LARGE_INTEGER *v75; // [rsp+100h] [rbp+0h]
  __int64 v76; // [rsp+108h] [rbp+8h]
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v66 = *((_OWORD *)this + 294);
  v67[0] = *((_QWORD *)this + 588);
  v67[1] = *((_QWORD *)this + 589);
  EtwEventActivityIdControl(4, v67);
  v59.QuadPart = 0;
  v62 = 0;
  v60 = 0;
  v63 = 0;
  v64 = 0;
  v65 = 0;
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0pq_EtwEventWriteTransfer(v2, AudioCore_Pump_Process_Start, this, 3);
  *((_DWORD *)this + 85) = 40;
  CAudioPump::AttachToMMCSS(this);
  v4 = *((_QWORD *)this + 586);
  if ( v4 )
  {
    v5 = *(void (__fastcall **)(__int64, HANDLE, char *))(*(_QWORD *)v4 + 40LL);
    CurrentThread = GetCurrentThread();
    v5(v4, CurrentThread, (char *)this + 4696);
  }
  wil::details::SetEvent(*((wil::details **)this + 33), v3);
  v7 = (int)AERTLockCurrentThread() >= 0;
  v61 = v7;
  v8 = *((_QWORD *)this + 584);
  v60 = v8;
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0p_EtwEventWriteTransfer(v8, AudioCore_Pump_Process_Stop, this);
  v10 = CAudioPump::Yield(this, &v60);
  if ( (byte_1400E7E41 & 8) != 0 )
    McTemplateU0pq_EtwEventWriteTransfer(v9, AudioCore_Pump_Process_Start, this, 4);
  if ( !*((_BYTE *)this + 76) )
  {
    while ( 1 )
    {
      if ( !*((_BYTE *)this + 4680) )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
        if ( *((_BYTE *)this + 76) )
        {
          if ( this != (CAudioPump *)-168LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
        }
        else
        {
          EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
          v56 = (CAudioPump *)((char *)this + 128);
          if ( this != (CAudioPump *)-168LL )
          {
            LastError = GetLastError();
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
            SetLastError(LastError);
          }
          v58 = 0;
          v12 = _InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) - 1;
          if ( v12 )
          {
            if ( v12 == 1 )
              *((_DWORD *)this + 85) = 40;
          }
          else
          {
            v41 = *((_DWORD *)this + 85);
            if ( v41 && (v42 = v41 - 1, (*((_DWORD *)this + 85) = v42) == 0)
              || CAudioPump::InputPumpWorkRoutine == *((unsigned int (__fastcall **)(CAudioPump *))this + 27)
              || *((_BYTE *)this + 4680) )
            {
              *((_DWORD *)this + 85) = 40;
              v43 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 40LL))(*((_QWORD *)this + 26));
              v44 = 0;
              if ( v43 != -2147418113 )
                v44 = v43;
              wil::details::in1diag3::Log_IfFailedMsg(
                retaddr,
                (void *)0x2DE,
                (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
                (const char *)(unsigned int)v44,
                (int)"SetPinInactive failed",
                v54);
              if ( v44 >= 0 )
              {
                _InterlockedExchange((volatile __int32 *)this + 84, 0);
                CAudioPump::CancelTimer(v45, *((void **)this + 37));
                CAudioPump::CancelDeadline(this);
                v51 = *((_QWORD *)this + 41);
                if ( v51 )
                {
                  v52 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v51 + 24LL))(v51);
                  if ( v52 < 0 )
                    wil::details::in1diag3::_Log_Hr(
                      retaddr,
                      (void *)0x2EE,
                      (unsigned int)"avcore\\audiocore\\server\\audiodg\\exe\\audiopump.cpp",
                      (const char *)(unsigned int)v52,
                      v53);
                }
              }
              else
              {
                CAudioPump::CancelTimer(v45, *((void **)this + 37));
                CAudioPump::CancelDeadline(this);
              }
              v47 = (wil::details *)*((_QWORD *)this + 54);
              if ( v47 )
                wil::details::SetEvent(v47, v46);
            }
          }
          if ( this != (CAudioPump *)-128LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
        }
      }
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 10) + 24LL))(*((_QWORD *)this + 10));
      switch ( v10 )
      {
        case 2:
          if ( *((_BYTE *)this + 4680) )
          {
            (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10), 1);
            goto LABEL_48;
          }
          break;
        case 32:
          if ( *((_BYTE *)this + 4680) )
          {
            CAudioPump::UpdatePresentationTimestamp(this);
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10), 0);
LABEL_99:
            v50 = (wil::details *)*((_QWORD *)this + 54);
            if ( v50 )
              wil::details::SetEvent(v50, v25);
            goto LABEL_48;
          }
          break;
        case 16:
          if ( *((_BYTE *)this + 4680) )
          {
            CAudioPump::UpdatePresentationTimestamp(this);
            CAudioPump::CheckForPause(this);
            (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 10) + 48LL))(*((_QWORD *)this + 10), 0);
            goto LABEL_48;
          }
          break;
        default:
          if ( *((_BYTE *)this + 4680) )
            goto LABEL_26;
          break;
      }
      v13 = 0;
      if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) )
        goto LABEL_46;
LABEL_26:
      if ( (byte_1400E7E41 & 8) != 0 )
      {
        v55 = this;
        v69 = &v55;
        v70 = 8;
        McGenEventWrite_EtwEventWriteTransfer(v13, (__int64)AudioCore_Pump_GetCurrentPaddingStart, v14, 2, (__int64)v68);
      }
      (*(void (__fastcall **)(_QWORD, LARGE_INTEGER *, __int128 *))(**((_QWORD **)this + 26) + 24LL))(
        *((_QWORD *)this + 26),
        &v59,
        &v63);
      if ( HIDWORD(v65) )
      {
        v16 = *((_QWORD *)this + 13);
        if ( *((_QWORD *)this + 39) )
        {
          if ( v59.QuadPart )
          {
            v18 = 0;
            if ( v16 + *((_QWORD *)this + 28) - v59.QuadPart > 0 )
              v18 = *((_QWORD *)this + 13);
          }
          else
          {
            v18 = 2 * v16;
          }
        }
        else
        {
          v18 = v16 + *((_QWORD *)this + 28) - v59.QuadPart;
          v15 = v18 % v16;
          if ( v18 % v16 )
            v18 = v16 + v16 + *((_QWORD *)this + 28) - v59.QuadPart - v18 % v16;
        }
      }
      else
      {
        v59.QuadPart = 0;
        v18 = 0;
      }
      if ( (byte_1400E7E41 & 8) != 0 )
      {
        v58 = v18;
        PerformanceCount = v59;
        v55 = this;
        v69 = &v55;
        v70 = 8;
        p_PerformanceCount = (CAudioPump **)&PerformanceCount;
        v72 = 8;
        v73 = (CAudioPump **)&v58;
        v74 = 8;
        McGenEventWrite_EtwEventWriteTransfer(v16, (__int64)AudioCore_Pump_GetCurrentPaddingStop, v17, 4, (__int64)v68);
      }
      if ( !v18 )
        goto LABEL_67;
      *((_BYTE *)this + 74) = 1;
      v16 = *((_QWORD *)this + 46);
      if ( v16 && v16 < 10000 )
      {
        if ( (byte_1400E7E41 & 8) != 0 )
        {
          LODWORD(v55) = *((unsigned __int8 *)this + 75);
          v56 = (CAudioPump *)v16;
          PerformanceCount.LowPart = *((_DWORD *)this + 61);
          v58 = (__int64)this;
          v69 = (CAudioPump **)&v58;
          p_PerformanceCount = (CAudioPump **)&PerformanceCount;
          v73 = &v56;
          v19 = (LARGE_INTEGER *)&v55;
          v20 = AudioCore_Pump_MMBufferingSkippedStart;
LABEL_40:
          v75 = v19;
          v70 = 8;
          v72 = 4;
          v74 = 8;
          v76 = 4;
          McGenEventWrite_EtwEventWriteTransfer(v16, (__int64)v20, v17, 5, (__int64)v68);
        }
      }
      else if ( !*((_BYTE *)this + 75) )
      {
        RtwqSetLongRunning(*((_DWORD *)this + 60), 1);
        *((_BYTE *)this + 75) = 1;
        if ( (byte_1400E7E41 & 8) != 0 )
        {
          PerformanceCount.LowPart = 1;
          v58 = *((_QWORD *)this + 46);
          LODWORD(v55) = *((_DWORD *)this + 61);
          v56 = this;
          v69 = &v56;
          p_PerformanceCount = &v55;
          v73 = (CAudioPump **)&v58;
          v19 = &PerformanceCount;
          v20 = AudioCore_Pump_MMBufferingStart;
          goto LABEL_40;
        }
      }
      if ( v18 > 0 && (int)(*((float *)this + 28) * (double)(int)v18 / 10000000.0 + 0.5) )
      {
        do
        {
          v21 = *((_QWORD *)this + 13);
          if ( v18 <= v21 )
            v21 = v18;
          v62 = v21;
          (*(void (__fastcall **)(_QWORD, __int64 *, __int128 *))(**((_QWORD **)this + 10) + 32LL))(
            *((_QWORD *)this + 10),
            &v62,
            &v63);
          v22 = (unsigned int)(int)(*((float *)this + 28) * (double)(int)v62 / 10000000.0 + 0.5);
          *(_QWORD *)&v64 = v22 + v64;
          *((_QWORD *)&v63 + 1) += v22;
          v18 -= v62;
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
        }
        while ( (int)((double)(int)v18 * *((float *)this + 28) / 10000000.0 + 0.5) );
        goto LABEL_46;
      }
LABEL_67:
      if ( (byte_1400E7E41 & 4) != 0 )
        McTemplateU0pi_EtwEventWriteTransfer(v16, v15, this, v18);
      if ( !*((_QWORD *)this + 39) && v59.QuadPart > 0 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 26) + 32LL))(*((_QWORD *)this + 26));
LABEL_46:
      v23 = *((_QWORD *)this + 10);
      v24 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 48LL);
      if ( v10 == 4 )
      {
        v24(v23, 0);
        v48 = *((_QWORD *)this + 53);
        if ( v48 )
        {
          v49 = (void *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v48 + 24LL))(v48);
          SetEvent(v49);
        }
        goto LABEL_48;
      }
      v24(v23, 1);
      if ( v10 == 32 )
        goto LABEL_99;
LABEL_48:
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      v27 = PerformanceCount.QuadPart - v60;
      if ( PerformanceCount.QuadPart - v60 < 0 )
        v28 = (double)(int)(v27 & 1 | (v27 >> 1)) + (double)(int)(v27 & 1 | (v27 >> 1));
      else
        v28 = (double)(int)v27;
      v29 = v28 * 10000000.0;
      v30 = g_u64QPCFrequency;
      if ( (g_u64QPCFrequency & 0x8000000000000000uLL) != 0LL )
      {
        v30 = g_u64QPCFrequency & 1;
        v31 = (double)(int)(v30 | (g_u64QPCFrequency >> 1)) + (double)(int)(v30 | (g_u64QPCFrequency >> 1));
      }
      else
      {
        v31 = (double)(int)g_u64QPCFrequency;
      }
      v32 = v29 / v31;
      v33 = (unsigned int)(int)v32;
      *((_QWORD *)this + 45) = v33;
      *((_QWORD *)this + 49) += v33;
      ++*((_DWORD *)this + 100);
      if ( (byte_1400E7E41 & 8) != 0 )
      {
        v55 = (CAudioPump *)*((_QWORD *)this + 44);
        v58 = (unsigned int)(int)v32;
        v56 = this;
        v69 = &v56;
        v70 = 8;
        p_PerformanceCount = (CAudioPump **)&v58;
        v72 = 8;
        v73 = &v55;
        v74 = 8;
        McGenEventWrite_EtwEventWriteTransfer(v30, (__int64)AudioCore_Pump_ProcPassDuration, v26, 4, (__int64)v68);
      }
      if ( v33 > *((_QWORD *)this + 44) && _InterlockedCompareExchange((volatile signed __int32 *)this + 84, 0, 0) )
        *((_QWORD *)this + 48) = _InterlockedIncrement64((volatile signed __int64 *)this + 48);
      else
        _InterlockedExchange64((volatile __int64 *)this + 48, 0);
      CAudioPump::SignalWorkCompleted(this);
      if ( (byte_1400E7E41 & 8) != 0 )
      {
        v56 = this;
        v69 = &v56;
        v70 = 8;
        McGenEventWrite_EtwEventWriteTransfer(v34, (__int64)AudioCore_Pump_Process_Stop, v35, 2, (__int64)v68);
      }
      v10 = CAudioPump::Yield(this, &v60);
      v60 = *((_QWORD *)this + 584);
      if ( (byte_1400E7E41 & 8) != 0 )
      {
        LODWORD(v55) = 5;
        v56 = this;
        v69 = &v56;
        v70 = 8;
        p_PerformanceCount = &v55;
        v72 = 4;
        McGenEventWrite_EtwEventWriteTransfer(v36, (__int64)AudioCore_Pump_Process_Start, v37, 3, (__int64)v68);
      }
      if ( *((_BYTE *)this + 76) )
      {
        v7 = v61;
        break;
      }
    }
  }
  CAudioPump::CancelDeadline(this);
  ResetEngineThreadPriority((void **)this + 29, *((_DWORD *)this + 61));
  *((_DWORD *)this + 61) = 0;
  if ( v7 )
    AERTUnlockCurrentThread();
  if ( (byte_1400E7E41 & 8) != 0 )
  {
    v56 = this;
    v69 = &v56;
    v70 = 8;
    McGenEventWrite_EtwEventWriteTransfer(v38, (__int64)AudioCore_Pump_Process_Stop, v39, 2, (__int64)v68);
  }
  EtwEventActivityIdControl(4, v67);
  return 0;
}

```

## disassembly

```asm
0x140004310  push    rbp
0x140004312  push    rbx
0x140004313  push    rsi
0x140004314  push    rdi
0x140004315  push    r12
0x140004317  push    r13
0x140004319  push    r14
0x14000431b  push    r15
0x14000431d  lea     rbp, [rsp-28h]
0x140004322  sub     rsp, 128h
0x140004329  mov     rax, cs:__security_cookie
0x140004330  xor     rax, rsp
0x140004333  mov     [rbp+60h+var_50], rax
0x140004337  mov     rdi, rcx
0x14000433a  movups  xmm0, xmmword ptr [rcx+1260h]
0x140004341  movups  [rbp+60h+var_C8], xmm0
0x140004345  mov     rax, [rcx+1260h]
0x14000434c  mov     [rbp+60h+var_B8], rax
0x140004350  mov     rax, [rcx+1268h]
0x140004357  mov     [rbp+60h+var_B0], rax
0x14000435b  lea     rdx, [rbp+60h+var_B8]
0x14000435f  mov     ecx, 4
0x140004364  call    cs:__imp_EtwEventActivityIdControl
0x14000436a  nop
0x14000436b  xor     r13d, r13d
0x14000436e  mov     [rsp+160h+var_110], r13
0x140004373  mov     [rsp+160h+var_F8], r13
0x140004378  mov     [rsp+160h+var_108], r13
0x14000437d  xorps   xmm0, xmm0
0x140004380  xor     eax, eax
0x140004382  movups  [rsp+160h+var_F0], xmm0
0x140004387  movups  [rbp+60h+var_E0], xmm0
0x14000438b  mov     [rbp+60h+var_D0], rax
0x14000438f  test    cs:byte_1400E7E41, 8
0x140004396  jnz     loc_140004CFA
0x14000439c  mov     dword ptr [rdi+154h], 28h ; '('
0x1400043a6  mov     rcx, rdi; this
0x1400043a9  call    ?AttachToMMCSS@CAudioPump@@AEAAXXZ; CAudioPump::AttachToMMCSS(void)
0x1400043ae  mov     rsi, [rdi+1250h]
0x1400043b5  test    rsi, rsi
0x1400043b8  jz      short loc_1400043DC
0x1400043ba  mov     rax, [rsi]
0x1400043bd  mov     rbx, [rax+28h]
0x1400043c1  call    cs:__imp_GetCurrentThread
0x1400043c7  lea     r8, [rdi+1258h]
0x1400043ce  mov     rdx, rax
0x1400043d1  mov     rcx, rsi
0x1400043d4  mov     rax, rbx
0x1400043d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043dc  mov     rcx, [rdi+108h]; this
0x1400043e3  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1400043e8  call    ?AERTLockCurrentThread@@YAJXZ; AERTLockCurrentThread(void)
0x1400043ed  mov     r12d, eax
0x1400043f0  shr     r12d, 1Fh
0x1400043f4  xor     r12b, 1
0x1400043f8  mov     [rsp+160h+var_100], r12d
0x1400043fd  mov     rcx, [rdi+1240h]
0x140004404  mov     [rsp+160h+var_108], rcx
0x140004409  test    cs:byte_1400E7E41, 8
0x140004410  jnz     loc_140004CA5
0x140004416  lea     rdx, [rsp+160h+var_108]
0x14000441b  mov     rcx, rdi
0x14000441e  call    ?Yield@CAudioPump@@AEAA?AW4TEventType@1@PEA_K@Z; CAudioPump::Yield(unsigned __int64 *)
0x140004423  mov     r15d, eax
0x140004426  test    cs:byte_1400E7E41, 8
0x14000442d  jnz     loc_140004C8B
0x140004433  movzx   ecx, byte ptr [rdi+4Ch]
0x140004437  test    cl, cl
0x140004439  jnz     loc_14000499D
0x14000443f  lea     r12, ?InputPumpWorkRoutine@CAudioPump@@CAKPEAX@Z; CAudioPump::InputPumpWorkRoutine(void *)
0x140004446  nop     word ptr [rax+rax+00000000h]
0x140004450  cmp     byte ptr [rdi+1248h], 0
0x140004457  jnz     loc_1400044E0
0x14000445d  lea     r14, [rdi+0A8h]
0x140004464  mov     rcx, r14; lpCriticalSection
0x140004467  call    cs:__imp_EnterCriticalSection
0x14000446d  nop
0x14000446e  movzx   eax, byte ptr [rdi+4Ch]
0x140004472  test    al, al
0x140004474  jnz     loc_140004B34
0x14000447a  lea     rsi, [rdi+80h]
0x140004481  mov     rcx, rsi; lpCriticalSection
0x140004484  call    cs:__imp_EnterCriticalSection
0x14000448a  mov     [rsp+160h+var_128], rsi
0x14000448f  test    r14, r14
0x140004492  jz      short loc_1400044AD
0x140004494  call    cs:__imp_GetLastError
0x14000449a  mov     ebx, eax
0x14000449c  mov     rcx, r14; lpCriticalSection
0x14000449f  call    cs:__imp_LeaveCriticalSection
0x1400044a5  mov     ecx, ebx; dwErrCode
0x1400044a7  call    cs:__imp_SetLastError
0x1400044ad  mov     [rsp+160h+var_118], r13
0x1400044b2  mov     ecx, r13d
0x1400044b5  xor     eax, eax
0x1400044b7  lock cmpxchg [rdi+150h], ecx
0x1400044bf  sub     eax, 1
0x1400044c2  jz      loc_140004B6E
0x1400044c8  cmp     eax, 1
0x1400044cb  jnz     short loc_1400044D7
0x1400044cd  mov     dword ptr [rdi+154h], 28h ; '('
0x1400044d7  test    rsi, rsi
0x1400044da  jnz     loc_140004A33
0x1400044e0  mov     rcx, [rdi+50h]
0x1400044e4  mov     rax, [rcx]
0x1400044e7  mov     rax, [rax+18h]
0x1400044eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044f0  cmp     r15d, 2
0x1400044f4  jnz     short loc_140004517
0x1400044f6  cmp     byte ptr [rdi+1248h], 0
0x1400044fd  jnz     loc_140004B4B
0x140004503  mov     ecx, r13d
0x140004506  xor     eax, eax
0x140004508  lock cmpxchg [rdi+150h], ecx
0x140004510  jnz     short loc_140004534
0x140004512  jmp     loc_1400047C9
0x140004517  cmp     r15d, 20h ; ' '
0x14000451b  jz      loc_140004CB9
0x140004521  cmp     r15d, 10h
0x140004525  jz      loc_140004D14
0x14000452b  cmp     byte ptr [rdi+1248h], 0
0x140004532  jz      short loc_140004503
0x140004534  test    cs:byte_1400E7E41, 8
0x14000453b  jz      short loc_14000456E
0x14000453d  mov     [rsp+160h+var_130], rdi
0x140004542  lea     rax, [rsp+160h+var_130]
0x140004547  mov     [rbp+60h+var_90], rax
0x14000454b  mov     [rbp+60h+var_88], 8
0x140004553  lea     rax, [rbp+60h+var_A0]
0x140004557  mov     qword ptr [rsp+160h+var_140], rax
0x14000455c  mov     r9d, 2
0x140004562  lea     rdx, AudioCore_Pump_GetCurrentPaddingStart
0x140004569  call    McGenEventWrite_EtwEventWriteTransfer
0x14000456e  mov     rcx, [rdi+0D0h]
0x140004575  mov     rax, [rcx]
0x140004578  lea     r8, [rsp+160h+var_F0]
0x14000457d  lea     rdx, [rsp+160h+var_110]
0x140004582  mov     rax, [rax+18h]
0x140004586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000458b  cmp     dword ptr [rbp+60h+var_D0+4], 0
0x14000458f  jz      loc_140004A80
0x140004595  mov     rcx, [rdi+68h]
0x140004599  cmp     qword ptr [rdi+138h], 0
0x1400045a1  jz      loc_140004A8D
0x1400045a7  cmp     [rsp+160h+var_110], 0
0x1400045ad  jz      loc_140004B65
0x1400045b3  mov     rax, [rdi+0E0h]
0x1400045ba  sub     rax, [rsp+160h+var_110]
0x1400045bf  add     rax, rcx
0x1400045c2  mov     rbx, r13
0x1400045c5  test    rax, rax
0x1400045c8  cmovg   rbx, rcx
0x1400045cc  test    cs:byte_1400E7E41, 8
0x1400045d3  jz      short loc_140004637
0x1400045d5  mov     [rsp+160h+var_118], rbx
0x1400045da  mov     rax, [rsp+160h+var_110]
0x1400045df  mov     qword ptr [rsp+160h+PerformanceCount], rax
0x1400045e4  mov     [rsp+160h+var_130], rdi
0x1400045e9  lea     rax, [rsp+160h+var_130]
0x1400045ee  mov     [rbp+60h+var_90], rax
0x1400045f2  mov     [rbp+60h+var_88], 8
0x1400045fa  lea     rax, [rsp+160h+PerformanceCount]
0x1400045ff  mov     [rbp+60h+var_80], rax
0x140004603  mov     [rbp+60h+var_78], 8
0x14000460b  lea     rax, [rsp+160h+var_118]
0x140004610  mov     [rbp+60h+var_70], rax
0x140004614  mov     [rbp+60h+var_68], 8
0x14000461c  lea     rax, [rbp+60h+var_A0]
0x140004620  mov     qword ptr [rsp+160h+var_140], rax
0x140004625  mov     r9d, 4
0x14000462b  lea     rdx, AudioCore_Pump_GetCurrentPaddingStop
0x140004632  call    McGenEventWrite_EtwEventWriteTransfer
0x140004637  test    rbx, rbx
0x14000463a  jz      loc_140004A41
0x140004640  mov     byte ptr [rdi+4Ah], 1
0x140004644  mov     rcx, [rdi+170h]
0x14000464b  test    rcx, rcx
0x14000464e  jz      loc_140004AB9
0x140004654  cmp     rcx, 2710h
0x14000465b  jge     loc_140004AB9
0x140004661  test    cs:byte_1400E7E41, 8
0x140004668  jz      short loc_1400046E5
0x14000466a  movzx   eax, byte ptr [rdi+4Bh]
0x14000466e  mov     dword ptr [rsp+160h+var_130], eax
0x140004672  mov     [rsp+160h+var_128], rcx
0x140004677  mov     eax, [rdi+0F4h]
0x14000467d  mov     dword ptr [rsp+160h+PerformanceCount], eax
0x140004681  mov     [rsp+160h+var_118], rdi
0x140004686  lea     rax, [rsp+160h+var_118]
0x14000468b  mov     [rbp+60h+var_90], rax
0x14000468f  lea     rax, [rsp+160h+PerformanceCount]
0x140004694  mov     [rbp+60h+var_80], rax
0x140004698  lea     rax, [rsp+160h+var_128]
0x14000469d  mov     [rbp+60h+var_70], rax
0x1400046a1  lea     rax, [rsp+160h+var_130]
0x1400046a6  lea     rdx, AudioCore_Pump_MMBufferingSkippedStart
0x1400046ad  mov     [rbp+60h+var_60], rax
0x1400046b1  lea     rax, [rbp+60h+var_A0]
0x1400046b5  mov     qword ptr [rsp+160h+var_140], rax
0x1400046ba  mov     [rbp+60h+var_88], 8
0x1400046c2  mov     [rbp+60h+var_78], 4
0x1400046ca  mov     [rbp+60h+var_68], 8
0x1400046d2  mov     [rbp+60h+var_58], 4
0x1400046da  mov     r9d, 5
0x1400046e0  call    McGenEventWrite_EtwEventWriteTransfer
0x1400046e5  test    rbx, rbx
0x1400046e8  jle     loc_140004A41
0x1400046ee  movss   xmm1, dword ptr [rdi+70h]
0x1400046f3  cvtps2pd xmm1, xmm1
0x1400046f6  xorps   xmm0, xmm0
0x1400046f9  cvtsi2sd xmm0, rbx
0x1400046fe  mulsd   xmm1, xmm0
0x140004702  divsd   xmm1, cs:__real@416312d000000000
0x14000470a  addsd   xmm1, cs:__real@3fe0000000000000
0x140004712  cvttsd2si rax, xmm1
0x140004717  test    eax, eax
0x140004719  jz      loc_140004A41
0x14000471f  mov     rax, [rdi+68h]
0x140004723  cmp     rbx, rax
0x140004726  cmovle  rax, rbx
0x14000472a  mov     [rsp+160h+var_F8], rax
0x14000472f  mov     rcx, [rdi+50h]
0x140004733  mov     rax, [rcx]
0x140004736  lea     r8, [rsp+160h+var_F0]
0x14000473b  lea     rdx, [rsp+160h+var_F8]
0x140004740  mov     rax, [rax+20h]
0x140004744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004749  movss   xmm1, dword ptr [rdi+70h]
0x14000474e  cvtps2pd xmm1, xmm1
0x140004751  mov     rdx, [rsp+160h+var_F8]
0x140004756  xorps   xmm0, xmm0
0x140004759  cvtsi2sd xmm0, rdx
0x14000475e  mulsd   xmm1, xmm0
0x140004762  divsd   xmm1, cs:__real@416312d000000000
0x14000476a  addsd   xmm1, cs:__real@3fe0000000000000
0x140004772  cvttsd2si rcx, xmm1
0x140004777  mov     ecx, ecx
0x140004779  add     qword ptr [rbp+60h+var_E0], rcx
0x14000477d  add     qword ptr [rsp+160h+var_F0+8], rcx
0x140004782  sub     rbx, rdx
0x140004785  mov     rcx, [rdi+0D0h]
0x14000478c  mov     rax, [rcx]
0x14000478f  mov     rax, [rax+20h]
0x140004793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004798  xorps   xmm1, xmm1
0x14000479b  cvtsi2sd xmm1, rbx
0x1400047a0  movss   xmm0, dword ptr [rdi+70h]
0x1400047a5  cvtps2pd xmm0, xmm0
0x1400047a8  mulsd   xmm1, xmm0
0x1400047ac  divsd   xmm1, cs:__real@416312d000000000
0x1400047b4  addsd   xmm1, cs:__real@3fe0000000000000
0x1400047bc  cvttsd2si rax, xmm1
0x1400047c1  test    eax, eax
0x1400047c3  jnz     loc_14000471F
0x1400047c9  mov     rcx, [rdi+50h]
0x1400047cd  mov     rax, [rcx]
0x1400047d0  mov     rax, [rax+30h]
0x1400047d4  cmp     r15d, 4
0x1400047d8  jz      loc_140004C4A
0x1400047de  mov     edx, 1
0x1400047e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047e8  cmp     r15d, 20h ; ' '
0x1400047ec  jz      loc_140004CE0
0x1400047f2  mov     qword ptr [rsp+160h+PerformanceCount], r13
0x1400047f7  lea     rcx, [rsp+160h+PerformanceCount]; lpPerformanceCount
0x1400047fc  call    cs:__imp_QueryPerformanceCounter
0x140004802  mov     rcx, qword ptr [rsp+160h+PerformanceCount]
0x140004807  sub     rcx, [rsp+160h+var_108]
0x14000480c  xorps   xmm0, xmm0
0x14000480f  js      loc_140004D52
0x140004815  cvtsi2sd xmm0, rcx
0x14000481a  mulsd   xmm0, cs:__real@416312d000000000
0x140004822  mov     rcx, cs:?g_u64QPCFrequency@@3_KA; unsigned __int64 g_u64QPCFrequency
0x140004829  xorps   xmm1, xmm1
0x14000482c  test    rcx, rcx
0x14000482f  js      loc_140004D6C
0x140004835  cvtsi2sd xmm1, rcx
0x14000483a  divsd   xmm0, xmm1
0x14000483e  cvttsd2si rbx, xmm0
0x140004843  mov     [rdi+168h], rbx
0x14000484a  add     [rdi+188h], rbx
0x140004851  inc     dword ptr [rdi+190h]
0x140004857  test    cs:byte_1400E7E41, 8
0x14000485e  jz      short loc_1400048C4
0x140004860  mov     rax, [rdi+160h]
0x140004867  mov     [rsp+160h+var_130], rax
0x14000486c  mov     [rsp+160h+var_118], rbx
0x140004871  mov     [rsp+160h+var_128], rdi
0x140004876  lea     rax, [rsp+160h+var_128]
0x14000487b  mov     [rbp+60h+var_90], rax
0x14000487f  mov     [rbp+60h+var_88], 8
0x140004887  lea     rax, [rsp+160h+var_118]
0x14000488c  mov     [rbp+60h+var_80], rax
0x140004890  mov     [rbp+60h+var_78], 8
0x140004898  lea     rax, [rsp+160h+var_130]
0x14000489d  mov     [rbp+60h+var_70], rax
0x1400048a1  mov     [rbp+60h+var_68], 8
0x1400048a9  lea     rax, [rbp+60h+var_A0]
0x1400048ad  mov     qword ptr [rsp+160h+var_140], rax
0x1400048b2  mov     r9d, 4
  ... truncated ...
```
