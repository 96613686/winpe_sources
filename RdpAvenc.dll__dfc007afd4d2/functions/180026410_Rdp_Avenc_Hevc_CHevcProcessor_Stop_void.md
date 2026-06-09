# Rdp::Avenc::Hevc::CHevcProcessor::Stop(void)

- ea: `0x180026410`
- end: `0x18002681b`
- name: `?Stop@CHevcProcessor@Hevc@Avenc@Rdp@@UEAAJXZ`
- size: `1035`
- prototype: `__int64 __fastcall(Rdp::Avenc::Hevc::CHevcProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops`

## callees

- `0x1800019f0`
- `0x1800069a0`
- `0x18000cf44`
- `0x18000d13c`
- `0x1800103c0`
- `0x180010bc8`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`
- `0x180022c9c`
- `0x180025884`
- `0x180026410`
- `0x180026af8`
- `0x180026f90`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026643`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180026643`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800267b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026473`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800267b2`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180026763`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x180026763`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180026650`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180026650`
- `MFPlat!MFUnregisterPlatformFromMMCSS` at `0x180026668`
- `MFPlat!MFUnregisterPlatformFromMMCSS` at `0x180026668`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Hevc::CHevcProcessor::Stop(Rdp::Avenc::Hevc::CHevcProcessor *this)
{
  char v2; // si
  bool v3; // di
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  HRESULT v11; // eax
  wil::details::in1diag3 *v12; // rcx
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rdi
  _QWORD *v17; // rdi
  void *v18; // rcx
  bool v19; // bl
  char v20; // al
  int v21; // r8d
  int v22; // edx
  __int64 result; // rax
  int v24; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+20h] [rbp-98h]
  int v26; // [rsp+28h] [rbp-90h]
  int v27; // [rsp+28h] [rbp-90h]
  char *v28; // [rsp+30h] [rbp-88h]
  const char *v29; // [rsp+60h] [rbp-58h] BYREF
  int v30[2]; // [rsp+68h] [rbp-50h] BYREF
  _OWORD v31[4]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v33; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v34; // [rsp+C8h] [rbp+10h] BYREF
  const char *v35; // [rsp+D0h] [rbp+18h] BYREF
  int *v36; // [rsp+D8h] [rbp+20h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v4 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v6) = v4;
    LOBYTE(v7) = v3;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      v6,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v24,
      v26,
      12,
      &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v24) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v24,
      (bool)"Processor is not started",
      v28);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v34 = *((_QWORD *)this + 9);
      v33 = *((_DWORD *)this + 20);
      v35 = "Stop Hevc processor";
      v36 = &xmmword_1800C21A0;
      v29 = "RdpAvenc";
      *(_QWORD *)v30 = 0x1000000;
      *(_QWORD *)&v31[0] = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800ADEAB,
        v8,
        v9,
        (__int64)v31,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v33,
        (__int64)&v34);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"HevcProcessorStop",
      "Rdp::Avenc::Hevc::CHevcProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
      0x81u);
    if ( (unsigned int)mtx_do_lock((char *)this + 288) )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)this + 91) == 0x7FFFFFFF )
    {
      *((_DWORD *)this + 91) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    *((_BYTE *)this + 440) = 0;
    if ( (*((_DWORD *)this + 91))-- == 1 )
    {
      *((_DWORD *)this + 90) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)this + 38);
    }
    WakeAllConditionVariable((PCONDITION_VARIABLE)this + 47);
    if ( *((_DWORD *)this + 70) )
      std::thread::join((Rdp::Avenc::Hevc::CHevcProcessor *)((char *)this + 272));
    v11 = MFUnregisterPlatformFromMMCSS();
    v12 = retaddr;
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x88,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)(unsigned int)v11,
        v25);
    v13 = (*(__int64 (__fastcall **)(wil::details::in1diag3 *))(*((_QWORD *)this + 31) + 8LL))(v12);
    if ( v13 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x8A,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
        (const char *)(unsigned int)v13,
        v25);
    v15 = *((_QWORD *)this + 24);
    if ( v15 )
    {
      Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::RemoveSession(
        v15,
        *((_DWORD *)this + 20));
      v31[0] = 0;
      std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=((char *)this + 232, v31);
      v16 = (volatile signed __int32 *)*((_QWORD *)&v31[0] + 1);
      if ( *((_QWORD *)&v31[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v31[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
          if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
        }
      }
      v17 = (_QWORD *)*((_QWORD *)this + 24);
      *((_QWORD *)this + 24) = 0;
      if ( v17 )
      {
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(v17 + 9);
        std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(v17 + 7);
        v18 = (void *)v17[5];
        if ( v18 )
          PerfStopProvider(v18);
        operator delete(v17);
      }
    }
    *((_BYTE *)this + 176) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v19 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v20 = GetCurrentThreadId();
      LOBYTE(v21) = v19;
      LOBYTE(v22) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        v21,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v25,
        v27,
        13,
        &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
        v20);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9B,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x180026410  push    rbx
0x180026412  push    rsi
0x180026413  push    rdi
0x180026414  push    r13
0x180026416  push    r14
0x180026418  push    r15
0x18002641a  sub     rsp, 88h
0x180026421  mov     rbx, rcx
0x180026424  lea     r13, WPP_GLOBAL_Control
0x18002642b  mov     rax, cs:WPP_GLOBAL_Control
0x180026432  mov     sil, 1
0x180026435  cmp     rax, r13
0x180026438  jz      short loc_18002644B
0x18002643a  test    [rax+1Ch], sil
0x18002643e  jz      short loc_18002644B
0x180026440  cmp     byte ptr [rax+19h], 4
0x180026444  jb      short loc_18002644B
0x180026446  mov     dil, sil
0x180026449  jmp     short loc_18002644E
0x18002644b  xor     dil, dil
0x18002644e  lea     rax, WPP_RECORDER_INITIALIZED
0x180026455  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002645c  setnz   r14b
0x180026460  test    dil, dil
0x180026463  jnz     short loc_180026473
0x180026465  test    r14b, r14b
0x180026468  jnz     short loc_180026473
0x18002646a  lea     r15, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x180026471  jmp     short loc_1800264AA
0x180026473  call    cs:__imp_GetCurrentThreadId
0x180026479  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18002647d  lea     r15, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x180026484  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180026489  mov     word ptr [rsp+0B8h+var_88], 0Ch; char *
0x180026490  mov     rcx, cs:WPP_GLOBAL_Control
0x180026497  mov     r9, [rcx+28h]; int
0x18002649b  mov     r8b, r14b; int
0x18002649e  mov     dl, dil; int
0x1800264a1  mov     rcx, [rcx+10h]; int
0x1800264a5  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800264aa  cmp     byte ptr [rbx+0B0h], 0
0x1800264b1  setz    al
0x1800264b4  mov     rcx, [rsp+0B8h]; this
0x1800264bc  lea     rdx, aProcessorIsNot; "Processor is not started"
0x1800264c3  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x1800264c8  mov     byte ptr [rsp+0B8h+var_98], al; int
0x1800264cc  mov     r9d, 8000FFFFh; char *
0x1800264d2  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800264d9  mov     edx, 76h ; 'v'; void *
0x1800264de  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800264e3  mov     eax, cs:dword_1800C1058
0x1800264e9  cmp     eax, 4
0x1800264ec  jbe     loc_1800265DC
0x1800264f2  mov     rcx, cs:qword_1800C1070
0x1800264f9  mov     rax, cs:qword_1800C1068
0x180026500  mov     rdx, 470000000000h
0x18002650a  test    rdx, rax
0x18002650d  jz      loc_1800265DC
0x180026513  mov     rax, rcx
0x180026516  and     rax, rdx
0x180026519  cmp     rax, rcx
0x18002651c  jnz     loc_1800265DC
0x180026522  mov     rax, [rbx+48h]
0x180026526  mov     [rsp+0B8h+arg_8], rax
0x18002652e  mov     eax, [rbx+50h]
0x180026531  mov     [rsp+0B8h+arg_0], eax
0x180026538  lea     rax, aStopHevcProces; "Stop Hevc processor"
0x18002653f  mov     [rsp+0B8h+arg_10], rax
0x180026547  lea     rax, xmmword_1800C21A0
0x18002654e  mov     [rsp+0B8h+arg_18], rax
0x180026556  lea     rax, aRdpavenc; "RdpAvenc"
0x18002655d  mov     [rsp+0B8h+var_58], rax
0x180026562  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x18002656b  lea     rax, aCheckpoint; "Checkpoint"
0x180026572  mov     qword ptr [rsp+0B8h+var_48], rax
0x180026577  lea     rax, [rsp+0B8h+arg_8]
0x18002657f  mov     [rsp+0B8h+var_68], rax
0x180026584  lea     rax, [rsp+0B8h+arg_0]
0x18002658c  mov     [rsp+0B8h+var_70], rax
0x180026591  lea     rax, [rsp+0B8h+arg_10]
0x180026599  mov     qword ptr [rsp+0B8h+var_78], rax
0x18002659e  lea     rax, [rsp+0B8h+arg_18]
0x1800265a6  mov     [rsp+0B8h+MessageGuid], rax
0x1800265ab  lea     rax, [rsp+0B8h+var_58]
0x1800265b0  mov     [rsp+0B8h+var_88], rax
0x1800265b5  lea     rax, [rsp+0B8h+var_50]
0x1800265ba  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x1800265bf  lea     rax, [rsp+0B8h+var_48]
0x1800265c4  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800265c9  lea     rdx, byte_1800ADEAB
0x1800265d0  lea     rcx, dword_1800C1058
0x1800265d7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800265dc  mov     [rsp+0B8h+var_98], 81h; int
0x1800265e4  lea     r9, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800265eb  lea     r8, aRdpAvencHevcCh_9; "Rdp::Avenc::Hevc::CHevcProcessor::Stop"
0x1800265f2  lea     rdx, aHevcprocessors_0; "HevcProcessorStop"
0x1800265f9  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180026600  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180026605  lea     rdi, [rbx+120h]
0x18002660c  mov     rcx, rdi
0x18002660f  call    mtx_do_lock
0x180026614  test    eax, eax
0x180026616  jnz     loc_1800267FE
0x18002661c  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180026623  jz      loc_180026808
0x180026629  xor     eax, eax
0x18002662b  xchg    al, [rbx+1B8h]
0x180026631  or      r14d, 0FFFFFFFFh
0x180026635  add     [rdi+4Ch], r14d
0x180026639  jnz     short loc_180026649
0x18002663b  mov     [rdi+48h], r14d
0x18002663f  lea     rcx, [rdi+10h]; SRWLock
0x180026643  call    cs:__imp_ReleaseSRWLockExclusive
0x180026649  lea     rcx, [rbx+178h]; ConditionVariable
0x180026650  call    cs:__imp_WakeAllConditionVariable
0x180026656  lea     rcx, [rbx+110h]; this
0x18002665d  cmp     dword ptr [rcx+8], 0
0x180026661  jz      short loc_180026668
0x180026663  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x180026668  call    cs:__imp_MFUnregisterPlatformFromMMCSS
0x18002666e  mov     rcx, [rsp+0B8h]; this
0x180026676  test    eax, eax
0x180026678  jns     short loc_18002668E
0x18002667a  mov     r9d, eax; char *
0x18002667d  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180026684  mov     edx, 88h; void *
0x180026689  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18002668e  mov     rax, [rbx+0F8h]
0x180026695  mov     rax, [rax+8]
0x180026699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002669e  mov     rcx, [rsp+0B8h]; this
0x1800266a6  test    eax, eax
0x1800266a8  jns     short loc_1800266BE
0x1800266aa  mov     r9d, eax; char *
0x1800266ad  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800266b4  mov     edx, 8Ah; void *
0x1800266b9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800266be  mov     rcx, [rbx+0C0h]
0x1800266c5  test    rcx, rcx
0x1800266c8  jz      loc_180026776
0x1800266ce  mov     edx, [rbx+50h]
0x1800266d1  call    ?RemoveSession@?$CPerfMonLogger@$1?RDPPerfMonCountersGuid@@3U_GUID@@A@details@Perf@Utils@Rdp@@QEAAXI@Z; Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::RemoveSession(uint)
0x1800266d6  xorps   xmm0, xmm0
0x1800266d9  movdqu  [rsp+0B8h+var_48], xmm0
0x1800266df  lea     rcx, [rbx+0E8h]
0x1800266e6  lea     rdx, [rsp+0B8h+var_48]
0x1800266eb  call    ??4?$shared_ptr@VCPerfMonSession@Perf@Utils@Rdp@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=(std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession> &&)
0x1800266f0  mov     rdi, qword ptr [rsp+0B8h+var_48+8]
0x1800266f5  test    rdi, rdi
0x1800266f8  jz      short loc_180026731
0x1800266fa  mov     eax, r14d
0x1800266fd  lock xadd [rdi+8], eax
0x180026702  add     eax, r14d
0x180026705  jnz     short loc_180026731
0x180026707  mov     rax, [rdi]
0x18002670a  mov     rcx, rdi
0x18002670d  mov     rax, [rax]
0x180026710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026715  mov     eax, r14d
0x180026718  lock xadd [rdi+0Ch], eax
0x18002671d  add     eax, r14d
0x180026720  jnz     short loc_180026731
0x180026722  mov     rax, [rdi]
0x180026725  mov     rcx, rdi
0x180026728  mov     rax, [rax+8]
0x18002672c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026731  mov     rdi, [rbx+0C0h]
0x180026738  mov     qword ptr [rbx+0C0h], 0
0x180026743  test    rdi, rdi
0x180026746  jz      short loc_180026776
0x180026748  lea     rcx, [rdi+48h]
0x18002674c  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VCSharedFence@Graphics@Utils@Rdp@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(void)
0x180026751  lea     rcx, [rdi+38h]
0x180026755  call    ??1?$list@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(void)
0x18002675a  mov     rcx, [rdi+28h]; ProviderHandle
0x18002675e  test    rcx, rcx
0x180026761  jz      short loc_180026769
0x180026763  call    cs:__imp_PerfStopProvider
0x180026769  mov     edx, 0C0h
0x18002676e  mov     rcx, rdi; Block
0x180026771  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026776  mov     byte ptr [rbx+0B0h], 0
0x18002677d  mov     rax, cs:WPP_GLOBAL_Control
0x180026784  cmp     rax, r13
0x180026787  jz      short loc_180026795
0x180026789  test    [rax+1Ch], sil
0x18002678d  jz      short loc_180026795
0x18002678f  cmp     byte ptr [rax+19h], 4
0x180026793  jnb     short loc_180026798
0x180026795  xor     sil, sil
0x180026798  lea     rax, WPP_RECORDER_INITIALIZED
0x18002679f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800267a6  setnz   bl
0x1800267a9  test    sil, sil
0x1800267ac  jnz     short loc_1800267B2
0x1800267ae  test    bl, bl
0x1800267b0  jz      short loc_1800267E2
0x1800267b2  call    cs:__imp_GetCurrentThreadId
0x1800267b8  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x1800267bc  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x1800267c1  mov     word ptr [rsp+0B8h+var_88], 0Dh; __int16
0x1800267c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800267cf  mov     r9, [rcx+28h]; int
0x1800267d3  mov     r8b, bl; int
0x1800267d6  mov     dl, sil; int
0x1800267d9  mov     rcx, [rcx+10h]; int
0x1800267dd  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800267e2  xor     eax, eax
0x1800267e4  jmp     short loc_1800267ED
0x1800267e6  mov     eax, [rsp+0B8h+arg_0]
0x1800267ed  add     rsp, 88h
0x1800267f4  pop     r15
0x1800267f6  pop     r14
0x1800267f8  pop     r13
0x1800267fa  pop     rdi
0x1800267fb  pop     rsi
0x1800267fc  pop     rbx
0x1800267fd  retn
0x1800267fe  mov     ecx, 5; int
0x180026803  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180026808  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x18002680f  mov     ecx, 6; int
0x180026814  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
