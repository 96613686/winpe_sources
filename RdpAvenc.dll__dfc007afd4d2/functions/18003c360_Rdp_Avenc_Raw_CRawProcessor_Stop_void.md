# Rdp::Avenc::Raw::CRawProcessor::Stop(void)

- ea: `0x18003c360`
- end: `0x18003c5e3`
- name: `?Stop@CRawProcessor@Raw@Avenc@Rdp@@UEAAJXZ`
- size: `643`
- prototype: `__int64 __fastcall(Rdp::Avenc::Raw::CRawProcessor *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800019f0`
- `0x18000e760`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`
- `0x18003c360`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c3c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c595`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c3c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c595`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Raw::CRawProcessor::Stop(Rdp::Avenc::Raw::CRawProcessor *this)
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
  bool v11; // di
  char v12; // al
  int v13; // r8d
  int v14; // edx
  __int64 result; // rax
  int v16; // [rsp+20h] [rbp-98h]
  int v17; // [rsp+20h] [rbp-98h]
  int v18; // [rsp+28h] [rbp-90h]
  int v19; // [rsp+28h] [rbp-90h]
  char *v20; // [rsp+30h] [rbp-88h]
  const char *v21; // [rsp+60h] [rbp-58h] BYREF
  int v22[2]; // [rsp+68h] [rbp-50h] BYREF
  const char *v23; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v25; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v26; // [rsp+C8h] [rbp+10h] BYREF
  const char *v27; // [rsp+D0h] [rbp+18h] BYREF
  int *v28; // [rsp+D8h] [rbp+20h] BYREF

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
      v16,
      v18,
      12,
      &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v16) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x5A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v16,
      (bool)"Processor is not started",
      v20);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v26 = *((_QWORD *)this + 9);
      v25 = *((_DWORD *)this + 20);
      v27 = "Stop Raw processor";
      v28 = &xmmword_1800C21A0;
      v21 = "RdpAvenc";
      *(_QWORD *)v22 = 0x1000000;
      v23 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800AF7A1,
        v8,
        v9,
        (__int64)&v23,
        (__int64)v22,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&v26);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"RawProcessorStop",
      "Rdp::Avenc::Raw::CRawProcessor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      0x65u);
    Rdp::Utils::TP::CThreadPool::Shutdown((Rdp::Avenc::Raw::CRawProcessor *)((char *)this + 192));
    *((_BYTE *)this + 176) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v11 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = GetCurrentThreadId();
      LOBYTE(v13) = v11;
      LOBYTE(v14) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v14,
        v13,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v17,
        v19,
        13,
        &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
        v12);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x6E,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x18003c360  push    rbx
0x18003c362  push    rsi
0x18003c363  push    rdi
0x18003c364  push    r12
0x18003c366  push    r13
0x18003c368  push    r14
0x18003c36a  push    r15
0x18003c36c  sub     rsp, 80h
0x18003c373  mov     rsi, rcx
0x18003c376  lea     r12, WPP_GLOBAL_Control
0x18003c37d  mov     rax, cs:WPP_GLOBAL_Control
0x18003c384  mov     bl, 1
0x18003c386  cmp     rax, r12
0x18003c389  jz      short loc_18003C39B
0x18003c38b  test    [rax+1Ch], bl
0x18003c38e  jz      short loc_18003C39B
0x18003c390  cmp     byte ptr [rax+19h], 4
0x18003c394  jb      short loc_18003C39B
0x18003c396  mov     dil, bl
0x18003c399  jmp     short loc_18003C39E
0x18003c39b  xor     dil, dil
0x18003c39e  lea     r13, WPP_RECORDER_INITIALIZED
0x18003c3a5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003c3ac  setnz   r14b
0x18003c3b0  test    dil, dil
0x18003c3b3  jnz     short loc_18003C3C3
0x18003c3b5  test    r14b, r14b
0x18003c3b8  jnz     short loc_18003C3C3
0x18003c3ba  lea     r15, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003c3c1  jmp     short loc_18003C3FA
0x18003c3c3  call    cs:__imp_GetCurrentThreadId
0x18003c3c9  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003c3cd  lea     r15, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x18003c3d4  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003c3d9  mov     word ptr [rsp+0B8h+var_88], 0Ch; char *
0x18003c3e0  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c3e7  mov     r9, [rcx+28h]; int
0x18003c3eb  mov     r8b, r14b; int
0x18003c3ee  mov     dl, dil; int
0x18003c3f1  mov     rcx, [rcx+10h]; int
0x18003c3f5  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003c3fa  cmp     byte ptr [rsi+0B0h], 0
0x18003c401  setz    al
0x18003c404  mov     rcx, [rsp+0B8h]; this
0x18003c40c  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18003c413  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x18003c418  mov     byte ptr [rsp+0B8h+var_98], al; int
0x18003c41c  mov     r9d, 8000FFFFh; char *
0x18003c422  lea     r8, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c429  mov     edx, 5Ah ; 'Z'; void *
0x18003c42e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003c433  mov     eax, cs:dword_1800C1058
0x18003c439  cmp     eax, 4
0x18003c43c  jbe     loc_18003C52C
0x18003c442  mov     rcx, cs:qword_1800C1070
0x18003c449  mov     rax, cs:qword_1800C1068
0x18003c450  mov     rdx, 470000000000h
0x18003c45a  test    rdx, rax
0x18003c45d  jz      loc_18003C52C
0x18003c463  mov     rax, rcx
0x18003c466  and     rax, rdx
0x18003c469  cmp     rax, rcx
0x18003c46c  jnz     loc_18003C52C
0x18003c472  mov     rax, [rsi+48h]
0x18003c476  mov     [rsp+0B8h+arg_8], rax
0x18003c47e  mov     eax, [rsi+50h]
0x18003c481  mov     [rsp+0B8h+arg_0], eax
0x18003c488  lea     rax, aStopRawProcess; "Stop Raw processor"
0x18003c48f  mov     [rsp+0B8h+arg_10], rax
0x18003c497  lea     rax, xmmword_1800C21A0
0x18003c49e  mov     [rsp+0B8h+arg_18], rax
0x18003c4a6  lea     rax, aRdpavenc; "RdpAvenc"
0x18003c4ad  mov     [rsp+0B8h+var_58], rax
0x18003c4b2  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x18003c4bb  lea     rax, aCheckpoint; "Checkpoint"
0x18003c4c2  mov     [rsp+0B8h+var_48], rax
0x18003c4c7  lea     rax, [rsp+0B8h+arg_8]
0x18003c4cf  mov     [rsp+0B8h+var_68], rax
0x18003c4d4  lea     rax, [rsp+0B8h+arg_0]
0x18003c4dc  mov     [rsp+0B8h+var_70], rax
0x18003c4e1  lea     rax, [rsp+0B8h+arg_10]
0x18003c4e9  mov     qword ptr [rsp+0B8h+var_78], rax
0x18003c4ee  lea     rax, [rsp+0B8h+arg_18]
0x18003c4f6  mov     [rsp+0B8h+MessageGuid], rax
0x18003c4fb  lea     rax, [rsp+0B8h+var_58]
0x18003c500  mov     [rsp+0B8h+var_88], rax
0x18003c505  lea     rax, [rsp+0B8h+var_50]
0x18003c50a  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x18003c50f  lea     rax, [rsp+0B8h+var_48]
0x18003c514  mov     qword ptr [rsp+0B8h+var_98], rax
0x18003c519  lea     rdx, byte_1800AF7A1
0x18003c520  lea     rcx, dword_1800C1058
0x18003c527  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003c52c  mov     [rsp+0B8h+var_98], 65h ; 'e'; int
0x18003c534  lea     r9, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003c53b  lea     r8, aRdpAvencRawCra_5; "Rdp::Avenc::Raw::CRawProcessor::Stop"
0x18003c542  lea     rdx, aRawprocessorst; "RawProcessorStop"
0x18003c549  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003c550  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18003c555  lea     rcx, [rsi+0C0h]; this
0x18003c55c  call    ?Shutdown@CThreadPool@TP@Utils@Rdp@@QEAAXXZ; Rdp::Utils::TP::CThreadPool::Shutdown(void)
0x18003c561  mov     byte ptr [rsi+0B0h], 0
0x18003c568  mov     rax, cs:WPP_GLOBAL_Control
0x18003c56f  cmp     rax, r12
0x18003c572  jz      short loc_18003C57F
0x18003c574  test    [rax+1Ch], bl
0x18003c577  jz      short loc_18003C57F
0x18003c579  cmp     byte ptr [rax+19h], 4
0x18003c57d  jnb     short loc_18003C581
0x18003c57f  xor     bl, bl
0x18003c581  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x18003c588  setnz   dil
0x18003c58c  test    bl, bl
0x18003c58e  jnz     short loc_18003C595
0x18003c590  test    dil, dil
0x18003c593  jz      short loc_18003C5C4
0x18003c595  call    cs:__imp_GetCurrentThreadId
0x18003c59b  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003c59f  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003c5a4  mov     word ptr [rsp+0B8h+var_88], 0Dh; __int16
0x18003c5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c5b2  mov     r9, [rcx+28h]; int
0x18003c5b6  mov     r8b, dil; int
0x18003c5b9  mov     dl, bl; int
0x18003c5bb  mov     rcx, [rcx+10h]; int
0x18003c5bf  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003c5c4  xor     eax, eax
0x18003c5c6  jmp     short loc_18003C5CF
0x18003c5c8  mov     eax, [rsp+0B8h+arg_0]
0x18003c5cf  add     rsp, 80h
0x18003c5d6  pop     r15
0x18003c5d8  pop     r14
0x18003c5da  pop     r13
0x18003c5dc  pop     r12
0x18003c5de  pop     rdi
0x18003c5df  pop     rsi
0x18003c5e0  pop     rbx
0x18003c5e1  retn
```
