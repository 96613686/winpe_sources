# Rdp::Avenc::Umrdp::CRdpSurface::SendRdpGraphicsUpdates(std::span<Rdp::Avenc::AVENC_MOVEREGION const,-1> const &,std::span<tagRECT const,-1> const &,uint)

- ea: `0x180020b44`
- end: `0x180020e9e`
- name: `?SendRdpGraphicsUpdates@CRdpSurface@Umrdp@Avenc@Rdp@@QEAAXAEBV?$span@$$CBUAVENC_MOVEREGION@Avenc@Rdp@@$0?0@std@@AEBV?$span@$$CBUtagRECT@@$0?0@6@I@Z`
- size: `858`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b9a0`
- `0x18001be10`

## callees

- `0x18000154c`
- `0x1800080cc`
- `0x18000b07c`
- `0x180015480`
- `0x1800156d0`
- `0x180016c9c`
- `0x180018108`
- `0x1800188e4`
- `0x18001893c`
- `0x180018dc8`
- `0x180018f00`
- `0x1800199cc`
- `0x180019c04`
- `0x180019c10`
- `0x180019df0`
- `0x180020b44`
- `0x18007d7a4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020d1b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180020d1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020df0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020df0`

## string_xrefs

- `0x180020e81`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\umrdpprocessor\updatechannel.cpp`
- `0x180020e75`: `Failed to commit event %d to shared memory`
- `0x180020c0e`: `SendRdpGraphicsUpdates`
- `0x180020c19`: `Rdp::Avenc::Umrdp::CRdpSurface::SendRdpGraphicsUpdates`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Umrdp::CRdpSurface::SendRdpGraphicsUpdates(
        __int64 a1,
        __int64 *a2,
        __int64 *a3,
        unsigned int a4)
{
  char v7; // r14
  bool v8; // bl
  bool v9; // di
  char CurrentThreadId; // al
  int v11; // r8d
  int v12; // edx
  __int64 v13; // rbx
  int v14; // r8d
  int v15; // r9d
  __int64 v16; // r13
  __int64 v17; // r12
  __int64 v18; // rdi
  const char *v19; // rsi
  __int64 v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rdi
  int v23; // esi
  unsigned int v24; // r8d
  const char *v25; // r9
  volatile signed __int32 *v26; // rdi
  __int64 v27; // rdi
  __int64 v28; // rsi
  __int64 v29; // rcx
  bool v30; // di
  char v31; // al
  int v32; // r8d
  int v33; // edx
  __int64 v35; // rax
  int v36; // ebx
  __int64 v37; // rcx
  unsigned __int8 *Header; // rax
  Rdp::Modern::CTSSharedBufferProducer *v39; // rcx
  unsigned int v40; // eax
  int v41; // [rsp+20h] [rbp-49h]
  char *v42; // [rsp+28h] [rbp-41h]
  const char *v43; // [rsp+50h] [rbp-19h] BYREF
  const char *v44; // [rsp+58h] [rbp-11h] BYREF
  const char *v45; // [rsp+60h] [rbp-9h] BYREF
  volatile signed __int32 *v46; // [rsp+68h] [rbp-1h]
  __int64 v47; // [rsp+70h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  __int64 v49; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v50; // [rsp+D8h] [rbp+6Fh] BYREF
  __int64 *v51; // [rsp+E0h] [rbp+77h]
  unsigned int v52; // [rsp+E8h] [rbp+7Fh]

  v52 = a4;
  v51 = a3;
  v7 = 1;
  v8 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v9 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v8 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v11) = v9;
    LOBYTE(v12) = v8;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v12,
      v11,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v41,
      (int)v42,
      10,
      &WPP_9986a7387a103c102bc78b7336a5d55e_Traceguids,
      CurrentThreadId);
  }
  v13 = *(_QWORD *)(a1 + 32);
  v47 = v13;
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(v13, 1500);
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    LODWORD(v49) = a4;
    v43 = "SendRdpGraphicsUpdates";
    v44 = "Rdp::Avenc::Umrdp::CRdpSurface::SendRdpGraphicsUpdates";
    LODWORD(v50) = 244;
    v45 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\surface.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)qword_1800ADB08,
      v14,
      v15,
      (__int64)&v45,
      (__int64)&v50,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v49);
  }
  v16 = *a2;
  v17 = *a2 + 28 * a2[1];
  while ( v16 != v17 )
  {
    v18 = *(_QWORD *)(a1 + 32);
    v50 = v18;
    v49 = *(_QWORD *)(a1 + 64);
    if ( !*(_BYTE *)(v18 + 144) )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_SURF_TO_SURF_EVENT>(
      v18,
      &v45);
    v19 = v45;
    v20 = *((_QWORD *)v45 + 2);
    *(_DWORD *)(v20 + 16) = 2;
    v21 = v49;
    *(_QWORD *)(v20 + 20) = v49;
    *(_QWORD *)(v20 + 28) = v21;
    *(_QWORD *)(v20 + 52) = 0;
    *(_QWORD *)(v20 + 60) = Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::GetTimeHNS();
    *(_OWORD *)(v20 + 36) = *(_OWORD *)(v16 + 12);
    *(_DWORD *)(v20 + 68) = *(_DWORD *)(v16 + 4);
    *(_DWORD *)(v20 + 72) = *(_DWORD *)(v16 + 8);
    *(_DWORD *)(v20 + 100) = 0;
    v22 = v50;
    v23 = Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(
            *(Rdp::Modern::CTSSharedBufferProducer **)(v50 + 104),
            *((unsigned __int8 **)v19 + 2));
    if ( v23 < 0 )
    {
      v35 = std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(&v45);
      v36 = *(_DWORD *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v35);
      Header = (unsigned __int8 *)Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(v37);
      Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(v39, Header);
      v40 = wil::verify_hresult<long>((unsigned int)v23);
      LODWORD(v42) = v36;
      wil::details::in1diag3::Throw_HrMsg(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\updatechannel.cpp",
        (const char *)v40,
        (int)"Failed to commit event %d to shared memory",
        v42);
    }
    if ( !SetEvent(*(HANDLE *)(v22 + 112)) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v24, v25);
    v26 = v46;
    if ( v46 )
    {
      if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    v16 += 28;
  }
  v27 = *v51;
  v28 = *v51 + 16 * v51[1];
  while ( 1 )
  {
    v29 = *(_QWORD *)(a1 + 32);
    if ( v27 == v28 )
      break;
    Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendDirtyRectUpdate(
      v29,
      *(_QWORD *)(a1 + 64),
      v27);
    v27 += 16;
  }
  Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendFrameMarker(
    v29,
    v52,
    *(unsigned int *)(a1 + 56));
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v7 = 0;
  }
  v30 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v31 = GetCurrentThreadId();
    LOBYTE(v32) = v30;
    LOBYTE(v33) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v33,
      v32,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v41,
      (int)v42,
      11,
      &WPP_9986a7387a103c102bc78b7336a5d55e_Traceguids,
      v31);
  }
  return Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(v13);
}

```

## disassembly

```asm
0x180020b44  mov     [rsp-8+arg_18], r9d
0x180020b49  mov     [rsp-8+arg_10], r8
0x180020b4e  push    rbp
0x180020b4f  push    rbx
0x180020b50  push    rsi
0x180020b51  push    rdi
0x180020b52  push    r12
0x180020b54  push    r13
0x180020b56  push    r14
0x180020b58  push    r15
0x180020b5a  lea     rbp, [rsp-1Fh]
0x180020b5f  sub     rsp, 88h
0x180020b66  mov     r12d, r9d
0x180020b69  mov     rsi, rdx
0x180020b6c  mov     r15, rcx
0x180020b6f  lea     rcx, WPP_GLOBAL_Control
0x180020b76  mov     r14b, 1
0x180020b79  mov     rax, cs:WPP_GLOBAL_Control
0x180020b80  cmp     rax, rcx
0x180020b83  jz      short loc_180020B96
0x180020b85  test    [rax+1Ch], r14b
0x180020b89  jz      short loc_180020B96
0x180020b8b  cmp     byte ptr [rax+19h], 4
0x180020b8f  jb      short loc_180020B96
0x180020b91  mov     bl, r14b
0x180020b94  jmp     short loc_180020B98
0x180020b96  xor     bl, bl
0x180020b98  lea     rax, WPP_RECORDER_INITIALIZED
0x180020b9f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180020ba6  setnz   dil
0x180020baa  lea     r13, WPP_9986a7387a103c102bc78b7336a5d55e_Traceguids
0x180020bb1  test    bl, bl
0x180020bb3  jnz     short loc_180020BBA
0x180020bb5  test    dil, dil
0x180020bb8  jz      short loc_180020BE9
0x180020bba  call    cs:__imp_GetCurrentThreadId
0x180020bc0  mov     dword ptr [rsp+0C0h+var_80], eax; char
0x180020bc4  mov     [rsp+0C0h+MessageGuid], r13; MessageGuid
0x180020bc9  mov     [rsp+0C0h+var_90], 0Ah; __int16
0x180020bd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020bd7  mov     r9, [rcx+28h]; int
0x180020bdb  mov     r8b, dil; int
0x180020bde  mov     dl, bl; int
0x180020be0  mov     rcx, [rcx+10h]; int
0x180020be4  call    WPP_RECORDER_AND_TRACE_SF_D
0x180020be9  mov     rbx, [r15+20h]
0x180020bed  mov     [rbp+57h+var_50], rbx
0x180020bf1  mov     edx, 5DCh
0x180020bf6  mov     rcx, rbx
0x180020bf9  call    ?lock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(uint)
0x180020bfe  nop
0x180020bff  mov     eax, cs:dword_1800C1058
0x180020c05  cmp     eax, 5
0x180020c08  jbe     short loc_180020C76
0x180020c0a  mov     dword ptr [rbp+57h+arg_0], r12d
0x180020c0e  lea     rax, aSendrdpgraphic; "SendRdpGraphicsUpdates"
0x180020c15  mov     [rbp+57h+var_70], rax
0x180020c19  lea     rax, aRdpAvencUmrdpC_10; "Rdp::Avenc::Umrdp::CRdpSurface::SendRdp"...
0x180020c20  mov     [rbp+57h+var_68], rax
0x180020c24  mov     dword ptr [rbp+57h+arg_8], 0F4h
0x180020c2b  lea     rax, aOnecoreuapTerm_28; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180020c32  mov     [rbp+57h+var_60], rax
0x180020c36  lea     rax, [rbp+57h+arg_0]
0x180020c3a  mov     qword ptr [rsp+0C0h+var_80], rax
0x180020c3f  lea     rax, [rbp+57h+var_70]
0x180020c43  mov     [rsp+0C0h+MessageGuid], rax
0x180020c48  lea     rax, [rbp+57h+var_68]
0x180020c4c  mov     qword ptr [rsp+0C0h+var_90], rax
0x180020c51  lea     rax, [rbp+57h+arg_8]
0x180020c55  mov     [rsp+0C0h+var_98], rax
0x180020c5a  lea     rax, [rbp+57h+var_60]
0x180020c5e  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180020c63  lea     rdx, qword_1800ADB08
0x180020c6a  lea     rcx, dword_1800C1058
0x180020c71  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180020c76  mov     r13, [rsi]
0x180020c79  imul    r12, [rsi+8], 1Ch
0x180020c7e  add     r12, r13
0x180020c81  jmp     loc_180020D70
0x180020c86  mov     rdi, [r15+20h]
0x180020c8a  mov     [rbp+57h+arg_8], rdi
0x180020c8e  mov     rax, [r15+40h]
0x180020c92  mov     [rbp+57h+arg_0], rax
0x180020c96  cmp     byte ptr [rdi+90h], 0
0x180020c9d  jnz     short loc_180020CA4
0x180020c9f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180020ca4  lea     rdx, [rbp+57h+var_60]
0x180020ca8  mov     rcx, rdi
0x180020cab  call    ??$AllocSharedBufEvent@UtagUMRDP_SURF_TO_SURF_EVENT@@@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA?AV?$shared_ptr@V?$CRdpSharedBufEvent@UtagUMRDP_SURF_TO_SURF_EVENT@@@Umrdp@Avenc@Rdp@@@std@@W4UMRDP_EVENT_TYPE@@I@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::AllocSharedBufEvent<tagUMRDP_SURF_TO_SURF_EVENT>(UMRDP_EVENT_TYPE,uint)
0x180020cb0  nop
0x180020cb1  mov     rsi, [rbp+57h+var_60]
0x180020cb5  mov     rdi, [rsi+10h]
0x180020cb9  mov     dword ptr [rdi+10h], 2
0x180020cc0  mov     rax, [rbp+57h+arg_0]
0x180020cc4  mov     [rdi+14h], rax
0x180020cc8  mov     [rdi+1Ch], rax
0x180020ccc  mov     qword ptr [rdi+34h], 0
0x180020cd4  call    ?GetTimeHNS@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@AEAA_JXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::GetTimeHNS(void)
0x180020cd9  mov     [rdi+3Ch], rax
0x180020cdd  movups  xmm0, xmmword ptr [r13+0Ch]
0x180020ce2  movdqu  xmmword ptr [rdi+24h], xmm0
0x180020ce7  mov     eax, [r13+4]
0x180020ceb  mov     [rdi+44h], eax
0x180020cee  mov     eax, [r13+8]
0x180020cf2  mov     [rdi+48h], eax
0x180020cf5  mov     dword ptr [rdi+64h], 0
0x180020cfc  mov     rdx, [rsi+10h]; unsigned __int8 *
0x180020d00  mov     rdi, [rbp+57h+arg_8]
0x180020d04  mov     rcx, [rdi+68h]; this
0x180020d08  call    ?CommitBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::CommitBuffer(uchar *)
0x180020d0d  mov     esi, eax
0x180020d0f  test    eax, eax
0x180020d11  js      loc_180020E43
0x180020d17  mov     rcx, [rdi+70h]; hEvent
0x180020d1b  call    cs:__imp_SetEvent
0x180020d21  mov     rcx, [rbp+5Fh]; this
0x180020d25  test    eax, eax
0x180020d27  jz      loc_180020E93
0x180020d2d  mov     rdi, [rbp+57h+var_58]
0x180020d31  test    rdi, rdi
0x180020d34  jz      short loc_180020D6C
0x180020d36  or      esi, 0FFFFFFFFh
0x180020d39  mov     eax, esi
0x180020d3b  lock xadd [rdi+8], eax
0x180020d40  add     eax, esi
0x180020d42  jnz     short loc_180020D6C
0x180020d44  mov     rax, [rdi]
0x180020d47  mov     rcx, rdi
0x180020d4a  mov     rax, [rax]
0x180020d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d52  mov     eax, esi
0x180020d54  lock xadd [rdi+0Ch], eax
0x180020d59  add     eax, esi
0x180020d5b  jnz     short loc_180020D6C
0x180020d5d  mov     rax, [rdi]
0x180020d60  mov     rcx, rdi
0x180020d63  mov     rax, [rax+8]
0x180020d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d6c  add     r13, 1Ch
0x180020d70  cmp     r13, r12
0x180020d73  jnz     loc_180020C86
0x180020d79  mov     rax, [rbp+57h+arg_10]
0x180020d7d  mov     rdi, [rax]
0x180020d80  mov     rsi, [rax+8]
0x180020d84  shl     rsi, 4
0x180020d88  add     rsi, rdi
0x180020d8b  jmp     short loc_180020D9D
0x180020d8d  mov     r8, rdi
0x180020d90  mov     rdx, [r15+40h]
0x180020d94  call    ?SendDirtyRectUpdate@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAX_KPEBUtagRECT@@@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendDirtyRectUpdate(unsigned __int64,tagRECT const *)
0x180020d99  add     rdi, 10h
0x180020d9d  mov     rcx, [r15+20h]
0x180020da1  cmp     rdi, rsi
0x180020da4  jnz     short loc_180020D8D
0x180020da6  mov     r8d, [r15+38h]
0x180020daa  mov     edx, [rbp+57h+arg_18]
0x180020dad  call    ?SendFrameMarker@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI_K@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendFrameMarker(uint,unsigned __int64)
0x180020db2  mov     rax, cs:WPP_GLOBAL_Control
0x180020db9  lea     rcx, WPP_GLOBAL_Control
0x180020dc0  cmp     rax, rcx
0x180020dc3  jz      short loc_180020DD1
0x180020dc5  test    [rax+1Ch], r14b
0x180020dc9  jz      short loc_180020DD1
0x180020dcb  cmp     byte ptr [rax+19h], 4
0x180020dcf  jnb     short loc_180020DD4
0x180020dd1  xor     r14b, r14b
0x180020dd4  lea     rax, WPP_RECORDER_INITIALIZED
0x180020ddb  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180020de2  setnz   dil
0x180020de6  test    r14b, r14b
0x180020de9  jnz     short loc_180020DF0
0x180020deb  test    dil, dil
0x180020dee  jz      short loc_180020E28
0x180020df0  call    cs:__imp_GetCurrentThreadId
0x180020df6  mov     dword ptr [rsp+0C0h+var_80], eax; char
0x180020dfa  lea     rax, WPP_9986a7387a103c102bc78b7336a5d55e_Traceguids
0x180020e01  mov     [rsp+0C0h+MessageGuid], rax; MessageGuid
0x180020e06  mov     [rsp+0C0h+var_90], 0Bh; __int16
0x180020e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e14  mov     r9, [rcx+28h]; int
0x180020e18  mov     r8b, dil; int
0x180020e1b  mov     dl, r14b; int
0x180020e1e  mov     rcx, [rcx+10h]; int
0x180020e22  call    WPP_RECORDER_AND_TRACE_SF_D
0x180020e27  nop
0x180020e28  mov     rcx, rbx
0x180020e2b  add     rsp, 88h
0x180020e32  pop     r15
0x180020e34  pop     r14
0x180020e36  pop     r13
0x180020e38  pop     r12
0x180020e3a  pop     rdi
0x180020e3b  pop     rsi
0x180020e3c  pop     rbx
0x180020e3d  pop     rbp
0x180020e3e  jmp     ?unlock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(void)
0x180020e43  lea     rcx, [rbp+57h+var_60]
0x180020e47  call    ??$?CV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@$0A@@?$shared_ptr@V?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@@std@@QEBAPEAV?$CRdpSharedBufEvent@UUMRDP_CREATE_SURFACE_EVENT_EX@@@Umrdp@Avenc@Rdp@@XZ; std::shared_ptr<Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>>::operator-><Rdp::Avenc::Umrdp::CRdpSharedBufEvent<UMRDP_CREATE_SURFACE_EVENT_EX>,0>(void)
0x180020e4c  mov     rcx, rax
0x180020e4f  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180020e54  mov     ebx, [rax]
0x180020e56  call    ?getHeader@?$CRdpSharedBufEvent@UtagUMRDP_MAP_CURSOR_BUFFER_EVENT@@@Umrdp@Avenc@Rdp@@QEAAPEAUUMRDP_EVENT_HEADER@@XZ; Rdp::Avenc::Umrdp::CRdpSharedBufEvent<tagUMRDP_MAP_CURSOR_BUFFER_EVENT>::getHeader(void)
0x180020e5b  mov     rdx, rax; unsigned __int8 *
0x180020e5e  call    ?FreeBuffer@CTSSharedBufferProducer@Modern@Rdp@@QEAAJPEAE@Z; Rdp::Modern::CTSSharedBufferProducer::FreeBuffer(uchar *)
0x180020e63  mov     ecx, esi
0x180020e65  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180020e6a  mov     r9d, eax; char *
0x180020e6d  mov     rcx, [rbp+5Fh]; this
0x180020e71  mov     dword ptr [rsp+0C0h+var_98], ebx; char *
0x180020e75  lea     rax, aFailedToCommit; "Failed to commit event %d to shared mem"...
0x180020e7c  mov     qword ptr [rsp+0C0h+var_A0], rax; int
0x180020e81  lea     r8, aOnecoreuapTerm_36; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180020e88  mov     edx, 14Dh; void *
0x180020e8d  call    ?Throw_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_HrMsg(void *,uint,char const *,long,char const *,...)
0x180020e93  mov     edx, 0A01h; void *
0x180020e98  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
