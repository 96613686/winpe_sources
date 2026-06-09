# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::Stop(void)

- ea: `0x18004c5f0`
- end: `0x18004cb86`
- name: `?Stop@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@UEAAJXZ`
- size: `1430`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044eb0`

## callees

- `0x18000406c`
- `0x1800050dc`
- `0x1800103c0`
- `0x180010bc8`
- `0x180011490`
- `0x1800153f8`
- `0x180015480`
- `0x1800203d4`
- `0x180026f90`
- `0x180042084`
- `0x18004c5f0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c6c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004cabd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004c6c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004cabd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004caff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004c653`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004caff`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004c6d2`
- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x18004c6d2`

## string_xrefs

- `0x18004c7d0`: `DirectStreamMedia_Service`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::Stop(
        __int64 a1)
{
  char v2; // r12
  bool v3; // bl
  bool v4; // di
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  bool v8; // zf
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r14
  int v16; // r8d
  int v17; // r9d
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rcx
  bool v21; // bl
  char v22; // al
  int v23; // r8d
  int v24; // edx
  int v26; // [rsp+20h] [rbp-C8h]
  int v27; // [rsp+20h] [rbp-C8h]
  char *v28; // [rsp+28h] [rbp-C0h]
  int v29; // [rsp+28h] [rbp-C0h]
  __int16 v30[4]; // [rsp+30h] [rbp-B8h]
  LPCGUID MessageGuid; // [rsp+38h] [rbp-B0h]
  char v32[8]; // [rsp+40h] [rbp-A8h]
  __int64 v33; // [rsp+48h] [rbp-A0h]
  __int64 v34; // [rsp+50h] [rbp-98h]
  __int64 v35; // [rsp+58h] [rbp-90h]
  __int64 v36; // [rsp+60h] [rbp-88h]
  int *v37; // [rsp+80h] [rbp-68h] BYREF
  const char *v38; // [rsp+88h] [rbp-60h] BYREF
  const char *v39; // [rsp+90h] [rbp-58h] BYREF
  __int64 v40; // [rsp+98h] [rbp-50h] BYREF
  _QWORD v41[9]; // [rsp+A0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  int v43; // [rsp+F0h] [rbp+8h] BYREF
  int v44; // [rsp+F8h] [rbp+10h] BYREF
  __int64 v45; // [rsp+100h] [rbp+18h] BYREF
  const char *v46; // [rsp+108h] [rbp+20h] BYREF

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
      v26,
      (int)v28,
      12,
      &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)mtx_do_lock(a1 + 176) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 252) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 252) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  *(_BYTE *)(a1 + 352) = 1;
  v8 = (*(_DWORD *)(a1 + 252))-- == 1;
  if ( v8 )
  {
    *(_DWORD *)(a1 + 248) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 192));
  }
  WakeAllConditionVariable((PCONDITION_VARIABLE)(a1 + 264));
  if ( *(_DWORD *)(a1 + 336) )
    std::thread::join((std::thread *)(a1 + 328));
  v11 = *(_QWORD *)(a1 + 160);
  *(_QWORD *)(a1 + 160) = 0;
  if ( v11 )
  {
    v12 = v11 + 8 + *(int *)(*(_QWORD *)(v11 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v13 = *(_QWORD *)(a1 + 168);
  *(_QWORD *)(a1 + 168) = 0;
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v14 = *(_QWORD *)(a1 + 96);
    v45 = v14 + 112;
    v43 = *(_DWORD *)(*(_QWORD *)(v14 + 104) + 136LL);
    v44 = *(_DWORD *)(v14 + 128);
    v46 = "Stop Ic3 frame processor";
    v37 = &xmmword_1800C21A0;
    v38 = "DirectStreamMedia_Service";
    v39 = "RdpAvenc";
    v40 = 0x1000000;
    v41[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800B1283,
      v9,
      v10,
      (__int64)v41,
      (__int64)&v40,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v37,
      (__int64)&v46,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v45);
  }
  v15 = *(_QWORD *)(a1 + 96);
  LODWORD(v36) = *(unsigned __int8 *)(v15 + 124);
  LODWORD(v35) = *(unsigned __int8 *)(v15 + 123);
  LODWORD(v34) = *(unsigned __int8 *)(v15 + 122);
  LODWORD(v33) = *(unsigned __int8 *)(v15 + 121);
  *(_DWORD *)v32 = *(unsigned __int8 *)(v15 + 120);
  LODWORD(MessageGuid) = *(unsigned __int16 *)(v15 + 118);
  *(_DWORD *)v30 = *(unsigned __int16 *)(v15 + 116);
  LODWORD(v28) = *(_DWORD *)(v15 + 112);
  Rdp::Modern::Utils::CInflightRecorder::pushN(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    (wchar_t *)L"Ic3FrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
    "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::Stop",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    0x120u,
    v28,
    *(_QWORD *)v30,
    MessageGuid,
    *(_QWORD *)v32,
    v33,
    v34,
    v35,
    v36,
    *(unsigned __int8 *)(v15 + 125),
    *(unsigned __int8 *)(v15 + 126),
    *(unsigned __int8 *)(v15 + 127));
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v18 = *(_QWORD *)(a1 + 96);
    v46 = (const char *)(v18 + 112);
    v43 = *(_DWORD *)(*(_QWORD *)(v18 + 104) + 136LL);
    v44 = *(_DWORD *)(v18 + 128);
    v41[0] = "StopFrameProcessor";
    v40 = (__int64)"Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFram"
                   "eAsyncProcessor>::Stop";
    LODWORD(v45) = 296;
    v39 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&dword_1800B1184,
      v16,
      v17,
      (__int64)&v39,
      (__int64)&v45,
      (__int64)&v40,
      (__int64)v41,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v46);
  }
  wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
    retaddr,
    298,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    2147549183LL);
  v19 = Rdp::Avenc::Ic3::CDsGfxChannel::SendStopStreamPdu(
          *(Rdp::Avenc::Ic3::CDsGfxChannel **)(a1 + 144),
          (const struct _GUID *)(*(_QWORD *)(a1 + 96) + 112LL),
          *(_DWORD *)(*(_QWORD *)(a1 + 96) + 128LL));
  wil::details::in1diag3::Log_IfFailedMsg(
    retaddr,
    (void *)0x12D,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    (const char *)v19,
    (int)"Unable to send stop stream pdu.",
    "Direct streaming GFX channel is not set.");
  if ( (unsigned int)mtx_do_lock(a1 + 16) )
    std::_Throw_Cpp_error(5);
  if ( *(_DWORD *)(a1 + 92) == 0x7FFFFFFF )
  {
    *(_DWORD *)(a1 + 92) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  v20 = *(_QWORD *)(a1 + 96);
  *(_QWORD *)(a1 + 96) = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v8 = (*(_DWORD *)(a1 + 92))-- == 1;
  if ( v8 )
  {
    *(_DWORD *)(a1 + 88) = -1;
    ReleaseSRWLockExclusive((PSRWLOCK)(a1 + 32));
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v2 = 0;
  }
  v21 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v22 = GetCurrentThreadId();
    LOBYTE(v23) = v21;
    LOBYTE(v24) = v2;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v24,
      v23,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v27,
      v29,
      13,
      &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
      v22);
  }
  return 0;
}

```

## disassembly

```asm
0x18004c5f0  push    rbx
0x18004c5f2  push    rsi
0x18004c5f3  push    rdi
0x18004c5f4  push    r12
0x18004c5f6  push    r13
0x18004c5f8  push    r14
0x18004c5fa  push    r15
0x18004c5fc  sub     rsp, 0B0h
0x18004c603  mov     r15, rcx
0x18004c606  lea     rcx, WPP_GLOBAL_Control
0x18004c60d  mov     rax, cs:WPP_GLOBAL_Control
0x18004c614  mov     r12b, 1
0x18004c617  cmp     rax, rcx
0x18004c61a  jz      short loc_18004C62D
0x18004c61c  test    [rax+1Ch], r12b
0x18004c620  jz      short loc_18004C62D
0x18004c622  cmp     byte ptr [rax+19h], 4
0x18004c626  jb      short loc_18004C62D
0x18004c628  mov     bl, r12b
0x18004c62b  jmp     short loc_18004C62F
0x18004c62d  xor     bl, bl
0x18004c62f  lea     rax, WPP_RECORDER_INITIALIZED
0x18004c636  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004c63d  setnz   dil
0x18004c641  test    bl, bl
0x18004c643  jnz     short loc_18004C653
0x18004c645  test    dil, dil
0x18004c648  jnz     short loc_18004C653
0x18004c64a  lea     r13, WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids
0x18004c651  jmp     short loc_18004C689
0x18004c653  call    cs:__imp_GetCurrentThreadId
0x18004c659  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18004c65d  lea     r13, WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids
0x18004c664  mov     [rsp+0E8h+MessageGuid], r13; MessageGuid
0x18004c669  mov     [rsp+0E8h+var_B8], 0Ch; __int16
0x18004c670  mov     rcx, cs:WPP_GLOBAL_Control
0x18004c677  mov     r9, [rcx+28h]; int
0x18004c67b  mov     r8b, dil; int
0x18004c67e  mov     dl, bl; int
0x18004c680  mov     rcx, [rcx+10h]; int
0x18004c684  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004c689  lea     rbx, [r15+0B0h]
0x18004c690  mov     rcx, rbx
0x18004c693  call    mtx_do_lock
0x18004c698  test    eax, eax
0x18004c69a  jnz     loc_18004CB4D
0x18004c6a0  cmp     dword ptr [rbx+4Ch], 7FFFFFFFh
0x18004c6a7  jz      loc_18004CB57
0x18004c6ad  mov     [r15+160h], r12b
0x18004c6b4  sub     dword ptr [rbx+4Ch], 1
0x18004c6b8  jnz     short loc_18004C6CB
0x18004c6ba  mov     dword ptr [rbx+48h], 0FFFFFFFFh
0x18004c6c1  lea     rcx, [rbx+10h]; SRWLock
0x18004c6c5  call    cs:__imp_ReleaseSRWLockExclusive
0x18004c6cb  lea     rcx, [r15+108h]; ConditionVariable
0x18004c6d2  call    cs:__imp_WakeAllConditionVariable
0x18004c6d8  cmp     dword ptr [r15+150h], 0
0x18004c6e0  jz      short loc_18004C6EE
0x18004c6e2  lea     rcx, [r15+148h]; this
0x18004c6e9  call    ?join@thread@std@@QEAAXXZ; std::thread::join(void)
0x18004c6ee  mov     rdx, [r15+0A0h]
0x18004c6f5  mov     qword ptr [r15+0A0h], 0
0x18004c700  test    rdx, rdx
0x18004c703  jz      short loc_18004C721
0x18004c705  mov     rax, [rdx+8]
0x18004c709  movsxd  rcx, dword ptr [rax+4]
0x18004c70d  add     rdx, 8
0x18004c711  add     rcx, rdx
0x18004c714  mov     rax, [rcx]
0x18004c717  mov     rax, [rax+10h]
0x18004c71b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c720  nop
0x18004c721  mov     rcx, [r15+0A8h]
0x18004c728  mov     qword ptr [r15+0A8h], 0
0x18004c733  test    rcx, rcx
0x18004c736  jz      short loc_18004C745
0x18004c738  mov     rax, [rcx]
0x18004c73b  mov     rax, [rax+8]
0x18004c73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004c744  nop
0x18004c745  mov     eax, cs:dword_1800C1058
0x18004c74b  cmp     eax, 4
0x18004c74e  jbe     loc_18004C891
0x18004c754  mov     rcx, cs:qword_1800C1070
0x18004c75b  mov     rax, cs:qword_1800C1068
0x18004c762  mov     rdx, 470000000000h
0x18004c76c  test    rdx, rax
0x18004c76f  jz      loc_18004C891
0x18004c775  mov     rax, rcx
0x18004c778  and     rax, rdx
0x18004c77b  cmp     rax, rcx
0x18004c77e  jnz     loc_18004C891
0x18004c784  mov     rdx, [r15+60h]
0x18004c788  lea     rax, [rdx+70h]
0x18004c78c  mov     [rsp+0E8h+arg_10], rax
0x18004c794  mov     rax, [rdx+68h]
0x18004c798  mov     ecx, [rax+88h]
0x18004c79e  mov     [rsp+0E8h+arg_0], ecx
0x18004c7a5  mov     eax, [rdx+80h]
0x18004c7ab  mov     [rsp+0E8h+arg_8], eax
0x18004c7b2  lea     rax, aStopIc3FramePr; "Stop Ic3 frame processor"
0x18004c7b9  mov     [rsp+0E8h+arg_18], rax
0x18004c7c1  lea     rax, xmmword_1800C21A0
0x18004c7c8  mov     [rsp+0E8h+var_68], rax
0x18004c7d0  lea     rax, aDirectstreamme; "DirectStreamMedia_Service"
0x18004c7d7  mov     [rsp+0E8h+var_60], rax
0x18004c7df  lea     rax, aRdpavenc; "RdpAvenc"
0x18004c7e6  mov     [rsp+0E8h+var_58], rax
0x18004c7ee  mov     [rsp+0E8h+var_50], 1000000h
0x18004c7fa  lea     rax, aCheckpoint; "Checkpoint"
0x18004c801  mov     [rsp+0E8h+var_48], rax
0x18004c809  lea     rax, [rsp+0E8h+arg_10]
0x18004c811  mov     [rsp+0E8h+var_88], rax
0x18004c816  lea     rax, [rsp+0E8h+arg_0]
0x18004c81e  mov     [rsp+0E8h+var_90], rax
0x18004c823  lea     rax, [rsp+0E8h+arg_8]
0x18004c82b  mov     [rsp+0E8h+var_98], rax
0x18004c830  lea     rax, [rsp+0E8h+arg_18]
0x18004c838  mov     [rsp+0E8h+var_A0], rax
0x18004c83d  lea     rax, [rsp+0E8h+var_68]
0x18004c845  mov     qword ptr [rsp+0E8h+var_A8], rax
0x18004c84a  lea     rax, [rsp+0E8h+var_60]
0x18004c852  mov     [rsp+0E8h+MessageGuid], rax
0x18004c857  lea     rax, [rsp+0E8h+var_58]
0x18004c85f  mov     qword ptr [rsp+0E8h+var_B8], rax
0x18004c864  lea     rax, [rsp+0E8h+var_50]
0x18004c86c  mov     [rsp+0E8h+var_C0], rax
0x18004c871  lea     rax, [rsp+0E8h+var_48]
0x18004c879  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18004c87e  lea     rdx, byte_1800B1283
0x18004c885  lea     rcx, dword_1800C1058
0x18004c88c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@65@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004c891  mov     r14, [r15+60h]
0x18004c895  movzx   eax, byte ptr [r14+7Fh]
0x18004c89a  movzx   ecx, byte ptr [r14+7Eh]
0x18004c89f  movzx   edx, byte ptr [r14+7Dh]
0x18004c8a4  movzx   r8d, byte ptr [r14+7Ch]
0x18004c8a9  movzx   r9d, byte ptr [r14+7Bh]
0x18004c8ae  movzx   r10d, byte ptr [r14+7Ah]
0x18004c8b3  movzx   r11d, byte ptr [r14+79h]
0x18004c8b8  movzx   ebx, byte ptr [r14+78h]
0x18004c8bd  movzx   edi, word ptr [r14+76h]
0x18004c8c2  movzx   esi, word ptr [r14+74h]
0x18004c8c7  mov     [rsp+0E8h+var_70], eax
0x18004c8cb  mov     [rsp+0E8h+var_78], ecx
0x18004c8cf  mov     [rsp+0E8h+var_80], edx
0x18004c8d3  mov     dword ptr [rsp+0E8h+var_88], r8d
0x18004c8d8  mov     dword ptr [rsp+0E8h+var_90], r9d
0x18004c8dd  mov     dword ptr [rsp+0E8h+var_98], r10d
0x18004c8e2  mov     dword ptr [rsp+0E8h+var_A0], r11d
0x18004c8e7  mov     dword ptr [rsp+0E8h+var_A8], ebx
0x18004c8eb  mov     dword ptr [rsp+0E8h+MessageGuid], edi
0x18004c8ef  mov     dword ptr [rsp+0E8h+var_B8], esi
0x18004c8f3  mov     eax, [r14+70h]
0x18004c8f7  mov     dword ptr [rsp+0E8h+var_C0], eax
0x18004c8fb  mov     [rsp+0E8h+var_C8], 120h; unsigned int
0x18004c903  lea     rdi, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004c90a  mov     r9, rdi; char *
0x18004c90d  lea     rbx, aRdpAvencIc3Cic_7; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004c914  mov     r8, rbx; char *
0x18004c917  lea     rdx, aIc3frameproces_0; "Ic3FrameProcessorStop: Id {%08lX-%04hX-"...
0x18004c91e  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18004c925  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18004c92a  mov     eax, cs:dword_1800C1058
0x18004c930  cmp     eax, 5
0x18004c933  jbe     loc_18004C9FF
0x18004c939  mov     rdx, [r15+60h]
0x18004c93d  lea     rax, [rdx+70h]
0x18004c941  mov     [rsp+0E8h+arg_18], rax
0x18004c949  mov     rax, [rdx+68h]
0x18004c94d  mov     ecx, [rax+88h]
0x18004c953  mov     [rsp+0E8h+arg_0], ecx
0x18004c95a  mov     eax, [rdx+80h]
0x18004c960  mov     [rsp+0E8h+arg_8], eax
0x18004c967  lea     rax, aStopframeproce; "StopFrameProcessor"
0x18004c96e  mov     [rsp+0E8h+var_48], rax
0x18004c976  mov     [rsp+0E8h+var_50], rbx
0x18004c97e  mov     dword ptr [rsp+0E8h+arg_10], 128h
0x18004c989  mov     [rsp+0E8h+var_58], rdi
0x18004c991  lea     rax, [rsp+0E8h+arg_18]
0x18004c999  mov     [rsp+0E8h+var_98], rax
0x18004c99e  lea     rax, [rsp+0E8h+arg_0]
0x18004c9a6  mov     [rsp+0E8h+var_A0], rax
0x18004c9ab  lea     rax, [rsp+0E8h+arg_8]
0x18004c9b3  mov     qword ptr [rsp+0E8h+var_A8], rax
0x18004c9b8  lea     rax, [rsp+0E8h+var_48]
0x18004c9c0  mov     [rsp+0E8h+MessageGuid], rax
0x18004c9c5  lea     rax, [rsp+0E8h+var_50]
0x18004c9cd  mov     qword ptr [rsp+0E8h+var_B8], rax
0x18004c9d2  lea     rax, [rsp+0E8h+arg_10]
0x18004c9da  mov     [rsp+0E8h+var_C0], rax
0x18004c9df  lea     rax, [rsp+0E8h+var_58]
0x18004c9e7  mov     qword ptr [rsp+0E8h+var_C8], rax
0x18004c9ec  lea     rdx, dword_1800B1184
0x18004c9f3  lea     rcx, dword_1800C1058
0x18004c9fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004c9ff  lea     rbx, [r15+90h]
0x18004ca06  mov     rcx, [rsp+0E8h]
0x18004ca0e  lea     rax, aDirectStreamin; "Direct streaming GFX channel is not set"...
0x18004ca15  mov     [rsp+0E8h+var_C0], rax; int
0x18004ca1a  mov     qword ptr [rsp+0E8h+var_C8], rbx
0x18004ca1f  mov     r9d, 8000FFFFh
0x18004ca25  mov     r8, rdi
0x18004ca28  mov     edx, 12Ah
0x18004ca2d  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18004ca32  mov     r8, [r15+60h]
0x18004ca36  lea     rdx, [r8+70h]; struct _GUID *
0x18004ca3a  mov     r8d, [r8+80h]; unsigned int
0x18004ca41  mov     rcx, [rbx]; this
0x18004ca44  call    ?SendStopStreamPdu@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJAEBU_GUID@@I@Z; Rdp::Avenc::Ic3::CDsGfxChannel::SendStopStreamPdu(_GUID const &,uint)
0x18004ca49  mov     rcx, [rsp+0E8h]; this
0x18004ca51  lea     rdx, aUnableToSendSt_0; "Unable to send stop stream pdu."
0x18004ca58  mov     qword ptr [rsp+0E8h+var_C8], rdx; int
0x18004ca5d  mov     r9d, eax; char *
0x18004ca60  mov     r8, rdi; unsigned int
0x18004ca63  mov     edx, 12Dh; void *
0x18004ca68  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004ca6d  lea     rcx, [r15+10h]
0x18004ca71  call    mtx_do_lock
0x18004ca76  test    eax, eax
0x18004ca78  jnz     loc_18004CB68
0x18004ca7e  cmp     dword ptr [r15+5Ch], 7FFFFFFFh
0x18004ca86  jz      loc_18004CB72
0x18004ca8c  mov     rcx, [r15+60h]
0x18004ca90  mov     qword ptr [r15+60h], 0
0x18004ca98  test    rcx, rcx
0x18004ca9b  jz      short loc_18004CAAA
0x18004ca9d  mov     rax, [rcx]
0x18004caa0  mov     rax, [rax+10h]
0x18004caa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004caa9  nop
0x18004caaa  sub     dword ptr [r15+5Ch], 1
0x18004caaf  jnz     short loc_18004CAC3
0x18004cab1  mov     dword ptr [r15+58h], 0FFFFFFFFh
0x18004cab9  lea     rcx, [r15+20h]; SRWLock
0x18004cabd  call    cs:__imp_ReleaseSRWLockExclusive
0x18004cac3  mov     rax, cs:WPP_GLOBAL_Control
0x18004caca  lea     rcx, WPP_GLOBAL_Control
0x18004cad1  cmp     rax, rcx
0x18004cad4  jz      short loc_18004CAE2
0x18004cad6  test    [rax+1Ch], r12b
0x18004cada  jz      short loc_18004CAE2
0x18004cadc  cmp     byte ptr [rax+19h], 4
0x18004cae0  jnb     short loc_18004CAE5
0x18004cae2  xor     r12b, r12b
0x18004cae5  lea     rax, WPP_RECORDER_INITIALIZED
0x18004caec  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004caf3  setnz   bl
0x18004caf6  test    r12b, r12b
0x18004caf9  jnz     short loc_18004CAFF
0x18004cafb  test    bl, bl
0x18004cafd  jz      short loc_18004CB2F
0x18004caff  call    cs:__imp_GetCurrentThreadId
0x18004cb05  mov     dword ptr [rsp+0E8h+var_A8], eax; char
0x18004cb09  mov     [rsp+0E8h+MessageGuid], r13; MessageGuid
0x18004cb0e  mov     [rsp+0E8h+var_B8], 0Dh; __int16
0x18004cb15  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cb1c  mov     r9, [rcx+28h]; int
0x18004cb20  mov     r8b, bl; int
0x18004cb23  mov     dl, r12b; int
0x18004cb26  mov     rcx, [rcx+10h]; int
0x18004cb2a  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004cb2f  xor     eax, eax
0x18004cb31  jmp     short loc_18004CB3A
0x18004cb33  mov     eax, [rsp+0E8h+arg_0]
0x18004cb3a  add     rsp, 0B0h
0x18004cb41  pop     r15
0x18004cb43  pop     r14
0x18004cb45  pop     r13
0x18004cb47  pop     r12
0x18004cb49  pop     rdi
0x18004cb4a  pop     rsi
0x18004cb4b  pop     rbx
0x18004cb4c  retn
0x18004cb4d  mov     ecx, 5; int
0x18004cb52  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004cb57  mov     dword ptr [rbx+4Ch], 7FFFFFFEh
0x18004cb5e  mov     ecx, 6; int
0x18004cb63  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004cb68  mov     ecx, 5; int
0x18004cb6d  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18004cb72  mov     dword ptr [r15+5Ch], 7FFFFFFEh
0x18004cb7a  mov     ecx, 6; int
0x18004cb7f  call    ?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
