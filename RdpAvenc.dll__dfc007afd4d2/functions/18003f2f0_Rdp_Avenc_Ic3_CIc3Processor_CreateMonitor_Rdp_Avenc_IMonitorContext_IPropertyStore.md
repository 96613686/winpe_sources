# Rdp::Avenc::Ic3::CIc3Processor::CreateMonitor(Rdp::Avenc::IMonitorContext * *,IPropertyStore *)

- ea: `0x18003f2f0`
- end: `0x18003f8e8`
- name: `?CreateMonitor@CIc3Processor@Ic3@Avenc@Rdp@@UEAAJPEAPEAUIMonitorContext@34@PEAUIPropertyStore@@@Z`
- size: `1528`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CIc3Processor *__hidden this, struct Rdp::Avenc::IMonitorContext **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

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
- `0x1800203d4`
- `0x18003f2f0`
- `0x18004170c`
- `0x1800431fc`
- `0x180082e84`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f86a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f360`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f86a`

## string_xrefs

- `0x18003f432`: `Create monitor context`
- `0x18003f6dc`: `Create monitor context`
- `0x18003f4f7`: `MonitorCreate`
- `0x18003f44a`: `DirectStreamMedia_Service`
- `0x18003f7f9`: `Unable to send create stream pdu.`
- `0x18003f4f0`: `Rdp::Avenc::Ic3::CIc3Processor::CreateMonitor`
- `0x18003f6eb`: `Rdp::Avenc::Ic3::CIc3Processor::CreateMonitor`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Rdp::Avenc::Ic3::CIc3Processor::CreateMonitor(
        Rdp::Avenc::Ic3::CIc3Processor *this,
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
  __int64 v13; // rax
  __int64 v14; // rbx
  const void *v15; // r9
  const char *v16; // r15
  const char *v17; // r14
  int v18; // r8d
  const char *v19; // r9
  __int64 v20; // r14
  _OWORD *v21; // r14
  const char *v22; // rax
  __int64 v23; // rcx
  unsigned int v24; // r8d
  const char *v25; // rdx
  unsigned int v26; // eax
  struct Rdp::Avenc::IMonitorContext *v27; // rbx
  bool v28; // bl
  char v29; // al
  int v30; // r8d
  int v31; // edx
  __int64 result; // rax
  int v33; // [rsp+20h] [rbp-B8h]
  int v34; // [rsp+20h] [rbp-B8h]
  int v35; // [rsp+28h] [rbp-B0h]
  int v36; // [rsp+28h] [rbp-B0h]
  char *v37; // [rsp+28h] [rbp-B0h]
  char *v38; // [rsp+30h] [rbp-A8h]
  const char *v39; // [rsp+60h] [rbp-78h] BYREF
  int *v40; // [rsp+68h] [rbp-70h] BYREF
  _QWORD v41[2]; // [rsp+70h] [rbp-68h] BYREF
  __int128 v42; // [rsp+80h] [rbp-58h] BYREF
  char v43[16]; // [rsp+90h] [rbp-48h] BYREF
  const char *v44; // [rsp+A0h] [rbp-38h] BYREF
  unsigned __int64 v45; // [rsp+A8h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  Rdp::Avenc::Ic3::CMonitorContext *v48; // [rsp+F8h] [rbp+20h] BYREF

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
      v33,
      v35,
      14,
      &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
      CurrentThreadId);
  }
  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x130,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)0x80004003LL,
        v33);
    LOBYTE(v33) = *((_BYTE *)this + 152) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      (const char *)0x8000FFFFLL,
      v33,
      (bool)"Processor is not started",
      v38);
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      LODWORD(v48) = *((_DWORD *)this + 14);
      v39 = "Create monitor context";
      v40 = &xmmword_1800C21A0;
      v41[0] = "DirectStreamMedia_Service";
      *(_QWORD *)&v42 = "RdpAvenc";
      *(_QWORD *)v43 = 0x1000000;
      v44 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800AFC46,
        v11,
        v12,
        (__int64)&v44,
        (__int64)v43,
        (__int64)&v42,
        (__int64)v41,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v48);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"MonitorCreate",
      "Rdp::Avenc::Ic3::CIc3Processor::CreateMonitor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      0x139u);
    v48 = (Rdp::Avenc::Ic3::CMonitorContext *)operator new(0x128u);
    v13 = Rdp::Avenc::Ic3::CMonitorContext::CMonitorContext(
            v48,
            (Rdp::Avenc::Ic3::CIc3Processor *)((char *)this - 80),
            a3,
            *((struct Rdp::Avenc::Ic3::CDsGfxChannel **)this + 20),
            *((struct IDirectStreamMediaControl **)this + 21));
    v14 = v13;
    *(_QWORD *)&v42 = v13;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
    v15 = (const void *)(v14 + 112);
    v44 = (const char *)*((_QWORD *)this + 3);
    v39 = (const char *)*((_QWORD *)v44 + 1);
    LODWORD(v48) = 0;
    *(_QWORD *)v43 = 0;
    v16 = v44;
    v17 = v39;
    if ( !v39[25] )
    {
      do
      {
        v39 = v17;
        if ( memcmp_0(v17 + 32, v15, 0x10u) >= 0 )
        {
          LODWORD(v48) = 1;
          v16 = v17;
          v17 = *(const char **)v17;
        }
        else
        {
          LODWORD(v48) = 0;
          v17 = (const char *)*((_QWORD *)v17 + 2);
        }
        v15 = (const void *)(v14 + 112);
      }
      while ( !v17[25] );
      v15 = (const void *)(v14 + 112);
    }
    if ( v16[25] || memcmp_0(v15, v16 + 32, 0x10u) < 0 )
    {
      if ( *((_QWORD *)this + 4) == 0x492492492492492LL )
        std::_Throw_tree_length_error();
      v41[0] = (char *)this + 24;
      v41[1] = 0;
      v21 = operator new(0x38u);
      v21[2] = *(_OWORD *)(v14 + 112);
      *((_QWORD *)v21 + 6) = v14;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      v22 = v44;
      *(_QWORD *)v21 = v44;
      *((_QWORD *)v21 + 1) = v22;
      *((_QWORD *)v21 + 2) = v22;
      *((_WORD *)v21 + 12) = 0;
      v44 = v39;
      v45 = __PAIR64__(*(unsigned int *)v43, (unsigned int)v48);
      std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(
        (char *)this + 24,
        &v44,
        v21);
    }
    else
    {
      v20 = *((_QWORD *)v16 + 6);
      *((_QWORD *)v16 + 6) = v14;
      if ( v14 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
    }
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v44 = "Create monitor context";
      *(_QWORD *)v43 = "Rdp::Avenc::Ic3::CIc3Processor::CreateMonitor";
      LODWORD(v48) = 322;
      *(_QWORD *)&v42 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)qword_1800AFC10,
        v18,
        (_DWORD)v19,
        (__int64)&v42,
        (__int64)&v48,
        (__int64)v43,
        (__int64)&v44);
    }
    v23 = *((_QWORD *)this + 20);
    if ( v23 )
    {
      v42 = *(_OWORD *)(v14 + 112);
      v24 = *(_DWORD *)(v14 + 144);
      *(_OWORD *)v43 = *(_OWORD *)(v14 + 176);
      if ( *(_QWORD *)(v14 + 280) <= 0xFu )
        v25 = (const char *)(v14 + 256);
      else
        v25 = *(const char **)(v14 + 256);
      v44 = v25;
      v45 = *(_QWORD *)(v14 + 272);
      v26 = Rdp::Avenc::Ic3::CDsGfxChannel::SendCreateStreamPdu(
              v23,
              &v42,
              *(_DWORD *)(v14 + 128),
              *(_DWORD *)(v14 + 140),
              v24,
              (unsigned int *)v43,
              (__int64)&v44);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0x14D,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)v26,
        (int)"Unable to send create stream pdu.",
        v37);
    }
    if ( v14 )
      v27 = (struct Rdp::Avenc::IMonitorContext *)(v14 + 80);
    else
      v27 = 0;
    *a2 = v27;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v5 = 0;
    }
    v28 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v29 = GetCurrentThreadId();
      LOBYTE(v30) = v28;
      LOBYTE(v31) = v5;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v31,
        v30,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v34,
        v36,
        15,
        &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
        v29);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x155,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
                           v19);
  }
  return result;
}

```

## disassembly

```asm
0x18003f2f0  mov     [rsp+arg_0], rbx
0x18003f2f5  mov     [rsp+arg_10], rsi
0x18003f2fa  mov     [rsp+arg_8], rdx
0x18003f2ff  push    rdi
0x18003f300  push    r12
0x18003f302  push    r13
0x18003f304  push    r14
0x18003f306  push    r15
0x18003f308  sub     rsp, 0B0h
0x18003f30f  mov     r15, r8
0x18003f312  mov     r13, rcx
0x18003f315  lea     rcx, WPP_GLOBAL_Control
0x18003f31c  mov     rax, cs:WPP_GLOBAL_Control
0x18003f323  mov     esi, 1
0x18003f328  cmp     rax, rcx
0x18003f32b  jz      short loc_18003F340
0x18003f32d  test    [rax+1Ch], sil
0x18003f331  jz      short loc_18003F340
0x18003f333  cmp     byte ptr [rax+19h], 4
0x18003f337  jb      short loc_18003F340
0x18003f339  mov     bl, sil
0x18003f33c  xor     edi, edi
0x18003f33e  jmp     short loc_18003F345
0x18003f340  xor     edi, edi
0x18003f342  mov     bl, dil
0x18003f345  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f34c  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f353  setnz   r14b
0x18003f357  test    bl, bl
0x18003f359  jnz     short loc_18003F360
0x18003f35b  test    r14b, r14b
0x18003f35e  jz      short loc_18003F396
0x18003f360  call    cs:__imp_GetCurrentThreadId
0x18003f366  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18003f36a  lea     r12, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x18003f371  mov     [rsp+0D8h+MessageGuid], r12; MessageGuid
0x18003f376  mov     word ptr [rsp+0D8h+var_A8], 0Eh; char *
0x18003f37d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f384  mov     r9, [rcx+28h]; int
0x18003f388  mov     r8b, r14b; int
0x18003f38b  mov     dl, bl; int
0x18003f38d  mov     rcx, [rcx+10h]; int
0x18003f391  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003f396  mov     rcx, [rsp+0D8h]; this
0x18003f39e  cmp     [rsp+0D8h+arg_8], rdi
0x18003f3a6  jz      loc_18003F8C9
0x18003f3ac  cmp     [r13+98h], dil
0x18003f3b3  setz    al
0x18003f3b6  mov     rcx, [rsp+0D8h]; this
0x18003f3be  lea     rdx, aProcessorIsNot; "Processor is not started"
0x18003f3c5  mov     [rsp+0D8h+var_B0], rdx; bool
0x18003f3ca  mov     byte ptr [rsp+0D8h+var_B8], al; int
0x18003f3ce  mov     r9d, 8000FFFFh; char *
0x18003f3d4  lea     r12, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003f3db  mov     r8, r12; unsigned int
0x18003f3de  mov     edx, 131h; void *
0x18003f3e3  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18003f3e8  mov     eax, cs:dword_1800C1058
0x18003f3ee  cmp     eax, 4
0x18003f3f1  jbe     loc_18003F4E5
0x18003f3f7  mov     rcx, cs:qword_1800C1070
0x18003f3fe  mov     rax, cs:qword_1800C1068
0x18003f405  mov     rdx, 470000000000h
0x18003f40f  test    rdx, rax
0x18003f412  jz      loc_18003F4E5
0x18003f418  mov     rax, rcx
0x18003f41b  and     rax, rdx
0x18003f41e  cmp     rax, rcx
0x18003f421  jnz     loc_18003F4E5
0x18003f427  mov     eax, [r13+38h]
0x18003f42b  mov     dword ptr [rsp+0D8h+arg_18], eax
0x18003f432  lea     rbx, aCreateMonitorC; "Create monitor context"
0x18003f439  mov     [rsp+0D8h+var_78], rbx
0x18003f43e  lea     rax, xmmword_1800C21A0
0x18003f445  mov     [rsp+0D8h+var_70], rax
0x18003f44a  lea     rax, aDirectstreamme; "DirectStreamMedia_Service"
0x18003f451  mov     [rsp+0D8h+var_68], rax
0x18003f456  lea     rax, aRdpavenc; "RdpAvenc"
0x18003f45d  mov     qword ptr [rsp+0D8h+var_58], rax
0x18003f465  mov     qword ptr [rsp+0D8h+var_48], 1000000h
0x18003f471  lea     rax, aCheckpoint; "Checkpoint"
0x18003f478  mov     [rsp+0D8h+var_38], rax
0x18003f480  lea     rax, [rsp+0D8h+arg_18]
0x18003f488  mov     [rsp+0D8h+var_88], rax
0x18003f48d  lea     rax, [rsp+0D8h+var_78]
0x18003f492  mov     [rsp+0D8h+var_90], rax
0x18003f497  lea     rax, [rsp+0D8h+var_70]
0x18003f49c  mov     qword ptr [rsp+0D8h+var_98], rax
0x18003f4a1  lea     rax, [rsp+0D8h+var_68]
0x18003f4a6  mov     [rsp+0D8h+MessageGuid], rax
0x18003f4ab  lea     rax, [rsp+0D8h+var_58]
0x18003f4b3  mov     [rsp+0D8h+var_A8], rax
0x18003f4b8  lea     rax, [rsp+0D8h+var_48]
0x18003f4c0  mov     [rsp+0D8h+var_B0], rax
0x18003f4c5  lea     rax, [rsp+0D8h+var_38]
0x18003f4cd  mov     [rsp+0D8h+var_B8], rax
0x18003f4d2  lea     rdx, word_1800AFC46
0x18003f4d9  lea     rcx, dword_1800C1058
0x18003f4e0  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003f4e5  mov     dword ptr [rsp+0D8h+var_B8], 139h; unsigned int
0x18003f4ed  mov     r9, r12; char *
0x18003f4f0  lea     r8, aRdpAvencIc3Cic_9; "Rdp::Avenc::Ic3::CIc3Processor::CreateM"...
0x18003f4f7  lea     rdx, aMonitorcreate; "MonitorCreate"
0x18003f4fe  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003f505  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18003f50a  mov     ecx, 128h; Size
0x18003f50f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f514  mov     [rsp+0D8h+arg_18], rax
0x18003f51c  lea     rdx, [r13-50h]; struct Rdp::Avenc::Ic3::CIc3Processor *
0x18003f520  mov     rcx, [r13+0A8h]
0x18003f527  mov     [rsp+0D8h+var_B8], rcx; struct IDirectStreamMediaControl *
0x18003f52c  mov     r9, [r13+0A0h]; struct Rdp::Avenc::Ic3::CDsGfxChannel *
0x18003f533  mov     r8, r15; struct IPropertyStore *
0x18003f536  mov     rcx, rax; this
0x18003f539  call    ??0CMonitorContext@Ic3@Avenc@Rdp@@QEAA@PEAVCIc3Processor@123@PEAUIPropertyStore@@PEAVCDsGfxChannel@123@PEAUIDirectStreamMediaControl@@@Z; Rdp::Avenc::Ic3::CMonitorContext::CMonitorContext(Rdp::Avenc::Ic3::CIc3Processor *,IPropertyStore *,Rdp::Avenc::Ic3::CDsGfxChannel *,IDirectStreamMediaControl *)
0x18003f53e  mov     rbx, rax
0x18003f541  mov     qword ptr [rsp+0D8h+var_58], rax
0x18003f549  test    rax, rax
0x18003f54c  jz      short loc_18003F55E
0x18003f54e  mov     rax, [rax]
0x18003f551  mov     rcx, rbx
0x18003f554  mov     rax, [rax+8]
0x18003f558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f55d  nop
0x18003f55e  lea     r9, [rbx+70h]
0x18003f562  mov     rax, [r13+18h]
0x18003f566  mov     [rsp+0D8h+var_38], rax
0x18003f56e  mov     rcx, [rax+8]
0x18003f572  mov     [rsp+0D8h+var_78], rcx
0x18003f577  mov     dword ptr [rsp+0D8h+arg_18], edi
0x18003f57e  xor     edx, edx
0x18003f580  mov     qword ptr [rsp+0D8h+var_48], rdx
0x18003f588  mov     r15, rax
0x18003f58b  mov     r14, rcx
0x18003f58e  cmp     [rcx+19h], dil
0x18003f592  jnz     short loc_18003F5D7
0x18003f594  mov     [rsp+0D8h+var_78], r14
0x18003f599  lea     rcx, [r14+20h]; Buf1
0x18003f59d  mov     r8d, 10h; Size
0x18003f5a3  mov     rdx, r9; Buf2
0x18003f5a6  call    memcmp_0
0x18003f5ab  test    eax, eax
0x18003f5ad  jns     short loc_18003F5BC
0x18003f5af  mov     dword ptr [rsp+0D8h+arg_18], edi
0x18003f5b6  mov     r14, [r14+10h]
0x18003f5ba  jmp     short loc_18003F5C9
0x18003f5bc  mov     dword ptr [rsp+0D8h+arg_18], esi
0x18003f5c3  mov     r15, r14
0x18003f5c6  mov     r14, [r14]
0x18003f5c9  cmp     [r14+19h], dil
0x18003f5cd  lea     r9, [rbx+70h]
0x18003f5d1  jz      short loc_18003F594
0x18003f5d3  lea     r9, [rbx+70h]
0x18003f5d7  cmp     [r15+19h], dil
0x18003f5db  jnz     short loc_18003F629
0x18003f5dd  lea     rdx, [r15+20h]; Buf2
0x18003f5e1  mov     r8d, 10h; Size
0x18003f5e7  mov     rcx, r9; Buf1
0x18003f5ea  call    memcmp_0
0x18003f5ef  test    eax, eax
0x18003f5f1  js      short loc_18003F629
0x18003f5f3  mov     r14, [r15+30h]
0x18003f5f7  mov     [r15+30h], rbx
0x18003f5fb  test    rbx, rbx
0x18003f5fe  jz      short loc_18003F60F
0x18003f600  mov     rax, [rbx]
0x18003f603  mov     rcx, rbx
0x18003f606  mov     rax, [rax+8]
0x18003f60a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f60f  test    r14, r14
0x18003f612  jz      short loc_18003F624
0x18003f614  mov     rax, [r14]
0x18003f617  mov     rcx, r14
0x18003f61a  mov     rax, [rax+10h]
0x18003f61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f623  nop
0x18003f624  jmp     loc_18003F6D1
0x18003f629  mov     rax, 492492492492492h
0x18003f633  lea     r15, [r13+18h]
0x18003f637  cmp     [r15+8], rax
0x18003f63b  jz      loc_18003F8E1
0x18003f641  mov     [rsp+0D8h+var_68], r15
0x18003f646  mov     [rsp+0D8h+var_60], rdi
0x18003f64b  mov     ecx, 38h ; '8'; Size
0x18003f650  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f655  mov     r14, rax
0x18003f658  movups  xmm0, xmmword ptr [rbx+70h]
0x18003f65c  movdqu  xmmword ptr [rax+20h], xmm0
0x18003f661  mov     [rax+30h], rbx
0x18003f665  test    rbx, rbx
0x18003f668  jz      short loc_18003F67A
0x18003f66a  mov     rcx, [rbx]
0x18003f66d  mov     rax, [rcx+8]
0x18003f671  mov     rcx, rbx
0x18003f674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f679  nop
0x18003f67a  mov     rax, [rsp+0D8h+var_38]
0x18003f682  mov     [r14], rax
0x18003f685  mov     [r14+8], rax
0x18003f689  mov     [r14+10h], rax
0x18003f68d  mov     word ptr [r14+18h], 0
0x18003f694  mov     rax, [rsp+0D8h+var_78]
0x18003f699  mov     [rsp+0D8h+var_38], rax
0x18003f6a1  mov     eax, dword ptr [rsp+0D8h+arg_18]
0x18003f6a8  mov     dword ptr [rsp+0D8h+var_30], eax
0x18003f6af  mov     rax, qword ptr [rsp+0D8h+var_48]
0x18003f6b7  mov     dword ptr [rsp+0D8h+var_30+4], eax
0x18003f6be  mov     r8, r14
0x18003f6c1  lea     rdx, [rsp+0D8h+var_38]
0x18003f6c9  mov     rcx, r15
0x18003f6cc  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@VCYuvMonitorContext@Yuv@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> *>,std::_Tree_node<std::pair<_GUID const,wil::com_ptr_t<Rdp::Avenc::Yuv::CYuvMonitorContext,wil::err_exception_policy>>,void *> * const)
0x18003f6d1  mov     eax, cs:dword_1800C1058
0x18003f6d7  cmp     eax, 4
0x18003f6da  jbe     short loc_18003F754
0x18003f6dc  lea     rax, aCreateMonitorC; "Create monitor context"
0x18003f6e3  mov     [rsp+0D8h+var_38], rax
0x18003f6eb  lea     rax, aRdpAvencIc3Cic_9; "Rdp::Avenc::Ic3::CIc3Processor::CreateM"...
0x18003f6f2  mov     qword ptr [rsp+0D8h+var_48], rax
0x18003f6fa  mov     dword ptr [rsp+0D8h+arg_18], 142h
0x18003f705  mov     qword ptr [rsp+0D8h+var_58], r12
0x18003f70d  lea     rax, [rsp+0D8h+var_38]
0x18003f715  mov     [rsp+0D8h+MessageGuid], rax
0x18003f71a  lea     rax, [rsp+0D8h+var_48]
0x18003f722  mov     [rsp+0D8h+var_A8], rax
0x18003f727  lea     rax, [rsp+0D8h+arg_18]
0x18003f72f  mov     [rsp+0D8h+var_B0], rax
0x18003f734  lea     rax, [rsp+0D8h+var_58]
0x18003f73c  mov     [rsp+0D8h+var_B8], rax
0x18003f741  lea     rdx, qword_1800AFC10
0x18003f748  lea     rcx, dword_1800C1058
0x18003f74f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003f754  mov     rcx, [r13+0A0h]
0x18003f75b  mov     r14d, 0Fh
0x18003f761  test    rcx, rcx
0x18003f764  jz      loc_18003F815
0x18003f76a  movups  xmm0, xmmword ptr [rbx+70h]
0x18003f76e  movdqu  [rsp+0D8h+var_58], xmm0
0x18003f777  mov     r8d, [rbx+90h]
0x18003f77e  movups  xmm0, xmmword ptr [rbx+0B0h]
0x18003f785  movdqu  xmmword ptr [rsp+0D8h+var_48], xmm0
0x18003f78e  lea     rax, [rbx+100h]
0x18003f795  cmp     [rax+18h], r14
0x18003f799  jbe     short loc_18003F7A0
0x18003f79b  mov     rdx, [rax]
0x18003f79e  jmp     short loc_18003F7A3
0x18003f7a0  mov     rdx, rax
0x18003f7a3  mov     [rsp+0D8h+var_38], rdx
0x18003f7ab  mov     rax, [rax+10h]
0x18003f7af  mov     [rsp+0D8h+var_30], rax
0x18003f7b7  lea     rax, [rsp+0D8h+var_38]
0x18003f7bf  mov     [rsp+0D8h+var_A8], rax
0x18003f7c4  lea     rax, [rsp+0D8h+var_48]
0x18003f7cc  mov     [rsp+0D8h+var_B0], rax; int
0x18003f7d1  mov     dword ptr [rsp+0D8h+var_B8], r8d
0x18003f7d6  mov     r9d, [rbx+8Ch]
0x18003f7dd  mov     r8d, [rbx+80h]
0x18003f7e4  lea     rdx, [rsp+0D8h+var_58]
0x18003f7ec  call    ?SendCreateStreamPdu@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJAEBU_GUID@@IIIAEBUtagRECT@@V?$basic_string_view@DU?$char_traits@D@std@@@std@@@Z; Rdp::Avenc::Ic3::CDsGfxChannel::SendCreateStreamPdu(_GUID const &,uint,uint,uint,tagRECT const &,std::string_view)
0x18003f7f1  mov     rcx, [rsp+0D8h]; this
0x18003f7f9  lea     rdx, aUnableToSendCr; "Unable to send create stream pdu."
0x18003f800  mov     [rsp+0D8h+var_B8], rdx; int
0x18003f805  mov     r9d, eax; char *
0x18003f808  mov     r8, r12; unsigned int
0x18003f80b  mov     edx, 14Dh; void *
0x18003f810  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003f815  test    rbx, rbx
0x18003f818  jz      short loc_18003F820
0x18003f81a  add     rbx, 50h ; 'P'
0x18003f81e  jmp     short loc_18003F823
0x18003f820  mov     rbx, rdi
0x18003f823  mov     rax, [rsp+0D8h+arg_8]
0x18003f82b  mov     [rax], rbx
0x18003f82e  mov     rax, cs:WPP_GLOBAL_Control
0x18003f835  lea     rcx, WPP_GLOBAL_Control
0x18003f83c  cmp     rax, rcx
0x18003f83f  jz      short loc_18003F84D
0x18003f841  test    [rax+1Ch], sil
0x18003f845  jz      short loc_18003F84D
0x18003f847  cmp     byte ptr [rax+19h], 4
0x18003f84b  jnb     short loc_18003F850
0x18003f84d  mov     sil, dil
0x18003f850  lea     rax, WPP_RECORDER_INITIALIZED
0x18003f857  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003f85e  setnz   bl
0x18003f861  test    sil, sil
0x18003f864  jnz     short loc_18003F86A
0x18003f866  test    bl, bl
0x18003f868  jz      short loc_18003F8A1
0x18003f86a  call    cs:__imp_GetCurrentThreadId
0x18003f870  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x18003f874  lea     rax, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x18003f87b  mov     [rsp+0D8h+MessageGuid], rax; MessageGuid
0x18003f880  mov     word ptr [rsp+0D8h+var_A8], r14w; __int16
0x18003f886  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f88d  mov     r9, [rcx+28h]; int
0x18003f891  mov     r8b, bl; int
0x18003f894  mov     dl, sil; int
0x18003f897  mov     rcx, [rcx+10h]; int
0x18003f89b  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003f8a0  nop
  ... truncated ...
```
