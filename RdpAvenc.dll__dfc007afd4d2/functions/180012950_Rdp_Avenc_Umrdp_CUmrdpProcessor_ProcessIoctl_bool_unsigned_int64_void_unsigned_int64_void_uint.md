# Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl(bool,unsigned __int64,void *,unsigned __int64,void *,uint *)

- ea: `0x180012950`
- end: `0x18001325e`
- name: `?ProcessIoctl@CUmrdpProcessor@Umrdp@Avenc@Rdp@@UEAAJ_N_KPEAX12PEAI@Z`
- size: `2318`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CUmrdpProcessor *this, char, unsigned __int64, struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_SET_UPDATE_CHANNEL *, unsigned __int64, void *, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, installer_update`

## callees

- `0x180001664`
- `0x18000178c`
- `0x1800019f0`
- `0x180001b2c`
- `0x18001143c`
- `0x180012950`
- `0x180013264`
- `0x180013878`
- `0x1800146bc`
- `0x180014710`
- `0x1800152c4`
- `0x1800153f8`
- `0x180015480`
- `0x180019020`
- `0x180019c10`
- `0x180019df0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800129b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800130a5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800129b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800130a5`

## string_xrefs

- `0x18001320e`: `RDPAVENC_OPCODE_SET_UPDATE_CHANNEL is requested by non-privileged process`
- `0x180013239`: `Input buffer size is too small to cast to RDPAVENV_OPCODE_SET_UPDATE_CHANNEL`
- `0x180012f96`: `Receive RDPAVENC_OPCODE_SET_UPDATE_CHANNEL`
- `0x18001304a`: `SetUpdateChannel`
- `0x180012cb8`: `Gfx update channel is not initialized`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl(
        Rdp::Avenc::Umrdp::CUmrdpProcessor *this,
        char a2,
        unsigned __int64 a3,
        struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_SET_UPDATE_CHANNEL *a4,
        unsigned __int64 a5,
        void *a6,
        unsigned int *a7)
{
  char v10; // r14
  bool v11; // r12
  bool v12; // r13
  char CurrentThreadId; // al
  int v14; // r8d
  int v15; // edx
  unsigned int *v16; // r13
  int v17; // r8d
  const char *v18; // r9
  __int64 v19; // rbx
  bool v20; // bl
  char v21; // al
  int v22; // r8d
  int v23; // edx
  __int64 result; // rax
  int v25; // [rsp+20h] [rbp-A8h]
  int v26; // [rsp+20h] [rbp-A8h]
  int v27; // [rsp+20h] [rbp-A8h]
  int v28; // [rsp+28h] [rbp-A0h]
  char *v29; // [rsp+28h] [rbp-A0h]
  char *v30; // [rsp+30h] [rbp-98h]
  char *v31; // [rsp+30h] [rbp-98h]
  __int64 v32; // [rsp+60h] [rbp-68h] BYREF
  char v33[8]; // [rsp+68h] [rbp-60h] BYREF
  const char *v34; // [rsp+70h] [rbp-58h] BYREF
  const char *v35; // [rsp+78h] [rbp-50h] BYREF
  const char *v36; // [rsp+80h] [rbp-48h] BYREF
  __int64 v37; // [rsp+88h] [rbp-40h] BYREF
  _QWORD v38[7]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  __int64 v40; // [rsp+D0h] [rbp+8h] BYREF
  char v41; // [rsp+D8h] [rbp+10h]

  v41 = a2;
  v10 = 1;
  v11 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
     && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
     && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v14) = v12;
    LOBYTE(v15) = v11;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v15,
      v14,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v25,
      v28,
      20,
      &WPP_44e245a864023212cc554d824265b257_Traceguids,
      CurrentThreadId);
  }
  try
  {
    LOBYTE(v25) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x188,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v25,
      (bool)"Processor is not started",
      v30);
    v29 = "BytesWritten can't ne null";
    v16 = a7;
    v26 = (int)a7;
    wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(
      retaddr,
      393,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      2147500035LL);
    if ( a3 < 0xC )
      wil::details::in1diag3::Throw_NtStatusMsg(
        retaddr,
        (void *)0x18F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
        (const char *)0xC0000023LL,
        (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_HEADER",
        "BytesWritten can't ne null");
    *v16 = 0;
    switch ( *((_DWORD *)a4 + 2) )
    {
      case 1:
        if ( !v41 )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x19E,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
            (const char *)0xC0000022LL,
            (int)"RDPAVENC_OPCODE_SET_UPDATE_CHANNEL is requested by non-privileged process",
            "BytesWritten can't ne null");
        if ( a3 < 0xA38 )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x1A6,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
            (const char *)0xC0000023LL,
            (int)"Input buffer size is too small to cast to RDPAVENV_OPCODE_SET_UPDATE_CHANNEL",
            "BytesWritten can't ne null");
        if ( (unsigned int)dword_1800C1058 > 4
          && (qword_1800C1068 & 0x470000000000LL) != 0
          && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
        {
          v38[0] = *(_QWORD *)((char *)this + 108);
          LODWORD(v40) = *((_DWORD *)this + 29);
          v36 = "Receive RDPAVENC_OPCODE_SET_UPDATE_CHANNEL";
          v35 = (const char *)&xmmword_1800C21A0;
          v34 = "RdpAvenc";
          *(_QWORD *)v33 = 0x1000000;
          v32 = (__int64)"Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)&dword_1800AC694,
            v17,
            (_DWORD)v18,
            (__int64)&v32,
            (__int64)v33,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v36,
            (__int64)&v40,
            (__int64)v38);
        }
        Rdp::Modern::Utils::CInflightRecorder::push0(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          L"SetUpdateChannel",
          "Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
          0x1AFu);
        Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessSetUpdateChannel(
          (Rdp::Avenc::Umrdp::CUmrdpProcessor *)((char *)this - 80),
          a4);
        break;
      case 2:
        if ( a3 < 0x10 )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x1BF,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
            (const char *)0xC0000023LL,
            (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_SET_GPU_ENCODE_MODE",
            "BytesWritten can't ne null");
        if ( (unsigned int)dword_1800C1058 > 4
          && (qword_1800C1068 & 0x470000000000LL) != 0
          && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
        {
          LODWORD(v40) = *((_DWORD *)a4 + 3);
          v36 = *(const char **)((char *)this + 108);
          LODWORD(v32) = *((_DWORD *)this + 29);
          v35 = "Receive RDPAVENC_OPCODE_SET_GPU_ENCODE_MODE";
          v34 = (const char *)&xmmword_1800C21A0;
          *(_QWORD *)v33 = "RdpAvenc";
          v37 = 0x1000000;
          v38[0] = "Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)word_1800AC622,
            v17,
            (_DWORD)v18,
            (__int64)v38,
            (__int64)&v37,
            (__int64)v33,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v32,
            (__int64)&v36,
            (__int64)&v40);
        }
        LODWORD(v29) = *((_DWORD *)a4 + 3);
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"SetGpuEncodeMode: %d",
          "Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
          0x1CBu);
        *((_BYTE *)this + 126) = *((_DWORD *)a4 + 3) == 0;
        break;
      case 3:
        if ( a3 < 0x4C )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x1D6,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
            (const char *)0xC0000023LL,
            (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_TAG_FRAME_REQ",
            "BytesWritten can't ne null");
        if ( (unsigned int)dword_1800C1058 > 5 )
        {
          v36 = *(const char **)((char *)this + 108);
          LODWORD(v40) = *((_DWORD *)this + 29);
          v35 = "Receive RDPAVENC_OPCODE_TAG_FRAME_REQ";
          v34 = "Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl";
          LODWORD(v32) = 480;
          *(_QWORD *)v33 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)byte_1800AC5BD,
            (unsigned int)"Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl",
            (_DWORD)v18,
            (__int64)v33,
            (__int64)&v32,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v40,
            (__int64)&v36);
        }
        Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessTagFrame(
          (Rdp::Avenc::Umrdp::CUmrdpProcessor *)((char *)this - 80),
          a4);
        break;
      case 5:
        if ( a3 < 0x458 )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x1EE,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
            (const char *)0xC0000023LL,
            (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_MMR_DATA",
            "BytesWritten can't ne null");
        if ( (unsigned int)dword_1800C1058 > 4
          && (qword_1800C1068 & 0x470000000000LL) != 0
          && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
        {
          v36 = *(const char **)((char *)this + 108);
          LODWORD(v40) = *((_DWORD *)this + 29);
          v35 = "Receive RDPAVENC_OPCODE_MMR_DATA";
          v34 = (const char *)&xmmword_1800C21A0;
          *(_QWORD *)v33 = "RdpAvenc";
          v32 = 0x1000000;
          v37 = (__int64)"Checkpoint";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)word_1800AC55A,
            v17,
            (_DWORD)v18,
            (__int64)&v37,
            (__int64)&v32,
            (__int64)v33,
            (__int64)&v34,
            (__int64)&v35,
            (__int64)&v40,
            (__int64)&v36);
        }
        Rdp::Modern::Utils::CInflightRecorder::pushN(
          (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
          (wchar_t *)L"Receive RDPAVENC_OPCODE_MMR_DATA",
          "Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl",
          "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
          0x1F9u);
        LOBYTE(v27) = *((_QWORD *)this + 7) == 0;
        wil::details::in1diag3::Throw_HrIfMsg(
          retaddr,
          (void *)0x339,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
          (const char *)0x80070057LL,
          v27,
          (bool)"Gfx update channel is not initialized",
          v31);
        v19 = *((_QWORD *)this + 7);
        v40 = v19;
        Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(v19, 1500);
        Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMMRHint(
          *((_QWORD *)this + 7),
          a4);
        Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(v19);
        break;
      case 0x100:
        if ( a3 < 0x10 )
          wil::details::in1diag3::Throw_NtStatusMsg(
            retaddr,
            (void *)0x207,
            (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
            (const char *)0xC0000023LL,
            (int)"Input buffer size is too small to cast to RDPAVENC_OPCODE_CONTROL_GRAPHICS_PROCESSING",
            "BytesWritten can't ne null");
        if ( (unsigned int)dword_1800C1058 > 4 )
        {
          LODWORD(v40) = *((_DWORD *)a4 + 3);
          *(_QWORD *)v33 = *(_QWORD *)((char *)this + 108);
          LODWORD(v37) = *((_DWORD *)this + 29);
          v34 = "Receive RDPAVENC_OPCODE_CONTROL_GRAPHICS_PROCESSING";
          v35 = "Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl";
          LODWORD(v32) = 530;
          v36 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800C1058,
            (unsigned int)word_1800AC4DA,
            (unsigned int)"Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessIoctl",
            (_DWORD)v18,
            (__int64)&v36,
            (__int64)&v32,
            (__int64)&v35,
            (__int64)&v34,
            (__int64)&v37,
            (__int64)v33,
            (__int64)&v40);
        }
        *((_BYTE *)this + 104) = *((_DWORD *)a4 + 3) != 0;
        break;
      default:
        LODWORD(v29) = *((_DWORD *)a4 + 2);
        wil::details::in1diag3::Throw_NtStatusMsg(
          retaddr,
          (void *)0x218,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
          (const char *)0xC00000BBLL,
          (int)"Unknown Ioctl 0x%lx",
          v29);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v10 = 0;
    }
    v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = GetCurrentThreadId();
      LOBYTE(v22) = v20;
      LOBYTE(v23) = v10;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        v22,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v26,
        (int)v29,
        21,
        &WPP_44e245a864023212cc554d824265b257_Traceguids,
        v21);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x222,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x180012950  mov     [rsp+arg_10], rbx
0x180012955  mov     [rsp+arg_8], dl
0x180012959  push    rsi
0x18001295a  push    r12
0x18001295c  push    r13
0x18001295e  push    r14
0x180012960  push    r15
0x180012962  sub     rsp, 0A0h
0x180012969  mov     r15, r9
0x18001296c  mov     rbx, r8
0x18001296f  mov     rsi, rcx
0x180012972  lea     rcx, WPP_GLOBAL_Control
0x180012979  mov     rax, cs:WPP_GLOBAL_Control
0x180012980  mov     r14b, 1
0x180012983  cmp     rax, rcx
0x180012986  jz      short loc_180012999
0x180012988  test    [rax+1Ch], r14b
0x18001298c  jz      short loc_180012999
0x18001298e  cmp     byte ptr [rax+19h], 4
0x180012992  jb      short loc_180012999
0x180012994  mov     r12b, r14b
0x180012997  jmp     short loc_18001299C
0x180012999  xor     r12b, r12b
0x18001299c  lea     rax, WPP_RECORDER_INITIALIZED
0x1800129a3  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800129aa  setnz   r13b
0x1800129ae  test    r12b, r12b
0x1800129b1  jnz     short loc_1800129B8
0x1800129b3  test    r13b, r13b
0x1800129b6  jz      short loc_1800129EF
0x1800129b8  call    cs:__imp_GetCurrentThreadId
0x1800129be  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x1800129c2  lea     rax, WPP_44e245a864023212cc554d824265b257_Traceguids
0x1800129c9  mov     [rsp+0C8h+MessageGuid], rax; MessageGuid
0x1800129ce  mov     word ptr [rsp+0C8h+var_98], 14h; char *
0x1800129d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800129dc  mov     r9, [rcx+28h]; int
0x1800129e0  mov     r8b, r13b; int
0x1800129e3  mov     dl, r12b; int
0x1800129e6  mov     rcx, [rcx+10h]; int
0x1800129ea  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800129ef  cmp     byte ptr [rsi+10h], 0
0x1800129f3  setz    al
0x1800129f6  mov     rcx, [rsp+0C8h]; this
0x1800129fe  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180012a05  mov     [rsp+0C8h+var_A0], rdx; bool
0x180012a0a  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x180012a0e  mov     r9d, 8000FFFFh; char *
0x180012a14  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180012a1b  mov     edx, 188h; void *
0x180012a20  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180012a25  mov     rcx, [rsp+0C8h]
0x180012a2d  lea     rax, aByteswrittenCa_0; "BytesWritten can't ne null"
0x180012a34  mov     [rsp+0C8h+var_A0], rax; char *
0x180012a39  mov     r13, [rsp+0C8h+arg_30]
0x180012a41  mov     qword ptr [rsp+0C8h+var_A8], r13
0x180012a46  mov     r9d, 80004003h
0x180012a4c  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180012a53  mov     edx, 189h
0x180012a58  call    ??$Throw_HrIfNullMsg@PEAX$0A@@in1diag3@details@wil@@YAPEAXPEAXIPEBDJ01ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<void *,0>(void *,uint,char const *,long,void *,char const *,...)
0x180012a5d  cmp     rbx, 0Ch
0x180012a61  jb      loc_180013100
0x180012a67  mov     dword ptr [r13+0], 0
0x180012a6f  mov     edx, [r15+8]
0x180012a73  mov     eax, edx
0x180012a75  sub     eax, 1
0x180012a78  jz      loc_180012F26
0x180012a7e  sub     eax, 1
0x180012a81  jz      loc_180012DD0
0x180012a87  sub     eax, 1
0x180012a8a  jz      loc_180012D0F
0x180012a90  sub     eax, 2
0x180012a93  jz      loc_180012B7C
0x180012a99  cmp     eax, 0FBh
0x180012a9e  jnz     loc_18001312B
0x180012aa4  cmp     rbx, 10h
0x180012aa8  jb      loc_18001315A
0x180012aae  mov     eax, cs:dword_1800C1058
0x180012ab4  cmp     eax, 4
0x180012ab7  jbe     loc_180012B6C
0x180012abd  mov     eax, [r15+0Ch]
0x180012ac1  mov     dword ptr [rsp+0C8h+arg_0], eax
0x180012ac8  mov     rax, [rsi+6Ch]
0x180012acc  mov     qword ptr [rsp+0C8h+var_60], rax
0x180012ad1  mov     eax, [rsi+74h]
0x180012ad4  mov     dword ptr [rsp+0C8h+var_40], eax
0x180012adb  lea     rax, aReceiveRdpaven_3; "Receive RDPAVENC_OPCODE_CONTROL_GRAPHIC"...
0x180012ae2  mov     [rsp+0C8h+var_58], rax
0x180012ae7  lea     r8, aRdpAvencUmrdpC_31; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Pro"...
0x180012aee  mov     [rsp+0C8h+var_50], r8
0x180012af3  mov     dword ptr [rsp+0C8h+var_68], 212h
0x180012afb  lea     rax, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180012b02  mov     [rsp+0C8h+var_48], rax
0x180012b0a  lea     rax, [rsp+0C8h+arg_0]
0x180012b12  mov     [rsp+0C8h+var_78], rax
0x180012b17  lea     rax, [rsp+0C8h+var_60]
0x180012b1c  mov     [rsp+0C8h+var_80], rax
0x180012b21  lea     rax, [rsp+0C8h+var_40]
0x180012b29  mov     qword ptr [rsp+0C8h+var_88], rax
0x180012b2e  lea     rax, [rsp+0C8h+var_58]
0x180012b33  mov     [rsp+0C8h+MessageGuid], rax
0x180012b38  lea     rax, [rsp+0C8h+var_50]
0x180012b3d  mov     [rsp+0C8h+var_98], rax
0x180012b42  lea     rax, [rsp+0C8h+var_68]
0x180012b47  mov     [rsp+0C8h+var_A0], rax
0x180012b4c  lea     rax, [rsp+0C8h+var_48]
0x180012b54  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180012b59  lea     rdx, word_1800AC4DA
0x180012b60  lea     rcx, dword_1800C1058
0x180012b67  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180012b6c  cmp     dword ptr [r15+0Ch], 0
0x180012b71  setnz   al
0x180012b74  xchg    al, [rsi+68h]
0x180012b77  jmp     loc_180013069
0x180012b7c  cmp     rbx, 458h
0x180012b83  jb      loc_180013185
0x180012b89  mov     eax, cs:dword_1800C1058
0x180012b8f  cmp     eax, 4
0x180012b92  jbe     loc_180012C7C
0x180012b98  mov     rdx, cs:qword_1800C1070
0x180012b9f  mov     rax, cs:qword_1800C1068
0x180012ba6  mov     rcx, 470000000000h
0x180012bb0  test    rcx, rax
0x180012bb3  jz      loc_180012C7C
0x180012bb9  mov     rax, rdx
0x180012bbc  and     rax, rcx
0x180012bbf  cmp     rax, rdx
0x180012bc2  jnz     loc_180012C7C
0x180012bc8  mov     rax, [rsi+6Ch]
0x180012bcc  mov     [rsp+0C8h+var_48], rax
0x180012bd4  mov     eax, [rsi+74h]
0x180012bd7  mov     dword ptr [rsp+0C8h+arg_0], eax
0x180012bde  lea     rax, aReceiveRdpaven_4; "Receive RDPAVENC_OPCODE_MMR_DATA"
0x180012be5  mov     [rsp+0C8h+var_50], rax
0x180012bea  lea     rax, xmmword_1800C21A0
0x180012bf1  mov     [rsp+0C8h+var_58], rax
0x180012bf6  lea     rax, aRdpavenc; "RdpAvenc"
0x180012bfd  mov     qword ptr [rsp+0C8h+var_60], rax
0x180012c02  mov     [rsp+0C8h+var_68], 1000000h
0x180012c0b  lea     rax, aCheckpoint; "Checkpoint"
0x180012c12  mov     [rsp+0C8h+var_40], rax
0x180012c1a  lea     rax, [rsp+0C8h+var_48]
0x180012c22  mov     [rsp+0C8h+var_78], rax
0x180012c27  lea     rax, [rsp+0C8h+arg_0]
0x180012c2f  mov     [rsp+0C8h+var_80], rax
0x180012c34  lea     rax, [rsp+0C8h+var_50]
0x180012c39  mov     qword ptr [rsp+0C8h+var_88], rax
0x180012c3e  lea     rax, [rsp+0C8h+var_58]
0x180012c43  mov     [rsp+0C8h+MessageGuid], rax
0x180012c48  lea     rax, [rsp+0C8h+var_60]
0x180012c4d  mov     [rsp+0C8h+var_98], rax; char *
0x180012c52  lea     rax, [rsp+0C8h+var_68]
0x180012c57  mov     [rsp+0C8h+var_A0], rax
0x180012c5c  lea     rax, [rsp+0C8h+var_40]
0x180012c64  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180012c69  lea     rdx, word_1800AC55A
0x180012c70  lea     rcx, dword_1800C1058
0x180012c77  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180012c7c  mov     [rsp+0C8h+var_A8], 1F9h; unsigned int
0x180012c84  lea     rbx, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180012c8b  mov     r9, rbx; char *
0x180012c8e  lea     r8, aRdpAvencUmrdpC_31; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Pro"...
0x180012c95  lea     rdx, aReceiveRdpaven_2; "Receive RDPAVENC_OPCODE_MMR_DATA"
0x180012c9c  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180012ca3  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180012ca8  cmp     qword ptr [rsi+38h], 0
0x180012cad  setz    al
0x180012cb0  mov     rcx, [rsp+0C8h]; this
0x180012cb8  lea     rdx, aGfxUpdateChann; "Gfx update channel is not initialized"
0x180012cbf  mov     [rsp+0C8h+var_A0], rdx; bool
0x180012cc4  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x180012cc8  mov     r9d, 80070057h; char *
0x180012cce  mov     r8, rbx; unsigned int
0x180012cd1  mov     edx, 339h; void *
0x180012cd6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180012cdb  mov     rbx, [rsi+38h]
0x180012cdf  mov     [rsp+0C8h+arg_0], rbx
0x180012ce7  mov     edx, 5DCh
0x180012cec  mov     rcx, rbx
0x180012cef  call    ?lock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXI@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::lock(uint)
0x180012cf4  nop
0x180012cf5  mov     rdx, r15
0x180012cf8  mov     rcx, [rsi+38h]
0x180012cfc  call    ?SendMMRHint@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXQEAU_RDPAVENC_OPCODE_MMR_DATA@234@@Z; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::SendMMRHint(Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_MMR_DATA * const)
0x180012d01  nop
0x180012d02  mov     rcx, rbx
0x180012d05  call    ?unlock@?$CRdpGfxUpdateChannelImpl@VCTSSharedBufferProducer@Modern@Rdp@@@Umrdp@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::Umrdp::CRdpGfxUpdateChannelImpl<Rdp::Modern::CTSSharedBufferProducer>::unlock(void)
0x180012d0a  jmp     loc_180013069
0x180012d0f  cmp     rbx, 4Ch ; 'L'
0x180012d13  jb      loc_1800131B0
0x180012d19  mov     eax, cs:dword_1800C1058
0x180012d1f  cmp     eax, 5
0x180012d22  jbe     loc_180012DBF
0x180012d28  mov     rax, [rsi+6Ch]
0x180012d2c  mov     [rsp+0C8h+var_48], rax
0x180012d34  mov     eax, [rsi+74h]
0x180012d37  mov     dword ptr [rsp+0C8h+arg_0], eax
0x180012d3e  lea     rax, aReceiveRdpaven_1; "Receive RDPAVENC_OPCODE_TAG_FRAME_REQ"
0x180012d45  mov     [rsp+0C8h+var_50], rax
0x180012d4a  lea     r8, aRdpAvencUmrdpC_31; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Pro"...
0x180012d51  mov     [rsp+0C8h+var_58], r8
0x180012d56  mov     dword ptr [rsp+0C8h+var_68], 1E0h
0x180012d5e  lea     rax, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180012d65  mov     qword ptr [rsp+0C8h+var_60], rax
0x180012d6a  lea     rax, [rsp+0C8h+var_48]
0x180012d72  mov     [rsp+0C8h+var_80], rax
0x180012d77  lea     rax, [rsp+0C8h+arg_0]
0x180012d7f  mov     qword ptr [rsp+0C8h+var_88], rax
0x180012d84  lea     rax, [rsp+0C8h+var_50]
0x180012d89  mov     [rsp+0C8h+MessageGuid], rax
0x180012d8e  lea     rax, [rsp+0C8h+var_58]
0x180012d93  mov     [rsp+0C8h+var_98], rax
0x180012d98  lea     rax, [rsp+0C8h+var_68]
0x180012d9d  mov     [rsp+0C8h+var_A0], rax
0x180012da2  lea     rax, [rsp+0C8h+var_60]
0x180012da7  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180012dac  lea     rdx, byte_1800AC5BD
0x180012db3  lea     rcx, dword_1800C1058
0x180012dba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180012dbf  mov     rdx, r15; struct Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TAG_FRAME_REQ *
0x180012dc2  lea     rcx, [rsi-50h]; this
0x180012dc6  call    ?ProcessTagFrame@CUmrdpProcessor@Umrdp@Avenc@Rdp@@AEAAXQEAU_RDPAVENC_OPCODE_TAG_FRAME_REQ@234@@Z; Rdp::Avenc::Umrdp::CUmrdpProcessor::ProcessTagFrame(Rdp::Avenc::Umrdp::_RDPAVENC_OPCODE_TAG_FRAME_REQ * const)
0x180012dcb  jmp     loc_180013069
0x180012dd0  cmp     rbx, 10h
0x180012dd4  jb      loc_1800131DB
0x180012dda  mov     eax, cs:dword_1800C1058
0x180012de0  cmp     eax, 4
0x180012de3  jbe     loc_180012EE5
0x180012de9  mov     rdx, cs:qword_1800C1070
0x180012df0  mov     rax, cs:qword_1800C1068
0x180012df7  mov     rcx, 470000000000h
0x180012e01  test    rcx, rax
0x180012e04  jz      loc_180012EE5
0x180012e0a  mov     rax, rdx
0x180012e0d  and     rax, rcx
0x180012e10  cmp     rax, rdx
0x180012e13  jnz     loc_180012EE5
0x180012e19  mov     eax, [r15+0Ch]
0x180012e1d  mov     dword ptr [rsp+0C8h+arg_0], eax
0x180012e24  mov     rax, [rsi+6Ch]
0x180012e28  mov     [rsp+0C8h+var_48], rax
0x180012e30  mov     eax, [rsi+74h]
0x180012e33  mov     dword ptr [rsp+0C8h+var_68], eax
0x180012e37  lea     rax, aReceiveRdpaven; "Receive RDPAVENC_OPCODE_SET_GPU_ENCODE_"...
0x180012e3e  mov     [rsp+0C8h+var_50], rax
0x180012e43  lea     rax, xmmword_1800C21A0
0x180012e4a  mov     [rsp+0C8h+var_58], rax
0x180012e4f  lea     rax, aRdpavenc; "RdpAvenc"
0x180012e56  mov     qword ptr [rsp+0C8h+var_60], rax
0x180012e5b  mov     [rsp+0C8h+var_40], 1000000h
0x180012e67  lea     rax, aCheckpoint; "Checkpoint"
0x180012e6e  mov     [rsp+0C8h+var_38], rax
0x180012e76  lea     rax, [rsp+0C8h+arg_0]
0x180012e7e  mov     [rsp+0C8h+var_70], rax
0x180012e83  lea     rax, [rsp+0C8h+var_48]
0x180012e8b  mov     [rsp+0C8h+var_78], rax
0x180012e90  lea     rax, [rsp+0C8h+var_68]
0x180012e95  mov     [rsp+0C8h+var_80], rax
0x180012e9a  lea     rax, [rsp+0C8h+var_50]
0x180012e9f  mov     qword ptr [rsp+0C8h+var_88], rax
0x180012ea4  lea     rax, [rsp+0C8h+var_58]
0x180012ea9  mov     [rsp+0C8h+MessageGuid], rax
0x180012eae  lea     rax, [rsp+0C8h+var_60]
0x180012eb3  mov     [rsp+0C8h+var_98], rax
0x180012eb8  lea     rax, [rsp+0C8h+var_40]
0x180012ec0  mov     [rsp+0C8h+var_A0], rax
0x180012ec5  lea     rax, [rsp+0C8h+var_38]
0x180012ecd  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180012ed2  lea     rdx, word_1800AC622
0x180012ed9  lea     rcx, dword_1800C1058
0x180012ee0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@46@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180012ee5  mov     eax, [r15+0Ch]
0x180012ee9  mov     dword ptr [rsp+0C8h+var_A0], eax
0x180012eed  mov     [rsp+0C8h+var_A8], 1CBh; unsigned int
0x180012ef5  lea     r9, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180012efc  lea     r8, aRdpAvencUmrdpC_31; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Pro"...
0x180012f03  lea     rdx, aSetgpuencodemo; "SetGpuEncodeMode: %d"
0x180012f0a  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180012f11  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180012f16  cmp     dword ptr [r15+0Ch], 0
0x180012f1b  setz    al
0x180012f1e  xchg    al, [rsi+7Eh]
0x180012f21  jmp     loc_180013069
0x180012f26  cmp     [rsp+0C8h+arg_8], 0
0x180012f2e  jz      loc_180013206
0x180012f34  cmp     rbx, 0A38h
0x180012f3b  jb      loc_180013231
0x180012f41  mov     eax, cs:dword_1800C1058
0x180012f47  cmp     eax, 4
0x180012f4a  jbe     loc_180013034
0x180012f50  mov     rdx, cs:qword_1800C1070
0x180012f57  mov     rax, cs:qword_1800C1068
0x180012f5e  mov     rcx, 470000000000h
0x180012f68  test    rcx, rax
0x180012f6b  jz      loc_180013034
0x180012f71  mov     rax, rdx
0x180012f74  and     rax, rcx
0x180012f77  cmp     rax, rdx
0x180012f7a  jnz     loc_180013034
0x180012f80  mov     rax, [rsi+6Ch]
  ... truncated ...
```
