# Rdp::Avenc::Yuv::CYuvFrameProcessor::StopInternal(void)

- ea: `0x180061074`
- end: `0x1800614d2`
- name: `?StopInternal@CYuvFrameProcessor@Yuv@Avenc@Rdp@@IEAAJXZ`
- size: `1118`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvFrameProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180062aa0`

## callees

- `0x180001114`
- `0x18000406c`
- `0x180006580`
- `0x1800153f8`
- `0x180015480`
- `0x18005b8f4`
- `0x180061074`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800610de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006146e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800610de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006146e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::Yuv::CYuvFrameProcessor::StopInternal(Rdp::Avenc::Yuv::CYuvFrameProcessor *this)
{
  char v2; // r12
  bool v3; // bl
  bool v4; // di
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  __int64 v8; // rdx
  int v9; // r8d
  int v10; // r9d
  __int64 v11; // rdx
  const char *v12; // r9
  __int64 v13; // rcx
  bool v14; // bl
  char v15; // al
  int v16; // r8d
  int v17; // edx
  __int64 result; // rax
  int v19; // [rsp+20h] [rbp-188h]
  int v20; // [rsp+20h] [rbp-188h]
  int v21; // [rsp+28h] [rbp-180h]
  int v22; // [rsp+28h] [rbp-180h]
  int v23; // [rsp+80h] [rbp-128h] BYREF
  int v24[2]; // [rsp+88h] [rbp-120h] BYREF
  int v25; // [rsp+90h] [rbp-118h] BYREF
  __int64 v26; // [rsp+98h] [rbp-110h] BYREF
  const char *v27; // [rsp+A0h] [rbp-108h] BYREF
  const char *v28; // [rsp+A8h] [rbp-100h] BYREF
  int v29[2]; // [rsp+B0h] [rbp-F8h] BYREF
  _BYTE v30[32]; // [rsp+C0h] [rbp-E8h] BYREF
  const char *v31; // [rsp+E0h] [rbp-C8h]
  __int64 v32; // [rsp+E8h] [rbp-C0h]
  int *v33; // [rsp+F0h] [rbp-B8h]
  __int64 v34; // [rsp+F8h] [rbp-B0h]
  const char *v35; // [rsp+100h] [rbp-A8h]
  __int64 v36; // [rsp+108h] [rbp-A0h]
  const char *v37; // [rsp+110h] [rbp-98h]
  __int64 v38; // [rsp+118h] [rbp-90h]
  int *v39; // [rsp+120h] [rbp-88h]
  __int64 v40; // [rsp+128h] [rbp-80h]
  const char *v41; // [rsp+130h] [rbp-78h]
  __int64 v42; // [rsp+138h] [rbp-70h]
  int *v43; // [rsp+140h] [rbp-68h]
  __int64 v44; // [rsp+148h] [rbp-60h]
  __int64 v45; // [rsp+150h] [rbp-58h]
  __int64 v46; // [rsp+158h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

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
      v19,
      v21,
      12,
      &WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v8 = *((_QWORD *)this + 2);
    v23 = *(_DWORD *)(*(_QWORD *)(v8 + 112) + 152LL);
    *(_QWORD *)v24 = 0x1000000;
    v45 = v8 + 120;
    v46 = 16;
    v43 = &v23;
    v44 = 4;
    v41 = "Stop Yuv frame processor";
    v42 = 25;
    v39 = &xmmword_1800C21A0;
    v40 = 16;
    v37 = "DirectStreamMedia_Driver";
    v38 = 25;
    v35 = "RdpAvenc";
    v36 = 9;
    v33 = v24;
    v34 = 8;
    v31 = "Checkpoint";
    v32 = 11;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C1058, &word_1800B4A0E, 0, 0, 10, v30);
  }
  try
  {
    v22 = *(_DWORD *)(*((_QWORD *)this + 2) + 120LL);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"YuvFrameProcessorStop: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::Yuv::CYuvFrameProcessor::StopInternal",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
      0x89u);
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v11 = *((_QWORD *)this + 2);
      v26 = v11 + 120;
      v23 = *(_DWORD *)(*(_QWORD *)(v11 + 112) + 152LL);
      v25 = *(_DWORD *)(v11 + 136);
      v27 = "StopFrameProcessor";
      v28 = "Rdp::Avenc::Yuv::CYuvFrameProcessor::StopInternal";
      v24[0] = 145;
      *(_QWORD *)v29 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800B4956,
        v9,
        v10,
        (__int64)v29,
        (__int64)v24,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&v23,
        (__int64)&v26);
    }
    Rdp::Avenc::Yuv::CYuvProcessor::OnStopFrameProcessor(
      *(Rdp::Avenc::Yuv::CYuvProcessor **)(*((_QWORD *)this + 2) + 112LL),
      (const struct _GUID *)(*((_QWORD *)this + 2) + 120LL),
      (unsigned __int64)this);
    v13 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v14 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = GetCurrentThreadId();
      LOBYTE(v16) = v14;
      LOBYTE(v17) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v17,
        v16,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v20,
        v22,
        13,
        &WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids,
        v15);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA0,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvframeprocessor.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180061074  push    rbx
0x180061076  push    rsi
0x180061077  push    rdi
0x180061078  push    r12
0x18006107a  push    r13
0x18006107c  push    r14
0x18006107e  sub     rsp, 178h
0x180061085  mov     rax, cs:__security_cookie
0x18006108c  xor     rax, rsp
0x18006108f  mov     [rsp+1A8h+var_48], rax
0x180061097  mov     r13, rcx
0x18006109a  lea     rcx, WPP_GLOBAL_Control
0x1800610a1  mov     rax, cs:WPP_GLOBAL_Control
0x1800610a8  mov     r12b, 1
0x1800610ab  cmp     rax, rcx
0x1800610ae  jz      short loc_1800610C1
0x1800610b0  test    [rax+1Ch], r12b
0x1800610b4  jz      short loc_1800610C1
0x1800610b6  cmp     byte ptr [rax+19h], 4
0x1800610ba  jb      short loc_1800610C1
0x1800610bc  mov     bl, r12b
0x1800610bf  jmp     short loc_1800610C3
0x1800610c1  xor     bl, bl
0x1800610c3  lea     rax, WPP_RECORDER_INITIALIZED
0x1800610ca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1800610d1  setnz   dil
0x1800610d5  test    bl, bl
0x1800610d7  jnz     short loc_1800610DE
0x1800610d9  test    dil, dil
0x1800610dc  jz      short loc_180061114
0x1800610de  call    cs:__imp_GetCurrentThreadId
0x1800610e4  mov     dword ptr [rsp+1A8h+var_168], eax; char
0x1800610e8  lea     rsi, WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids
0x1800610ef  mov     [rsp+1A8h+MessageGuid], rsi; MessageGuid
0x1800610f4  mov     [rsp+1A8h+var_178], 0Ch; __int16
0x1800610fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180061102  mov     r9, [rcx+28h]; int
0x180061106  mov     r8b, dil; int
0x180061109  mov     dl, bl; int
0x18006110b  mov     rcx, [rcx+10h]; int
0x18006110f  call    WPP_RECORDER_AND_TRACE_SF_D
0x180061114  mov     eax, cs:dword_1800C1058
0x18006111a  cmp     eax, 4
0x18006111d  jbe     loc_180061279
0x180061123  mov     rcx, cs:qword_1800C1070
0x18006112a  mov     rax, cs:qword_1800C1068
0x180061131  mov     rdx, 470000000000h
0x18006113b  test    rdx, rax
0x18006113e  jz      loc_180061279
0x180061144  mov     rax, rcx
0x180061147  and     rax, rdx
0x18006114a  cmp     rax, rcx
0x18006114d  jnz     loc_180061279
0x180061153  mov     rdx, [r13+10h]
0x180061157  mov     rax, [rdx+70h]
0x18006115b  mov     ecx, [rax+98h]
0x180061161  mov     [rsp+1A8h+var_128], ecx
0x180061168  mov     qword ptr [rsp+1A8h+var_120], 1000000h
0x180061174  lea     rax, [rdx+78h]
0x180061178  mov     [rsp+1A8h+var_58], rax
0x180061180  mov     [rsp+1A8h+var_50], 10h
0x18006118c  lea     rax, [rsp+1A8h+var_128]
0x180061194  mov     [rsp+1A8h+var_68], rax
0x18006119c  mov     [rsp+1A8h+var_60], 4
0x1800611a8  lea     rax, aStopYuvFramePr; "Stop Yuv frame processor"
0x1800611af  mov     [rsp+1A8h+var_78], rax
0x1800611b7  mov     [rsp+1A8h+var_70], 19h
0x1800611c3  lea     rax, xmmword_1800C21A0
0x1800611ca  mov     [rsp+1A8h+var_88], rax
0x1800611d2  mov     [rsp+1A8h+var_80], 10h
0x1800611de  lea     rax, aDirectstreamme_0; "DirectStreamMedia_Driver"
0x1800611e5  mov     [rsp+1A8h+var_98], rax
0x1800611ed  mov     [rsp+1A8h+var_90], 19h
0x1800611f9  lea     rax, aRdpavenc; "RdpAvenc"
0x180061200  mov     [rsp+1A8h+var_A8], rax
0x180061208  mov     [rsp+1A8h+var_A0], 9
0x180061214  lea     rax, [rsp+1A8h+var_120]
0x18006121c  mov     [rsp+1A8h+var_B8], rax
0x180061224  mov     [rsp+1A8h+var_B0], 8
0x180061230  lea     rax, aCheckpoint; "Checkpoint"
0x180061237  mov     [rsp+1A8h+var_C8], rax
0x18006123f  mov     [rsp+1A8h+var_C0], 0Bh
0x18006124b  lea     rax, [rsp+1A8h+var_E8]
0x180061253  mov     qword ptr [rsp+1A8h+var_180], rax
0x180061258  mov     [rsp+1A8h+var_188], 0Ah
0x180061260  xor     r9d, r9d
0x180061263  xor     r8d, r8d
0x180061266  lea     rdx, word_1800B4A0E
0x18006126d  lea     rcx, dword_1800C1058
0x180061274  call    _tlgWriteTransfer_EventWriteTransfer
0x180061279  mov     r14, [r13+10h]
0x18006127d  movzx   eax, byte ptr [r14+87h]
0x180061285  movzx   ecx, byte ptr [r14+86h]
0x18006128d  movzx   edx, byte ptr [r14+85h]
0x180061295  movzx   r8d, byte ptr [r14+84h]
0x18006129d  movzx   r9d, byte ptr [r14+83h]
0x1800612a5  movzx   r10d, byte ptr [r14+82h]
0x1800612ad  movzx   r11d, byte ptr [r14+81h]
0x1800612b5  movzx   ebx, byte ptr [r14+80h]
0x1800612bd  movzx   edi, word ptr [r14+7Eh]
0x1800612c2  movzx   esi, word ptr [r14+7Ch]
0x1800612c7  mov     [rsp+1A8h+var_130], eax
0x1800612cb  mov     [rsp+1A8h+var_138], ecx
0x1800612cf  mov     [rsp+1A8h+var_140], edx
0x1800612d3  mov     [rsp+1A8h+var_148], r8d
0x1800612d8  mov     [rsp+1A8h+var_150], r9d
0x1800612dd  mov     dword ptr [rsp+1A8h+var_158], r10d
0x1800612e2  mov     dword ptr [rsp+1A8h+var_160], r11d
0x1800612e7  mov     dword ptr [rsp+1A8h+var_168], ebx
0x1800612eb  mov     dword ptr [rsp+1A8h+MessageGuid], edi
0x1800612ef  mov     dword ptr [rsp+1A8h+var_178], esi
0x1800612f3  mov     eax, [r14+78h]
0x1800612f7  mov     [rsp+1A8h+var_180], eax
0x1800612fb  mov     [rsp+1A8h+var_188], 89h; unsigned int
0x180061303  lea     rbx, aOnecoreuapTerm_53; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18006130a  mov     r9, rbx; char *
0x18006130d  lea     rdi, aRdpAvencYuvCyu_11; "Rdp::Avenc::Yuv::CYuvFrameProcessor::St"...
0x180061314  mov     r8, rdi; char *
0x180061317  lea     rdx, aYuvframeproces; "YuvFrameProcessorStop: Id {%08lX-%04hX-"...
0x18006131e  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180061325  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18006132a  mov     eax, cs:dword_1800C1058
0x180061330  cmp     eax, 4
0x180061333  jbe     loc_1800613FF
0x180061339  mov     rdx, [r13+10h]
0x18006133d  lea     rax, [rdx+78h]
0x180061341  mov     [rsp+1A8h+var_110], rax
0x180061349  mov     rax, [rdx+70h]
0x18006134d  mov     ecx, [rax+98h]
0x180061353  mov     [rsp+1A8h+var_128], ecx
0x18006135a  mov     eax, [rdx+88h]
0x180061360  mov     [rsp+1A8h+var_118], eax
0x180061367  lea     rax, aStopframeproce; "StopFrameProcessor"
0x18006136e  mov     [rsp+1A8h+var_108], rax
0x180061376  mov     [rsp+1A8h+var_100], rdi
0x18006137e  mov     [rsp+1A8h+var_120], 91h
0x180061389  mov     qword ptr [rsp+1A8h+var_F8], rbx
0x180061391  lea     rax, [rsp+1A8h+var_110]
0x180061399  mov     [rsp+1A8h+var_158], rax
0x18006139e  lea     rax, [rsp+1A8h+var_128]
0x1800613a6  mov     [rsp+1A8h+var_160], rax
0x1800613ab  lea     rax, [rsp+1A8h+var_118]
0x1800613b3  mov     qword ptr [rsp+1A8h+var_168], rax
0x1800613b8  lea     rax, [rsp+1A8h+var_108]
0x1800613c0  mov     [rsp+1A8h+MessageGuid], rax
0x1800613c5  lea     rax, [rsp+1A8h+var_100]
0x1800613cd  mov     qword ptr [rsp+1A8h+var_178], rax
0x1800613d2  lea     rax, [rsp+1A8h+var_120]
0x1800613da  mov     qword ptr [rsp+1A8h+var_180], rax; int
0x1800613df  lea     rax, [rsp+1A8h+var_F8]
0x1800613e7  mov     qword ptr [rsp+1A8h+var_188], rax; int
0x1800613ec  lea     rdx, word_1800B4956
0x1800613f3  lea     rcx, dword_1800C1058
0x1800613fa  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x1800613ff  mov     rcx, [r13+10h]
0x180061403  lea     rdx, [rcx+78h]; struct _GUID *
0x180061407  mov     r8, r13; unsigned __int64
0x18006140a  mov     rcx, [rcx+70h]; this
0x18006140e  call    ?OnStopFrameProcessor@CYuvProcessor@Yuv@Avenc@Rdp@@QEAAXAEBU_GUID@@_K@Z; Rdp::Avenc::Yuv::CYuvProcessor::OnStopFrameProcessor(_GUID const &,unsigned __int64)
0x180061413  nop
0x180061414  mov     rcx, [r13+10h]
0x180061418  mov     qword ptr [r13+10h], 0
0x180061420  test    rcx, rcx
0x180061423  jz      short loc_180061432
0x180061425  mov     rax, [rcx]
0x180061428  mov     rax, [rax+10h]
0x18006142c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061431  nop
0x180061432  mov     rax, cs:WPP_GLOBAL_Control
0x180061439  lea     rcx, WPP_GLOBAL_Control
0x180061440  cmp     rax, rcx
0x180061443  jz      short loc_180061451
0x180061445  test    [rax+1Ch], r12b
0x180061449  jz      short loc_180061451
0x18006144b  cmp     byte ptr [rax+19h], 4
0x18006144f  jnb     short loc_180061454
0x180061451  xor     r12b, r12b
0x180061454  lea     rax, WPP_RECORDER_INITIALIZED
0x18006145b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180061462  setnz   bl
0x180061465  test    r12b, r12b
0x180061468  jnz     short loc_18006146E
0x18006146a  test    bl, bl
0x18006146c  jz      short loc_1800614A5
0x18006146e  call    cs:__imp_GetCurrentThreadId
0x180061474  mov     dword ptr [rsp+1A8h+var_168], eax; char
0x180061478  lea     rax, WPP_5f6013b65d4837ea31da93ef4012fafd_Traceguids
0x18006147f  mov     [rsp+1A8h+MessageGuid], rax; MessageGuid
0x180061484  mov     [rsp+1A8h+var_178], 0Dh; __int16
0x18006148b  mov     rcx, cs:WPP_GLOBAL_Control
0x180061492  mov     r9, [rcx+28h]; int
0x180061496  mov     r8b, bl; int
0x180061499  mov     dl, r12b; int
0x18006149c  mov     rcx, [rcx+10h]; int
0x1800614a0  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800614a5  xor     eax, eax
0x1800614a7  jmp     short loc_1800614B0
0x1800614a9  mov     eax, [rsp+1A8h+var_120]
0x1800614b0  mov     rcx, [rsp+1A8h+var_48]
0x1800614b8  xor     rcx, rsp; StackCookie
0x1800614bb  call    __security_check_cookie
0x1800614c0  add     rsp, 178h
0x1800614c7  pop     r14
0x1800614c9  pop     r13
0x1800614cb  pop     r12
0x1800614cd  pop     rdi
0x1800614ce  pop     rsi
0x1800614cf  pop     rbx
0x1800614d0  retn
```
