# Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>::Stop(void)

- ea: `0x18001ea90`
- end: `0x18001ed09`
- name: `?Stop@?$CFrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UIUmrdpFrameProcessorRailPrivate@Umrdp@23@@Umrdp@Avenc@Rdp@@UEAAJXZ`
- size: `633`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001c78`
- `0x1800153f8`
- `0x180015480`
- `0x18001d290`
- `0x18001ea90`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eaf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ecbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001eaf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ecbb`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>::Stop(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // bl
  bool v6; // di
  bool v7; // r14
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rcx
  __int64 v12; // rax
  const char *v13; // r9
  __int64 v14; // rcx
  bool v15; // di
  char v16; // al
  int v17; // r8d
  int v18; // edx
  __int64 result; // rax
  int v20; // [rsp+20h] [rbp-98h]
  int v21; // [rsp+20h] [rbp-98h]
  int v22; // [rsp+28h] [rbp-90h]
  int v23; // [rsp+28h] [rbp-90h]
  const char *v24; // [rsp+60h] [rbp-58h] BYREF
  __int64 v25; // [rsp+68h] [rbp-50h] BYREF
  const char *v26; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v28; // [rsp+C0h] [rbp+8h] BYREF
  int v29; // [rsp+C8h] [rbp+10h] BYREF
  const char *v30; // [rsp+D0h] [rbp+18h] BYREF
  int *v31; // [rsp+D8h] [rbp+20h] BYREF

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
      v20,
      v22,
      10,
      &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 32);
    v28 = *(_DWORD *)(v11 + 128);
    v29 = *(_DWORD *)(*(_QWORD *)(v11 + 120) + 196LL);
    v30 = "Stop Umrdp frame processor";
    v31 = &xmmword_1800C21A0;
    v24 = "RdpAvenc";
    v25 = 0x1000000;
    v26 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800ACF1D,
      a3,
      a4,
      (__int64)&v26,
      (__int64)&v25,
      (__int64)&v24,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v28);
  }
  v12 = *(_QWORD *)(a1 + 32);
  v23 = *(_DWORD *)(v12 + 128);
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"UmrdpFrameProcessorStop: Id %d",
      "Rdp::Avenc::Umrdp::CFrameProcessor<struct Rdp::Avenc::ICpuFrameProcessor,struct Rdp::Avenc::Umrdp::IUmrdpFrameProc"
      "essorRailPrivate>::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
      0x4Au);
    Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>::DestroyRdpSurface(a1 - 80);
    v14 = *(_QWORD *)(a1 + 32);
    *(_QWORD *)(a1 + 32) = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v15 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = GetCurrentThreadId();
      LOBYTE(v17) = v15;
      LOBYTE(v18) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v18,
        v17,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v21,
        v23,
        11,
        &WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids,
        v16);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x52,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\frameprocessor.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x18001ea90  push    rbx
0x18001ea92  push    rsi
0x18001ea93  push    rdi
0x18001ea94  push    r12
0x18001ea96  push    r13
0x18001ea98  push    r14
0x18001ea9a  push    r15
0x18001ea9c  sub     rsp, 80h
0x18001eaa3  mov     rsi, rcx
0x18001eaa6  lea     r12, WPP_GLOBAL_Control
0x18001eaad  mov     rax, cs:WPP_GLOBAL_Control
0x18001eab4  mov     bl, 1
0x18001eab6  cmp     rax, r12
0x18001eab9  jz      short loc_18001EACB
0x18001eabb  test    [rax+1Ch], bl
0x18001eabe  jz      short loc_18001EACB
0x18001eac0  cmp     byte ptr [rax+19h], 4
0x18001eac4  jb      short loc_18001EACB
0x18001eac6  mov     dil, bl
0x18001eac9  jmp     short loc_18001EACE
0x18001eacb  xor     dil, dil
0x18001eace  lea     r13, WPP_RECORDER_INITIALIZED
0x18001ead5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001eadc  setnz   r14b
0x18001eae0  test    dil, dil
0x18001eae3  jnz     short loc_18001EAF3
0x18001eae5  test    r14b, r14b
0x18001eae8  jnz     short loc_18001EAF3
0x18001eaea  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001eaf1  jmp     short loc_18001EB2A
0x18001eaf3  call    cs:__imp_GetCurrentThreadId
0x18001eaf9  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001eafd  lea     r15, WPP_19b31c027c473e795a0f5fbb7cb41a6c_Traceguids
0x18001eb04  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18001eb09  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x18001eb10  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb17  mov     r9, [rcx+28h]; int
0x18001eb1b  mov     r8b, r14b; int
0x18001eb1e  mov     dl, dil; int
0x18001eb21  mov     rcx, [rcx+10h]; int
0x18001eb25  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001eb2a  mov     eax, cs:dword_1800C1058
0x18001eb30  cmp     eax, 4
0x18001eb33  jbe     loc_18001EC2F
0x18001eb39  mov     rcx, cs:qword_1800C1070
0x18001eb40  mov     rax, cs:qword_1800C1068
0x18001eb47  mov     rdx, 470000000000h
0x18001eb51  test    rdx, rax
0x18001eb54  jz      loc_18001EC2F
0x18001eb5a  mov     rax, rcx
0x18001eb5d  and     rax, rdx
0x18001eb60  cmp     rax, rcx
0x18001eb63  jnz     loc_18001EC2F
0x18001eb69  mov     rcx, [rsi+20h]
0x18001eb6d  mov     eax, [rcx+80h]
0x18001eb73  mov     [rsp+0B8h+arg_0], eax
0x18001eb7a  mov     rax, [rcx+78h]
0x18001eb7e  mov     ecx, [rax+0C4h]
0x18001eb84  mov     [rsp+0B8h+arg_8], ecx
0x18001eb8b  lea     rax, aStopUmrdpFrame; "Stop Umrdp frame processor"
0x18001eb92  mov     [rsp+0B8h+arg_10], rax
0x18001eb9a  lea     rax, xmmword_1800C21A0
0x18001eba1  mov     [rsp+0B8h+arg_18], rax
0x18001eba9  lea     rax, aRdpavenc; "RdpAvenc"
0x18001ebb0  mov     [rsp+0B8h+var_58], rax
0x18001ebb5  mov     [rsp+0B8h+var_50], 1000000h
0x18001ebbe  lea     rax, aCheckpoint; "Checkpoint"
0x18001ebc5  mov     [rsp+0B8h+var_48], rax
0x18001ebca  lea     rax, [rsp+0B8h+arg_0]
0x18001ebd2  mov     [rsp+0B8h+var_68], rax
0x18001ebd7  lea     rax, [rsp+0B8h+arg_8]
0x18001ebdf  mov     [rsp+0B8h+var_70], rax
0x18001ebe4  lea     rax, [rsp+0B8h+arg_10]
0x18001ebec  mov     qword ptr [rsp+0B8h+var_78], rax
0x18001ebf1  lea     rax, [rsp+0B8h+arg_18]
0x18001ebf9  mov     [rsp+0B8h+MessageGuid], rax
0x18001ebfe  lea     rax, [rsp+0B8h+var_58]
0x18001ec03  mov     qword ptr [rsp+0B8h+var_88], rax
0x18001ec08  lea     rax, [rsp+0B8h+var_50]
0x18001ec0d  mov     qword ptr [rsp+0B8h+var_90], rax
0x18001ec12  lea     rax, [rsp+0B8h+var_48]
0x18001ec17  mov     qword ptr [rsp+0B8h+var_98], rax
0x18001ec1c  lea     rdx, byte_1800ACF1D
0x18001ec23  lea     rcx, dword_1800C1058
0x18001ec2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001ec2f  mov     rax, [rsi+20h]
0x18001ec33  mov     edx, [rax+80h]
0x18001ec39  mov     [rsp+0B8h+var_90], edx; int
0x18001ec3d  mov     [rsp+0B8h+var_98], 4Ah ; 'J'; int
0x18001ec45  lea     r9, aOnecoreuapTerm_56; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001ec4c  lea     r8, aRdpAvencUmrdpC_35; "Rdp::Avenc::Umrdp::CFrameProcessor<stru"...
0x18001ec53  lea     rdx, aUmrdpframeproc_0; "UmrdpFrameProcessorStop: Id %d"
0x18001ec5a  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001ec61  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18001ec66  lea     rcx, [rsi-50h]
0x18001ec6a  call    ?DestroyRdpSurface@?$CFrameProcessor@UICpuFrameProcessor@Avenc@Rdp@@UIUmrdpFrameProcessorRailPrivate@Umrdp@23@@Umrdp@Avenc@Rdp@@IEAAXXZ; Rdp::Avenc::Umrdp::CFrameProcessor<Rdp::Avenc::ICpuFrameProcessor,Rdp::Avenc::Umrdp::IUmrdpFrameProcessorRailPrivate>::DestroyRdpSurface(void)
0x18001ec6f  nop
0x18001ec70  mov     rcx, [rsi+20h]
0x18001ec74  mov     qword ptr [rsi+20h], 0
0x18001ec7c  test    rcx, rcx
0x18001ec7f  jz      short loc_18001EC8E
0x18001ec81  mov     rax, [rcx]
0x18001ec84  mov     rax, [rax+10h]
0x18001ec88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec8d  nop
0x18001ec8e  mov     rax, cs:WPP_GLOBAL_Control
0x18001ec95  cmp     rax, r12
0x18001ec98  jz      short loc_18001ECA5
0x18001ec9a  test    [rax+1Ch], bl
0x18001ec9d  jz      short loc_18001ECA5
0x18001ec9f  cmp     byte ptr [rax+19h], 4
0x18001eca3  jnb     short loc_18001ECA7
0x18001eca5  xor     bl, bl
0x18001eca7  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18001ecae  setnz   dil
0x18001ecb2  test    bl, bl
0x18001ecb4  jnz     short loc_18001ECBB
0x18001ecb6  test    dil, dil
0x18001ecb9  jz      short loc_18001ECEA
0x18001ecbb  call    cs:__imp_GetCurrentThreadId
0x18001ecc1  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18001ecc5  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18001ecca  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x18001ecd1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ecd8  mov     r9, [rcx+28h]; int
0x18001ecdc  mov     r8b, dil; int
0x18001ecdf  mov     dl, bl; int
0x18001ece1  mov     rcx, [rcx+10h]; int
0x18001ece5  call    WPP_RECORDER_AND_TRACE_SF_D
0x18001ecea  xor     eax, eax
0x18001ecec  jmp     short loc_18001ECF5
0x18001ecee  mov     eax, [rsp+0B8h+arg_0]
0x18001ecf5  add     rsp, 80h
0x18001ecfc  pop     r15
0x18001ecfe  pop     r14
0x18001ed00  pop     r13
0x18001ed02  pop     r12
0x18001ed04  pop     rdi
0x18001ed05  pop     rsi
0x18001ed06  pop     rbx
0x18001ed07  retn
```
