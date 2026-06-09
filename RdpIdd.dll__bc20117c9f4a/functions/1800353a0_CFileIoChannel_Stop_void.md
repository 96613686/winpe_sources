# CFileIoChannel::Stop(void)

- ea: `0x1800353a0`
- end: `0x180035648`
- name: `?Stop@CFileIoChannel@@UEAAJXZ`
- size: `680`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001af0`
- `0x180005f8c`
- `0x18000d614`
- `0x18000d6d8`
- `0x18000dbd8`
- `0x18001dd70`
- `0x180021570`
- `0x180021750`
- `0x1800335b4`
- `0x1800353a0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18003561d`
- `msvcp_win!_Mtx_unlock` at `0x18003561d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800355e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800355e4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileIoChannel::Stop(CFileIoChannel *this)
{
  char v2; // bl
  bool v3; // si
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  struct _Mtx_internal_imp_t *v8; // rsi
  _DWORD *v9; // r8
  int v10; // r8d
  int v11; // r9d
  bool v12; // di
  char v13; // al
  int v14; // r8d
  int v15; // edx
  const char *v16; // r9
  __int64 result; // rax
  int v18; // [rsp+20h] [rbp-98h]
  int v19; // [rsp+20h] [rbp-98h]
  int v20; // [rsp+28h] [rbp-90h]
  int v21; // [rsp+28h] [rbp-90h]
  char *v22; // [rsp+30h] [rbp-88h]
  const char *v23; // [rsp+60h] [rbp-58h] BYREF
  int v24[2]; // [rsp+68h] [rbp-50h] BYREF
  _QWORD v25[9]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  int v27; // [rsp+C0h] [rbp+8h] BYREF
  char *v28; // [rsp+C8h] [rbp+10h] BYREF
  const char *v29; // [rsp+D0h] [rbp+18h] BYREF
  GUID *v30; // [rsp+D8h] [rbp+20h] BYREF

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
      v18,
      v20,
      14,
      &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
      CurrentThreadId);
  }
  CFileIoChannel::Flush(this);
  v8 = (CFileIoChannel *)((char *)this + 32);
  v25[1] = (char *)this + 32;
  try
  {
    std::_Mutex_base::lock((CFileIoChannel *)((char *)this + 32));
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x14B,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      (const char *)0x8000FFFFLL,
      *((_BYTE *)this + 432) == 0,
      (bool)"Channel is not started",
      v22);
    v9 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v9 > 4u && (unsigned __int8)tlgKeywordOn(v9, 0x470000000000LL) )
    {
      v27 = *((_DWORD *)this + 103);
      v28 = (char *)this + 380;
      v29 = "Stop FileIo channel";
      v30 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v23 = "RdpIdd";
      *(_QWORD *)v24 = 0x1000000;
      v25[0] = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v10,
        (unsigned int)word_18005026A,
        v10,
        v11,
        (__int64)v25,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"FileIoChannelStop",
      "CFileIoChannel::Stop",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      0x156u);
    wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset((char *)this + 424);
    *((_BYTE *)this + 432) = 0;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v12 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v13 = GetCurrentThreadId();
      LOBYTE(v14) = v12;
      LOBYTE(v15) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v15,
        v14,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v19,
        v21,
        15,
        &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
        v13);
    }
    _Mtx_unlock(v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x15E,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x1800353a0  push    rbx
0x1800353a2  push    rsi
0x1800353a3  push    rdi
0x1800353a4  push    r12
0x1800353a6  push    r13
0x1800353a8  push    r14
0x1800353aa  push    r15
0x1800353ac  sub     rsp, 80h
0x1800353b3  mov     rdi, rcx
0x1800353b6  lea     r12, WPP_GLOBAL_Control
0x1800353bd  mov     rax, cs:WPP_GLOBAL_Control
0x1800353c4  mov     bl, 1
0x1800353c6  cmp     rax, r12
0x1800353c9  jz      short loc_1800353DB
0x1800353cb  test    [rax+1Ch], bl
0x1800353ce  jz      short loc_1800353DB
0x1800353d0  cmp     byte ptr [rax+19h], 4
0x1800353d4  jb      short loc_1800353DB
0x1800353d6  mov     sil, bl
0x1800353d9  jmp     short loc_1800353DE
0x1800353db  xor     sil, sil
0x1800353de  lea     r13, WPP_RECORDER_INITIALIZED
0x1800353e5  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800353ec  setnz   r14b
0x1800353f0  test    sil, sil
0x1800353f3  jnz     short loc_180035403
0x1800353f5  test    r14b, r14b
0x1800353f8  jnz     short loc_180035403
0x1800353fa  lea     r15, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x180035401  jmp     short loc_180035440
0x180035403  call    cs:__imp_GetCurrentThreadId
0x18003540a  nop     dword ptr [rax+rax+00h]
0x18003540f  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x180035413  lea     r15, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x18003541a  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x18003541f  mov     word ptr [rsp+0B8h+var_88], 0Eh; char *
0x180035426  mov     rcx, cs:WPP_GLOBAL_Control
0x18003542d  mov     r9, [rcx+28h]; int
0x180035431  mov     r8b, r14b; int
0x180035434  mov     dl, sil; int
0x180035437  mov     rcx, [rcx+10h]; int
0x18003543b  call    WPP_RECORDER_AND_TRACE_SF_D
0x180035440  mov     rcx, rdi; this
0x180035443  call    ?Flush@CFileIoChannel@@AEAAXXZ; CFileIoChannel::Flush(void)
0x180035448  lea     rsi, [rdi+20h]
0x18003544c  mov     [rsp+0B8h+var_40], rsi
0x180035451  mov     rcx, rsi; this
0x180035454  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180035459  nop
0x18003545a  cmp     byte ptr [rdi+1B0h], 0
0x180035461  setz    al
0x180035464  mov     rcx, [rsp+0B8h]; this
0x18003546c  lea     rdx, aChannelIsNotSt; "Channel is not started"
0x180035473  mov     qword ptr [rsp+0B8h+var_90], rdx; bool
0x180035478  mov     [rsp+0B8h+var_98], al; char
0x18003547c  mov     r9d, 8000FFFFh; char *
0x180035482  lea     r8, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180035489  mov     edx, 14Bh; void *
0x18003548e  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180035493  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180035498  mov     r8, [rax+8]
0x18003549c  mov     eax, [r8]
0x18003549f  cmp     eax, 4
0x1800354a2  jbe     loc_18003557B
0x1800354a8  mov     rdx, 470000000000h
0x1800354b2  mov     rcx, r8
0x1800354b5  call    _tlgKeywordOn
0x1800354ba  test    al, al
0x1800354bc  jz      loc_18003557B
0x1800354c2  lea     rcx, [rdi+17Ch]
0x1800354c9  mov     eax, [rcx+20h]
0x1800354cc  mov     [rsp+0B8h+arg_0], eax
0x1800354d3  mov     [rsp+0B8h+arg_8], rcx
0x1800354db  lea     rax, aStopFileioChan; "Stop FileIo channel"
0x1800354e2  mov     [rsp+0B8h+arg_10], rax
0x1800354ea  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x1800354f1  mov     [rsp+0B8h+arg_18], rax
0x1800354f9  lea     rax, aRdpidd; "RdpIdd"
0x180035500  mov     [rsp+0B8h+var_58], rax
0x180035505  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x18003550e  lea     rax, aCheckpoint; "Checkpoint"
0x180035515  mov     [rsp+0B8h+var_48], rax
0x18003551a  lea     rax, [rsp+0B8h+arg_0]
0x180035522  mov     [rsp+0B8h+var_68], rax
0x180035527  lea     rax, [rsp+0B8h+arg_8]
0x18003552f  mov     [rsp+0B8h+var_70], rax
0x180035534  lea     rax, [rsp+0B8h+arg_10]
0x18003553c  mov     qword ptr [rsp+0B8h+var_78], rax
0x180035541  lea     rax, [rsp+0B8h+arg_18]
0x180035549  mov     [rsp+0B8h+MessageGuid], rax
0x18003554e  lea     rax, [rsp+0B8h+var_58]
0x180035553  mov     [rsp+0B8h+var_88], rax
0x180035558  lea     rax, [rsp+0B8h+var_50]
0x18003555d  mov     qword ptr [rsp+0B8h+var_90], rax; int
0x180035562  lea     rax, [rsp+0B8h+var_48]
0x180035567  mov     qword ptr [rsp+0B8h+var_98], rax
0x18003556c  lea     rdx, word_18005026A
0x180035573  mov     rcx, r8
0x180035576  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18003557b  mov     dword ptr [rsp+0B8h+var_98], 156h; int
0x180035583  lea     r9, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18003558a  lea     r8, aCfileiochannel_0; "CFileIoChannel::Stop"
0x180035591  lea     rdx, aFileiochannels; "FileIoChannelStop"
0x180035598  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003559f  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x1800355a4  lea     rcx, [rdi+1A8h]
0x1800355ab  call    ?reset@?$com_ptr_t@UIFileIoChannelEvents@Avenc@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<Rdp::Avenc::IFileIoChannelEvents,wil::err_exception_policy>::reset(void)
0x1800355b0  mov     byte ptr [rdi+1B0h], 0
0x1800355b7  mov     rax, cs:WPP_GLOBAL_Control
0x1800355be  cmp     rax, r12
0x1800355c1  jz      short loc_1800355CE
0x1800355c3  test    [rax+1Ch], bl
0x1800355c6  jz      short loc_1800355CE
0x1800355c8  cmp     byte ptr [rax+19h], 4
0x1800355cc  jnb     short loc_1800355D0
0x1800355ce  xor     bl, bl
0x1800355d0  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1800355d7  setnz   dil
0x1800355db  test    bl, bl
0x1800355dd  jnz     short loc_1800355E4
0x1800355df  test    dil, dil
0x1800355e2  jz      short loc_18003561A
0x1800355e4  call    cs:__imp_GetCurrentThreadId
0x1800355eb  nop     dword ptr [rax+rax+00h]
0x1800355f0  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x1800355f4  mov     [rsp+0B8h+MessageGuid], r15; MessageGuid
0x1800355f9  mov     word ptr [rsp+0B8h+var_88], 0Fh; __int16
0x180035600  mov     rcx, cs:WPP_GLOBAL_Control
0x180035607  mov     r9, [rcx+28h]; int
0x18003560b  mov     r8b, dil; int
0x18003560e  mov     dl, bl; int
0x180035610  mov     rcx, [rcx+10h]; int
0x180035614  call    WPP_RECORDER_AND_TRACE_SF_D
0x180035619  nop
0x18003561a  mov     rcx, rsi; _Mtx_t
0x18003561d  call    cs:__imp__Mtx_unlock
0x180035624  nop     dword ptr [rax+rax+00h]
0x180035629  xor     eax, eax
0x18003562b  jmp     short loc_180035634
0x18003562d  mov     eax, [rsp+0B8h+arg_0]
0x180035634  add     rsp, 80h
0x18003563b  pop     r15
0x18003563d  pop     r14
0x18003563f  pop     r13
0x180035641  pop     r12
0x180035643  pop     rdi
0x180035644  pop     rsi
0x180035645  pop     rbx
0x180035646  retn
```
