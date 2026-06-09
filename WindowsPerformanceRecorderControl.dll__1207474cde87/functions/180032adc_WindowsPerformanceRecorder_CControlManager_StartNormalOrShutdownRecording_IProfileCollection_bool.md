# WindowsPerformanceRecorder::CControlManager::StartNormalOrShutdownRecording(IProfileCollection *,bool)

- ea: `0x180032adc`
- end: `0x1800332c0`
- name: `?StartNormalOrShutdownRecording@CControlManager@WindowsPerformanceRecorder@@AEAAJPEAUIProfileCollection@@_N@Z`
- size: `2020`
- prototype: `__int64 __fastcall(WindowsPerformanceRecorder::CControlManager *__hidden this, struct IProfileCollection *, bool)`
- caller_count: `2`
- callee_count: `41`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180032620`
- `0x180061f90`

## callees

- `0x180007c40`
- `0x180008330`
- `0x1800192e8`
- `0x18001a92c`
- `0x18001bf98`
- `0x18001d1bc`
- `0x18001e6b8`
- `0x18001e6e0`
- `0x18001ea58`
- `0x1800234f0`
- `0x180023b34`
- `0x180024270`
- `0x1800248d8`
- `0x18002c430`
- `0x180032adc`
- `0x180035004`
- `0x180036d08`
- `0x180036d94`
- `0x180039084`
- `0x180040a04`
- `0x180042638`
- `0x1800449a0`
- `0x1800483c8`
- `0x18004865c`
- `0x1800490f8`
- `0x18004a61c`
- `0x18004a664`
- `0x18004a6ec`
- `0x18004b024`
- `0x18004ed10`
- `0x180058e54`
- `0x180059820`
- `0x18005a0c8`
- `0x18005aa04`
- `0x18005c660`
- `0x18005d068`
- `0x18005d868`
- `0x18005f6f4`
- `0x180060168`
- `0x180071b28`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x180032d3e`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetActiveProcessorCount` at `0x180032d3e`
- `ntdll!NtQuerySystemInformation` at `0x180032d2b`
- `ntdll!NtQuerySystemInformation` at `0x180032d2b`

## string_xrefs

- `0x180032e93`: `COMGUARD`

## pseudocode

```c
// Hidden C++ exception states: #wind=7 #try_helpers=2
__int64 __fastcall WindowsPerformanceRecorder::CControlManager::StartNormalOrShutdownRecording(
        WindowsPerformanceRecorder::CControlManager *this,
        struct IProfileCollection *a2,
        unsigned __int8 a3)
{
  int TempDirectoryPath; // edi
  __int64 v7; // rbx
  unsigned __int16 *v8; // r13
  int RunningProfileTraceType; // eax
  int v10; // eax
  char v11; // r15
  int v12; // eax
  const unsigned __int16 *v13; // r9
  char *v14; // r13
  WindowsPerformanceRecorder::CControlManager *v15; // rcx
  bool v16; // r8
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v17; // r15
  struct WindowsPerformanceRecorder::CETWProperties::CEventSession **i; // rdi
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v19; // r12
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession **v20; // r13
  const struct WindowsPerformanceRecorder::CETWProperties::CEventSession *v21; // r15
  const unsigned __int16 *SessionName; // rax
  const char *v23; // rax
  int v25; // edi
  signed int v26; // edi
  __int64 InstanceNameScopedData; // rax
  int v28; // eax
  unsigned int v29; // r15d
  __int64 v30; // rcx
  int v31; // eax
  WindowsPerformanceRecorder::CControlManager *v32; // rcx
  __int64 *v33; // r15
  __int64 *v34; // r13
  _DWORD *v35; // r12
  __int64 v36; // r8
  unsigned int v37; // edx
  __int64 v38; // rcx
  int started; // eax
  __int64 *v40; // r15
  __int64 *v41; // r12
  char *v42; // r15
  int Format; // [rsp+20h] [rbp-B8h]
  char *v44; // [rsp+28h] [rbp-B0h]
  void (__fastcall ***v45)(_QWORD, GUID *, _QWORD *); // [rsp+30h] [rbp-A8h] BYREF
  char v46; // [rsp+38h] [rbp-A0h]
  char *v47; // [rsp+40h] [rbp-98h]
  __int64 v48; // [rsp+48h] [rbp-90h]
  __int64 v49; // [rsp+50h] [rbp-88h] BYREF
  __int64 v50; // [rsp+58h] [rbp-80h] BYREF
  __int64 SystemInformation; // [rsp+60h] [rbp-78h] BYREF
  __int64 v52; // [rsp+68h] [rbp-70h] BYREF
  unsigned __int16 *v53[13]; // [rsp+70h] [rbp-68h] BYREF
  WindowsPerformanceRecorder::CETWProperties *ReturnLength; // [rsp+F8h] [rbp+20h] BYREF

  v53[3] = (unsigned __int16 *)-2LL;
  TempDirectoryPath = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(this);
  LODWORD(v45) = TempDirectoryPath;
  if ( TempDirectoryPath >= 0 )
  {
    if ( !a2 )
      TempDirectoryPath = -2147467261;
    LODWORD(v45) = TempDirectoryPath;
  }
  v7 = 0;
  v48 = 0;
  v8 = 0;
  v47 = 0;
  v46 = 0;
  if ( TempDirectoryPath >= 0 )
  {
    RunningProfileTraceType = WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(this);
    TempDirectoryPath = RunningProfileTraceType;
    LODWORD(v45) = RunningProfileTraceType;
    if ( !RunningProfileTraceType )
    {
      v10 = *((_DWORD *)this + 142);
      if ( (v10 & 1) != 0 )
      {
        TempDirectoryPath = -984076287;
        goto LABEL_9;
      }
      if ( (v10 & 2) != 0 )
      {
        TempDirectoryPath = -984076265;
        goto LABEL_9;
      }
      if ( (v10 & 8) != 0 )
      {
        TempDirectoryPath = -984076274;
LABEL_9:
        LODWORD(v45) = TempDirectoryPath;
LABEL_10:
        v11 = 0;
        goto LABEL_67;
      }
      goto LABEL_18;
    }
    if ( RunningProfileTraceType == -984076288 )
    {
      TempDirectoryPath = 0;
      LODWORD(v45) = 0;
      goto LABEL_18;
    }
    LODWORD(v45) = RunningProfileTraceType;
    if ( RunningProfileTraceType >= 0 )
    {
LABEL_18:
      if ( !*(_DWORD *)(*((_QWORD *)this + 66) - 16LL) )
      {
        TempDirectoryPath = WindowsPerformanceRecorder::Impl::GetTempDirectoryPath((__int64)this + 528);
        LODWORD(v45) = TempDirectoryPath;
      }
      if ( TempDirectoryPath >= 0 )
      {
        ReturnLength = (WindowsPerformanceRecorder::CETWProperties *)operator new(0x1A8u);
        v7 = WindowsPerformanceRecorder::CETWProperties::CETWProperties(ReturnLength);
        v48 = v7;
        v12 = WindowsPerformanceRecorder::CETWProperties::Initialize(
                (WindowsPerformanceRecorder::CETWProperties *)v7,
                a2,
                this,
                a3);
        TempDirectoryPath = v12;
        if ( v12 < 0 )
        {
          LODWORD(v45) = v12;
        }
        else
        {
          v14 = *(char **)(v7 + 320);
          v47 = v14;
          if ( (Microsoft_Windows_Performance_Recorder_ControlEnableBits & 0x10) != 0 )
            McTemplateU0z_EventWriteTransfer(
              &WindowsPerformanceRecorderControlProvider_Context,
              Perf_WPRProfileIds,
              *(_QWORD *)(v7 + 328));
          WindowsPerformanceRecorder::TelemetryUsage(
            (WindowsPerformanceRecorder *)0x2000,
            (unsigned __int64)"StartNormalOrShutdownRecording",
            v14,
            v13);
          if ( *(_BYTE *)(v7 + 416) )
          {
            v17 = *(struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v7 + 16);
            for ( i = *(struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v7 + 8); i != v17; ++i )
              WindowsPerformanceRecorder::CControlManager::SetSessionBuffersizeToLarge(v15, *i);
          }
          v19 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v7 + 8);
          v20 = *(const struct WindowsPerformanceRecorder::CETWProperties::CEventSession ***)(v7 + 16);
          while ( v19 != v20 )
          {
            v21 = *v19;
            if ( (int)WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(this, *v19) >= 0 )
            {
              TempDirectoryPath = -984076268;
              LODWORD(v45) = -984076268;
              SessionName = WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v21);
              WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
                this,
                3310891028LL,
                2,
                &IID_IControlManager,
                SessionName);
              v23 = (const char *)WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(v21);
              WindowsPerformanceRecorder::TraceHR(
                (WindowsPerformanceRecorder *)2,
                "StartNormalOrShutdownRecording",
                (const char *)0xA45,
                0xC5583014,
                "%ws",
                v23);
              goto LABEL_10;
            }
            if ( *(_DWORD *)v21 == 5 )
            {
              SystemInformation = 0;
              LODWORD(ReturnLength) = 0;
              if ( NtQuerySystemInformation(SystemDeviceInformation|0x80, &SystemInformation, 8u, (PULONG)&ReturnLength) >= 0
                && GetActiveProcessorCount(0xFFFFu) < (unsigned int)SystemInformation
                && !*((_BYTE *)v21 + 210) )
              {
                ATL::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>(
                  &v49,
                  (void (__fastcall ***)(_QWORD, GUID *, _QWORD *))a2);
                if ( !v49 )
                {
                  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v49);
                  if ( v7 )
                    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
                  v48 = 0;
                  return 2147500034LL;
                }
                v45 = 0;
                v25 = (*(__int64 (__fastcall **)(__int64, void (__fastcall ****)(_QWORD, GUID *, _QWORD *)))(*(_QWORD *)v49 + 96LL))(
                        v49,
                        &v45);
                if ( v25 < 0 )
                {
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v49);
                  if ( v7 )
                    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
                  v48 = 0;
                  return (unsigned int)v25;
                }
                ATL::CComQIPtr<WindowsPerformanceRecorder::ITraceMergePropertyElement,&__s_GUID const _GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7>::CComQIPtr<WindowsPerformanceRecorder::ITraceMergePropertyElement,&__s_GUID const _GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7>(
                  &v50,
                  v45);
                if ( !v50 )
                {
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v49);
                  if ( v7 )
                    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
                  v48 = 0;
                  return 2147500034LL;
                }
                v52 = 0;
                v26 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v50 + 24LL))(v50, &v52);
                if ( v26 < 0 )
                {
                  WindowsPerformanceRecorder::TraceHR(
                    (WindowsPerformanceRecorder *)2,
                    "StartNormalOrShutdownRecording",
                    (const char *)0xA5F,
                    v26,
                    "COMGUARD",
                    v44);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v49);
                  if ( v7 )
                    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
                  v48 = 0;
                  return (unsigned int)v26;
                }
                if ( !*(_BYTE *)(v52 + 58) )
                {
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
                  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                  ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v49);
                  if ( v7 )
                    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
                  v48 = 0;
                  return 3310880319LL;
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v50);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v45);
                ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(&v49);
              }
            }
            ++v19;
          }
          if ( a3 && *(_DWORD *)(v7 + 256) == 1 && !*((_BYTE *)this + 572)
            || *(_DWORD *)(v7 + 256) == 2 && *((_BYTE *)this + 572) )
          {
            TempDirectoryPath = -984068082;
            LODWORD(v45) = -984068082;
          }
          else
          {
            TempDirectoryPath = WindowsPerformanceRecorder::CControlManager::SetProgressHandlerRuntimeState(
                                  this,
                                  (struct WindowsPerformanceRecorder::CETWProperties *)v7,
                                  v16,
                                  1);
            LODWORD(v45) = TempDirectoryPath;
            if ( TempDirectoryPath >= 0 )
            {
              v31 = WindowsPerformanceRecorder::CControlManager::PresetSampledCounter(
                      this,
                      (struct WindowsPerformanceRecorder::CETWProperties *)v7);
              TempDirectoryPath = v31;
              if ( v31 >= 0 )
              {
                v46 = 1;
                v33 = *(__int64 **)(v7 + 8);
                v34 = *(__int64 **)(v7 + 16);
                while ( v33 != v34 )
                {
                  v35 = (_DWORD *)*v33;
                  TempDirectoryPath = WindowsPerformanceRecorder::CControlManager::StartEventSession(
                                        (__int64)this,
                                        (const unsigned __int16 *)v47,
                                        *v33,
                                        *(_DWORD *)(v7 + 256));
                  LODWORD(v45) = TempDirectoryPath;
                  if ( TempDirectoryPath < 0 )
                    goto LABEL_64;
                  if ( *v35 == 1
                    && (unsigned __int8)WindowsPerformanceRecorder::CETWProperties::CEventSession::HasSystemKeywordType(
                                          v35,
                                          1) )
                  {
                    WindowsPerformanceRecorder::CControlManager::CaptureStateRundown(v38, v35, v37);
                  }
                  TempDirectoryPath = WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Update(
                                        this,
                                        1,
                                        v36);
                  LODWORD(v45) = TempDirectoryPath;
                  if ( TempDirectoryPath < 0 )
                    goto LABEL_64;
                  ++v33;
                }
                if ( !a3
                  || !*((_BYTE *)this + 572)
                  || (started = WindowsPerformanceRecorder::CControlManager::EnableSoftRebootPreservation(
                                  v32,
                                  (struct WindowsPerformanceRecorder::CETWProperties *)v7),
                      TempDirectoryPath = started,
                      started >= 0) )
                {
                  started = WindowsPerformanceRecorder::CControlManager::StartHardwareCounter(
                              this,
                              (struct WindowsPerformanceRecorder::CETWProperties *)v7);
                  TempDirectoryPath = started;
                }
                LODWORD(v45) = started;
              }
              else
              {
                LODWORD(v45) = v31;
                WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(
                  this,
                  (struct WindowsPerformanceRecorder::CETWProperties *)v7);
              }
            }
          }
LABEL_64:
          v8 = (unsigned __int16 *)v47;
        }
      }
    }
  }
  v11 = 0;
  LOBYTE(ReturnLength) = 0;
  if ( TempDirectoryPath >= 0 )
  {
    TempDirectoryPath = WindowsPerformanceRecorder::CControlManager::VerifyAllProvidersEnabled(this, v8);
    LODWORD(v45) = TempDirectoryPath;
    v11 = (char)ReturnLength;
  }
LABEL_67:
  WindowsPerformanceRecorder::CXmlWriter::CXmlWriter((WindowsPerformanceRecorder::CXmlWriter *)v53);
  if ( TempDirectoryPath >= 0 )
  {
    InstanceNameScopedData = WindowsPerformanceRecorder::CInstanceNameScopedObjectImpl<WindowsPerformanceRecorder::CProfile>::GetInstanceNameScopedData((char *)this + 216);
    v28 = WindowsPerformanceRecorder::CETWProperties::TranslateToXML(
            (WindowsPerformanceRecorder::CETWProperties *)v7,
            (struct WindowsPerformanceRecorder::CXmlWriter *)v53,
            v11,
            0,
            (struct WindowsPerformanceRecorder::CProfilesCache *)(InstanceNameScopedData + 40));
    TempDirectoryPath = v28;
    if ( v28 < 0 )
    {
      LODWORD(v45) = v28;
    }
    else
    {
      TempDirectoryPath = WindowsPerformanceRecorder::CControlManager::SaveStateInRegistry(
                            (const BYTE **)this,
                            (const BYTE *)v53[0],
                            L"Normal",
                            a3 ^ 1u,
                            a3,
                            1);
      LODWORD(v45) = TempDirectoryPath;
      v29 = *(_DWORD *)(v7 + 256);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        (__int64 *)&ReturnLength,
        (char *)v53[0]);
      WindowsPerformanceRecorder::CControlManager::LogProfileXmlEvent(v30, &ReturnLength, v29);
      WindowsPerformanceRecorder::Status::CSessionInfo::~CSessionInfo((WindowsPerformanceRecorder::Status::CSessionInfo *)&ReturnLength);
    }
  }
  std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(v53);
  if ( TempDirectoryPath < 0 )
  {
    if ( v46 )
    {
      if ( v7 )
      {
        v40 = *(__int64 **)(v7 + 8);
        v41 = *(__int64 **)(v7 + 16);
        while ( v40 != v41 )
          WindowsPerformanceRecorder::CControlManager::CancelEventSession(
            this,
            (const unsigned __int16 *)v47,
            *v40++,
            *(_DWORD *)(v7 + 256),
            0);
        WindowsPerformanceRecorder::CControlManager::RestoreHardwareCounter(
          this,
          (struct WindowsPerformanceRecorder::CETWProperties *)v7);
      }
      WindowsPerformanceRecorder::CControlManager::ClearStateInRegistry(this, L"Normal");
    }
    v42 = v47;
    WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(
      this,
      (unsigned int)TempDirectoryPath,
      1,
      &IID_IControlManager,
      v47);
    WindowsPerformanceRecorder::TelemetryError(
      (WindowsPerformanceRecorder *)0x2000,
      (unsigned __int64)"StartNormalOrShutdownRecording",
      v42,
      (const unsigned __int16 *)(unsigned int)TempDirectoryPath,
      Format);
  }
  WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_End(this, TempDirectoryPath, 0);
  if ( v7 )
    (**(void (__fastcall ***)(__int64, __int64))v7)(v7, 1);
  return (unsigned int)TempDirectoryPath;
}

```

## disassembly

```asm
0x180032adc  mov     rax, rsp
0x180032adf  mov     [rax+18h], r8b
0x180032ae3  mov     [rax+10h], rdx
0x180032ae7  mov     [rax+8], rcx
0x180032aeb  push    rbx
0x180032aec  push    rdi
0x180032aed  push    r12
0x180032aef  push    r13
0x180032af1  push    r14
0x180032af3  push    r15
0x180032af5  sub     rsp, 0A8h
0x180032afc  mov     qword ptr [rax-50h], 0FFFFFFFFFFFFFFFEh
0x180032b04  mov     r12b, r8b
0x180032b07  mov     r15, rdx
0x180032b0a  mov     r14, rcx
0x180032b0d  call    ?ControlProgressHandler_Begin@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::ControlProgressHandler_Begin(void)
0x180032b12  mov     edi, eax
0x180032b14  mov     dword ptr [rsp+0D8h+var_A8], eax
0x180032b18  test    eax, eax
0x180032b1a  js      short loc_180032B2B
0x180032b1c  mov     eax, 80004003h
0x180032b21  test    r15, r15
0x180032b24  cmovz   edi, eax
0x180032b27  mov     dword ptr [rsp+0D8h+var_A8], edi
0x180032b2b  xor     ebx, ebx
0x180032b2d  mov     [rsp+0D8h+var_90], rbx
0x180032b32  xor     r13d, r13d
0x180032b35  mov     [rsp+0D8h+var_98], r13
0x180032b3a  mov     [rsp+0D8h+var_A0], r13b
0x180032b3f  test    edi, edi
0x180032b41  js      loc_180032FC4
0x180032b47  mov     rcx, r14; this
0x180032b4a  call    ?GetRunningProfileTraceType@CControlManager@WindowsPerformanceRecorder@@AEAAJXZ; WindowsPerformanceRecorder::CControlManager::GetRunningProfileTraceType(void)
0x180032b4f  mov     edi, eax
0x180032b51  mov     dword ptr [rsp+0D8h+var_A8], eax
0x180032b55  test    eax, eax
0x180032b57  jnz     short loc_180032B8B
0x180032b59  mov     eax, [r14+238h]
0x180032b60  test    al, 1
0x180032b62  jz      short loc_180032B75
0x180032b64  mov     edi, 0C5583001h
0x180032b69  mov     dword ptr [rsp+0D8h+var_A8], edi
0x180032b6d  xor     r15b, r15b
0x180032b70  jmp     loc_180032FF8
0x180032b75  test    al, 2
0x180032b77  jz      short loc_180032B80
0x180032b79  mov     edi, 0C5583017h
0x180032b7e  jmp     short loc_180032B69
0x180032b80  test    al, 8
0x180032b82  jz      short loc_180032BA6
0x180032b84  mov     edi, 0C558300Eh
0x180032b89  jmp     short loc_180032B69
0x180032b8b  cmp     eax, 0C5583000h
0x180032b90  jnz     short loc_180032B9A
0x180032b92  xor     edi, edi
0x180032b94  mov     dword ptr [rsp+0D8h+var_A8], edi
0x180032b98  jmp     short loc_180032BA6
0x180032b9a  mov     dword ptr [rsp+0D8h+var_A8], eax
0x180032b9e  test    eax, eax
0x180032ba0  js      loc_180032FC4
0x180032ba6  lea     rcx, [r14+210h]
0x180032bad  mov     rax, [rcx]
0x180032bb0  cmp     dword ptr [rax-10h], 0
0x180032bb4  jnz     short loc_180032BC1
0x180032bb6  call    ?GetTempDirectoryPath@Impl@WindowsPerformanceRecorder@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WindowsPerformanceRecorder::Impl::GetTempDirectoryPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180032bbb  mov     edi, eax
0x180032bbd  mov     dword ptr [rsp+0D8h+var_A8], eax
0x180032bc1  test    edi, edi
0x180032bc3  js      loc_180032FC4
0x180032bc9  mov     ecx, 1A8h; Size
0x180032bce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180032bd3  mov     [rsp+0D8h+ReturnLength], rax
0x180032bdb  mov     rcx, rax; this
0x180032bde  call    ??0CETWProperties@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CETWProperties::CETWProperties(void)
0x180032be3  mov     rbx, rax
0x180032be6  mov     [rsp+0D8h+var_90], rax
0x180032beb  mov     r9b, r12b; bool
0x180032bee  mov     r8, r14; struct WindowsPerformanceRecorder::CControlManager *
0x180032bf1  mov     rdx, r15; struct IProfileCollection *
0x180032bf4  mov     rcx, rax; this
0x180032bf7  call    ?Initialize@CETWProperties@WindowsPerformanceRecorder@@QEAAJPEAUIProfileCollection@@PEAVCControlManager@2@_N@Z; WindowsPerformanceRecorder::CETWProperties::Initialize(IProfileCollection *,WindowsPerformanceRecorder::CControlManager *,bool)
0x180032bfc  mov     edi, eax
0x180032bfe  test    eax, eax
0x180032c00  js      loc_1800331A2
0x180032c06  mov     r13, [rbx+140h]
0x180032c0d  mov     [rsp+0D8h+var_98], r13
0x180032c12  test    byte ptr cs:Microsoft_Windows_Performance_Recorder_ControlEnableBits, 10h
0x180032c19  jz      short loc_180032C35
0x180032c1b  mov     r8, [rbx+148h]
0x180032c22  lea     rdx, Perf_WPRProfileIds
0x180032c29  lea     rcx, WindowsPerformanceRecorderControlProvider_Context
0x180032c30  call    McTemplateU0z_EventWriteTransfer
0x180032c35  mov     r8, r13; char *
0x180032c38  lea     rdx, aStartnormalors; "StartNormalOrShutdownRecording"
0x180032c3f  mov     ecx, 2000h; this
0x180032c44  call    ?TelemetryUsage@WindowsPerformanceRecorder@@YAX_KPEBDPEBG@Z; WindowsPerformanceRecorder::TelemetryUsage(unsigned __int64,char const *,ushort const *)
0x180032c49  cmp     byte ptr [rbx+1A0h], 0
0x180032c50  jz      short loc_180032C6D
0x180032c52  mov     r15, [rbx+10h]
0x180032c56  mov     rdi, [rbx+8]
0x180032c5a  jmp     short loc_180032C68
0x180032c5c  mov     rdx, [rdi]; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180032c5f  call    ?SetSessionBuffersizeToLarge@CControlManager@WindowsPerformanceRecorder@@AEAAXPEAUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::SetSessionBuffersizeToLarge(WindowsPerformanceRecorder::CETWProperties::CEventSession *)
0x180032c64  add     rdi, 8
0x180032c68  cmp     rdi, r15
0x180032c6b  jnz     short loc_180032C5C
0x180032c6d  mov     r12, [rbx+8]
0x180032c71  mov     r13, [rbx+10h]
0x180032c75  cmp     r12, r13
0x180032c78  jz      loc_180032F7E
0x180032c7e  mov     r15, [r12]
0x180032c82  mov     rdx, r15; struct WindowsPerformanceRecorder::CETWProperties::CEventSession *
0x180032c85  mov     rcx, r14; this
0x180032c88  call    ?SetRunningEventTraceProperties@CControlManager@WindowsPerformanceRecorder@@AEAAJAEBUCEventSession@CETWProperties@2@@Z; WindowsPerformanceRecorder::CControlManager::SetRunningEventTraceProperties(WindowsPerformanceRecorder::CETWProperties::CEventSession const &)
0x180032c8d  test    eax, eax
0x180032c8f  js      short loc_180032CF6
0x180032c91  mov     edi, 0C5583014h
0x180032c96  mov     dword ptr [rsp+0D8h+var_A8], edi
0x180032c9a  mov     rcx, r15; this
0x180032c9d  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180032ca2  mov     [rsp+0D8h+Format], rax
0x180032ca7  lea     r9, IID_IControlManager
0x180032cae  mov     r8d, 2
0x180032cb4  mov     edx, edi
0x180032cb6  mov     rcx, r14
0x180032cb9  call    ?SetControlErrorInfo@CControlManager@WindowsPerformanceRecorder@@QEAAXJW4__MIDL_IControlErrorInfo_0001@@AEBU_GUID@@PEBG@Z; WindowsPerformanceRecorder::CControlManager::SetControlErrorInfo(long,__MIDL_IControlErrorInfo_0001,_GUID const &,ushort const *)
0x180032cbe  mov     rcx, r15; this
0x180032cc1  call    ?get_SessionName@CEventSession@CETWProperties@WindowsPerformanceRecorder@@QEBAPEBGXZ; WindowsPerformanceRecorder::CETWProperties::CEventSession::get_SessionName(void)
0x180032cc6  mov     [rsp+0D8h+var_B0], rax; char *
0x180032ccb  lea     rax, aWs_0; "%ws"
0x180032cd2  mov     [rsp+0D8h+Format], rax; Format
0x180032cd7  mov     r9d, edi; unsigned int
0x180032cda  mov     r8d, 0A45h; char *
0x180032ce0  lea     rdx, aStartnormalors; "StartNormalOrShutdownRecording"
0x180032ce7  mov     ecx, 2; this
0x180032cec  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180032cf1  jmp     loc_180032B6D
0x180032cf6  cmp     dword ptr [r15], 5
0x180032cfa  jnz     loc_180032F75
0x180032d00  mov     [rsp+0D8h+SystemInformation], 0
0x180032d09  mov     dword ptr [rsp+0D8h+ReturnLength], 0
0x180032d14  lea     r9, [rsp+0D8h+ReturnLength]; ReturnLength
0x180032d1c  mov     r8d, 8; SystemInformationLength
0x180032d22  lea     rdx, [rsp+0D8h+SystemInformation]; SystemInformation
0x180032d27  lea     ecx, [r8+7Fh]; SystemInformationClass
0x180032d2b  call    cs:__imp_NtQuerySystemInformation
0x180032d31  test    eax, eax
0x180032d33  js      loc_180032F75
0x180032d39  mov     ecx, 0FFFFh; GroupNumber
0x180032d3e  call    cs:__imp_GetActiveProcessorCount
0x180032d44  cmp     eax, dword ptr [rsp+0D8h+SystemInformation]
0x180032d48  jnb     loc_180032F75
0x180032d4e  cmp     byte ptr [r15+0D2h], 0
0x180032d56  jnz     loc_180032F75
0x180032d5c  mov     rdx, [rsp+0D8h+arg_8]
0x180032d64  lea     rcx, [rsp+0D8h+var_88]
0x180032d69  call    ??0?$CComQIPtr@UIProfileCollection2@@$1?_GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>::CComQIPtr<IProfileCollection2,&__s_GUID const _GUID_47c60a6d_30a2_46c9_85ac_79eed0d584e4>(IUnknown *)
0x180032d6e  nop
0x180032d6f  mov     rcx, [rsp+0D8h+var_88]
0x180032d74  test    rcx, rcx
0x180032d77  jnz     short loc_180032DAF
0x180032d79  lea     rcx, [rsp+0D8h+var_88]
0x180032d7e  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180032d83  nop
0x180032d84  test    rbx, rbx
0x180032d87  jz      short loc_180032D9C
0x180032d89  mov     rax, [rbx]
0x180032d8c  mov     edx, 1
0x180032d91  mov     rcx, rbx
0x180032d94  mov     rax, [rax]
0x180032d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d9c  mov     [rsp+0D8h+var_90], 0
0x180032da5  mov     eax, 80004002h
0x180032daa  jmp     loc_1800332AE
0x180032daf  mov     [rsp+0D8h+var_A8], 0
0x180032db8  mov     rax, [rcx]
0x180032dbb  lea     rdx, [rsp+0D8h+var_A8]
0x180032dc0  mov     rax, [rax+60h]
0x180032dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dc9  mov     edi, eax
0x180032dcb  test    eax, eax
0x180032dcd  jns     short loc_180032E0D
0x180032dcf  lea     rcx, [rsp+0D8h+var_A8]
0x180032dd4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032dd9  nop
0x180032dda  lea     rcx, [rsp+0D8h+var_88]
0x180032ddf  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180032de4  nop
0x180032de5  test    rbx, rbx
0x180032de8  jz      short loc_180032DFD
0x180032dea  mov     rax, [rbx]
0x180032ded  mov     edx, 1
0x180032df2  mov     rcx, rbx
0x180032df5  mov     rax, [rax]
0x180032df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032dfd  mov     [rsp+0D8h+var_90], 0
0x180032e06  mov     eax, edi
0x180032e08  jmp     loc_1800332AE
0x180032e0d  mov     rdx, [rsp+0D8h+var_A8]
0x180032e12  lea     rcx, [rsp+0D8h+var_80]
0x180032e17  call    ??0?$CComQIPtr@UITraceMergePropertyElement@WindowsPerformanceRecorder@@$1?_GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<WindowsPerformanceRecorder::ITraceMergePropertyElement,&__s_GUID const _GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7>::CComQIPtr<WindowsPerformanceRecorder::ITraceMergePropertyElement,&__s_GUID const _GUID_3aaab089_6481_4c2b_8491_0053d8fd27c7>(IUnknown *)
0x180032e1c  nop
0x180032e1d  mov     rcx, [rsp+0D8h+var_80]
0x180032e22  test    rcx, rcx
0x180032e25  jnz     short loc_180032E73
0x180032e27  lea     rcx, [rsp+0D8h+var_80]
0x180032e2c  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032e31  nop
0x180032e32  lea     rcx, [rsp+0D8h+var_A8]
0x180032e37  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032e3c  nop
0x180032e3d  lea     rcx, [rsp+0D8h+var_88]
0x180032e42  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180032e47  nop
0x180032e48  test    rbx, rbx
0x180032e4b  jz      short loc_180032E60
0x180032e4d  mov     rax, [rbx]
0x180032e50  mov     edx, 1
0x180032e55  mov     rcx, rbx
0x180032e58  mov     rax, [rax]
0x180032e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e60  mov     [rsp+0D8h+var_90], 0
0x180032e69  mov     eax, 80004002h
0x180032e6e  jmp     loc_1800332AE
0x180032e73  mov     [rsp+0D8h+var_70], 0
0x180032e7c  mov     rax, [rcx]
0x180032e7f  lea     rdx, [rsp+0D8h+var_70]
0x180032e84  mov     rax, [rax+18h]
0x180032e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e8d  mov     edi, eax
0x180032e8f  test    eax, eax
0x180032e91  jns     short loc_180032F03
0x180032e93  lea     rax, aComguard; "COMGUARD"
0x180032e9a  mov     [rsp+0D8h+Format], rax; Format
0x180032e9f  mov     r9d, edi; unsigned int
0x180032ea2  mov     r8d, 0A5Fh; char *
0x180032ea8  lea     rdx, aStartnormalors; "StartNormalOrShutdownRecording"
0x180032eaf  mov     ecx, 2; this
0x180032eb4  call    ?TraceHR@WindowsPerformanceRecorder@@YAXEPEBDIJ0ZZ; WindowsPerformanceRecorder::TraceHR(uchar,char const *,uint,long,char const *,...)
0x180032eb9  nop
0x180032eba  lea     rcx, [rsp+0D8h+var_80]
0x180032ebf  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032ec4  nop
0x180032ec5  lea     rcx, [rsp+0D8h+var_A8]
0x180032eca  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032ecf  nop
0x180032ed0  lea     rcx, [rsp+0D8h+var_88]
0x180032ed5  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180032eda  nop
0x180032edb  test    rbx, rbx
0x180032ede  jz      short loc_180032EF3
0x180032ee0  mov     rax, [rbx]
0x180032ee3  mov     edx, 1
0x180032ee8  mov     rcx, rbx
0x180032eeb  mov     rax, [rax]
0x180032eee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ef3  mov     [rsp+0D8h+var_90], 0
0x180032efc  mov     eax, edi
0x180032efe  jmp     loc_1800332AE
0x180032f03  mov     rax, [rsp+0D8h+var_70]
0x180032f08  lea     rcx, [rsp+0D8h+var_80]
0x180032f0d  cmp     byte ptr [rax+3Ah], 0
0x180032f11  jnz     short loc_180032F5A
0x180032f13  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032f18  nop
0x180032f19  lea     rcx, [rsp+0D8h+var_A8]
0x180032f1e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032f23  nop
0x180032f24  lea     rcx, [rsp+0D8h+var_88]
0x180032f29  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180032f2e  nop
0x180032f2f  test    rbx, rbx
0x180032f32  jz      short loc_180032F47
0x180032f34  mov     rax, [rbx]
0x180032f37  mov     edx, 1
0x180032f3c  mov     rcx, rbx
0x180032f3f  mov     rax, [rax]
0x180032f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f47  mov     [rsp+0D8h+var_90], 0
0x180032f50  mov     eax, 0C558063Fh
0x180032f55  jmp     loc_1800332AE
0x180032f5a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032f5f  nop
0x180032f60  lea     rcx, [rsp+0D8h+var_A8]
0x180032f65  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180032f6a  nop
0x180032f6b  lea     rcx, [rsp+0D8h+var_88]
0x180032f70  call    ??1?$CComPtrBase@UIProfileCollection2@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IProfileCollection2>::~CComPtrBase<IProfileCollection2>(void)
0x180032f75  add     r12, 8
0x180032f79  jmp     loc_180032C75
0x180032f7e  cmp     [rsp+0D8h+arg_10], 0
0x180032f86  jz      short loc_180032F9B
0x180032f88  cmp     dword ptr [rbx+100h], 1
0x180032f8f  jnz     short loc_180032F9B
0x180032f91  cmp     byte ptr [r14+23Ch], 0
0x180032f99  jz      short loc_180032FB6
0x180032f9b  cmp     dword ptr [rbx+100h], 2
0x180032fa2  jnz     loc_1800330AC
0x180032fa8  cmp     byte ptr [r14+23Ch], 0
0x180032fb0  jz      loc_1800330AC
  ... truncated ...
```
