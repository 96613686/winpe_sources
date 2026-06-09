# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Stop(void)

- ea: `0x1800345b0`
- end: `0x1800348e3`
- name: `?Stop@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJXZ`
- size: `819`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops`

## callees

- `0x1800019f0`
- `0x1800069a0`
- `0x18000cf44`
- `0x18000d13c`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`
- `0x180022c9c`
- `0x180025884`
- `0x1800345b0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034895`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034613`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034895`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18003484e`
- `api-ms-win-core-perfcounters-l1-1-0!PerfStopProvider` at `0x18003484e`

## string_xrefs

- `0x180034672`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x180034784`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x1800346d8`: `Stop SinkWriter processor`
- `0x18003478b`: `Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Stop`
- `0x180034792`: `SinkWriterProcessorStop`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Stop(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this)
{
  char v2; // bl
  bool v3; // di
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  const char *v10; // r9
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  _QWORD *v13; // rdi
  void *v14; // rcx
  bool v15; // di
  char v16; // al
  int v17; // r8d
  int v18; // edx
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-98h]
  int v21; // [rsp+20h] [rbp-98h]
  int v22; // [rsp+28h] [rbp-90h]
  int v23; // [rsp+28h] [rbp-90h]
  char *v24; // [rsp+30h] [rbp-88h]
  const char *v25; // [rsp+60h] [rbp-58h] BYREF
  int v26[2]; // [rsp+68h] [rbp-50h] BYREF
  _OWORD v27[4]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v29; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v30; // [rsp+C8h] [rbp+10h] BYREF
  const char *v31; // [rsp+D0h] [rbp+18h] BYREF
  int *v32; // [rsp+D8h] [rbp+20h] BYREF

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
      v20,
      v22,
      12,
      &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v20) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v20,
      (bool)"Processor is not started",
      v24);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v30 = *((_QWORD *)this + 9);
      v29 = *((_DWORD *)this + 20);
      v31 = "Stop SinkWriter processor";
      v32 = &xmmword_1800C21A0;
      v25 = "RdpAvenc";
      *(_QWORD *)v26 = 0x1000000;
      *(_QWORD *)&v27[0] = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AEEB6,
        v8,
        v9,
        (__int64)v27,
        (__int64)v26,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v29,
        (__int64)&v30);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"SinkWriterProcessorStop",
      "Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      0x65u);
    v11 = *((_QWORD *)this + 24);
    if ( v11 )
    {
      Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::RemoveSession(
        v11,
        *((_DWORD *)this + 20));
      v27[0] = 0;
      std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=((char *)this + 232, v27);
      v12 = (volatile signed __int32 *)*((_QWORD *)&v27[0] + 1);
      if ( *((_QWORD *)&v27[0] + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( !_InterlockedDecrement(v12 + 3) )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      v13 = (_QWORD *)*((_QWORD *)this + 24);
      *((_QWORD *)this + 24) = 0;
      if ( v13 )
      {
        std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(v13 + 9);
        std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(v13 + 7);
        v14 = (void *)v13[5];
        if ( v14 )
          PerfStopProvider(v14);
        operator delete(v13);
      }
    }
    *((_BYTE *)this + 176) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = GetCurrentThreadId();
      LOBYTE(v17) = v15;
      LOBYTE(v18) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v17,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v21,
        v23,
        13,
        &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
        v16);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x76,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800345b0  push    rbx
0x1800345b2  push    rsi
0x1800345b3  push    rdi
0x1800345b4  push    r12
0x1800345b6  push    r13
0x1800345b8  push    r14
0x1800345ba  push    r15
0x1800345bc  sub     rsp, 80h
0x1800345c3  mov     rsi, rcx
0x1800345c6  lea     r12, WPP_GLOBAL_Control
0x1800345cd  mov     rax, cs:WPP_GLOBAL_Control
0x1800345d4  mov     bl, 1
0x1800345d6  cmp     rax, r12
0x1800345d9  jz      short loc_1800345EB
0x1800345db  test    [rax+1Ch], bl
0x1800345de  jz      short loc_1800345EB
0x1800345e0  cmp     byte ptr [rax+19h], 4
0x1800345e4  jb      short loc_1800345EB
0x1800345e6  mov     dil, bl
0x1800345e9  jmp     short loc_1800345EE
0x1800345eb  xor     dil, dil
0x1800345ee  lea     r13, WPP_RECORDER_INITIALIZED
0x1800345f5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800345fc  setnz   r14b
0x180034600  test    dil, dil
0x180034603  jnz     short loc_180034613
0x180034605  test    r14b, r14b
0x180034608  jnz     short loc_180034613
0x18003460a  lea     r15, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x180034611  jmp     short loc_18003464A
0x180034613  call    cs:__imp_GetCurrentThreadId
0x180034619  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003461d  lea     r15, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x180034624  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x180034629  mov     word ptr [rsp+0B8h+var_88], 0Ch; char *
0x180034630  mov     rcx, cs:WPP_GLOBAL_Control
0x180034637  mov     r9, [rcx+28h]; int
0x18003463b  mov     r8b, r14b; int
0x18003463e  mov     dl, dil; int
0x180034641  mov     rcx, [rcx+10h]; int
0x180034645  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003464a  cmp     byte ptr [rsi+0B0h], 0
0x180034651  setz    al
0x180034654  mov     rcx, [rsp+0B8h]; this
0x18003465c  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180034663  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x180034668  mov     byte ptr [rsp+0B8h+var_98], al; int
0x18003466c  mov     r9d, 8000FFFFh; char *
0x180034672  lea     r8, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180034679  mov     edx, 5Ah ; 'Z'; void *
0x18003467e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180034683  mov     eax, cs:dword_1800C1058
0x180034689  cmp     eax, 4
0x18003468c  jbe     loc_18003477C
0x180034692  mov     rcx, cs:qword_1800C1070
0x180034699  mov     rax, cs:qword_1800C1068
0x1800346a0  mov     rdx, 470000000000h
0x1800346aa  test    rdx, rax
0x1800346ad  jz      loc_18003477C
0x1800346b3  mov     rax, rcx
0x1800346b6  and     rax, rdx
0x1800346b9  cmp     rax, rcx
0x1800346bc  jnz     loc_18003477C
0x1800346c2  mov     rax, [rsi+48h]
0x1800346c6  mov     [rsp+0B8h+arg_8], rax
0x1800346ce  mov     eax, [rsi+50h]
0x1800346d1  mov     [rsp+0B8h+arg_0], eax
0x1800346d8  lea     rax, aStopSinkwriter_0; "Stop SinkWriter processor"
0x1800346df  mov     [rsp+0B8h+arg_10], rax
0x1800346e7  lea     rax, xmmword_1800C21A0
0x1800346ee  mov     [rsp+0B8h+arg_18], rax
0x1800346f6  lea     rax, aRdpavenc; "RdpAvenc"
0x1800346fd  mov     [rsp+0B8h+var_58], rax
0x180034702  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x18003470b  lea     rax, aCheckpoint; "Checkpoint"
0x180034712  mov     qword ptr [rsp+0B8h+var_48], rax
0x180034717  lea     rax, [rsp+0B8h+arg_8]
0x18003471f  mov     [rsp+0B8h+var_68], rax
0x180034724  lea     rax, [rsp+0B8h+arg_0]
0x18003472c  mov     [rsp+0B8h+var_70], rax
0x180034731  lea     rax, [rsp+0B8h+arg_10]
0x180034739  mov     qword ptr [rsp+0B8h+var_78], rax
0x18003473e  lea     rax, [rsp+0B8h+arg_18]
0x180034746  mov     [rsp+0B8h+MessageGuid], rax
0x18003474b  lea     rax, [rsp+0B8h+var_58]
0x180034750  mov     [rsp+0B8h+var_88], rax
0x180034755  lea     rax, [rsp+0B8h+var_50]
0x18003475a  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x18003475f  lea     rax, [rsp+0B8h+var_48]
0x180034764  mov     qword ptr [rsp+0B8h+var_98], rax
0x180034769  lea     rdx, word_1800AEEB6
0x180034770  lea     rcx, dword_1800C1058
0x180034777  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003477c  mov     [rsp+0B8h+var_98], 65h ; 'e'; int
0x180034784  lea     r9, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003478b  lea     r8, aRdpAvencSinkwr_10; "Rdp::Avenc::SinkWriter::CSinkWriterProc"...
0x180034792  lea     rdx, aSinkwriterproc_0; "SinkWriterProcessorStop"
0x180034799  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800347a0  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x1800347a5  mov     rcx, [rsi+0C0h]
0x1800347ac  test    rcx, rcx
0x1800347af  jz      loc_180034861
0x1800347b5  mov     edx, [rsi+50h]
0x1800347b8  call    ?RemoveSession@?$CPerfMonLogger@$1?RDPPerfMonCountersGuid@@3U_GUID@@A@details@Perf@Utils@Rdp@@QEAAXI@Z; Rdp::Utils::Perf::details::CPerfMonLogger<&_GUID RDPPerfMonCountersGuid>::RemoveSession(uint)
0x1800347bd  xorps   xmm0, xmm0
0x1800347c0  movdqu  [rsp+0B8h+var_48], xmm0
0x1800347c6  lea     rcx, [rsi+0E8h]
0x1800347cd  lea     rdx, [rsp+0B8h+var_48]
0x1800347d2  call    ??4?$shared_ptr@VCPerfMonSession@Perf@Utils@Rdp@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession>::operator=(std::shared_ptr<Rdp::Utils::Perf::CPerfMonSession> &&)
0x1800347d7  mov     rdi, qword ptr [rsp+0B8h+var_48+8]
0x1800347dc  test    rdi, rdi
0x1800347df  jz      short loc_18003481C
0x1800347e1  or      r14d, 0FFFFFFFFh
0x1800347e5  mov     eax, r14d
0x1800347e8  lock xadd [rdi+8], eax
0x1800347ed  add     eax, r14d
0x1800347f0  jnz     short loc_18003481C
0x1800347f2  mov     rax, [rdi]
0x1800347f5  mov     rcx, rdi
0x1800347f8  mov     rax, [rax]
0x1800347fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034800  mov     eax, r14d
0x180034803  lock xadd [rdi+0Ch], eax
0x180034808  add     eax, r14d
0x18003480b  jnz     short loc_18003481C
0x18003480d  mov     rax, [rdi]
0x180034810  mov     rcx, rdi
0x180034813  mov     rax, [rax+8]
0x180034817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003481c  mov     rdi, [rsi+0C0h]
0x180034823  mov     qword ptr [rsi+0C0h], 0
0x18003482e  test    rdi, rdi
0x180034831  jz      short loc_180034861
0x180034833  lea     rcx, [rdi+48h]
0x180034837  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@QEAXV?$shared_ptr@VCSharedFence@Graphics@Utils@Rdp@@@std@@@std@@@std@@@std@@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedFence>>>>>>>(void)
0x18003483c  lea     rcx, [rdi+38h]
0x180034840  call    ??1?$list@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@V?$allocator@U?$pair@QEAXV?$shared_ptr@VCSharedTexture@Graphics@Utils@Rdp@@@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>::~list<std::pair<void * const,std::shared_ptr<Rdp::Utils::Graphics::CSharedTexture>>>(void)
0x180034845  mov     rcx, [rdi+28h]; ProviderHandle
0x180034849  test    rcx, rcx
0x18003484c  jz      short loc_180034854
0x18003484e  call    cs:__imp_PerfStopProvider
0x180034854  mov     edx, 0C0h
0x180034859  mov     rcx, rdi; Block
0x18003485c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180034861  mov     byte ptr [rsi+0B0h], 0
0x180034868  mov     rax, cs:WPP_GLOBAL_Control
0x18003486f  cmp     rax, r12
0x180034872  jz      short loc_18003487F
0x180034874  test    [rax+1Ch], bl
0x180034877  jz      short loc_18003487F
0x180034879  cmp     byte ptr [rax+19h], 4
0x18003487d  jnb     short loc_180034881
0x18003487f  xor     bl, bl
0x180034881  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x180034888  setnz   dil
0x18003488c  test    bl, bl
0x18003488e  jnz     short loc_180034895
0x180034890  test    dil, dil
0x180034893  jz      short loc_1800348C4
0x180034895  call    cs:__imp_GetCurrentThreadId
0x18003489b  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003489f  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x1800348a4  mov     word ptr [rsp+0B8h+var_88], 0Dh; __int16
0x1800348ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800348b2  mov     r9, [rcx+28h]; int
0x1800348b6  mov     r8b, dil; int
0x1800348b9  mov     dl, bl; int
0x1800348bb  mov     rcx, [rcx+10h]; int
0x1800348bf  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800348c4  xor     eax, eax
0x1800348c6  jmp     short loc_1800348CF
0x1800348c8  mov     eax, [rsp+0B8h+arg_0]
0x1800348cf  add     rsp, 80h
0x1800348d6  pop     r15
0x1800348d8  pop     r14
0x1800348da  pop     r13
0x1800348dc  pop     r12
0x1800348de  pop     rdi
0x1800348df  pop     rsi
0x1800348e0  pop     rbx
0x1800348e1  retn
```
