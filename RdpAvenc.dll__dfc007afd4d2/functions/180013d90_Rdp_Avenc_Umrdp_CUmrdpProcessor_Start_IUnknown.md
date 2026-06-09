# Rdp::Avenc::Umrdp::CUmrdpProcessor::Start(IUnknown *)

- ea: `0x180013d90`
- end: `0x180014220`
- name: `?Start@CUmrdpProcessor@Umrdp@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(Rdp::Avenc::Umrdp::CUmrdpProcessor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x18000e848`
- `0x18000ec04`
- `0x180011490`
- `0x1800124ec`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x180013d90`
- `0x1800153f8`
- `0x180015480`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013df8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013df8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800141a6`

## string_xrefs

- `0x18001420d`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Avenc::Umrdp::CUmrdpProcessor::Start(
        Rdp::Avenc::Umrdp::CUmrdpProcessor *this,
        struct IUnknown *a2)
{
  char v4; // di
  bool v5; // r14
  bool v6; // r15
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  Rdp::Utils::Props **v10; // r15
  struct _GUID *v11; // r9
  __int64 v12; // rcx
  int v13; // eax
  unsigned int Guid; // eax
  unsigned int *v15; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v17; // rdx
  struct _LUID *v18; // r9
  unsigned int Luid; // eax
  unsigned int *v20; // r9
  unsigned int v21; // eax
  bool *v22; // r9
  unsigned int Bool; // eax
  bool *v24; // r9
  unsigned int v25; // eax
  int v26; // r8d
  int v27; // r9d
  const char *v28; // r9
  bool v29; // si
  char v30; // al
  int v31; // r8d
  int v32; // edx
  __int64 result; // rax
  int v34; // [rsp+20h] [rbp-A8h]
  int v35; // [rsp+20h] [rbp-A8h]
  int v36; // [rsp+28h] [rbp-A0h]
  char *v37; // [rsp+28h] [rbp-A0h]
  char *v38; // [rsp+28h] [rbp-A0h]
  char *v39; // [rsp+28h] [rbp-A0h]
  char *v40; // [rsp+28h] [rbp-A0h]
  char *v41; // [rsp+28h] [rbp-A0h]
  int v42; // [rsp+28h] [rbp-A0h]
  int *v43; // [rsp+60h] [rbp-68h] BYREF
  const char *v44; // [rsp+68h] [rbp-60h] BYREF
  int v45[2]; // [rsp+70h] [rbp-58h] BYREF
  struct _tagpropertykey v46[4]; // [rsp+78h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  int v48; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v49; // [rsp+E0h] [rbp+18h] BYREF
  const char *v50; // [rsp+E8h] [rbp+20h] BYREF

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
      v34,
      v36,
      12,
      &WPP_44e245a864023212cc554d824265b257_Traceguids,
      CurrentThreadId);
  }
  v10 = (Rdp::Utils::Props **)((char *)this + 24);
  try
  {
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      100,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      2147549183LL);
    *(_QWORD *)&v46[0].pid = a2;
    if ( a2 )
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->AddRef)(a2);
    v12 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = 0;
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    if ( a2 )
    {
      v13 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
              a2,
              &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
              (char *)this + 32);
      if ( v13 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v13,
          (_DWORD)this + 24);
    }
    else
    {
      *((_QWORD *)this + 4) = 0;
    }
    v46[0].fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v10, (struct IPropertyStore *)&PKEY_Activity_Id, v46, v11);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v46[0].fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v10,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)((char *)this + 116),
               v15);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x7E,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v37);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(
             *v10,
             v17,
             (const struct _tagpropertykey *)((char *)this + 108),
             v18);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x88,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v38);
    v21 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
            *v10,
            (struct IPropertyStore *)&PKEY_Bind_Process_Pid,
            (const struct _tagpropertykey *)this + 6,
            v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x92,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)v21,
      (int)"Failed to retrieve PKEY_Bind_Process_Pid property",
      v39);
    Bool = Rdp::Utils::Props::IPropertyStore_GetBool(
             *v10,
             (struct IPropertyStore *)&PKEY_Console_Mode_Enabled,
             (const struct _tagpropertykey *)((char *)this + 124),
             v22);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x9C,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)Bool,
      (int)"Failed to retrieve PKEY_Console_Mode_Enabled property",
      v40);
    v25 = Rdp::Utils::Props::IPropertyStore_GetBool(
            *v10,
            (struct IPropertyStore *)&PKEY_Large_Cursor_Enabled,
            (const struct _tagpropertykey *)((char *)this + 125),
            v24);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xA6,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      (const char *)v25,
      (int)"Failed to retrieve PKEY_Large_Cursor_Enabled property",
      v41);
    *((_BYTE *)this + 16) = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v49 = *(_QWORD *)((char *)this + 108);
      v48 = *((_DWORD *)this + 29);
      v50 = "Start Umrdp processor";
      v43 = &xmmword_1800C21A0;
      v44 = "RdpAvenc";
      *(_QWORD *)v45 = 0x1000000;
      *(_QWORD *)&v46[0].fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800AC86B,
        v26,
        v27,
        (__int64)v46,
        (__int64)v45,
        (__int64)&v44,
        (__int64)&v43,
        (__int64)&v50,
        (__int64)&v48,
        (__int64)&v49);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"UmrdpProcessorStart",
      "Rdp::Avenc::Umrdp::CUmrdpProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
      0xB3u);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v29 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v30 = GetCurrentThreadId();
      LOBYTE(v31) = v29;
      LOBYTE(v32) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v32,
        v31,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v35,
        v42,
        13,
        &WPP_44e245a864023212cc554d824265b257_Traceguids,
        v30);
    }
    if ( a2 )
      ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB8,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\umrdpprocessor\\umrdpprocessor.cpp",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x180013d90  push    rbx
0x180013d92  push    rsi
0x180013d93  push    rdi
0x180013d94  push    r12
0x180013d96  push    r13
0x180013d98  push    r14
0x180013d9a  push    r15
0x180013d9c  sub     rsp, 90h
0x180013da3  mov     rbx, rdx
0x180013da6  mov     rsi, rcx
0x180013da9  lea     rcx, WPP_GLOBAL_Control
0x180013db0  mov     rax, cs:WPP_GLOBAL_Control
0x180013db7  mov     dil, 1
0x180013dba  cmp     rax, rcx
0x180013dbd  jz      short loc_180013DD0
0x180013dbf  test    [rax+1Ch], dil
0x180013dc3  jz      short loc_180013DD0
0x180013dc5  cmp     byte ptr [rax+19h], 4
0x180013dc9  jb      short loc_180013DD0
0x180013dcb  mov     r14b, dil
0x180013dce  jmp     short loc_180013DD3
0x180013dd0  xor     r14b, r14b
0x180013dd3  lea     rax, WPP_RECORDER_INITIALIZED
0x180013dda  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180013de1  setnz   r15b
0x180013de5  test    r14b, r14b
0x180013de8  jnz     short loc_180013DF8
0x180013dea  test    r15b, r15b
0x180013ded  jnz     short loc_180013DF8
0x180013def  lea     r12, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180013df6  jmp     short loc_180013E2F
0x180013df8  call    cs:__imp_GetCurrentThreadId
0x180013dfe  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x180013e02  lea     r12, WPP_44e245a864023212cc554d824265b257_Traceguids
0x180013e09  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x180013e0e  mov     [rsp+0C8h+var_98], 0Ch; __int16
0x180013e15  mov     rcx, cs:WPP_GLOBAL_Control
0x180013e1c  mov     r9, [rcx+28h]; int
0x180013e20  mov     r8b, r15b; int
0x180013e23  mov     dl, r14b; int
0x180013e26  mov     rcx, [rcx+10h]; int
0x180013e2a  call    WPP_RECORDER_AND_TRACE_SF_D
0x180013e2f  lea     r15, [rsi+18h]
0x180013e33  mov     rcx, [rsp+0C8h]
0x180013e3b  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x180013e42  mov     [rsp+0C8h+var_A0], rax; char *
0x180013e47  mov     qword ptr [rsp+0C8h+var_A8], r15; int
0x180013e4c  mov     r9d, 8000FFFFh
0x180013e52  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180013e59  mov     edx, 64h ; 'd'
0x180013e5e  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x180013e63  nop
0x180013e64  mov     qword ptr [rsp+0C8h+var_50+10h], rbx
0x180013e6c  test    rbx, rbx
0x180013e6f  jz      short loc_180013E81
0x180013e71  mov     rax, [rbx]
0x180013e74  mov     rcx, rbx
0x180013e77  mov     rax, [rax+8]
0x180013e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e80  nop
0x180013e81  lea     r14, [rsi+20h]
0x180013e85  mov     rcx, [r14]
0x180013e88  mov     qword ptr [r14], 0
0x180013e8f  test    rcx, rcx
0x180013e92  jz      short loc_180013EA1
0x180013e94  mov     rax, [rcx]
0x180013e97  mov     rax, [rax+10h]
0x180013e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ea0  nop
0x180013ea1  test    rbx, rbx
0x180013ea4  jz      short loc_180013ED0
0x180013ea6  mov     rax, [rbx]
0x180013ea9  mov     r8, r14
0x180013eac  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x180013eb3  mov     rcx, rbx
0x180013eb6  mov     rax, [rax]
0x180013eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ebe  mov     rcx, [rsp+0C8h]; this
0x180013ec6  test    eax, eax
0x180013ec8  js      loc_18001420A
0x180013ece  jmp     short loc_180013ED7
0x180013ed0  mov     qword ptr [r14], 0
0x180013ed7  xorps   xmm0, xmm0
0x180013eda  movups  xmmword ptr [rsp+0C8h+var_50], xmm0
0x180013edf  lea     r8, [rsp+0C8h+var_50]; struct _tagpropertykey *
0x180013ee4  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x180013eeb  mov     rcx, [r15]; this
0x180013eee  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x180013ef3  mov     rcx, [rsp+0C8h]; this
0x180013efb  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x180013f02  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180013f07  mov     r9d, eax; char *
0x180013f0a  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180013f11  mov     edx, 72h ; 'r'; void *
0x180013f16  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013f1b  movups  xmm0, xmmword ptr [rsp+0C8h+var_50]
0x180013f20  movdqu  cs:xmmword_1800C21A0, xmm0
0x180013f28  lea     r8, [rsi+74h]; struct _tagpropertykey *
0x180013f2c  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x180013f33  mov     rcx, [r15]; this
0x180013f36  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180013f3b  mov     rcx, [rsp+0C8h]; this
0x180013f43  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x180013f4a  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180013f4f  mov     r9d, eax; char *
0x180013f52  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180013f59  mov     edx, 7Eh ; '~'; void *
0x180013f5e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013f63  lea     r8, [rsi+6Ch]; struct _tagpropertykey *
0x180013f67  mov     rcx, [r15]; this
0x180013f6a  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x180013f6f  mov     rcx, [rsp+0C8h]; this
0x180013f77  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x180013f7e  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180013f83  mov     r9d, eax; char *
0x180013f86  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180013f8d  mov     edx, 88h; void *
0x180013f92  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013f97  lea     r8, [rsi+78h]; struct _tagpropertykey *
0x180013f9b  lea     rdx, PKEY_Bind_Process_Pid; struct IPropertyStore *
0x180013fa2  mov     rcx, [r15]; this
0x180013fa5  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180013faa  mov     rcx, [rsp+0C8h]; this
0x180013fb2  lea     rdx, aFailedToRetrie_22; "Failed to retrieve PKEY_Bind_Process_Pi"...
0x180013fb9  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180013fbe  mov     r9d, eax; char *
0x180013fc1  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180013fc8  mov     edx, 92h; void *
0x180013fcd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180013fd2  lea     r8, [rsi+7Ch]; struct _tagpropertykey *
0x180013fd6  lea     rdx, PKEY_Console_Mode_Enabled; struct IPropertyStore *
0x180013fdd  mov     rcx, [r15]; this
0x180013fe0  call    ?IPropertyStore_GetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEA_N@Z; Rdp::Utils::Props::IPropertyStore_GetBool(IPropertyStore *,_tagpropertykey const &,bool *)
0x180013fe5  mov     rcx, [rsp+0C8h]; this
0x180013fed  lea     rdx, aFailedToRetrie_16; "Failed to retrieve PKEY_Console_Mode_En"...
0x180013ff4  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180013ff9  mov     r9d, eax; char *
0x180013ffc  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180014003  mov     edx, 9Ch; void *
0x180014008  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18001400d  lea     r8, [rsi+7Dh]; struct _tagpropertykey *
0x180014011  lea     rdx, PKEY_Large_Cursor_Enabled; struct IPropertyStore *
0x180014018  mov     rcx, [r15]; this
0x18001401b  call    ?IPropertyStore_GetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEA_N@Z; Rdp::Utils::Props::IPropertyStore_GetBool(IPropertyStore *,_tagpropertykey const &,bool *)
0x180014020  mov     rcx, [rsp+0C8h]; this
0x180014028  lea     rdx, aFailedToRetrie_1; "Failed to retrieve PKEY_Large_Cursor_En"...
0x18001402f  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x180014034  mov     r9d, eax; char *
0x180014037  lea     r8, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001403e  mov     edx, 0A6h; void *
0x180014043  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180014048  mov     [rsi+10h], dil
0x18001404c  mov     eax, cs:dword_1800C1058
0x180014052  cmp     eax, 4
0x180014055  jbe     loc_18001413F
0x18001405b  mov     rcx, cs:qword_1800C1070
0x180014062  mov     rax, cs:qword_1800C1068
0x180014069  mov     rdx, 470000000000h
0x180014073  test    rdx, rax
0x180014076  jz      loc_18001413F
0x18001407c  mov     rax, rcx
0x18001407f  and     rax, rdx
0x180014082  cmp     rax, rcx
0x180014085  jnz     loc_18001413F
0x18001408b  mov     rax, [rsi+6Ch]
0x18001408f  mov     [rsp+0C8h+arg_10], rax
0x180014097  mov     eax, [rsi+74h]
0x18001409a  mov     [rsp+0C8h+arg_0], eax
0x1800140a1  lea     rax, aStartUmrdpProc; "Start Umrdp processor"
0x1800140a8  mov     [rsp+0C8h+arg_18], rax
0x1800140b0  lea     rax, xmmword_1800C21A0
0x1800140b7  mov     [rsp+0C8h+var_68], rax
0x1800140bc  lea     rax, aRdpavenc; "RdpAvenc"
0x1800140c3  mov     [rsp+0C8h+var_60], rax
0x1800140c8  mov     qword ptr [rsp+0C8h+var_58], 1000000h
0x1800140d1  lea     rax, aCheckpoint; "Checkpoint"
0x1800140d8  mov     qword ptr [rsp+0C8h+var_50], rax
0x1800140dd  lea     rax, [rsp+0C8h+arg_10]
0x1800140e5  mov     [rsp+0C8h+var_78], rax
0x1800140ea  lea     rax, [rsp+0C8h+arg_0]
0x1800140f2  mov     [rsp+0C8h+var_80], rax
0x1800140f7  lea     rax, [rsp+0C8h+arg_18]
0x1800140ff  mov     qword ptr [rsp+0C8h+var_88], rax
0x180014104  lea     rax, [rsp+0C8h+var_68]
0x180014109  mov     [rsp+0C8h+MessageGuid], rax
0x18001410e  lea     rax, [rsp+0C8h+var_60]
0x180014113  mov     qword ptr [rsp+0C8h+var_98], rax
0x180014118  lea     rax, [rsp+0C8h+var_58]
0x18001411d  mov     [rsp+0C8h+var_A0], rax; int
0x180014122  lea     rax, [rsp+0C8h+var_50]
0x180014127  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18001412c  lea     rdx, byte_1800AC86B
0x180014133  lea     rcx, dword_1800C1058
0x18001413a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18001413f  mov     [rsp+0C8h+var_A8], 0B3h; int
0x180014147  lea     r9, aOnecoreuapTerm_58; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18001414e  lea     r8, aRdpAvencUmrdpC_17; "Rdp::Avenc::Umrdp::CUmrdpProcessor::Sta"...
0x180014155  lea     rdx, aUmrdpprocessor_0; "UmrdpProcessorStart"
0x18001415c  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180014163  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180014168  mov     rax, cs:WPP_GLOBAL_Control
0x18001416f  lea     rcx, WPP_GLOBAL_Control
0x180014176  cmp     rax, rcx
0x180014179  jz      short loc_180014187
0x18001417b  test    [rax+1Ch], dil
0x18001417f  jz      short loc_180014187
0x180014181  cmp     byte ptr [rax+19h], 4
0x180014185  jnb     short loc_18001418A
0x180014187  xor     dil, dil
0x18001418a  lea     rax, WPP_RECORDER_INITIALIZED
0x180014191  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180014198  setnz   sil
0x18001419c  test    dil, dil
0x18001419f  jnz     short loc_1800141A6
0x1800141a1  test    sil, sil
0x1800141a4  jz      short loc_1800141D7
0x1800141a6  call    cs:__imp_GetCurrentThreadId
0x1800141ac  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x1800141b0  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x1800141b5  mov     [rsp+0C8h+var_98], 0Dh; __int16
0x1800141bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800141c3  mov     r9, [rcx+28h]; int
0x1800141c7  mov     r8b, sil; int
0x1800141ca  mov     dl, dil; int
0x1800141cd  mov     rcx, [rcx+10h]; int
0x1800141d1  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800141d6  nop
0x1800141d7  test    rbx, rbx
0x1800141da  jz      short loc_1800141EC
0x1800141dc  mov     rax, [rbx]
0x1800141df  mov     rcx, rbx
0x1800141e2  mov     rax, [rax+10h]
0x1800141e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141eb  nop
0x1800141ec  xor     eax, eax
0x1800141ee  jmp     short loc_1800141F7
0x1800141f0  mov     eax, [rsp+0C8h+arg_0]
0x1800141f7  add     rsp, 90h
0x1800141fe  pop     r15
0x180014200  pop     r14
0x180014202  pop     r13
0x180014204  pop     r12
0x180014206  pop     rdi
0x180014207  pop     rsi
0x180014208  pop     rbx
0x180014209  retn
0x18001420a  mov     r9d, eax; char *
0x18001420d  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014214  mov     edx, 1CBEh; void *
0x180014219  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
