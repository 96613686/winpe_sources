# Rdp::Avenc::Hevc::CHevcFrameProcessor::Start(void)

- ea: `0x18002cb80`
- end: `0x18002d1b3`
- name: `?Start@CHevcFrameProcessor@Hevc@Avenc@Rdp@@UEAAJXZ`
- size: `1587`
- prototype: `__int64 __fastcall(Rdp::Avenc::Hevc::CHevcFrameProcessor *this, __int64, int, int)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028f70`

## callees

- `0x180002b38`
- `0x180003604`
- `0x1800065a4`
- `0x18000ec04`
- `0x18001143c`
- `0x180011490`
- `0x1800152c4`
- `0x180015480`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x180028840`
- `0x18002aa1c`
- `0x18002aac0`
- `0x18002b904`
- `0x18002cb80`
- `0x18002dd40`
- `0x18002e0c4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cbdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d10f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002cbdd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002d10f`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002cfb5`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18002cfb5`

## string_xrefs

- `0x18002d1a0`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18002d02c`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18002d015`: `Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Hevc::CHevcFrameProcessor::Start(
        Rdp::Avenc::Hevc::CHevcFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // r14
  bool v6; // bl
  bool v7; // di
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  const struct _tlgProvider_t *v12; // rax
  int v13; // r8d
  int v14; // r9d
  const char **v15; // r15
  __int64 v16; // rax
  __int64 v17; // r12
  unsigned int v18; // r13d
  char *v19; // rdi
  volatile signed __int32 *v20; // rbx
  int v21; // eax
  __int64 v22; // rbx
  volatile signed __int32 *v23; // rbx
  __int64 v24; // rax
  const char *v25; // r9
  volatile signed __int32 *v26; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v27; // r15
  _DWORD *v28; // rax
  int v29; // r13d
  _DWORD *v30; // r12
  __int64 v31; // r8
  int v32; // edx
  unsigned int v33; // edx
  bool v34; // si
  char v35; // al
  int v36; // r8d
  int v37; // edx
  __int64 result; // rax
  int v39; // [rsp+20h] [rbp-A8h]
  int v40; // [rsp+20h] [rbp-A8h]
  int v41; // [rsp+28h] [rbp-A0h]
  const char *v42; // [rsp+28h] [rbp-A0h]
  int *v43; // [rsp+60h] [rbp-68h] BYREF
  const char *v44; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v45[2]; // [rsp+70h] [rbp-58h] BYREF
  const char *v46; // [rsp+80h] [rbp-48h] BYREF
  __int64 v47; // [rsp+88h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  char *v49; // [rsp+D8h] [rbp+10h] BYREF
  const char *v50; // [rsp+E0h] [rbp+18h] BYREF
  const char *v51; // [rsp+E8h] [rbp+20h] BYREF

  v5 = 1;
  v6 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v7 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v9) = v7;
    LOBYTE(v10) = v6;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      v9,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v39,
      v41,
      10,
      &WPP_bc0801f283643948a642b8834c5cca7a_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *((_QWORD *)this + 7);
    LODWORD(v49) = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v50 = (const char *)(v11 + 120);
    v51 = "Start Hevc frame processor";
    v43 = &xmmword_1800C21A0;
    v44 = "RdpAvenc";
    v45[0] = 0x1000000;
    v46 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)word_1800AE83A,
      a3,
      a4,
      (__int64)&v46,
      (__int64)v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v49);
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"HevcFrameProcessorStart",
      "Rdp::Avenc::Hevc::CHevcFrameProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
      0x3Eu);
    v12 = RdpGrfxPipelinePerfProvider::Provider();
    if ( *(_DWORD *)v12 > 5u )
    {
      v49 = (char *)this - 80;
      v50 = "Start";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        (_DWORD)v12,
        (unsigned int)byte_1800AE80D,
        v13,
        v14,
        (__int64)&v50,
        (__int64)&v49);
    }
    v15 = (const char **)(*(_QWORD *)(*((_QWORD *)this + 7) + 112LL) + 288LL);
    v42 = "Graphics file I/O channel is not available";
    v40 = (int)v15;
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      70,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
      2147500035LL);
    v16 = *((_QWORD *)this + 7);
    v17 = v16 + 176;
    v18 = *(_DWORD *)(v16 + 152);
    LODWORD(v49) = *(_DWORD *)(v16 + 148);
    v19 = (char *)operator new(0xD0u);
    v50 = v19;
    *((_DWORD *)v19 + 2) = 1;
    *((_DWORD *)v19 + 3) = 1;
    *(_QWORD *)v19 = &std::_Ref_count_obj2<Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>>::`vftable';
    Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>::CBitRateController<Rdp::Avenc::H265_420_Profile>(
      v19 + 16,
      (unsigned int)v49,
      v18,
      v17);
    *((_QWORD *)this + 8) = v19 + 16;
    v20 = (volatile signed __int32 *)*((_QWORD *)this + 9);
    *((_QWORD *)this + 9) = v19;
    if ( v20 )
    {
      if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    v49 = 0;
    v21 = (**((__int64 (__fastcall ***)(char *, GUID *, char **))this - 10))(
            (char *)this - 80,
            &GUID_a06bc936_6fd4_47ff_9fc7_68fe54155cab,
            &v49);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v21,
        (int)v15);
    v50 = v49;
    v51 = *v15;
    v22 = std::make_shared<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel1 *,Rdp::Avenc::IIoPacketCompleteEvents *>(
            v45,
            &v51,
            &v50);
    v46 = *(const char **)v22;
    v47 = *(_QWORD *)(v22 + 8);
    *(_QWORD *)v22 = 0;
    *(_QWORD *)(v22 + 8) = 0;
    std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(
      (char *)this + 32,
      &v46);
    v23 = *(volatile signed __int32 **)(v22 + 8);
    if ( v23 )
    {
      if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
        if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
      }
    }
    if ( v49 )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v49 + 16LL))(v49);
    v24 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)this + 40);
    v26 = (volatile signed __int32 *)v24;
    v27 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)this + 4);
    v46 = (const char *)v27;
    v47 = v24;
    if ( v24 )
      _InterlockedAdd((volatile signed __int32 *)(v24 + 8), 1u);
    if ( (_InterlockedExchange64((volatile __int64 *)this + 5, v24) & 3) == 2 )
      WakeByAddressAll((char *)this + 40);
    if ( v27 )
    {
      Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v27, 0x1000u, 0, 0);
      v28 = (_DWORD *)*((_QWORD *)this + 7);
      v29 = v28[38];
      LODWORD(v50) = v28[37];
      LODWORD(v49) = v28[34];
      v30 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v27, 0xFu);
      wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
        retaddr,
        266,
        "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
        2147942414LL);
      *v30 = 9;
      v30[1] = 15;
      *((_WORD *)v30 + 4) = (_WORD)v49;
      *((_WORD *)v30 + 5) = (_WORD)v50;
      *((_WORD *)v30 + 6) = v29;
      *((_BYTE *)v30 + 14) = 33;
      v31 = *((_QWORD *)this + 7);
      Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::MapSurfaceToScaledOutput(
        (_DWORD)v27,
        v32,
        *(_DWORD *)(v31 + 136),
        *(_DWORD *)(*(_QWORD *)(v31 + 112) + 164LL),
        *(_DWORD *)(*(_QWORD *)(v31 + 112) + 168LL),
        *(_DWORD *)(v31 + 140),
        *(_DWORD *)(v31 + 144),
        *(_DWORD *)(v31 + 148),
        *(_DWORD *)(v31 + 152));
      Rdp::Avenc::CFcWireEncoder::Flush(v27, v33);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v34 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v35 = GetCurrentThreadId();
      LOBYTE(v36) = v34;
      LOBYTE(v37) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v37,
        v36,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v40,
        (int)v42,
        11,
        &WPP_bc0801f283643948a642b8834c5cca7a_Traceguids,
        v35);
    }
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x76,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcframeprocessor.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x18002cb80  push    rbx
0x18002cb82  push    rsi
0x18002cb83  push    rdi
0x18002cb84  push    r12
0x18002cb86  push    r13
0x18002cb88  push    r14
0x18002cb8a  push    r15
0x18002cb8c  sub     rsp, 90h
0x18002cb93  mov     rsi, rcx
0x18002cb96  lea     rcx, WPP_GLOBAL_Control
0x18002cb9d  mov     rax, cs:WPP_GLOBAL_Control
0x18002cba4  mov     r14d, 1
0x18002cbaa  cmp     rax, rcx
0x18002cbad  jz      short loc_18002CBC0
0x18002cbaf  test    [rax+1Ch], r14b
0x18002cbb3  jz      short loc_18002CBC0
0x18002cbb5  cmp     byte ptr [rax+19h], 4
0x18002cbb9  jb      short loc_18002CBC0
0x18002cbbb  mov     bl, r14b
0x18002cbbe  jmp     short loc_18002CBC2
0x18002cbc0  xor     bl, bl
0x18002cbc2  lea     rax, WPP_RECORDER_INITIALIZED
0x18002cbc9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002cbd0  setnz   dil
0x18002cbd4  test    bl, bl
0x18002cbd6  jnz     short loc_18002CBDD
0x18002cbd8  test    dil, dil
0x18002cbdb  jz      short loc_18002CC13
0x18002cbdd  call    cs:__imp_GetCurrentThreadId
0x18002cbe3  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18002cbe7  lea     r15, WPP_bc0801f283643948a642b8834c5cca7a_Traceguids
0x18002cbee  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x18002cbf3  mov     [rsp+0C8h+var_98], 0Ah; __int16
0x18002cbfa  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cc01  mov     r9, [rcx+28h]; int
0x18002cc05  mov     r8b, dil; int
0x18002cc08  mov     dl, bl; int
0x18002cc0a  mov     rcx, [rcx+10h]; int
0x18002cc0e  call    WPP_RECORDER_AND_TRACE_SF_D
0x18002cc13  mov     eax, cs:dword_1800C1058
0x18002cc19  cmp     eax, 4
0x18002cc1c  jbe     loc_18002CD17
0x18002cc22  mov     rcx, cs:qword_1800C1070
0x18002cc29  mov     rax, cs:qword_1800C1068
0x18002cc30  mov     rdx, 470000000000h
0x18002cc3a  test    rdx, rax
0x18002cc3d  jz      loc_18002CD17
0x18002cc43  mov     rax, rcx
0x18002cc46  and     rax, rdx
0x18002cc49  cmp     rax, rcx
0x18002cc4c  jnz     loc_18002CD17
0x18002cc52  mov     rdx, [rsi+38h]
0x18002cc56  mov     rax, [rdx+70h]
0x18002cc5a  mov     ecx, [rax+0A0h]
0x18002cc60  mov     dword ptr [rsp+0C8h+arg_8], ecx
0x18002cc67  lea     rax, [rdx+78h]
0x18002cc6b  mov     [rsp+0C8h+arg_10], rax
0x18002cc73  lea     rax, aStartHevcFrame; "Start Hevc frame processor"
0x18002cc7a  mov     [rsp+0C8h+arg_18], rax
0x18002cc82  lea     rax, xmmword_1800C21A0
0x18002cc89  mov     [rsp+0C8h+var_68], rax
0x18002cc8e  lea     rax, aRdpavenc; "RdpAvenc"
0x18002cc95  mov     [rsp+0C8h+var_60], rax
0x18002cc9a  mov     [rsp+0C8h+var_58], 1000000h
0x18002cca3  lea     rax, aCheckpoint; "Checkpoint"
0x18002ccaa  mov     [rsp+0C8h+var_48], rax
0x18002ccb2  lea     rax, [rsp+0C8h+arg_8]
0x18002ccba  mov     [rsp+0C8h+var_78], rax
0x18002ccbf  lea     rax, [rsp+0C8h+arg_10]
0x18002ccc7  mov     [rsp+0C8h+var_80], rax
0x18002cccc  lea     rax, [rsp+0C8h+arg_18]
0x18002ccd4  mov     qword ptr [rsp+0C8h+var_88], rax
0x18002ccd9  lea     rax, [rsp+0C8h+var_68]
0x18002ccde  mov     [rsp+0C8h+MessageGuid], rax
0x18002cce3  lea     rax, [rsp+0C8h+var_60]
0x18002cce8  mov     qword ptr [rsp+0C8h+var_98], rax
0x18002cced  lea     rax, [rsp+0C8h+var_58]
0x18002ccf2  mov     qword ptr [rsp+0C8h+var_A0], rax
0x18002ccf7  lea     rax, [rsp+0C8h+var_48]
0x18002ccff  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18002cd04  lea     rdx, word_1800AE83A
0x18002cd0b  lea     rcx, dword_1800C1058
0x18002cd12  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18002cd17  mov     [rsp+0C8h+var_A8], 3Eh ; '>'; unsigned int
0x18002cd1f  lea     r9, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002cd26  lea     r8, aRdpAvencHevcCh_6; "Rdp::Avenc::Hevc::CHevcFrameProcessor::"...
0x18002cd2d  lea     rdx, aHevcframeproce; "HevcFrameProcessorStart"
0x18002cd34  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18002cd3b  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18002cd40  call    ?Provider@RdpGrfxPipelinePerfProvider@@SAPEBU_tlgProvider_t@@XZ; RdpGrfxPipelinePerfProvider::Provider(void)
0x18002cd45  mov     ecx, [rax]
0x18002cd47  cmp     ecx, 5
0x18002cd4a  jbe     short loc_18002CD90
0x18002cd4c  lea     rcx, [rsi-50h]
0x18002cd50  mov     [rsp+0C8h+arg_8], rcx
0x18002cd58  lea     rcx, aStart; "Start"
0x18002cd5f  mov     [rsp+0C8h+arg_10], rcx
0x18002cd67  lea     rcx, [rsp+0C8h+arg_8]
0x18002cd6f  mov     qword ptr [rsp+0C8h+var_A0], rcx
0x18002cd74  lea     rcx, [rsp+0C8h+arg_10]
0x18002cd7c  mov     qword ptr [rsp+0C8h+var_A8], rcx
0x18002cd81  lea     rdx, byte_1800AE80D
0x18002cd88  mov     rcx, rax
0x18002cd8b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x18002cd90  mov     rax, [rsi+38h]
0x18002cd94  mov     r15, [rax+70h]
0x18002cd98  add     r15, 120h
0x18002cd9f  mov     rcx, [rsp+0C8h]
0x18002cda7  lea     rax, aGraphicsFileIO; "Graphics file I/O channel is not availa"...
0x18002cdae  mov     qword ptr [rsp+0C8h+var_A0], rax
0x18002cdb3  mov     qword ptr [rsp+0C8h+var_A8], r15; int
0x18002cdb8  mov     r9d, 80004003h
0x18002cdbe  lea     r8, aOnecoreuapTerm_57; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002cdc5  mov     edx, 46h ; 'F'
0x18002cdca  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18002cdcf  mov     rax, [rsi+38h]
0x18002cdd3  lea     r12, [rax+0B0h]
0x18002cdda  mov     r13d, [rax+98h]
0x18002cde1  mov     eax, [rax+94h]
0x18002cde7  mov     dword ptr [rsp+0C8h+arg_8], eax
0x18002cdee  mov     ecx, 0D0h; Size
0x18002cdf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002cdf8  mov     rdi, rax
0x18002cdfb  mov     [rsp+0C8h+arg_10], rax
0x18002ce03  mov     [rax+8], r14d
0x18002ce07  mov     [rax+0Ch], r14d
0x18002ce0b  lea     rax, ??_7?$_Ref_count_obj2@V?$CBitRateController@UH265_420_Profile@Avenc@Rdp@@@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>>::`vftable'
0x18002ce12  mov     [rdi], rax
0x18002ce15  lea     rbx, [rdi+10h]
0x18002ce19  mov     r9, r12
0x18002ce1c  mov     r8d, r13d
0x18002ce1f  mov     edx, dword ptr [rsp+0C8h+arg_8]
0x18002ce26  mov     rcx, rbx
0x18002ce29  call    ??0?$CBitRateController@UH265_420_Profile@Avenc@Rdp@@@Avenc@Rdp@@QEAA@IIAEBUDXGI_RATIONAL@@@Z; Rdp::Avenc::CBitRateController<Rdp::Avenc::H265_420_Profile>::CBitRateController<Rdp::Avenc::H265_420_Profile>(uint,uint,DXGI_RATIONAL const &)
0x18002ce2e  nop
0x18002ce2f  mov     [rsi+40h], rbx
0x18002ce33  mov     rbx, [rsi+48h]
0x18002ce37  mov     [rsi+48h], rdi
0x18002ce3b  or      edi, 0FFFFFFFFh
0x18002ce3e  test    rbx, rbx
0x18002ce41  jz      short loc_18002CE76
0x18002ce43  mov     eax, edi
0x18002ce45  lock xadd [rbx+8], eax
0x18002ce4a  add     eax, edi
0x18002ce4c  jnz     short loc_18002CE76
0x18002ce4e  mov     rax, [rbx]
0x18002ce51  mov     rcx, rbx
0x18002ce54  mov     rax, [rax]
0x18002ce57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce5c  mov     eax, edi
0x18002ce5e  lock xadd [rbx+0Ch], eax
0x18002ce63  add     eax, edi
0x18002ce65  jnz     short loc_18002CE76
0x18002ce67  mov     rax, [rbx]
0x18002ce6a  mov     rcx, rbx
0x18002ce6d  mov     rax, [rax+8]
0x18002ce71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ce76  lea     rcx, [rsi-50h]
0x18002ce7a  mov     [rsp+0C8h+arg_8], 0
0x18002ce86  mov     rax, [rcx]
0x18002ce89  lea     r8, [rsp+0C8h+arg_8]
0x18002ce91  lea     rdx, _GUID_a06bc936_6fd4_47ff_9fc7_68fe54155cab
0x18002ce98  mov     rax, [rax]
0x18002ce9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cea0  mov     rcx, [rsp+0C8h]; this
0x18002cea8  test    eax, eax
0x18002ceaa  js      loc_18002D19D
0x18002ceb0  mov     rax, [rsp+0C8h+arg_8]
0x18002ceb8  mov     [rsp+0C8h+arg_10], rax
0x18002cec0  mov     rax, [r15]
0x18002cec3  mov     [rsp+0C8h+arg_18], rax
0x18002cecb  lea     r8, [rsp+0C8h+arg_10]
0x18002ced3  lea     rdx, [rsp+0C8h+arg_18]
0x18002cedb  lea     rcx, [rsp+0C8h+var_58]
0x18002cee0  call    ??$make_shared@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@PEAUIFileIoChannel1@Avenc@3@PEAUIIoPacketCompleteEvents@53@@std@@YA?AV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@0@$$QEAPEAUIFileIoChannel1@Avenc@Rdp@@$$QEAPEAUIIoPacketCompleteEvents@34@@Z; std::make_shared<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>,Rdp::Avenc::IFileIoChannel1 *,Rdp::Avenc::IIoPacketCompleteEvents *>(Rdp::Avenc::IFileIoChannel1 * &&,Rdp::Avenc::IIoPacketCompleteEvents * &&)
0x18002cee5  mov     rbx, rax
0x18002cee8  mov     rcx, [rax]
0x18002ceeb  mov     [rsp+0C8h+var_48], rcx
0x18002cef3  mov     rcx, [rax+8]
0x18002cef7  mov     [rsp+0C8h+var_40], rcx
0x18002ceff  mov     qword ptr [rax], 0
0x18002cf06  mov     qword ptr [rax+8], 0
0x18002cf0e  lea     rcx, [rsi+20h]
0x18002cf12  lea     rdx, [rsp+0C8h+var_48]
0x18002cf1a  call    ?store@?$atomic@V?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAXV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,std::memory_order)
0x18002cf1f  mov     rbx, [rbx+8]
0x18002cf23  test    rbx, rbx
0x18002cf26  jz      short loc_18002CF5C
0x18002cf28  mov     eax, edi
0x18002cf2a  lock xadd [rbx+8], eax
0x18002cf2f  add     eax, edi
0x18002cf31  jnz     short loc_18002CF5C
0x18002cf33  mov     rax, [rbx]
0x18002cf36  mov     rcx, rbx
0x18002cf39  mov     rax, [rax]
0x18002cf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf41  mov     eax, edi
0x18002cf43  lock xadd [rbx+0Ch], eax
0x18002cf48  add     eax, edi
0x18002cf4a  jnz     short loc_18002CF5C
0x18002cf4c  mov     rax, [rbx]
0x18002cf4f  mov     rcx, rbx
0x18002cf52  mov     rax, [rax+8]
0x18002cf56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf5b  nop
0x18002cf5c  mov     rcx, [rsp+0C8h+arg_8]
0x18002cf64  test    rcx, rcx
0x18002cf67  jz      short loc_18002CF76
0x18002cf69  mov     rax, [rcx]
0x18002cf6c  mov     rax, [rax+10h]
0x18002cf70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cf75  nop
0x18002cf76  lea     r12, [rsi+28h]
0x18002cf7a  mov     rcx, r12; Address
0x18002cf7d  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x18002cf82  mov     rbx, rax
0x18002cf85  mov     r15, [rsi+20h]
0x18002cf89  mov     [rsp+0C8h+var_48], r15
0x18002cf91  mov     [rsp+0C8h+var_40], rax
0x18002cf99  test    rax, rax
0x18002cf9c  jz      short loc_18002CFA3
0x18002cf9e  lock add [rax+8], r14d
0x18002cfa3  mov     rdx, rbx
0x18002cfa6  xchg    rdx, [r12]
0x18002cfaa  and     dl, 3
0x18002cfad  cmp     dl, 2
0x18002cfb0  jnz     short loc_18002CFBC
0x18002cfb2  mov     rcx, r12; Address
0x18002cfb5  call    cs:__imp_WakeByAddressAll
0x18002cfbb  nop
0x18002cfbc  test    r15, r15
0x18002cfbf  jz      loc_18002D0D1
0x18002cfc5  xor     r9d, r9d; unsigned __int64
0x18002cfc8  xor     r8d, r8d; unsigned int
0x18002cfcb  mov     edx, 1000h; unsigned __int64
0x18002cfd0  mov     rcx, r15; this
0x18002cfd3  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x18002cfd8  mov     rax, [rsi+38h]
0x18002cfdc  mov     r13d, [rax+98h]
0x18002cfe3  mov     ecx, [rax+94h]
0x18002cfe9  mov     dword ptr [rsp+0C8h+arg_10], ecx
0x18002cff0  mov     eax, [rax+88h]
0x18002cff6  mov     dword ptr [rsp+0C8h+arg_8], eax
0x18002cffd  mov     edx, 0Fh; unsigned __int64
0x18002d002  mov     rcx, r15; this
0x18002d005  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x18002d00a  mov     r12, rax
0x18002d00d  mov     rcx, [rsp+0C8h]
0x18002d015  lea     rax, aUnableToEnsure_2; "Unable to ensure RDPGFX_CREATE_SURFACE_"...
0x18002d01c  mov     qword ptr [rsp+0C8h+var_A0], rax
0x18002d021  mov     qword ptr [rsp+0C8h+var_A8], r12
0x18002d026  mov     r9d, 8007000Eh
0x18002d02c  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18002d033  mov     edx, 10Ah
0x18002d038  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18002d03d  mov     dword ptr [r12], 9
0x18002d045  mov     dword ptr [r12+4], 0Fh
0x18002d04e  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x18002d055  mov     [r12+8], ax
0x18002d05b  mov     eax, dword ptr [rsp+0C8h+arg_10]
0x18002d062  mov     [r12+0Ah], ax
0x18002d068  mov     [r12+0Ch], r13w
0x18002d06e  mov     byte ptr [r12+0Eh], 21h ; '!'
0x18002d074  mov     r8, [rsi+38h]
0x18002d078  mov     r9, [r8+70h]
0x18002d07c  mov     eax, [r8+98h]
0x18002d083  mov     dword ptr [rsp+0C8h+var_88], eax
0x18002d087  mov     eax, [r8+94h]
0x18002d08e  mov     dword ptr [rsp+0C8h+MessageGuid], eax
0x18002d092  mov     eax, [r8+90h]
0x18002d099  mov     dword ptr [rsp+0C8h+var_98], eax
0x18002d09d  mov     eax, [r8+8Ch]
0x18002d0a4  mov     [rsp+0C8h+var_A0], eax; int
0x18002d0a8  mov     eax, [r9+0A8h]
0x18002d0af  mov     [rsp+0C8h+var_A8], eax; int
0x18002d0b3  mov     r9d, [r9+0A4h]
0x18002d0ba  mov     r8d, [r8+88h]
0x18002d0c1  mov     rcx, r15
0x18002d0c4  call    ?MapSurfaceToScaledOutput@?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@QEAAX_NIHHHHII@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>::MapSurfaceToScaledOutput(bool,uint,int,int,int,int,uint,uint)
0x18002d0c9  mov     rcx, r15; this
0x18002d0cc  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x18002d0d1  mov     rax, cs:WPP_GLOBAL_Control
0x18002d0d8  lea     rcx, WPP_GLOBAL_Control
0x18002d0df  cmp     rax, rcx
0x18002d0e2  jz      short loc_18002D0F0
0x18002d0e4  test    [rax+1Ch], r14b
0x18002d0e8  jz      short loc_18002D0F0
0x18002d0ea  cmp     byte ptr [rax+19h], 4
0x18002d0ee  jnb     short loc_18002D0F3
0x18002d0f0  xor     r14b, r14b
0x18002d0f3  lea     rax, WPP_RECORDER_INITIALIZED
0x18002d0fa  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002d101  setnz   sil
0x18002d105  test    r14b, r14b
0x18002d108  jnz     short loc_18002D10F
0x18002d10a  test    sil, sil
0x18002d10d  jz      short loc_18002D147
0x18002d10f  call    cs:__imp_GetCurrentThreadId
0x18002d115  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18002d119  lea     rax, WPP_bc0801f283643948a642b8834c5cca7a_Traceguids
  ... truncated ...
```
