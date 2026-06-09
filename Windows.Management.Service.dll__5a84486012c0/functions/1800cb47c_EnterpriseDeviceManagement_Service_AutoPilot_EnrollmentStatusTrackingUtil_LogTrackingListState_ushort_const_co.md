# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogTrackingListState(ushort const * const,ushort const * const,unsigned __int64)

- ea: `0x1800cb47c`
- end: `0x1800cb755`
- name: `?LogTrackingListState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJQEBG0_K@Z`
- size: `729`
- prototype: `static int(const unsigned __int16 *const, const unsigned __int16 *const, unsigned __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c7050`
- `0x1800c7500`

## callees

- `0x18000b820`
- `0x180067a54`
- `0x18007755c`
- `0x18008019c`
- `0x180084208`
- `0x1800873a4`
- `0x180089614`
- `0x1800ca2d0`
- `0x1800cb47c`
- `0x1800ce040`
- `0x1800ce0fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb50d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb5a5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb50d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cb5a5`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cb600`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cb600`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cb69b`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cb69b`

## string_xrefs

- `0x1800cb52e`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb5ba`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb6b2`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cb701`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogTrackingListState(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        char a3)
{
  __int64 ProviderSubkeyName; // rax
  const WCHAR *v7; // rax
  unsigned int v8; // ebx
  unsigned int v9; // ebx
  unsigned int v11; // eax
  unsigned int v12; // ebx
  int DWORD; // eax
  unsigned int v14; // ebx
  __int64 v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  DWORD dwOptions; // [rsp+20h] [rbp-88h]
  DWORD dwOptionsa; // [rsp+20h] [rbp-88h]
  unsigned int v20; // [rsp+50h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-50h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-48h] BYREF
  _BYTE v23[32]; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  ProviderSubkeyName = EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(
                         v23,
                         a1);
  v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(ProviderSubkeyName);
  v8 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v7, 0, 0, 0, 0xF003Fu, 0, &hKey, 0);
  std::wstring::_Tidy_deallocate(v23);
  if ( v8 )
  {
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x3F5,
           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
           (const char *)v8,
           dwOptions);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
  else
  {
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v11 = RegCreateKeyExW(hKey, L"LastLoggedState", 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
    if ( v11 )
    {
      v12 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x401,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
              (const char *)v11,
              dwOptionsa);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return v12;
    }
    else
    {
      v20 = 0;
      DWORD = OmaDmRegistryGetDWORD(phkResult, 0, a2, &v20);
      v14 = DWORD;
      if ( DWORD <= -2147024895 || (v15 = (unsigned int)(DWORD + 2147024892), (unsigned int)v15 <= 0x7FF8FFFB) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x405,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
          (const char *)(unsigned int)DWORD,
          dwOptionsa);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return v14;
      }
      else
      {
        if ( v20 )
          goto LABEL_16;
        if ( a2 == L"ListRetrievalStarted"
          && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        {
          McTemplateU0zz_EventWriteTransfer(
            v15,
            AutopilotManagerBeginningProviderTrackingListRetrieval,
            L"Provider",
            a1);
        }
        if ( a2 == L"ListRetrievalSucceeded"
          && (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        {
          McTemplateU0zzd_EventWriteTransfer(
            v15,
            (unsigned int)AutopilotManagerProviderTrackingListRetrievalSucceeded,
            (unsigned int)L"Provider",
            (_DWORD)a1,
            a3);
        }
        v16 = OmaDmRegistrySetDWORD(phkResult, 0, a2, 1u);
        v17 = v16;
        if ( v16 >= 0 )
        {
LABEL_16:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x413,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\enrollmentstatustrackingutil.cpp",
            (const char *)(unsigned int)v16,
            dwOptionsa);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          return v17;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1800cb47c  mov     [rsp+arg_10], rbx
0x1800cb481  push    rsi
0x1800cb482  push    rdi
0x1800cb483  push    r14
0x1800cb485  sub     rsp, 90h
0x1800cb48c  mov     rax, cs:__security_cookie
0x1800cb493  xor     rax, rsp
0x1800cb496  mov     [rsp+0A8h+var_20], rax
0x1800cb49e  mov     r14, r8
0x1800cb4a1  mov     rdi, rdx
0x1800cb4a4  mov     rsi, rcx
0x1800cb4a7  mov     [rsp+0A8h+hKey], 0
0x1800cb4b0  xor     edx, edx
0x1800cb4b2  lea     rcx, [rsp+0A8h+hKey]
0x1800cb4b7  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cb4bc  mov     rdx, rsi
0x1800cb4bf  lea     rcx, [rsp+0A8h+var_40]
0x1800cb4c4  call    ?GetProviderSubkeyName@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(ushort const * const)
0x1800cb4c9  mov     rcx, rax
0x1800cb4cc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cb4d1  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1800cb4da  lea     rcx, [rsp+0A8h+hKey]
0x1800cb4df  mov     [rsp+0A8h+phkResult], rcx; phkResult
0x1800cb4e4  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cb4ed  mov     [rsp+0A8h+samDesired], 0F003Fh; samDesired
0x1800cb4f5  mov     [rsp+0A8h+dwOptions], 0; unsigned int
0x1800cb4fd  xor     r9d, r9d; lpClass
0x1800cb500  xor     r8d, r8d; Reserved
0x1800cb503  mov     rdx, rax; lpSubKey
0x1800cb506  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cb50d  call    cs:__imp_RegCreateKeyExW
0x1800cb513  mov     ebx, eax
0x1800cb515  lea     rcx, [rsp+0A8h+var_40]
0x1800cb51a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cb51f  test    ebx, ebx
0x1800cb521  jz      short loc_1800CB552
0x1800cb523  mov     rcx, [rsp+0A8h]; this
0x1800cb52b  mov     r9d, ebx; char *
0x1800cb52e  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb535  mov     edx, 3F5h; void *
0x1800cb53a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cb53f  mov     ebx, eax
0x1800cb541  lea     rcx, [rsp+0A8h+hKey]
0x1800cb546  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb54b  mov     eax, ebx
0x1800cb54d  jmp     loc_1800CB730
0x1800cb552  mov     [rsp+0A8h+var_50], 0
0x1800cb55b  xor     edx, edx
0x1800cb55d  lea     rcx, [rsp+0A8h+var_50]
0x1800cb562  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cb567  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1800cb570  lea     rax, [rsp+0A8h+var_50]
0x1800cb575  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800cb57a  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cb583  mov     [rsp+0A8h+samDesired], 0F003Fh; samDesired
0x1800cb58b  mov     [rsp+0A8h+dwOptions], 0; int
0x1800cb593  xor     r9d, r9d; lpClass
0x1800cb596  xor     r8d, r8d; Reserved
0x1800cb599  lea     rdx, aLastloggedstat; "LastLoggedState"
0x1800cb5a0  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800cb5a5  call    cs:__imp_RegCreateKeyExW
0x1800cb5ab  test    eax, eax
0x1800cb5ad  jz      short loc_1800CB5E9
0x1800cb5af  mov     rcx, [rsp+0A8h]; this
0x1800cb5b7  mov     r9d, eax; char *
0x1800cb5ba  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb5c1  mov     edx, 401h; void *
0x1800cb5c6  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cb5cb  mov     ebx, eax
0x1800cb5cd  lea     rcx, [rsp+0A8h+var_50]
0x1800cb5d2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb5d7  nop
0x1800cb5d8  lea     rcx, [rsp+0A8h+hKey]
0x1800cb5dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb5e2  mov     eax, ebx
0x1800cb5e4  jmp     loc_1800CB730
0x1800cb5e9  mov     [rsp+0A8h+var_58], 0
0x1800cb5f1  lea     r9, [rsp+0A8h+var_58]
0x1800cb5f6  mov     r8, rdi
0x1800cb5f9  xor     edx, edx
0x1800cb5fb  mov     rcx, [rsp+0A8h+var_50]
0x1800cb600  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cb606  mov     ebx, eax
0x1800cb608  cmp     eax, 80070001h
0x1800cb60d  jle     loc_1800CB6F6
0x1800cb613  lea     ecx, [rax+7FF8FFFCh]
0x1800cb619  cmp     ecx, 7FF8FFFBh
0x1800cb61f  jbe     loc_1800CB6F6
0x1800cb625  cmp     [rsp+0A8h+var_58], 0
0x1800cb62a  jnz     loc_1800CB6DD
0x1800cb630  lea     rax, aListretrievals; "ListRetrievalStarted"
0x1800cb637  cmp     rdi, rax
0x1800cb63a  jnz     short loc_1800CB65B
0x1800cb63c  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800cb643  jz      short loc_1800CB65B
0x1800cb645  mov     r9, rsi
0x1800cb648  lea     r8, aProvider; "Provider"
0x1800cb64f  lea     rdx, AutopilotManagerBeginningProviderTrackingListRetrieval
0x1800cb656  call    McTemplateU0zz_EventWriteTransfer
0x1800cb65b  lea     rax, aListretrievals_0; "ListRetrievalSucceeded"
0x1800cb662  cmp     rdi, rax
0x1800cb665  jnz     short loc_1800CB68B
0x1800cb667  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800cb66e  jz      short loc_1800CB68B
0x1800cb670  mov     [rsp+0A8h+dwOptions], r14d; int
0x1800cb675  mov     r9, rsi
0x1800cb678  lea     r8, aProvider; "Provider"
0x1800cb67f  lea     rdx, AutopilotManagerProviderTrackingListRetrievalSucceeded
0x1800cb686  call    McTemplateU0zzd_EventWriteTransfer
0x1800cb68b  mov     r9d, 1
0x1800cb691  mov     r8, rdi
0x1800cb694  xor     edx, edx
0x1800cb696  mov     rcx, [rsp+0A8h+var_50]
0x1800cb69b  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800cb6a1  mov     ebx, eax
0x1800cb6a3  test    eax, eax
0x1800cb6a5  jns     short loc_1800CB6DD
0x1800cb6a7  mov     rcx, [rsp+0A8h]; this
0x1800cb6af  mov     r9d, eax; char *
0x1800cb6b2  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb6b9  mov     edx, 413h; void *
0x1800cb6be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb6c3  nop
0x1800cb6c4  lea     rcx, [rsp+0A8h+var_50]
0x1800cb6c9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb6ce  nop
0x1800cb6cf  lea     rcx, [rsp+0A8h+hKey]
0x1800cb6d4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb6d9  mov     eax, ebx
0x1800cb6db  jmp     short loc_1800CB730
0x1800cb6dd  lea     rcx, [rsp+0A8h+var_50]
0x1800cb6e2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb6e7  nop
0x1800cb6e8  lea     rcx, [rsp+0A8h+hKey]
0x1800cb6ed  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb6f2  xor     eax, eax
0x1800cb6f4  jmp     short loc_1800CB730
0x1800cb6f6  mov     rcx, [rsp+0A8h]; this
0x1800cb6fe  mov     r9d, ebx; char *
0x1800cb701  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cb708  mov     edx, 405h; void *
0x1800cb70d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cb712  nop
0x1800cb713  lea     rcx, [rsp+0A8h+var_50]
0x1800cb718  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb71d  nop
0x1800cb71e  lea     rcx, [rsp+0A8h+hKey]
0x1800cb723  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cb728  mov     eax, ebx
0x1800cb72a  jmp     short loc_1800CB730
0x1800cb72c  mov     eax, [rsp+0A8h+var_58]
0x1800cb730  mov     rcx, [rsp+0A8h+var_20]
0x1800cb738  xor     rcx, rsp; StackCookie
0x1800cb73b  call    __security_check_cookie
0x1800cb740  mov     rbx, [rsp+0A8h+arg_10]
0x1800cb748  add     rsp, 90h
0x1800cb74f  pop     r14
0x1800cb751  pop     rdi
0x1800cb752  pop     rsi
0x1800cb753  retn
```
