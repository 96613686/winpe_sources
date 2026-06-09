# CMidi2SchedulerMidiTransform::QueueWorker(void)

- ea: `0x18000af80`
- end: `0x18000b538`
- name: `?QueueWorker@CMidi2SchedulerMidiTransform@@AEAAXXZ`
- size: `1464`
- prototype: `void __fastcall(CMidi2SchedulerMidiTransform *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `service_task`

## callees

- `0x1800016dc`
- `0x1800017f4`
- `0x1800096d8`
- `0x18000a08c`
- `0x18000a6c0`
- `0x18000a83c`
- `0x18000aa6c`
- `0x18000ab08`
- `0x18000af80`
- `0x18000b964`
- `0x18000c008`
- `0x18000c38c`

## import_xrefs

- `msvcp_win!_Mtx_lock` at `0x18000b161`
- `msvcp_win!_Mtx_lock` at `0x18000b161`
- `msvcp_win!_Mtx_unlock` at `0x18000b424`
- `msvcp_win!_Mtx_unlock` at `0x18000b424`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b170`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b18b`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b170`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000b18b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b03d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b029`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000b03d`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000b037`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000b04b`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000b037`
- `api-ms-win-core-processthreads-l1-1-0!SetPriorityClass` at `0x18000b04b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b05f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000b05f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b051`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000b051`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b13b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b13b`

## pseudocode

```c
void __fastcall CMidi2SchedulerMidiTransform::QueueWorker(CMidi2SchedulerMidiTransform *this)
{
  CMidi2SchedulerMidiTransform *v1; // rdi
  _DWORD *v2; // rcx
  int v3; // r8d
  int v4; // r9d
  const wchar_t *v5; // rax
  HANDLE CurrentProcess; // rax
  HANDLE v7; // rax
  HANDLE CurrentThread; // rax
  unsigned int v9; // r8d
  __int64 v10; // r14
  LONGLONG QuadPart; // r13
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  unsigned __int64 v15; // rbx
  unsigned int i; // r12d
  __int64 v17; // rax
  __int64 *v18; // r8
  __int64 v19; // rax
  __int64 v20; // rcx
  int v21; // eax
  unsigned int v22; // r8d
  int v23; // r14d
  LARGE_INTEGER **v24; // r14
  __int64 v25; // rdx
  LARGE_INTEGER *v26; // rax
  __int64 v27; // r10
  __int64 v28; // r11
  __int64 v29; // r9
  __int64 *v30; // r8
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // rax
  bool v34; // zf
  _DWORD *v35; // rcx
  int v36; // r8d
  int v37; // r9d
  _QWORD *v38; // rax
  __int64 v39; // rax
  _DWORD *v40; // rcx
  int v41; // r8d
  int v42; // r9d
  CMidi2SchedulerMidiTransform *v43; // rax
  _DWORD *v44; // rcx
  int v45; // r8d
  int v46; // r9d
  const wchar_t *v47; // rax
  int v48; // [rsp+20h] [rbp-D8h]
  int v49; // [rsp+20h] [rbp-D8h]
  const char *v50; // [rsp+50h] [rbp-A8h] BYREF
  const char *v51; // [rsp+58h] [rbp-A0h] BYREF
  const char *v52; // [rsp+60h] [rbp-98h] BYREF
  __int64 v53; // [rsp+68h] [rbp-90h] BYREF
  int v54; // [rsp+70h] [rbp-88h]
  int v55; // [rsp+74h] [rbp-84h]
  _QWORD v56[3]; // [rsp+78h] [rbp-80h] BYREF
  _QWORD v57[2]; // [rsp+90h] [rbp-68h] BYREF
  _QWORD v58[2]; // [rsp+A0h] [rbp-58h] BYREF
  _QWORD v59[9]; // [rsp+B0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]
  CMidi2SchedulerMidiTransform *v61; // [rsp+100h] [rbp+8h] BYREF
  const wchar_t *v62; // [rsp+108h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+110h] [rbp+18h] BYREF
  const char *v64; // [rsp+118h] [rbp+20h] BYREF

  v61 = this;
  v1 = this;
  v2 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
  if ( *v2 > 4u )
  {
    v5 = (const wchar_t *)((char *)v1 + 16);
    if ( *((_QWORD *)v1 + 5) > 7u )
      v5 = *(const wchar_t **)v5;
    v62 = v5;
    PerformanceCount.QuadPart = (LONGLONG)L"Enter";
    v64 = (const char *)v1;
    v50 = "CMidi2SchedulerMidiTransform::QueueWorker";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v2,
      (unsigned int)qword_1800115C0,
      v3,
      v4,
      (__int64)&v50,
      (__int64)&v64,
      (__int64)&PerformanceCount,
      (__int64)&v62);
  }
  CurrentProcess = GetCurrentProcess();
  SetPriorityClass(CurrentProcess, 0x80u);
  v7 = GetCurrentProcess();
  SetPriorityClass(v7, 0x100u);
  CurrentThread = GetCurrentThread();
  SetThreadPriority(CurrentThread, 15);
  v10 = *((_QWORD *)v1 + 14) + 100LL;
  v51 = (const char *)v10;
  QuadPart = 0;
  while ( 1 )
  {
    v12 = *((_QWORD *)v1 + 31);
    if ( v12 )
    {
      if ( (*(_DWORD *)(v12 + 4) & 1) != 0 )
        break;
    }
    try
    {
      if ( !*((_QWORD *)v1 + 10) )
        goto LABEL_10;
      v14 = *((_QWORD *)v1 + 31);
      if ( v14 && (*(_DWORD *)(v14 + 4) & 1) != 0 )
        goto LABEL_11;
      if ( !*((_QWORD *)v1 + 10) )
        goto LABEL_11;
      v62 = 0;
      if ( (int)CMidi2SchedulerMidiTransform::GetTopMessageTimestamp(v1, (unsigned __int64 *)&v62) < 0 )
        goto LABEL_11;
      v15 = (unsigned __int64)v62 - v10;
      PerformanceCount.QuadPart = 0;
      QueryPerformanceCounter(&PerformanceCount);
      if ( PerformanceCount.QuadPart < v15 )
      {
        LODWORD(v62) = 0;
        v39 = *((_QWORD *)v1 + 31);
        if ( v39 && (*(_DWORD *)(v39 + 4) & 1) != 0
          || (int)CMidi2SchedulerMidiTransform::CalculateSafeSleepTime(v1, v15, (unsigned int *)&v62) < 0
          || (unsigned int)v62 <= 0xF )
        {
          goto LABEL_11;
        }
LABEL_10:
        wil::slim_event_t<1>::wait((char *)v1 + 260);
        goto LABEL_11;
      }
      v64 = (char *)v1 + 136;
      if ( _Mtx_lock((CMidi2SchedulerMidiTransform *)((char *)v1 + 136)) )
        std::_Throw_Cpp_error(5);
      if ( *((_DWORD *)v1 + 53) == 0x7FFFFFFF )
      {
        *((_DWORD *)v1 + 53) = 2147483646;
        std::_Throw_Cpp_error(6);
      }
      for ( i = 0; *((_QWORD *)v1 + 10); ++i )
      {
        v17 = *((_QWORD *)v1 + 31);
        if ( v17 )
        {
          if ( (*(_DWORD *)(v17 + 4) & 1) != 0 )
            break;
        }
        if ( i >= 0x1F4 )
          break;
        v18 = *(__int64 **)(*((_QWORD *)v1 + 7) + 8 * (*((_QWORD *)v1 + 9) & (*((_QWORD *)v1 + 8) - 1LL)));
        v19 = *v18;
        if ( *v18 > (unsigned __int64)v62 )
          break;
        v20 = *((_QWORD *)v1 + 31);
        if ( v20 )
        {
          if ( (*(_DWORD *)(v20 + 4) & 1) != 0 )
            goto LABEL_35;
          v19 = *v18;
        }
        v21 = CMidi2SchedulerMidiTransform::SendMidiMessageNow(v1, 0, v18[2], *((unsigned int *)v18 + 3), v19);
        v23 = v21;
        if ( v21 < 0 )
        {
          wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x2DE, v22, (const char *)(unsigned int)v21, v49);
          v35 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
          if ( *v35 > 2u )
          {
            LODWORD(v62) = v23;
            v38 = (_QWORD *)((char *)v1 + 16);
            if ( *((_QWORD *)v1 + 5) > 7u )
              v38 = (_QWORD *)*v38;
            PerformanceCount.QuadPart = (LONGLONG)v38;
            v64 = (const char *)L"Unable to send message";
            v50 = (const char *)v1;
            v52 = "CMidi2SchedulerMidiTransform::QueueWorker";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (_DWORD)v35,
              (unsigned int)&byte_18001155F,
              v36,
              v37,
              (__int64)&v52,
              (__int64)&v50,
              (__int64)&v64,
              (__int64)&PerformanceCount,
              (__int64)&v62);
          }
          break;
        }
LABEL_35:
        v24 = (LARGE_INTEGER **)((char *)v1 + 48);
        v25 = *((_QWORD *)v1 + 10);
        if ( v1 == (CMidi2SchedulerMidiTransform *)-48LL || (v26 = *v24) == 0 )
        {
          PerformanceCount.QuadPart = 0;
        }
        else
        {
          PerformanceCount = **v24;
          QuadPart = v26->QuadPart;
        }
        if ( v25 >= 2 )
        {
          v27 = *((_QWORD *)v1 + 9);
          v28 = *((_QWORD *)v1 + 11);
          v29 = v27 + v25 - 1;
          v30 = *(__int64 **)(*(_QWORD *)(QuadPart + 8) + 8 * (v29 & (*(_QWORD *)(QuadPart + 16) - 1LL)));
          v53 = *v30;
          v54 = *((_DWORD *)v30 + 2);
          v55 = *((_DWORD *)v30 + 3);
          v31 = v30[4];
          v30[4] = 0;
          v32 = v30[3];
          v30[3] = 0;
          v33 = v30[2];
          v30[2] = 0;
          v56[0] = v33;
          v56[1] = v32;
          v56[2] = v31;
          v57[0] = QuadPart;
          v57[1] = v29;
          v58[0] = QuadPart;
          v58[1] = v29;
          v59[0] = PerformanceCount.QuadPart;
          v59[1] = v27;
          std::_Pop_heap_hole_unchecked<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(
            (unsigned int)v59,
            (unsigned int)v58,
            (unsigned int)v57,
            (unsigned int)&v53,
            v28);
          std::vector<unsigned char>::~vector<unsigned char>(v56);
        }
        std::vector<unsigned char>::~vector<unsigned char>(
          *(_QWORD *)(*((_QWORD *)v1 + 7)
                    + 8 * ((*((_QWORD *)v1 + 8) - 1LL) & (*((_QWORD *)v1 + 10) - 1LL + *((_QWORD *)v1 + 9))))
        + 16LL);
        v34 = (*((_QWORD *)v1 + 10))-- == 1;
        QuadPart = 0;
        if ( v34 )
          *((_QWORD *)v1 + 9) = 0;
      }
      _Mtx_unlock((CMidi2SchedulerMidiTransform *)((char *)v1 + 136));
      v10 = (__int64)v51;
LABEL_11:
      v13 = *((_QWORD *)v1 + 31);
      if ( !v13 || (*(_DWORD *)(v13 + 4) & 1) == 0 )
      {
        if ( *((_DWORD *)v1 + 65) )
          _InterlockedExchange((volatile __int32 *)v1 + 65, 0);
        v62 = 0;
        std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(&v62);
      }
    }
    catch ( ... )
    {
      wil::details::in1diag3::_Log_Hr(retaddr, (void *)0x33E, v9, (const char *)0x80004005LL, v48);
      v44 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
      if ( *v44 > 2u )
      {
        v47 = (const wchar_t *)((char *)v61 + 16);
        if ( *((_QWORD *)v61 + 5) > 7u )
          v47 = *(const wchar_t **)v47;
        v62 = v47;
        PerformanceCount.QuadPart = (LONGLONG)L"Exception processing queue";
        v64 = (const char *)v61;
        v51 = "CMidi2SchedulerMidiTransform::QueueWorker";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v44,
          (unsigned int)qword_180011508,
          v45,
          v46,
          (__int64)&v51,
          (__int64)&v64,
          (__int64)&PerformanceCount,
          (__int64)&v62);
      }
      v1 = v61;
      break;
    }
  }
  v40 = (_DWORD *)*((_QWORD *)MidiSchedulerTransformTelemetryProvider::Instance() + 1);
  if ( *v40 > 4u )
  {
    v43 = (CMidi2SchedulerMidiTransform *)((char *)v1 + 16);
    if ( *((_QWORD *)v1 + 5) > 7u )
      v43 = *(CMidi2SchedulerMidiTransform **)v43;
    v61 = v43;
    v62 = L"Exit";
    PerformanceCount.QuadPart = (LONGLONG)v1;
    v64 = "CMidi2SchedulerMidiTransform::QueueWorker";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v40,
      (unsigned int)word_1800114B2,
      v41,
      v42,
      (__int64)&v64,
      (__int64)&PerformanceCount,
      (__int64)&v62,
      (__int64)&v61);
  }
  *((_BYTE *)v1 + 256) = 1;
}

```

## disassembly

```asm
0x18000af80  mov     [rsp+arg_0], rcx
0x18000af85  push    rbx
0x18000af86  push    rsi
0x18000af87  push    rdi
0x18000af88  push    r12
0x18000af8a  push    r13
0x18000af8c  push    r14
0x18000af8e  push    r15
0x18000af90  sub     rsp, 0C0h
0x18000af97  mov     rdi, rcx
0x18000af9a  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000af9f  mov     rcx, [rax+8]
0x18000afa3  mov     eax, [rcx]
0x18000afa5  cmp     eax, 4
0x18000afa8  jbe     short loc_18000B022
0x18000afaa  lea     rax, [rdi+10h]
0x18000afae  cmp     qword ptr [rax+18h], 7
0x18000afb3  jbe     short loc_18000AFB8
0x18000afb5  mov     rax, [rax]
0x18000afb8  mov     [rsp+0F8h+arg_8], rax
0x18000afc0  lea     rax, aEnter; "Enter"
0x18000afc7  mov     qword ptr [rsp+0F8h+PerformanceCount], rax
0x18000afcf  mov     [rsp+0F8h+arg_18], rdi
0x18000afd7  lea     r15, aCmidi2schedule_5; "CMidi2SchedulerMidiTransform::QueueWork"...
0x18000afde  mov     [rsp+0F8h+var_A8], r15
0x18000afe3  lea     rax, [rsp+0F8h+arg_8]
0x18000afeb  mov     [rsp+0F8h+var_C0], rax
0x18000aff0  lea     rax, [rsp+0F8h+PerformanceCount]
0x18000aff8  mov     [rsp+0F8h+var_C8], rax
0x18000affd  lea     rax, [rsp+0F8h+arg_18]
0x18000b005  mov     [rsp+0F8h+var_D0], rax
0x18000b00a  lea     rax, [rsp+0F8h+var_A8]
0x18000b00f  mov     qword ptr [rsp+0F8h+var_D8], rax
0x18000b014  lea     rdx, qword_1800115C0
0x18000b01b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18000b020  jmp     short loc_18000B029
0x18000b022  lea     r15, aCmidi2schedule_5; "CMidi2SchedulerMidiTransform::QueueWork"...
0x18000b029  call    cs:__imp_GetCurrentProcess
0x18000b02f  mov     rcx, rax; hProcess
0x18000b032  mov     edx, 80h; dwPriorityClass
0x18000b037  call    cs:__imp_SetPriorityClass
0x18000b03d  call    cs:__imp_GetCurrentProcess
0x18000b043  mov     rcx, rax; hProcess
0x18000b046  mov     edx, 100h; dwPriorityClass
0x18000b04b  call    cs:__imp_SetPriorityClass
0x18000b051  call    cs:__imp_GetCurrentThread
0x18000b057  mov     rcx, rax; hThread
0x18000b05a  mov     edx, 0Fh; nPriority
0x18000b05f  call    cs:__imp_SetThreadPriority
0x18000b065  mov     r14, [rdi+70h]
0x18000b069  add     r14, 64h ; 'd'
0x18000b06d  mov     [rsp+0F8h+var_A0], r14
0x18000b072  xor     r13d, r13d
0x18000b075  lea     esi, [r13+1]
0x18000b079  mov     rax, [rdi+0F8h]
0x18000b080  test    rax, rax
0x18000b083  jz      short loc_18000B093
0x18000b085  mov     eax, [rax+4]
0x18000b088  nop
0x18000b089  test    sil, al
0x18000b08c  jz      short loc_18000B093
0x18000b08e  jmp     loc_18000B499
0x18000b093  cmp     [rdi+50h], r13
0x18000b097  jnz     short loc_18000B0E9
0x18000b099  mov     edx, 0EA60h
0x18000b09e  lea     rcx, [rdi+104h]; Address
0x18000b0a5  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x18000b0aa  mov     rax, [rdi+0F8h]
0x18000b0b1  test    rax, rax
0x18000b0b4  jz      short loc_18000B0BF
0x18000b0b6  mov     eax, [rax+4]
0x18000b0b9  nop
0x18000b0ba  test    sil, al
0x18000b0bd  jnz     short loc_18000B079
0x18000b0bf  mov     eax, [rdi+104h]
0x18000b0c5  test    eax, eax
0x18000b0c7  jz      short loc_18000B0D2
0x18000b0c9  mov     eax, r13d
0x18000b0cc  xchg    eax, [rdi+104h]
0x18000b0d2  mov     [rsp+0F8h+arg_8], r13
0x18000b0da  lea     rcx, [rsp+0F8h+arg_8]
0x18000b0e2  call    ??$sleep_for@_JU?$ratio@$00$0DOI@@std@@@this_thread@std@@YAXAEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@@Z; std::this_thread::sleep_for<__int64,std::ratio<1,1000>>(std::chrono::duration<__int64,std::ratio<1,1000>> const &)
0x18000b0e7  jmp     short loc_18000B079
0x18000b0e9  mov     rax, [rdi+0F8h]
0x18000b0f0  test    rax, rax
0x18000b0f3  jz      short loc_18000B0FE
0x18000b0f5  mov     eax, [rax+4]
0x18000b0f8  nop
0x18000b0f9  test    sil, al
0x18000b0fc  jnz     short loc_18000B0AA
0x18000b0fe  cmp     [rdi+50h], r13
0x18000b102  jz      short loc_18000B0AA
0x18000b104  mov     [rsp+0F8h+arg_8], r13
0x18000b10c  lea     rdx, [rsp+0F8h+arg_8]; unsigned __int64 *
0x18000b114  mov     rcx, rdi; this
0x18000b117  call    ?GetTopMessageTimestamp@CMidi2SchedulerMidiTransform@@AEAAJAEA_K@Z; CMidi2SchedulerMidiTransform::GetTopMessageTimestamp(unsigned __int64 &)
0x18000b11c  test    eax, eax
0x18000b11e  js      short loc_18000B0AA
0x18000b120  mov     rbx, [rsp+0F8h+arg_8]
0x18000b128  sub     rbx, r14
0x18000b12b  mov     qword ptr [rsp+0F8h+PerformanceCount], r13
0x18000b133  lea     rcx, [rsp+0F8h+PerformanceCount]; lpPerformanceCount
0x18000b13b  call    cs:__imp_QueryPerformanceCounter
0x18000b141  cmp     qword ptr [rsp+0F8h+PerformanceCount], rbx
0x18000b149  jb      loc_18000B434
0x18000b14f  lea     rbx, [rdi+88h]
0x18000b156  mov     [rsp+0F8h+arg_18], rbx
0x18000b15e  mov     rcx, rbx; _Mtx_t
0x18000b161  call    cs:__imp__Mtx_lock
0x18000b167  test    eax, eax
0x18000b169  jz      short loc_18000B176
0x18000b16b  mov     ecx, 5
0x18000b170  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000b176  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18000b17d  jnz     short loc_18000B192
0x18000b17f  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18000b186  mov     ecx, 6
0x18000b18b  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000b191  nop
0x18000b192  mov     r12d, r13d
0x18000b195  cmp     [rdi+50h], r13
0x18000b199  jz      loc_18000B421
0x18000b19f  mov     rax, [rdi+0F8h]
0x18000b1a6  test    rax, rax
0x18000b1a9  jz      short loc_18000B1B8
0x18000b1ab  mov     eax, [rax+4]
0x18000b1ae  nop
0x18000b1af  test    sil, al
0x18000b1b2  jnz     loc_18000B421
0x18000b1b8  cmp     r12d, 1F4h
0x18000b1bf  jnb     loc_18000B421
0x18000b1c5  mov     rcx, [rdi+40h]
0x18000b1c9  sub     rcx, rsi
0x18000b1cc  and     rcx, [rdi+48h]
0x18000b1d0  mov     rax, [rdi+38h]
0x18000b1d4  mov     r8, [rax+rcx*8]
0x18000b1d8  mov     rax, [r8]
0x18000b1db  cmp     rax, [rsp+0F8h+arg_8]
0x18000b1e3  ja      loc_18000B421
0x18000b1e9  mov     rcx, [rdi+0F8h]
0x18000b1f0  test    rcx, rcx
0x18000b1f3  jz      short loc_18000B201
0x18000b1f5  mov     eax, [rcx+4]
0x18000b1f8  nop
0x18000b1f9  test    sil, al
0x18000b1fc  jnz     short loc_18000B223
0x18000b1fe  mov     rax, [r8]
0x18000b201  mov     qword ptr [rsp+0F8h+var_D8], rax; int
0x18000b206  mov     r9d, [r8+0Ch]
0x18000b20a  mov     r8, [r8+10h]
0x18000b20e  xor     edx, edx
0x18000b210  mov     rcx, rdi
0x18000b213  call    ?SendMidiMessageNow@CMidi2SchedulerMidiTransform@@AEAAJW4__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004@@PEAXI_J@Z; CMidi2SchedulerMidiTransform::SendMidiMessageNow(__MIDL___MIDL_itf_windowsmidiservices_0000_0000_0004,void *,uint,__int64)
0x18000b218  mov     r14d, eax
0x18000b21b  test    eax, eax
0x18000b21d  js      loc_18000B37D
0x18000b223  lea     r14, [rdi+30h]
0x18000b227  mov     rdx, [r14+20h]
0x18000b22b  test    r14, r14
0x18000b22e  jz      short loc_18000B24B
0x18000b230  mov     rcx, [r14]
0x18000b233  mov     rax, rcx
0x18000b236  test    rcx, rcx
0x18000b239  jz      short loc_18000B24B
0x18000b23b  mov     rcx, [rcx]
0x18000b23e  mov     qword ptr [rsp+0F8h+PerformanceCount], rcx
0x18000b246  mov     r13, [rax]
0x18000b249  jmp     short loc_18000B253
0x18000b24b  mov     qword ptr [rsp+0F8h+PerformanceCount], r13
0x18000b253  cmp     rdx, 2
0x18000b257  jl      loc_18000B339
0x18000b25d  mov     r10, [r14+18h]
0x18000b261  mov     r11, [r14+28h]
0x18000b265  lea     r9, [rdx-1]
0x18000b269  add     r9, r10
0x18000b26c  mov     rcx, [r13+10h]
0x18000b270  sub     rcx, rsi
0x18000b273  and     rcx, r9
0x18000b276  mov     rax, [r13+8]
0x18000b27a  mov     r8, [rax+rcx*8]
0x18000b27e  mov     rax, [r8]
0x18000b281  mov     [rsp+0F8h+var_90], rax
0x18000b286  mov     eax, [r8+8]
0x18000b28a  mov     [rsp+0F8h+var_88], eax
0x18000b28e  mov     eax, [r8+0Ch]
0x18000b292  mov     [rsp+0F8h+var_84], eax
0x18000b296  mov     rdx, [r8+20h]
0x18000b29a  mov     qword ptr [r8+20h], 0
0x18000b2a2  mov     rcx, [r8+18h]
0x18000b2a6  mov     qword ptr [r8+18h], 0
0x18000b2ae  mov     rax, [r8+10h]
0x18000b2b2  mov     qword ptr [r8+10h], 0
0x18000b2ba  mov     [rsp+0F8h+var_80], rax
0x18000b2bf  mov     [rsp+0F8h+var_78], rcx
0x18000b2c7  mov     [rsp+0F8h+var_70], rdx
0x18000b2cf  mov     [rsp+0F8h+var_68], r13
0x18000b2d7  mov     [rsp+0F8h+var_60], r9
0x18000b2df  mov     [rsp+0F8h+var_58], r13
0x18000b2e7  mov     [rsp+0F8h+var_50], r9
0x18000b2ef  mov     rax, qword ptr [rsp+0F8h+PerformanceCount]
0x18000b2f7  mov     [rsp+0F8h+var_48], rax
0x18000b2ff  mov     [rsp+0F8h+var_40], r10
0x18000b307  mov     qword ptr [rsp+0F8h+var_D8], r11
0x18000b30c  lea     r9, [rsp+0F8h+var_90]
0x18000b311  lea     r8, [rsp+0F8h+var_68]
0x18000b319  lea     rdx, [rsp+0F8h+var_58]
0x18000b321  lea     rcx, [rsp+0F8h+var_48]
0x18000b329  call    ??$_Pop_heap_hole_unchecked@V?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@std@@UScheduledUmpMessage@@P6A_NAEAU3@0@Z@std@@YAXV?$_Deque_unchecked_iterator@V?$_Deque_val@U?$_Deque_simple_types@UScheduledUmpMessage@@@std@@@std@@@0@00$$QEAUScheduledUmpMessage@@P6A_NAEAU2@2@Z@Z; std::_Pop_heap_hole_unchecked<std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &)>(std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,std::_Deque_unchecked_iterator<std::_Deque_val<std::_Deque_simple_types<ScheduledUmpMessage>>>,ScheduledUmpMessage &&,bool (*)(ScheduledUmpMessage &,ScheduledUmpMessage &))
0x18000b32e  nop
0x18000b32f  lea     rcx, [rsp+0F8h+var_80]
0x18000b334  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000b339  mov     rcx, [r14+18h]
0x18000b33d  mov     rax, [r14+20h]
0x18000b341  dec     rax
0x18000b344  add     rcx, rax
0x18000b347  mov     rax, [r14+10h]
0x18000b34b  sub     rax, rsi
0x18000b34e  and     rcx, rax
0x18000b351  mov     rax, [r14+8]
0x18000b355  mov     rcx, [rax+rcx*8]
0x18000b359  add     rcx, 10h
0x18000b35d  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000b362  sub     qword ptr [r14+20h], 1
0x18000b367  jnz     short loc_18000B372
0x18000b369  xor     r13d, r13d
0x18000b36c  mov     [r14+18h], r13
0x18000b370  jmp     short loc_18000B375
0x18000b372  xor     r13d, r13d
0x18000b375  add     r12d, esi
0x18000b378  jmp     loc_18000B195
0x18000b37d  mov     rcx, [rsp+0F8h]; this
0x18000b385  mov     r9d, r14d; char *
0x18000b388  mov     edx, 2DEh; void *
0x18000b38d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000b392  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b397  mov     rcx, [rax+8]
0x18000b39b  mov     eax, [rcx]
0x18000b39d  cmp     eax, 2
0x18000b3a0  jbe     short loc_18000B421
0x18000b3a2  mov     dword ptr [rsp+0F8h+arg_8], r14d
0x18000b3aa  lea     rax, [rdi+10h]
0x18000b3ae  cmp     qword ptr [rdi+28h], 7
0x18000b3b3  jbe     short loc_18000B3B8
0x18000b3b5  mov     rax, [rax]
0x18000b3b8  mov     qword ptr [rsp+0F8h+PerformanceCount], rax
0x18000b3c0  lea     rax, aUnableToSendMe; "Unable to send message"
0x18000b3c7  mov     [rsp+0F8h+arg_18], rax
0x18000b3cf  mov     [rsp+0F8h+var_A8], rdi
0x18000b3d4  mov     [rsp+0F8h+var_98], r15
0x18000b3d9  lea     rax, [rsp+0F8h+arg_8]
0x18000b3e1  mov     [rsp+0F8h+var_B8], rax
0x18000b3e6  lea     rax, [rsp+0F8h+PerformanceCount]
0x18000b3ee  mov     [rsp+0F8h+var_C0], rax
0x18000b3f3  lea     rax, [rsp+0F8h+arg_18]
0x18000b3fb  mov     [rsp+0F8h+var_C8], rax
0x18000b400  lea     rax, [rsp+0F8h+var_A8]
0x18000b405  mov     [rsp+0F8h+var_D0], rax
0x18000b40a  lea     rax, [rsp+0F8h+var_98]
0x18000b40f  mov     qword ptr [rsp+0F8h+var_D8], rax
0x18000b414  lea     rdx, byte_18001155F
0x18000b41b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18000b420  nop
0x18000b421  mov     rcx, rbx; _Mtx_t
0x18000b424  call    cs:__imp__Mtx_unlock
0x18000b42a  mov     r14, [rsp+0F8h+var_A0]
0x18000b42f  jmp     loc_18000B0AA
0x18000b434  mov     dword ptr [rsp+0F8h+arg_8], r13d
0x18000b43c  mov     rax, [rdi+0F8h]
0x18000b443  test    rax, rax
0x18000b446  jz      short loc_18000B455
0x18000b448  mov     eax, [rax+4]
0x18000b44b  nop
0x18000b44c  test    sil, al
0x18000b44f  jnz     loc_18000B0AA
0x18000b455  lea     r8, [rsp+0F8h+arg_8]; unsigned int *
0x18000b45d  mov     rdx, rbx; unsigned __int64
0x18000b460  mov     rcx, rdi; this
0x18000b463  call    ?CalculateSafeSleepTime@CMidi2SchedulerMidiTransform@@AEAAJ_KAEAI@Z; CMidi2SchedulerMidiTransform::CalculateSafeSleepTime(unsigned __int64,uint &)
0x18000b468  test    eax, eax
0x18000b46a  js      loc_18000B0AA
0x18000b470  mov     edx, dword ptr [rsp+0F8h+arg_8]
0x18000b477  cmp     edx, 0Fh
0x18000b47a  jbe     loc_18000B0AA
0x18000b480  jmp     loc_18000B09E
0x18000b485  lea     r15, aCmidi2schedule_5; "CMidi2SchedulerMidiTransform::QueueWork"...
0x18000b48c  mov     esi, 1
0x18000b491  mov     rdi, [rsp+0F8h+arg_0]
0x18000b499  call    ?Instance@MidiSchedulerTransformTelemetryProvider@@KAPEAV1@XZ; MidiSchedulerTransformTelemetryProvider::Instance(void)
0x18000b49e  mov     rcx, [rax+8]
0x18000b4a2  mov     eax, [rcx]
0x18000b4a4  cmp     eax, 4
0x18000b4a7  jbe     short loc_18000B51E
0x18000b4a9  lea     rax, [rdi+10h]
0x18000b4ad  cmp     qword ptr [rax+18h], 7
0x18000b4b2  jbe     short loc_18000B4B7
0x18000b4b4  mov     rax, [rax]
0x18000b4b7  mov     [rsp+0F8h+arg_0], rax
0x18000b4bf  lea     rax, aExit; "Exit"
0x18000b4c6  mov     [rsp+0F8h+arg_8], rax
0x18000b4ce  mov     qword ptr [rsp+0F8h+PerformanceCount], rdi
  ... truncated ...
```
