# SyncPollingOptionsForMultipleSession(ushort const *)

- ea: `0x180010804`
- end: `0x180010aae`
- name: `?SyncPollingOptionsForMultipleSession@@YAJPEBG@Z`
- size: `682`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180004168`

## callees

- `0x180001c60`
- `0x18000707c`
- `0x1800075e8`
- `0x180007778`
- `0x18000a464`
- `0x18000a718`
- `0x18000c938`
- `0x18000de68`
- `0x18000fa24`
- `0x180010804`
- `0x180011828`
- `0x180011e0c`
- `0x180015e1c`
- `0x180017170`
- `0x18001b9d8`
- `0x18001bd4c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010a29`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180010a29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010a69`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010a69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180010994`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180010994`

## string_xrefs

- `0x18001092b`: `Schedule #4 created by enrollment client`

## pseudocode

```c
__int64 __fastcall SyncPollingOptionsForMultipleSession(const unsigned __int16 *a1)
{
  int v2; // ebx
  int i; // r14d
  unsigned int MultipleSessionValueFromRegistry; // esi
  unsigned int v6; // esi
  int v7; // r14d
  __int64 j; // rbx
  __int64 v9; // rdx
  __int64 v10; // rcx
  const unsigned __int16 *v11; // r8
  int v12; // ebx
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
  if ( (unsigned int)IsWvdFeatureAllowed(a1) )
  {
    v2 = 0;
    for ( i = 0; i < 2; ++i )
    {
      MultipleSessionValueFromRegistry = GetMultipleSessionValueFromRegistry(
                                           a1,
                                           *((LPCWSTR *)&g_MultipleSessionRegistryKeyNames + i),
                                           &v20[i]);
      if ( (int)(MultipleSessionValueFromRegistry + 0x80000000) >= 0 && MultipleSessionValueFromRegistry != -2147024894 )
      {
        EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return MultipleSessionValueFromRegistry;
      }
      if ( MultipleSessionValueFromRegistry != -2147024894 )
        v2 = 1;
    }
    if ( v2 )
    {
      v6 = v20[0];
      v7 = v20[0] != 0 ? v20[1] : 0;
      v20[1] = v7;
      for ( j = 0; j != 2; ++j )
      {
        SetMultipleSessionValueToRegistry(a1, *((LPCWSTR *)&g_MultipleSessionRegistryKeyNames + j), v20[j]);
        if ( (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 2) != 0 )
          McTemplateU0zq_EventWriteTransfer(v10, v9, *((_QWORD *)&g_MultipleSessionRegistryKeyNames + j), v20[j]);
      }
      if ( v6 )
      {
        v12 = ScheduleOneOmaDmSession(
                a1,
                L"Schedule #4 created by enrollment client",
                v7,
                v6,
                v6,
                0,
                pcbData,
                v18,
                0,
                1);
      }
      else
      {
        v12 = DmDeleteTask(&g_MultipleSessionRegistryKeyNames, a1, v11);
        if ( (unsigned int)(v12 + 2147024894) <= 1 || v12 == -2147023728 )
          goto LABEL_21;
      }
      if ( v12 < 0 )
      {
        Logger = CEnrollmentLogger::GetLogger();
        CEnrollmentLogger::LogDMPollUserScheduleSetupFail(Logger, v12);
LABEL_23:
        EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        return (unsigned int)v12;
      }
LABEL_21:
      SystemTime = 0;
      GetSystemTime(&SystemTime);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
        &hkey,
        0);
      DeviceEnrollerKey = GetDeviceEnrollerKey(a1, &hkey);
      v12 = DeviceEnrollerKey;
      if ( DeviceEnrollerKey >= 0 )
      {
        pvData = 0;
        v22 = 16;
        ValueW = RegGetValueW(hkey, 0, L"UserSessionScheduleTimestamp", 8u, 0, &pvData, &v22);
        v12 = ValueW;
        if ( ValueW > 0 )
          v12 = (unsigned __int16)ValueW | 0x80070000;
        if ( v12 < 0 )
          v12 = RegSetValueExW(hkey, L"UserSessionScheduleTimestamp", 0, 3u, (const BYTE *)&SystemTime, 0x10u);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1479,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\enrollactivities\\dmscheduleadminlib\\utils.cpp",
          (const char *)(unsigned int)DeviceEnrollerKey,
          pdwType);
      }
      goto LABEL_23;
    }
  }
  EvtPerfTraceScope::~EvtPerfTraceScope((EvtPerfTraceScope *)v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return 1;
}

```

## disassembly

```asm
0x180010804  push    rbp
0x180010806  push    rbx
0x180010807  push    rsi
0x180010808  push    rdi
0x180010809  push    r12
0x18001080b  push    r14
0x18001080d  lea     rbp, [rsp-2Fh]
0x180010812  sub     rsp, 0A8h
0x180010819  mov     rax, cs:__security_cookie
0x180010820  xor     rax, rsp
0x180010823  mov     [rbp+57h+var_40], rax
0x180010827  mov     rdi, rcx
0x18001082a  mov     qword ptr [rbp+57h+var_78], 0
0x180010832  lea     rcx, [rbp+57h+var_70]; this
0x180010836  mov     [rbp+57h+hkey], 0
0x18001083e  lea     rdx, aSyncpollingopt_0; "SyncPollingOptionsForMultipleSession"
0x180010845  call    ??0EvtPerfTraceScope@@QEAA@PEBD@Z; EvtPerfTraceScope::EvtPerfTraceScope(char const *)
0x18001084a  mov     rcx, rdi; unsigned __int16 *
0x18001084d  call    ?IsWvdFeatureAllowed@@YAHPEBG@Z; IsWvdFeatureAllowed(ushort const *)
0x180010852  mov     r12d, 1
0x180010858  test    eax, eax
0x18001085a  jz      loc_180010A7C
0x180010860  xor     ebx, ebx
0x180010862  xor     r14d, r14d
0x180010865  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x18001086c  cmp     r14d, 2
0x180010870  jge     short loc_1800108C7
0x180010872  movsxd  rdx, r14d
0x180010875  lea     r8, [rbp+57h+var_78]
0x180010879  lea     r8, [r8+rdx*4]; unsigned int *
0x18001087d  mov     rdx, [rcx+rdx*8]; lpValue
0x180010881  mov     rcx, rdi; unsigned __int16 *
0x180010884  call    ?GetMultipleSessionValueFromRegistry@@YAJPEBG0PEAK@Z; GetMultipleSessionValueFromRegistry(ushort const *,ushort const *,ulong *)
0x180010889  mov     esi, eax
0x18001088b  mov     eax, 80000000h
0x180010890  lea     ecx, [rsi+rax]
0x180010893  test    eax, ecx
0x180010895  jnz     short loc_18001089F
0x180010897  cmp     esi, 80070002h
0x18001089d  jnz     short loc_1800108AE
0x18001089f  cmp     esi, 80070002h
0x1800108a5  cmovnz  ebx, r12d
0x1800108a9  add     r14d, r12d
0x1800108ac  jmp     short loc_180010865
0x1800108ae  lea     rcx, [rbp+57h+var_70]; this
0x1800108b2  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800108b7  lea     rcx, [rbp+57h+hkey]
0x1800108bb  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800108c0  mov     eax, esi
0x1800108c2  jmp     loc_180010A91
0x1800108c7  test    ebx, ebx
0x1800108c9  jz      loc_180010A7C
0x1800108cf  mov     esi, [rbp+57h+var_78]
0x1800108d2  mov     eax, esi
0x1800108d4  neg     eax
0x1800108d6  sbb     r14d, r14d
0x1800108d9  and     r14d, [rbp+57h+var_78+4]
0x1800108dd  mov     [rbp+57h+var_78+4], r14d
0x1800108e1  xor     ebx, ebx
0x1800108e3  mov     rdx, [rcx+rbx*8]; lpValueName
0x1800108e7  mov     rcx, rdi; unsigned __int16 *
0x1800108ea  mov     r8d, [rbp+rbx*4+57h+var_78]; unsigned int
0x1800108ef  call    ?SetMultipleSessionValueToRegistry@@YAJPEBG0K@Z; SetMultipleSessionValueToRegistry(ushort const *,ushort const *,ulong)
0x1800108f4  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 2
0x1800108fb  jz      short loc_180010912
0x1800108fd  mov     r9d, [rbp+rbx*4+57h+var_78]
0x180010902  lea     r8, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; ushort const * near * g_MultipleSessionRegistryKeyNames
0x180010909  mov     r8, [r8+rbx*8]
0x18001090d  call    McTemplateU0zq_EventWriteTransfer
0x180010912  add     rbx, r12
0x180010915  lea     rcx, ?g_MultipleSessionRegistryKeyNames@@3PAPEBGA; unsigned __int16 *
0x18001091c  cmp     rbx, 2
0x180010920  jnz     short loc_1800108E3
0x180010922  test    esi, esi
0x180010924  jz      short loc_180010958
0x180010926  mov     [rsp+0D0h+var_88], r12d; int
0x18001092b  lea     rdx, aSchedule4Creat; "Schedule #4 created by enrollment clien"...
0x180010932  mov     [rsp+0D0h+var_90], 0; int
0x18001093a  mov     r9d, esi; unsigned int
0x18001093d  mov     dword ptr [rsp+0D0h+pvData], 0; int
0x180010945  mov     r8d, r14d; unsigned int
0x180010948  mov     rcx, rdi; unsigned __int16 *
0x18001094b  mov     dword ptr [rsp+0D0h+pdwType], esi; unsigned int
0x18001094f  call    ?ScheduleOneOmaDmSession@@YAJPEBG0KKKHHHHH@Z; ScheduleOneOmaDmSession(ushort const *,ushort const *,ulong,ulong,ulong,int,int,int,int,int)
0x180010954  mov     ebx, eax
0x180010956  jmp     short loc_180010974
0x180010958  mov     rdx, rdi; unsigned __int16 *
0x18001095b  call    ?DmDeleteTask@@YAJPEBG00@Z; DmDeleteTask(ushort const *,ushort const *,ushort const *)
0x180010960  mov     ebx, eax
0x180010962  add     eax, 7FF8FFFEh
0x180010967  cmp     eax, r12d
0x18001096a  jbe     short loc_180010989
0x18001096c  cmp     ebx, 80070490h
0x180010972  jz      short loc_180010989
0x180010974  test    ebx, ebx
0x180010976  jns     short loc_180010989
0x180010978  call    ?GetLogger@CEnrollmentLogger@@SAPEAV1@XZ; CEnrollmentLogger::GetLogger(void)
0x18001097d  mov     edx, ebx; int
0x18001097f  mov     rcx, rax; this
0x180010982  call    ?LogDMPollUserScheduleSetupFail@CEnrollmentLogger@@QEAAXJ@Z; CEnrollmentLogger::LogDMPollUserScheduleSetupFail(long)
0x180010987  jmp     short loc_1800109D5
0x180010989  xorps   xmm0, xmm0
0x18001098c  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x180010990  movups  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x180010994  call    cs:__imp_GetSystemTime
0x18001099b  nop     dword ptr [rax+rax+00h]
0x1800109a0  xor     edx, edx
0x1800109a2  lea     rcx, [rbp+57h+hkey]
0x1800109a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800109ab  lea     rdx, [rbp+57h+hkey]; HKEY *
0x1800109af  mov     rcx, rdi; pszMore
0x1800109b2  call    ?GetDeviceEnrollerKey@@YAJPEBGPEAPEAUHKEY__@@H@Z; GetDeviceEnrollerKey(ushort const *,HKEY__ * *,int)
0x1800109b7  mov     ebx, eax
0x1800109b9  test    eax, eax
0x1800109bb  jns     short loc_1800109EE
0x1800109bd  mov     rcx, [rbp+5Fh]; this
0x1800109c1  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\enterprisemgmt\\enro"...
0x1800109c8  mov     r9d, eax; char *
0x1800109cb  mov     edx, 1479h; void *
0x1800109d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800109d5  lea     rcx, [rbp+57h+var_70]; this
0x1800109d9  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x1800109de  lea     rcx, [rbp+57h+hkey]
0x1800109e2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800109e7  mov     eax, ebx
0x1800109e9  jmp     loc_180010A91
0x1800109ee  mov     rcx, [rbp+57h+hkey]; hkey
0x1800109f2  lea     rax, [rbp+57h+var_68]
0x1800109f6  mov     [rsp+0D0h+pcbData], rax; pcbData
0x1800109fb  lea     r8, aUsersessionsch; "UserSessionScheduleTimestamp"
0x180010a02  mov     edi, 10h
0x180010a07  lea     rax, [rbp+57h+var_50]
0x180010a0b  xorps   xmm0, xmm0
0x180010a0e  mov     [rsp+0D0h+pvData], rax; pvData
0x180010a13  xor     edx, edx; lpSubKey
0x180010a15  mov     [rsp+0D0h+pdwType], 0; pdwType
0x180010a1e  movups  [rbp+57h+var_50], xmm0
0x180010a22  lea     r9d, [rdi-8]; dwFlags
0x180010a26  mov     [rbp+57h+var_68], edi
0x180010a29  call    cs:__imp_RegGetValueW
0x180010a30  nop     dword ptr [rax+rax+00h]
0x180010a35  mov     ebx, eax
0x180010a37  test    eax, eax
0x180010a39  jle     short loc_180010A44
0x180010a3b  movzx   ebx, ax
0x180010a3e  or      ebx, 80070000h
0x180010a44  test    ebx, ebx
0x180010a46  jns     short loc_1800109D5
0x180010a48  mov     rcx, [rbp+57h+hkey]; hKey
0x180010a4c  lea     rax, [rbp+57h+SystemTime]
0x180010a50  mov     dword ptr [rsp+0D0h+pvData], edi; cbData
0x180010a54  lea     rdx, aUsersessionsch; "UserSessionScheduleTimestamp"
0x180010a5b  mov     r9d, 3; dwType
0x180010a61  mov     [rsp+0D0h+pdwType], rax; lpData
0x180010a66  xor     r8d, r8d; Reserved
0x180010a69  call    cs:__imp_RegSetValueExW
0x180010a70  nop     dword ptr [rax+rax+00h]
0x180010a75  mov     ebx, eax
0x180010a77  jmp     loc_1800109D5
0x180010a7c  lea     rcx, [rbp+57h+var_70]; this
0x180010a80  call    ??1EvtPerfTraceScope@@QEAA@XZ; EvtPerfTraceScope::~EvtPerfTraceScope(void)
0x180010a85  lea     rcx, [rbp+57h+hkey]
0x180010a89  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180010a8e  mov     eax, r12d
0x180010a91  mov     rcx, [rbp+57h+var_40]
0x180010a95  xor     rcx, rsp; StackCookie
0x180010a98  call    __security_check_cookie
0x180010a9d  add     rsp, 0A8h
0x180010aa4  pop     r14
0x180010aa6  pop     r12
0x180010aa8  pop     rdi
0x180010aa9  pop     rsi
0x180010aaa  pop     rbx
0x180010aab  pop     rbp
0x180010aac  retn
```
