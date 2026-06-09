# CAudioClient::SetupAudioStreamWithAudioSrv(CPrivCritSecLock &,_AUDCLNT_SHAREMODE,ulong &,__int64,__int64,tWAVEFORMATEX const *,_GUID const *,SYSTEM_AUDIO_STREAM_TYPE &,SYSTEM_AUDIO_STREAM &,std::function<void (void)> &)

- ea: `0x180049300`
- end: `0x18004a49d`
- name: `?SetupAudioStreamWithAudioSrv@CAudioClient@@AEAAJAEAVCPrivCritSecLock@@W4_AUDCLNT_SHAREMODE@@AEAK_J3PEBUtWAVEFORMATEX@@PEBU_GUID@@AEAW4SYSTEM_AUDIO_STREAM_TYPE@@AEAUSYSTEM_AUDIO_STREAM@@AEAV?$function@$$A6AXXZ@std@@@Z`
- size: `4509`
- prototype: `__int64 __usercall@<rax>(CAudioClient *this@<rcx>, __int64, __int64, __int64, __int64, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180047344`

## callees

- `0x18000da68`
- `0x180010a90`
- `0x180012730`
- `0x180012f6c`
- `0x1800165ac`
- `0x180016b78`
- `0x180023224`
- `0x180049300`
- `0x18004a4a4`
- `0x18004bb74`
- `0x18004d8a8`
- `0x18004e488`
- `0x18004faac`
- `0x180052668`
- `0x180054d8c`
- `0x1800587b0`
- `0x18006a63c`
- `0x18006a838`
- `0x18006a9bc`
- `0x180087e80`
- `0x180087ea4`
- `0x18008eecc`
- `0x180092e54`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800493b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800497e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049b38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049c50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a06d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800493b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800497e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049932`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049b38`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049c50`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180049dc0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a06d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a357`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800493ae`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800497e3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004992c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180049b32`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180049c4a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180049dba`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004a067`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004a1c2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004a351`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800493ae`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x1800497e3`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004992c`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180049b32`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180049c4a`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x180049dba`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004a067`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004a1c2`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18004a351`
- `MMDevAPI!__imp_RegisterForMediaCallback` at `0x180049f14`
- `MMDevAPI!__imp_RegisterForMediaCallback` at `0x180049f14`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CAudioClient::SetupAudioStreamWithAudioSrv(
        CAudioClient *this,
        __int64 a2,
        enum _AUDCLNT_SHAREMODE a3,
        unsigned int *a4,
        __int64 a5,
        __int64 a6,
        struct tWAVEFORMATEX *a7,
        GUID *a8,
        _DWORD *a9,
        __int64 a10,
        __int64 a11)
{
  GUID *v13; // r14
  CInProcLogger *v14; // rcx
  int v15; // eax
  unsigned int v16; // edi
  unsigned int v18; // ebx
  __int64 v19; // rax
  enum _AUDCLNT_SHAREMODE v20; // edi
  int v21; // eax
  CInProcLogger *v22; // rcx
  unsigned int v23; // eax
  __int64 v24; // rcx
  int v25; // ecx
  int v26; // eax
  CInProcLogger *v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30; // eax
  CInProcLogger *v31; // rcx
  int v32; // eax
  CInProcLogger *v33; // rcx
  CInProcLogger *v34; // rcx
  __int64 v35; // rax
  void *v36; // rcx
  __int64 v37; // rcx
  int v38; // eax
  unsigned int v39; // r14d
  int v40; // eax
  int v41; // ecx
  int v42; // eax
  CInProcLogger *v43; // rcx
  int RemoteStream; // eax
  CInProcLogger *v45; // rcx
  CInProcLogger *v46; // rcx
  int v47; // [rsp+20h] [rbp-E0h]
  int v48; // [rsp+20h] [rbp-E0h]
  int v49; // [rsp+20h] [rbp-E0h]
  int v50; // [rsp+20h] [rbp-E0h]
  int v51; // [rsp+20h] [rbp-E0h]
  int v52; // [rsp+20h] [rbp-E0h]
  DWORD CurrentThreadId; // [rsp+30h] [rbp-D0h]
  __int64 v54; // [rsp+30h] [rbp-D0h]
  __int64 v55; // [rsp+30h] [rbp-D0h]
  __int64 v56; // [rsp+30h] [rbp-D0h]
  __int64 v57; // [rsp+30h] [rbp-D0h]
  __int64 v58; // [rsp+30h] [rbp-D0h]
  __int64 v59; // [rsp+30h] [rbp-D0h]
  __int64 v60; // [rsp+30h] [rbp-D0h]
  __int64 v61; // [rsp+38h] [rbp-C8h]
  __int64 v62; // [rsp+38h] [rbp-C8h]
  __int64 v63; // [rsp+38h] [rbp-C8h]
  __int64 v64; // [rsp+38h] [rbp-C8h]
  __int64 v65; // [rsp+38h] [rbp-C8h]
  __int64 v66; // [rsp+38h] [rbp-C8h]
  __int64 v67; // [rsp+38h] [rbp-C8h]
  STRSAFE_LPWSTR v68; // [rsp+40h] [rbp-C0h] BYREF
  STRSAFE_LPWSTR v69; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int8 v70[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v71; // [rsp+58h] [rbp-A8h] BYREF
  enum _AUDCLNT_SHAREMODE v72; // [rsp+60h] [rbp-A0h]
  _QWORD v73[3]; // [rsp+68h] [rbp-98h] BYREF
  struct tWAVEFORMATEX *Src; // [rsp+80h] [rbp-80h]
  __int64 v75; // [rsp+88h] [rbp-78h]
  _QWORD *v76; // [rsp+90h] [rbp-70h]
  char v77; // [rsp+98h] [rbp-68h]
  PVOID BackTrace[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v79; // [rsp+B0h] [rbp-50h]
  wchar_t pszDest[1024]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+908h] [rbp+808h]

  v72 = a3;
  v13 = a8;
  Src = a7;
  v75 = a11;
  v73[0] = this;
  v73[1] = a10;
  v73[2] = a2;
  v76 = v73;
  v77 = 1;
  *(_OWORD *)BackTrace = 0;
  v79 = 0;
  v68 = pszDest;
  v69 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  CurrentThreadId = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v68, (unsigned __int64 *)&v69, 0, L"[%d]:", CurrentThreadId);
  StringCchPrintfExW(
    v68,
    (unsigned __int64)v69,
    &v68,
    (unsigned __int64 *)&v69,
    0,
    L"S1: %p (%x)",
    this,
    *(_DWORD *)a10);
  HIDWORD(v54) = HIDWORD(v79);
  v47 = (int)BackTrace[1];
  StringCchPrintfW(v68, (unsigned __int64)v69, L"[%p %p %p %p]", BackTrace[0]);
  CInProcLogger::AddLog(v14, pszDest);
  v15 = CAudioClient::CheckForDisconnection(this);
  v16 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x585,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)(unsigned int)v15,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v16;
  }
  if ( *((_BYTE *)this + 832) || *((_QWORD *)this + 36) )
  {
    v18 = -2004287486;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x589,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)0x88890002LL,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v18;
  }
  if ( a5 < 0 )
  {
    v18 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x58C,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)0x80070057LL,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v18;
  }
  if ( (*a4 & 0x10000) != 0 )
  {
    if ( !a8 )
      goto LABEL_13;
    v19 = *(_QWORD *)&a8->Data1 - *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1;
    if ( *(_QWORD *)&a8->Data1 == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1 )
      v19 = *(_QWORD *)a8->Data4 - *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4;
    if ( !v19 )
    {
LABEL_13:
      v18 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x590,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x80070057LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
  }
  if ( (*(_BYTE *)a4 & 3) != 0 )
  {
    v18 = -2004287455;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x593,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)0x88890021LL,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v18;
  }
  if ( (*a4 & 0x400000) != 0 )
  {
    v18 = -2004287455;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x596,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)0x88890021LL,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v18;
  }
  if ( (*a4 & 0x800000) != 0 )
  {
    v18 = -2004287455;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x599,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)0x88890021LL,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v18;
  }
  v20 = v72;
  if ( *((_DWORD *)this + 85) )
  {
    if ( v72 == AUDCLNT_SHAREMODE_EXCLUSIVE )
    {
      v18 = -2004287451;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59D,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890025LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
    if ( (*a4 & 0x40000) == 0 )
    {
      v18 = -2004287451;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A1,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890025LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
    if ( (*a4 & 0x20000) != 0 )
    {
      v18 = -2004287451;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5A5,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890025LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
  }
  if ( *((_DWORD *)this + 87) && (*a4 & 0x20000) != 0 )
  {
    v18 = -2004287455;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5A9,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)0x88890021LL,
      v47);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v18;
  }
  if ( (*a4 & 0x1000000) != 0 )
  {
    v21 = *((_DWORD *)this + 52);
    if ( v21 == 1 || !v21 && (*a4 & 0x20000) != 0 )
    {
      v18 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5AE,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x80070057LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
  }
  if ( !*((_QWORD *)this + 21) )
  {
    if ( !*((_QWORD *)this + 22) )
    {
      v18 = -2147467261;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B3,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x80004003LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
    if ( (*a4 & 0x20000) == 0 )
    {
      v18 = -2004287455;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5B4,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890021LL,
        v47);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
  }
  *(_OWORD *)BackTrace = 0;
  v79 = 0;
  v69 = pszDest;
  v68 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  LODWORD(v54) = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v54);
  LODWORD(v61) = *(_DWORD *)a10;
  StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S2: %p (%x)", this, v61);
  StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0], BackTrace[1], v79);
  CInProcLogger::AddLog(v22, pszDest);
  *a4 |= 2 - (*((_DWORD *)this + 85) != 0);
  v23 = *a4;
  v24 = *((_QWORD *)this + 24) - DEVINTERFACE_AUDIO_KEYWORDDETECTOR;
  if ( !v24 )
    v24 = *((_QWORD *)this + 25) - *((_QWORD *)&DEVINTERFACE_AUDIO_KEYWORDDETECTOR + 1);
  if ( !v24 )
  {
    v23 |= 0x400000u;
    *a4 = v23;
  }
  if ( *((_DWORD *)this + 54) )
  {
    v25 = *((_DWORD *)this + 55);
    if ( v25 )
    {
      if ( v25 != 2 )
        goto LABEL_50;
      v26 = v23 | 0x2000000;
    }
    else
    {
      v26 = v23 | 0x4000000;
    }
    *a4 = v26;
  }
LABEL_50:
  *((_DWORD *)this + 120) = v20;
  *(_OWORD *)BackTrace = 0;
  v79 = 0;
  v69 = pszDest;
  v68 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  LODWORD(v55) = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v55);
  LODWORD(v62) = *(_DWORD *)a10;
  StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S3: %p (%x)", this, v62);
  HIDWORD(v56) = HIDWORD(v79);
  v48 = (int)BackTrace[1];
  StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0]);
  CInProcLogger::AddLog(v27, pszDest);
  if ( *((_DWORD *)this + 202) )
  {
    v70[0] = 0;
    wil::details::unique_storage<wil::details::resource_policy<_PSM_APPSTATE_REGISTRATION *,void (*)(_PSM_APPSTATE_REGISTRATION *),&void PsmUnregisterAppStateChangeNotification(_PSM_APPSTATE_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_PSM_APPSTATE_REGISTRATION *,_PSM_APPSTATE_REGISTRATION *,0,std::nullptr_t>>::reset(
      (char *)this + 760,
      0);
    v28 = CAudioClient::RegisterSuspensionHandler(this, v70, (struct _PSM_APPSTATE_REGISTRATION **)this + 95);
    v16 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5D8,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)(unsigned int)v28,
        v48);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v16;
    }
    v29 = v70[0];
    *((_DWORD *)this + 195) = v70[0];
    if ( (*((_DWORD *)this + 120) == 1 || *((_DWORD *)this + 85) || *((_DWORD *)this + 90) || *((_DWORD *)this + 87))
      && v29 )
    {
      v18 = -2004287450;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5DE,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890026LL,
        v48);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<void *,unsigned long (*)(void *),&unsigned long PowerUnregisterSuspendResumeNotification(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      (char *)this + 768,
      0);
    v30 = CAudioClient::RegisterSuspensionHandlerForClassicApp(this, (void **)this + 96);
    v16 = v30;
    if ( v30 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5E5,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)(unsigned int)v30,
        v48);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v16;
    }
  }
  v71 = 0;
  v68 = (STRSAFE_LPWSTR)1024;
  *(_OWORD *)BackTrace = 0;
  v79 = 0;
  v69 = pszDest;
  if ( *((_QWORD *)this + 21) )
  {
    RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
    LODWORD(v56) = GetCurrentThreadId();
    StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v56);
    LODWORD(v63) = *(_DWORD *)a10;
    StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S4: %p (%x)", this, v63);
    StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0], BackTrace[1], v79);
    CInProcLogger::AddLog(v33, pszDest);
    BackTrace[0] = &v71;
    BackTrace[1] = 0;
    LOBYTE(v79) = 1;
    if ( !a8 )
      v13 = &GUID_00000000_0000_0000_0000_000000000000;
    v16 = CAudioClient::InitializeAudioServer(
            this,
            *((const unsigned __int16 **)this + 21),
            v72,
            *a4,
            Src,
            v13,
            (unsigned __int16 **)&BackTrace[1]);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(BackTrace);
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F2,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)v16,
        v50);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v16;
    }
  }
  else
  {
    RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
    LODWORD(v56) = GetCurrentThreadId();
    StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v56);
    LODWORD(v63) = *(_DWORD *)a10;
    StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S5: %p (%x)", this, v63);
    StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0], BackTrace[1], v79);
    CInProcLogger::AddLog(v31, pszDest);
    if ( !a8 )
      v13 = &GUID_00000000_0000_0000_0000_000000000000;
    v32 = CAudioClient::InitializeAudioServer(this, *((void **)this + 22), *a4, Src, v13);
    v16 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x5F7,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)(unsigned int)v32,
        v49);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v16;
    }
  }
  *(_OWORD *)BackTrace = 0;
  v79 = 0;
  v69 = pszDest;
  v68 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  LODWORD(v57) = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v57);
  LODWORD(v64) = *(_DWORD *)a10;
  StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S6: %p (%x)", this, v64);
  HIDWORD(v58) = HIDWORD(v79);
  v51 = (int)BackTrace[1];
  StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0]);
  CInProcLogger::AddLog(v34, pszDest);
  v35 = v71;
  v71 = 0;
  v36 = (void *)*((_QWORD *)this + 40);
  *((_QWORD *)this + 40) = v35;
  if ( v36 )
    operator delete(v36, 2u);
  v68 = (STRSAFE_LPWSTR)this;
  v37 = *((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v38 = Microsoft::WRL::Details::MakeAndInitialize<CAudioClient::CAudioClientNotificationDelegator,CAudioClient::CAudioClientNotificationDelegator,CAudioClient *>(
          (char *)this + 304,
          &v68);
  v39 = v38;
  if ( v38 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x601,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)(unsigned int)v38,
      v51);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v39;
  }
  v40 = RegisterForMediaCallback(32800, *((_QWORD *)this + 38));
  v16 = v40;
  if ( v40 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x605,
      (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
      (const char *)(unsigned int)v40,
      v51);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return v16;
  }
  *((_BYTE *)this + 848) = 1;
  v41 = *((_DWORD *)this + 52);
  v42 = *a4 & 0x20000;
  if ( v41 )
  {
    if ( v42 || v41 != 1 )
    {
      v18 = -2004287485;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62B,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890003LL,
        v51);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
    *a9 = 1;
  }
  else if ( v42 )
  {
    if ( v72 == AUDCLNT_SHAREMODE_EXCLUSIVE )
    {
      v18 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x60E,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x80070057LL,
        v51);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
    *a9 = (*((_BYTE *)this + 356) != 0) + 2;
    *((_DWORD *)this + 57) = 1;
  }
  else
  {
    if ( *((_BYTE *)this + 356) )
    {
      v18 = -2004287455;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x61F,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)0x88890021LL,
        v51);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v18;
    }
    *a9 = 0;
  }
  *(_OWORD *)BackTrace = 0;
  v79 = 0;
  v69 = pszDest;
  v68 = (STRSAFE_LPWSTR)1024;
  RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
  LODWORD(v58) = GetCurrentThreadId();
  StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v58);
  LODWORD(v65) = *(_DWORD *)a10;
  StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S7: %p (%x)", this, v65);
  StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0], BackTrace[1], v79);
  CInProcLogger::AddLog(v43, pszDest);
  RemoteStream = CAudioClient::CreateRemoteStream(this, (unsigned int)*a9, a5, a6);
  v16 = RemoteStream;
  if ( RemoteStream >= 0 )
  {
    *(_OWORD *)BackTrace = 0;
    v79 = 0;
    v69 = pszDest;
    v68 = (STRSAFE_LPWSTR)1024;
    RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
    LODWORD(v59) = GetCurrentThreadId();
    StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v59);
    LODWORD(v66) = *(_DWORD *)a10;
    StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S8: %p (%x)", this, v66);
    HIDWORD(v60) = HIDWORD(v79);
    v52 = (int)BackTrace[1];
    StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0]);
    CInProcLogger::AddLog(v45, pszDest);
    wistd::unique_ptr<tWAVEFORMATEX,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
      (char *)this + 856,
      0);
    BackTrace[0] = (char *)this + 856;
    BackTrace[1] = 0;
    LOBYTE(v79) = 1;
    v16 = CloneWaveFormat(Src, (struct tWAVEFORMATEX **)&BackTrace[1]);
    wil::details::out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<XvmMessage,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(BackTrace);
    if ( (v16 & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x635,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)v16,
        v52);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v16;
    }
    *((_QWORD *)this + 100) = *(_QWORD *)(a10 + 40);
    *((_DWORD *)this + 121) = *a4;
    *((_QWORD *)this + 102) = a6;
    *((_QWORD *)this + 103) = a5;
    *((_DWORD *)this + 60) = *(_DWORD *)(a10 + 1252);
    std::function_void___cdecl_void__::operator___lambda_b6c22cd56477191249fefae79ee210e7____0_(v75, v73);
    v77 = 0;
    *(_OWORD *)BackTrace = 0;
    v79 = 0;
    v69 = pszDest;
    v68 = (STRSAFE_LPWSTR)1024;
    RtlCaptureStackBackTrace(2u, 4u, BackTrace, 0);
    LODWORD(v60) = GetCurrentThreadId();
    StringCchPrintfExW(pszDest, 0x400u, &v69, (unsigned __int64 *)&v68, 0, L"[%d]:", v60);
    LODWORD(v67) = *(_DWORD *)a10;
    StringCchPrintfExW(v69, (unsigned __int64)v68, &v69, (unsigned __int64 *)&v68, 0, L"S9: %p (%x)", this, v67);
    StringCchPrintfW(v69, (unsigned __int64)v68, L"[%p %p %p %p]", BackTrace[0], BackTrace[1], v79);
    CInProcLogger::AddLog(v46, pszDest);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
    return 0;
  }
  else
  {
    if ( RemoteStream != -2005139333 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x631,
        (unsigned int)"avcore\\audiocore\\client\\audioclient\\audioclientcore.cpp",
        (const char *)(unsigned int)RemoteStream,
        a10);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
      lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
      return v16;
    }
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v71);
    lambda_b6c22cd56477191249fefae79ee210e7_::operator()(v73);
    return 2289827963LL;
  }
}

```

## disassembly

```asm
0x180049300  mov     [rsp-8+arg_8], rbx
0x180049305  push    rbp
0x180049306  push    rsi
0x180049307  push    rdi
0x180049308  push    r12
0x18004930a  push    r13
0x18004930c  push    r14
0x18004930e  push    r15
0x180049310  lea     rbp, [rsp-7D0h]
0x180049318  sub     rsp, 8D0h
0x18004931f  mov     rax, cs:__security_cookie
0x180049326  xor     rax, rsp
0x180049329  mov     [rbp+800h+var_40], rax
0x180049330  mov     r15, r9
0x180049333  mov     [rsp+900h+var_8A0], r8d
0x180049338  mov     rsi, rcx
0x18004933b  mov     r13, [rbp+800h+arg_40]
0x180049342  mov     r14, [rbp+800h+arg_38]
0x180049349  mov     r12, [rbp+800h+arg_48]
0x180049350  mov     rax, [rbp+800h+arg_30]
0x180049357  mov     [rbp+800h+Src], rax
0x18004935b  mov     rax, [rbp+800h+arg_50]
0x180049362  mov     [rbp+800h+var_878], rax
0x180049366  mov     [rsp+900h+var_898], rcx
0x18004936b  mov     [rsp+900h+var_890], r12
0x180049370  mov     [rsp+900h+var_888], rdx
0x180049375  lea     rbx, [rsp+900h+var_898]
0x18004937a  mov     [rbp+800h+var_870], rbx
0x18004937e  mov     [rbp+800h+var_868], 1
0x180049382  xorps   xmm0, xmm0
0x180049385  movups  xmmword ptr [rbp+800h+BackTrace], xmm0
0x180049389  movups  [rbp+800h+var_850], xmm0
0x18004938d  lea     rax, [rbp+800h+pszDest]
0x180049391  mov     [rsp+900h+var_8C0], rax
0x180049396  mov     edi, 400h
0x18004939b  mov     [rsp+900h+var_8B8], rdi
0x1800493a0  xor     r9d, r9d; BackTraceHash
0x1800493a3  lea     r8, [rbp+800h+BackTrace]; BackTrace
0x1800493a7  lea     edx, [r9+4]; FramesToCapture
0x1800493ab  lea     ecx, [rdx-2]; FramesToSkip
0x1800493ae  call    cs:__imp_RtlCaptureStackBackTrace
0x1800493b4  call    cs:__imp_GetCurrentThreadId
0x1800493ba  mov     dword ptr [rsp+900h+var_8D8+8], eax
0x1800493be  lea     rax, aD; "[%d]:"
0x1800493c5  mov     qword ptr [rsp+900h+var_8D8], rax; unsigned __int16 *
0x1800493ca  mov     [rsp+900h+var_8E0], 0; unsigned int
0x1800493d3  lea     r9, [rsp+900h+var_8B8]; unsigned __int64 *
0x1800493d8  lea     r8, [rsp+900h+var_8C0]; unsigned __int16 **
0x1800493dd  mov     edx, edi; unsigned __int64
0x1800493df  lea     rcx, [rbp+800h+pszDest]; pszDest
0x1800493e3  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x1800493e8  mov     eax, [r12]
0x1800493ec  mov     dword ptr [rsp+900h+var_8C8], eax
0x1800493f0  mov     qword ptr [rsp+900h+var_8D8+8], rsi
0x1800493f5  lea     rax, aS1PX; "S1: %p (%x)"
0x1800493fc  mov     qword ptr [rsp+900h+var_8D8], rax; unsigned __int16 *
0x180049401  mov     [rsp+900h+var_8E0], 0; unsigned int
0x18004940a  lea     r9, [rsp+900h+var_8B8]; unsigned __int64 *
0x18004940f  lea     r8, [rsp+900h+var_8C0]; unsigned __int16 **
0x180049414  mov     rdx, [rsp+900h+var_8B8]; unsigned __int64
0x180049419  mov     rcx, [rsp+900h+var_8C0]; pszDest
0x18004941e  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180049423  mov     rax, qword ptr [rbp+800h+var_850+8]
0x180049427  mov     qword ptr [rsp+900h+var_8D8+8], rax
0x18004942c  mov     rax, qword ptr [rbp+800h+var_850]
0x180049430  mov     qword ptr [rsp+900h+var_8D8], rax
0x180049435  mov     rax, [rbp+800h+BackTrace+8]
0x180049439  mov     [rsp+900h+var_8E0], rax; int
0x18004943e  mov     r9, [rbp+800h+BackTrace]
0x180049442  lea     r8, aPPPP; "[%p %p %p %p]"
0x180049449  mov     rdx, [rsp+900h+var_8B8]; unsigned __int64
0x18004944e  mov     rcx, [rsp+900h+var_8C0]; unsigned __int16 *
0x180049453  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180049458  lea     rdx, [rbp+800h+pszDest]; unsigned __int16 *
0x18004945c  call    ?AddLog@CInProcLogger@@QEAAXPEBG@Z; CInProcLogger::AddLog(ushort const *)
0x180049461  mov     rcx, rsi; this
0x180049464  call    ?CheckForDisconnection@CAudioClient@@AEAAJXZ; CAudioClient::CheckForDisconnection(void)
0x180049469  mov     edi, eax
0x18004946b  xor     ecx, ecx
0x18004946d  test    eax, eax
0x18004946f  jns     short loc_18004949F
0x180049471  mov     rcx, [rbp+808h]; this
0x180049478  mov     r9d, eax; char *
0x18004947b  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049482  mov     edx, 585h; void *
0x180049487  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004948c  nop
0x18004948d  lea     rcx, [rsp+900h+var_898]
0x180049492  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x180049497  nop
0x180049498  mov     eax, edi
0x18004949a  jmp     loc_18004A473
0x18004949f  cmp     [rsi+340h], cl
0x1800494a5  jnz     loc_18004A445
0x1800494ab  cmp     [rsi+120h], rcx
0x1800494b2  jnz     loc_18004A445
0x1800494b8  cmp     [rbp+800h+arg_20], rcx
0x1800494bf  jge     short loc_1800494F2
0x1800494c1  mov     rcx, [rbp+808h]; this
0x1800494c8  mov     ebx, 80070057h
0x1800494cd  mov     r9d, ebx; char *
0x1800494d0  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x1800494d7  mov     edx, 58Ch; void *
0x1800494dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800494e1  nop
0x1800494e2  lea     rcx, [rsp+900h+var_898]
0x1800494e7  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x1800494ec  nop
0x1800494ed  jmp     loc_18004A471
0x1800494f2  test    dword ptr [r15], 10000h
0x1800494f9  jz      short loc_18004954D
0x1800494fb  test    r14, r14
0x1800494fe  jz      short loc_18004951C
0x180049500  mov     rax, [r14]
0x180049503  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004950a  jnz     short loc_180049517
0x18004950c  mov     rax, [r14+8]
0x180049510  sub     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180049517  test    rax, rax
0x18004951a  jnz     short loc_18004954D
0x18004951c  mov     rcx, [rbp+808h]; this
0x180049523  mov     ebx, 80070057h
0x180049528  mov     r9d, ebx; char *
0x18004952b  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049532  mov     edx, 590h; void *
0x180049537  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004953c  nop
0x18004953d  lea     rcx, [rsp+900h+var_898]
0x180049542  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x180049547  nop
0x180049548  jmp     loc_18004A471
0x18004954d  test    byte ptr [r15], 3
0x180049551  jz      short loc_180049584
0x180049553  mov     rcx, [rbp+808h]; this
0x18004955a  mov     ebx, 88890021h
0x18004955f  mov     r9d, ebx; char *
0x180049562  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049569  mov     edx, 593h; void *
0x18004956e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049573  nop
0x180049574  lea     rcx, [rsp+900h+var_898]
0x180049579  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x18004957e  nop
0x18004957f  jmp     loc_18004A471
0x180049584  test    dword ptr [r15], 400000h
0x18004958b  jz      short loc_1800495BE
0x18004958d  mov     rcx, [rbp+808h]; this
0x180049594  mov     ebx, 88890021h
0x180049599  mov     r9d, ebx; char *
0x18004959c  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x1800495a3  mov     edx, 596h; void *
0x1800495a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800495ad  nop
0x1800495ae  lea     rcx, [rsp+900h+var_898]
0x1800495b3  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x1800495b8  nop
0x1800495b9  jmp     loc_18004A471
0x1800495be  test    dword ptr [r15], 800000h
0x1800495c5  jz      short loc_1800495F8
0x1800495c7  mov     rcx, [rbp+808h]; this
0x1800495ce  mov     ebx, 88890021h
0x1800495d3  mov     r9d, ebx; char *
0x1800495d6  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x1800495dd  mov     edx, 599h; void *
0x1800495e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800495e7  nop
0x1800495e8  lea     rcx, [rsp+900h+var_898]
0x1800495ed  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x1800495f2  nop
0x1800495f3  jmp     loc_18004A471
0x1800495f8  mov     edx, 20000h
0x1800495fd  mov     edi, [rsp+900h+var_8A0]
0x180049601  cmp     [rsi+154h], ecx
0x180049607  jz      loc_1800496B3
0x18004960d  cmp     edi, 1
0x180049610  jnz     short loc_180049643
0x180049612  mov     rcx, [rbp+808h]; this
0x180049619  mov     ebx, 88890025h
0x18004961e  mov     r9d, ebx; char *
0x180049621  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049628  mov     edx, 59Dh; void *
0x18004962d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049632  nop
0x180049633  lea     rcx, [rsp+900h+var_898]
0x180049638  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x18004963d  nop
0x18004963e  jmp     loc_18004A471
0x180049643  test    dword ptr [r15], 40000h
0x18004964a  jnz     short loc_18004967D
0x18004964c  mov     rcx, [rbp+808h]; this
0x180049653  mov     ebx, 88890025h
0x180049658  mov     r9d, ebx; char *
0x18004965b  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049662  mov     edx, 5A1h; void *
0x180049667  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004966c  nop
0x18004966d  lea     rcx, [rsp+900h+var_898]
0x180049672  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x180049677  nop
0x180049678  jmp     loc_18004A471
0x18004967d  test    [r15], edx
0x180049680  jz      short loc_1800496B3
0x180049682  mov     rcx, [rbp+808h]; this
0x180049689  mov     ebx, 88890025h
0x18004968e  mov     r9d, ebx; char *
0x180049691  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049698  mov     edx, 5A5h; void *
0x18004969d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800496a2  nop
0x1800496a3  lea     rcx, [rsp+900h+var_898]
0x1800496a8  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x1800496ad  nop
0x1800496ae  jmp     loc_18004A471
0x1800496b3  cmp     [rsi+15Ch], ecx
0x1800496b9  jz      short loc_1800496F1
0x1800496bb  test    [r15], edx
0x1800496be  jz      short loc_1800496F1
0x1800496c0  mov     rcx, [rbp+808h]; this
0x1800496c7  mov     ebx, 88890021h
0x1800496cc  mov     r9d, ebx; char *
0x1800496cf  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x1800496d6  mov     edx, 5A9h; void *
0x1800496db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800496e0  nop
0x1800496e1  lea     rcx, [rsp+900h+var_898]
0x1800496e6  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x1800496eb  nop
0x1800496ec  jmp     loc_18004A471
0x1800496f1  test    dword ptr [r15], 1000000h
0x1800496f8  jz      short loc_18004973F
0x1800496fa  mov     eax, [rsi+0D0h]
0x180049700  cmp     eax, 1
0x180049703  jz      short loc_18004970E
0x180049705  test    eax, eax
0x180049707  jnz     short loc_18004973F
0x180049709  test    [r15], edx
0x18004970c  jz      short loc_18004973F
0x18004970e  mov     rcx, [rbp+808h]; this
0x180049715  mov     ebx, 80070057h
0x18004971a  mov     r9d, ebx; char *
0x18004971d  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049724  mov     edx, 5AEh; void *
0x180049729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004972e  nop
0x18004972f  lea     rcx, [rsp+900h+var_898]
0x180049734  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x180049739  nop
0x18004973a  jmp     loc_18004A471
0x18004973f  cmp     [rsi+0A8h], rcx
0x180049746  jnz     short loc_1800497B8
0x180049748  cmp     [rsi+0B0h], rcx
0x18004974f  jnz     short loc_180049782
0x180049751  mov     rcx, [rbp+808h]; this
0x180049758  mov     ebx, 80004003h
0x18004975d  mov     r9d, ebx; char *
0x180049760  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x180049767  mov     edx, 5B3h; void *
0x18004976c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049771  nop
0x180049772  lea     rcx, [rsp+900h+var_898]
0x180049777  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x18004977c  nop
0x18004977d  jmp     loc_18004A471
0x180049782  test    [r15], edx
0x180049785  jnz     short loc_1800497B8
0x180049787  mov     rcx, [rbp+808h]; this
0x18004978e  mov     ebx, 88890021h
0x180049793  mov     r9d, ebx; char *
0x180049796  lea     r8, aAvcoreAudiocor_42; "avcore\\audiocore\\client\\audioclient"...
0x18004979d  mov     edx, 5B4h; void *
0x1800497a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800497a7  nop
0x1800497a8  lea     rcx, [rsp+900h+var_898]
0x1800497ad  call    _lambda_b6c22cd56477191249fefae79ee210e7___operator__
0x1800497b2  nop
0x1800497b3  jmp     loc_18004A471
0x1800497b8  xorps   xmm0, xmm0
0x1800497bb  movups  xmmword ptr [rbp+800h+BackTrace], xmm0
0x1800497bf  movups  [rbp+800h+var_850], xmm0
0x1800497c3  lea     rax, [rbp+800h+pszDest]
0x1800497c7  mov     [rsp+900h+var_8B8], rax
0x1800497cc  mov     [rsp+900h+var_8C0], 400h
0x1800497d5  xor     r9d, r9d; BackTraceHash
0x1800497d8  lea     r8, [rbp+800h+BackTrace]; BackTrace
0x1800497dc  lea     edx, [r9+4]; FramesToCapture
0x1800497e0  lea     ecx, [rdx-2]; FramesToSkip
0x1800497e3  call    cs:__imp_RtlCaptureStackBackTrace
0x1800497e9  call    cs:__imp_GetCurrentThreadId
0x1800497ef  mov     dword ptr [rsp+900h+var_8D8+8], eax
0x1800497f3  lea     rax, aD; "[%d]:"
0x1800497fa  mov     qword ptr [rsp+900h+var_8D8], rax; unsigned __int16 *
0x1800497ff  mov     [rsp+900h+var_8E0], 0; unsigned int
0x180049808  lea     r9, [rsp+900h+var_8C0]; unsigned __int64 *
0x18004980d  lea     r8, [rsp+900h+var_8B8]; unsigned __int16 **
0x180049812  mov     edx, 400h; unsigned __int64
0x180049817  lea     rcx, [rbp+800h+pszDest]; pszDest
0x18004981b  call    ?StringCchPrintfExW@@YAJPEAG_KPEAPEAGPEA_KKPEBGZZ; StringCchPrintfExW(ushort *,unsigned __int64,ushort * *,unsigned __int64 *,ulong,ushort const *,...)
0x180049820  mov     eax, [r12]
0x180049824  mov     dword ptr [rsp+900h+var_8C8], eax
0x180049828  mov     qword ptr [rsp+900h+var_8D8+8], rsi
  ... truncated ...
```
