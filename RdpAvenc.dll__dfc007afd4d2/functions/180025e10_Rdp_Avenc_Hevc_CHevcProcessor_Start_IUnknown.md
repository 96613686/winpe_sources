# Rdp::Avenc::Hevc::CHevcProcessor::Start(IUnknown *)

- ea: `0x180025e10`
- end: `0x180026408`
- name: `?Start@CHevcProcessor@Hevc@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `1528`
- prototype: `int(Rdp::Avenc::Hevc::CHevcProcessor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x1800019f0`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x180010bc8`
- `0x180011490`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x1800153f8`
- `0x180015480`
- `0x180025e10`
- `0x1800273e8`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180026313`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180026313`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800262f0`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x1800262f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025e79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026377`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800261fb`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x1800261fb`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800263a7`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800263a7`
- `MFPlat!MFRegisterPlatformWithMMCSS` at `0x18002626c`
- `MFPlat!MFRegisterPlatformWithMMCSS` at `0x18002626c`

## string_xrefs

- `0x180025ed7`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x180025f9f`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x1800263ce`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800263e2`: `onecoreuap\termsrv\rdp_bin\win\common/inc/ComObject.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Rdp::Avenc::Hevc::CHevcProcessor::Start(Rdp::Avenc::Hevc::CHevcProcessor *this, struct IUnknown *a2)
{
  char v4; // bl
  char v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  char *v10; // rdi
  Rdp::Utils::Props **v11; // rsi
  int v12; // eax
  struct _GUID *v13; // r9
  _QWORD *v14; // rax
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  unsigned int Guid; // eax
  unsigned int *v18; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v20; // rdx
  struct _LUID *v21; // r9
  unsigned int Luid; // eax
  int v23; // r8d
  int v24; // r9d
  _DWORD *v25; // rax
  volatile signed __int32 *v26; // rsi
  HRESULT v27; // eax
  unsigned int v28; // eax
  unsigned int v29; // eax
  _QWORD *v30; // rax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int v33; // ecx
  int v34; // eax
  bool v35; // di
  char v36; // al
  int v37; // r8d
  int v38; // edx
  const char *v39; // r9
  __int64 result; // rax
  int v41; // [rsp+20h] [rbp-B8h]
  int v42; // [rsp+20h] [rbp-B8h]
  int v43; // [rsp+28h] [rbp-B0h]
  char *v44; // [rsp+28h] [rbp-B0h]
  char *v45; // [rsp+28h] [rbp-B0h]
  char *v46; // [rsp+28h] [rbp-B0h]
  char *v47; // [rsp+28h] [rbp-B0h]
  int *v48; // [rsp+60h] [rbp-78h] BYREF
  const char *v49; // [rsp+68h] [rbp-70h] BYREF
  char v50[8]; // [rsp+70h] [rbp-68h] BYREF
  struct _tagpropertykey v51; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]
  _QWORD *v53; // [rsp+E0h] [rbp+8h] BYREF
  DWORD pdwTaskId; // [rsp+E8h] [rbp+10h] BYREF
  __int64 v55; // [rsp+F0h] [rbp+18h] BYREF
  const char *v56; // [rsp+F8h] [rbp+20h] BYREF

  v4 = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v5 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    v5 = 0;
  }
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
      v41,
      v43,
      10,
      &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
      CurrentThreadId);
  }
  v10 = (char *)this - 80;
  v11 = (Rdp::Utils::Props **)((char *)this + 32);
  try
  {
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      196,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      2147549183LL);
    v53 = 0;
    v12 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, _QWORD **))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
            &v53);
    if ( v12 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v12,
        (_DWORD)this - 80 + 112);
    v14 = v53;
    v15 = 0;
    v53 = 0;
    v16 = *((_QWORD *)v10 + 15);
    *((_QWORD *)v10 + 15) = v14;
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
      v15 = v53;
    }
    if ( v15 )
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    v51.fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v11, (struct IPropertyStore *)&PKEY_Activity_Id, &v51, v13);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v51.fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v11,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)v10 + 8,
               v18);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v44);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(*v11, v20, (const struct _tagpropertykey *)(v10 + 152), v21);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v45);
    v10[256] = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      v55 = *((_QWORD *)this + 9);
      LODWORD(v53) = *((_DWORD *)this + 20);
      v56 = "Start Hevc processor";
      v48 = &xmmword_1800C21A0;
      v49 = "RdpAvenc";
      *(_QWORD *)v50 = 0x1000000;
      *(_QWORD *)&v51.fmtid.Data1 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (unsigned int)&dword_1800C1058,
        (unsigned int)&word_1800ADF16,
        v23,
        v24,
        (__int64)&v51,
        (__int64)v50,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v56,
        (__int64)&v53,
        (__int64)&v55);
    }
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"HevcProcessorStart",
      "Rdp::Avenc::Hevc::CHevcProcessor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
      0x3Bu);
    v25 = operator new(0x58u);
    v25[2] = 1;
    v25[3] = 1;
    *(_QWORD *)v25 = &std::_Ref_count_obj2<Rdp::Avenc::Hevc::CMFApi>::`vftable';
    *((_QWORD *)v25 + 2) = 0;
    *((_QWORD *)v25 + 3) = 0;
    *((_QWORD *)v25 + 4) = 0;
    *((_QWORD *)v25 + 6) = 0;
    *((_QWORD *)v25 + 7) = 0;
    *((_QWORD *)v25 + 8) = 0;
    *((_QWORD *)v25 + 9) = 0;
    *((_QWORD *)v25 + 10) = 0;
    *((_QWORD *)this + 31) = v25 + 4;
    v26 = (volatile signed __int32 *)*((_QWORD *)this + 32);
    *((_QWORD *)this + 32) = v25;
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    Rdp::Avenc::Hevc::CMFApi::Init(*((Rdp::Avenc::Hevc::CMFApi **)this + 31));
    v27 = CoInitializeEx(0, 0);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x18,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/ComObject.h",
        (const char *)(unsigned int)v27,
        v42);
    v28 = (**((__int64 (__fastcall ***)(__int64, _QWORD))this + 31))(131184, 0);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
      (const char *)v28,
      (int)"CMFStartup failed. Cannot use HEVC encoding",
      v46);
    pdwTaskId = 0;
    v29 = MFRegisterPlatformWithMMCSS(L"Playback", &pdwTaskId, -2);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
      (const char *)v29,
      (int)"MFRegisterPlatformWithMMCSS failed. Cannot use HEVC encoding",
      v47);
    v10[520] = 1;
    v30 = operator new(0x18u);
    *v30 = v10;
    v30[1] = Rdp::Avenc::Hevc::CHevcProcessor::PacketWriterThreadProc;
    *((_DWORD *)v30 + 4) = 0;
    *((_DWORD *)v30 + 5) = *(_DWORD *)&v51.fmtid.Data4[4];
    v53 = v30;
    v31 = _o__beginthreadex(
            0,
            0,
            std::thread::_Invoke<std::tuple<void (Rdp::Avenc::RdpProg::CRdpProgProcessor::*)(void),Rdp::Avenc::RdpProg::CRdpProgProcessor *>,0,1>,
            v30);
    *(_QWORD *)&v51.fmtid.Data1 = v31;
    if ( !v31 )
    {
      *(_DWORD *)v51.fmtid.Data4 = 0;
      std::_Throw_Cpp_error(6);
    }
    if ( *((_DWORD *)v10 + 90) )
    {
      _o_terminate(v32, v31);
      __debugbreak();
    }
    v33 = *(_DWORD *)v51.fmtid.Data4;
    v34 = *(_DWORD *)&v51.fmtid.Data4[4];
    *((_QWORD *)v10 + 44) = v31;
    *((_DWORD *)v10 + 90) = v33;
    *((_DWORD *)v10 + 91) = v34;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v35 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v36 = GetCurrentThreadId();
      LOBYTE(v37) = v35;
      LOBYTE(v38) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v38,
        v37,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        0,
        (int)v51.fmtid.Data4,
        11,
        &WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids,
        v36);
    }
    CoUninitialize();
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v53) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0x5F,
                     (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\hevcprocessor\\hevcprocessor.cpp",
                     v39);
    return (unsigned int)v53;
  }
  return result;
}

```

## disassembly

```asm
0x180025e10  push    rbx
0x180025e12  push    rsi
0x180025e13  push    rdi
0x180025e14  push    r12
0x180025e16  push    r13
0x180025e18  push    r14
0x180025e1a  push    r15
0x180025e1c  sub     rsp, 0A0h
0x180025e23  mov     r15, rdx
0x180025e26  mov     r14, rcx
0x180025e29  xor     r13d, r13d
0x180025e2c  lea     rcx, WPP_GLOBAL_Control
0x180025e33  mov     rax, cs:WPP_GLOBAL_Control
0x180025e3a  lea     ebx, [r13+1]
0x180025e3e  cmp     rax, rcx
0x180025e41  jz      short loc_180025E51
0x180025e43  test    [rax+1Ch], bl
0x180025e46  jz      short loc_180025E51
0x180025e48  cmp     byte ptr [rax+19h], 4
0x180025e4c  mov     dil, bl
0x180025e4f  jnb     short loc_180025E54
0x180025e51  mov     dil, r13b
0x180025e54  lea     rax, WPP_RECORDER_INITIALIZED
0x180025e5b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180025e62  setnz   sil
0x180025e66  test    dil, dil
0x180025e69  jnz     short loc_180025E79
0x180025e6b  test    sil, sil
0x180025e6e  jnz     short loc_180025E79
0x180025e70  lea     r12, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x180025e77  jmp     short loc_180025EB0
0x180025e79  call    cs:__imp_GetCurrentThreadId
0x180025e7f  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x180025e83  lea     r12, WPP_bcb8ca3ea8623ed87e5640a8139f2dec_Traceguids
0x180025e8a  mov     [rsp+0D8h+MessageGuid], r12; MessageGuid
0x180025e8f  mov     [rsp+0D8h+var_A8], 0Ah; __int16
0x180025e96  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e9d  mov     r9, [rcx+28h]; int
0x180025ea1  mov     r8b, sil; int
0x180025ea4  mov     dl, dil; int
0x180025ea7  mov     rcx, [rcx+10h]; int
0x180025eab  call    WPP_RECORDER_AND_TRACE_SF_D
0x180025eb0  lea     rdi, [r14-50h]
0x180025eb4  lea     rsi, [rdi+70h]
0x180025eb8  mov     rcx, [rsp+0D8h]
0x180025ec0  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x180025ec7  mov     [rsp+0D8h+var_B0], rax; char *
0x180025ecc  mov     qword ptr [rsp+0D8h+var_B8], rsi; int
0x180025ed1  mov     r9d, 8000FFFFh
0x180025ed7  lea     r8, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180025ede  mov     edx, 0C4h
0x180025ee3  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x180025ee8  mov     [rsp+0D8h+arg_0], r13
0x180025ef0  mov     rax, [r15]
0x180025ef3  lea     r8, [rsp+0D8h+arg_0]
0x180025efb  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x180025f02  mov     rcx, r15
0x180025f05  mov     rax, [rax]
0x180025f08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f0d  mov     rcx, [rsp+0D8h]; this
0x180025f15  test    eax, eax
0x180025f17  js      loc_1800263CB
0x180025f1d  mov     rax, [rsp+0D8h+arg_0]
0x180025f25  mov     rcx, r13
0x180025f28  mov     [rsp+0D8h+arg_0], rcx
0x180025f30  mov     rdx, [rdi+78h]
0x180025f34  mov     [rdi+78h], rax
0x180025f38  test    rdx, rdx
0x180025f3b  jz      short loc_180025F54
0x180025f3d  mov     rax, [rdx]
0x180025f40  mov     rcx, rdx
0x180025f43  mov     rax, [rax+10h]
0x180025f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f4c  mov     rcx, [rsp+0D8h+arg_0]
0x180025f54  test    rcx, rcx
0x180025f57  jz      short loc_180025F66
0x180025f59  mov     rax, [rcx]
0x180025f5c  mov     rax, [rax+10h]
0x180025f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f65  nop
0x180025f66  xorps   xmm0, xmm0
0x180025f69  movups  xmmword ptr [rsp+0D8h+var_58.fmtid.Data1], xmm0
0x180025f71  lea     r8, [rsp+0D8h+var_58]; struct _tagpropertykey *
0x180025f79  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x180025f80  mov     rcx, [rsi]; this
0x180025f83  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x180025f88  mov     rcx, [rsp+0D8h]; this
0x180025f90  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x180025f97  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x180025f9c  mov     r9d, eax; char *
0x180025f9f  lea     r15, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180025fa6  mov     r8, r15; unsigned int
0x180025fa9  mov     edx, 0D1h; void *
0x180025fae  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180025fb3  movups  xmm0, xmmword ptr [rsp+0D8h+var_58.fmtid.Data1]
0x180025fbb  movdqu  cs:xmmword_1800C21A0, xmm0
0x180025fc3  lea     r8, [rdi+0A0h]; struct _tagpropertykey *
0x180025fca  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x180025fd1  mov     rcx, [rsi]; this
0x180025fd4  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x180025fd9  mov     rcx, [rsp+0D8h]; this
0x180025fe1  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x180025fe8  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x180025fed  mov     r9d, eax; char *
0x180025ff0  mov     r8, r15; unsigned int
0x180025ff3  mov     edx, 0DDh; void *
0x180025ff8  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180025ffd  lea     r8, [rdi+98h]; struct _tagpropertykey *
0x180026004  mov     rcx, [rsi]; this
0x180026007  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x18002600c  mov     rcx, [rsp+0D8h]; this
0x180026014  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x18002601b  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x180026020  mov     r9d, eax; char *
0x180026023  mov     r8, r15; unsigned int
0x180026026  mov     edx, 0E7h; void *
0x18002602b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180026030  mov     [rdi+100h], bl
0x180026036  mov     eax, cs:dword_1800C1058
0x18002603c  cmp     eax, 4
0x18002603f  jbe     loc_180026130
0x180026045  mov     rcx, cs:qword_1800C1070
0x18002604c  mov     rax, cs:qword_1800C1068
0x180026053  mov     rdx, 470000000000h
0x18002605d  test    rdx, rax
0x180026060  jz      loc_180026130
0x180026066  mov     rax, rcx
0x180026069  and     rax, rdx
0x18002606c  cmp     rax, rcx
0x18002606f  jnz     loc_180026130
0x180026075  mov     rax, [r14+48h]
0x180026079  mov     [rsp+0D8h+arg_10], rax
0x180026081  mov     eax, [r14+50h]
0x180026085  mov     dword ptr [rsp+0D8h+arg_0], eax
0x18002608c  lea     rax, aStartHevcProce; "Start Hevc processor"
0x180026093  mov     [rsp+0D8h+arg_18], rax
0x18002609b  lea     rax, xmmword_1800C21A0
0x1800260a2  mov     [rsp+0D8h+var_78], rax
0x1800260a7  lea     rax, aRdpavenc; "RdpAvenc"
0x1800260ae  mov     [rsp+0D8h+var_70], rax
0x1800260b3  mov     qword ptr [rsp+0D8h+var_68], 1000000h
0x1800260bc  lea     rax, aCheckpoint; "Checkpoint"
0x1800260c3  mov     qword ptr [rsp+0D8h+var_58.fmtid.Data1], rax
0x1800260cb  lea     rax, [rsp+0D8h+arg_10]
0x1800260d3  mov     [rsp+0D8h+var_88], rax
0x1800260d8  lea     rax, [rsp+0D8h+arg_0]
0x1800260e0  mov     [rsp+0D8h+var_90], rax
0x1800260e5  lea     rax, [rsp+0D8h+arg_18]
0x1800260ed  mov     qword ptr [rsp+0D8h+var_98], rax
0x1800260f2  lea     rax, [rsp+0D8h+var_78]
0x1800260f7  mov     [rsp+0D8h+MessageGuid], rax
0x1800260fc  lea     rax, [rsp+0D8h+var_70]
0x180026101  mov     qword ptr [rsp+0D8h+var_A8], rax
0x180026106  lea     rax, [rsp+0D8h+var_68]
0x18002610b  mov     [rsp+0D8h+var_B0], rax; char *
0x180026110  lea     rax, [rsp+0D8h+var_58]
0x180026118  mov     qword ptr [rsp+0D8h+var_B8], rax
0x18002611d  lea     rdx, word_1800ADF16
0x180026124  lea     rcx, dword_1800C1058
0x18002612b  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x180026130  mov     [rsp+0D8h+var_B8], 3Bh ; ';'; int
0x180026138  lea     r9, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18002613f  lea     r8, aRdpAvencHevcCh_2; "Rdp::Avenc::Hevc::CHevcProcessor::Start"
0x180026146  lea     rdx, aHevcprocessors; "HevcProcessorStart"
0x18002614d  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x180026154  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x180026159  mov     ecx, 58h ; 'X'; Size
0x18002615e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026163  mov     [rax+8], ebx
0x180026166  mov     [rax+0Ch], ebx
0x180026169  lea     rcx, ??_7?$_Ref_count_obj2@VCMFApi@Hevc@Avenc@Rdp@@@std@@6B@; const std::_Ref_count_obj2<Rdp::Avenc::Hevc::CMFApi>::`vftable'
0x180026170  mov     [rax], rcx
0x180026173  lea     rcx, [rax+10h]
0x180026177  mov     [rcx], r13
0x18002617a  mov     [rcx+8], r13
0x18002617e  mov     [rcx+10h], r13
0x180026182  mov     [rcx+20h], r13
0x180026186  mov     [rcx+28h], r13
0x18002618a  mov     [rcx+30h], r13
0x18002618e  mov     [rcx+38h], r13
0x180026192  mov     [rcx+40h], r13
0x180026196  mov     [r14+0F8h], rcx
0x18002619d  mov     rsi, [r14+100h]
0x1800261a4  mov     [r14+100h], rax
0x1800261ab  test    rsi, rsi
0x1800261ae  jz      short loc_1800261EB
0x1800261b0  or      r15d, 0FFFFFFFFh
0x1800261b4  mov     eax, r15d
0x1800261b7  lock xadd [rsi+8], eax
0x1800261bc  add     eax, r15d
0x1800261bf  jnz     short loc_1800261EB
0x1800261c1  mov     rax, [rsi]
0x1800261c4  mov     rcx, rsi
0x1800261c7  mov     rax, [rax]
0x1800261ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261cf  mov     eax, r15d
0x1800261d2  lock xadd [rsi+0Ch], eax
0x1800261d7  add     eax, r15d
0x1800261da  jnz     short loc_1800261EB
0x1800261dc  mov     rax, [rsi]
0x1800261df  mov     rcx, rsi
0x1800261e2  mov     rax, [rax+8]
0x1800261e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261eb  mov     rcx, [r14+0F8h]; this
0x1800261f2  call    ?Init@CMFApi@Hevc@Avenc@Rdp@@QEAAXXZ; Rdp::Avenc::Hevc::CMFApi::Init(void)
0x1800261f7  xor     edx, edx; dwCoInit
0x1800261f9  xor     ecx, ecx; pvReserved
0x1800261fb  call    cs:__imp_CoInitializeEx
0x180026201  mov     rcx, [rsp+0D8h]; this
0x180026209  test    eax, eax
0x18002620b  js      loc_1800263DF
0x180026211  mov     rax, [r14+0F8h]
0x180026218  xor     edx, edx
0x18002621a  mov     ecx, 20070h
0x18002621f  mov     rax, [rax]
0x180026222  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026227  mov     rcx, [rsp+0D8h]; this
0x18002622f  lea     rdx, aCmfstartupFail; "CMFStartup failed. Cannot use HEVC enco"...
0x180026236  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x18002623b  mov     r9d, eax; char *
0x18002623e  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180026245  mov     edx, 49h ; 'I'; void *
0x18002624a  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002624f  mov     [rsp+0D8h+pdwTaskId], r13d
0x180026257  mov     r8d, 0FFFFFFFEh; lPriority
0x18002625d  lea     rdx, [rsp+0D8h+pdwTaskId]; pdwTaskId
0x180026265  lea     rcx, wszClass; "Playback"
0x18002626c  call    cs:__imp_MFRegisterPlatformWithMMCSS
0x180026272  mov     rcx, [rsp+0D8h]; this
0x18002627a  lea     rdx, aMfregisterplat_0; "MFRegisterPlatformWithMMCSS failed. Can"...
0x180026281  mov     qword ptr [rsp+0D8h+var_B8], rdx; int
0x180026286  mov     r9d, eax; char *
0x180026289  lea     r8, aOnecoreuapTerm_26; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x180026290  mov     edx, 52h ; 'R'; void *
0x180026295  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18002629a  mov     eax, ebx
0x18002629c  xchg    al, [rdi+208h]
0x1800262a2  mov     ecx, 18h; Size
0x1800262a7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800262ac  mov     [rax], rdi
0x1800262af  lea     rcx, ?PacketWriterThreadProc@CHevcProcessor@Hevc@Avenc@Rdp@@AEAAXXZ; Rdp::Avenc::Hevc::CHevcProcessor::PacketWriterThreadProc(void)
0x1800262b6  mov     [rax+8], rcx
0x1800262ba  mov     [rax+10h], r13d
0x1800262be  mov     ecx, dword ptr [rsp+0D8h+var_58.fmtid.Data4+4]
0x1800262c5  mov     [rax+14h], ecx
0x1800262c8  mov     [rsp+0D8h+arg_0], rax
0x1800262d0  lea     rcx, [rsp+0D8h+var_58.fmtid.Data4]
0x1800262d8  mov     [rsp+0D8h+var_B0], rcx; int
0x1800262dd  mov     [rsp+0D8h+var_B8], r13d; int
0x1800262e2  mov     r9, rax
0x1800262e5  lea     r8, ??$_Invoke@V?$tuple@P8CRdpProgProcessor@RdpProg@Avenc@Rdp@@EAAXXZPEAV1234@@std@@$0A@$00@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<void (Rdp::Avenc::RdpProg::CRdpProgProcessor::*)(void),Rdp::Avenc::RdpProg::CRdpProgProcessor *>,0,1>(void *)
0x1800262ec  xor     edx, edx
0x1800262ee  xor     ecx, ecx
0x1800262f0  call    cs:__imp__o__beginthreadex
0x1800262f6  mov     rdx, rax
0x1800262f9  mov     qword ptr [rsp+0D8h+var_58.fmtid.Data1], rax
0x180026301  test    rax, rax
0x180026304  jz      loc_1800263F4
0x18002630a  cmp     [rdi+168h], r13d
0x180026311  jz      short loc_18002631A
0x180026313  call    cs:__imp__o_terminate
0x180026319  int     3; Trap to Debugger
0x18002631a  mov     ecx, dword ptr [rsp+0D8h+var_58.fmtid.Data4]
0x180026321  mov     eax, dword ptr [rsp+0D8h+var_58.fmtid.Data4+4]
0x180026328  mov     [rdi+160h], rdx
0x18002632f  mov     [rdi+168h], ecx
0x180026335  mov     [rdi+16Ch], eax
0x18002633b  mov     rax, cs:WPP_GLOBAL_Control
0x180026342  lea     rcx, WPP_GLOBAL_Control
0x180026349  cmp     rax, rcx
0x18002634c  jz      short loc_180026359
0x18002634e  test    [rax+1Ch], bl
0x180026351  jz      short loc_180026359
0x180026353  cmp     byte ptr [rax+19h], 4
0x180026357  jnb     short loc_18002635C
0x180026359  mov     bl, r13b
0x18002635c  lea     rax, WPP_RECORDER_INITIALIZED
0x180026363  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002636a  setnz   dil
0x18002636e  test    bl, bl
0x180026370  jnz     short loc_180026377
0x180026372  test    dil, dil
0x180026375  jz      short loc_1800263A7
0x180026377  call    cs:__imp_GetCurrentThreadId
0x18002637d  mov     dword ptr [rsp+0D8h+var_98], eax; char
0x180026381  mov     [rsp+0D8h+MessageGuid], r12; MessageGuid
0x180026386  mov     [rsp+0D8h+var_A8], 0Bh; __int16
0x18002638d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026394  mov     r9, [rcx+28h]; int
0x180026398  mov     r8b, dil; int
0x18002639b  mov     dl, bl; int
0x18002639d  mov     rcx, [rcx+10h]; int
0x1800263a1  call    WPP_RECORDER_AND_TRACE_SF_D
0x1800263a6  nop
0x1800263a7  call    cs:__imp_CoUninitialize
0x1800263ad  xor     eax, eax
0x1800263af  jmp     short loc_1800263B8
0x1800263b1  mov     eax, dword ptr [rsp+0D8h+arg_0]
0x1800263b8  add     rsp, 0A0h
0x1800263bf  pop     r15
  ... truncated ...
```
