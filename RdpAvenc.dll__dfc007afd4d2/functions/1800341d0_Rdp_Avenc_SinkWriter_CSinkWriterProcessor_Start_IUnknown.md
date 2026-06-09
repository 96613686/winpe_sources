# Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Start(IUnknown *)

- ea: `0x1800341d0`
- end: `0x1800345a4`
- name: `?Start@CSinkWriterProcessor@SinkWriter@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `980`
- prototype: `__int64 __fastcall(Rdp::Avenc::SinkWriter::CSinkWriterProcessor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800019f0`
- `0x18000e848`
- `0x18000ec04`
- `0x180011490`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x1800153f8`
- `0x180015480`
- `0x1800341d0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034234`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034234`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034543`

## string_xrefs

- `0x18003428e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180034353`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18003439b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x1800343cf`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180034591`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003443b`: `Start SinkWriter processor`
- `0x1800344e7`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\sinkwriterprocessor\sinkwriterprocessor.cpp`
- `0x1800344ee`: `Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Start`
- `0x1800344f5`: `SinkWriterProcessorStart`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Start(
        Rdp::Avenc::SinkWriter::CSinkWriterProcessor *this,
        struct IUnknown *a2)
{
  char v4; // bl
  bool v5; // si
  bool v6; // r14
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  Rdp::Utils::Props **v10; // rsi
  int v11; // eax
  struct _GUID *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  unsigned int Guid; // eax
  unsigned int *v17; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v19; // rdx
  struct _LUID *v20; // r9
  unsigned int Luid; // eax
  int v22; // r8d
  int v23; // r9d
  const char *v24; // r9
  bool v25; // di
  char v26; // al
  int v27; // r8d
  int v28; // edx
  __int64 result; // rax
  int v30; // [rsp+20h] [rbp-98h]
  int v31; // [rsp+20h] [rbp-98h]
  int v32; // [rsp+28h] [rbp-90h]
  char *v33; // [rsp+28h] [rbp-90h]
  char *v34; // [rsp+28h] [rbp-90h]
  int v35; // [rsp+28h] [rbp-90h]
  const char *v36; // [rsp+60h] [rbp-58h] BYREF
  int v37[2]; // [rsp+68h] [rbp-50h] BYREF
  struct _tagpropertykey v38; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]
  __int64 v40; // [rsp+C0h] [rbp+8h] BYREF
  __int64 v41; // [rsp+C8h] [rbp+10h] BYREF
  const char *v42; // [rsp+D0h] [rbp+18h] BYREF
  int *v43; // [rsp+D8h] [rbp+20h] BYREF

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
      v30,
      v32,
      10,
      &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
      CurrentThreadId);
  }
  try
  {
    v10 = (Rdp::Utils::Props **)((char *)this + 32);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      196,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      2147549183LL);
    v40 = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
            &v40);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        (_DWORD)this + 32);
    v13 = v40;
    v14 = 0;
    v40 = 0;
    v15 = *((_QWORD *)this + 5);
    *((_QWORD *)this + 5) = v13;
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v14 = v40;
    }
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v38.fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v10, (struct IPropertyStore *)&PKEY_Activity_Id, &v38, v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v38.fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v10,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)this + 4,
               v17);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v33);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(
             *v10,
             v19,
             (const struct _tagpropertykey *)((char *)this + 72),
             v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v34);
    *((_BYTE *)this + 176) = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v41 = *((_QWORD *)this + 9);
      LODWORD(v40) = *((_DWORD *)this + 20);
      v42 = "Start SinkWriter processor";
      v43 = &xmmword_1800C21A0;
      v36 = "RdpAvenc";
      *(_QWORD *)v37 = 0x1000000;
      *(_QWORD *)&v38.fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800AEF21,
        v22,
        v23,
        (__int64)&v38,
        (__int64)v37,
        (__int64)&v36,
        (__int64)&v43,
        (__int64)&v42,
        (__int64)&v40,
        (__int64)&v41);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"SinkWriterProcessorStart",
      "Rdp::Avenc::SinkWriter::CSinkWriterProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
      0x3Eu);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v25 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v26 = GetCurrentThreadId();
      LOBYTE(v27) = v25;
      LOBYTE(v28) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v28,
        v27,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v31,
        v35,
        11,
        &WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids,
        v26);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x43,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\sinkwriterprocessor\\sinkwriterprocessor.cpp",
                           v24);
  }
  return result;
}

```

## disassembly

```asm
0x1800341d0  push    rbx
0x1800341d2  push    rsi
0x1800341d3  push    rdi
0x1800341d4  push    r12
0x1800341d6  push    r14
0x1800341d8  push    r15
0x1800341da  sub     rsp, 88h
0x1800341e1  mov     r15, rdx
0x1800341e4  mov     rdi, rcx
0x1800341e7  lea     rcx, WPP_GLOBAL_Control
0x1800341ee  mov     rax, cs:WPP_GLOBAL_Control
0x1800341f5  mov     bl, 1
0x1800341f7  cmp     rax, rcx
0x1800341fa  jz      short loc_18003420C
0x1800341fc  test    [rax+1Ch], bl
0x1800341ff  jz      short loc_18003420C
0x180034201  cmp     byte ptr [rax+19h], 4
0x180034205  jb      short loc_18003420C
0x180034207  mov     sil, bl
0x18003420a  jmp     short loc_18003420F
0x18003420c  xor     sil, sil
0x18003420f  lea     rax, WPP_RECORDER_INITIALIZED
0x180034216  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003421d  setnz   r14b
0x180034221  test    sil, sil
0x180034224  jnz     short loc_180034234
0x180034226  test    r14b, r14b
0x180034229  jnz     short loc_180034234
0x18003422b  lea     r12, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x180034232  jmp     short loc_18003426B
0x180034234  call    cs:__imp_GetCurrentThreadId
0x18003423a  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003423e  lea     r12, WPP_f1a190f3335e3be81643dcf04f2aa623_Traceguids
0x180034245  mov     [rsp+0B8h+MessageGuid], r12; MessageGuid
0x18003424a  mov     [rsp+0B8h+var_88], 0Ah; __int16
0x180034251  mov     rcx, cs:WPP_GLOBAL_Control
0x180034258  mov     r9, [rcx+28h]; int
0x18003425c  mov     r8b, r14b; int
0x18003425f  mov     dl, sil; int
0x180034262  mov     rcx, [rcx+10h]; int
0x180034266  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003426b  lea     rsi, [rdi+20h]
0x18003426f  mov     rcx, [rsp+0B8h]
0x180034277  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x18003427e  mov     [rsp+0B8h+var_90], rax; char *
0x180034283  mov     qword ptr [rsp+0B8h+var_98], rsi; int
0x180034288  mov     r9d, 8000FFFFh
0x18003428e  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180034295  mov     edx, 0C4h
0x18003429a  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18003429f  mov     [rsp+0B8h+arg_0], 0
0x1800342ab  mov     rax, [r15]
0x1800342ae  lea     r8, [rsp+0B8h+arg_0]
0x1800342b6  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x1800342bd  mov     rcx, r15
0x1800342c0  mov     rax, [rax]
0x1800342c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800342c8  mov     rcx, [rsp+0B8h]; this
0x1800342d0  test    eax, eax
0x1800342d2  js      loc_18003458E
0x1800342d8  mov     rax, [rsp+0B8h+arg_0]
0x1800342e0  xor     ecx, ecx
0x1800342e2  mov     [rsp+0B8h+arg_0], rcx
0x1800342ea  mov     rdx, [rdi+28h]
0x1800342ee  mov     [rdi+28h], rax
0x1800342f2  test    rdx, rdx
0x1800342f5  jz      short loc_18003430E
0x1800342f7  mov     rax, [rdx]
0x1800342fa  mov     rcx, rdx
0x1800342fd  mov     rax, [rax+10h]
0x180034301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034306  mov     rcx, [rsp+0B8h+arg_0]
0x18003430e  test    rcx, rcx
0x180034311  jz      short loc_180034320
0x180034313  mov     rax, [rcx]
0x180034316  mov     rax, [rax+10h]
0x18003431a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003431f  nop
0x180034320  xorps   xmm0, xmm0
0x180034323  movups  xmmword ptr [rsp+0B8h+var_48.fmtid.Data1], xmm0
0x180034328  lea     r8, [rsp+0B8h+var_48]; struct _tagpropertykey *
0x18003432d  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x180034334  mov     rcx, [rsi]; this
0x180034337  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18003433c  mov     rcx, [rsp+0B8h]; this
0x180034344  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x18003434b  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180034350  mov     r9d, eax; char *
0x180034353  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003435a  mov     edx, 0D1h; void *
0x18003435f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180034364  movups  xmm0, xmmword ptr [rsp+0B8h+var_48.fmtid.Data1]
0x180034369  movdqu  cs:xmmword_1800C21A0, xmm0
0x180034371  lea     r8, [rdi+50h]; struct _tagpropertykey *
0x180034375  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x18003437c  mov     rcx, [rsi]; this
0x18003437f  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180034384  mov     rcx, [rsp+0B8h]; this
0x18003438c  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x180034393  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x180034398  mov     r9d, eax; char *
0x18003439b  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800343a2  mov     edx, 0DDh; void *
0x1800343a7  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800343ac  lea     r8, [rdi+48h]; struct _tagpropertykey *
0x1800343b0  mov     rcx, [rsi]; this
0x1800343b3  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x1800343b8  mov     rcx, [rsp+0B8h]; this
0x1800343c0  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x1800343c7  mov     qword ptr [rsp+0B8h+var_98], rdx; int
0x1800343cc  mov     r9d, eax; char *
0x1800343cf  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800343d6  mov     edx, 0E7h; void *
0x1800343db  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800343e0  mov     [rdi+0B0h], bl
0x1800343e6  mov     eax, cs:dword_1800C1058
0x1800343ec  cmp     eax, 4
0x1800343ef  jbe     loc_1800344DF
0x1800343f5  mov     rcx, cs:qword_1800C1070
0x1800343fc  mov     rax, cs:qword_1800C1068
0x180034403  mov     rdx, 470000000000h
0x18003440d  test    rdx, rax
0x180034410  jz      loc_1800344DF
0x180034416  mov     rax, rcx
0x180034419  and     rax, rdx
0x18003441c  cmp     rax, rcx
0x18003441f  jnz     loc_1800344DF
0x180034425  mov     rax, [rdi+48h]
0x180034429  mov     [rsp+0B8h+arg_8], rax
0x180034431  mov     eax, [rdi+50h]
0x180034434  mov     dword ptr [rsp+0B8h+arg_0], eax
0x18003443b  lea     rax, aStartSinkwrite_0; "Start SinkWriter processor"
0x180034442  mov     [rsp+0B8h+arg_10], rax
0x18003444a  lea     rax, xmmword_1800C21A0
0x180034451  mov     [rsp+0B8h+arg_18], rax
0x180034459  lea     rax, aRdpavenc; "RdpAvenc"
0x180034460  mov     [rsp+0B8h+var_58], rax
0x180034465  mov     qword ptr [rsp+0B8h+var_50], 1000000h
0x18003446e  lea     rax, aCheckpoint; "Checkpoint"
0x180034475  mov     qword ptr [rsp+0B8h+var_48.fmtid.Data1], rax
0x18003447a  lea     rax, [rsp+0B8h+arg_8]
0x180034482  mov     [rsp+0B8h+var_68], rax
0x180034487  lea     rax, [rsp+0B8h+arg_0]
0x18003448f  mov     [rsp+0B8h+var_70], rax
0x180034494  lea     rax, [rsp+0B8h+arg_10]
0x18003449c  mov     qword ptr [rsp+0B8h+var_78], rax
0x1800344a1  lea     rax, [rsp+0B8h+arg_18]
0x1800344a9  mov     [rsp+0B8h+MessageGuid], rax
0x1800344ae  lea     rax, [rsp+0B8h+var_58]
0x1800344b3  mov     qword ptr [rsp+0B8h+var_88], rax
0x1800344b8  lea     rax, [rsp+0B8h+var_50]
0x1800344bd  mov     [rsp+0B8h+var_90], rax; int
0x1800344c2  lea     rax, [rsp+0B8h+var_48]
0x1800344c7  mov     qword ptr [rsp+0B8h+var_98], rax
0x1800344cc  lea     rdx, byte_1800AEF21
0x1800344d3  lea     rcx, dword_1800C1058
0x1800344da  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800344df  mov     [rsp+0B8h+var_98], 3Eh ; '>'; int
0x1800344e7  lea     r9, aOnecoreuapTerm_30; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800344ee  lea     r8, aRdpAvencSinkwr_9; "Rdp::Avenc::SinkWriter::CSinkWriterProc"...
0x1800344f5  lea     rdx, aSinkwriterproc; "SinkWriterProcessorStart"
0x1800344fc  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180034503  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180034508  mov     rax, cs:WPP_GLOBAL_Control
0x18003450f  lea     rcx, WPP_GLOBAL_Control
0x180034516  cmp     rax, rcx
0x180034519  jz      short loc_180034526
0x18003451b  test    [rax+1Ch], bl
0x18003451e  jz      short loc_180034526
0x180034520  cmp     byte ptr [rax+19h], 4
0x180034524  jnb     short loc_180034528
0x180034526  xor     bl, bl
0x180034528  lea     rax, WPP_RECORDER_INITIALIZED
0x18003452f  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180034536  setnz   dil
0x18003453a  test    bl, bl
0x18003453c  jnz     short loc_180034543
0x18003453e  test    dil, dil
0x180034541  jz      short loc_180034572
0x180034543  call    cs:__imp_GetCurrentThreadId
0x180034549  mov     dword ptr [rsp+0B8h+var_78], eax; char
0x18003454d  mov     [rsp+0B8h+MessageGuid], r12; MessageGuid
0x180034552  mov     [rsp+0B8h+var_88], 0Bh; __int16
0x180034559  mov     rcx, cs:WPP_GLOBAL_Control
0x180034560  mov     r9, [rcx+28h]; int
0x180034564  mov     r8b, dil; int
0x180034567  mov     dl, bl; int
0x180034569  mov     rcx, [rcx+10h]; int
0x18003456d  call    WPP_RECORDER_AND_TRACE_SF_D
0x180034572  xor     eax, eax
0x180034574  jmp     short loc_18003457D
0x180034576  mov     eax, dword ptr [rsp+0B8h+arg_0]
0x18003457d  add     rsp, 88h
0x180034584  pop     r15
0x180034586  pop     r14
0x180034588  pop     r12
0x18003458a  pop     rdi
0x18003458b  pop     rsi
0x18003458c  pop     rbx
0x18003458d  retn
0x18003458e  mov     r9d, eax; char *
0x180034591  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180034598  mov     edx, 1CBEh; void *
0x18003459d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
