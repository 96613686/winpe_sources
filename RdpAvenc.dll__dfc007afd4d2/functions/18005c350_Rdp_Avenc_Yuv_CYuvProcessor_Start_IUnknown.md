# Rdp::Avenc::Yuv::CYuvProcessor::Start(IUnknown *)

- ea: `0x18005c350`
- end: `0x18005c764`
- name: `?Start@CYuvProcessor@Yuv@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(Rdp::Avenc::Yuv::CYuvProcessor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003c64`
- `0x18000e848`
- `0x18000ec04`
- `0x180011490`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x1800153f8`
- `0x180015480`
- `0x1800183fc`
- `0x18005a918`
- `0x18005c350`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c3b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c703`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c3b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005c703`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c6c2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18005c6c2`

## string_xrefs

- `0x18005c40e`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18005c4d3`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18005c51b`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18005c54f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18005c751`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Rdp::Avenc::Yuv::CYuvProcessor::Start(Rdp::Avenc::Yuv::CYuvProcessor *this, struct IUnknown *a2)
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
  HLOCAL v13; // rax
  HLOCAL v14; // rcx
  __int64 v15; // rdx
  unsigned int Guid; // eax
  unsigned int *v17; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v19; // rdx
  struct _LUID *v20; // r9
  unsigned int Luid; // eax
  int v22; // r8d
  int v23; // r9d
  WCHAR **v24; // rax
  void *v25; // rdx
  const char *v26; // r9
  bool v27; // di
  char v28; // al
  int v29; // r8d
  int v30; // edx
  __int64 result; // rax
  int v32; // [rsp+20h] [rbp-A8h]
  int v33; // [rsp+20h] [rbp-A8h]
  int v34; // [rsp+28h] [rbp-A0h]
  char *v35; // [rsp+28h] [rbp-A0h]
  char *v36; // [rsp+28h] [rbp-A0h]
  int v37; // [rsp+28h] [rbp-A0h]
  const char *v38; // [rsp+60h] [rbp-68h] BYREF
  const char *v39; // [rsp+68h] [rbp-60h] BYREF
  int v40[2]; // [rsp+70h] [rbp-58h] BYREF
  struct _tagpropertykey v41; // [rsp+78h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  HLOCAL hMem; // [rsp+D0h] [rbp+8h] BYREF
  __int64 v44; // [rsp+D8h] [rbp+10h] BYREF
  const char *v45; // [rsp+E0h] [rbp+18h] BYREF
  int *v46; // [rsp+E8h] [rbp+20h] BYREF

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
      v32,
      v34,
      10,
      &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
      CurrentThreadId);
  }
  v10 = (Rdp::Utils::Props **)((char *)this + 24);
  try
  {
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      196,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      2147549183LL);
    hMem = 0;
    v11 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, HLOCAL *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
            &hMem);
    if ( v11 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v11,
        (_DWORD)this + 24);
    v13 = hMem;
    v14 = 0;
    hMem = 0;
    v15 = *((_QWORD *)this + 4);
    *((_QWORD *)this + 4) = v13;
    if ( v15 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
      v14 = hMem;
    }
    if ( v14 )
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)v14 + 16LL))(v14);
    v41.fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v10, (struct IPropertyStore *)&PKEY_Activity_Id, &v41, v12);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v41.fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v10,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)((char *)this + 72),
               v17);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v35);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(
             *v10,
             v19,
             (const struct _tagpropertykey *)((char *)this + 64),
             v20);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v36);
    *((_BYTE *)this + 168) = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v44 = *((_QWORD *)this + 8);
      LODWORD(hMem) = *((_DWORD *)this + 18);
      v45 = "Start Yuv processor";
      v46 = &xmmword_1800C21A0;
      v38 = "DirectStreamMedia_Driver";
      v39 = "RdpAvenc";
      *(_QWORD *)v40 = 0x1000000;
      *(_QWORD *)&v41.fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)byte_1800B3F91,
        v22,
        v23,
        (__int64)&v41,
        (__int64)v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)&v46,
        (__int64)&v45,
        (__int64)&hMem,
        (__int64)&v44);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"YuvProcessorStart",
      "Rdp::Avenc::Yuv::CYuvProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
      0x3Eu);
    v24 = (WCHAR **)Rdp::Security::CreateTermsrvSid(&hMem);
    Rdp::Security::GrantProcessAccessPermissions(*v24, v25);
    if ( hMem )
      LocalFree(hMem);
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v27 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v28 = GetCurrentThreadId();
      LOBYTE(v29) = v27;
      LOBYTE(v30) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v30,
        v29,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v33,
        v37,
        11,
        &WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids,
        v28);
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x48,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\yuvprocessor\\yuvprocessor.cpp",
                           v26);
  }
  return result;
}

```

## disassembly

```asm
0x18005c350  push    rbx
0x18005c352  push    rsi
0x18005c353  push    rdi
0x18005c354  push    r12
0x18005c356  push    r14
0x18005c358  push    r15
0x18005c35a  sub     rsp, 98h
0x18005c361  mov     r15, rdx
0x18005c364  mov     rdi, rcx
0x18005c367  lea     rcx, WPP_GLOBAL_Control
0x18005c36e  mov     rax, cs:WPP_GLOBAL_Control
0x18005c375  mov     bl, 1
0x18005c377  cmp     rax, rcx
0x18005c37a  jz      short loc_18005C38C
0x18005c37c  test    [rax+1Ch], bl
0x18005c37f  jz      short loc_18005C38C
0x18005c381  cmp     byte ptr [rax+19h], 4
0x18005c385  jb      short loc_18005C38C
0x18005c387  mov     sil, bl
0x18005c38a  jmp     short loc_18005C38F
0x18005c38c  xor     sil, sil
0x18005c38f  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c396  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c39d  setnz   r14b
0x18005c3a1  test    sil, sil
0x18005c3a4  jnz     short loc_18005C3B4
0x18005c3a6  test    r14b, r14b
0x18005c3a9  jnz     short loc_18005C3B4
0x18005c3ab  lea     r12, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005c3b2  jmp     short loc_18005C3EB
0x18005c3b4  call    cs:__imp_GetCurrentThreadId
0x18005c3ba  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18005c3be  lea     r12, WPP_ad6665f7b8be3bbcc1289583115d6a25_Traceguids
0x18005c3c5  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x18005c3ca  mov     [rsp+0C8h+var_98], 0Ah; __int16
0x18005c3d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c3d8  mov     r9, [rcx+28h]; int
0x18005c3dc  mov     r8b, r14b; int
0x18005c3df  mov     dl, sil; int
0x18005c3e2  mov     rcx, [rcx+10h]; int
0x18005c3e6  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005c3eb  lea     rsi, [rdi+18h]
0x18005c3ef  mov     rcx, [rsp+0C8h]
0x18005c3f7  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x18005c3fe  mov     [rsp+0C8h+var_A0], rax; char *
0x18005c403  mov     qword ptr [rsp+0C8h+var_A8], rsi; int
0x18005c408  mov     r9d, 8000FFFFh
0x18005c40e  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c415  mov     edx, 0C4h
0x18005c41a  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18005c41f  mov     [rsp+0C8h+hMem], 0
0x18005c42b  mov     rax, [r15]
0x18005c42e  lea     r8, [rsp+0C8h+hMem]
0x18005c436  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x18005c43d  mov     rcx, r15
0x18005c440  mov     rax, [rax]
0x18005c443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c448  mov     rcx, [rsp+0C8h]; this
0x18005c450  test    eax, eax
0x18005c452  js      loc_18005C74E
0x18005c458  mov     rax, [rsp+0C8h+hMem]
0x18005c460  xor     ecx, ecx
0x18005c462  mov     [rsp+0C8h+hMem], rcx
0x18005c46a  mov     rdx, [rdi+20h]
0x18005c46e  mov     [rdi+20h], rax
0x18005c472  test    rdx, rdx
0x18005c475  jz      short loc_18005C48E
0x18005c477  mov     rax, [rdx]
0x18005c47a  mov     rcx, rdx
0x18005c47d  mov     rax, [rax+10h]
0x18005c481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c486  mov     rcx, [rsp+0C8h+hMem]
0x18005c48e  test    rcx, rcx
0x18005c491  jz      short loc_18005C4A0
0x18005c493  mov     rax, [rcx]
0x18005c496  mov     rax, [rax+10h]
0x18005c49a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c49f  nop
0x18005c4a0  xorps   xmm0, xmm0
0x18005c4a3  movups  xmmword ptr [rsp+0C8h+var_50.fmtid.Data1], xmm0
0x18005c4a8  lea     r8, [rsp+0C8h+var_50]; struct _tagpropertykey *
0x18005c4ad  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x18005c4b4  mov     rcx, [rsi]; this
0x18005c4b7  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18005c4bc  mov     rcx, [rsp+0C8h]; this
0x18005c4c4  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x18005c4cb  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x18005c4d0  mov     r9d, eax; char *
0x18005c4d3  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c4da  mov     edx, 0D1h; void *
0x18005c4df  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005c4e4  movups  xmm0, xmmword ptr [rsp+0C8h+var_50.fmtid.Data1]
0x18005c4e9  movdqu  cs:xmmword_1800C21A0, xmm0
0x18005c4f1  lea     r8, [rdi+48h]; struct _tagpropertykey *
0x18005c4f5  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x18005c4fc  mov     rcx, [rsi]; this
0x18005c4ff  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18005c504  mov     rcx, [rsp+0C8h]; this
0x18005c50c  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x18005c513  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x18005c518  mov     r9d, eax; char *
0x18005c51b  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c522  mov     edx, 0DDh; void *
0x18005c527  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005c52c  lea     r8, [rdi+40h]; struct _tagpropertykey *
0x18005c530  mov     rcx, [rsi]; this
0x18005c533  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x18005c538  mov     rcx, [rsp+0C8h]; this
0x18005c540  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x18005c547  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x18005c54c  mov     r9d, eax; char *
0x18005c54f  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c556  mov     edx, 0E7h; void *
0x18005c55b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18005c560  mov     [rdi+0A8h], bl
0x18005c566  mov     eax, cs:dword_1800C1058
0x18005c56c  cmp     eax, 4
0x18005c56f  jbe     loc_18005C675
0x18005c575  mov     rcx, cs:qword_1800C1070
0x18005c57c  mov     rax, cs:qword_1800C1068
0x18005c583  mov     rdx, 470000000000h
0x18005c58d  test    rdx, rax
0x18005c590  jz      loc_18005C675
0x18005c596  mov     rax, rcx
0x18005c599  and     rax, rdx
0x18005c59c  cmp     rax, rcx
0x18005c59f  jnz     loc_18005C675
0x18005c5a5  mov     rax, [rdi+40h]
0x18005c5a9  mov     [rsp+0C8h+arg_8], rax
0x18005c5b1  mov     eax, [rdi+48h]
0x18005c5b4  mov     dword ptr [rsp+0C8h+hMem], eax
0x18005c5bb  lea     rax, aStartYuvProces; "Start Yuv processor"
0x18005c5c2  mov     [rsp+0C8h+arg_10], rax
0x18005c5ca  lea     rax, xmmword_1800C21A0
0x18005c5d1  mov     [rsp+0C8h+arg_18], rax
0x18005c5d9  lea     rax, aDirectstreamme_0; "DirectStreamMedia_Driver"
0x18005c5e0  mov     [rsp+0C8h+var_68], rax
0x18005c5e5  lea     rax, aRdpavenc; "RdpAvenc"
0x18005c5ec  mov     [rsp+0C8h+var_60], rax
0x18005c5f1  mov     qword ptr [rsp+0C8h+var_58], 1000000h
0x18005c5fa  lea     rax, aCheckpoint; "Checkpoint"
0x18005c601  mov     qword ptr [rsp+0C8h+var_50.fmtid.Data1], rax
0x18005c606  lea     rax, [rsp+0C8h+arg_8]
0x18005c60e  mov     [rsp+0C8h+var_70], rax
0x18005c613  lea     rax, [rsp+0C8h+hMem]
0x18005c61b  mov     [rsp+0C8h+var_78], rax
0x18005c620  lea     rax, [rsp+0C8h+arg_10]
0x18005c628  mov     [rsp+0C8h+var_80], rax
0x18005c62d  lea     rax, [rsp+0C8h+arg_18]
0x18005c635  mov     qword ptr [rsp+0C8h+var_88], rax
0x18005c63a  lea     rax, [rsp+0C8h+var_68]
0x18005c63f  mov     [rsp+0C8h+MessageGuid], rax
0x18005c644  lea     rax, [rsp+0C8h+var_60]
0x18005c649  mov     qword ptr [rsp+0C8h+var_98], rax
0x18005c64e  lea     rax, [rsp+0C8h+var_58]
0x18005c653  mov     [rsp+0C8h+var_A0], rax; int
0x18005c658  lea     rax, [rsp+0C8h+var_50]
0x18005c65d  mov     qword ptr [rsp+0C8h+var_A8], rax
0x18005c662  lea     rdx, byte_1800B3F91
0x18005c669  lea     rcx, dword_1800C1058
0x18005c670  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18005c675  mov     [rsp+0C8h+var_A8], 3Eh ; '>'; int
0x18005c67d  lea     r9, aOnecoreuapTerm_33; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18005c684  lea     r8, aRdpAvencYuvCyu_7; "Rdp::Avenc::Yuv::CYuvProcessor::Start"
0x18005c68b  lea     rdx, aYuvprocessorst; "YuvProcessorStart"
0x18005c692  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18005c699  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18005c69e  lea     rcx, [rsp+0C8h+hMem]; pSid
0x18005c6a6  call    ?CreateTermsrvSid@Security@Rdp@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@XZ; Rdp::Security::CreateTermsrvSid(void)
0x18005c6ab  nop
0x18005c6ac  mov     rcx, [rax]; this
0x18005c6af  call    ?GrantProcessAccessPermissions@Security@Rdp@@YAXPEAXK@Z; Rdp::Security::GrantProcessAccessPermissions(void *,ulong)
0x18005c6b4  nop
0x18005c6b5  mov     rcx, [rsp+0C8h+hMem]; hMem
0x18005c6bd  test    rcx, rcx
0x18005c6c0  jz      short loc_18005C6C8
0x18005c6c2  call    cs:__imp_LocalFree
0x18005c6c8  mov     rax, cs:WPP_GLOBAL_Control
0x18005c6cf  lea     rcx, WPP_GLOBAL_Control
0x18005c6d6  cmp     rax, rcx
0x18005c6d9  jz      short loc_18005C6E6
0x18005c6db  test    [rax+1Ch], bl
0x18005c6de  jz      short loc_18005C6E6
0x18005c6e0  cmp     byte ptr [rax+19h], 4
0x18005c6e4  jnb     short loc_18005C6E8
0x18005c6e6  xor     bl, bl
0x18005c6e8  lea     rax, WPP_RECORDER_INITIALIZED
0x18005c6ef  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005c6f6  setnz   dil
0x18005c6fa  test    bl, bl
0x18005c6fc  jnz     short loc_18005C703
0x18005c6fe  test    dil, dil
0x18005c701  jz      short loc_18005C732
0x18005c703  call    cs:__imp_GetCurrentThreadId
0x18005c709  mov     dword ptr [rsp+0C8h+var_88], eax; char
0x18005c70d  mov     [rsp+0C8h+MessageGuid], r12; MessageGuid
0x18005c712  mov     [rsp+0C8h+var_98], 0Bh; __int16
0x18005c719  mov     rcx, cs:WPP_GLOBAL_Control
0x18005c720  mov     r9, [rcx+28h]; int
0x18005c724  mov     r8b, dil; int
0x18005c727  mov     dl, bl; int
0x18005c729  mov     rcx, [rcx+10h]; int
0x18005c72d  call    WPP_RECORDER_AND_TRACE_SF_D
0x18005c732  xor     eax, eax
0x18005c734  jmp     short loc_18005C73D
0x18005c736  mov     eax, dword ptr [rsp+0C8h+hMem]
0x18005c73d  add     rsp, 98h
0x18005c744  pop     r15
0x18005c746  pop     r14
0x18005c748  pop     r12
0x18005c74a  pop     rdi
0x18005c74b  pop     rsi
0x18005c74c  pop     rbx
0x18005c74d  retn
0x18005c74e  mov     r9d, eax; char *
0x18005c751  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005c758  mov     edx, 1CBEh; void *
0x18005c75d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
