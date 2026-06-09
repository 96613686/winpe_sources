# CFileIoChannel::Start(void)

- ea: `0x180034dd0`
- end: `0x1800351fb`
- name: `?Start@CFileIoChannel@@UEAAJXZ`
- size: `1067`
- prototype: `__int64 __fastcall(CFileIoChannel *__hidden this)`
- caller_count: `0`
- callee_count: `13`
- tags: ``

## callees

- `0x180001af0`
- `0x18000621c`
- `0x180007b38`
- `0x18000d614`
- `0x18000d6d8`
- `0x18000dbd8`
- `0x1800106b8`
- `0x180017ac8`
- `0x18001dd70`
- `0x180021570`
- `0x180033a34`
- `0x180034dd0`
- `0x18003f010`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800351d0`
- `msvcp_win!_Mtx_unlock` at `0x1800351d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035197`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034e33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035197`

## string_xrefs

- `0x180034e8d`: `Channel is already started`
- `0x180034ee4`: `Failed to retrieve PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length property`
- `0x180034f1f`: `Failed to retrieve PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length property`
- `0x180034fbd`: `Failed to initialize pending Read queue`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CFileIoChannel::Start(CFileIoChannel *this)
{
  char v2; // bl
  bool v3; // si
  bool v4; // r14
  char CurrentThreadId; // al
  int v6; // r8d
  int v7; // edx
  struct _Mtx_internal_imp_t *v8; // rsi
  unsigned int *v9; // r9
  Rdp::Utils::Props *v10; // rcx
  int *v11; // r14
  unsigned int UInt32; // eax
  unsigned int *v13; // r9
  unsigned int v14; // eax
  int v15; // eax
  unsigned int v16; // eax
  _DWORD *v17; // r8
  int v18; // r8d
  int v19; // r9d
  bool v20; // di
  char v21; // al
  int v22; // r8d
  int v23; // edx
  const char *v24; // r9
  __int64 result; // rax
  int v26; // [rsp+20h] [rbp-138h]
  int v27; // [rsp+20h] [rbp-138h]
  int v28; // [rsp+28h] [rbp-130h]
  char *v29; // [rsp+28h] [rbp-130h]
  char *v30; // [rsp+28h] [rbp-130h]
  int v31; // [rsp+28h] [rbp-130h]
  char *v32; // [rsp+30h] [rbp-128h]
  int v33; // [rsp+80h] [rbp-D8h] BYREF
  char *v34; // [rsp+88h] [rbp-D0h] BYREF
  const char *v35; // [rsp+90h] [rbp-C8h] BYREF
  GUID *v36; // [rsp+98h] [rbp-C0h] BYREF
  const char *v37; // [rsp+A0h] [rbp-B8h] BYREF
  int v38[2]; // [rsp+A8h] [rbp-B0h] BYREF
  _QWORD v39[2]; // [rsp+B0h] [rbp-A8h] BYREF
  int v40; // [rsp+C0h] [rbp-98h] BYREF
  __int64 v41; // [rsp+C4h] [rbp-94h]
  _BYTE v42[140]; // [rsp+CCh] [rbp-8Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+0h]
  int v44; // [rsp+160h] [rbp+8h] BYREF
  int v45; // [rsp+168h] [rbp+10h] BYREF
  int v46; // [rsp+170h] [rbp+18h] BYREF
  int v47; // [rsp+178h] [rbp+20h] BYREF

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
      v26,
      v28,
      12,
      &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
      CurrentThreadId);
  }
  v8 = (CFileIoChannel *)((char *)this + 32);
  v39[1] = (char *)this + 32;
  try
  {
    std::_Mutex_base::lock((CFileIoChannel *)((char *)this + 32));
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xE1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      (const char *)0x8000FFFFLL,
      *((_BYTE *)this + 432),
      (bool)"Channel is already started",
      v32);
    v10 = (Rdp::Utils::Props *)*((_QWORD *)this + 3);
    v11 = (int *)((char *)this + 356);
    if ( v10 )
    {
      UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
                 v10,
                 (struct IPropertyStore *)&PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length,
                 (const struct _tagpropertykey *)((char *)this + 356),
                 v9);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0xED,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)UInt32,
        (int)"Failed to retrieve PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length property",
        v29);
      v14 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
              *((Rdp::Utils::Props **)this + 3),
              (struct IPropertyStore *)&PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length,
              (const struct _tagpropertykey *)this + 18,
              v13);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
        (const char *)v14,
        (int)"Failed to retrieve PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length property",
        v30);
    }
    if ( *((_DWORD *)this + 94) == 2 )
    {
      v15 = 16;
      if ( (unsigned int)*v11 < 0x10 )
        v15 = *v11;
      *v11 = v15;
    }
    memset_0(v42, 0, 0x54u);
    v40 = 96;
    v41 = 3;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, int *, _QWORD, char *))(WdfFunctions_02025 + 680))(
            WdfDriverGlobals,
            *((_QWORD *)this + 24),
            &v40,
            0,
            (char *)this + 200);
    wil::details::in1diag3::Throw_IfNtStatusFailedMsg(
      retaddr,
      (void *)0x116,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      (const char *)v16,
      (int)"Failed to initialize pending Read queue",
      v29);
    *((_BYTE *)this + 432) = 1;
    v17 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v17 > 4u && (unsigned __int8)tlgKeywordOn(v17, 0x470000000000LL) )
    {
      v44 = *v11;
      v45 = *((_DWORD *)this + 91);
      v46 = *((_DWORD *)this + 88);
      v47 = *((_DWORD *)this + 92);
      v33 = *((_DWORD *)this + 103);
      v34 = (char *)this + 380;
      v35 = "Start FileIo channel";
      v36 = &RdpIddLoggingProviderWithCorrelationId::g_CorrelationId;
      v37 = "RdpIdd";
      *(_QWORD *)v38 = 0x1000000;
      v39[0] = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)byte_1800502D9,
        v18,
        v19,
        (__int64)v39,
        (__int64)v38,
        (__int64)&v37,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v33,
        (__int64)&v47,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&v44);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)&Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"FileIoChannelStart",
      "CFileIoChannel::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
      0x127u);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v2 = 0;
    }
    v20 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = GetCurrentThreadId();
      LOBYTE(v22) = v20;
      LOBYTE(v23) = v2;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v23,
        v22,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v27,
        v31,
        13,
        &WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids,
        v21);
    }
    _Mtx_unlock(v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x12C,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\fileio.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x180034dd0  push    rbx
0x180034dd2  push    rsi
0x180034dd3  push    rdi
0x180034dd4  push    r12
0x180034dd6  push    r13
0x180034dd8  push    r14
0x180034dda  push    r15
0x180034ddc  sub     rsp, 120h
0x180034de3  mov     rdi, rcx
0x180034de6  lea     r13, WPP_GLOBAL_Control
0x180034ded  mov     rax, cs:WPP_GLOBAL_Control
0x180034df4  mov     bl, 1
0x180034df6  cmp     rax, r13
0x180034df9  jz      short loc_180034E0B
0x180034dfb  test    [rax+1Ch], bl
0x180034dfe  jz      short loc_180034E0B
0x180034e00  cmp     byte ptr [rax+19h], 4
0x180034e04  jb      short loc_180034E0B
0x180034e06  mov     sil, bl
0x180034e09  jmp     short loc_180034E0E
0x180034e0b  xor     sil, sil
0x180034e0e  lea     rax, WPP_RECORDER_INITIALIZED
0x180034e15  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180034e1c  setnz   r14b
0x180034e20  test    sil, sil
0x180034e23  jnz     short loc_180034E33
0x180034e25  test    r14b, r14b
0x180034e28  jnz     short loc_180034E33
0x180034e2a  lea     r15, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x180034e31  jmp     short loc_180034E70
0x180034e33  call    cs:__imp_GetCurrentThreadId
0x180034e3a  nop     dword ptr [rax+rax+00h]
0x180034e3f  mov     dword ptr [rsp+158h+var_118], eax; char
0x180034e43  lea     r15, WPP_676c857ae9aa3c3b3a5fb41536c15598_Traceguids
0x180034e4a  mov     [rsp+158h+MessageGuid], r15; MessageGuid
0x180034e4f  mov     word ptr [rsp+158h+var_128], 0Ch; char *
0x180034e56  mov     rcx, cs:WPP_GLOBAL_Control
0x180034e5d  mov     r9, [rcx+28h]; int
0x180034e61  mov     r8b, r14b; int
0x180034e64  mov     dl, sil; int
0x180034e67  mov     rcx, [rcx+10h]; int
0x180034e6b  call    WPP_RECORDER_AND_TRACE_SF_D
0x180034e70  lea     rsi, [rdi+20h]
0x180034e74  mov     [rsp+158h+var_A0], rsi
0x180034e7c  mov     rcx, rsi; this
0x180034e7f  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180034e84  nop
0x180034e85  mov     rcx, [rsp+158h]; this
0x180034e8d  lea     rax, aChannelIsAlrea; "Channel is already started"
0x180034e94  mov     [rsp+158h+var_130], rax; char *
0x180034e99  mov     al, [rdi+1B0h]
0x180034e9f  mov     [rsp+158h+var_138], al; char
0x180034ea3  mov     r9d, 8000FFFFh; char *
0x180034ea9  lea     r12, aOnecoreuapTerm_11; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x180034eb0  mov     r8, r12; unsigned int
0x180034eb3  mov     edx, 0E1h; void *
0x180034eb8  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180034ebd  mov     rcx, [rdi+18h]; this
0x180034ec1  lea     r14, [rdi+164h]
0x180034ec8  test    rcx, rcx
0x180034ecb  jz      short loc_180034F3B
0x180034ecd  mov     r8, r14; struct _tagpropertykey *
0x180034ed0  lea     rdx, PKEY_Caps_FileIo_Read_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180034ed7  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180034edc  mov     rcx, [rsp+158h]; this
0x180034ee4  lea     rdx, aFailedToRetrie_3; "Failed to retrieve PKEY_Caps_FileIo_Rea"...
0x180034eeb  mov     qword ptr [rsp+158h+var_138], rdx; int
0x180034ef0  mov     r9d, eax; char *
0x180034ef3  mov     r8, r12; unsigned int
0x180034ef6  mov     edx, 0EDh; void *
0x180034efb  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034f00  lea     r8, [rdi+168h]; struct _tagpropertykey *
0x180034f07  lea     rdx, PKEY_Caps_FileIo_Write_Irp_Min_Buffer_Length; struct IPropertyStore *
0x180034f0e  mov     rcx, [rdi+18h]; this
0x180034f12  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180034f17  mov     rcx, [rsp+158h]; this
0x180034f1f  lea     rdx, aFailedToRetrie_0; "Failed to retrieve PKEY_Caps_FileIo_Wri"...
0x180034f26  mov     qword ptr [rsp+158h+var_138], rdx; int
0x180034f2b  mov     r9d, eax; char *
0x180034f2e  mov     r8, r12; unsigned int
0x180034f31  mov     edx, 0F7h; void *
0x180034f36  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034f3b  cmp     dword ptr [rdi+178h], 2
0x180034f42  jnz     short loc_180034F53
0x180034f44  mov     eax, 10h
0x180034f49  cmp     [r14], eax
0x180034f4c  cmovb   eax, [r14]
0x180034f50  mov     [r14], eax
0x180034f53  xor     edx, edx; Val
0x180034f55  lea     r8d, [rdx+54h]; Size
0x180034f59  lea     rcx, [rsp+158h+var_8C]; void *
0x180034f61  call    memset_0
0x180034f66  mov     [rsp+158h+var_98], 60h ; '`'
0x180034f71  mov     [rsp+158h+var_94], 3
0x180034f7d  lea     rcx, [rdi+0C8h]
0x180034f84  mov     rax, cs:WdfFunctions_02025
0x180034f8b  mov     qword ptr [rsp+158h+var_138], rcx
0x180034f90  xor     r9d, r9d
0x180034f93  lea     r8, [rsp+158h+var_98]
0x180034f9b  mov     rdx, [rdi+0C0h]
0x180034fa2  mov     rcx, cs:WdfDriverGlobals
0x180034fa9  mov     rax, [rax+2A8h]
0x180034fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034fb5  mov     rcx, [rsp+158h]; this
0x180034fbd  lea     rdx, aFailedToInitia_0; "Failed to initialize pending Read queue"
0x180034fc4  mov     qword ptr [rsp+158h+var_138], rdx; int
0x180034fc9  mov     r9d, eax; char *
0x180034fcc  mov     r8, r12; unsigned int
0x180034fcf  mov     edx, 116h; void *
0x180034fd4  call    ?Throw_IfNtStatusFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfNtStatusFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034fd9  mov     [rdi+1B0h], bl
0x180034fdf  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x180034fe4  mov     r8, [rax+8]
0x180034fe8  mov     eax, [r8]
0x180034feb  cmp     eax, 4
0x180034fee  jbe     loc_18003513E
0x180034ff4  mov     rdx, 470000000000h
0x180034ffe  mov     rcx, r8
0x180035001  call    _tlgKeywordOn
0x180035006  test    al, al
0x180035008  jz      loc_18003513E
0x18003500e  mov     eax, [r14]
0x180035011  mov     [rsp+158h+arg_0], eax
0x180035018  mov     eax, [rdi+16Ch]
0x18003501e  mov     [rsp+158h+arg_8], eax
0x180035025  mov     eax, [rdi+160h]
0x18003502b  mov     [rsp+158h+arg_10], eax
0x180035032  mov     eax, [rdi+170h]
0x180035038  mov     [rsp+158h+arg_18], eax
0x18003503f  lea     rcx, [rdi+17Ch]
0x180035046  mov     eax, [rcx+20h]
0x180035049  mov     [rsp+158h+var_D8], eax
0x180035050  mov     [rsp+158h+var_D0], rcx
0x180035058  lea     rax, aStartFileioCha; "Start FileIo channel"
0x18003505f  mov     [rsp+158h+var_C8], rax
0x180035067  lea     rax, ?g_CorrelationId@RdpIddLoggingProviderWithCorrelationId@@2U_GUID@@A; _GUID RdpIddLoggingProviderWithCorrelationId::g_CorrelationId
0x18003506e  mov     [rsp+158h+var_C0], rax
0x180035076  lea     rax, aRdpidd; "RdpIdd"
0x18003507d  mov     [rsp+158h+var_B8], rax
0x180035085  mov     qword ptr [rsp+158h+var_B0], 1000000h
0x180035091  lea     rax, aCheckpoint; "Checkpoint"
0x180035098  mov     [rsp+158h+var_A8], rax
0x1800350a0  lea     rax, [rsp+158h+arg_0]
0x1800350a8  mov     [rsp+158h+var_E8], rax
0x1800350ad  lea     rax, [rsp+158h+arg_8]
0x1800350b5  mov     [rsp+158h+var_F0], rax
0x1800350ba  lea     rax, [rsp+158h+arg_10]
0x1800350c2  mov     [rsp+158h+var_F8], rax
0x1800350c7  lea     rax, [rsp+158h+arg_18]
0x1800350cf  mov     [rsp+158h+var_100], rax
0x1800350d4  lea     rax, [rsp+158h+var_D8]
0x1800350dc  mov     [rsp+158h+var_108], rax
0x1800350e1  lea     rax, [rsp+158h+var_D0]
0x1800350e9  mov     [rsp+158h+var_110], rax
0x1800350ee  lea     rax, [rsp+158h+var_C8]
0x1800350f6  mov     qword ptr [rsp+158h+var_118], rax
0x1800350fb  lea     rax, [rsp+158h+var_C0]
0x180035103  mov     [rsp+158h+MessageGuid], rax
0x180035108  lea     rax, [rsp+158h+var_B8]
0x180035110  mov     [rsp+158h+var_128], rax
0x180035115  lea     rax, [rsp+158h+var_B0]
0x18003511d  mov     [rsp+158h+var_130], rax; int
0x180035122  lea     rax, [rsp+158h+var_A8]
0x18003512a  mov     qword ptr [rsp+158h+var_138], rax
0x18003512f  lea     rdx, byte_1800502D9
0x180035136  mov     rcx, r8
0x180035139  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U3@U?$_tlgWrapperByVal@$03@@U4@U4@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@35AEBU?$_tlgWrapperByVal@$03@@6666@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003513e  mov     dword ptr [rsp+158h+var_138], 127h; int
0x180035146  mov     r9, r12; char *
0x180035149  lea     r8, aCfileiochannel; "CFileIoChannel::Start"
0x180035150  lea     rdx, aFileiochannels_0; "FileIoChannelStart"
0x180035157  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003515e  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180035163  mov     rax, cs:WPP_GLOBAL_Control
0x18003516a  cmp     rax, r13
0x18003516d  jz      short loc_18003517A
0x18003516f  test    [rax+1Ch], bl
0x180035172  jz      short loc_18003517A
0x180035174  cmp     byte ptr [rax+19h], 4
0x180035178  jnb     short loc_18003517C
0x18003517a  xor     bl, bl
0x18003517c  lea     rax, WPP_RECORDER_INITIALIZED
0x180035183  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003518a  setnz   dil
0x18003518e  test    bl, bl
0x180035190  jnz     short loc_180035197
0x180035192  test    dil, dil
0x180035195  jz      short loc_1800351CD
0x180035197  call    cs:__imp_GetCurrentThreadId
0x18003519e  nop     dword ptr [rax+rax+00h]
0x1800351a3  mov     dword ptr [rsp+158h+var_118], eax; char
0x1800351a7  mov     [rsp+158h+MessageGuid], r15; MessageGuid
0x1800351ac  mov     word ptr [rsp+158h+var_128], 0Dh; __int16
0x1800351b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800351ba  mov     r9, [rcx+28h]; int
0x1800351be  mov     r8b, dil; int
0x1800351c1  mov     dl, bl; int
0x1800351c3  mov     rcx, [rcx+10h]; int
0x1800351c7  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800351cc  nop
0x1800351cd  mov     rcx, rsi; _Mtx_t
0x1800351d0  call    cs:__imp__Mtx_unlock
0x1800351d7  nop     dword ptr [rax+rax+00h]
0x1800351dc  xor     eax, eax
0x1800351de  jmp     short loc_1800351E7
0x1800351e0  mov     eax, [rsp+158h+arg_0]
0x1800351e7  add     rsp, 120h
0x1800351ee  pop     r15
0x1800351f0  pop     r14
0x1800351f2  pop     r13
0x1800351f4  pop     r12
0x1800351f6  pop     rdi
0x1800351f7  pop     rsi
0x1800351f8  pop     rbx
0x1800351f9  retn
```
