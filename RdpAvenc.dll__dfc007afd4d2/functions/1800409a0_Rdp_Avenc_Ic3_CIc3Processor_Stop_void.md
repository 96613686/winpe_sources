# Rdp::Avenc::Ic3::CIc3Processor::Stop(void)

- ea: `0x1800409a0`
- end: `0x180040d15`
- name: `?Stop@CIc3Processor@Ic3@Avenc@Rdp@@UEAAJXZ`
- size: `885`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CIc3Processor *__hidden this)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180003c64`
- `0x1800146bc`
- `0x1800152c4`
- `0x180015480`
- `0x1800203d4`
- `0x1800409a0`
- `0x180042868`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040a04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040a04`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040cc7`

## string_xrefs

- `0x180040aea`: `DirectStreamMedia_Service`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Ic3::CIc3Processor::Stop(Rdp::Avenc::Ic3::CIc3Processor *this)
{
  char v2; // si
  bool v3; // r14
  bool v4; // r15
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  int v8; // r8d
  int v9; // r9d
  const char *v10; // r9
  Rdp::Avenc::Ic3::CDsGfxChannel *v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  bool v18; // di
  char v19; // al
  int v20; // r8d
  int v21; // edx
  __int64 result; // rax
  int v23; // [rsp+20h] [rbp-98h]
  int v24; // [rsp+20h] [rbp-98h]
  int v25; // [rsp+28h] [rbp-90h]
  char *v26; // [rsp+28h] [rbp-90h]
  char *v27; // [rsp+30h] [rbp-88h]
  const char *v28; // [rsp+60h] [rbp-58h] BYREF
  const char *v29; // [rsp+68h] [rbp-50h] BYREF
  char v30[8]; // [rsp+70h] [rbp-48h] BYREF
  const char *v31; // [rsp+78h] [rbp-40h] BYREF
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
      v23,
      v25,
      12,
      &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v23) = *((_BYTE *)this + 152) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xF0,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      (const char *)0x8000FFFFLL,
      v23,
      (bool)"Processor is not started",
      v27);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v34 = *((_QWORD *)this + 6);
      v33 = *((_DWORD *)this + 14);
      v35 = "Stop Ic3 processor";
      v36 = &xmmword_1800C21A0;
      v28 = "DirectStreamMedia_Service";
      v29 = "RdpAvenc";
      *(_QWORD *)v30 = 0x1000000;
      v31 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800AFD43,
        v8,
        v9,
        (__int64)&v31,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v33,
        (__int64)&v34);
    }
    Rdp::Modern::Utils::CInflightRecorder::push0(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      L"Ic3ProcessorStop",
      "Rdp::Avenc::Ic3::CIc3Processor::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      0xFCu);
    v11 = (Rdp::Avenc::Ic3::CDsGfxChannel *)*((_QWORD *)this + 20);
    if ( v11 )
    {
      v12 = Rdp::Avenc::Ic3::CDsGfxChannel::Stop(v11);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x101,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)v12,
        (int)"Unable to stop DS GFX channel.",
        v26);
    }
    v13 = *((_QWORD *)this + 23);
    if ( v13 )
    {
      v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 32LL))(v13);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x107,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)v14,
        (int)"Unable to stop Debug Panel channel.",
        v26);
    }
    v15 = *((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = 0;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
    v16 = *((_QWORD *)this + 23);
    *((_QWORD *)this + 23) = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v17 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = 0;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    *((_BYTE *)this + 152) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v18 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v19 = GetCurrentThreadId();
      LOBYTE(v20) = v18;
      LOBYTE(v21) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v21,
        v20,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v24,
        (int)v26,
        13,
        &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
        v19);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x113,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
                           v10);
  }
  return result;
}

```

## disassembly

```asm
0x1800409a0  push    rsi
0x1800409a2  push    rdi
0x1800409a3  push    r12
0x1800409a5  push    r13
0x1800409a7  push    r14
0x1800409a9  push    r15
0x1800409ab  sub     rsp, 88h
0x1800409b2  mov     rdi, rcx
0x1800409b5  lea     r13, WPP_GLOBAL_Control
0x1800409bc  mov     rax, cs:WPP_GLOBAL_Control
0x1800409c3  mov     sil, 1
0x1800409c6  cmp     rax, r13
0x1800409c9  jz      short loc_1800409DC
0x1800409cb  test    [rax+1Ch], sil
0x1800409cf  jz      short loc_1800409DC
0x1800409d1  cmp     byte ptr [rax+19h], 4
0x1800409d5  jb      short loc_1800409DC
0x1800409d7  mov     r14b, sil
0x1800409da  jmp     short loc_1800409DF
0x1800409dc  xor     r14b, r14b
0x1800409df  lea     rax, WPP_RECORDER_INITIALIZED
0x1800409e6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800409ed  setnz   r15b
0x1800409f1  test    r14b, r14b
0x1800409f4  jnz     short loc_180040A04
0x1800409f6  test    r15b, r15b
0x1800409f9  jnz     short loc_180040A04
0x1800409fb  lea     r12, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x180040a02  jmp     short loc_180040A3B
0x180040a04  call    cs:__imp_GetCurrentThreadId
0x180040a0a  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180040a0e  lea     r12, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x180040a15  mov     [rsp+0B8h+MessageGuid], r12; MessageGuid
0x180040a1a  mov     word ptr [rsp+0B8h+var_88], 0Ch; char *
0x180040a21  mov     rcx, cs:WPP_GLOBAL_Control
0x180040a28  mov     r9, [rcx+28h]; int
0x180040a2c  mov     r8b, r15b; int
0x180040a2f  mov     dl, r14b; int
0x180040a32  mov     rcx, [rcx+10h]; int
0x180040a36  call    WPP_RECORDER_AND_TRACE_SF_D
0x180040a3b  cmp     byte ptr [rdi+98h], 0
0x180040a42  setz    al
0x180040a45  mov     rcx, [rsp+0B8h]; this
0x180040a4d  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180040a54  mov     [rsp+0B8h+var_90], rdx; bool
0x180040a59  mov     byte ptr [rsp+0B8h+var_98], al; int
0x180040a5d  mov     r9d, 8000FFFFh; char *
0x180040a63  lea     r14, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180040a6a  mov     r8, r14; unsigned int
0x180040a6d  mov     edx, 0F0h; void *
0x180040a72  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180040a77  mov     eax, cs:dword_1800C1058
0x180040a7d  cmp     eax, 4
0x180040a80  jbe     loc_180040B86
0x180040a86  mov     rcx, cs:qword_1800C1070
0x180040a8d  mov     rax, cs:qword_1800C1068
0x180040a94  mov     rdx, 470000000000h
0x180040a9e  test    rdx, rax
0x180040aa1  jz      loc_180040B86
0x180040aa7  mov     rax, rcx
0x180040aaa  and     rax, rdx
0x180040aad  cmp     rax, rcx
0x180040ab0  jnz     loc_180040B86
0x180040ab6  mov     rax, [rdi+30h]
0x180040aba  mov     [rsp+0B8h+arg_8], rax
0x180040ac2  mov     eax, [rdi+38h]
0x180040ac5  mov     [rsp+0B8h+arg_0], eax
0x180040acc  lea     rax, aStopIc3Process; "Stop Ic3 processor"
0x180040ad3  mov     [rsp+0B8h+arg_10], rax
0x180040adb  lea     rax, xmmword_1800C21A0
0x180040ae2  mov     [rsp+0B8h+arg_18], rax
0x180040aea  lea     rax, aDirectstreamme; "DirectStreamMedia_Service"
0x180040af1  mov     [rsp+0B8h+var_58], rax
0x180040af6  lea     rax, aRdpavenc; "RdpAvenc"
0x180040afd  mov     [rsp+0B8h+var_50], rax
0x180040b02  mov     qword ptr [rsp+0B8h+var_48], 1000000h
0x180040b0b  lea     rax, aCheckpoint; "Checkpoint"
0x180040b12  mov     [rsp+0B8h+var_40], rax
0x180040b17  lea     rax, [rsp+0B8h+arg_8]
0x180040b1f  mov     [rsp+0B8h+var_60], rax
0x180040b24  lea     rax, [rsp+0B8h+arg_0]
0x180040b2c  mov     [rsp+0B8h+var_68], rax
0x180040b31  lea     rax, [rsp+0B8h+arg_10]
0x180040b39  mov     [rsp+0B8h+var_70], rax
0x180040b3e  lea     rax, [rsp+0B8h+arg_18]
0x180040b46  mov     qword ptr [rsp+0B8h+var_78], rax
0x180040b4b  lea     rax, [rsp+0B8h+var_58]
0x180040b50  mov     [rsp+0B8h+MessageGuid], rax
0x180040b55  lea     rax, [rsp+0B8h+var_50]
0x180040b5a  mov     [rsp+0B8h+var_88], rax
0x180040b5f  lea     rax, [rsp+0B8h+var_48]
0x180040b64  mov     [rsp+0B8h+var_90], rax; int
0x180040b69  lea     rax, [rsp+0B8h+var_40]
0x180040b6e  mov     qword ptr [rsp+0B8h+var_98], rax
0x180040b73  lea     rdx, byte_1800AFD43
0x180040b7a  lea     rcx, dword_1800C1058
0x180040b81  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180040b86  mov     [rsp+0B8h+var_98], 0FCh; unsigned int
0x180040b8e  mov     r9, r14; char *
0x180040b91  lea     r8, aRdpAvencIc3Cic_17; "Rdp::Avenc::Ic3::CIc3Processor::Stop"
0x180040b98  lea     rdx, aIc3processorst_0; "Ic3ProcessorStop"
0x180040b9f  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180040ba6  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180040bab  mov     rcx, [rdi+0A0h]; this
0x180040bb2  test    rcx, rcx
0x180040bb5  jz      short loc_180040BE0
0x180040bb7  call    ?Stop@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJXZ; Rdp::Avenc::Ic3::CDsGfxChannel::Stop(void)
0x180040bbc  mov     rcx, [rsp+0B8h]; this
0x180040bc4  lea     rdx, aUnableToStopDs; "Unable to stop DS GFX channel."
0x180040bcb  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180040bd0  mov     r9d, eax; char *
0x180040bd3  mov     r8, r14; unsigned int
0x180040bd6  mov     edx, 101h; void *
0x180040bdb  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180040be0  mov     rcx, [rdi+0B8h]
0x180040be7  test    rcx, rcx
0x180040bea  jz      short loc_180040C1D
0x180040bec  mov     rax, [rcx]
0x180040bef  mov     rax, [rax+20h]
0x180040bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040bf8  mov     rcx, [rsp+0B8h]; this
0x180040c00  lea     rdx, aUnableToStopDe; "Unable to stop Debug Panel channel."
0x180040c07  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180040c0c  mov     r9d, eax; char *
0x180040c0f  mov     r8, r14; unsigned int
0x180040c12  mov     edx, 107h; void *
0x180040c17  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180040c1c  nop
0x180040c1d  mov     rcx, [rdi+0A0h]
0x180040c24  mov     qword ptr [rdi+0A0h], 0
0x180040c2f  test    rcx, rcx
0x180040c32  jz      short loc_180040C41
0x180040c34  mov     rax, [rcx]
0x180040c37  mov     rax, [rax+10h]
0x180040c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c40  nop
0x180040c41  mov     rcx, [rdi+0B8h]
0x180040c48  mov     qword ptr [rdi+0B8h], 0
0x180040c53  test    rcx, rcx
0x180040c56  jz      short loc_180040C65
0x180040c58  mov     rax, [rcx]
0x180040c5b  mov     rax, [rax+10h]
0x180040c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c64  nop
0x180040c65  mov     rcx, [rdi+0A8h]
0x180040c6c  mov     qword ptr [rdi+0A8h], 0
0x180040c77  test    rcx, rcx
0x180040c7a  jz      short loc_180040C89
0x180040c7c  mov     rax, [rcx]
0x180040c7f  mov     rax, [rax+10h]
0x180040c83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040c88  nop
0x180040c89  mov     byte ptr [rdi+98h], 0
0x180040c90  mov     rax, cs:WPP_GLOBAL_Control
0x180040c97  cmp     rax, r13
0x180040c9a  jz      short loc_180040CA8
0x180040c9c  test    [rax+1Ch], sil
0x180040ca0  jz      short loc_180040CA8
0x180040ca2  cmp     byte ptr [rax+19h], 4
0x180040ca6  jnb     short loc_180040CAB
0x180040ca8  xor     sil, sil
0x180040cab  lea     rax, WPP_RECORDER_INITIALIZED
0x180040cb2  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180040cb9  setnz   dil
0x180040cbd  test    sil, sil
0x180040cc0  jnz     short loc_180040CC7
0x180040cc2  test    dil, dil
0x180040cc5  jz      short loc_180040CF7
0x180040cc7  call    cs:__imp_GetCurrentThreadId
0x180040ccd  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180040cd1  mov     [rsp+0B8h+MessageGuid], r12; MessageGuid
0x180040cd6  mov     word ptr [rsp+0B8h+var_88], 0Dh; __int16
0x180040cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180040ce4  mov     r9, [rcx+28h]; int
0x180040ce8  mov     r8b, dil; int
0x180040ceb  mov     dl, sil; int
0x180040cee  mov     rcx, [rcx+10h]; int
0x180040cf2  call    WPP_RECORDER_AND_TRACE_SF_D
0x180040cf7  xor     eax, eax
0x180040cf9  jmp     short loc_180040D02
0x180040cfb  mov     eax, [rsp+0B8h+arg_0]
0x180040d02  add     rsp, 88h
0x180040d09  pop     r15
0x180040d0b  pop     r14
0x180040d0d  pop     r13
0x180040d0f  pop     r12
0x180040d11  pop     rdi
0x180040d12  pop     rsi
0x180040d13  retn
```
