# SyncPollingOptionsForMultipleSession(ushort const *)

- ea: `0x140010a68`
- end: `0x140010d58`
- name: `?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z`
- size: `752`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140007f34`

## callees

- `0x140002930`
- `0x140004b0c`
- `0x140006984`
- `0x140007b34`
- `0x140008bf4`
- `0x1400090d4`
- `0x14000b5a0`
- `0x14000b754`
- `0x14000e530`
- `0x14000fe10`
- `0x140010a68`
- `0x140011aa8`
- `0x1400177b0`
- `0x140017b10`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140010ce4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140010ce4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140010d1e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140010d1e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140010c55`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140010c55`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x140010ab1`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x140010ab1`
- `DMCmnUtils!DmDeleteTask` at `0x140010c03`
- `DMCmnUtils!DmDeleteTask` at `0x140010c03`

## string_xrefs

- `0x140010bdf`: `Schedule #4 created by enrollment client`
- `0x140010bf2`: `Schedule #4 created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptionsForMultipleSession(unsigned __int16 *a1)
{
  int v3; // edi
  int v4; // r15d
  int v5; // ebx
  unsigned int MultipleSessionValueFromRegistry; // r14d
  unsigned int v7; // r14d
  unsigned int v8; // r15d
  __int64 i; // rdi
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // edi
  CEnrollmentLogger *Logger; // rax
  int v14; // r8d
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-59h]
  int pcbData; // [rsp+30h] [rbp-49h]
  int v19; // [rsp+38h] [rbp-41h]
  HKEY hkey; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v21[2]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v22[8]; // [rsp+60h] [rbp-19h] BYREF
  DWORD v23; // [rsp+68h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-9h] BYREF
  __int128 pvData; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_QWORD *)v21 = 0;
  hkey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v22, "SyncPollingOptionsForMultipleSession");
  if ( !IsWvdFeatureAllowed(a1) )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v22);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
    return 1;
  }
  v3 = 0;
  v4 = 0;
  v5 = 1;
  while ( v4 < 2 )
  {
    MultipleSessionValueFromRegistry = GetMultipleSessionValueFromRegistry(
                                         a1,
                                         (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[v4],
                                         &v21[v4]);
    if ( (int)(MultipleSessionValueFromRegistry + 0x80000000) >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v22);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return MultipleSessionValueFromRegistry;
    }
    if ( MultipleSessionValueFromRegistry != -2147024894 )
      v3 = 1;
    ++v4;
  }
  if ( v3 )
  {
    v7 = v21[0];
    v8 = v21[0] != 0 ? v21[1] : 0;
    v21[1] = v8;
    for ( i = 0; i != 2; ++i )
    {
      SetMultipleSessionValueToRegistry(a1, (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[i], v21[i]);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(v11, v10, (&g_MultipleSessionRegistryKeyNames)[i], v21[i]);
    }
    if ( v7 )
    {
      v12 = ScheduleOneOmaDmSession(a1, L"Schedule #4 created by enrollment client", v8, v7, v7, 0, pcbData, v19, 0, 1);
    }
    else
    {
      v12 = DmDeleteTask(L"\\Microsoft\\Windows\\EnterpriseMgmt", a1, L"Schedule #4 created by enrollment client");
      if ( (unsigned int)(v12 + 2147024894) <= 1 || v12 == -2147023728 )
      {
LABEL_23:
        SystemTime = 0;
        GetSystemTime(&SystemTime);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hkey,
          0);
        DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey, v14);
        v5 = DeviceEnrollerKey;
        if ( DeviceEnrollerKey >= 0 )
        {
          pvData = 0;
          v23 = 16;
          ValueW = RegGetValueW(hkey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v23);
          v5 = ValueW;
          if ( ValueW > 0 )
            v5 = (unsigned __int16)ValueW | 0x80070000;
          if ( v5 < 0 )
            v5 = RegSetValueExW(hkey, L"UserSessionScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v22);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1479,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
            (const char *)(unsigned int)DeviceEnrollerKey,
            pdwType);
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v22);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        }
        return (unsigned int)v5;
      }
    }
    if ( v12 < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, v12);
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v22);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return (unsigned int)v12;
    }
    goto LABEL_23;
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v22);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140010a68  push    rbp
0x140010a6a  push    rbx
0x140010a6b  push    rsi
0x140010a6c  push    rdi
0x140010a6d  push    r14
0x140010a6f  push    r15
0x140010a71  lea     rbp, [rsp-2Fh]
0x140010a76  sub     rsp, 0A8h
0x140010a7d  mov     rax, cs:__security_cookie
0x140010a84  xor     rax, rsp
0x140010a87  mov     [rbp+57h+var_40], rax
0x140010a8b  mov     rsi, rcx
0x140010a8e  mov     qword ptr [rbp+57h+var_78], 0
0x140010a96  mov     [rbp+57h+hkey], 0
0x140010a9e  lea     rdx, aSyncpollingopt; "SyncPollingOptionsForMultipleSession"
0x140010aa5  lea     rcx, [rbp+57h+var_70]; this
0x140010aa9  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x140010aae  mov     rcx, rsi
0x140010ab1  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x140010ab7  test    eax, eax
0x140010ab9  jnz     short loc_140010AD9
0x140010abb  lea     rcx, [rbp+57h+var_70]; this
0x140010abf  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010ac4  nop
0x140010ac5  lea     rcx, [rbp+57h+hkey]
0x140010ac9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010ace  nop
0x140010acf  mov     eax, 1
0x140010ad4  jmp     loc_140010D3C
0x140010ad9  xor     edi, edi
0x140010adb  xor     r15d, r15d
0x140010ade  lea     ebx, [rdi+1]
0x140010ae1  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x140010ae8  cmp     r15d, 2
0x140010aec  jge     short loc_140010B49
0x140010aee  movsxd  rdx, r15d
0x140010af1  lea     r8, [rbp+57h+var_78]
0x140010af5  lea     r8, [r8+rdx*4]; unsigned int *
0x140010af9  mov     rdx, [rcx+rdx*8]; lpValue
0x140010afd  mov     rcx, rsi; unsigned __int16 *
0x140010b00  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x140010b05  mov     r14d, eax
0x140010b08  mov     eax, 80000000h
0x140010b0d  lea     ecx, [r14+rax]
0x140010b11  test    eax, ecx
0x140010b13  jnz     short loc_140010B1E
0x140010b15  cmp     r14d, 80070002h
0x140010b1c  jnz     short loc_140010B2D
0x140010b1e  cmp     r14d, 80070002h
0x140010b25  cmovnz  edi, ebx
0x140010b28  add     r15d, ebx
0x140010b2b  jmp     short loc_140010AE1
0x140010b2d  lea     rcx, [rbp+57h+var_70]; this
0x140010b31  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010b36  nop
0x140010b37  lea     rcx, [rbp+57h+hkey]
0x140010b3b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010b40  nop
0x140010b41  mov     eax, r14d
0x140010b44  jmp     loc_140010D3C
0x140010b49  test    edi, edi
0x140010b4b  jnz     short loc_140010B66
0x140010b4d  lea     rcx, [rbp+57h+var_70]; this
0x140010b51  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010b56  nop
0x140010b57  lea     rcx, [rbp+57h+hkey]
0x140010b5b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010b60  nop
0x140010b61  jmp     loc_140010D3A
0x140010b66  mov     r14d, [rbp+57h+var_78]
0x140010b6a  mov     eax, r14d
0x140010b6d  neg     eax
0x140010b6f  sbb     r15d, r15d
0x140010b72  and     r15d, [rbp+57h+var_78+4]
0x140010b76  mov     [rbp+57h+var_78+4], r15d
0x140010b7a  xor     edi, edi
0x140010b7c  mov     r8d, [rbp+rdi*4+57h+var_78]; unsigned int
0x140010b81  mov     rdx, [rcx+rdi*8]; lpValueName
0x140010b85  mov     rcx, rsi; unsigned __int16 *
0x140010b88  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x140010b8d  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x140010b94  jz      short loc_140010BAB
0x140010b96  mov     r9d, [rbp+rdi*4+57h+var_78]
0x140010b9b  lea     r8, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x140010ba2  mov     r8, [r8+rdi*8]
0x140010ba6  call    McTemplateU0zq_EventWriteTransfer
0x140010bab  add     rdi, rbx
0x140010bae  cmp     rdi, 2
0x140010bb2  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x140010bb9  jnz     short loc_140010B7C
0x140010bbb  test    r14d, r14d
0x140010bbe  jz      short loc_140010BF2
0x140010bc0  mov     [rsp+0D0h+var_88], ebx; int
0x140010bc4  mov     [rsp+0D0h+var_90], 0; int
0x140010bcc  mov     dword ptr [rsp+0D0h+pvData], 0; int
0x140010bd4  mov     dword ptr [rsp+0D0h+pdwType], r14d; unsigned int
0x140010bd9  mov     r9d, r14d; unsigned int
0x140010bdc  mov     r8d, r15d; unsigned int
0x140010bdf  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x140010be6  mov     rcx, rsi; unsigned __int16 *
0x140010be9  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x140010bee  mov     edi, eax
0x140010bf0  jmp     short loc_140010C1C
0x140010bf2  lea     r8, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x140010bf9  mov     rdx, rsi
0x140010bfc  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x140010c03  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x140010c09  mov     edi, eax
0x140010c0b  add     eax, 7FF8FFFEh
0x140010c10  cmp     eax, ebx
0x140010c12  jbe     short loc_140010C4A
0x140010c14  cmp     edi, 80070490h
0x140010c1a  jz      short loc_140010C4A
0x140010c1c  test    edi, edi
0x140010c1e  jns     short loc_140010C4A
0x140010c20  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140010c25  mov     edx, edi; int
0x140010c27  mov     rcx, rax; this
0x140010c2a  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x140010c2f  lea     rcx, [rbp+57h+var_70]; this
0x140010c33  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010c38  nop
0x140010c39  lea     rcx, [rbp+57h+hkey]
0x140010c3d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010c42  nop
0x140010c43  mov     eax, edi
0x140010c45  jmp     loc_140010D3C
0x140010c4a  xorps   xmm0, xmm0
0x140010c4d  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x140010c51  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x140010c55  call    cs:__imp_GetSystemTime
0x140010c5b  xor     edx, edx
0x140010c5d  lea     rcx, [rbp+57h+hkey]
0x140010c61  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x140010c66  lea     rdx, [rbp+57h+hkey]; HKEY *
0x140010c6a  mov     rcx, rsi; pszMore
0x140010c6d  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x140010c72  mov     ebx, eax
0x140010c74  test    eax, eax
0x140010c76  jns     short loc_140010CA9
0x140010c78  mov     rcx, [rbp+5Fh]; this
0x140010c7c  mov     r9d, eax; char *
0x140010c7f  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x140010c86  mov     edx, 1479h; void *
0x140010c8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140010c90  lea     rcx, [rbp+57h+var_70]; this
0x140010c94  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010c99  nop
0x140010c9a  lea     rcx, [rbp+57h+hkey]
0x140010c9e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010ca3  nop
0x140010ca4  jmp     loc_140010D3A
0x140010ca9  xorps   xmm0, xmm0
0x140010cac  movups  [rbp+57h+var_50], xmm0
0x140010cb0  mov     edi, 10h
0x140010cb5  mov     [rbp+57h+var_68], edi
0x140010cb8  lea     rax, [rbp+57h+var_68]
0x140010cbc  mov     [rsp+0D0h+pcbData], rax; pcbData
0x140010cc1  lea     rax, [rbp+57h+var_50]
0x140010cc5  mov     [rsp+0D0h+pvData], rax; pvData
0x140010cca  mov     [rsp+0D0h+pdwType], 0; pdwType
0x140010cd3  lea     r9d, [rdi-8]; dwFlags
0x140010cd7  lea     r8, aUsersessionsch; "UserSessionScheduleTimestamp"
0x140010cde  xor     edx, edx; lpSubKey
0x140010ce0  mov     rcx, [rbp+57h+hkey]; hkey
0x140010ce4  call    cs:__imp_RegGetValueW
0x140010cea  mov     ebx, eax
0x140010cec  test    eax, eax
0x140010cee  jle     short loc_140010CF9
0x140010cf0  movzx   ebx, ax
0x140010cf3  or      ebx, 80070000h
0x140010cf9  test    ebx, ebx
0x140010cfb  jns     short loc_140010D26
0x140010cfd  mov     dword ptr [rsp+0D0h+pvData], edi; cbData
0x140010d01  lea     rax, [rbp+57h+SystemTime]
0x140010d05  mov     [rsp+0D0h+pdwType], rax; lpData
0x140010d0a  mov     r9d, 3; dwType
0x140010d10  xor     r8d, r8d; Reserved
0x140010d13  lea     rdx, aUsersessionsch; "UserSessionScheduleTimestamp"
0x140010d1a  mov     rcx, [rbp+57h+hkey]; hKey
0x140010d1e  call    cs:__imp_RegSetValueExW
0x140010d24  mov     ebx, eax
0x140010d26  lea     rcx, [rbp+57h+var_70]; this
0x140010d2a  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140010d2f  nop
0x140010d30  lea     rcx, [rbp+57h+hkey]
0x140010d34  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140010d39  nop
0x140010d3a  mov     eax, ebx
0x140010d3c  mov     rcx, [rbp+57h+var_40]
0x140010d40  xor     rcx, rsp; StackCookie
0x140010d43  call    __security_check_cookie
0x140010d48  add     rsp, 0A8h
0x140010d4f  pop     r15
0x140010d51  pop     r14
0x140010d53  pop     rdi
0x140010d54  pop     rsi
0x140010d55  pop     rbx
0x140010d56  pop     rbp
0x140010d57  retn
```
