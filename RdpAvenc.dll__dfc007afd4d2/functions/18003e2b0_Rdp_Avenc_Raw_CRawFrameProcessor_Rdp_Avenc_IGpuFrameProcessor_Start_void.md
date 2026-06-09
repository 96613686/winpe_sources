# Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::Start(void)

- ea: `0x18003e2b0`
- end: `0x18003e659`
- name: `?Start@?$CRawFrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@@Raw@Avenc@Rdp@@UEAAJXZ`
- size: `937`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x180003604`
- `0x1800065a4`
- `0x18000d3a4`
- `0x18001143c`
- `0x1800152c4`
- `0x180015480`
- `0x180038e20`
- `0x180038eb4`
- `0x18003968c`
- `0x180039ff0`
- `0x18003de48`
- `0x18003e2b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e60b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e60b`

## string_xrefs

- `0x18003e54c`: `onecoreuap\termsrv\rdp_bin\win\common/protocol/RdpEgfx/RdpEgfx.h`
- `0x18003e535`: `Unable to ensure RDPGFX_CREATE_SURFACE_PDU_SIZE`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Raw::CRawFrameProcessor<Rdp::Avenc::IGpuFrameProcessor>::Start(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // bl
  bool v6; // di
  bool v7; // si
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  struct Rdp::Avenc::IFileIoChannel *v12; // rsi
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v13; // rdi
  struct Rdp::Avenc::IIoPacketCompleteEvents *v14; // r8
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor **v15; // rdi
  _QWORD *v16; // rcx
  _DWORD *v17; // rax
  int v18; // r12d
  int v19; // r13d
  __int64 v20; // rsi
  __int64 v21; // rdx
  __int64 v22; // rdx
  __int64 v23; // r9
  int v24; // r8d
  bool v25; // r8
  bool v26; // di
  char v27; // al
  int v28; // r8d
  int v29; // edx
  int v31; // [rsp+20h] [rbp-98h]
  int v32; // [rsp+20h] [rbp-98h]
  int v33; // [rsp+28h] [rbp-90h]
  int v34; // [rsp+28h] [rbp-90h]
  int v35; // [rsp+30h] [rbp-88h]
  int *v36; // [rsp+60h] [rbp-58h] BYREF
  const char *v37; // [rsp+68h] [rbp-50h] BYREF
  __int64 v38; // [rsp+70h] [rbp-48h] BYREF
  const char *v39; // [rsp+78h] [rbp-40h] BYREF
  void *retaddr; // [rsp+B8h] [rbp+0h]
  Rdp::Avenc::CFcWireEncoderWithBulkCompressor *v41; // [rsp+C8h] [rbp+10h] BYREF
  __int64 v42; // [rsp+D0h] [rbp+18h] BYREF
  const char *v43; // [rsp+D8h] [rbp+20h] BYREF

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
      v31,
      v33,
      10,
      &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 8);
    LODWORD(v41) = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 160LL);
    v42 = v11 + 120;
    v43 = "Start Raw frame processor";
    v36 = &xmmword_1800C21A0;
    v37 = "RdpAvenc";
    v38 = 0x1000000;
    v39 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&word_1800AFAF6,
      a3,
      a4,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"RawFrameProcessorStart",
    "Rdp::Avenc::Raw::CRawFrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor>::Start",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawframeprocessor.cpp",
    0x43u);
  v12 = *(struct Rdp::Avenc::IFileIoChannel **)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 112LL) + 480LL);
  if ( v12 )
  {
    v13 = (Rdp::Avenc::CFcWireEncoderWithBulkCompressor *)operator new(0xC08u);
    v41 = v13;
    Rdp::Avenc::CFcWireEncoderWithBulkCompressor::CFcWireEncoderWithBulkCompressor(v13, v12, v14);
    *((_DWORD *)v13 + 768) = 0;
    v41 = v13;
    v15 = (Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24);
    std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>,0>(
      a1 + 24,
      &v41);
    std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>(&v41);
    Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(
      *(Rdp::Avenc::CFcWireEncoderWithBulkCompressor **)(a1 + 24),
      0x1000u);
    v16 = *(_QWORD **)(a1 + 24);
    v17 = *(_DWORD **)(a1 + 8);
    v18 = v17[38];
    v19 = v17[37];
    LODWORD(v41) = v17[34];
    v20 = 0;
    v21 = v16[4];
    if ( (unsigned __int64)(v16[5] - v21) >= 0xF )
    {
      v20 = v21 + v16[1];
      v16[4] = v21 + 15;
    }
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      266,
      "onecoreuap\\termsrv\\rdp_bin\\win\\common/protocol/RdpEgfx/RdpEgfx.h",
      2147942414LL);
    *(_DWORD *)v20 = 9;
    *(_DWORD *)(v20 + 4) = 15;
    *(_WORD *)(v20 + 8) = (_WORD)v41;
    *(_WORD *)(v20 + 10) = v19;
    *(_WORD *)(v20 + 12) = v18;
    *(_BYTE *)(v20 + 14) = 33;
    v22 = *(_QWORD *)(a1 + 8);
    v23 = *(_QWORD *)(v22 + 112);
    v35 = *(_DWORD *)(v22 + 144);
    v34 = *(_DWORD *)(v22 + 140);
    v24 = *(_DWORD *)(v22 + 136);
    LOBYTE(v22) = *(_BYTE *)(v22 + 200);
    Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::MapSurfaceToOutput(
      (unsigned int)*v15,
      v22,
      v24,
      *(_DWORD *)(v23 + 164),
      *(_DWORD *)(v23 + 168),
      v34,
      v35);
    Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(*v15, 0, v25);
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v5 = 0;
  }
  v26 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v27 = GetCurrentThreadId();
    LOBYTE(v28) = v26;
    LOBYTE(v29) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v29,
      v28,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v32,
      v33,
      11,
      &WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids,
      v27);
  }
  return 0;
}

```

## disassembly

```asm
0x18003e2b0  push    rbx
0x18003e2b2  push    rsi
0x18003e2b3  push    rdi
0x18003e2b4  push    r12
0x18003e2b6  push    r13
0x18003e2b8  push    r14
0x18003e2ba  push    r15
0x18003e2bc  sub     rsp, 80h
0x18003e2c3  mov     r14, rcx
0x18003e2c6  lea     rcx, WPP_GLOBAL_Control
0x18003e2cd  mov     rax, cs:WPP_GLOBAL_Control
0x18003e2d4  mov     bl, 1
0x18003e2d6  cmp     rax, rcx
0x18003e2d9  jz      short loc_18003E2EB
0x18003e2db  test    [rax+1Ch], bl
0x18003e2de  jz      short loc_18003E2EB
0x18003e2e0  cmp     byte ptr [rax+19h], 4
0x18003e2e4  jb      short loc_18003E2EB
0x18003e2e6  mov     dil, bl
0x18003e2e9  jmp     short loc_18003E2EE
0x18003e2eb  xor     dil, dil
0x18003e2ee  lea     r12, WPP_RECORDER_INITIALIZED
0x18003e2f5  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003e2fc  setnz   sil
0x18003e300  test    dil, dil
0x18003e303  jnz     short loc_18003E313
0x18003e305  test    sil, sil
0x18003e308  jnz     short loc_18003E313
0x18003e30a  lea     r15, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003e311  jmp     short loc_18003E34A
0x18003e313  call    cs:__imp_GetCurrentThreadId
0x18003e319  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003e31d  lea     r15, WPP_4305ebc2891e3311ffa3fc8a7ac47271_Traceguids
0x18003e324  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003e329  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x18003e330  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e337  mov     r9, [rcx+28h]; int
0x18003e33b  mov     r8b, sil; int
0x18003e33e  mov     dl, dil; int
0x18003e341  mov     rcx, [rcx+10h]; int
0x18003e345  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003e34a  mov     eax, cs:dword_1800C1058
0x18003e350  cmp     eax, 4
0x18003e353  jbe     loc_18003E448
0x18003e359  mov     rcx, cs:qword_1800C1070
0x18003e360  mov     rax, cs:qword_1800C1068
0x18003e367  mov     rdx, 470000000000h
0x18003e371  test    rdx, rax
0x18003e374  jz      loc_18003E448
0x18003e37a  mov     rax, rcx
0x18003e37d  and     rax, rdx
0x18003e380  cmp     rax, rcx
0x18003e383  jnz     loc_18003E448
0x18003e389  mov     rdx, [r14+8]
0x18003e38d  mov     rax, [rdx+70h]
0x18003e391  mov     ecx, [rax+0A0h]
0x18003e397  mov     dword ptr [rsp+0B8h+arg_8], ecx
0x18003e39e  lea     rax, [rdx+78h]
0x18003e3a2  mov     [rsp+0B8h+arg_10], rax
0x18003e3aa  lea     rax, aStartRawFrameP; "Start Raw frame processor"
0x18003e3b1  mov     [rsp+0B8h+arg_18], rax
0x18003e3b9  lea     rax, xmmword_1800C21A0
0x18003e3c0  mov     [rsp+0B8h+var_58], rax
0x18003e3c5  lea     rax, aRdpavenc; "RdpAvenc"
0x18003e3cc  mov     [rsp+0B8h+var_50], rax
0x18003e3d1  mov     [rsp+0B8h+var_48], 1000000h
0x18003e3da  lea     rax, aCheckpoint; "Checkpoint"
0x18003e3e1  mov     [rsp+0B8h+var_40], rax
0x18003e3e6  lea     rax, [rsp+0B8h+arg_8]
0x18003e3ee  mov     [rsp+0B8h+var_68], rax
0x18003e3f3  lea     rax, [rsp+0B8h+arg_10]
0x18003e3fb  mov     [rsp+0B8h+var_70], rax
0x18003e400  lea     rax, [rsp+0B8h+arg_18]
0x18003e408  mov     qword ptr [rsp+0B8h+var_78], rax
0x18003e40d  lea     rax, [rsp+0B8h+var_58]
0x18003e412  mov     [rsp+0B8h+MessageGuid], rax
0x18003e417  lea     rax, [rsp+0B8h+var_50]
0x18003e41c  mov     qword ptr [rsp+0B8h+var_88], rax
0x18003e421  lea     rax, [rsp+0B8h+var_48]
0x18003e426  mov     qword ptr [rsp+0B8h+var_90], rax
0x18003e42b  lea     rax, [rsp+0B8h+var_40]
0x18003e430  mov     qword ptr [rsp+0B8h+var_98], rax
0x18003e435  lea     rdx, word_1800AFAF6
0x18003e43c  lea     rcx, dword_1800C1058
0x18003e443  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003e448  mov     [rsp+0B8h+var_98], 43h ; 'C'; unsigned int
0x18003e450  lea     r9, aOnecoreuapTerm_6; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003e457  lea     r8, aRdpAvencRawCra_0; "Rdp::Avenc::Raw::CRawFrameProcessor<str"...
0x18003e45e  lea     rdx, aRawframeproces_0; "RawFrameProcessorStart"
0x18003e465  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003e46c  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18003e471  mov     rax, [r14+8]
0x18003e475  mov     rcx, [rax+70h]
0x18003e479  mov     rsi, [rcx+1E0h]
0x18003e480  test    rsi, rsi
0x18003e483  jz      loc_18003E5D7
0x18003e489  mov     ecx, 0C08h; Size
0x18003e48e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003e493  mov     rdi, rax
0x18003e496  mov     [rsp+0B8h+arg_8], rax
0x18003e49e  mov     rdx, rsi; struct Rdp::Avenc::IFileIoChannel *
0x18003e4a1  mov     rcx, rax; this
0x18003e4a4  call    ??0CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAA@PEAUIFileIoChannel@12@PEAUIIoPacketCompleteEvents@12@@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::CFcWireEncoderWithBulkCompressor(Rdp::Avenc::IFileIoChannel *,Rdp::Avenc::IIoPacketCompleteEvents *)
0x18003e4a9  mov     dword ptr [rdi+0C00h], 0
0x18003e4b3  mov     [rsp+0B8h+arg_8], rdi
0x18003e4bb  lea     rdi, [r14+18h]
0x18003e4bf  lea     rdx, [rsp+0B8h+arg_8]
0x18003e4c7  mov     rcx, rdi
0x18003e4ca  call    ??$?4U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@$0A@@?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::operator=<std::default_delete<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>,0>(std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>> &&)
0x18003e4cf  lea     rcx, [rsp+0B8h+arg_8]
0x18003e4d7  call    ??1?$unique_ptr@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@U?$default_delete@V?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@@std@@@std@@QEAA@XZ; std::unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>::~unique_ptr<Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>>(void)
0x18003e4dc  mov     edx, 1000h; unsigned __int64
0x18003e4e1  mov     rcx, [rdi]; this
0x18003e4e4  call    ?AllocatePool@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAX_K@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::AllocatePool(unsigned __int64)
0x18003e4e9  mov     rcx, [rdi]
0x18003e4ec  mov     rax, [r14+8]
0x18003e4f0  mov     r12d, [rax+98h]
0x18003e4f7  mov     r13d, [rax+94h]
0x18003e4fe  mov     eax, [rax+88h]
0x18003e504  mov     dword ptr [rsp+0B8h+arg_8], eax
0x18003e50b  xor     esi, esi
0x18003e50d  mov     rdx, [rcx+20h]
0x18003e511  mov     rax, [rcx+28h]
0x18003e515  sub     rax, rdx
0x18003e518  cmp     rax, 0Fh
0x18003e51c  jb      short loc_18003E52D
0x18003e51e  mov     rsi, [rcx+8]
0x18003e522  add     rsi, rdx
0x18003e525  lea     rax, [rdx+0Fh]
0x18003e529  mov     [rcx+20h], rax
0x18003e52d  mov     rcx, [rsp+0B8h]
0x18003e535  lea     rax, aUnableToEnsure_2; "Unable to ensure RDPGFX_CREATE_SURFACE_"...
0x18003e53c  mov     qword ptr [rsp+0B8h+var_90], rax
0x18003e541  mov     qword ptr [rsp+0B8h+var_98], rsi
0x18003e546  mov     r9d, 8007000Eh
0x18003e54c  lea     r8, aOnecoreuapTerm_14; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18003e553  mov     edx, 10Ah
0x18003e558  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x18003e55d  mov     dword ptr [rsi], 9
0x18003e563  mov     dword ptr [rsi+4], 0Fh
0x18003e56a  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18003e571  mov     [rsi+8], ax
0x18003e575  mov     [rsi+0Ah], r13w
0x18003e57a  mov     [rsi+0Ch], r12w
0x18003e57f  mov     byte ptr [rsi+0Eh], 21h ; '!'
0x18003e583  mov     rdx, [r14+8]
0x18003e587  mov     r9, [rdx+70h]
0x18003e58b  mov     eax, [rdx+90h]
0x18003e591  mov     dword ptr [rsp+0B8h+var_88], eax
0x18003e595  mov     eax, [rdx+8Ch]
0x18003e59b  mov     [rsp+0B8h+var_90], eax; int
0x18003e59f  mov     eax, [r9+0A8h]
0x18003e5a6  mov     [rsp+0B8h+var_98], eax; int
0x18003e5aa  mov     r9d, [r9+0A4h]
0x18003e5b1  mov     r8d, [rdx+88h]
0x18003e5b8  mov     dl, [rdx+0C8h]
0x18003e5be  mov     rcx, [rdi]
0x18003e5c1  call    ?MapSurfaceToOutput@?$CRdpEgfx@VCFcWireEncoderWithBulkCompressor@Avenc@Rdp@@@Protocol@Rdp@@QEAAX_NIHHHH@Z; Rdp::Protocol::CRdpEgfx<Rdp::Avenc::CFcWireEncoderWithBulkCompressor>::MapSurfaceToOutput(bool,uint,int,int,int,int)
0x18003e5c6  xor     edx, edx; unsigned int
0x18003e5c8  mov     rcx, [rdi]; this
0x18003e5cb  call    ?Flush@CFcWireEncoderWithBulkCompressor@Avenc@Rdp@@QEAAXI_N@Z; Rdp::Avenc::CFcWireEncoderWithBulkCompressor::Flush(uint,bool)
0x18003e5d0  lea     r12, WPP_RECORDER_INITIALIZED
0x18003e5d7  mov     rax, cs:WPP_GLOBAL_Control
0x18003e5de  lea     rcx, WPP_GLOBAL_Control
0x18003e5e5  cmp     rax, rcx
0x18003e5e8  jz      short loc_18003E5F5
0x18003e5ea  test    [rax+1Ch], bl
0x18003e5ed  jz      short loc_18003E5F5
0x18003e5ef  cmp     byte ptr [rax+19h], 4
0x18003e5f3  jnb     short loc_18003E5F7
0x18003e5f5  xor     bl, bl
0x18003e5f7  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18003e5fe  setnz   dil
0x18003e602  test    bl, bl
0x18003e604  jnz     short loc_18003E60B
0x18003e606  test    dil, dil
0x18003e609  jz      short loc_18003E63A
0x18003e60b  call    cs:__imp_GetCurrentThreadId
0x18003e611  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003e615  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003e61a  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x18003e621  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e628  mov     r9, [rcx+28h]; int
0x18003e62c  mov     r8b, dil; int
0x18003e62f  mov     dl, bl; int
0x18003e631  mov     rcx, [rcx+10h]; int
0x18003e635  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003e63a  xor     eax, eax
0x18003e63c  jmp     short loc_18003E645
0x18003e63e  mov     eax, dword ptr [rsp+0B8h+arg_8]
0x18003e645  add     rsp, 80h
0x18003e64c  pop     r15
0x18003e64e  pop     r14
0x18003e650  pop     r13
0x18003e652  pop     r12
0x18003e654  pop     rdi
0x18003e655  pop     rsi
0x18003e656  pop     rbx
0x18003e657  retn
```
