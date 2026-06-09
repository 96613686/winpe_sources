# EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::LogTrackingListState(ushort const * const,ushort const * const,unsigned __int64)

- ea: `0x1800cd7b4`
- end: `0x1800cdaa5`
- name: `?LogTrackingListState@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CAJQEBG0_K@Z`
- size: `753`
- prototype: `static int(const unsigned __int16 *const, const unsigned __int16 *const, unsigned __int64)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800c9144`
- `0x1800c961c`

## callees

- `0x18000b8f0`
- `0x180067e54`
- `0x180077de0`
- `0x180080bac`
- `0x180084d80`
- `0x180088144`
- `0x18008a454`
- `0x1800cc544`
- `0x1800cd7b4`
- `0x1800d0440`
- `0x1800d04fc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd845`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd8e3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd845`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800cd8e3`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cd944`
- `DMCmnUtils!OmaDmRegistryGetDWORD` at `0x1800cd944`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cd9e5`
- `DMCmnUtils!OmaDmRegistrySetDWORD` at `0x1800cd9e5`

## string_xrefs

- `0x1800cd86c`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cd8fe`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cda02`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`
- `0x1800cda51`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\enrollmentstatustrackingutil.cpp`

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
0x1800cd7b4  mov     [rsp+arg_10], rbx
0x1800cd7b9  push    rsi
0x1800cd7ba  push    rdi
0x1800cd7bb  push    r14
0x1800cd7bd  sub     rsp, 90h
0x1800cd7c4  mov     rax, cs:__security_cookie
0x1800cd7cb  xor     rax, rsp
0x1800cd7ce  mov     [rsp+0A8h+var_20], rax
0x1800cd7d6  mov     r14, r8
0x1800cd7d9  mov     rdi, rdx
0x1800cd7dc  mov     rsi, rcx
0x1800cd7df  mov     [rsp+0A8h+hKey], 0
0x1800cd7e8  xor     edx, edx
0x1800cd7ea  lea     rcx, [rsp+0A8h+hKey]
0x1800cd7ef  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cd7f4  mov     rdx, rsi
0x1800cd7f7  lea     rcx, [rsp+0A8h+var_40]
0x1800cd7fc  call    ?GetProviderSubkeyName@EnrollmentStatusTrackingUtil@AutoPilot@Service@EnterpriseDeviceManagement@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBG@Z; EnterpriseDeviceManagement::Service::AutoPilot::EnrollmentStatusTrackingUtil::GetProviderSubkeyName(ushort const * const)
0x1800cd801  mov     rcx, rax
0x1800cd804  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800cd809  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1800cd812  lea     rcx, [rsp+0A8h+hKey]
0x1800cd817  mov     [rsp+0A8h+phkResult], rcx; phkResult
0x1800cd81c  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd825  mov     [rsp+0A8h+samDesired], 0F003Fh; samDesired
0x1800cd82d  mov     [rsp+0A8h+dwOptions], 0; unsigned int
0x1800cd835  xor     r9d, r9d; lpClass
0x1800cd838  xor     r8d, r8d; Reserved
0x1800cd83b  mov     rdx, rax; lpSubKey
0x1800cd83e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cd845  call    cs:__imp_RegCreateKeyExW
0x1800cd84c  nop     dword ptr [rax+rax+00h]
0x1800cd851  mov     ebx, eax
0x1800cd853  lea     rcx, [rsp+0A8h+var_40]
0x1800cd858  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cd85d  test    ebx, ebx
0x1800cd85f  jz      short loc_1800CD890
0x1800cd861  mov     rcx, [rsp+0A8h]; this
0x1800cd869  mov     r9d, ebx; char *
0x1800cd86c  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd873  mov     edx, 3F5h; void *
0x1800cd878  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cd87d  mov     ebx, eax
0x1800cd87f  lea     rcx, [rsp+0A8h+hKey]
0x1800cd884  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd889  mov     eax, ebx
0x1800cd88b  jmp     loc_1800CDA80
0x1800cd890  mov     [rsp+0A8h+var_50], 0
0x1800cd899  xor     edx, edx
0x1800cd89b  lea     rcx, [rsp+0A8h+var_50]
0x1800cd8a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800cd8a5  mov     [rsp+0A8h+lpdwDisposition], 0; lpdwDisposition
0x1800cd8ae  lea     rax, [rsp+0A8h+var_50]
0x1800cd8b3  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800cd8b8  mov     [rsp+0A8h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800cd8c1  mov     [rsp+0A8h+samDesired], 0F003Fh; samDesired
0x1800cd8c9  mov     [rsp+0A8h+dwOptions], 0; int
0x1800cd8d1  xor     r9d, r9d; lpClass
0x1800cd8d4  xor     r8d, r8d; Reserved
0x1800cd8d7  lea     rdx, aLastloggedstat; "LastLoggedState"
0x1800cd8de  mov     rcx, [rsp+0A8h+hKey]; hKey
0x1800cd8e3  call    cs:__imp_RegCreateKeyExW
0x1800cd8ea  nop     dword ptr [rax+rax+00h]
0x1800cd8ef  test    eax, eax
0x1800cd8f1  jz      short loc_1800CD92D
0x1800cd8f3  mov     rcx, [rsp+0A8h]; this
0x1800cd8fb  mov     r9d, eax; char *
0x1800cd8fe  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cd905  mov     edx, 401h; void *
0x1800cd90a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800cd90f  mov     ebx, eax
0x1800cd911  lea     rcx, [rsp+0A8h+var_50]
0x1800cd916  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd91b  nop
0x1800cd91c  lea     rcx, [rsp+0A8h+hKey]
0x1800cd921  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cd926  mov     eax, ebx
0x1800cd928  jmp     loc_1800CDA80
0x1800cd92d  mov     [rsp+0A8h+var_58], 0
0x1800cd935  lea     r9, [rsp+0A8h+var_58]
0x1800cd93a  mov     r8, rdi
0x1800cd93d  xor     edx, edx
0x1800cd93f  mov     rcx, [rsp+0A8h+var_50]
0x1800cd944  call    cs:__imp_?OmaDmRegistryGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; OmaDmRegistryGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800cd94b  nop     dword ptr [rax+rax+00h]
0x1800cd950  mov     ebx, eax
0x1800cd952  cmp     eax, 80070001h
0x1800cd957  jle     loc_1800CDA46
0x1800cd95d  lea     ecx, [rax+7FF8FFFCh]
0x1800cd963  cmp     ecx, 7FF8FFFBh
0x1800cd969  jbe     loc_1800CDA46
0x1800cd96f  cmp     [rsp+0A8h+var_58], 0
0x1800cd974  jnz     loc_1800CDA2D
0x1800cd97a  lea     rax, aListretrievals; "ListRetrievalStarted"
0x1800cd981  cmp     rdi, rax
0x1800cd984  jnz     short loc_1800CD9A5
0x1800cd986  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800cd98d  jz      short loc_1800CD9A5
0x1800cd98f  mov     r9, rsi
0x1800cd992  lea     r8, aProvider; "Provider"
0x1800cd999  lea     rdx, AutopilotManagerBeginningProviderTrackingListRetrieval
0x1800cd9a0  call    McTemplateU0zz_EventWriteTransfer
0x1800cd9a5  lea     rax, aListretrievals_0; "ListRetrievalSucceeded"
0x1800cd9ac  cmp     rdi, rax
0x1800cd9af  jnz     short loc_1800CD9D5
0x1800cd9b1  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1800cd9b8  jz      short loc_1800CD9D5
0x1800cd9ba  mov     [rsp+0A8h+dwOptions], r14d; int
0x1800cd9bf  mov     r9, rsi
0x1800cd9c2  lea     r8, aProvider; "Provider"
0x1800cd9c9  lea     rdx, AutopilotManagerProviderTrackingListRetrievalSucceeded
0x1800cd9d0  call    McTemplateU0zzd_EventWriteTransfer
0x1800cd9d5  mov     r9d, 1
0x1800cd9db  mov     r8, rdi
0x1800cd9de  xor     edx, edx
0x1800cd9e0  mov     rcx, [rsp+0A8h+var_50]
0x1800cd9e5  call    cs:__imp_?OmaDmRegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; OmaDmRegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800cd9ec  nop     dword ptr [rax+rax+00h]
0x1800cd9f1  mov     ebx, eax
0x1800cd9f3  test    eax, eax
0x1800cd9f5  jns     short loc_1800CDA2D
0x1800cd9f7  mov     rcx, [rsp+0A8h]; this
0x1800cd9ff  mov     r9d, eax; char *
0x1800cda02  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cda09  mov     edx, 413h; void *
0x1800cda0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cda13  nop
0x1800cda14  lea     rcx, [rsp+0A8h+var_50]
0x1800cda19  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cda1e  nop
0x1800cda1f  lea     rcx, [rsp+0A8h+hKey]
0x1800cda24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cda29  mov     eax, ebx
0x1800cda2b  jmp     short loc_1800CDA80
0x1800cda2d  lea     rcx, [rsp+0A8h+var_50]
0x1800cda32  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cda37  nop
0x1800cda38  lea     rcx, [rsp+0A8h+hKey]
0x1800cda3d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cda42  xor     eax, eax
0x1800cda44  jmp     short loc_1800CDA80
0x1800cda46  mov     rcx, [rsp+0A8h]; this
0x1800cda4e  mov     r9d, ebx; char *
0x1800cda51  lea     r8, aOnecoreuapAdmi_116; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800cda58  mov     edx, 405h; void *
0x1800cda5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cda62  nop
0x1800cda63  lea     rcx, [rsp+0A8h+var_50]
0x1800cda68  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cda6d  nop
0x1800cda6e  lea     rcx, [rsp+0A8h+hKey]
0x1800cda73  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cda78  mov     eax, ebx
0x1800cda7a  jmp     short loc_1800CDA80
0x1800cda7c  mov     eax, [rsp+0A8h+var_58]
0x1800cda80  mov     rcx, [rsp+0A8h+var_20]
0x1800cda88  xor     rcx, rsp; StackCookie
0x1800cda8b  call    __security_check_cookie
0x1800cda90  mov     rbx, [rsp+0A8h+arg_10]
0x1800cda98  add     rsp, 90h
0x1800cda9f  pop     r14
0x1800cdaa1  pop     rdi
0x1800cdaa2  pop     rsi
0x1800cdaa3  retn
```
