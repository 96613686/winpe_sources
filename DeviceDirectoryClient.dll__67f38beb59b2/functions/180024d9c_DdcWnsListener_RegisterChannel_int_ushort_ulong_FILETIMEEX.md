# DdcWnsListener::RegisterChannel(int *,ushort *,ulong *,FILETIMEEX *)

- ea: `0x180024d9c`
- end: `0x180024fb2`
- name: `?RegisterChannel@DdcWnsListener@@SAJPEAHPEAGPEAKPEATFILETIMEEX@@@Z`
- size: `534`
- prototype: `static int(int *, unsigned __int16 *, unsigned int *, union FILETIMEEX *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000c034`

## callees

- `0x1800024c0`
- `0x180002fc0`
- `0x1800050b8`
- `0x180011e74`
- `0x1800128fc`
- `0x18001364c`
- `0x18001b844`
- `0x1800248e0`
- `0x180024d0c`
- `0x180024d9c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024eea`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024eea`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024f09`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180024f09`

## string_xrefs

- `0x180024e3d`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcwnslistener.cpp`
- `0x180024ea1`: `CHR(GetMdmCommonSettingValuesPersistedLocation(wszMdmSettingsKey, &cchMdmSettingsKey))`
- `0x180024f42`: `CHR(RegisterChannel(&ftExpiration, pwszChannelUri, pcchChannelUri))`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcWnsListener::RegisterChannel(int *a1, unsigned __int16 *a2, unsigned int *a3, FILETIME *a4)
{
  int v8; // edx
  int v9; // ecx
  int v10; // r8d
  int MdmCommonSettingValuesPersistedLocation; // ebx
  char v13; // [rsp+20h] [rbp-E0h]
  const char *v14; // [rsp+28h] [rbp-D8h]
  FILETIME FileTime2; // [rsp+30h] [rbp-D0h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v17; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v18; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v19; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v20[264]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(v20, 0, 0x208u);
  v17 = 260;
  FileTime2 = 0;
  SystemTimeAsFileTime = 0;
  v18 = 8;
  v19 = 0;
  if ( a1 )
  {
    if ( !a4 )
    {
      MdmCommonSettingValuesPersistedLocation = -2147024809;
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
        McTemplateU0dsqs_EventWriteTransfer(
          v9,
          v8,
          -2147024809,
          (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
          69,
          "CPR(pftExpiration)");
      goto LABEL_21;
    }
    MdmCommonSettingValuesPersistedLocation = GetMdmCommonSettingValuesPersistedLocation(v20, &v17);
    if ( MdmCommonSettingValuesPersistedLocation >= 0 )
    {
      if ( (int)DdcRegistry::GetByteValue(
                  HKEY_LOCAL_MACHINE,
                  v20,
                  L"ChannelUrlExpiration",
                  (unsigned __int8 *const)&FileTime2,
                  &v18) >= 0 )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        *(_QWORD *)&SystemTimeAsFileTime += 1728000000000LL;
        if ( CompareFileTime(&SystemTimeAsFileTime, &FileTime2) < 0 )
        {
          *a1 = 0;
          *a4 = FileTime2;
          goto LABEL_21;
        }
      }
      MdmCommonSettingValuesPersistedLocation = DdcWnsListener::RegisterChannel((union FILETIMEEX *)&FileTime2, a2, a3);
      if ( MdmCommonSettingValuesPersistedLocation >= 0 )
      {
        *a1 = 1;
        *a4 = FileTime2;
        if ( (int)DdcTaskSchedulerWrapper::Initialize((DdcTaskSchedulerWrapper *)&v19) >= 0 )
          ((void (__fastcall *)(_QWORD, _QWORD))DdcTaskSchedulerWrapper::ScheduleWnsChannelRegistrationFallbackSchedule)(
            &v19,
            FileTime2);
        goto LABEL_21;
      }
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_21;
      v14 = "CHR(RegisterChannel(&ftExpiration, pwszChannelUri, pcchChannelUri))";
      v13 = 95;
    }
    else
    {
      if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) == 0 )
        goto LABEL_21;
      v14 = "CHR(GetMdmCommonSettingValuesPersistedLocation(wszMdmSettingsKey, &cchMdmSettingsKey))";
      v13 = 71;
    }
    v10 = MdmCommonSettingValuesPersistedLocation;
    goto LABEL_4;
  }
  v10 = -2147024809;
  MdmCommonSettingValuesPersistedLocation = -2147024809;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
  {
    v14 = "CPR(pfChannelRenewed)";
    v13 = 68;
LABEL_4:
    McTemplateU0dsqs_EventWriteTransfer(
      v9,
      v8,
      v10,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcwnslistener.cpp",
      v13,
      v14);
  }
LABEL_21:
  ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(&v19);
  return (unsigned int)MdmCommonSettingValuesPersistedLocation;
}

```

## disassembly

```asm
0x180024d9c  push    rbp
0x180024d9e  push    rbx
0x180024d9f  push    rsi
0x180024da0  push    rdi
0x180024da1  push    r14
0x180024da3  push    r15
0x180024da5  lea     rbp, [rsp-178h]
0x180024dad  sub     rsp, 278h
0x180024db4  mov     rax, cs:__security_cookie
0x180024dbb  xor     rax, rsp
0x180024dbe  mov     [rbp+1A0h+var_40], rax
0x180024dc5  mov     rdi, r9
0x180024dc8  mov     r15, r8
0x180024dcb  mov     r14, rdx
0x180024dce  mov     rsi, rcx
0x180024dd1  xor     edx, edx; Val
0x180024dd3  mov     r8d, 208h; Size
0x180024dd9  lea     rcx, [rsp+2A0h+var_250]; void *
0x180024dde  call    memset_0
0x180024de3  mov     [rsp+2A0h+var_260], 104h
0x180024deb  mov     qword ptr [rsp+2A0h+FileTime2.dwLowDateTime], 0
0x180024df4  mov     qword ptr [rsp+2A0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180024dfd  mov     [rsp+2A0h+var_25C], 8
0x180024e05  mov     [rsp+2A0h+var_258], 0
0x180024e0e  test    rsi, rsi
0x180024e11  jnz     short loc_180024E4E
0x180024e13  mov     r8d, 80070057h
0x180024e19  mov     ebx, r8d
0x180024e1c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024e23  jz      loc_180024F87
0x180024e29  lea     rax, aCprPfchannelre; "CPR(pfChannelRenewed)"
0x180024e30  mov     [rsp+2A0h+var_278], rax
0x180024e35  mov     dword ptr [rsp+2A0h+var_280], 44h ; 'D'
0x180024e3d  lea     r9, aOnecoreuapShel_7; "onecoreuap\\shell\\devicedirectory\\dev"...
0x180024e44  call    McTemplateU0dsqs_EventWriteTransfer
0x180024e49  jmp     loc_180024F87
0x180024e4e  test    rdi, rdi
0x180024e51  jnz     short loc_180024E7F
0x180024e53  mov     r8d, 80070057h
0x180024e59  mov     ebx, r8d
0x180024e5c  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024e63  jz      loc_180024F87
0x180024e69  lea     rax, aCprPftexpirati; "CPR(pftExpiration)"
0x180024e70  mov     [rsp+2A0h+var_278], rax
0x180024e75  mov     dword ptr [rsp+2A0h+var_280], 45h ; 'E'
0x180024e7d  jmp     short loc_180024E3D
0x180024e7f  lea     rdx, [rsp+2A0h+var_260]; unsigned int *
0x180024e84  lea     rcx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180024e89  call    ?GetMdmCommonSettingValuesPersistedLocation@@YAJPEAGPEAK@Z; GetMdmCommonSettingValuesPersistedLocation(ushort *,ulong *)
0x180024e8e  mov     ebx, eax
0x180024e90  test    eax, eax
0x180024e92  jns     short loc_180024EBA
0x180024e94  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024e9b  jz      loc_180024F87
0x180024ea1  lea     rax, aChrGetmdmcommo; "CHR(GetMdmCommonSettingValuesPersistedL"...
0x180024ea8  mov     [rsp+2A0h+var_278], rax
0x180024ead  mov     dword ptr [rsp+2A0h+var_280], 47h ; 'G'
0x180024eb5  mov     r8d, ebx
0x180024eb8  jmp     short loc_180024E3D
0x180024eba  lea     rax, [rsp+2A0h+var_25C]
0x180024ebf  mov     [rsp+2A0h+var_280], rax; unsigned int *
0x180024ec4  lea     r9, [rsp+2A0h+FileTime2]; unsigned __int8 *
0x180024ec9  lea     r8, aChannelurlexpi; "ChannelUrlExpiration"
0x180024ed0  lea     rdx, [rsp+2A0h+var_250]; unsigned __int16 *
0x180024ed5  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180024edc  call    ?GetByteValue@DdcRegistry@@SAJPEAUHKEY__@@PEBG1QEAEAEAK@Z; DdcRegistry::GetByteValue(HKEY__ *,ushort const *,ushort const *,uchar * const,ulong &)
0x180024ee1  test    eax, eax
0x180024ee3  js      short loc_180024F23
0x180024ee5  lea     rcx, [rsp+2A0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024eea  call    cs:__imp_GetSystemTimeAsFileTime
0x180024ef0  mov     rax, 19254D38000h
0x180024efa  add     qword ptr [rsp+2A0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180024eff  lea     rdx, [rsp+2A0h+FileTime2]; lpFileTime2
0x180024f04  lea     rcx, [rsp+2A0h+SystemTimeAsFileTime]; lpFileTime1
0x180024f09  call    cs:__imp_CompareFileTime
0x180024f0f  test    eax, eax
0x180024f11  jns     short loc_180024F23
0x180024f13  mov     dword ptr [rsi], 0
0x180024f19  mov     rax, qword ptr [rsp+2A0h+FileTime2.dwLowDateTime]
0x180024f1e  mov     [rdi], rax
0x180024f21  jmp     short loc_180024F87
0x180024f23  mov     r8, r15; unsigned int *
0x180024f26  mov     rdx, r14; unsigned __int16 *
0x180024f29  lea     rcx, [rsp+2A0h+FileTime2]; union FILETIMEEX *
0x180024f2e  call    ?RegisterChannel@DdcWnsListener@@CAJPEATFILETIMEEX@@PEAGPEAK@Z; DdcWnsListener::RegisterChannel(FILETIMEEX *,ushort *,ulong *)
0x180024f33  mov     ebx, eax
0x180024f35  test    eax, eax
0x180024f37  jns     short loc_180024F5B
0x180024f39  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x180024f40  jz      short loc_180024F87
0x180024f42  lea     rax, aChrRegistercha; "CHR(RegisterChannel(&ftExpiration, pwsz"...
0x180024f49  mov     [rsp+2A0h+var_278], rax
0x180024f4e  mov     dword ptr [rsp+2A0h+var_280], 5Fh ; '_'
0x180024f56  jmp     loc_180024EB5
0x180024f5b  mov     dword ptr [rsi], 1
0x180024f61  mov     rax, qword ptr [rsp+2A0h+FileTime2.dwLowDateTime]
0x180024f66  mov     [rdi], rax
0x180024f69  lea     rcx, [rsp+2A0h+var_258]; this
0x180024f6e  call    ?Initialize@DdcTaskSchedulerWrapper@@QEAAJXZ; DdcTaskSchedulerWrapper::Initialize(void)
0x180024f73  test    eax, eax
0x180024f75  js      short loc_180024F87
0x180024f77  mov     rdx, qword ptr [rsp+2A0h+FileTime2.dwLowDateTime]
0x180024f7c  lea     rcx, [rsp+2A0h+var_258]
0x180024f81  call    ?ScheduleWnsChannelRegistrationFallbackSchedule@DdcTaskSchedulerWrapper@@QEAAJTFILETIMEEX@@@Z; DdcTaskSchedulerWrapper::ScheduleWnsChannelRegistrationFallbackSchedule(FILETIMEEX)
0x180024f86  nop
0x180024f87  lea     rcx, [rsp+2A0h+var_258]
0x180024f8c  call    ??1?$CComPtrBase@UIWpnPlatform@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IWpnPlatform>::~CComPtrBase<IWpnPlatform>(void)
0x180024f91  mov     eax, ebx
0x180024f93  mov     rcx, [rbp+1A0h+var_40]
0x180024f9a  xor     rcx, rsp; StackCookie
0x180024f9d  call    __security_check_cookie
0x180024fa2  add     rsp, 278h
0x180024fa9  pop     r15
0x180024fab  pop     r14
0x180024fad  pop     rdi
0x180024fae  pop     rsi
0x180024faf  pop     rbx
0x180024fb0  pop     rbp
0x180024fb1  retn
```
