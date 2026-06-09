# Rdp::Avenc::Ic3::CIc3Processor::Start(IUnknown *)

- ea: `0x18003fc50`
- end: `0x180040993`
- name: `?Start@CIc3Processor@Ic3@Avenc@Rdp@@UEAAJPEAUIUnknown@@@Z`
- size: `3395`
- prototype: `__int64 __fastcall(Rdp::Avenc::Ic3::CIc3Processor *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001008`
- `0x180001114`
- `0x18000154c`
- `0x180003c64`
- `0x180006580`
- `0x1800065a4`
- `0x18000e848`
- `0x18000ec04`
- `0x180011490`
- `0x1800124ec`
- `0x180012580`
- `0x180012618`
- `0x1800126b0`
- `0x1800153f8`
- `0x180015480`
- `0x1800203d4`
- `0x1800240b8`
- `0x18003eea4`
- `0x18003f8f0`
- `0x18003f990`
- `0x18003f9d4`
- `0x18003fc50`
- `0x180040d1c`
- `0x1800425b4`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040312`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180040312`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800402e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fcc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040895`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003fcc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040895`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800402f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040309`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004033f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004034c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800402f8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180040309`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004033f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004034c`

## string_xrefs

- `0x18003fe5a`: `onecoreuap\termsrv\rdp_bin\win\rdpavenc\common/ProcessorBase.h`
- `0x18004092e`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180040942`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180040957`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18004096c`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x180040980`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18003fd69`: `DirectStreamMedia_Service`
- `0x1800407bd`: `DirectStreamMedia_Service`
- `0x180040463`: `DSEnableSuperChroma registry value`
- `0x180040519`: `Static frame reencode count overwritten by registry value`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Rdp::Avenc::Ic3::CIc3Processor::Start(
        Rdp::Avenc::Ic3::CIc3Processor *this,
        struct IUnknown *a2,
        int a3,
        int a4)
{
  char v6; // r15
  char v7; // bl
  bool v8; // si
  char CurrentThreadId; // al
  int v10; // r8d
  int v11; // edx
  Rdp::Utils::Props **v12; // rsi
  int v13; // eax
  struct _GUID *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned int Guid; // eax
  unsigned int *v19; // r9
  unsigned int UInt32; // eax
  struct IPropertyStore *v21; // rdx
  struct _LUID *v22; // r9
  unsigned int Luid; // eax
  int v24; // eax
  bool *v25; // r9
  __int64 v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  struct IUnknown **v29; // r9
  unsigned int Unknown; // eax
  __int64 v31; // rax
  __int64 v32; // rbx
  Rdp::Avenc::Ic3::CDsGfxChannel *v33; // rbx
  __int64 v34; // r12
  int v35; // eax
  int v36; // r8d
  int v37; // r9d
  unsigned int v38; // ebx
  struct IUnknown **v39; // r9
  unsigned int v40; // eax
  struct IRDPCoreChannelManager *v41; // r14
  int v42; // eax
  unsigned int *v43; // r9
  __int64 v44; // rax
  __int64 v45; // rcx
  __int64 v46; // rdx
  Rdp::Avenc::Ic3::CIc3Processor *v47; // rax
  Rdp::Avenc::Ic3::CIc3Processor *v48; // r14
  _QWORD **v49; // rsi
  _QWORD *v50; // r12
  _QWORD *v51; // rbx
  DWORD LastError; // r13d
  void *v53; // rcx
  _QWORD *v54; // rbx
  void *v55; // rcx
  unsigned int *v56; // r9
  __int64 *v57; // rbx
  __int64 v58; // rsi
  int v59; // eax
  unsigned int v60; // ebx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // rdx
  __int64 v64; // rcx
  int v65; // r8d
  int v66; // r9d
  int v67; // r8d
  unsigned int v68; // r9d
  DWORD pid; // esi
  const char *v70; // rbx
  int v71; // r8d
  const char *v72; // r9
  unsigned int v73; // eax
  bool v74; // bl
  char v75; // al
  int v76; // r8d
  int v77; // edx
  __int64 result; // rax
  int v79; // [rsp+20h] [rbp-178h]
  int v80; // [rsp+20h] [rbp-178h]
  int v81; // [rsp+20h] [rbp-178h]
  int v82; // [rsp+20h] [rbp-178h]
  int v83; // [rsp+20h] [rbp-178h]
  int v84; // [rsp+28h] [rbp-170h]
  char *v85; // [rsp+28h] [rbp-170h]
  char *v86; // [rsp+28h] [rbp-170h]
  char *v87; // [rsp+28h] [rbp-170h]
  char *v88; // [rsp+28h] [rbp-170h]
  char *v89; // [rsp+28h] [rbp-170h]
  char *v90; // [rsp+28h] [rbp-170h]
  char *v91; // [rsp+28h] [rbp-170h]
  char v92[8]; // [rsp+60h] [rbp-138h] BYREF
  char v93[4]; // [rsp+68h] [rbp-130h] BYREF
  __int64 v94; // [rsp+70h] [rbp-128h] BYREF
  struct IRDPCoreChannelManager *v95; // [rsp+78h] [rbp-120h] BYREF
  const char *v96; // [rsp+80h] [rbp-118h] BYREF
  struct _tagpropertykey v97; // [rsp+88h] [rbp-110h] BYREF
  const char *v98; // [rsp+A0h] [rbp-F8h] BYREF
  struct _tagpropertykey v99; // [rsp+A8h] [rbp-F0h] BYREF
  const char *v100; // [rsp+D0h] [rbp-C8h]
  __int64 v101; // [rsp+D8h] [rbp-C0h]
  __int64 *v102; // [rsp+E0h] [rbp-B8h]
  __int64 v103; // [rsp+E8h] [rbp-B0h]
  const char *v104; // [rsp+F0h] [rbp-A8h]
  __int64 v105; // [rsp+F8h] [rbp-A0h]
  const char *v106; // [rsp+100h] [rbp-98h]
  __int64 v107; // [rsp+108h] [rbp-90h]
  int *v108; // [rsp+110h] [rbp-88h]
  __int64 v109; // [rsp+118h] [rbp-80h]
  const char *v110; // [rsp+120h] [rbp-78h]
  __int64 v111; // [rsp+128h] [rbp-70h]
  const char **v112; // [rsp+130h] [rbp-68h]
  __int64 v113; // [rsp+138h] [rbp-60h]
  struct _tagpropertykey *v114; // [rsp+140h] [rbp-58h]
  __int64 v115; // [rsp+148h] [rbp-50h]
  char *v116; // [rsp+150h] [rbp-48h]
  __int64 v117; // [rsp+158h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+0h]

  v6 = 1;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v7 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    v7 = 0;
  }
  v8 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v7 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v10) = v8;
    LOBYTE(v11) = v7;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      v10,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v79,
      v84,
      10,
      &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
      CurrentThreadId);
  }
  if ( (unsigned int)dword_1800C1058 > 4
    && (qword_1800C1068 & 0x470000000000LL) != 0
    && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
  {
    *(_QWORD *)&v99.fmtid.Data1 = *((_QWORD *)this + 6);
    *(_DWORD *)v93 = *((_DWORD *)this + 14);
    v95 = (struct IRDPCoreChannelManager *)"Start Ic3 processor";
    *(_QWORD *)v92 = &xmmword_1800C21A0;
    v98 = "DirectStreamMedia_Service";
    v96 = "RdpAvenc";
    v94 = 0x1000000;
    *(_QWORD *)&v97.fmtid.Data1 = "Checkpoint";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800C1058,
      (unsigned int)qword_1800AFEB8,
      a3,
      a4,
      (__int64)&v97,
      (__int64)&v94,
      (__int64)&v96,
      (__int64)&v98,
      (__int64)v92,
      (__int64)&v95,
      (__int64)v93,
      (__int64)&v99);
  }
  try
  {
    Rdp::Modern::Utils::CInflightRecorder::pushN(
      (Rdp::Modern::Utils::CInflightRecorder *)Rdp::Modern::Utils::CInflightRecorder::g_Ifr,
      (wchar_t *)L"Ic3ProcessorStart",
      "Rdp::Avenc::Ic3::CIc3Processor::Start",
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      0x4Cu);
    v12 = (Rdp::Utils::Props **)((char *)this + 8);
    wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(
      retaddr,
      196,
      "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      2147549183LL);
    *(_QWORD *)v92 = 0;
    v13 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a,
            v92);
    if ( v13 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v13,
        (_DWORD)this + 8);
    v15 = *(_QWORD *)v92;
    v16 = 0;
    *(_QWORD *)v92 = 0;
    v17 = *((_QWORD *)this + 2);
    *((_QWORD *)this + 2) = v15;
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v16 = *(_QWORD *)v92;
    }
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v97.fmtid = 0;
    Guid = Rdp::Utils::Props::IPropertyStore_GetGuid(*v12, (struct IPropertyStore *)&PKEY_Activity_Id, &v97, v14);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xD1,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Guid,
      (int)"Failed to retrieve PKEY_Activity_Id property",
      "PropertyStore is not initialized");
    *(GUID *)&xmmword_1800C21A0 = v97.fmtid;
    UInt32 = Rdp::Utils::Props::IPropertyStore_GetUInt32(
               *v12,
               (struct IPropertyStore *)&PKEY_Session_Id,
               (const struct _tagpropertykey *)((char *)this + 56),
               v19);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xDD,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)UInt32,
      (int)"Failed to retrieve PKEY_Session_Id property",
      v85);
    Luid = Rdp::Utils::Props::IPropertyStore_GetLuid(
             *v12,
             v21,
             (const struct _tagpropertykey *)((char *)this + 48),
             v22);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0xE7,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\common/ProcessorBase.h",
      (const char *)Luid,
      (int)"Failed to retrieve PKEY_Terminal_Luid property",
      v86);
    *((_BYTE *)this + 152) = 1;
    *(_QWORD *)v92 = 0;
    v24 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, char *))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_7407257e_6f64_4407_a627_8b5ca5625af2,
            v92);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v24,
        v80);
    v26 = *(_QWORD *)v92;
    v27 = 0;
    *(_QWORD *)v92 = 0;
    v28 = *((_QWORD *)this + 22);
    *((_QWORD *)this + 22) = v26;
    if ( v28 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v27 = *(_QWORD *)v92;
    }
    if ( v27 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    if ( (int)Rdp::Utils::Props::IPropertyStore_GetBool(
                *((Rdp::Utils::Props **)this + 1),
                (struct IPropertyStore *)&PKEY_EnableDirectStreamMediaApiServer,
                (const struct _tagpropertykey *)((char *)this + 224),
                v25) < 0 )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        *(_QWORD *)&v97.fmtid.Data1 = "Failed to retrieve PKEY_EnableDirectStreamMediaApiServer property. Falling back to"
                                      " Legacy Direct Stream Media APIs.";
        v94 = (__int64)"Rdp::Avenc::Ic3::CIc3Processor::Start";
        *(_DWORD *)v93 = 92;
        v96 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)word_1800AFE82,
          (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
          (_DWORD)v29,
          (__int64)&v96,
          (__int64)v93,
          (__int64)&v94,
          (__int64)&v97);
      }
      *((_BYTE *)this + 224) = 0;
    }
    *(_QWORD *)&v99.fmtid.Data1 = 0;
    Unknown = Rdp::Utils::Props::IPropertyStore_GetUnknown(
                *((Rdp::Utils::Props **)this + 1),
                (struct IPropertyStore *)&PKEY_DynamicVcManager,
                &v99,
                v29);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x69,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      (const char *)Unknown,
      (int)"Failed to retrieve PKEY_DynamicVcManager property",
      v87);
    *(_QWORD *)&v97.fmtid.Data1 = operator new(0xA0u);
    v31 = Rdp::Avenc::Ic3::CDsGfxChannel::CDsGfxChannel(
            *(Rdp::Avenc::Ic3::CDsGfxChannel **)&v97.fmtid.Data1,
            *((struct IPropertyStore **)this + 1),
            (Rdp::Avenc::Ic3::CIc3Processor *)((char *)this - 80));
    v32 = *((_QWORD *)this + 20);
    *((_QWORD *)this + 20) = v31;
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 8LL))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v33 = (Rdp::Avenc::Ic3::CDsGfxChannel *)*((_QWORD *)this + 20);
    v95 = 0;
    v34 = *(_QWORD *)&v99.fmtid.Data1;
    v35 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, struct IRDPCoreChannelManager **))&v99.fmtid.Data1)(
            *(_QWORD *)&v99.fmtid.Data1,
            &GUID_0fd57159_e83e_476a_b9a8_4a7976e71e18,
            &v95);
    if ( v35 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v35,
        v81);
    v38 = Rdp::Avenc::Ic3::CDsGfxChannel::Start(v33, v95, v36, v37);
    if ( v95 )
      (*(void (__fastcall **)(struct IRDPCoreChannelManager *))(*(_QWORD *)v95 + 16LL))(v95);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x6D,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      (const char *)v38,
      (int)"Failed to start DS GFX channel",
      v88);
    v95 = 0;
    v40 = Rdp::Utils::Props::IPropertyStore_GetUnknown(
            *((Rdp::Utils::Props **)this + 1),
            (struct IPropertyStore *)&PKEY_DirectStreamMediaControl,
            (const struct _tagpropertykey *)&v95,
            v39);
    wil::details::in1diag3::Throw_IfFailedMsg(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      (const char *)v40,
      (int)"Failed to retrieve PKEY_DirectStreamMediaControl property",
      v89);
    *(_QWORD *)v92 = 0;
    v41 = v95;
    v42 = (**(__int64 (__fastcall ***)(struct IRDPCoreChannelManager *, GUID *, char *))v95)(
            v95,
            &GUID_f6a2162d_28c1_43c5_8fcd_bfa081bf68ea,
            v92);
    if ( v42 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v42,
        v82);
    v44 = *(_QWORD *)v92;
    v45 = 0;
    *(_QWORD *)v92 = 0;
    v46 = *((_QWORD *)this + 21);
    *((_QWORD *)this + 21) = v44;
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v45 = *(_QWORD *)v92;
    }
    if ( v45 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
    if ( (int)Rdp::Utils::Props::IPropertyStore_GetUInt32(
                *((Rdp::Utils::Props **)this + 1),
                (struct IPropertyStore *)&PKEY_Capture_Process_Pid,
                (const struct _tagpropertykey *)this + 10,
                v43) >= 0 )
    {
      v47 = (Rdp::Avenc::Ic3::CIc3Processor *)Rdp::Security::InitializeLocalSystemSecurityAttr(&v97);
      v48 = v47;
      v49 = (_QWORD **)((char *)this + 216);
      if ( (Rdp::Avenc::Ic3::CIc3Processor *)((char *)this + 216) != v47 )
      {
        v50 = *(_QWORD **)v47;
        v51 = *v49;
        if ( *v49 )
        {
          LastError = GetLastError();
          v53 = (void *)v51[1];
          if ( v53 )
          {
            LocalFree(v53);
            v51[1] = 0;
          }
          LocalFree(v51);
          SetLastError(LastError);
        }
        *v49 = v50;
        *(_QWORD *)v48 = 0;
        v34 = *(_QWORD *)&v99.fmtid.Data1;
      }
      v54 = *(_QWORD **)&v97.fmtid.Data1;
      if ( *(_QWORD *)&v97.fmtid.Data1 )
      {
        v55 = *(void **)(*(_QWORD *)&v97.fmtid.Data1 + 8LL);
        if ( v55 )
        {
          LocalFree(v55);
          v54[1] = 0;
        }
        LocalFree(v54);
      }
      v41 = v95;
    }
    if ( (int)Rdp::DebugPanel::LoadHostDllAndGetChannel((char *)this + 192, (char *)this + 184) >= 0 )
    {
      v57 = (__int64 *)*((_QWORD *)this + 23);
      v58 = *v57;
      *(_QWORD *)v92 = 0;
      v59 = (**(__int64 (__fastcall ***)(__int64, GUID *, char *))v34)(
              v34,
              &GUID_0fd57159_e83e_476a_b9a8_4a7976e71e18,
              v92);
      if ( v59 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v59,
          v82);
      v60 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(v58 + 24))(v57, *(_QWORD *)v92);
      if ( *(_QWORD *)v92 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v92 + 16LL))(*(_QWORD *)v92);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x90,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)v60,
        (int)"Failed to start Debug Panel channel",
        v90);
    }
    if ( (int)Rdp::Utils::Props::IPropertyStore_GetUInt32(
                *((Rdp::Utils::Props **)this + 1),
                (struct IPropertyStore *)&PKEY_GrfxPipelineImageQuality,
                (const struct _tagpropertykey *)((char *)this + 204),
                v56) < 0 )
      *((_DWORD *)this + 51) = 3;
    *(_DWORD *)v93 = 0;
    if ( (int)wil::reg::get_value_nothrow<unsigned long,0>(v62, v61, L"DSEnableSuperChroma", v93) >= 0 )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        LODWORD(v98) = *(_DWORD *)v93;
        *(_QWORD *)&v97.fmtid.Data1 = "DSEnableSuperChroma registry value";
        v94 = (__int64)"Rdp::Avenc::Ic3::CIc3Processor::Start";
        *(_DWORD *)v92 = 170;
        v96 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)byte_1800AFE01,
          v65,
          v66,
          (__int64)&v96,
          (__int64)v92,
          (__int64)&v94,
          (__int64)&v97,
          (__int64)&v98);
      }
      *((_BYTE *)this + 209) = *(_DWORD *)v93 != 0;
    }
    v97.pid = 0;
    if ( (int)wil::reg::get_value_nothrow<unsigned long,0>(v64, v63, L"DSStaticFrameReencodeCount", &v97.pid) < 0 )
    {
      pid = 0;
    }
    else
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        *(_QWORD *)&v97.fmtid.Data1 = "Static frame reencode count overwritten by registry value";
        v94 = (__int64)"Rdp::Avenc::Ic3::CIc3Processor::Start";
        *(_DWORD *)v92 = 182;
        v96 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800AFE4C,
          v67,
          v68,
          (__int64)&v96,
          (__int64)v92,
          (__int64)&v94,
          (__int64)&v97);
      }
      pid = v97.pid;
      if ( v97.pid > 0x64 )
        pid = 100;
      v97.pid = pid;
    }
    v70 = (const char *)(unsigned int)Rdp::Utils::Props::IPropertyStore_SetUInt32(
                                        *((Rdp::Utils::Props **)this + 1),
                                        (struct IPropertyStore *)&PKEY_StaticFrameReencodeCount,
                                        (const struct _tagpropertykey *)pid,
                                        v68);
    wil::details::in1diag3::Log_IfFailedMsg(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
      v70,
      (int)"Failed to set PKEY_StaticFrameReencodeCount property",
      v90);
    if ( (int)v70 >= 0 )
    {
      if ( (unsigned int)dword_1800C1058 > 4 )
      {
        *(_DWORD *)v92 = pid;
        *(_QWORD *)&v97.fmtid.Data1 = "Signal PKEY_StaticFrameReencodeCount change";
        v94 = (__int64)"Rdp::Avenc::Ic3::CIc3Processor::Start";
        LODWORD(v98) = 195;
        v96 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          (unsigned int)&dword_1800C1058,
          (unsigned int)&dword_1800AFDBC,
          v71,
          (_DWORD)v72,
          (__int64)&v96,
          (__int64)&v98,
          (__int64)&v94,
          (__int64)&v97,
          (__int64)v92);
      }
      v73 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 22) + 24LL))(*((_QWORD *)this + 22), 1);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
        (const char *)v73,
        (int)"Failed to signal PKEY_StaticFrameReencodeCount change",
        v91);
    }
    *((_BYTE *)this + 208) = 1;
    if ( (unsigned int)dword_1800C1058 > 4
      && (qword_1800C1068 & 0x470000000000LL) != 0
      && (qword_1800C1070 & 0x470000000000LL) == qword_1800C1070 )
    {
      *(_DWORD *)v92 = *((_QWORD *)this + 21) != 0;
      *(_QWORD *)&v97.fmtid.Data1 = *((_QWORD *)this + 6);
      LODWORD(v98) = *((_DWORD *)this + 14);
      v94 = 0x1000000;
      v116 = v92;
      v117 = 4;
      v114 = &v97;
      v115 = 8;
      v112 = &v98;
      v113 = 4;
      v110 = "Ic3 processor started";
      v111 = 22;
      v108 = &xmmword_1800C21A0;
      v109 = 16;
      v106 = "DirectStreamMedia_Service";
      v107 = 26;
      v104 = "RdpAvenc";
      v105 = 9;
      v102 = &v94;
      v103 = 8;
      v100 = "Checkpoint";
      v101 = 11;
      tlgWriteTransfer_EventWriteTransfer(&dword_1800C1058, qword_1800AFCB8, 0, 0, 11, v99.fmtid.Data4);
    }
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v6 = 0;
    }
    v74 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v6 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v75 = GetCurrentThreadId();
      LOBYTE(v76) = v74;
      LOBYTE(v77) = v6;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v77,
        v76,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v83,
        (int)v91,
        11,
        &WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids,
        v75);
    }
    if ( v41 )
      (*(void (__fastcall **)(struct IRDPCoreChannelManager *))(*(_QWORD *)v41 + 16LL))(v41);
    if ( v34 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xD9,
                           (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\rdpavenc\\ic3processor\\ic3processor.cpp",
                           v72);
  }
  return result;
}

```

## disassembly

```asm
0x18003fc50  mov     [rsp+arg_10], rbx
0x18003fc55  mov     [rsp+arg_18], rsi
0x18003fc5a  push    rdi
0x18003fc5b  push    r12
0x18003fc5d  push    r13
0x18003fc5f  push    r14
0x18003fc61  push    r15
0x18003fc63  sub     rsp, 170h
0x18003fc6a  mov     rax, cs:__security_cookie
0x18003fc71  xor     rax, rsp
0x18003fc74  mov     [rsp+198h+var_38], rax
0x18003fc7c  mov     r14, rdx
0x18003fc7f  mov     rdi, rcx
0x18003fc82  xor     r13d, r13d
0x18003fc85  lea     rcx, WPP_GLOBAL_Control
0x18003fc8c  mov     rax, cs:WPP_GLOBAL_Control
0x18003fc93  lea     r15d, [r13+1]
0x18003fc97  cmp     rax, rcx
0x18003fc9a  jz      short loc_18003FCAB
0x18003fc9c  test    [rax+1Ch], r15b
0x18003fca0  jz      short loc_18003FCAB
0x18003fca2  cmp     byte ptr [rax+19h], 4
0x18003fca6  mov     bl, r15b
0x18003fca9  jnb     short loc_18003FCAE
0x18003fcab  mov     bl, r13b
0x18003fcae  lea     rax, WPP_RECORDER_INITIALIZED
0x18003fcb5  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003fcbc  setnz   sil
0x18003fcc0  test    bl, bl
0x18003fcc2  jnz     short loc_18003FCC9
0x18003fcc4  test    sil, sil
0x18003fcc7  jz      short loc_18003FCFF
0x18003fcc9  call    cs:__imp_GetCurrentThreadId
0x18003fccf  mov     dword ptr [rsp+198h+var_158], eax; char
0x18003fcd3  lea     r12, WPP_4b9a76f9a4743e6350985cf8338b8839_Traceguids
0x18003fcda  mov     [rsp+198h+MessageGuid], r12; MessageGuid
0x18003fcdf  mov     [rsp+198h+var_168], 0Ah; __int16
0x18003fce6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fced  mov     r9, [rcx+28h]; int
0x18003fcf1  mov     r8b, sil; int
0x18003fcf4  mov     dl, bl; int
0x18003fcf6  mov     rcx, [rcx+10h]; int
0x18003fcfa  call    WPP_RECORDER_AND_TRACE_SF_D
0x18003fcff  mov     eax, cs:dword_1800C1058
0x18003fd05  cmp     eax, 4
0x18003fd08  jbe     loc_18003FE0E
0x18003fd0e  mov     rcx, cs:qword_1800C1070
0x18003fd15  mov     rax, cs:qword_1800C1068
0x18003fd1c  mov     rbx, 470000000000h
0x18003fd26  test    rbx, rax
0x18003fd29  jz      loc_18003FE0E
0x18003fd2f  mov     rax, rcx
0x18003fd32  and     rax, rbx
0x18003fd35  cmp     rax, rcx
0x18003fd38  jnz     loc_18003FE0E
0x18003fd3e  mov     rax, [rdi+30h]
0x18003fd42  mov     qword ptr [rsp+198h+var_F0.fmtid.Data1], rax
0x18003fd4a  mov     eax, [rdi+38h]
0x18003fd4d  mov     dword ptr [rsp+198h+var_130], eax
0x18003fd51  lea     rax, aStartIc3Proces; "Start Ic3 processor"
0x18003fd58  mov     qword ptr [rsp+198h+var_120.fmtid.Data1], rax
0x18003fd5d  lea     rbx, xmmword_1800C21A0
0x18003fd64  mov     qword ptr [rsp+198h+var_138], rbx
0x18003fd69  lea     rbx, aDirectstreamme; "DirectStreamMedia_Service"
0x18003fd70  mov     [rsp+198h+var_F8], rbx
0x18003fd78  lea     rbx, aRdpavenc; "RdpAvenc"
0x18003fd7f  mov     qword ptr [rsp+198h+var_120.fmtid.Data4], rbx
0x18003fd87  mov     [rsp+198h+var_128], 1000000h
0x18003fd90  lea     rbx, aCheckpoint; "Checkpoint"
0x18003fd97  mov     qword ptr [rsp+198h+var_120.pid], rbx
0x18003fd9f  lea     rax, [rsp+198h+var_F0]
0x18003fda7  mov     [rsp+198h+var_140], rax
0x18003fdac  lea     rax, [rsp+198h+var_130]
0x18003fdb1  mov     [rsp+198h+var_148], rax
0x18003fdb6  lea     rax, [rsp+198h+var_120]
0x18003fdbb  mov     [rsp+198h+var_150], rax
0x18003fdc0  lea     rax, [rsp+198h+var_138]
0x18003fdc5  mov     qword ptr [rsp+198h+var_158], rax
0x18003fdca  lea     rax, [rsp+198h+var_F8]
0x18003fdd2  mov     [rsp+198h+MessageGuid], rax
0x18003fdd7  lea     rax, [rsp+198h+var_120.fmtid.Data4]
0x18003fddf  mov     qword ptr [rsp+198h+var_168], rax
0x18003fde4  lea     rax, [rsp+198h+var_128]
0x18003fde9  mov     [rsp+198h+var_170], rax
0x18003fdee  lea     rax, [rsp+198h+var_120.pid]
0x18003fdf6  mov     qword ptr [rsp+198h+var_178], rax
0x18003fdfb  lea     rdx, qword_1800AFEB8
0x18003fe02  lea     rcx, dword_1800C1058
0x18003fe09  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U1@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@3AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x18003fe0e  mov     [rsp+198h+var_178], 4Ch ; 'L'; unsigned int
0x18003fe16  lea     r9, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003fe1d  lea     r8, aRdpAvencIc3Cic_2; "Rdp::Avenc::Ic3::CIc3Processor::Start"
0x18003fe24  lea     rdx, aIc3processorst; "Ic3ProcessorStart"
0x18003fe2b  lea     rcx, ?g_Ifr@CInflightRecorder@Utils@Modern@Rdp@@0V1234@A; this
0x18003fe32  call    ?pushN@CInflightRecorder@Utils@Modern@Rdp@@QEAAXPEBGPEBD1IZZ; Rdp::Modern::Utils::CInflightRecorder::pushN(ushort const *,char const *,char const *,uint,...)
0x18003fe37  lea     rsi, [rdi+8]
0x18003fe3b  mov     rcx, [rsp+198h]
0x18003fe43  lea     rax, aPropertystoreI; "PropertyStore is not initialized"
0x18003fe4a  mov     [rsp+198h+var_170], rax; char *
0x18003fe4f  mov     qword ptr [rsp+198h+var_178], rsi; int
0x18003fe54  mov     r9d, 8000FFFFh
0x18003fe5a  lea     r12, aOnecoreuapTerm_44; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18003fe61  mov     r8, r12
0x18003fe64  mov     edx, 0C4h
0x18003fe69  call    ??$Throw_HrIfNullMsg@V?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@wil@@$0A@@in1diag3@details@wil@@YAXPEAXIPEBDJAEBV?$com_ptr_t@UIPropertyStore@@Uerr_exception_policy@wil@@@2@1ZZ; wil::details::in1diag3::Throw_HrIfNullMsg<wil::com_ptr_t<IPropertyStore,wil::err_exception_policy>,0>(void *,uint,char const *,long,wil::com_ptr_t<IPropertyStore,wil::err_exception_policy> const &,char const *,...)
0x18003fe6e  mov     qword ptr [rsp+198h+var_138], r13
0x18003fe73  mov     rax, [r14]
0x18003fe76  lea     r8, [rsp+198h+var_138]
0x18003fe7b  lea     rdx, _GUID_d446623d_bea3_4095_bb2e_25ff7e09a37a
0x18003fe82  mov     rcx, r14
0x18003fe85  mov     rax, [rax]
0x18003fe88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fe8d  mov     rcx, [rsp+198h]; this
0x18003fe95  test    eax, eax
0x18003fe97  js      loc_18004092B
0x18003fe9d  mov     rax, qword ptr [rsp+198h+var_138]
0x18003fea2  mov     rcx, r13
0x18003fea5  mov     qword ptr [rsp+198h+var_138], rcx
0x18003feaa  mov     rdx, [rdi+10h]
0x18003feae  mov     [rdi+10h], rax
0x18003feb2  test    rdx, rdx
0x18003feb5  jz      short loc_18003FECB
0x18003feb7  mov     rax, [rdx]
0x18003feba  mov     rcx, rdx
0x18003febd  mov     rax, [rax+10h]
0x18003fec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fec6  mov     rcx, qword ptr [rsp+198h+var_138]
0x18003fecb  test    rcx, rcx
0x18003fece  jz      short loc_18003FEDD
0x18003fed0  mov     rax, [rcx]
0x18003fed3  mov     rax, [rax+10h]
0x18003fed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003fedc  nop
0x18003fedd  xorps   xmm0, xmm0
0x18003fee0  movups  xmmword ptr [rsp+198h+var_120.pid], xmm0
0x18003fee8  lea     r8, [rsp+198h+var_120.pid]; struct _tagpropertykey *
0x18003fef0  lea     rdx, PKEY_Activity_Id; struct IPropertyStore *
0x18003fef7  mov     rcx, [rsi]; this
0x18003fefa  call    ?IPropertyStore_GetGuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_GUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetGuid(IPropertyStore *,_tagpropertykey const &,_GUID *)
0x18003feff  mov     rcx, [rsp+198h]; this
0x18003ff07  lea     rdx, aFailedToRetrie_17; "Failed to retrieve PKEY_Activity_Id pro"...
0x18003ff0e  mov     qword ptr [rsp+198h+var_178], rdx; int
0x18003ff13  mov     r9d, eax; char *
0x18003ff16  mov     r8, r12; unsigned int
0x18003ff19  mov     edx, 0D1h; void *
0x18003ff1e  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003ff23  movups  xmm0, xmmword ptr [rsp+198h+var_120.pid]
0x18003ff2b  movdqu  cs:xmmword_1800C21A0, xmm0
0x18003ff33  lea     r8, [rdi+38h]; struct _tagpropertykey *
0x18003ff37  lea     rdx, PKEY_Session_Id; struct IPropertyStore *
0x18003ff3e  mov     rcx, [rsi]; this
0x18003ff41  call    ?IPropertyStore_GetUInt32@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAI@Z; Rdp::Utils::Props::IPropertyStore_GetUInt32(IPropertyStore *,_tagpropertykey const &,uint *)
0x18003ff46  mov     rcx, [rsp+198h]; this
0x18003ff4e  lea     rdx, aFailedToRetrie_19; "Failed to retrieve PKEY_Session_Id prop"...
0x18003ff55  mov     qword ptr [rsp+198h+var_178], rdx; int
0x18003ff5a  mov     r9d, eax; char *
0x18003ff5d  mov     r8, r12; unsigned int
0x18003ff60  mov     edx, 0DDh; void *
0x18003ff65  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003ff6a  lea     r8, [rdi+30h]; struct _tagpropertykey *
0x18003ff6e  mov     rcx, [rsi]; this
0x18003ff71  call    ?IPropertyStore_GetLuid@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAU_LUID@@@Z; Rdp::Utils::Props::IPropertyStore_GetLuid(IPropertyStore *,_tagpropertykey const &,_LUID *)
0x18003ff76  mov     rcx, [rsp+198h]; this
0x18003ff7e  lea     rdx, aFailedToRetrie_12; "Failed to retrieve PKEY_Terminal_Luid p"...
0x18003ff85  mov     qword ptr [rsp+198h+var_178], rdx; int
0x18003ff8a  mov     r9d, eax; char *
0x18003ff8d  mov     r8, r12; unsigned int
0x18003ff90  mov     edx, 0E7h; void *
0x18003ff95  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18003ff9a  mov     [rdi+98h], r15b
0x18003ffa1  mov     qword ptr [rsp+198h+var_138], r13
0x18003ffa6  mov     rax, [r14]
0x18003ffa9  lea     r8, [rsp+198h+var_138]
0x18003ffae  lea     rdx, _GUID_7407257e_6f64_4407_a627_8b5ca5625af2
0x18003ffb5  mov     rcx, r14
0x18003ffb8  mov     rax, [rax]
0x18003ffbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffc0  mov     rcx, [rsp+198h]; this
0x18003ffc8  test    eax, eax
0x18003ffca  js      loc_18004093F
0x18003ffd0  mov     rax, qword ptr [rsp+198h+var_138]
0x18003ffd5  mov     rcx, r13
0x18003ffd8  mov     qword ptr [rsp+198h+var_138], rcx
0x18003ffdd  mov     rdx, [rdi+0B0h]
0x18003ffe4  mov     [rdi+0B0h], rax
0x18003ffeb  test    rdx, rdx
0x18003ffee  jz      short loc_180040004
0x18003fff0  mov     rax, [rdx]
0x18003fff3  mov     rcx, rdx
0x18003fff6  mov     rax, [rax+10h]
0x18003fffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ffff  mov     rcx, qword ptr [rsp+198h+var_138]
0x180040004  test    rcx, rcx
0x180040007  jz      short loc_180040016
0x180040009  mov     rax, [rcx]
0x18004000c  mov     rax, [rax+10h]
0x180040010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040015  nop
0x180040016  lea     rsi, [rdi+0E0h]
0x18004001d  mov     r8, rsi; struct _tagpropertykey *
0x180040020  lea     rdx, PKEY_EnableDirectStreamMediaApiServer; struct IPropertyStore *
0x180040027  mov     rcx, [rdi+8]; this
0x18004002b  call    ?IPropertyStore_GetBool@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEA_N@Z; Rdp::Utils::Props::IPropertyStore_GetBool(IPropertyStore *,_tagpropertykey const &,bool *)
0x180040030  test    eax, eax
0x180040032  jns     loc_1800400B9
0x180040038  mov     eax, cs:dword_1800C1058
0x18004003e  cmp     eax, 4
0x180040041  jbe     short loc_1800400B6
0x180040043  lea     rax, aFailedToRetrie_0; "Failed to retrieve PKEY_EnableDirectStr"...
0x18004004a  mov     qword ptr [rsp+198h+var_120.pid], rax
0x180040052  lea     rax, aRdpAvencIc3Cic_2; "Rdp::Avenc::Ic3::CIc3Processor::Start"
0x180040059  mov     [rsp+198h+var_128], rax
0x18004005e  mov     dword ptr [rsp+198h+var_130], 5Ch ; '\'
0x180040066  lea     r8, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x18004006d  mov     qword ptr [rsp+198h+var_120.fmtid.Data4], r8
0x180040075  lea     rax, [rsp+198h+var_120.pid]
0x18004007d  mov     [rsp+198h+MessageGuid], rax
0x180040082  lea     rax, [rsp+198h+var_128]
0x180040087  mov     qword ptr [rsp+198h+var_168], rax
0x18004008c  lea     rax, [rsp+198h+var_130]
0x180040091  mov     [rsp+198h+var_170], rax; char *
0x180040096  lea     rax, [rsp+198h+var_120.fmtid.Data4]
0x18004009e  mov     qword ptr [rsp+198h+var_178], rax
0x1800400a3  lea     rdx, word_1800AFE82
0x1800400aa  lea     rcx, dword_1800C1058
0x1800400b1  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800400b6  mov     [rsi], r13b
0x1800400b9  mov     qword ptr [rsp+198h+var_F0.fmtid.Data1], r13
0x1800400c1  lea     r8, [rsp+198h+var_F0]; struct _tagpropertykey *
0x1800400c9  lea     rdx, PKEY_DynamicVcManager; struct IPropertyStore *
0x1800400d0  mov     rcx, [rdi+8]; this
0x1800400d4  call    ?IPropertyStore_GetUnknown@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUIUnknown@@@Z; Rdp::Utils::Props::IPropertyStore_GetUnknown(IPropertyStore *,_tagpropertykey const &,IUnknown * *)
0x1800400d9  mov     rcx, [rsp+198h]; this
0x1800400e1  lea     rdx, aFailedToRetrie_24; "Failed to retrieve PKEY_DynamicVcManage"...
0x1800400e8  mov     qword ptr [rsp+198h+var_178], rdx; int
0x1800400ed  mov     r9d, eax; char *
0x1800400f0  lea     rsi, aOnecoreuapTerm_1; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpa"...
0x1800400f7  mov     r8, rsi; unsigned int
0x1800400fa  mov     edx, 69h ; 'i'; void *
0x1800400ff  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180040104  mov     ecx, 0A0h; Size
0x180040109  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18004010e  mov     qword ptr [rsp+198h+var_120.pid], rax
0x180040116  lea     r8, [rdi-50h]; struct Rdp::Avenc::Ic3::CIc3Processor *
0x18004011a  mov     rdx, [rdi+8]; struct IPropertyStore *
0x18004011e  mov     rcx, rax; this
0x180040121  call    ??0CDsGfxChannel@Ic3@Avenc@Rdp@@QEAA@PEAUIPropertyStore@@PEAVCIc3Processor@123@@Z; Rdp::Avenc::Ic3::CDsGfxChannel::CDsGfxChannel(IPropertyStore *,Rdp::Avenc::Ic3::CIc3Processor *)
0x180040126  nop
0x180040127  mov     rbx, [rdi+0A0h]
0x18004012e  mov     [rdi+0A0h], rax
0x180040135  test    rax, rax
0x180040138  jz      short loc_180040149
0x18004013a  mov     rdx, [rax]
0x18004013d  mov     rcx, rax
0x180040140  mov     rax, [rdx+8]
0x180040144  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040149  test    rbx, rbx
0x18004014c  jz      short loc_18004015E
0x18004014e  mov     rax, [rbx]
0x180040151  mov     rcx, rbx
0x180040154  mov     rax, [rax+10h]
0x180040158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004015d  nop
0x18004015e  mov     rbx, [rdi+0A0h]
0x180040165  mov     qword ptr [rsp+198h+var_120.fmtid.Data1], r13
0x18004016a  mov     r12, qword ptr [rsp+198h+var_F0.fmtid.Data1]
0x180040172  mov     rax, [r12]
0x180040176  lea     r8, [rsp+198h+var_120]
0x18004017b  lea     rdx, _GUID_0fd57159_e83e_476a_b9a8_4a7976e71e18
0x180040182  mov     rcx, r12
0x180040185  mov     rax, [rax]
0x180040188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004018d  mov     rcx, [rsp+198h]; this
0x180040195  test    eax, eax
0x180040197  js      loc_180040954
0x18004019d  mov     rdx, qword ptr [rsp+198h+var_120.fmtid.Data1]; struct IRDPCoreChannelManager *
0x1800401a2  mov     rcx, rbx; this
0x1800401a5  call    ?Start@CDsGfxChannel@Ic3@Avenc@Rdp@@QEAAJPEAUIRDPCoreChannelManager@@@Z; Rdp::Avenc::Ic3::CDsGfxChannel::Start(IRDPCoreChannelManager *)
0x1800401aa  mov     ebx, eax
0x1800401ac  mov     rcx, qword ptr [rsp+198h+var_120.fmtid.Data1]
0x1800401b1  test    rcx, rcx
0x1800401b4  jz      short loc_1800401C3
0x1800401b6  mov     rdx, [rcx]
0x1800401b9  mov     rax, [rdx+10h]
0x1800401bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800401c2  nop
0x1800401c3  mov     rcx, [rsp+198h]; this
0x1800401cb  lea     rax, aFailedToStartD; "Failed to start DS GFX channel"
0x1800401d2  mov     qword ptr [rsp+198h+var_178], rax; int
0x1800401d7  mov     r9d, ebx; char *
0x1800401da  mov     r8, rsi; unsigned int
0x1800401dd  mov     edx, 6Dh ; 'm'; void *
0x1800401e2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800401e7  nop
0x1800401e8  mov     qword ptr [rsp+198h+var_120.fmtid.Data1], r13
0x1800401ed  lea     r8, [rsp+198h+var_120]; struct _tagpropertykey *
0x1800401f2  lea     rdx, PKEY_DirectStreamMediaControl; struct IPropertyStore *
0x1800401f9  mov     rcx, [rdi+8]; this
0x1800401fd  call    ?IPropertyStore_GetUnknown@Props@Utils@Rdp@@YAJPEAUIPropertyStore@@AEBU_tagpropertykey@@PEAPEAUIUnknown@@@Z; Rdp::Utils::Props::IPropertyStore_GetUnknown(IPropertyStore *,_tagpropertykey const &,IUnknown * *)
0x180040202  mov     rcx, [rsp+198h]; this
  ... truncated ...
```
