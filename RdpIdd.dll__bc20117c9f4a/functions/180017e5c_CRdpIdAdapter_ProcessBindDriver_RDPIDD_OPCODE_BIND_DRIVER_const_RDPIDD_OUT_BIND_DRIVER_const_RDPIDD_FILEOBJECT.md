# CRdpIdAdapter::ProcessBindDriver(_RDPIDD_OPCODE_BIND_DRIVER * const,_RDPIDD_OUT_BIND_DRIVER * const,RDPIDD_FILEOBJECT_CONTEXT *)

- ea: `0x180017e5c`
- end: `0x180018186`
- name: `?ProcessBindDriver@CRdpIdAdapter@@AEAAXQEAU_RDPIDD_OPCODE_BIND_DRIVER@@QEAU_RDPIDD_OUT_BIND_DRIVER@@PEAURDPIDD_FILEOBJECT_CONTEXT@@@Z`
- size: `810`
- prototype: `void __fastcall(CRdpIdAdapter *__hidden this, struct _RDPIDD_OPCODE_BIND_DRIVER *const, struct _RDPIDD_OUT_BIND_DRIVER *const, struct RDPIDD_FILEOBJECT_CONTEXT *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800185bc`

## callees

- `0x180001af0`
- `0x18000402c`
- `0x18000d614`
- `0x180017e5c`
- `0x18001dd70`
- `0x18002142c`

## string_xrefs

- `0x180017e74`: `Driver has already been binded`

## pseudocode

```c
void __fastcall CRdpIdAdapter::ProcessBindDriver(
        CRdpIdAdapter *this,
        struct _RDPIDD_OPCODE_BIND_DRIVER *const a2,
        struct _RDPIDD_OUT_BIND_DRIVER *const a3,
        struct RDPIDD_FILEOBJECT_CONTEXT *a4)
{
  int v8; // ecx
  _DWORD *v9; // r8
  int v10; // r8d
  int v11; // r9d
  _DWORD *v12; // r8
  int v13; // r8d
  int v14; // r9d
  _DWORD *v15; // r8
  int v16; // r8d
  int v17; // r9d
  const char *v18; // [rsp+30h] [rbp-30h]
  __int64 v19; // [rsp+50h] [rbp-10h] BYREF
  __int64 v20; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  int v22; // [rsp+90h] [rbp+30h] BYREF
  __int64 v23; // [rsp+98h] [rbp+38h] BYREF
  GUID *v24; // [rsp+A0h] [rbp+40h] BYREF
  const char *v25; // [rsp+A8h] [rbp+48h] BYREF

  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0xB4C,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
    (const char *)0x80070057LL,
    *((_BYTE *)this + 448) == 1,
    (bool)"Driver has already been binded",
    v18);
  *((_DWORD *)this + 110) = *((_DWORD *)a2 + 3);
  v8 = *((_DWORD *)a2 + 4);
  *((_DWORD *)this + 111) = v8;
  *((_DWORD *)this + 135) = *((_DWORD *)a4 + 10);
  *((_BYTE *)this + 448) = 1;
  if ( (v8 & 2) != 0 )
    *((_BYTE *)this + 593) = 0;
  switch ( *((_DWORD *)this + 110) )
  {
    case 1:
      v15 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v15 > 4u && (unsigned __int8)tlgKeywordOn(v15, 0x470000000000LL) )
      {
        v23 = *((_QWORD *)this + 65);
        v22 = *((_DWORD *)this + 129);
        v24 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v25 = "RdpIdd";
        v19 = (__int64)"Checkpoint";
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v16,
          (unsigned int)&byte_18004C74F,
          v16,
          v17,
          (__int64)&v19,
          (__int64)&v20,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v23);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"DesktopModeEnabled",
        "CRdpIdAdapter::ProcessBindDriver",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0xB75u);
      break;
    case 2:
      v12 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v12 > 4u && (unsigned __int8)tlgKeywordOn(v12, 0x470000000000LL) )
      {
        v23 = *((_QWORD *)this + 65);
        v22 = *((_DWORD *)this + 129);
        v24 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v25 = "RdpIdd";
        v19 = (__int64)"Checkpoint";
        v20 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v13,
          (unsigned int)word_18004C7BA,
          v13,
          v14,
          (__int64)&v19,
          (__int64)&v20,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v23);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"RailModeEnabled",
        "CRdpIdAdapter::ProcessBindDriver",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0xB6Cu);
      break;
    case 3:
      v9 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
      if ( *v9 > 4u && (unsigned __int8)tlgKeywordOn(v9, 0x470000000000LL) )
      {
        v23 = *((_QWORD *)this + 65);
        v22 = *((_DWORD *)this + 129);
        v24 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
        v25 = "RdpIdd";
        v20 = (__int64)"Checkpoint";
        v19 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
          v10,
          (unsigned int)word_18004C822,
          v10,
          v11,
          (__int64)&v20,
          (__int64)&v19,
          (__int64)&v25,
          (__int64)&v24,
          (__int64)&v22,
          (__int64)&v23);
      }
      Rdp::Modern::Utils::CInflightRecorder::push0(
        (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
        L"VailvGpuModeEnabled",
        "CRdpIdAdapter::ProcessBindDriver",
        "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\adapter.cpp",
        0xB63u);
      break;
  }
  *(_DWORD *)a3 = 12;
  *((_DWORD *)a3 + 1) = *((_DWORD *)this + 86);
  *((_DWORD *)a3 + 2) = *((_DWORD *)this + 87);
}

```

## disassembly

```asm
0x180017e5c  push    rbp
0x180017e5e  push    rbx
0x180017e5f  push    rsi
0x180017e60  push    rdi
0x180017e61  push    r14
0x180017e63  mov     rbp, rsp
0x180017e66  sub     rsp, 60h
0x180017e6a  cmp     byte ptr [rcx+1C0h], 1
0x180017e71  mov     rbx, rdx
0x180017e74  lea     rdx, aDriverHasAlrea_0; "Driver has already been binded"
0x180017e7b  mov     rdi, r9
0x180017e7e  mov     qword ptr [rsp+60h+var_38], rdx; bool
0x180017e83  setz    al
0x180017e86  mov     r14, r8
0x180017e89  mov     [rsp+60h+var_40], al; char
0x180017e8d  mov     rsi, rcx
0x180017e90  lea     r8, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180017e97  mov     rcx, [rbp+28h]; this
0x180017e9b  mov     edx, 0B4Ch; void *
0x180017ea0  mov     r9d, 80070057h; char *
0x180017ea6  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180017eab  mov     eax, [rbx+0Ch]
0x180017eae  mov     [rsi+1B8h], eax
0x180017eb4  mov     ecx, [rbx+10h]
0x180017eb7  mov     [rsi+1BCh], ecx
0x180017ebd  mov     eax, [rdi+28h]
0x180017ec0  mov     [rsi+21Ch], eax
0x180017ec6  mov     byte ptr [rsi+1C0h], 1
0x180017ecd  test    cl, 2
0x180017ed0  jz      short loc_180017EDA
0x180017ed2  xor     eax, eax
0x180017ed4  xchg    al, [rsi+251h]
0x180017eda  mov     ecx, [rsi+1B8h]
0x180017ee0  sub     ecx, 1
0x180017ee3  jz      loc_180018085
0x180017ee9  sub     ecx, 1
0x180017eec  jz      loc_180017FC0
0x180017ef2  cmp     ecx, 1
0x180017ef5  jnz     loc_18001815F
0x180017efb  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180017f00  mov     r8, [rax+8]
0x180017f04  mov     eax, [r8]
0x180017f07  cmp     eax, 4
0x180017f0a  jbe     loc_180017FAC
0x180017f10  mov     rdx, 470000000000h
0x180017f1a  mov     rcx, r8
0x180017f1d  call    _tlgKeywordOn
0x180017f22  test    al, al
0x180017f24  jz      loc_180017FAC
0x180017f2a  mov     rax, [rsi+208h]
0x180017f31  lea     rdx, word_18004C822
0x180017f38  mov     [rbp+arg_8], rax
0x180017f3c  mov     rcx, r8
0x180017f3f  mov     eax, [rsi+204h]
0x180017f45  mov     [rbp+arg_0], eax
0x180017f48  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180017f4f  mov     [rbp+arg_10], rax
0x180017f53  lea     rax, aRdpidd; "RdpIdd"
0x180017f5a  mov     [rbp+arg_18], rax
0x180017f5e  lea     rax, aCheckpoint; "Checkpoint"
0x180017f65  mov     [rbp+var_8], rax
0x180017f69  lea     rax, [rbp+arg_8]
0x180017f6d  mov     [rsp+60h+var_18], rax
0x180017f72  lea     rax, [rbp+arg_0]
0x180017f76  mov     [rsp+60h+var_20], rax
0x180017f7b  lea     rax, [rbp+arg_10]
0x180017f7f  mov     [rsp+60h+var_28], rax
0x180017f84  lea     rax, [rbp+arg_18]
0x180017f88  mov     [rsp+60h+var_30], rax
0x180017f8d  lea     rax, [rbp+var_10]
0x180017f91  mov     qword ptr [rsp+60h+var_38], rax
0x180017f96  lea     rax, [rbp+var_8]
0x180017f9a  mov     qword ptr [rsp+60h+var_40], rax
0x180017f9f  mov     [rbp+var_10], 1000000h
0x180017fa7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180017fac  mov     dword ptr [rsp+60h+var_40], 0B63h
0x180017fb4  lea     rdx, aVailvgpumodeen; "VailvGpuModeEnabled"
0x180017fbb  jmp     loc_180018145
0x180017fc0  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180017fc5  mov     r8, [rax+8]
0x180017fc9  mov     eax, [r8]
0x180017fcc  cmp     eax, 4
0x180017fcf  jbe     loc_180018071
0x180017fd5  mov     rdx, 470000000000h
0x180017fdf  mov     rcx, r8
0x180017fe2  call    _tlgKeywordOn
0x180017fe7  test    al, al
0x180017fe9  jz      loc_180018071
0x180017fef  mov     rax, [rsi+208h]
0x180017ff6  lea     rdx, word_18004C7BA
0x180017ffd  mov     [rbp+arg_8], rax
0x180018001  mov     rcx, r8
0x180018004  mov     eax, [rsi+204h]
0x18001800a  mov     [rbp+arg_0], eax
0x18001800d  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x180018014  mov     [rbp+arg_10], rax
0x180018018  lea     rax, aRdpidd; "RdpIdd"
0x18001801f  mov     [rbp+arg_18], rax
0x180018023  lea     rax, aCheckpoint; "Checkpoint"
0x18001802a  mov     [rbp+var_10], rax
0x18001802e  lea     rax, [rbp+arg_8]
0x180018032  mov     [rsp+60h+var_18], rax
0x180018037  lea     rax, [rbp+arg_0]
0x18001803b  mov     [rsp+60h+var_20], rax
0x180018040  lea     rax, [rbp+arg_10]
0x180018044  mov     [rsp+60h+var_28], rax
0x180018049  lea     rax, [rbp+arg_18]
0x18001804d  mov     [rsp+60h+var_30], rax
0x180018052  lea     rax, [rbp+var_8]
0x180018056  mov     qword ptr [rsp+60h+var_38], rax
0x18001805b  lea     rax, [rbp+var_10]
0x18001805f  mov     qword ptr [rsp+60h+var_40], rax
0x180018064  mov     [rbp+var_8], 1000000h
0x18001806c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180018071  mov     dword ptr [rsp+60h+var_40], 0B6Ch
0x180018079  lea     rdx, aRailmodeenable; "RailModeEnabled"
0x180018080  jmp     loc_180018145
0x180018085  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18001808a  mov     r8, [rax+8]
0x18001808e  mov     eax, [r8]
0x180018091  cmp     eax, 4
0x180018094  jbe     loc_180018136
0x18001809a  mov     rdx, 470000000000h
0x1800180a4  mov     rcx, r8
0x1800180a7  call    _tlgKeywordOn
0x1800180ac  test    al, al
0x1800180ae  jz      loc_180018136
0x1800180b4  mov     rax, [rsi+208h]
0x1800180bb  lea     rdx, byte_18004C74F
0x1800180c2  mov     [rbp+arg_8], rax
0x1800180c6  mov     rcx, r8
0x1800180c9  mov     eax, [rsi+204h]
0x1800180cf  mov     [rbp+arg_0], eax
0x1800180d2  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800180d9  mov     [rbp+arg_10], rax
0x1800180dd  lea     rax, aRdpidd; "RdpIdd"
0x1800180e4  mov     [rbp+arg_18], rax
0x1800180e8  lea     rax, aCheckpoint; "Checkpoint"
0x1800180ef  mov     [rbp+var_10], rax
0x1800180f3  lea     rax, [rbp+arg_8]
0x1800180f7  mov     [rsp+60h+var_18], rax
0x1800180fc  lea     rax, [rbp+arg_0]
0x180018100  mov     [rsp+60h+var_20], rax
0x180018105  lea     rax, [rbp+arg_10]
0x180018109  mov     [rsp+60h+var_28], rax
0x18001810e  lea     rax, [rbp+arg_18]
0x180018112  mov     [rsp+60h+var_30], rax
0x180018117  lea     rax, [rbp+var_8]
0x18001811b  mov     qword ptr [rsp+60h+var_38], rax
0x180018120  lea     rax, [rbp+var_10]
0x180018124  mov     qword ptr [rsp+60h+var_40], rax
0x180018129  mov     [rbp+var_8], 1000000h
0x180018131  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180018136  mov     dword ptr [rsp+60h+var_40], 0B75h; unsigned int
0x18001813e  lea     rdx, aDesktopmodeena; "DesktopModeEnabled"
0x180018145  lea     r9, aOnecoreuapTerm_15; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18001814c  lea     r8, aCrdpidadapterP_0; "CRdpIdAdapter::ProcessBindDriver"
0x180018153  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18001815a  call    ?push0@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1I@Z; Rdp::Modern::Utils::CInflightRecorder::push0(ushort const *,char const *,char const *,uint)
0x18001815f  mov     dword ptr [r14], 0Ch
0x180018166  mov     eax, [rsi+158h]
0x18001816c  mov     [r14+4], eax
0x180018170  mov     eax, [rsi+15Ch]
0x180018176  mov     [r14+8], eax
0x18001817a  add     rsp, 60h
0x18001817e  pop     r14
0x180018180  pop     rdi
0x180018181  pop     rsi
0x180018182  pop     rbx
0x180018183  pop     rbp
0x180018184  retn
```
