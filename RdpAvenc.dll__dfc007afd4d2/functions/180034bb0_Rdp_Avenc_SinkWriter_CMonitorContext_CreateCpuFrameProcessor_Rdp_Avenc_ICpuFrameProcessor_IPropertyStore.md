# Rdp::Avenc::SinkWriter::CMonitorContext::CreateCpuFrameProcessor(Rdp::Avenc::ICpuFrameProcessor * *,IPropertyStore *)

- ea: `0x180034bb0`
- end: `0x180034e49`
- name: `?CreateCpuFrameProcessor@CMonitorContext@SinkWriter@Avenc@Rdp@@UEAAJPEAPEAUICpuFrameProcessor@34@PEAUIPropertyStore@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CMonitorContext *__hidden this, struct Rdp::Avenc::ICpuFrameProcessor **, struct IPropertyStore *)`
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x180002a0c`
- `0x1800065a4`
- `0x18000ec04`
- `0x1800146bc`
- `0x1800153f8`
- `0x1800348ec`
- `0x180034bb0`
- `0x180089010`

## string_xrefs

- `0x180034e36`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180034c07`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\monitorcontext.cpp`
- `0x180034e22`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\monitorcontext.cpp`
- `0x180034c9d`: `Create Cpu SinkWriter frame processor`
- `0x180034daa`: `CreateCpuSinkWriterFrameProcessor: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}`
- `0x180034cac`: `Rdp::Avenc::SinkWriter::CMonitorContext::CreateCpuFrameProcessor`
- `0x180034da3`: `Rdp::Avenc::SinkWriter::CMonitorContext::CreateCpuFrameProcessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::SinkWriter::CMonitorContext::CreateCpuFrameProcessor(
        Rdp::Avenc::SinkWriter::CMonitorContext *this,
        struct Rdp::Avenc::ICpuFrameProcessor **a2,
        struct IPropertyStore *a3)
{
  __int64 v5; // rax
  int v6; // r8d
  int v7; // r9d
  __int64 v8; // rbx
  const char *v9; // r9
  __int64 (__fastcall ***v10)(_QWORD, GUID *, struct Rdp::Avenc::ICpuFrameProcessor **); // rcx
  int v11; // eax
  __int64 result; // rax
  int v13; // [rsp+20h] [rbp-A8h]
  int v14; // [rsp+20h] [rbp-A8h]
  bool v15[8]; // [rsp+28h] [rbp-A0h]
  const char *v16; // [rsp+30h] [rbp-98h]
  __int64 v17; // [rsp+30h] [rbp-98h]
  __int64 v18; // [rsp+38h] [rbp-90h]
  __int64 v19; // [rsp+40h] [rbp-88h]
  __int64 v20; // [rsp+48h] [rbp-80h]
  char *v21; // [rsp+80h] [rbp-48h] BYREF
  const char *v22; // [rsp+88h] [rbp-40h] BYREF
  const char *v23; // [rsp+90h] [rbp-38h] BYREF
  const char *v24; // [rsp+98h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *v26; // [rsp+D8h] [rbp+10h] BYREF
  int v27; // [rsp+E8h] [rbp+20h] BYREF

  try
  {
    if ( !a2 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x96,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\monitorcontext.cpp",
        (const char *)0x80004003LL,
        v13);
    LOBYTE(v13) = *((_BYTE *)this + 16) == 0;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\monitorcontext.cpp",
      (const char *)0x8000FFFFLL,
      v13,
      (bool)"Monitor context is not started",
      v16);
    v26 = (Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor *)operator new(0xA0u);
    v5 = Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::CSinkWriterFrameProcessor(
           v26,
           (Rdp::Avenc::SinkWriter::CMonitorContext *)((char *)this - 80));
    v8 = *((_QWORD *)this + 17);
    *((_QWORD *)this + 17) = v5;
    if ( v5 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 8LL))(v5);
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    if ( (unsigned int)dword_1800C1058 > 4 )
    {
      v21 = (char *)this + 40;
      LODWORD(v26) = *(_DWORD *)(*((_QWORD *)this + 4) + 160LL);
      v22 = "Create Cpu SinkWriter frame processor";
      v23 = "Rdp::Avenc::SinkWriter::CMonitorContext::CreateCpuFrameProcessor";
      v27 = 157;
      v24 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\monitorcontext.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&dword_1800AEFFC,
        v6,
        v7,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v26,
        (__int64)&v21);
    }
    LODWORD(v20) = *((unsigned __int8 *)this + 49);
    LODWORD(v19) = *((unsigned __int8 *)this + 48);
    LODWORD(v18) = *((unsigned __int16 *)this + 23);
    LODWORD(v17) = *((unsigned __int16 *)this + 22);
    *(_DWORD *)v15 = *((_DWORD *)this + 10);
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"CreateCpuSinkWriterFrameProcessor: Id {%08lX-%04hX-%04hX-%02hhX%02hhX-%02hhX%02hhX%02hhX%02hhX%02hhX%02hhX}",
      "Rdp::Avenc::SinkWriter::CMonitorContext::CreateCpuFrameProcessor",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\monitorcontext.cpp",
      0xA0u,
      *(_QWORD *)v15,
      v17,
      v18,
      v19,
      v20,
      *((unsigned __int8 *)this + 50),
      *((unsigned __int8 *)this + 51),
      *((unsigned __int8 *)this + 52),
      *((unsigned __int8 *)this + 53),
      *((unsigned __int8 *)this + 54),
      *((unsigned __int8 *)this + 55));
    v10 = (__int64 (__fastcall ***)(_QWORD, GUID *, struct Rdp::Avenc::ICpuFrameProcessor **))*((_QWORD *)this + 17);
    if ( v10 )
    {
      v11 = (**v10)(v10, &GUID_743ce3e5_a291_458d_ab1b_3fc4e1445c48, a2);
      if ( v11 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v11,
          v14);
    }
    else
    {
      *a2 = 0;
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xA5,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\monitorcontext.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180034bb0  mov     [rsp+arg_0], rbx
0x180034bb5  mov     [rsp+arg_10], rsi
0x180034bba  push    rdi
0x180034bbb  push    r12
0x180034bbd  push    r13
0x180034bbf  push    r14
0x180034bc1  push    r15
0x180034bc3  sub     rsp, 0A0h
0x180034bca  mov     r13, rdx
0x180034bcd  mov     r15, rcx
0x180034bd0  mov     rcx, [rsp+0C8h]; this
0x180034bd8  test    rdx, rdx
0x180034bdb  jz      loc_180034E1C
0x180034be1  cmp     byte ptr [r15+10h], 0
0x180034be6  setz    al
0x180034be9  mov     rcx, [rsp+0C8h]; this
0x180034bf1  lea     rdx, aMonitorContext; "Monitor context is not started"
0x180034bf8  mov     qword ptr [rsp+0C8h+var_A0], rdx; bool
0x180034bfd  mov     byte ptr [rsp+0C8h+var_A8], al; int
0x180034c01  mov     r9d, 8000FFFFh; char *
0x180034c07  lea     r12, aOnecoreuapTerm_59; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180034c0e  mov     r8, r12; unsigned int
0x180034c11  mov     edx, 97h; void *
0x180034c16  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180034c1b  mov     ecx, 0A0h; Size
0x180034c20  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180034c25  mov     [rsp+0C8h+arg_8], rax
0x180034c2d  lea     rdx, [r15-50h]; struct Rdp::Avenc::SinkWriter::CMonitorContext *
0x180034c31  mov     rcx, rax; this
0x180034c34  call    ??0CSinkWriterFrameProcessor@SinkWriter@Avenc@Rdp@@QEAA@PEAVCMonitorContext@123@@Z; Rdp::Avenc::SinkWriter::CSinkWriterFrameProcessor::CSinkWriterFrameProcessor(Rdp::Avenc::SinkWriter::CMonitorContext *)
0x180034c39  nop
0x180034c3a  mov     rbx, [r15+88h]
0x180034c41  mov     [r15+88h], rax
0x180034c48  test    rax, rax
0x180034c4b  jz      short loc_180034C5C
0x180034c4d  mov     rdx, [rax]
0x180034c50  mov     rcx, rax
0x180034c53  mov     rax, [rdx+8]
0x180034c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c5c  test    rbx, rbx
0x180034c5f  jz      short loc_180034C71
0x180034c61  mov     rax, [rbx]
0x180034c64  mov     rcx, rbx
0x180034c67  mov     rax, [rax+10h]
0x180034c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034c70  nop
0x180034c71  mov     eax, cs:dword_1800C1058
0x180034c77  cmp     eax, 4
0x180034c7a  jbe     loc_180034D2F
0x180034c80  lea     rax, [r15+28h]
0x180034c84  mov     [rsp+0C8h+var_48], rax
0x180034c8c  mov     rax, [r15+20h]
0x180034c90  mov     ecx, [rax+0A0h]
0x180034c96  mov     dword ptr [rsp+0C8h+arg_8], ecx
0x180034c9d  lea     rax, aCreateCpuSinkw; "Create Cpu SinkWriter frame processor"
0x180034ca4  mov     [rsp+0C8h+var_40], rax
0x180034cac  lea     rax, aRdpAvencSinkwr_0; "Rdp::Avenc::SinkWriter::CMonitorContext"...
0x180034cb3  mov     [rsp+0C8h+var_38], rax
0x180034cbb  mov     [rsp+0C8h+arg_18], 9Dh
0x180034cc6  mov     [rsp+0C8h+var_30], r12
0x180034cce  lea     rax, [rsp+0C8h+var_48]
0x180034cd6  mov     [rsp+0C8h+var_80], rax
0x180034cdb  lea     rax, [rsp+0C8h+arg_8]
0x180034ce3  mov     [rsp+0C8h+var_88], rax
0x180034ce8  lea     rax, [rsp+0C8h+var_40]
0x180034cf0  mov     [rsp+0C8h+var_90], rax
0x180034cf5  lea     rax, [rsp+0C8h+var_38]
0x180034cfd  mov     [rsp+0C8h+var_98], rax
0x180034d02  lea     rax, [rsp+0C8h+arg_18]
0x180034d0a  mov     qword ptr [rsp+0C8h+var_A0], rax
0x180034d0f  lea     rax, [rsp+0C8h+var_30]
0x180034d17  mov     qword ptr [rsp+0C8h+var_A8], rax
0x180034d1c  lea     rdx, dword_1800AEFFC
0x180034d23  lea     rcx, dword_1800C1058
0x180034d2a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x180034d2f  lea     r8, [r15+28h]
0x180034d33  movzx   eax, byte ptr [r15+37h]
0x180034d38  movzx   ecx, byte ptr [r15+36h]
0x180034d3d  movzx   edx, byte ptr [r15+35h]
0x180034d42  movzx   r9d, byte ptr [r15+34h]
0x180034d47  movzx   r10d, byte ptr [r15+33h]
0x180034d4c  movzx   r11d, byte ptr [r15+32h]
0x180034d51  movzx   ebx, byte ptr [r15+31h]
0x180034d56  movzx   edi, byte ptr [r15+30h]
0x180034d5b  movzx   esi, word ptr [r15+2Eh]
0x180034d60  movzx   r14d, word ptr [r15+2Ch]
0x180034d65  mov     [rsp+0C8h+var_50], eax
0x180034d69  mov     [rsp+0C8h+var_58], ecx
0x180034d6d  mov     [rsp+0C8h+var_60], edx
0x180034d71  mov     [rsp+0C8h+var_68], r9d
0x180034d76  mov     [rsp+0C8h+var_70], r10d
0x180034d7b  mov     [rsp+0C8h+var_78], r11d
0x180034d80  mov     dword ptr [rsp+0C8h+var_80], ebx
0x180034d84  mov     dword ptr [rsp+0C8h+var_88], edi
0x180034d88  mov     dword ptr [rsp+0C8h+var_90], esi
0x180034d8c  mov     dword ptr [rsp+0C8h+var_98], r14d
0x180034d91  mov     eax, [r8]
0x180034d94  mov     dword ptr [rsp+0C8h+var_A0], eax
0x180034d98  mov     [rsp+0C8h+var_A8], 0A0h; int
0x180034da0  mov     r9, r12; char *
0x180034da3  lea     r8, aRdpAvencSinkwr_0; "Rdp::Avenc::SinkWriter::CMonitorContext"...
0x180034daa  lea     rdx, aCreatecpusinkw; "CreateCpuSinkWriterFrameProcessor: Id {"...
0x180034db1  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180034db8  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180034dbd  mov     rcx, [r15+88h]
0x180034dc4  test    rcx, rcx
0x180034dc7  jz      short loc_180034DEC
0x180034dc9  mov     rax, [rcx]
0x180034dcc  mov     r8, r13
0x180034dcf  lea     rdx, _GUID_743ce3e5_a291_458d_ab1b_3fc4e1445c48
0x180034dd6  mov     rax, [rax]
0x180034dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034dde  mov     rcx, [rsp+0C8h]; this
0x180034de6  test    eax, eax
0x180034de8  js      short loc_180034E33
0x180034dea  jmp     short loc_180034DF4
0x180034dec  mov     qword ptr [r13+0], 0
0x180034df4  xor     eax, eax
0x180034df6  jmp     short loc_180034DFF
0x180034df8  mov     eax, dword ptr [rsp+0C8h+arg_8]
0x180034dff  lea     r11, [rsp+0C8h+var_28]
0x180034e07  mov     rbx, [r11+30h]
0x180034e0b  mov     rsi, [r11+40h]
0x180034e0f  mov     rsp, r11
0x180034e12  pop     r15
0x180034e14  pop     r14
0x180034e16  pop     r13
0x180034e18  pop     r12
0x180034e1a  pop     rdi
0x180034e1b  retn
0x180034e1c  mov     r9d, 80004003h; char *
0x180034e22  lea     r8, aOnecoreuapTerm_59; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180034e29  mov     edx, 96h; void *
0x180034e2e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180034e33  mov     r9d, eax; char *
0x180034e36  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034e3d  mov     edx, 1CBEh; void *
0x180034e42  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
