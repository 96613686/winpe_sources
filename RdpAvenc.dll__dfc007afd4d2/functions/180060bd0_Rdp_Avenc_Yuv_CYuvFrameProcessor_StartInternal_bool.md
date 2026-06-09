# Rdp::Avenc::Yuv::CYuvFrameProcessor::StartInternal(bool)

- ea: `0x180060bd0`
- end: `0x18006106b`
- name: `?StartInternal@CYuvFrameProcessor@Yuv@Avenc@Rdp@@IEAAJ_N@Z`
- size: `1179`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvFrameProcessor *__hidden this, bool)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180062990`
- `0x1800629b0`

## callees

- `0x180001114`
- `0x18000406c`
- `0x180006580`
- `0x1800152c4`
- `0x180015480`
- `0x18005af04`
- `0x180060bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060c4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060f45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060c4c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060f45`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall Rdp::Avenc::Yuv::CYuvFrameProcessor::StartInternal(
        Rdp::Avenc::Yuv::CYuvFrameProcessor *this,
        bool a2)
{
  char v4; // di
  bool v5; // si
  bool v6; // r14
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  __int64 v10; // rdx
  int v11; // r8d
  int v12; // r9d
  __int64 v13; // rdx
  int v14; // r8d
  int v15; // r9d
  bool v16; // si
  char v17; // al
  int v18; // r8d
  int v19; // edx
  __int64 v20; // rdx
  unsigned int v22[2]; // [rsp+20h] [rbp-158h]
  int v23[2]; // [rsp+28h] [rbp-150h]
  int v24; // [rsp+60h] [rbp-118h] BYREF
  int v25; // [rsp+64h] [rbp-114h] BYREF
  int v26[2]; // [rsp+68h] [rbp-110h] BYREF
  const char *v27; // [rsp+70h] [rbp-108h] BYREF
  const char *v28; // [rsp+78h] [rbp-100h] BYREF
  const char *v29; // [rsp+80h] [rbp-F8h] BYREF
  int v30[2]; // [rsp+88h] [rbp-F0h] BYREF
  _BYTE v31[32]; // [rsp+90h] [rbp-E8h] BYREF
  const char *v32; // [rsp+B0h] [rbp-C8h]
  __int64 v33; // [rsp+B8h] [rbp-C0h]
  int *v34; // [rsp+C0h] [rbp-B8h]
  __int64 v35; // [rsp+C8h] [rbp-B0h]
  const char *v36; // [rsp+D0h] [rbp-A8h]
  __int64 v37; // [rsp+D8h] [rbp-A0h]
  const char *v38; // [rsp+E0h] [rbp-98h]
  __int64 v39; // [rsp+E8h] [rbp-90h]
  int *v40; // [rsp+F0h] [rbp-88h]
  __int64 v41; // [rsp+F8h] [rbp-80h]
  const char *v42; // [rsp+100h] [rbp-78h]
  __int64 v43; // [rsp+108h] [rbp-70h]
  __int64 v44; // [rsp+110h] [rbp-68h]
  __int64 v45; // [rsp+118h] [rbp-60h]
  int *v46; // [rsp+120h] [rbp-58h]
  __int64 v47; // [rsp+128h] [rbp-50h]
  int *v48; // [rsp+130h] [rbp-48h]
  __int64 v49; // [rsp+138h] [rbp-40h]

  v4 = 1;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v22[0],
      v23[0],
      10,
      &WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v10 = *((_QWORD *)this + 2);
    v24 = *(_DWORD *)(*(_QWORD *)(v10 + 112) + 152LL);
    v25 = *(_DWORD *)(v10 + 136);
    *(_QWORD *)v26 = 0x1000000;
    v48 = &v24;
    v49 = 4;
    v46 = &v25;
    v47 = 4;
    v44 = v10 + 120;
    v45 = 16;
    v42 = "Start Yuv frame processor";
    v43 = 26;
    v40 = &xmmword_1800C21A0;
    v41 = 16;
    v38 = "DirectStreamMedia_Driver";
    v39 = 25;
    v36 = "RdpAvenc";
    v37 = 9;
    v34 = v26;
    v35 = 8;
    v32 = "Checkpoint";
    v33 = 11;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C1058, &byte_1800B4B3F, 0, 0, 11, v31);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"YuvFrameProcessorStart",
    "Rdp::Avenc::Yuv::CYuvFrameProcessor::StartInternal",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
    0x46u);
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    v13 = *((_QWORD *)this + 2);
    v27 = (const char *)(v13 + 120);
    v25 = *(_DWORD *)(*(_QWORD *)(v13 + 112) + 152LL);
    v24 = *(_DWORD *)(v13 + 136);
    v28 = "StartFrameProcessor";
    v29 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::StartInternal";
    v26[0] = 78;
    *(_QWORD *)v30 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800B4AE3,
      v11,
      v12,
      (__int64)v30,
      (__int64)v26,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v27);
  }
  Rdp::Avenc::Yuv::CYuvProcessor::OnCreateFrameProcessor(
    *(Rdp::Avenc::Yuv::CYuvProcessor **)(*((_QWORD *)this + 2) + 112LL),
    (const struct _GUID *)(*((_QWORD *)this + 2) + 120LL),
    (unsigned __int64)this,
    a2);
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v4 = 0;
  }
  v16 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v17 = GetCurrentThreadId();
    LOBYTE(v18) = v16;
    LOBYTE(v19) = v4;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      v18,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v22[0],
      v23[0],
      11,
      &WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids,
      v17);
  }
  if ( (unsigned int)dword_1800C1058 > 4 )
  {
    v20 = *((_QWORD *)this + 2);
    *(_QWORD *)v30 = v20 + 120;
    v26[0] = *(_DWORD *)(*(_QWORD *)(v20 + 112) + 152LL);
    v25 = *(_DWORD *)(v20 + 136);
    v29 = "StartFrameProcessor - done";
    v28 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::StartInternal";
    v24 = 98;
    v27 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)&byte_1800B4A87,
      v14,
      v15,
      (__int64)&v27,
      (__int64)&v24,
      (__int64)&v28,
      (__int64)&v29,
      (__int64)&v25,
      (__int64)v26,
      (__int64)v30);
  }
  return 0;
}

```

## disassembly

```asm
0x180060bd0  mov     [rsp+arg_10], rsi
0x180060bd5  push    rdi
0x180060bd6  push    r12
0x180060bd8  push    r13
0x180060bda  push    r14
0x180060bdc  push    r15
0x180060bde  sub     rsp, 150h
0x180060be5  mov     rax, cs:__security_cookie
0x180060bec  xor     rax, rsp
0x180060bef  mov     [rsp+178h+var_38], rax
0x180060bf7  mov     r13b, dl
0x180060bfa  mov     r15, rcx
0x180060bfd  lea     rcx, WPP_GLOBAL_Control
0x180060c04  mov     rax, cs:WPP_GLOBAL_Control
0x180060c0b  mov     dil, 1
0x180060c0e  cmp     rax, rcx
0x180060c11  jz      short loc_180060C24
0x180060c13  test    [rax+1Ch], dil
0x180060c17  jz      short loc_180060C24
0x180060c19  cmp     byte ptr [rax+19h], 4
0x180060c1d  jb      short loc_180060C24
0x180060c1f  mov     sil, dil
0x180060c22  jmp     short loc_180060C27
0x180060c24  xor     sil, sil
0x180060c27  lea     rax, WPP_RECORDER_INITIALIZED
0x180060c2e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180060c35  setnz   r14b
0x180060c39  test    sil, sil
0x180060c3c  jnz     short loc_180060C4C
0x180060c3e  test    r14b, r14b
0x180060c41  jnz     short loc_180060C4C
0x180060c43  lea     r12, WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids
0x180060c4a  jmp     short loc_180060C83
0x180060c4c  call    cs:__imp_GetCurrentThreadId
0x180060c52  mov     dword ptr [rsp+178h+var_138], eax; char
0x180060c56  lea     r12, WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids
0x180060c5d  mov     [rsp+178h+MessageGuid], r12; MessageGuid
0x180060c62  mov     [rsp+178h+var_148], 0Ah; __int16
0x180060c69  mov     rcx, cs:WPP_GLOBAL_Control
0x180060c70  mov     r9, [rcx+28h]; int
0x180060c74  mov     r8b, r14b; int
0x180060c77  mov     dl, sil; int
0x180060c7a  mov     rcx, [rcx+10h]; int
0x180060c7e  call    WPP_RECORDER_AND_TRACE_SF_D
0x180060c83  mov     eax, cs:dword_1800C1058
0x180060c89  cmp     eax, 4
0x180060c8c  jbe     loc_180060E00
0x180060c92  mov     rcx, cs:qword_1800C1070
0x180060c99  mov     rax, cs:qword_1800C1068
0x180060ca0  mov     rdx, 470000000000h
0x180060caa  test    rdx, rax
0x180060cad  jz      loc_180060E00
0x180060cb3  mov     rax, rcx
0x180060cb6  and     rax, rdx
0x180060cb9  cmp     rax, rcx
0x180060cbc  jnz     loc_180060E00
0x180060cc2  mov     rdx, [r15+10h]
0x180060cc6  mov     rax, [rdx+70h]
0x180060cca  mov     ecx, [rax+98h]
0x180060cd0  mov     [rsp+178h+var_118], ecx
0x180060cd4  mov     eax, [rdx+88h]
0x180060cda  mov     [rsp+178h+var_114], eax
0x180060cde  mov     qword ptr [rsp+178h+var_110], 1000000h
0x180060ce7  lea     rax, [rsp+178h+var_118]
0x180060cec  mov     [rsp+178h+var_48], rax
0x180060cf4  mov     [rsp+178h+var_40], 4
0x180060d00  lea     rax, [rsp+178h+var_114]
0x180060d05  mov     [rsp+178h+var_58], rax
0x180060d0d  mov     [rsp+178h+var_50], 4
0x180060d19  lea     rax, [rdx+78h]
0x180060d1d  mov     [rsp+178h+var_68], rax
0x180060d25  mov     [rsp+178h+var_60], 10h
0x180060d31  lea     rax, aStartYuvFrameP; "Start Yuv frame processor"
0x180060d38  mov     [rsp+178h+var_78], rax
0x180060d40  mov     [rsp+178h+var_70], 1Ah
0x180060d4c  lea     rax, xmmword_1800C21A0
0x180060d53  mov     [rsp+178h+var_88], rax
0x180060d5b  mov     [rsp+178h+var_80], 10h
0x180060d67  lea     rax, aDirectstreamme_0; "DirectStreamMedia_Driver"
0x180060d6e  mov     [rsp+178h+var_98], rax
0x180060d76  mov     [rsp+178h+var_90], 19h
0x180060d82  lea     rax, aRdpavenc; "RdpAvenc"
0x180060d89  mov     [rsp+178h+var_A8], rax
0x180060d91  mov     [rsp+178h+var_A0], 9
0x180060d9d  lea     rax, [rsp+178h+var_110]
0x180060da2  mov     [rsp+178h+var_B8], rax
0x180060daa  mov     [rsp+178h+var_B0], 8
0x180060db6  lea     rax, aCheckpoint; "Checkpoint"
0x180060dbd  mov     [rsp+178h+var_C8], rax
0x180060dc5  mov     r14d, 0Bh
0x180060dcb  mov     [rsp+178h+var_C0], r14
0x180060dd3  lea     rax, [rsp+178h+var_E8]
0x180060ddb  mov     qword ptr [rsp+178h+var_150], rax
0x180060de0  mov     [rsp+178h+var_158], r14d
0x180060de5  xor     r9d, r9d
0x180060de8  xor     r8d, r8d
0x180060deb  lea     rdx, byte_1800B4B3F
0x180060df2  lea     rcx, dword_1800C1058
0x180060df9  call    _tlgWriteTransfer_EventWriteTransfer
0x180060dfe  jmp     short loc_180060E06
0x180060e00  mov     r14d, 0Bh
0x180060e06  mov     [rsp+178h+var_158], 46h ; 'F'; unsigned int
0x180060e0e  lea     rsi, aOnecoreuapTerm_53; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180060e15  mov     r9, rsi; char *
0x180060e18  lea     r8, aRdpAvencYuvCyu_0; "Rdp::Avenc::Yuv::CYuvFrameProcessor::St"...
0x180060e1f  lea     rdx, aYuvframeproces_0; "YuvFrameProcessorStart"
0x180060e26  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180060e2d  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x180060e32  mov     eax, cs:dword_1800C1058
0x180060e38  cmp     eax, 4
0x180060e3b  jbe     loc_180060EF0
0x180060e41  mov     rdx, [r15+10h]
0x180060e45  lea     rax, [rdx+78h]
0x180060e49  mov     [rsp+178h+var_108], rax
0x180060e4e  mov     rax, [rdx+70h]
0x180060e52  mov     ecx, [rax+98h]
0x180060e58  mov     [rsp+178h+var_114], ecx
0x180060e5c  mov     eax, [rdx+88h]
0x180060e62  mov     [rsp+178h+var_118], eax
0x180060e66  lea     rax, aStartframeproc_1; "StartFrameProcessor"
0x180060e6d  mov     [rsp+178h+var_100], rax
0x180060e72  lea     rax, aRdpAvencYuvCyu_0; "Rdp::Avenc::Yuv::CYuvFrameProcessor::St"...
0x180060e79  mov     [rsp+178h+var_F8], rax
0x180060e81  mov     [rsp+178h+var_110], 4Eh ; 'N'
0x180060e89  mov     qword ptr [rsp+178h+var_F0], rsi
0x180060e91  lea     rax, [rsp+178h+var_108]
0x180060e96  mov     [rsp+178h+var_128], rax
0x180060e9b  lea     rax, [rsp+178h+var_114]
0x180060ea0  mov     [rsp+178h+var_130], rax
0x180060ea5  lea     rax, [rsp+178h+var_118]
0x180060eaa  mov     qword ptr [rsp+178h+var_138], rax
0x180060eaf  lea     rax, [rsp+178h+var_100]
0x180060eb4  mov     [rsp+178h+MessageGuid], rax
0x180060eb9  lea     rax, [rsp+178h+var_F8]
0x180060ec1  mov     qword ptr [rsp+178h+var_148], rax
0x180060ec6  lea     rax, [rsp+178h+var_110]
0x180060ecb  mov     qword ptr [rsp+178h+var_150], rax; int
0x180060ed0  lea     rax, [rsp+178h+var_F0]
0x180060ed8  mov     qword ptr [rsp+178h+var_158], rax; int
0x180060edd  lea     rdx, byte_1800B4AE3
0x180060ee4  lea     rcx, dword_1800C1058
0x180060eeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180060ef0  mov     rcx, [r15+10h]
0x180060ef4  lea     rdx, [rcx+78h]; struct _GUID *
0x180060ef8  mov     r9b, r13b; bool
0x180060efb  mov     r8, r15; unsigned __int64
0x180060efe  mov     rcx, [rcx+70h]; this
0x180060f02  call    ?OnCreateFrameProcessor@CYuvProcessor@Yuv@Avenc@Rdp@@QEAAXAEBU_GUID@@_K_N@Z; Rdp::Avenc::Yuv::CYuvProcessor::OnCreateFrameProcessor(_GUID const &,unsigned __int64,bool)
0x180060f07  mov     rax, cs:WPP_GLOBAL_Control
0x180060f0e  lea     rcx, WPP_GLOBAL_Control
0x180060f15  cmp     rax, rcx
0x180060f18  jz      short loc_180060F26
0x180060f1a  test    [rax+1Ch], dil
0x180060f1e  jz      short loc_180060F26
0x180060f20  cmp     byte ptr [rax+19h], 4
0x180060f24  jnb     short loc_180060F29
0x180060f26  xor     dil, dil
0x180060f29  lea     rax, WPP_RECORDER_INITIALIZED
0x180060f30  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180060f37  setnz   sil
0x180060f3b  test    dil, dil
0x180060f3e  jnz     short loc_180060F45
0x180060f40  test    sil, sil
0x180060f43  jz      short loc_180060F74
0x180060f45  call    cs:__imp_GetCurrentThreadId
0x180060f4b  mov     dword ptr [rsp+178h+var_138], eax; char
0x180060f4f  mov     [rsp+178h+MessageGuid], r12; MessageGuid
0x180060f54  mov     [rsp+178h+var_148], r14w; __int16
0x180060f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180060f61  mov     r9, [rcx+28h]; int
0x180060f65  mov     r8b, sil; int
0x180060f68  mov     dl, dil; int
0x180060f6b  mov     rcx, [rcx+10h]; int
0x180060f6f  call    WPP_RECORDER_AND_TRACE_SF_D
0x180060f74  mov     eax, cs:dword_1800C1058
0x180060f7a  cmp     eax, 4
0x180060f7d  jbe     loc_180061039
0x180060f83  mov     rdx, [r15+10h]
0x180060f87  lea     rax, [rdx+78h]
0x180060f8b  mov     qword ptr [rsp+178h+var_F0], rax
0x180060f93  mov     rax, [rdx+70h]
0x180060f97  mov     ecx, [rax+98h]
0x180060f9d  mov     [rsp+178h+var_110], ecx
0x180060fa1  mov     eax, [rdx+88h]
0x180060fa7  mov     [rsp+178h+var_114], eax
0x180060fab  lea     rax, aStartframeproc; "StartFrameProcessor - done"
0x180060fb2  mov     [rsp+178h+var_F8], rax
0x180060fba  lea     rax, aRdpAvencYuvCyu_0; "Rdp::Avenc::Yuv::CYuvFrameProcessor::St"...
0x180060fc1  mov     [rsp+178h+var_100], rax
0x180060fc6  mov     [rsp+178h+var_118], 62h ; 'b'
0x180060fce  lea     rax, aOnecoreuapTerm_53; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180060fd5  mov     [rsp+178h+var_108], rax
0x180060fda  lea     rax, [rsp+178h+var_F0]
0x180060fe2  mov     [rsp+178h+var_128], rax
0x180060fe7  lea     rax, [rsp+178h+var_110]
0x180060fec  mov     [rsp+178h+var_130], rax
0x180060ff1  lea     rax, [rsp+178h+var_114]
0x180060ff6  mov     qword ptr [rsp+178h+var_138], rax
0x180060ffb  lea     rax, [rsp+178h+var_F8]
0x180061003  mov     [rsp+178h+MessageGuid], rax
0x180061008  lea     rax, [rsp+178h+var_100]
0x18006100d  mov     qword ptr [rsp+178h+var_148], rax
0x180061012  lea     rax, [rsp+178h+var_118]
0x180061017  mov     qword ptr [rsp+178h+var_150], rax
0x18006101c  lea     rax, [rsp+178h+var_108]
0x180061021  mov     qword ptr [rsp+178h+var_158], rax
0x180061026  lea     rdx, byte_1800B4A87
0x18006102d  lea     rcx, dword_1800C1058
0x180061034  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180061039  xor     eax, eax
0x18006103b  jmp     short loc_180061041
0x18006103d  mov     eax, [rsp+178h+var_110]
0x180061041  mov     rcx, [rsp+178h+var_38]
0x180061049  xor     rcx, rsp; StackCookie
0x18006104c  call    __security_check_cookie
0x180061051  mov     rsi, [rsp+178h+arg_10]
0x180061059  add     rsp, 150h
0x180061060  pop     r15
0x180061062  pop     r14
0x180061064  pop     r13
0x180061066  pop     r12
0x180061068  pop     rdi
0x180061069  retn
```
