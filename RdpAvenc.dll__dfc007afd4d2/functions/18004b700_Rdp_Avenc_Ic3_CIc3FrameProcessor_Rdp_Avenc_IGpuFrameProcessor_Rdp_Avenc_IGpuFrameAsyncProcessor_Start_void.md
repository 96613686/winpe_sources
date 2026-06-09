# Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::Start(void)

- ea: `0x18004b700`
- end: `0x18004c03b`
- name: `?Start@?$CIc3FrameProcessor@UIGpuFrameProcessor@Avenc@Rdp@@UIGpuFrameAsyncProcessor@23@@Ic3@Avenc@Rdp@@UEAAJXZ`
- size: `2363`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180044a80`

## callees

- `0x18000406c`
- `0x1800047c0`
- `0x1800050dc`
- `0x1800065a4`
- `0x18000e848`
- `0x180010bc8`
- `0x180011490`
- `0x1800152c4`
- `0x180015480`
- `0x180041d0c`
- `0x18004b700`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004be6e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x18004be6e`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004be4b`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18004be4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bee0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b75d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004bee0`

## string_xrefs

- `0x18004b819`: `DirectStreamMedia_Service`

## pseudocode

```c
__int64 __fastcall Rdp::Avenc::Ic3::CIc3FrameProcessor<Rdp::Avenc::IGpuFrameProcessor,Rdp::Avenc::IGpuFrameAsyncProcessor>::Start(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4)
{
  char v5; // si
  bool v6; // di
  bool v7; // r14
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  __int64 v11; // rdx
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rdi
  __int64 v17; // rdi
  void (__fastcall *v18)(__int64, __int64); // r12
  _QWORD *v19; // r14
  __int64 v20; // rcx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rdx
  __int64 v24; // rax
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rdx
  __int64 v28; // rdx
  unsigned int started; // eax
  int v30; // r8d
  int v31; // r9d
  _QWORD *v32; // rax
  __int64 v33; // rdx
  __int64 v34; // rcx
  int v35; // ecx
  int v36; // eax
  bool v37; // r14
  char v38; // al
  int v39; // r8d
  int v40; // edx
  __int64 v41; // rdx
  int v43; // [rsp+20h] [rbp-B8h]
  int v44; // [rsp+20h] [rbp-B8h]
  int v45; // [rsp+28h] [rbp-B0h]
  struct tagRECT *v46; // [rsp+28h] [rbp-B0h]
  struct tagRECT *v47; // [rsp+28h] [rbp-B0h]
  const char *v48; // [rsp+70h] [rbp-68h] BYREF
  const char *v49; // [rsp+78h] [rbp-60h] BYREF
  const char *v50; // [rsp+80h] [rbp-58h] BYREF
  const char *v51; // [rsp+88h] [rbp-50h] BYREF
  int v52[4]; // [rsp+90h] [rbp-48h] BYREF
  _QWORD v53[7]; // [rsp+A0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  _QWORD *v55; // [rsp+E8h] [rbp+10h] BYREF
  int v56; // [rsp+F0h] [rbp+18h] BYREF
  __int64 v57; // [rsp+F8h] [rbp+20h] BYREF

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
      v43,
      v45,
      10,
      &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    v11 = *(_QWORD *)(a1 + 96);
    v57 = v11 + 112;
    LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(v11 + 104) + 136LL);
    v56 = *(_DWORD *)(v11 + 128);
    v48 = "Start Ic3 frame processor";
    v49 = (const char *)&xmmword_1800C21A0;
    v50 = "DirectStreamMedia_Service";
    v51 = "RdpAvenc";
    *(_QWORD *)v52 = 0x1000000;
    v53[0] = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800B142B,
      a3,
      a4,
      (__int64)v53,
      (__int64)v52,
      (__int64)&v51,
      (__int64)&v50,
      (__int64)&v49,
      (__int64)&v48,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)&v57);
  }
  Rdp::Modern::Utils::CInflightRecorder::push0(
    (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
    L"Ic3FrameProcessorStart",
    "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::Start",
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    0xA0u);
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v14 = *(_QWORD *)(a1 + 96);
    v53[0] = v14 + 112;
    LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(v14 + 104) + 136LL);
    v56 = *(_DWORD *)(v14 + 128);
    *(_QWORD *)v52 = "StartFrameProcessor";
    v51 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::Start";
    LODWORD(v57) = 168;
    v50 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)qword_1800B14B0,
      v12,
      v13,
      (__int64)&v50,
      (__int64)&v57,
      (__int64)&v51,
      (__int64)v52,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)v53);
  }
  v15 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 200LL);
  v16 = *(_QWORD *)(a1 + 144);
  *(_QWORD *)(a1 + 144) = v15;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
  if ( v16 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
    retaddr,
    172,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    2147549183LL);
  v17 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 208LL);
  v53[0] = v17;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
  wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
    retaddr,
    175,
    "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    2147549183LL);
  v18 = *(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 80LL);
  v19 = (_QWORD *)(a1 + 152);
  v20 = *(_QWORD *)(a1 + 152);
  *(_QWORD *)(a1 + 152) = 0;
  if ( v20 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  v18(v17, a1 + 152);
  if ( *v19 )
  {
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      v23 = *(_QWORD *)(a1 + 96);
      *(_QWORD *)v52 = v23 + 112;
      LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(v23 + 104) + 136LL);
      v56 = *(_DWORD *)(v23 + 128);
      v51 = "Getting Media Clock Timestamp";
      v50 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncP"
            "rocessor>::Start";
      LODWORD(v57) = 187;
      v49 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B13CB,
        v21,
        v22,
        (__int64)&v49,
        (__int64)&v57,
        (__int64)&v50,
        (__int64)&v51,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)v52);
    }
    v24 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v19 + 24LL))(*v19);
    if ( (unsigned int)dword_1800C1058 > 5 )
    {
      *(_QWORD *)v52 = v24;
      v27 = *(_QWORD *)(a1 + 96);
      v51 = (const char *)(v27 + 112);
      LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(v27 + 104) + 136LL);
      v56 = *(_DWORD *)(v27 + 128);
      v50 = "Media Clock Timestamp retrieved";
      v49 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncP"
            "rocessor>::Start";
      LODWORD(v57) = 198;
      v48 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&byte_1800B1307,
        v25,
        v26,
        (__int64)&v48,
        (__int64)&v57,
        (__int64)&v49,
        (__int64)&v50,
        (__int64)&v56,
        (__int64)&v55,
        (__int64)&v51,
        (__int64)v52);
    }
  }
  else if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v28 = *(_QWORD *)(a1 + 96);
    *(_QWORD *)v52 = v28 + 112;
    LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(v28 + 104) + 136LL);
    v56 = *(_DWORD *)(v28 + 128);
    v51 = "No media clock available";
    v50 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::Start";
    LODWORD(v57) = 208;
    v49 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800B136B,
      v21,
      v22,
      (__int64)&v49,
      (__int64)&v57,
      (__int64)&v50,
      (__int64)&v51,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)v52);
  }
  started = Rdp::Avenc::Ic3::CDsGfxChannel::SendStartStreamPdu(
              *(Rdp::Avenc::Ic3::CDsGfxChannel **)(a1 + 144),
              (const struct _GUID *)(*(_QWORD *)(a1 + 96) + 112LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 96) + 128LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 96) + 140LL),
              *(_DWORD *)(*(_QWORD *)(a1 + 96) + 144LL),
              (const struct tagRECT *)(*(_QWORD *)(a1 + 96) + 176LL));
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xDA,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp",
    (const char *)started,
    (int)"Unable to send start stream pdu.",
    (const char *)v46);
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 104LL) + 288LL) )
  {
    *(_BYTE *)(a1 + 352) = 0;
    v32 = operator new(8u);
    *v32 = a1 - 80;
    v55 = v32;
    v47 = (struct tagRECT *)&v52[2];
    v44 = 0;
    v33 = _o__beginthreadex(
            0,
            0,
            ____Invoke_V__tuple_V_lambda_1___CO___Start___CIc3FrameProcessor_UIGpuFrameProcessor_Avenc_Rdp__UIGpuFrameAsyncProcessor_23__Ic3_Avenc_Rdp__UEAAJXZ__std___0A__thread_std__CAIPEAX_Z,
            v32);
    *(_QWORD *)v52 = v33;
    if ( !v33 )
    {
      v52[2] = 0;
      std::_Throw_Cpp_error(6);
    }
    if ( *(_DWORD *)(a1 + 336) )
    {
      _o_terminate(v34, v33);
      __debugbreak();
    }
    v35 = v52[2];
    v36 = v52[3];
    *(_OWORD *)v52 = 0;
    *(_QWORD *)(a1 + 328) = v33;
    *(_DWORD *)(a1 + 336) = v35;
    *(_DWORD *)(a1 + 340) = v36;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
  {
    v5 = 0;
  }
  v37 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v38 = GetCurrentThreadId();
    LOBYTE(v39) = v37;
    LOBYTE(v40) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v40,
      v39,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v44,
      (int)v47,
      11,
      &WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids,
      v38);
  }
  if ( (unsigned int)dword_1800C1058 > 5 )
  {
    v41 = *(_QWORD *)(a1 + 96);
    v53[0] = v41 + 112;
    LODWORD(v55) = *(_DWORD *)(*(_QWORD *)(v41 + 104) + 136LL);
    v56 = *(_DWORD *)(v41 + 128);
    *(_QWORD *)v52 = "StartFrameProcessorDone";
    v51 = "Rdp::Avenc::Ic3::CIc3FrameProcessor<struct Rdp::Avenc::IGpuFrameProcessor,struct Rdp::Avenc::IGpuFrameAsyncProcessor>::Start";
    LODWORD(v57) = 234;
    v50 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3frameprocessor.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)byte_1800B1223,
      v30,
      v31,
      (__int64)&v50,
      (__int64)&v57,
      (__int64)&v51,
      (__int64)v52,
      (__int64)&v56,
      (__int64)&v55,
      (__int64)v53);
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  return 0;
}

```

## disassembly

```asm
0x18004b700  mov     [rsp+arg_0], rbx
0x18004b705  push    rsi
0x18004b706  push    rdi
0x18004b707  push    r12
0x18004b709  push    r14
0x18004b70b  push    r15
0x18004b70d  sub     rsp, 0B0h
0x18004b714  mov     rbx, rcx
0x18004b717  lea     rcx, WPP_GLOBAL_Control
0x18004b71e  mov     rax, cs:WPP_GLOBAL_Control
0x18004b725  mov     sil, 1
0x18004b728  cmp     rax, rcx
0x18004b72b  jz      short loc_18004B73E
0x18004b72d  test    [rax+1Ch], sil
0x18004b731  jz      short loc_18004B73E
0x18004b733  cmp     byte ptr [rax+19h], 4
0x18004b737  jb      short loc_18004B73E
0x18004b739  mov     dil, sil
0x18004b73c  jmp     short loc_18004B741
0x18004b73e  xor     dil, dil
0x18004b741  lea     rax, WPP_RECORDER_INITIALIZED
0x18004b748  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18004b74f  setnz   r14b
0x18004b753  test    dil, dil
0x18004b756  jnz     short loc_18004B75D
0x18004b758  test    r14b, r14b
0x18004b75b  jz      short loc_18004B794
0x18004b75d  call    cs:__imp_GetCurrentThreadId
0x18004b763  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18004b767  lea     r15, WPP_82575e15b34e32cfad750d208edc4dfe_Traceguids
0x18004b76e  mov     [rsp+0D8h+MessageGuid], r15; MessageGuid
0x18004b773  mov     [rsp+0D8h+var_A8], 0Ah; __int16
0x18004b77a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b781  mov     r9, [rcx+28h]; int
0x18004b785  mov     r8b, r14b; int
0x18004b788  mov     dl, dil; int
0x18004b78b  mov     rcx, [rcx+10h]; int
0x18004b78f  call    WPP_RECORDER_AND_TRACE_SF_D
0x18004b794  mov     eax, cs:dword_1800C1058
0x18004b79a  cmp     eax, 4
0x18004b79d  jbe     loc_18004B8D4
0x18004b7a3  mov     rcx, cs:qword_1800C1070
0x18004b7aa  mov     rax, cs:qword_1800C1068
0x18004b7b1  mov     rdx, 470000000000h
0x18004b7bb  test    rdx, rax
0x18004b7be  jz      loc_18004B8D4
0x18004b7c4  mov     rax, rcx
0x18004b7c7  and     rax, rdx
0x18004b7ca  cmp     rax, rcx
0x18004b7cd  jnz     loc_18004B8D4
0x18004b7d3  mov     rdx, [rbx+60h]
0x18004b7d7  lea     rax, [rdx+70h]
0x18004b7db  mov     [rsp+0D8h+arg_18], rax
0x18004b7e3  mov     rax, [rdx+68h]
0x18004b7e7  mov     ecx, [rax+88h]
0x18004b7ed  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004b7f4  mov     eax, [rdx+80h]
0x18004b7fa  mov     [rsp+0D8h+arg_10], eax
0x18004b801  lea     rax, aStartIc3FrameP; "Start Ic3 frame processor"
0x18004b808  mov     [rsp+0D8h+var_68], rax
0x18004b80d  lea     rax, xmmword_1800C21A0
0x18004b814  mov     [rsp+0D8h+var_60], rax
0x18004b819  lea     rax, aDirectstreamme; "DirectStreamMedia_Service"
0x18004b820  mov     [rsp+0D8h+var_58], rax
0x18004b828  lea     rax, aRdpavenc; "RdpAvenc"
0x18004b82f  mov     [rsp+0D8h+var_50], rax
0x18004b837  mov     qword ptr [rsp+0D8h+var_48], 1000000h
0x18004b843  lea     rax, aCheckpoint; "Checkpoint"
0x18004b84a  mov     [rsp+0D8h+var_38], rax
0x18004b852  lea     rax, [rsp+0D8h+arg_18]
0x18004b85a  mov     [rsp+0D8h+var_78], rax
0x18004b85f  lea     rax, [rsp+0D8h+arg_8]
0x18004b867  mov     [rsp+0D8h+var_80], rax
0x18004b86c  lea     rax, [rsp+0D8h+arg_10]
0x18004b874  mov     [rsp+0D8h+var_88], rax
0x18004b879  lea     rax, [rsp+0D8h+var_68]
0x18004b87e  mov     [rsp+0D8h+var_90], rax
0x18004b883  lea     rax, [rsp+0D8h+var_60]
0x18004b888  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004b88d  lea     rax, [rsp+0D8h+var_58]
0x18004b895  mov     [rsp+0D8h+MessageGuid], rax
0x18004b89a  lea     rax, [rsp+0D8h+var_50]
0x18004b8a2  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004b8a7  lea     rax, [rsp+0D8h+var_48]
0x18004b8af  mov     [rsp+0D8h+var_B0], rax
0x18004b8b4  lea     rax, [rsp+0D8h+var_38]
0x18004b8bc  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004b8c1  lea     rdx, byte_1800B142B
0x18004b8c8  lea     rcx, dword_1800C1058
0x18004b8cf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U4@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@65@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004b8d4  mov     [rsp+0D8h+var_B8], 0A0h; unsigned int
0x18004b8dc  lea     r14, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004b8e3  mov     r9, r14; char *
0x18004b8e6  lea     rdi, aRdpAvencIc3Cic_8; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004b8ed  mov     r8, rdi; char *
0x18004b8f0  lea     rdx, aIc3frameproces; "Ic3FrameProcessorStart"
0x18004b8f7  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18004b8fe  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18004b903  mov     eax, cs:dword_1800C1058
0x18004b909  cmp     eax, 5
0x18004b90c  jbe     loc_18004B9D8
0x18004b912  mov     rdx, [rbx+60h]
0x18004b916  lea     rax, [rdx+70h]
0x18004b91a  mov     [rsp+0D8h+var_38], rax
0x18004b922  mov     rax, [rdx+68h]
0x18004b926  mov     ecx, [rax+88h]
0x18004b92c  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004b933  mov     eax, [rdx+80h]
0x18004b939  mov     [rsp+0D8h+arg_10], eax
0x18004b940  lea     rax, aStartframeproc_1; "StartFrameProcessor"
0x18004b947  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004b94f  mov     [rsp+0D8h+var_50], rdi
0x18004b957  mov     dword ptr [rsp+0D8h+arg_18], 0A8h
0x18004b962  mov     [rsp+0D8h+var_58], r14
0x18004b96a  lea     rax, [rsp+0D8h+var_38]
0x18004b972  mov     [rsp+0D8h+var_88], rax
0x18004b977  lea     rax, [rsp+0D8h+arg_8]
0x18004b97f  mov     [rsp+0D8h+var_90], rax
0x18004b984  lea     rax, [rsp+0D8h+arg_10]
0x18004b98c  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004b991  lea     rax, [rsp+0D8h+var_48]
0x18004b999  mov     [rsp+0D8h+MessageGuid], rax
0x18004b99e  lea     rax, [rsp+0D8h+var_50]
0x18004b9a6  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004b9ab  lea     rax, [rsp+0D8h+arg_18]
0x18004b9b3  mov     [rsp+0D8h+var_B0], rax
0x18004b9b8  lea     rax, [rsp+0D8h+var_58]
0x18004b9c0  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004b9c5  lea     rdx, qword_1800B14B0
0x18004b9cc  lea     rcx, dword_1800C1058
0x18004b9d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004b9d8  lea     r15, [rbx+90h]
0x18004b9df  mov     rax, [rbx+60h]
0x18004b9e3  mov     rcx, [rax+0C8h]
0x18004b9ea  mov     rdi, [r15]
0x18004b9ed  mov     [r15], rcx
0x18004b9f0  test    rcx, rcx
0x18004b9f3  jz      short loc_18004BA01
0x18004b9f5  mov     rax, [rcx]
0x18004b9f8  mov     rax, [rax+8]
0x18004b9fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba01  test    rdi, rdi
0x18004ba04  jz      short loc_18004BA16
0x18004ba06  mov     rax, [rdi]
0x18004ba09  mov     rcx, rdi
0x18004ba0c  mov     rax, [rax+10h]
0x18004ba10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba15  nop
0x18004ba16  mov     rcx, [rsp+0D8h]
0x18004ba1e  lea     rax, aUnableToRetrie_0; "Unable to retrieve DS GFX channel."
0x18004ba25  mov     [rsp+0D8h+var_B0], rax
0x18004ba2a  mov     qword ptr [rsp+0D8h+var_B8], r15
0x18004ba2f  mov     r12d, 8000FFFFh
0x18004ba35  mov     r9d, r12d
0x18004ba38  mov     r8, r14
0x18004ba3b  mov     edx, 0ACh
0x18004ba40  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18004ba45  mov     rax, [rbx+60h]
0x18004ba49  mov     rdi, [rax+0D0h]
0x18004ba50  mov     [rsp+0D8h+var_38], rdi
0x18004ba58  test    rdi, rdi
0x18004ba5b  jz      short loc_18004BA6D
0x18004ba5d  mov     rax, [rdi]
0x18004ba60  mov     rcx, rdi
0x18004ba63  mov     rax, [rax+8]
0x18004ba67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ba6c  nop
0x18004ba6d  mov     rcx, [rsp+0D8h]
0x18004ba75  lea     rax, aUnableToRetrie; "Unable to retrieve DS media control."
0x18004ba7c  mov     [rsp+0D8h+var_B0], rax
0x18004ba81  lea     rax, [rsp+0D8h+var_38]
0x18004ba89  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004ba8e  mov     r9d, r12d
0x18004ba91  mov     r8, r14
0x18004ba94  mov     edx, 0AFh
0x18004ba99  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18004ba9e  mov     rax, [rdi]
0x18004baa1  mov     r12, [rax+50h]
0x18004baa5  lea     r14, [rbx+98h]
0x18004baac  mov     rcx, [r14]
0x18004baaf  mov     qword ptr [r14], 0
0x18004bab6  test    rcx, rcx
0x18004bab9  jz      short loc_18004BAC8
0x18004babb  mov     rdx, [rcx]
0x18004babe  mov     rax, [rdx+10h]
0x18004bac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bac7  nop
0x18004bac8  mov     rdx, r14
0x18004bacb  mov     rcx, rdi
0x18004bace  mov     rax, r12
0x18004bad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bad6  xor     r12d, r12d
0x18004bad9  cmp     [r14], r12
0x18004badc  mov     eax, cs:dword_1800C1058
0x18004bae2  jz      loc_18004BCBF
0x18004bae8  cmp     eax, 5
0x18004baeb  jbe     loc_18004BBBF
0x18004baf1  mov     rdx, [rbx+60h]
0x18004baf5  lea     rax, [rdx+70h]
0x18004baf9  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004bb01  mov     rax, [rdx+68h]
0x18004bb05  mov     ecx, [rax+88h]
0x18004bb0b  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004bb12  mov     eax, [rdx+80h]
0x18004bb18  mov     [rsp+0D8h+arg_10], eax
0x18004bb1f  lea     rax, aGettingMediaCl; "Getting Media Clock Timestamp"
0x18004bb26  mov     [rsp+0D8h+var_50], rax
0x18004bb2e  lea     rax, aRdpAvencIc3Cic_8; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004bb35  mov     [rsp+0D8h+var_58], rax
0x18004bb3d  mov     dword ptr [rsp+0D8h+arg_18], 0BBh
0x18004bb48  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004bb4f  mov     [rsp+0D8h+var_60], rax
0x18004bb54  lea     rax, [rsp+0D8h+var_48]
0x18004bb5c  mov     [rsp+0D8h+var_88], rax
0x18004bb61  lea     rax, [rsp+0D8h+arg_8]
0x18004bb69  mov     [rsp+0D8h+var_90], rax
0x18004bb6e  lea     rax, [rsp+0D8h+arg_10]
0x18004bb76  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004bb7b  lea     rax, [rsp+0D8h+var_50]
0x18004bb83  mov     [rsp+0D8h+MessageGuid], rax
0x18004bb88  lea     rax, [rsp+0D8h+var_58]
0x18004bb90  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004bb95  lea     rax, [rsp+0D8h+arg_18]
0x18004bb9d  mov     [rsp+0D8h+var_B0], rax
0x18004bba2  lea     rax, [rsp+0D8h+var_60]
0x18004bba7  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004bbac  lea     rdx, byte_1800B13CB
0x18004bbb3  lea     rcx, dword_1800C1058
0x18004bbba  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18004bbbf  mov     rcx, [r14]
0x18004bbc2  mov     rax, [rcx]
0x18004bbc5  mov     rax, [rax+18h]
0x18004bbc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbce  mov     ecx, cs:dword_1800C1058
0x18004bbd4  cmp     ecx, 5
0x18004bbd7  jbe     loc_18004BD96
0x18004bbdd  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004bbe5  mov     rdx, [rbx+60h]
0x18004bbe9  lea     rax, [rdx+70h]
0x18004bbed  mov     [rsp+0D8h+var_50], rax
0x18004bbf5  mov     rax, [rdx+68h]
0x18004bbf9  mov     ecx, [rax+88h]
0x18004bbff  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004bc06  mov     eax, [rdx+80h]
0x18004bc0c  mov     [rsp+0D8h+arg_10], eax
0x18004bc13  lea     rax, aMediaClockTime; "Media Clock Timestamp retrieved"
0x18004bc1a  mov     [rsp+0D8h+var_58], rax
0x18004bc22  lea     rax, aRdpAvencIc3Cic_8; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004bc29  mov     [rsp+0D8h+var_60], rax
0x18004bc2e  mov     dword ptr [rsp+0D8h+arg_18], 0C6h
0x18004bc39  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004bc40  mov     [rsp+0D8h+var_68], rax
0x18004bc45  lea     rax, [rsp+0D8h+var_48]
0x18004bc4d  mov     [rsp+0D8h+var_80], rax
0x18004bc52  lea     rax, [rsp+0D8h+var_50]
0x18004bc5a  mov     [rsp+0D8h+var_88], rax
0x18004bc5f  lea     rax, [rsp+0D8h+arg_8]
0x18004bc67  mov     [rsp+0D8h+var_90], rax
0x18004bc6c  lea     rax, [rsp+0D8h+arg_10]
0x18004bc74  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004bc79  lea     rax, [rsp+0D8h+var_58]
0x18004bc81  mov     [rsp+0D8h+MessageGuid], rax
0x18004bc86  lea     rax, [rsp+0D8h+var_60]
0x18004bc8b  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004bc90  lea     rax, [rsp+0D8h+arg_18]
0x18004bc98  mov     [rsp+0D8h+var_B0], rax
0x18004bc9d  lea     rax, [rsp+0D8h+var_68]
0x18004bca2  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18004bca7  lea     rdx, byte_1800B1307
0x18004bcae  lea     rcx, dword_1800C1058
0x18004bcb5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U2@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3344AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<8> const &)
0x18004bcba  jmp     loc_18004BD96
0x18004bcbf  cmp     eax, 5
0x18004bcc2  jbe     loc_18004BD96
0x18004bcc8  mov     rdx, [rbx+60h]
0x18004bccc  lea     rax, [rdx+70h]
0x18004bcd0  mov     qword ptr [rsp+0D8h+var_48], rax
0x18004bcd8  mov     rax, [rdx+68h]
0x18004bcdc  mov     ecx, [rax+88h]
0x18004bce2  mov     dword ptr [rsp+0D8h+arg_8], ecx
0x18004bce9  mov     eax, [rdx+80h]
0x18004bcef  mov     [rsp+0D8h+arg_10], eax
0x18004bcf6  lea     rax, aNoMediaClockAv; "No media clock available"
0x18004bcfd  mov     [rsp+0D8h+var_50], rax
0x18004bd05  lea     rax, aRdpAvencIc3Cic_8; "Rdp::Avenc::Ic3::CIc3FrameProcessor<str"...
0x18004bd0c  mov     [rsp+0D8h+var_58], rax
0x18004bd14  mov     dword ptr [rsp+0D8h+arg_18], 0D0h
0x18004bd1f  lea     rax, aOnecoreuapTerm_23; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004bd26  mov     [rsp+0D8h+var_60], rax
0x18004bd2b  lea     rax, [rsp+0D8h+var_48]
0x18004bd33  mov     [rsp+0D8h+var_88], rax
0x18004bd38  lea     rax, [rsp+0D8h+arg_8]
0x18004bd40  mov     [rsp+0D8h+var_90], rax
0x18004bd45  lea     rax, [rsp+0D8h+arg_10]
0x18004bd4d  mov     qword ptr [rsp+0D8h+var_98], rax
0x18004bd52  lea     rax, [rsp+0D8h+var_50]
0x18004bd5a  mov     [rsp+0D8h+MessageGuid], rax
0x18004bd5f  lea     rax, [rsp+0D8h+var_58]
0x18004bd67  mov     qword ptr [rsp+0D8h+var_A8], rax
0x18004bd6c  lea     rax, [rsp+0D8h+arg_18]
  ... truncated ...
```
