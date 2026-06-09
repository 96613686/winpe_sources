# Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::Stop(void)

- ea: `0x180068360`
- end: `0x1800687f2`
- name: `?Stop@CRdpProgFrameProcessor@RdpProg@Avenc@Rdp@@UEAAJXZ`
- size: `1170`
- prototype: `__int64 __fastcall(Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180066030`

## callees

- `0x180002be0`
- `0x18001143c`
- `0x1800153f8`
- `0x180015480`
- `0x180022fb8`
- `0x180023b34`
- `0x180023ee4`
- `0x18002dd40`
- `0x18002e0c4`
- `0x180068360`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800683c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068760`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800683c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180068760`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180068610`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180068610`

## string_xrefs

- `0x180068697`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x180068680`: `Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::Stop(
        Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *this,
        __int64 a2,
        int a3,
        int a4)
{
  Rdp::Avenc::RdpProg::CRdpProgFrameProcessor *v4; // r13
  char v5; // r12
  bool v6; // bl
  bool v7; // di
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rax
  volatile signed __int32 *v14; // rbx
  Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *v15; // rsi
  const char *v16; // r9
  unsigned int v17; // edx
  __int64 *v18; // r14
  __int64 v19; // rcx
  void (__fastcall ***v20)(_QWORD, __int64); // rcx
  bool v21; // di
  char v22; // al
  int v23; // r8d
  int v24; // edx
  __int64 result; // rax
  int v26; // [rsp+20h] [rbp-C8h]
  _DWORD *v27; // [rsp+20h] [rbp-C8h]
  int v28; // [rsp+28h] [rbp-C0h]
  const char *v29; // [rsp+28h] [rbp-C0h]
  int *v30; // [rsp+80h] [rbp-68h] BYREF
  const char *v31; // [rsp+88h] [rbp-60h] BYREF
  __int128 v32; // [rsp+90h] [rbp-58h] BYREF
  _QWORD v33[9]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  int v36; // [rsp+F8h] [rbp+10h] BYREF
  __int64 *v37; // [rsp+100h] [rbp+18h] BYREF
  const char *v38; // [rsp+108h] [rbp+20h] BYREF

  v4 = this;
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
      v26,
      v28,
      12,
      &WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *((_QWORD *)v4 + 6);
    v37 = (__int64 *)(v11 + 120);
    v36 = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v38 = "Stop RdpProg frame processor";
    v30 = &xmmword_1800C21A0;
    v31 = "RdpAvenc";
    *(_QWORD *)&v32 = 0x1000000;
    v33[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800B552F,
      a3,
      a4,
      (__int64)v33,
      (__int64)&v32,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v38,
      (__int64)&v36,
      (__int64)&v37);
  }
  v37 = (__int64 *)((char *)v4 + 48);
  v12 = *((_QWORD *)v4 + 6);
  LODWORD(v29) = *(_DWORD *)(v12 + 120);
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"RdpProgFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::RdpProg::CRdpProgFrameProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
      0xA5u);
    v13 = std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load((char *)v4 + 40);
    v14 = (volatile signed __int32 *)v13;
    v38 = (const char *)v13;
    v15 = (Rdp::Avenc::CFcWireEncoderWithBulkUncompressed *)*((_QWORD *)v4 + 4);
    v33[0] = v15;
    v33[1] = v13;
    if ( v13 )
      _InterlockedAdd((volatile signed __int32 *)(v13 + 8), 1u);
    if ( (_InterlockedExchange64((volatile __int64 *)v4 + 5, v13) & 3) == 2 )
      WakeByAddressAll((char *)v4 + 40);
    v32 = 0;
    std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(
      (char *)v4 + 32,
      &v32);
    if ( v15 )
    {
      try
      {
        Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(v15, 0x1000u, 0, 0);
        v18 = v37;
        v36 = *(_DWORD *)(*v37 + 136);
        v29 = "Unable to ensure RDPGFX_DELETE_SURFACE_PDU_SIZE";
        v27 = Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(v15, 0xAu);
        wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
          retaddr,
          343,
          "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
          2147942414LL);
        *v27 = 10;
        v27[1] = 10;
        *((_WORD *)v27 + 4) = v36;
        Rdp::Avenc::CFcWireEncoder::Flush(v15, v17);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0xB7,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
          v16);
        v5 = 1;
        v4 = this;
        v14 = (volatile signed __int32 *)v38;
        goto LABEL_19;
      }
    }
    else
    {
LABEL_19:
      v18 = v37;
    }
    v19 = *v18;
    *v18 = 0;
    if ( v19 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    v20 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)v4 + 29);
    *((_QWORD *)v4 + 29) = 0;
    if ( v20 )
      (**v20)(v20, 1);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v22 = GetCurrentThreadId();
      LOBYTE(v23) = v21;
      LOBYTE(v24) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v24,
        v23,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)v27,
        (int)v29,
        13,
        &WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids,
        v22);
    }
    if ( v14 )
    {
      if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC0,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rdpprogprocessor\\rdpprogframeprocessor.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x180068360  mov     [rsp+arg_0], rcx
0x180068365  push    rbx
0x180068366  push    rsi
0x180068367  push    rdi
0x180068368  push    r12
0x18006836a  push    r13
0x18006836c  push    r14
0x18006836e  push    r15
0x180068370  sub     rsp, 0B0h
0x180068377  mov     r13, rcx
0x18006837a  lea     rcx, WPP_GLOBAL_Control
0x180068381  mov     rax, cs:WPP_GLOBAL_Control
0x180068388  mov     r12d, 1
0x18006838e  cmp     rax, rcx
0x180068391  jz      short loc_1800683A7
0x180068393  test    [rax+1Ch], r12b
0x180068397  jz      short loc_1800683A7
0x180068399  cmp     byte ptr [rax+19h], 4
0x18006839d  jb      short loc_1800683A7
0x18006839f  mov     bl, r12b
0x1800683a2  xor     r15d, r15d
0x1800683a5  jmp     short loc_1800683AD
0x1800683a7  xor     r15d, r15d
0x1800683aa  mov     bl, r15b
0x1800683ad  lea     rax, WPP_RECORDER_INITIALIZED
0x1800683b4  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800683bb  setnz   dil
0x1800683bf  test    bl, bl
0x1800683c1  jnz     short loc_1800683C8
0x1800683c3  test    dil, dil
0x1800683c6  jz      short loc_1800683FE
0x1800683c8  call    cs:__imp_GetCurrentThreadId
0x1800683ce  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x1800683d2  lea     rsi, WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids
0x1800683d9  mov     [rsp+0E8h+MessageGuid], rsi; MessageGuid
0x1800683de  mov     [rsp+0E8h+var_B8], 0Ch; __int16
0x1800683e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800683ec  mov     r9, [rcx+28h]; int
0x1800683f0  mov     r8b, dil; int
0x1800683f3  mov     dl, bl; int
0x1800683f5  mov     rcx, [rcx+10h]; int
0x1800683f9  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800683fe  mov     eax, cs:dword_1800C1058
0x180068404  cmp     eax, 4
0x180068407  jbe     loc_180068514
0x18006840d  mov     rcx, cs:qword_1800C1070
0x180068414  mov     rax, cs:qword_1800C1068
0x18006841b  mov     rdx, 470000000000h
0x180068425  test    rdx, rax
0x180068428  jz      loc_180068514
0x18006842e  mov     rax, rcx
0x180068431  and     rax, rdx
0x180068434  cmp     rax, rcx
0x180068437  jnz     loc_180068514
0x18006843d  mov     rcx, [r13+30h]
0x180068441  lea     rax, [rcx+78h]
0x180068445  mov     [rsp+0E8h+arg_10], rax
0x18006844d  mov     rax, [rcx+70h]
0x180068451  mov     ecx, [rax+0A0h]
0x180068457  mov     [rsp+0E8h+arg_8], ecx
0x18006845e  lea     rax, aStopRdpprogFra; "Stop RdpProg frame processor"
0x180068465  mov     [rsp+0E8h+arg_18], rax
0x18006846d  lea     rax, xmmword_1800C21A0
0x180068474  mov     [rsp+0E8h+var_68], rax
0x18006847c  lea     rax, aRdpavenc; "RdpAvenc"
0x180068483  mov     [rsp+0E8h+var_60], rax
0x18006848b  mov     qword ptr [rsp+0E8h+var_58], 1000000h
0x180068497  lea     rax, aCheckpoint; "Checkpoint"
0x18006849e  mov     [rsp+0E8h+var_48], rax
0x1800684a6  lea     rax, [rsp+0E8h+arg_10]
0x1800684ae  mov     [rsp+0E8h+var_98], rax
0x1800684b3  lea     rax, [rsp+0E8h+arg_8]
0x1800684bb  mov     [rsp+0E8h+var_A0], rax
0x1800684c0  lea     rax, [rsp+0E8h+arg_18]
0x1800684c8  mov     qword ptr [rsp+0E8h+var_A8], rax
0x1800684cd  lea     rax, [rsp+0E8h+var_68]
0x1800684d5  mov     [rsp+0E8h+MessageGuid], rax
0x1800684da  lea     rax, [rsp+0E8h+var_60]
0x1800684e2  mov     qword ptr [rsp+0E8h+var_B8], rax
0x1800684e7  lea     rax, [rsp+0E8h+var_58]
0x1800684ef  mov     [rsp+0E8h+var_C0], rax
0x1800684f4  lea     rax, [rsp+0E8h+var_48]
0x1800684fc  mov     qword ptr [rsp+0E8h+var_C8], rax
0x180068501  lea     rdx, byte_1800B552F
0x180068508  lea     rcx, dword_1800C1058
0x18006850f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180068514  lea     rax, [r13+30h]
0x180068518  mov     [rsp+0E8h+arg_10], rax
0x180068520  mov     r14, [rax]
0x180068523  movzx   eax, byte ptr [r14+87h]
0x18006852b  movzx   ecx, byte ptr [r14+86h]
0x180068533  movzx   edx, byte ptr [r14+85h]
0x18006853b  movzx   r8d, byte ptr [r14+84h]
0x180068543  movzx   r9d, byte ptr [r14+83h]
0x18006854b  movzx   r10d, byte ptr [r14+82h]
0x180068553  movzx   r11d, byte ptr [r14+81h]
0x18006855b  movzx   ebx, byte ptr [r14+80h]
0x180068563  movzx   edi, word ptr [r14+7Eh]
0x180068568  movzx   esi, word ptr [r14+7Ch]
0x18006856d  mov     [rsp+0E8h+var_70], eax
0x180068571  mov     [rsp+0E8h+var_78], ecx
0x180068575  mov     [rsp+0E8h+var_80], edx
0x180068579  mov     [rsp+0E8h+var_88], r8d
0x18006857e  mov     [rsp+0E8h+var_90], r9d
0x180068583  mov     dword ptr [rsp+0E8h+var_98], r10d
0x180068588  mov     dword ptr [rsp+0E8h+var_A0], r11d
0x18006858d  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x180068591  mov     dword ptr [rsp+0E8h+MessageGuid], edi
0x180068595  mov     dword ptr [rsp+0E8h+var_B8], esi
0x180068599  mov     eax, [r14+78h]
0x18006859d  mov     dword ptr [rsp+0E8h+var_C0], eax
0x1800685a1  mov     [rsp+0E8h+var_C8], 0A5h; unsigned int
0x1800685a9  lea     r9, aOnecoreuapTerm_35; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800685b0  lea     r8, aRdpAvencRdppro_2; "Rdp::Avenc::RdpProg::CRdpProgFrameProce"...
0x1800685b7  lea     rdx, aRdpprogframepr; "RdpProgFrameProcessorStop: Id {%08lX-%0"...
0x1800685be  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x1800685c5  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800685ca  lea     rdi, [r13+28h]
0x1800685ce  mov     rcx, rdi; Address
0x1800685d1  call    ?_Lock_and_load@?$_Locked_pointer@V_Ref_count_base@std@@@std@@QEAAPEAV_Ref_count_base@2@XZ; std::_Locked_pointer<std::_Ref_count_base>::_Lock_and_load(void)
0x1800685d6  mov     rbx, rax
0x1800685d9  mov     [rsp+0E8h+arg_18], rax
0x1800685e1  mov     rsi, [r13+20h]
0x1800685e5  mov     [rsp+0E8h+var_48], rsi
0x1800685ed  mov     [rsp+0E8h+var_40], rax
0x1800685f5  test    rax, rax
0x1800685f8  jz      short loc_1800685FF
0x1800685fa  lock add [rax+8], r12d
0x1800685ff  mov     rdx, rax
0x180068602  xchg    rdx, [rdi]
0x180068605  and     dl, 3
0x180068608  cmp     dl, 2
0x18006860b  jnz     short loc_180068617
0x18006860d  mov     rcx, rdi; Address
0x180068610  call    cs:__imp_WakeByAddressAll
0x180068616  nop
0x180068617  xorps   xmm0, xmm0
0x18006861a  movdqu  [rsp+0E8h+var_58], xmm0
0x180068623  lea     rdx, [rsp+0E8h+var_58]
0x18006862b  lea     rcx, [r13+20h]
0x18006862f  call    ?store@?$atomic@V?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAXV?$shared_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@@Protocol@Rdp@@@2@W4memory_order@2@@Z; std::atomic<std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>>::store(std::shared_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkUncompressed>>,std::memory_order)
0x180068634  test    rsi, rsi
0x180068637  jz      loc_1800686E1
0x18006863d  xor     r9d, r9d; unsigned __int64
0x180068640  xor     r8d, r8d; unsigned int
0x180068643  mov     edx, 1000h; unsigned __int64
0x180068648  mov     rcx, rsi; this
0x18006864b  call    ?AllocatePool@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAX_KI0@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::AllocatePool(unsigned __int64,uint,unsigned __int64)
0x180068650  mov     r14, [rsp+0E8h+arg_10]
0x180068658  mov     rax, [r14]
0x18006865b  mov     eax, [rax+88h]
0x180068661  mov     [rsp+0E8h+arg_8], eax
0x180068668  mov     edx, 0Ah; unsigned __int64
0x18006866d  mov     rcx, rsi; this
0x180068670  call    ?EnsureBuffer@CFcWireEncoderWithBulkUncompressed@Avenc@Rdp@@QEAAPEAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkUncompressed::EnsureBuffer(unsigned __int64)
0x180068675  mov     rdi, rax
0x180068678  mov     rcx, [rsp+0E8h]
0x180068680  lea     rax, aUnableToEnsure_20; "Unable to ensure RDPGFX_DELETE_SURFACE_"...
0x180068687  mov     [rsp+0E8h+var_C0], rax
0x18006868c  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x180068691  mov     r9d, 8007000Eh
0x180068697  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18006869e  mov     edx, 157h
0x1800686a3  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x1800686a8  mov     eax, 0Ah
0x1800686ad  mov     [rdi], eax
0x1800686af  mov     [rdi+4], eax
0x1800686b2  mov     eax, [rsp+0E8h+arg_8]
0x1800686b9  mov     [rdi+8], ax
0x1800686bd  mov     rcx, rsi; this
0x1800686c0  call    ?Flush@CFcWireEncoder@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::CFcWireEncoder::Flush(uint)
0x1800686c5  nop
0x1800686c6  jmp     short loc_1800686E9
0x1800686c8  mov     r12d, 1
0x1800686ce  xor     r15d, r15d
0x1800686d1  mov     r13, [rsp+0E8h+arg_0]
0x1800686d9  mov     rbx, [rsp+0E8h+arg_18]
0x1800686e1  mov     r14, [rsp+0E8h+arg_10]
0x1800686e9  lea     rdi, WPP_GLOBAL_Control
0x1800686f0  lea     rsi, WPP_RECORDER_INITIALIZED
0x1800686f7  mov     rcx, [r14]
0x1800686fa  mov     [r14], r15
0x1800686fd  test    rcx, rcx
0x180068700  jz      short loc_18006870F
0x180068702  mov     rax, [rcx]
0x180068705  mov     rax, [rax+10h]
0x180068709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006870e  nop
0x18006870f  mov     rcx, [r13+0E8h]
0x180068716  mov     [r13+0E8h], r15
0x18006871d  test    rcx, rcx
0x180068720  jz      short loc_180068730
0x180068722  mov     rax, [rcx]
0x180068725  mov     edx, r12d
0x180068728  mov     rax, [rax]
0x18006872b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068730  mov     rax, cs:WPP_GLOBAL_Control
0x180068737  cmp     rax, rdi
0x18006873a  jz      short loc_180068748
0x18006873c  test    [rax+1Ch], r12b
0x180068740  jz      short loc_180068748
0x180068742  cmp     byte ptr [rax+19h], 4
0x180068746  jnb     short loc_18006874B
0x180068748  mov     r12b, r15b
0x18006874b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x180068752  setnz   dil
0x180068756  test    r12b, r12b
0x180068759  jnz     short loc_180068760
0x18006875b  test    dil, dil
0x18006875e  jz      short loc_180068798
0x180068760  call    cs:__imp_GetCurrentThreadId
0x180068766  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18006876a  lea     rax, WPP_a6c7f7db86c33c0e0753adfc7a80bf79_Traceguids
0x180068771  mov     [rsp+0E8h+MessageGuid], rax; MessageGuid
0x180068776  mov     [rsp+0E8h+var_B8], 0Dh; __int16
0x18006877d  mov     rcx, cs:WPP_GLOBAL_Control
0x180068784  mov     r9, [rcx+28h]; int
0x180068788  mov     r8b, dil; int
0x18006878b  mov     dl, r12b; int
0x18006878e  mov     rcx, [rcx+10h]; int
0x180068792  call    WPP_RECORDER_AND_TRACE_SF_D
0x180068797  nop
0x180068798  test    rbx, rbx
0x18006879b  jz      short loc_1800687D3
0x18006879d  or      edi, 0FFFFFFFFh
0x1800687a0  mov     eax, edi
0x1800687a2  lock xadd [rbx+8], eax
0x1800687a7  add     eax, edi
0x1800687a9  jnz     short loc_1800687D3
0x1800687ab  mov     rax, [rbx]
0x1800687ae  mov     rcx, rbx
0x1800687b1  mov     rax, [rax]
0x1800687b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687b9  mov     eax, edi
0x1800687bb  lock xadd [rbx+0Ch], eax
0x1800687c0  add     eax, edi
0x1800687c2  jnz     short loc_1800687D3
0x1800687c4  mov     rax, [rbx]
0x1800687c7  mov     rcx, rbx
0x1800687ca  mov     rax, [rax+8]
0x1800687ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800687d3  xor     eax, eax
0x1800687d5  jmp     short loc_1800687DE
0x1800687d7  mov     eax, dword ptr [rsp+0E8h+arg_0]
0x1800687de  add     rsp, 0B0h
0x1800687e5  pop     r15
0x1800687e7  pop     r14
0x1800687e9  pop     r13
0x1800687eb  pop     r12
0x1800687ed  pop     rdi
0x1800687ee  pop     rsi
0x1800687ef  pop     rbx
0x1800687f0  retn
```
