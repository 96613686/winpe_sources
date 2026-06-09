# Rdp::Avenc::Raw::CRawProcessor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x180039b00`
- end: `0x180039fea`
- name: `?CreateMonitor@CRawProcessor@Raw@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1258`
- prototype: `__int64 __fastcall(Rdp::Avenc::Raw::CRawProcessor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x1800018c4`
- `0x1800065a4`
- `0x18000ec04`
- `0x1800146bc`
- `0x180014e7c`
- `0x1800150ac`
- `0x1800153f8`
- `0x180015480`
- `0x1800223f8`
- `0x180039b00`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039f6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039b66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180039f6f`

## string_xrefs

- `0x180039c3a`: `Create monitor context`
- `0x180039eb7`: `Create monitor context`
- `0x180039cd7`: `MonitorCreate`
- `0x180039cd0`: `Rdp::Avenc::Raw::CRawProcessor::CreateMonitor`
- `0x180039ec3`: `Rdp::Avenc::Raw::CRawProcessor::CreateMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Rdp::Avenc::Raw::CRawProcessor::CreateMonitor(
        Rdp::Avenc::Raw::CRawProcessor *this,
        struct Rdp::Avenc::IMonitorContext **a2,
        struct IPropertyStore *a3)
{
  char v5; // si
  bool v6; // bl
  bool v7; // r14
  char CurrentThreadId; // al
  int v9; // r8d
  int v10; // edx
  int v11; // r8d
  int v12; // r9d
  char *v13; // rbx
  const void *v14; // r9
  int v15; // r12d
  __int64 v16; // r13
  const char *v17; // r14
  __int64 v18; // r14
  int v19; // r8d
  const char *v20; // r9
  const char *v21; // r13
  _OWORD *v22; // r14
  __int64 v23; // rax
  bool v24; // bl
  char v25; // al
  int v26; // r8d
  int v27; // edx
  __int64 result; // rax
  int v29; // [rsp+20h] [rbp-88h]
  int v30; // [rsp+20h] [rbp-88h]
  int v31; // [rsp+28h] [rbp-80h]
  int v32; // [rsp+28h] [rbp-80h]
  char *v33; // [rsp+30h] [rbp-78h]
  const char *v34; // [rsp+50h] [rbp-58h] BYREF
  unsigned __int64 v35; // [rsp+58h] [rbp-50h] BYREF
  int v36[2]; // [rsp+60h] [rbp-48h] BYREF
  __int64 v37; // [rsp+68h] [rbp-40h] BYREF
  const char *v38; // [rsp+70h] [rbp-38h] BYREF
  unsigned __int64 v39; // [rsp+78h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  const char *v42; // [rsp+C8h] [rbp+20h] BYREF

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
      v29,
      v31,
      14,
      &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
        (const char *)0x80004003LL,
        v29);
    LOBYTE(v29) = *((_BYTE *)this + 176) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v29,
      (bool)"Processor is not started",
      v33);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      LODWORD(v42) = *((_DWORD *)this + 20);
      v34 = "Create monitor context";
      v35 = (unsigned __int64)&xmmword_1800C21A0;
      *(_QWORD *)v36 = "RdpAvenc";
      v37 = 0x1000000;
      v38 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800AF73D,
        v11,
        v12,
        (__int64)&v38,
        (__int64)&v37,
        (__int64)v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v42);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"MonitorCreate",
      "Rdp::Avenc::Raw::CRawProcessor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
      0x93u);
    v13 = (char *)operator new(0xD8u);
    v42 = v13;
    Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(
      (__int64)v13,
      (__int64)this - 80,
      (__int64)a3);
    *(_QWORD *)v13 = &Rdp::Avenc::Raw::CMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
    v35 = (unsigned __int64)(v13 + 80);
    *((_QWORD *)v13 + 10) = &Rdp::Avenc::Raw::CMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'};
    *((_QWORD *)v13 + 11) = &Rdp::Avenc::Raw::CMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'};
    *((_QWORD *)v13 + 26) = 0;
    v34 = v13;
    ((void (__fastcall *)(char *))Rdp::Utils::Com::ComObject<Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Yuv::CYuvProcessor,>,Rdp::Avenc::IMonitorContext1,Rdp::Avenc::ICursorControl1>::AddRef)(v13);
    v38 = (char *)this + 48;
    v14 = v13 + 120;
    v37 = *((_QWORD *)this + 6);
    v42 = *(const char **)(v37 + 8);
    v15 = 0;
    *(_QWORD *)v36 = 0;
    v16 = v37;
    v17 = v42;
    if ( !v42[25] )
    {
      do
      {
        v42 = v17;
        if ( memcmp_0(v17 + 32, v14, 0x10u) >= 0 )
        {
          v15 = 1;
          v16 = (__int64)v17;
          v17 = *(const char **)v17;
        }
        else
        {
          v15 = 0;
          v17 = (const char *)*((_QWORD *)v17 + 2);
        }
        v14 = v13 + 120;
      }
      while ( !v17[25] );
      v14 = v13 + 120;
    }
    if ( *(_BYTE *)(v16 + 25) || memcmp_0(v14, (const void *)(v16 + 32), 0x10u) < 0 )
    {
      v21 = v38;
      if ( *((_QWORD *)v38 + 1) == 0x492492492492492LL )
        std::_Throw_tree_length_error();
      v39 = 0;
      v22 = operator new(0x38u);
      v22[2] = *(_OWORD *)(v13 + 120);
      *((_QWORD *)v22 + 6) = v13;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
      v23 = v37;
      *(_QWORD *)v22 = v37;
      *((_QWORD *)v22 + 1) = v23;
      *((_QWORD *)v22 + 2) = v23;
      *((_WORD *)v22 + 12) = 0;
      v38 = v42;
      v39 = __PAIR64__(v36[0], v15);
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(
        v21,
        &v38,
        v22);
    }
    else
    {
      v18 = *(_QWORD *)(v16 + 48);
      *(_QWORD *)(v16 + 48) = v13;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v38 = "Create monitor context";
      v37 = (__int64)"Rdp::Avenc::Raw::CRawProcessor::CreateMonitor";
      LODWORD(v42) = 151;
      *(_QWORD *)v36 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&byte_1800AF707,
        v19,
        (_DWORD)v20,
        (__int64)v36,
        (__int64)&v42,
        (__int64)&v37,
        (__int64)&v38);
    }
    *a2 = (struct Rdp::Avenc::IMonitorContext *)(v35 & -(__int64)(v13 != 0));
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v24 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v25 = GetCurrentThreadId();
      LOBYTE(v26) = v24;
      LOBYTE(v27) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v27,
        v26,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v30,
        v32,
        15,
        &WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids,
        v25);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x9E,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\rawprocessor\\rawprocessor.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x180039b00  mov     [rsp+arg_0], rbx
0x180039b05  mov     [rsp+arg_8], rdx
0x180039b0a  push    rsi
0x180039b0b  push    r12
0x180039b0d  push    r13
0x180039b0f  push    r14
0x180039b11  push    r15
0x180039b13  sub     rsp, 80h
0x180039b1a  mov     r12, r8
0x180039b1d  mov     r13, rcx
0x180039b20  lea     rcx, WPP_GLOBAL_Control
0x180039b27  mov     rax, cs:WPP_GLOBAL_Control
0x180039b2e  mov     esi, 1
0x180039b33  cmp     rax, rcx
0x180039b36  jz      short loc_180039B49
0x180039b38  test    [rax+1Ch], sil
0x180039b3c  jz      short loc_180039B49
0x180039b3e  cmp     byte ptr [rax+19h], 4
0x180039b42  jb      short loc_180039B49
0x180039b44  mov     bl, sil
0x180039b47  jmp     short loc_180039B4B
0x180039b49  xor     bl, bl
0x180039b4b  lea     rax, WPP_RECORDER_INITIALIZED
0x180039b52  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039b59  setnz   r14b
0x180039b5d  test    bl, bl
0x180039b5f  jnz     short loc_180039B66
0x180039b61  test    r14b, r14b
0x180039b64  jz      short loc_180039B9C
0x180039b66  call    cs:__imp_GetCurrentThreadId
0x180039b6c  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180039b70  lea     r15, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x180039b77  mov     [rsp+0A8h+MessageGuid], r15; MessageGuid
0x180039b7c  mov     word ptr [rsp+0A8h+var_78], 0Eh; char *
0x180039b83  mov     rcx, cs:WPP_GLOBAL_Control
0x180039b8a  mov     r9, [rcx+28h]; int
0x180039b8e  mov     r8b, r14b; int
0x180039b91  mov     dl, bl; int
0x180039b93  mov     rcx, [rcx+10h]; int
0x180039b97  call    WPP_RECORDER_AND_TRACE_SF_D
0x180039b9c  mov     rcx, [rsp+0A8h]; this
0x180039ba4  cmp     [rsp+0A8h+arg_8], 0
0x180039bad  jz      loc_180039FCB
0x180039bb3  cmp     byte ptr [r13+0B0h], 0
0x180039bbb  setz    al
0x180039bbe  mov     rcx, [rsp+0A8h]; this
0x180039bc6  lea     rdx, aProcessorIsNot; "Processor is not started"
0x180039bcd  mov     qword ptr [rsp+0A8h+var_80], rdx; bool
0x180039bd2  mov     byte ptr [rsp+0A8h+var_88], al; int
0x180039bd6  mov     r9d, 8000FFFFh; char *
0x180039bdc  lea     r15, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180039be3  mov     r8, r15; unsigned int
0x180039be6  mov     edx, 8Ch; void *
0x180039beb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180039bf0  mov     eax, cs:dword_1800C1058
0x180039bf6  cmp     eax, 4
0x180039bf9  jbe     loc_180039CC5
0x180039bff  mov     rcx, cs:qword_1800C1070
0x180039c06  mov     rax, cs:qword_1800C1068
0x180039c0d  mov     rdx, 470000000000h
0x180039c17  test    rdx, rax
0x180039c1a  jz      loc_180039CC5
0x180039c20  mov     rax, rcx
0x180039c23  and     rax, rdx
0x180039c26  cmp     rax, rcx
0x180039c29  jnz     loc_180039CC5
0x180039c2f  mov     eax, [r13+50h]
0x180039c33  mov     dword ptr [rsp+0A8h+arg_18], eax
0x180039c3a  lea     rbx, aCreateMonitorC; "Create monitor context"
0x180039c41  mov     [rsp+0A8h+var_58], rbx
0x180039c46  lea     rax, xmmword_1800C21A0
0x180039c4d  mov     [rsp+0A8h+var_50], rax
0x180039c52  lea     rax, aRdpavenc; "RdpAvenc"
0x180039c59  mov     qword ptr [rsp+0A8h+var_48], rax
0x180039c5e  mov     [rsp+0A8h+var_40], 1000000h
0x180039c67  lea     rax, aCheckpoint; "Checkpoint"
0x180039c6e  mov     [rsp+0A8h+var_38], rax
0x180039c73  lea     rax, [rsp+0A8h+arg_18]
0x180039c7b  mov     [rsp+0A8h+var_60], rax
0x180039c80  lea     rax, [rsp+0A8h+var_58]
0x180039c85  mov     qword ptr [rsp+0A8h+var_68], rax
0x180039c8a  lea     rax, [rsp+0A8h+var_50]
0x180039c8f  mov     [rsp+0A8h+MessageGuid], rax
0x180039c94  lea     rax, [rsp+0A8h+var_48]
0x180039c99  mov     [rsp+0A8h+var_78], rax
0x180039c9e  lea     rax, [rsp+0A8h+var_40]
0x180039ca3  mov     qword ptr [rsp+0A8h+var_80], rax
0x180039ca8  lea     rax, [rsp+0A8h+var_38]
0x180039cad  mov     qword ptr [rsp+0A8h+var_88], rax
0x180039cb2  lea     rdx, byte_1800AF73D
0x180039cb9  lea     rcx, dword_1800C1058
0x180039cc0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180039cc5  mov     [rsp+0A8h+var_88], 93h; unsigned int
0x180039ccd  mov     r9, r15; char *
0x180039cd0  lea     r8, aRdpAvencRawCra; "Rdp::Avenc::Raw::CRawProcessor::CreateM"...
0x180039cd7  lea     rdx, aMonitorcreate; "MonitorCreate"
0x180039cde  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180039ce5  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180039cea  mov     ecx, 0D8h; Size
0x180039cef  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039cf4  mov     rbx, rax
0x180039cf7  mov     [rsp+0A8h+arg_18], rax
0x180039cff  lea     rdx, [r13-50h]
0x180039d03  mov     r8, r12
0x180039d06  mov     rcx, rax
0x180039d09  call    ??0?$CMonitorContextBase@VCSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UICursorControl1@34@@Avenc@Rdp@@QEAA@PEAVCSinkWriterProcessor@SinkWriter@12@PEAUIPropertyStore@@@Z; Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *,IPropertyStore *)
0x180039d0e  lea     rax, ??_7CMonitorContext@Raw@Avenc@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Avenc::Raw::CMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x180039d15  mov     [rbx], rax
0x180039d18  lea     rax, [rbx+50h]
0x180039d1c  mov     [rsp+0A8h+var_50], rax
0x180039d21  lea     rcx, ??_7CMonitorContext@Raw@Avenc@Rdp@@6BIMonitorContext1@23@@; const Rdp::Avenc::Raw::CMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'}
0x180039d28  mov     [rax], rcx
0x180039d2b  lea     rax, ??_7CMonitorContext@Raw@Avenc@Rdp@@6BICursorControl1@23@@; const Rdp::Avenc::Raw::CMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'}
0x180039d32  mov     [rbx+58h], rax
0x180039d36  mov     qword ptr [rbx+0D0h], 0
0x180039d41  mov     [rsp+0A8h+var_58], rbx
0x180039d46  mov     rcx, rbx
0x180039d49  mov     rax, cs:off_18008B450
0x180039d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039d55  nop
0x180039d56  lea     rax, [r13+30h]
0x180039d5a  mov     [rsp+0A8h+var_38], rax
0x180039d5f  lea     r9, [rbx+78h]
0x180039d63  mov     rcx, [rax]
0x180039d66  mov     [rsp+0A8h+var_40], rcx
0x180039d6b  mov     rax, [rcx+8]
0x180039d6f  mov     [rsp+0A8h+arg_18], rax
0x180039d77  xor     r12d, r12d
0x180039d7a  xor     edx, edx
0x180039d7c  mov     qword ptr [rsp+0A8h+var_48], rdx
0x180039d81  mov     r13, rcx
0x180039d84  mov     r14, rax
0x180039d87  cmp     [rax+19h], dl
0x180039d8a  jnz     short loc_180039DCB
0x180039d8c  mov     [rsp+0A8h+arg_18], r14
0x180039d94  lea     rcx, [r14+20h]; Buf1
0x180039d98  mov     r8d, 10h; Size
0x180039d9e  mov     rdx, r9; Buf2
0x180039da1  call    memcmp_0
0x180039da6  test    eax, eax
0x180039da8  jns     short loc_180039DB3
0x180039daa  xor     r12d, r12d
0x180039dad  mov     r14, [r14+10h]
0x180039db1  jmp     short loc_180039DBC
0x180039db3  mov     r12d, esi
0x180039db6  mov     r13, r14
0x180039db9  mov     r14, [r14]
0x180039dbc  cmp     byte ptr [r14+19h], 0
0x180039dc1  lea     r9, [rbx+78h]
0x180039dc5  jz      short loc_180039D8C
0x180039dc7  lea     r9, [rbx+78h]
0x180039dcb  cmp     byte ptr [r13+19h], 0
0x180039dd0  jnz     short loc_180039E19
0x180039dd2  lea     rdx, [r13+20h]; Buf2
0x180039dd6  mov     r8d, 10h; Size
0x180039ddc  mov     rcx, r9; Buf1
0x180039ddf  call    memcmp_0
0x180039de4  test    eax, eax
0x180039de6  js      short loc_180039E19
0x180039de8  mov     r14, [r13+30h]
0x180039dec  mov     [r13+30h], rbx
0x180039df0  mov     rax, [rbx]
0x180039df3  mov     rcx, rbx
0x180039df6  mov     rax, [rax+8]
0x180039dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039dff  test    r14, r14
0x180039e02  jz      short loc_180039E14
0x180039e04  mov     rax, [r14]
0x180039e07  mov     rcx, r14
0x180039e0a  mov     rax, [rax+10h]
0x180039e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e13  nop
0x180039e14  jmp     loc_180039EAC
0x180039e19  mov     rax, 492492492492492h
0x180039e23  mov     r13, [rsp+0A8h+var_38]
0x180039e28  cmp     [r13+8], rax
0x180039e2c  jz      loc_180039FE3
0x180039e32  mov     [rsp+0A8h+var_38], r13
0x180039e37  mov     [rsp+0A8h+var_30], 0
0x180039e40  mov     ecx, 38h ; '8'; Size
0x180039e45  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180039e4a  mov     r14, rax
0x180039e4d  movups  xmm0, xmmword ptr [rbx+78h]
0x180039e51  movdqu  xmmword ptr [rax+20h], xmm0
0x180039e56  mov     [rax+30h], rbx
0x180039e5a  mov     rcx, [rbx]
0x180039e5d  mov     rax, [rcx+8]
0x180039e61  mov     rcx, rbx
0x180039e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039e69  nop
0x180039e6a  mov     rax, [rsp+0A8h+var_40]
0x180039e6f  mov     [r14], rax
0x180039e72  mov     [r14+8], rax
0x180039e76  mov     [r14+10h], rax
0x180039e7a  mov     word ptr [r14+18h], 0
0x180039e81  mov     rax, [rsp+0A8h+arg_18]
0x180039e89  mov     [rsp+0A8h+var_38], rax
0x180039e8e  mov     dword ptr [rsp+0A8h+var_30], r12d
0x180039e93  mov     rax, qword ptr [rsp+0A8h+var_48]
0x180039e98  mov     dword ptr [rsp+0A8h+var_30+4], eax
0x180039e9c  mov     r8, r14
0x180039e9f  lea     rdx, [rsp+0A8h+var_38]
0x180039ea4  mov     rcx, r13
0x180039ea7  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x180039eac  mov     eax, cs:dword_1800C1058
0x180039eb2  cmp     eax, 4
0x180039eb5  jbe     short loc_180039F1D
0x180039eb7  lea     rax, aCreateMonitorC; "Create monitor context"
0x180039ebe  mov     [rsp+0A8h+var_38], rax
0x180039ec3  lea     rax, aRdpAvencRawCra; "Rdp::Avenc::Raw::CRawProcessor::CreateM"...
0x180039eca  mov     [rsp+0A8h+var_40], rax
0x180039ecf  mov     dword ptr [rsp+0A8h+arg_18], 97h
0x180039eda  mov     qword ptr [rsp+0A8h+var_48], r15
0x180039edf  lea     rax, [rsp+0A8h+var_38]
0x180039ee4  mov     [rsp+0A8h+MessageGuid], rax
0x180039ee9  lea     rax, [rsp+0A8h+var_40]
0x180039eee  mov     [rsp+0A8h+var_78], rax
0x180039ef3  lea     rax, [rsp+0A8h+arg_18]
0x180039efb  mov     qword ptr [rsp+0A8h+var_80], rax; int
0x180039f00  lea     rax, [rsp+0A8h+var_48]
0x180039f05  mov     qword ptr [rsp+0A8h+var_88], rax; int
0x180039f0a  lea     rdx, byte_1800AF707
0x180039f11  lea     rcx, dword_1800C1058
0x180039f18  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180039f1d  neg     rbx
0x180039f20  sbb     rax, rax
0x180039f23  and     rax, [rsp+0A8h+var_50]
0x180039f28  mov     rcx, [rsp+0A8h+arg_8]
0x180039f30  mov     [rcx], rax
0x180039f33  mov     rax, cs:WPP_GLOBAL_Control
0x180039f3a  lea     rcx, WPP_GLOBAL_Control
0x180039f41  cmp     rax, rcx
0x180039f44  jz      short loc_180039F52
0x180039f46  test    [rax+1Ch], sil
0x180039f4a  jz      short loc_180039F52
0x180039f4c  cmp     byte ptr [rax+19h], 4
0x180039f50  jnb     short loc_180039F55
0x180039f52  xor     sil, sil
0x180039f55  lea     rax, WPP_RECORDER_INITIALIZED
0x180039f5c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180039f63  setnz   bl
0x180039f66  test    sil, sil
0x180039f69  jnz     short loc_180039F6F
0x180039f6b  test    bl, bl
0x180039f6d  jz      short loc_180039FA7
0x180039f6f  call    cs:__imp_GetCurrentThreadId
0x180039f75  mov     dword ptr [rsp+0A8h+var_68], eax; char
0x180039f79  lea     rax, WPP_9fd2a530fe4f38971d9b2d15cc14ffcc_Traceguids
0x180039f80  mov     [rsp+0A8h+MessageGuid], rax; MessageGuid
0x180039f85  mov     word ptr [rsp+0A8h+var_78], 0Fh; __int16
0x180039f8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180039f93  mov     r9, [rcx+28h]; int
0x180039f97  mov     r8b, bl; int
0x180039f9a  mov     dl, sil; int
0x180039f9d  mov     rcx, [rcx+10h]; int
0x180039fa1  call    WPP_RECORDER_AND_TRACE_SF_D
0x180039fa6  nop
0x180039fa7  xor     eax, eax
0x180039fa9  jmp     short loc_180039FB2
0x180039fab  mov     eax, dword ptr [rsp+0A8h+arg_8]
0x180039fb2  mov     rbx, [rsp+0A8h+arg_0]
0x180039fba  add     rsp, 80h
0x180039fc1  pop     r15
0x180039fc3  pop     r14
0x180039fc5  pop     r13
0x180039fc7  pop     r12
0x180039fc9  pop     rsi
0x180039fca  retn
0x180039fcb  mov     r9d, 80004003h; char *
0x180039fd1  lea     r8, aOnecoreuapTerm_42; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180039fd8  mov     edx, 8Bh; void *
0x180039fdd  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180039fe3  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
