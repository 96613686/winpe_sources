# Rdp::Avenc::Yuv::CYuvProcessor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x18005a2e0`
- end: `0x18005a82c`
- name: `?CreateMonitor@CYuvProcessor@Yuv@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1356`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvProcessor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001008`
- `0x180003b08`
- `0x1800065a4`
- `0x18000ec04`
- `0x1800146bc`
- `0x180014e7c`
- `0x1800150ac`
- `0x1800153f8`
- `0x180015480`
- `0x1800223f8`
- `0x18005a2e0`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a7b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a346`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005a7b1`

## string_xrefs

- `0x18005a41a`: `Create monitor context`
- `0x18005a6ed`: `Create monitor context`
- `0x18005a4d9`: `MonitorCreate`
- `0x18005a4d2`: `Rdp::Avenc::Yuv::CYuvProcessor::CreateMonitor`
- `0x18005a6fc`: `Rdp::Avenc::Yuv::CYuvProcessor::CreateMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Rdp::Avenc::Yuv::CYuvProcessor::CreateMonitor(
        Rdp::Avenc::Yuv::CYuvProcessor *this,
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
  const char *v16; // r13
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
  int v29; // [rsp+20h] [rbp-A8h]
  int v30; // [rsp+20h] [rbp-A8h]
  int v31; // [rsp+28h] [rbp-A0h]
  int v32; // [rsp+28h] [rbp-A0h]
  char *v33; // [rsp+30h] [rbp-98h]
  const char *v34; // [rsp+60h] [rbp-68h] BYREF
  int *v35; // [rsp+68h] [rbp-60h] BYREF
  unsigned __int64 v36; // [rsp+70h] [rbp-58h] BYREF
  int v37[2]; // [rsp+78h] [rbp-50h] BYREF
  _QWORD v38[2]; // [rsp+80h] [rbp-48h] BYREF
  const char *v39; // [rsp+90h] [rbp-38h] BYREF
  unsigned __int64 v40; // [rsp+98h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  const char *v43; // [rsp+E8h] [rbp+20h] BYREF

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
      &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
        (const char *)0x80004003LL,
        v29);
    LOBYTE(v29) = *((_BYTE *)this + 168) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      (const char *)0x8000FFFFLL,
      v29,
      (bool)"Processor is not started",
      v33);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      LODWORD(v43) = *((_DWORD *)this + 18);
      v34 = "Create monitor context";
      v35 = &xmmword_1800C21A0;
      v36 = (unsigned __int64)"DirectStreamMedia_Driver";
      *(_QWORD *)v37 = "RdpAvenc";
      v38[0] = 0x1000000;
      v39 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800B3EA6,
        v11,
        v12,
        (__int64)&v39,
        (__int64)v38,
        (__int64)v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v43);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"MonitorCreate",
      "Rdp::Avenc::Yuv::CYuvProcessor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      0x98u);
    v13 = (char *)operator new(0xE8u);
    v43 = v13;
    Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(
      (__int64)v13,
      (__int64)this - 80,
      (__int64)a3);
    *(_QWORD *)v13 = &Rdp::Avenc::Yuv::CYuvMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'};
    v36 = (unsigned __int64)(v13 + 80);
    *((_QWORD *)v13 + 10) = &Rdp::Avenc::Yuv::CYuvMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'};
    *((_QWORD *)v13 + 11) = &Rdp::Avenc::Yuv::CYuvMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'};
    *((_QWORD *)v13 + 26) = 0;
    *((_QWORD *)v13 + 27) = 0;
    *((_QWORD *)v13 + 28) = 0;
    v35 = (int *)v13;
    ((void (__fastcall *)(char *))Rdp::Utils::Com::ComObject<Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::Yuv::CYuvProcessor,>,Rdp::Avenc::IMonitorContext1,Rdp::Avenc::ICursorControl1>::AddRef)(v13);
    v39 = (char *)this + 40;
    v14 = v13 + 120;
    v38[0] = *((_QWORD *)this + 5);
    v43 = *(const char **)(v38[0] + 8LL);
    v15 = 0;
    *(_QWORD *)v37 = 0;
    v16 = (const char *)v38[0];
    v17 = v43;
    if ( !v43[25] )
    {
      do
      {
        v43 = v17;
        if ( memcmp_0(v17 + 32, v14, 0x10u) >= 0 )
        {
          v15 = 1;
          v16 = v17;
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
    if ( v16[25] || memcmp_0(v14, v16 + 32, 0x10u) < 0 )
    {
      v21 = v39;
      if ( *((_QWORD *)v39 + 1) == 0x492492492492492LL )
        std::_Throw_tree_length_error();
      v40 = 0;
      v22 = operator new(0x38u);
      v22[2] = *(_OWORD *)(v13 + 120);
      *((_QWORD *)v22 + 6) = v13;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
      v23 = v38[0];
      *(_QWORD *)v22 = v38[0];
      *((_QWORD *)v22 + 1) = v23;
      *((_QWORD *)v22 + 2) = v23;
      *((_WORD *)v22 + 12) = 0;
      v39 = v43;
      v40 = __PAIR64__(v37[0], v15);
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(
        v21,
        &v39,
        v22);
    }
    else
    {
      v18 = *((_QWORD *)v16 + 6);
      *((_QWORD *)v16 + 6) = v13;
      (*(void (__fastcall **)(char *))(*(_QWORD *)v13 + 8LL))(v13);
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v39 = "Create monitor context";
      v38[0] = "Rdp::Avenc::Yuv::CYuvProcessor::CreateMonitor";
      LODWORD(v43) = 156;
      *(_QWORD *)v37 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800B3E70,
        v19,
        (_DWORD)v20,
        (__int64)v37,
        (__int64)&v43,
        (__int64)v38,
        (__int64)&v39);
    }
    *a2 = (struct Rdp::Avenc::IMonitorContext *)(v36 & -(__int64)(v13 != 0));
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
        &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
        v25);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA3,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
                           v20);
  }
  return result;
}

```

## disassembly

```asm
0x18005a2e0  mov     [rsp+arg_0], rbx
0x18005a2e5  mov     [rsp+arg_8], rdx
0x18005a2ea  push    rsi
0x18005a2eb  push    r12
0x18005a2ed  push    r13
0x18005a2ef  push    r14
0x18005a2f1  push    r15
0x18005a2f3  sub     rsp, 0A0h
0x18005a2fa  mov     r12, r8
0x18005a2fd  mov     r13, rcx
0x18005a300  lea     rcx, WPP_GLOBAL_Control
0x18005a307  mov     rax, cs:WPP_GLOBAL_Control
0x18005a30e  mov     esi, 1
0x18005a313  cmp     rax, rcx
0x18005a316  jz      short loc_18005A329
0x18005a318  test    [rax+1Ch], sil
0x18005a31c  jz      short loc_18005A329
0x18005a31e  cmp     byte ptr [rax+19h], 4
0x18005a322  jb      short loc_18005A329
0x18005a324  mov     bl, sil
0x18005a327  jmp     short loc_18005A32B
0x18005a329  xor     bl, bl
0x18005a32b  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a332  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a339  setnz   r14b
0x18005a33d  test    bl, bl
0x18005a33f  jnz     short loc_18005A346
0x18005a341  test    r14b, r14b
0x18005a344  jz      short loc_18005A37C
0x18005a346  call    cs:__imp_GetCurrentThreadId
0x18005a34c  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18005a350  lea     r15, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005a357  mov     [rsp+0C8h+MessageGuid], r15; MessageGuid
0x18005a35c  mov     word ptr [rsp+0C8h+var_98], 0Eh; char *
0x18005a363  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a36a  mov     r9, [rcx+28h]; int
0x18005a36e  mov     r8b, r14b; int
0x18005a371  mov     dl, bl; int
0x18005a373  mov     rcx, [rcx+10h]; int
0x18005a377  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005a37c  mov     rcx, [rsp+0C8h]; this
0x18005a384  cmp     [rsp+0C8h+arg_8], 0
0x18005a38d  jz      loc_18005A80D
0x18005a393  cmp     byte ptr [r13+0A8h], 0
0x18005a39b  setz    al
0x18005a39e  mov     rcx, [rsp+0C8h]; this
0x18005a3a6  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18005a3ad  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x18005a3b2  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x18005a3b6  mov     r9d, 8000FFFFh; char *
0x18005a3bc  lea     r15, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005a3c3  mov     r8, r15; unsigned int
0x18005a3c6  mov     edx, 90h; void *
0x18005a3cb  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18005a3d0  mov     eax, cs:dword_1800C1058
0x18005a3d6  cmp     eax, 4
0x18005a3d9  jbe     loc_18005A4C7
0x18005a3df  mov     rcx, cs:qword_1800C1070
0x18005a3e6  mov     rax, cs:qword_1800C1068
0x18005a3ed  mov     rdx, 470000000000h
0x18005a3f7  test    rdx, rax
0x18005a3fa  jz      loc_18005A4C7
0x18005a400  mov     rax, rcx
0x18005a403  and     rax, rdx
0x18005a406  cmp     rax, rcx
0x18005a409  jnz     loc_18005A4C7
0x18005a40f  mov     eax, [r13+48h]
0x18005a413  mov     dword ptr [rsp+0C8h+arg_18], eax
0x18005a41a  lea     rbx, aCreateMonitorC; "Create monitor context"
0x18005a421  mov     [rsp+0C8h+var_68], rbx
0x18005a426  lea     rax, xmmword_1800C21A0
0x18005a42d  mov     [rsp+0C8h+var_60], rax
0x18005a432  lea     rax, aDirectstreamme_0; "DirectStreamMedia_Driver"
0x18005a439  mov     [rsp+0C8h+var_58], rax
0x18005a43e  lea     rax, aRdpavenc; "RdpAvenc"
0x18005a445  mov     qword ptr [rsp+0C8h+var_50], rax
0x18005a44a  mov     [rsp+0C8h+var_48], 1000000h
0x18005a456  lea     rax, aCheckpoint; "Checkpoint"
0x18005a45d  mov     [rsp+0C8h+var_38], rax
0x18005a465  lea     rax, [rsp+0C8h+arg_18]
0x18005a46d  mov     [rsp+0C8h+var_78], rax
0x18005a472  lea     rax, [rsp+0C8h+var_68]
0x18005a477  mov     [rsp+0C8h+var_80], rax
0x18005a47c  lea     rax, [rsp+0C8h+var_60]
0x18005a481  mov     qword ptr [rsp+0C8h+var_88], rax
0x18005a486  lea     rax, [rsp+0C8h+var_58]
0x18005a48b  mov     [rsp+0C8h+MessageGuid], rax
0x18005a490  lea     rax, [rsp+0C8h+var_50]
0x18005a495  mov     [rsp+0C8h+var_98], rax
0x18005a49a  lea     rax, [rsp+0C8h+var_48]
0x18005a4a2  mov     qword ptr [rsp+0C8h+var_A0], rax
0x18005a4a7  lea     rax, [rsp+0C8h+var_38]
0x18005a4af  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18005a4b4  lea     rdx, word_1800B3EA6
0x18005a4bb  lea     rcx, dword_1800C1058
0x18005a4c2  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18005a4c7  mov     [rsp+0C8h+var_A8], 98h; unsigned int
0x18005a4cf  mov     r9, r15; char *
0x18005a4d2  lea     r8, aRdpAvencYuvCyu_1; "Rdp::Avenc::Yuv::CYuvProcessor::CreateM"...
0x18005a4d9  lea     rdx, aMonitorcreate; "MonitorCreate"
0x18005a4e0  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18005a4e7  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18005a4ec  mov     ecx, 0E8h; Size
0x18005a4f1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a4f6  mov     rbx, rax
0x18005a4f9  mov     [rsp+0C8h+arg_18], rax
0x18005a501  lea     rdx, [r13-50h]
0x18005a505  mov     r8, r12
0x18005a508  mov     rcx, rax
0x18005a50b  call    ??0?$CMonitorContextBase@VCSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UICursorControl1@34@@Avenc@Rdp@@QEAA@PEAVCSinkWriterProcessor@SinkWriter@12@PEAUIPropertyStore@@@Z; Rdp::Avenc::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>::CMonitorContextBase<Rdp::Avenc::SinkWriter::CSinkWriterProcessor,Rdp::Avenc::ICursorControl1>(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *,IPropertyStore *)
0x18005a510  lea     rax, ??_7CYuvMonitorContext@Yuv@Avenc@Rdp@@6BIUnknownBase@Com@Utils@3@@; const Rdp::Avenc::Yuv::CYuvMonitorContext::`vftable'{for `Rdp::Utils::Com::IUnknownBase'}
0x18005a517  mov     [rbx], rax
0x18005a51a  lea     rax, [rbx+50h]
0x18005a51e  mov     [rsp+0C8h+var_58], rax
0x18005a523  lea     rcx, ??_7CYuvMonitorContext@Yuv@Avenc@Rdp@@6BIMonitorContext1@23@@; const Rdp::Avenc::Yuv::CYuvMonitorContext::`vftable'{for `Rdp::Avenc::IMonitorContext1'}
0x18005a52a  mov     [rax], rcx
0x18005a52d  lea     rax, ??_7CYuvMonitorContext@Yuv@Avenc@Rdp@@6BICursorControl1@23@@; const Rdp::Avenc::Yuv::CYuvMonitorContext::`vftable'{for `Rdp::Avenc::ICursorControl1'}
0x18005a534  mov     [rbx+58h], rax
0x18005a538  mov     qword ptr [rbx+0D0h], 0
0x18005a543  mov     qword ptr [rbx+0D8h], 0
0x18005a54e  mov     qword ptr [rbx+0E0h], 0
0x18005a559  mov     [rsp+0C8h+var_60], rbx
0x18005a55e  mov     rcx, rbx
0x18005a561  mov     rax, cs:off_18008C330
0x18005a568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a56d  nop
0x18005a56e  lea     rax, [r13+28h]
0x18005a572  mov     [rsp+0C8h+var_38], rax
0x18005a57a  lea     r9, [rbx+78h]
0x18005a57e  mov     rcx, [rax]
0x18005a581  mov     [rsp+0C8h+var_48], rcx
0x18005a589  mov     rax, [rcx+8]
0x18005a58d  mov     [rsp+0C8h+arg_18], rax
0x18005a595  xor     r12d, r12d
0x18005a598  xor     edx, edx
0x18005a59a  mov     qword ptr [rsp+0C8h+var_50], rdx
0x18005a59f  mov     r13, rcx
0x18005a5a2  mov     r14, rax
0x18005a5a5  cmp     [rax+19h], dl
0x18005a5a8  jnz     short loc_18005A5E9
0x18005a5aa  mov     [rsp+0C8h+arg_18], r14
0x18005a5b2  lea     rcx, [r14+20h]; Buf1
0x18005a5b6  mov     r8d, 10h; Size
0x18005a5bc  mov     rdx, r9; Buf2
0x18005a5bf  call    memcmp_0
0x18005a5c4  test    eax, eax
0x18005a5c6  jns     short loc_18005A5D1
0x18005a5c8  xor     r12d, r12d
0x18005a5cb  mov     r14, [r14+10h]
0x18005a5cf  jmp     short loc_18005A5DA
0x18005a5d1  mov     r12d, esi
0x18005a5d4  mov     r13, r14
0x18005a5d7  mov     r14, [r14]
0x18005a5da  cmp     byte ptr [r14+19h], 0
0x18005a5df  lea     r9, [rbx+78h]
0x18005a5e3  jz      short loc_18005A5AA
0x18005a5e5  lea     r9, [rbx+78h]
0x18005a5e9  cmp     byte ptr [r13+19h], 0
0x18005a5ee  jnz     short loc_18005A637
0x18005a5f0  lea     rdx, [r13+20h]; Buf2
0x18005a5f4  mov     r8d, 10h; Size
0x18005a5fa  mov     rcx, r9; Buf1
0x18005a5fd  call    memcmp_0
0x18005a602  test    eax, eax
0x18005a604  js      short loc_18005A637
0x18005a606  mov     r14, [r13+30h]
0x18005a60a  mov     [r13+30h], rbx
0x18005a60e  mov     rax, [rbx]
0x18005a611  mov     rcx, rbx
0x18005a614  mov     rax, [rax+8]
0x18005a618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a61d  test    r14, r14
0x18005a620  jz      short loc_18005A632
0x18005a622  mov     rax, [r14]
0x18005a625  mov     rcx, r14
0x18005a628  mov     rax, [rax+10h]
0x18005a62c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a631  nop
0x18005a632  jmp     loc_18005A6E2
0x18005a637  mov     rax, 492492492492492h
0x18005a641  mov     r13, [rsp+0C8h+var_38]
0x18005a649  cmp     [r13+8], rax
0x18005a64d  jz      loc_18005A825
0x18005a653  mov     [rsp+0C8h+var_38], r13
0x18005a65b  mov     [rsp+0C8h+var_30], 0
0x18005a667  mov     ecx, 38h ; '8'; Size
0x18005a66c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18005a671  mov     r14, rax
0x18005a674  movups  xmm0, xmmword ptr [rbx+78h]
0x18005a678  movdqu  xmmword ptr [rax+20h], xmm0
0x18005a67d  mov     [rax+30h], rbx
0x18005a681  mov     rcx, [rbx]
0x18005a684  mov     rax, [rcx+8]
0x18005a688  mov     rcx, rbx
0x18005a68b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a690  nop
0x18005a691  mov     rax, [rsp+0C8h+var_48]
0x18005a699  mov     [r14], rax
0x18005a69c  mov     [r14+8], rax
0x18005a6a0  mov     [r14+10h], rax
0x18005a6a4  mov     word ptr [r14+18h], 0
0x18005a6ab  mov     rax, [rsp+0C8h+arg_18]
0x18005a6b3  mov     [rsp+0C8h+var_38], rax
0x18005a6bb  mov     dword ptr [rsp+0C8h+var_30], r12d
0x18005a6c3  mov     rax, qword ptr [rsp+0C8h+var_50]
0x18005a6c8  mov     dword ptr [rsp+0C8h+var_30+4], eax
0x18005a6cf  mov     r8, r14
0x18005a6d2  lea     rdx, [rsp+0C8h+var_38]
0x18005a6da  mov     rcx, r13
0x18005a6dd  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x18005a6e2  mov     eax, cs:dword_1800C1058
0x18005a6e8  cmp     eax, 4
0x18005a6eb  jbe     short loc_18005A75F
0x18005a6ed  lea     rax, aCreateMonitorC; "Create monitor context"
0x18005a6f4  mov     [rsp+0C8h+var_38], rax
0x18005a6fc  lea     rax, aRdpAvencYuvCyu_1; "Rdp::Avenc::Yuv::CYuvProcessor::CreateM"...
0x18005a703  mov     [rsp+0C8h+var_48], rax
0x18005a70b  mov     dword ptr [rsp+0C8h+arg_18], 9Ch
0x18005a716  mov     qword ptr [rsp+0C8h+var_50], r15
0x18005a71b  lea     rax, [rsp+0C8h+var_38]
0x18005a723  mov     [rsp+0C8h+MessageGuid], rax
0x18005a728  lea     rax, [rsp+0C8h+var_48]
0x18005a730  mov     [rsp+0C8h+var_98], rax
0x18005a735  lea     rax, [rsp+0C8h+arg_18]
0x18005a73d  mov     qword ptr [rsp+0C8h+var_A0], rax; int
0x18005a742  lea     rax, [rsp+0C8h+var_50]
0x18005a747  mov     qword ptr [rsp+0C8h+var_A8], rax; int
0x18005a74c  lea     rdx, qword_1800B3E70
0x18005a753  lea     rcx, dword_1800C1058
0x18005a75a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18005a75f  neg     rbx
0x18005a762  sbb     rax, rax
0x18005a765  and     rax, [rsp+0C8h+var_58]
0x18005a76a  mov     rcx, [rsp+0C8h+arg_8]
0x18005a772  mov     [rcx], rax
0x18005a775  mov     rax, cs:WPP_GLOBAL_Control
0x18005a77c  lea     rcx, WPP_GLOBAL_Control
0x18005a783  cmp     rax, rcx
0x18005a786  jz      short loc_18005A794
0x18005a788  test    [rax+1Ch], sil
0x18005a78c  jz      short loc_18005A794
0x18005a78e  cmp     byte ptr [rax+19h], 4
0x18005a792  jnb     short loc_18005A797
0x18005a794  xor     sil, sil
0x18005a797  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a79e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a7a5  setnz   bl
0x18005a7a8  test    sil, sil
0x18005a7ab  jnz     short loc_18005A7B1
0x18005a7ad  test    bl, bl
0x18005a7af  jz      short loc_18005A7E9
0x18005a7b1  call    cs:__imp_GetCurrentThreadId
0x18005a7b7  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18005a7bb  lea     rax, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005a7c2  mov     [rsp+0C8h+MessageGuid], rax; MessageGuid
0x18005a7c7  mov     word ptr [rsp+0C8h+var_98], 0Fh; __int16
0x18005a7ce  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a7d5  mov     r9, [rcx+28h]; int
0x18005a7d9  mov     r8b, bl; int
0x18005a7dc  mov     dl, sil; int
0x18005a7df  mov     rcx, [rcx+10h]; int
0x18005a7e3  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005a7e8  nop
0x18005a7e9  xor     eax, eax
0x18005a7eb  jmp     short loc_18005A7F4
0x18005a7ed  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x18005a7f4  mov     rbx, [rsp+0C8h+arg_0]
0x18005a7fc  add     rsp, 0A0h
0x18005a803  pop     r15
0x18005a805  pop     r14
0x18005a807  pop     r13
0x18005a809  pop     r12
0x18005a80b  pop     rsi
0x18005a80c  retn
0x18005a80d  mov     r9d, 80004003h; char *
0x18005a813  lea     r8, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005a81a  mov     edx, 8Fh; void *
0x18005a81f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18005a825  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
