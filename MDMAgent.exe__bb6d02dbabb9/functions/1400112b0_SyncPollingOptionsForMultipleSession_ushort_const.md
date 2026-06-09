# SyncPollingOptionsForMultipleSession(ushort const *)

- ea: `0x1400112b0`
- end: `0x1400115bf`
- name: `?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z`
- size: `783`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000829c`

## callees

- `0x1400029c0`
- `0x140004b94`
- `0x140006bf4`
- `0x140007e3c`
- `0x140009004`
- `0x1400094bc`
- `0x14000bac4`
- `0x14000bc88`
- `0x14000ec7c`
- `0x140010618`
- `0x1400112b0`
- `0x1400122b4`
- `0x14001848c`
- `0x1400187fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001153e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14001153e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001157e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x14001157e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400114a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1400114a9`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1400112f9`
- `DMCmnUtils!IsWvdFeatureAllowed` at `0x1400112f9`
- `DMCmnUtils!DmDeleteTask` at `0x140011451`
- `DMCmnUtils!DmDeleteTask` at `0x140011451`

## string_xrefs

- `0x14001142d`: `Schedule #4 created by enrollment client`
- `0x140011440`: `Schedule #4 created by enrollment client`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SyncPollingOptionsForMultipleSession(const unsigned __int16 *a1)
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
  int DeviceEnrollerKey; // eax
  LSTATUS ValueW; // eax
  int pdwType; // [rsp+20h] [rbp-59h]
  int pcbData; // [rsp+30h] [rbp-49h]
  int v18; // [rsp+38h] [rbp-41h]
  HKEY hkey; // [rsp+50h] [rbp-29h] BYREF
  unsigned int v20[2]; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v21[8]; // [rsp+60h] [rbp-19h] BYREF
  DWORD v22; // [rsp+68h] [rbp-11h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-9h] BYREF
  __int128 pvData; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_QWORD *)v20 = 0;
  hkey = 0;
  EvtPerfTraceScope::EvtPerfTraceScope((EvtPerfTraceScope *)v21, "SyncPollingOptionsForMultipleSession");
  if ( !IsWvdFeatureAllowed(a1) )
  {
    EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
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
                                         &v20[v4]);
    if ( (int)(MultipleSessionValueFromRegistry + 0x80000000) >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
    {
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return MultipleSessionValueFromRegistry;
    }
    if ( MultipleSessionValueFromRegistry != -2147024894 )
      v3 = 1;
    ++v4;
  }
  if ( v3 )
  {
    v7 = v20[0];
    v8 = v20[0] != 0 ? v20[1] : 0;
    v20[1] = v8;
    for ( i = 0; i != 2; ++i )
    {
      SetMultipleSessionValueToRegistry(a1, (LPCWSTR)(&g_MultipleSessionRegistryKeyNames)[i], v20[i]);
      if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
        McTemplateU0zq_EventWriteTransfer(v11, v10, (&g_MultipleSessionRegistryKeyNames)[i], v20[i]);
    }
    if ( v7 )
    {
      v12 = ScheduleOneOmaDmSession(a1, L"Schedule #4 created by enrollment client", v8, v7, v7, 0, pcbData, v18, 0, 1);
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
        DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey);
        v5 = DeviceEnrollerKey;
        if ( DeviceEnrollerKey >= 0 )
        {
          pvData = 0;
          v22 = 16;
          ValueW = RegGetValueW(hkey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v22);
          v5 = ValueW;
          if ( ValueW > 0 )
            v5 = (unsigned __int16)ValueW | 0x80070000;
          if ( v5 < 0 )
            v5 = RegSetValueExW(hkey, L"UserSessionScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
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
          EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        }
        return (unsigned int)v5;
      }
    }
    if ( v12 < 0 )
    {
      Logger = CEnrollmentLogger::GetLogger();
      CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, v12);
      EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      return (unsigned int)v12;
    }
    goto LABEL_23;
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400112b0  push    rbp
0x1400112b2  push    rbx
0x1400112b3  push    rsi
0x1400112b4  push    rdi
0x1400112b5  push    r14
0x1400112b7  push    r15
0x1400112b9  lea     rbp, [rsp-2Fh]
0x1400112be  sub     rsp, 0A8h
0x1400112c5  mov     rax, cs:__security_cookie
0x1400112cc  xor     rax, rsp
0x1400112cf  mov     [rbp+57h+var_40], rax
0x1400112d3  mov     rsi, rcx
0x1400112d6  mov     qword ptr [rbp+57h+var_78], 0
0x1400112de  mov     [rbp+57h+hkey], 0
0x1400112e6  lea     rdx, aSyncpollingopt; "SyncPollingOptionsForMultipleSession"
0x1400112ed  lea     rcx, [rbp+57h+var_70]; this
0x1400112f1  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x1400112f6  mov     rcx, rsi
0x1400112f9  call    cs:__imp_?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x140011300  nop     dword ptr [rax+rax+00h]
0x140011305  test    eax, eax
0x140011307  jnz     short loc_140011327
0x140011309  lea     rcx, [rbp+57h+var_70]; this
0x14001130d  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140011312  nop
0x140011313  lea     rcx, [rbp+57h+hkey]
0x140011317  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001131c  nop
0x14001131d  mov     eax, 1
0x140011322  jmp     loc_1400115A2
0x140011327  xor     edi, edi
0x140011329  xor     r15d, r15d
0x14001132c  lea     ebx, [rdi+1]
0x14001132f  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x140011336  cmp     r15d, 2
0x14001133a  jge     short loc_140011397
0x14001133c  movsxd  rdx, r15d
0x14001133f  lea     r8, [rbp+57h+var_78]
0x140011343  lea     r8, [r8+rdx*4]; unsigned int *
0x140011347  mov     rdx, [rcx+rdx*8]; lpValue
0x14001134b  mov     rcx, rsi; unsigned __int16 *
0x14001134e  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x140011353  mov     r14d, eax
0x140011356  mov     eax, 80000000h
0x14001135b  lea     ecx, [r14+rax]
0x14001135f  test    eax, ecx
0x140011361  jnz     short loc_14001136C
0x140011363  cmp     r14d, 80070002h
0x14001136a  jnz     short loc_14001137B
0x14001136c  cmp     r14d, 80070002h
0x140011373  cmovnz  edi, ebx
0x140011376  add     r15d, ebx
0x140011379  jmp     short loc_14001132F
0x14001137b  lea     rcx, [rbp+57h+var_70]; this
0x14001137f  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140011384  nop
0x140011385  lea     rcx, [rbp+57h+hkey]
0x140011389  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001138e  nop
0x14001138f  mov     eax, r14d
0x140011392  jmp     loc_1400115A2
0x140011397  test    edi, edi
0x140011399  jnz     short loc_1400113B4
0x14001139b  lea     rcx, [rbp+57h+var_70]; this
0x14001139f  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1400113a4  nop
0x1400113a5  lea     rcx, [rbp+57h+hkey]
0x1400113a9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400113ae  nop
0x1400113af  jmp     loc_1400115A0
0x1400113b4  mov     r14d, [rbp+57h+var_78]
0x1400113b8  mov     eax, r14d
0x1400113bb  neg     eax
0x1400113bd  sbb     r15d, r15d
0x1400113c0  and     r15d, [rbp+57h+var_78+4]
0x1400113c4  mov     [rbp+57h+var_78+4], r15d
0x1400113c8  xor     edi, edi
0x1400113ca  mov     r8d, [rbp+rdi*4+57h+var_78]; unsigned int
0x1400113cf  mov     rdx, [rcx+rdi*8]; lpValueName
0x1400113d3  mov     rcx, rsi; unsigned __int16 *
0x1400113d6  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x1400113db  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1400113e2  jz      short loc_1400113F9
0x1400113e4  mov     r9d, [rbp+rdi*4+57h+var_78]
0x1400113e9  lea     r8, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x1400113f0  mov     r8, [r8+rdi*8]
0x1400113f4  call    McTemplateU0zq_EventWriteTransfer
0x1400113f9  add     rdi, rbx
0x1400113fc  cmp     rdi, 2
0x140011400  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x140011407  jnz     short loc_1400113CA
0x140011409  test    r14d, r14d
0x14001140c  jz      short loc_140011440
0x14001140e  mov     [rsp+0D0h+var_88], ebx; int
0x140011412  mov     [rsp+0D0h+var_90], 0; int
0x14001141a  mov     dword ptr [rsp+0D0h+pvData], 0; int
0x140011422  mov     dword ptr [rsp+0D0h+pdwType], r14d; unsigned int
0x140011427  mov     r9d, r14d; unsigned int
0x14001142a  mov     r8d, r15d; unsigned int
0x14001142d  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x140011434  mov     rcx, rsi; unsigned __int16 *
0x140011437  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x14001143c  mov     edi, eax
0x14001143e  jmp     short loc_140011470
0x140011440  lea     r8, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x140011447  mov     rdx, rsi
0x14001144a  lea     rcx, aMicrosoftWindo_1; "\\Microsoft\\Windows\\EnterpriseMgmt"
0x140011451  call    cs:__imp_?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x140011458  nop     dword ptr [rax+rax+00h]
0x14001145d  mov     edi, eax
0x14001145f  add     eax, 7FF8FFFEh
0x140011464  cmp     eax, ebx
0x140011466  jbe     short loc_14001149E
0x140011468  cmp     edi, 80070490h
0x14001146e  jz      short loc_14001149E
0x140011470  test    edi, edi
0x140011472  jns     short loc_14001149E
0x140011474  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x140011479  mov     edx, edi; int
0x14001147b  mov     rcx, rax; this
0x14001147e  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x140011483  lea     rcx, [rbp+57h+var_70]; this
0x140011487  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x14001148c  nop
0x14001148d  lea     rcx, [rbp+57h+hkey]
0x140011491  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x140011496  nop
0x140011497  mov     eax, edi
0x140011499  jmp     loc_1400115A2
0x14001149e  xorps   xmm0, xmm0
0x1400114a1  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x1400114a5  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x1400114a9  call    cs:__imp_GetSystemTime
0x1400114b0  nop     dword ptr [rax+rax+00h]
0x1400114b5  xor     edx, edx
0x1400114b7  lea     rcx, [rbp+57h+hkey]
0x1400114bb  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1400114c0  lea     rdx, [rbp+57h+hkey]; HKEY *
0x1400114c4  mov     rcx, rsi; pszMore
0x1400114c7  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x1400114cc  mov     ebx, eax
0x1400114ce  test    eax, eax
0x1400114d0  jns     short loc_140011503
0x1400114d2  mov     rcx, [rbp+5Fh]; this
0x1400114d6  mov     r9d, eax; char *
0x1400114d9  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1400114e0  mov     edx, 1479h; void *
0x1400114e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1400114ea  lea     rcx, [rbp+57h+var_70]; this
0x1400114ee  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1400114f3  nop
0x1400114f4  lea     rcx, [rbp+57h+hkey]
0x1400114f8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1400114fd  nop
0x1400114fe  jmp     loc_1400115A0
0x140011503  xorps   xmm0, xmm0
0x140011506  movups  [rbp+57h+var_50], xmm0
0x14001150a  mov     edi, 10h
0x14001150f  mov     [rbp+57h+var_68], edi
0x140011512  lea     rax, [rbp+57h+var_68]
0x140011516  mov     [rsp+0D0h+pcbData], rax; pcbData
0x14001151b  lea     rax, [rbp+57h+var_50]
0x14001151f  mov     [rsp+0D0h+pvData], rax; pvData
0x140011524  mov     [rsp+0D0h+pdwType], 0; pdwType
0x14001152d  lea     r9d, [rdi-8]; dwFlags
0x140011531  lea     r8, aUsersessionsch; "UserSessionScheduleTimestamp"
0x140011538  xor     edx, edx; lpSubKey
0x14001153a  mov     rcx, [rbp+57h+hkey]; hkey
0x14001153e  call    cs:__imp_RegGetValueW
0x140011545  nop     dword ptr [rax+rax+00h]
0x14001154a  mov     ebx, eax
0x14001154c  test    eax, eax
0x14001154e  jle     short loc_140011559
0x140011550  movzx   ebx, ax
0x140011553  or      ebx, 80070000h
0x140011559  test    ebx, ebx
0x14001155b  jns     short loc_14001158C
0x14001155d  mov     dword ptr [rsp+0D0h+pvData], edi; cbData
0x140011561  lea     rax, [rbp+57h+SystemTime]
0x140011565  mov     [rsp+0D0h+pdwType], rax; lpData
0x14001156a  mov     r9d, 3; dwType
0x140011570  xor     r8d, r8d; Reserved
0x140011573  lea     rdx, aUsersessionsch; "UserSessionScheduleTimestamp"
0x14001157a  mov     rcx, [rbp+57h+hkey]; hKey
0x14001157e  call    cs:__imp_RegSetValueExW
0x140011585  nop     dword ptr [rax+rax+00h]
0x14001158a  mov     ebx, eax
0x14001158c  lea     rcx, [rbp+57h+var_70]; this
0x140011590  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x140011595  nop
0x140011596  lea     rcx, [rbp+57h+hkey]
0x14001159a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x14001159f  nop
0x1400115a0  mov     eax, ebx
0x1400115a2  mov     rcx, [rbp+57h+var_40]
0x1400115a6  xor     rcx, rsp; StackCookie
0x1400115a9  call    __security_check_cookie
0x1400115ae  add     rsp, 0A8h
0x1400115b5  pop     r15
0x1400115b7  pop     r14
0x1400115b9  pop     rdi
0x1400115ba  pop     rsi
0x1400115bb  pop     rbx
0x1400115bc  pop     rbp
0x1400115bd  retn
```
