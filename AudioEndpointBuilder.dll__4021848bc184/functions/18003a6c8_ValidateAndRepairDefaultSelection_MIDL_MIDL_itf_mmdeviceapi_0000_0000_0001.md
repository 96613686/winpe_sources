# ValidateAndRepairDefaultSelection(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)

- ea: `0x18003a6c8`
- end: `0x18003aba8`
- name: `?ValidateAndRepairDefaultSelection@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@@Z`
- size: `1248`
- prototype: `__int64 __fastcall(enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180039d90`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180012e80`
- `0x18001707c`
- `0x1800395ec`
- `0x18003a6c8`
- `0x18003abb0`
- `0x18003e920`
- `0x18003e944`
- `0x18003ee40`
- `0x18005a72c`
- `0x18005a948`
- `0x18005ab60`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a836`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18003a836`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a90e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a90e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a9c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aa92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aad1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003a9c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aa92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003aad1`

## string_xrefs

- `0x18003a7bc`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a7d7`: `avcore\audiocore\server\audioendpointbuilder\dll\audmig.cpp`
- `0x18003a94d`: `Repairing default to %s\n`
- `0x18003a99a`: `Repair complete\n`
- `0x18003a98c`: `Repair failed (0x%08x)\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall ValidateAndRepairDefaultSelection(enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001 a1)
{
  __int64 v1; // r12
  int DefaultIds; // eax
  unsigned int v3; // ebx
  __int64 v4; // rdx
  enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0002 i; // r15d
  unsigned __int16 *v6; // rcx
  unsigned __int16 *v7; // rdx
  int MatchingEndpoint; // eax
  struct IMMDevice *v9; // rbx
  int v10; // eax
  int v11; // edi
  HRESULT v12; // eax
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rdi
  int v14; // eax
  int v15; // eax
  unsigned int v16; // ebx
  int ppv; // [rsp+20h] [rbp-69h]
  LPVOID pv; // [rsp+30h] [rbp-59h] BYREF
  struct IMMDevice *v20; // [rsp+38h] [rbp-51h] BYREF
  int v21; // [rsp+40h] [rbp-49h] BYREF
  LPVOID v22; // [rsp+48h] [rbp-41h] BYREF
  unsigned __int16 *v23[3]; // [rsp+50h] [rbp-39h] BYREF
  unsigned __int16 *v24[3]; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v25[3]; // [rsp+80h] [rbp-9h] BYREF
  _QWORD v26[3]; // [rsp+98h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v1 = a1;
  `eh vector constructor iterator'(
    v26,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector constructor iterator'(
    v24,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector constructor iterator'(
    v25,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector constructor iterator'(
    v23,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  AudMigLibSetupLog(L"Validating default selection for %s\r\n", off_18006AD60[v1]);
  DefaultIds = GetDefaultIds(v1, (__int64)v26, (__int64)v24);
  v3 = DefaultIds;
  if ( DefaultIds < 0 )
  {
    v4 = 1880;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
      (const char *)(unsigned int)DefaultIds,
      ppv);
    goto LABEL_43;
  }
  DefaultIds = GetPreviousIds(v1, (__int64)v25, (__int64)v23);
  v3 = DefaultIds;
  if ( DefaultIds < 0 )
  {
    v4 = 1881;
    goto LABEL_5;
  }
  for ( i = eConsole; ; ++i )
  {
    if ( (unsigned int)i >= ERole_enum_count )
    {
      v3 = 0;
      goto LABEL_43;
    }
    AudMigLibSetupLog(L"Checking default for %s\r\n", off_18006AD40[i]);
    AEBTelemetry::LogPostUpgradeDefaultInformation(
      (enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001)v1,
      i,
      v23[i],
      v24[i]);
    v6 = v24[i];
    if ( v6 )
    {
      v7 = v23[i];
      if ( v7 )
      {
        if ( (unsigned int)_o__wcsicmp(v6, v7) )
          break;
      }
    }
    if ( v24[i] )
    {
      if ( !v23[i] )
      {
        AudMigLibSetupLog(L"Prior OS lacking a default, or migration issue encountered\r\n");
        continue;
      }
    }
    else if ( v23[i] )
    {
      AudMigLibSetupLog(L"There is no default available in the system, but there was one prior to upgrade\r\n");
      AEBTelemetry::LogDefaultDeviceIssue(L"NoDefault", v23[i]);
      continue;
    }
    AudMigLibSetupLog(L"default is as expected\r\n");
LABEL_32:
    ;
  }
  AudMigLibSetupLog(L"Incorrect defaults, actual %s, expected %s\r\n", v24[i], v23[i]);
  AudMigLibSetupLog(L"Incorrect defaults, actual %s, expected %s\r\n", v26[i], v25[i]);
  v20 = 0;
  MatchingEndpoint = FindMatchingEndpoint((struct IMMDeviceEnumerator *)g_DeviceEnumerator, v23[i], &v20);
  v3 = MatchingEndpoint;
  if ( MatchingEndpoint < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76E,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
      (const char *)(unsigned int)MatchingEndpoint,
      ppv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
    goto LABEL_43;
  }
  v9 = v20;
  if ( !v20 )
  {
    AudMigLibSetupLog(L"Unable to locate an endpoint matching the prior os endpoint, migration data lost\r\n");
    AEBTelemetry::LogDefaultDeviceIssue(L"DefaultIdentificationProblem", v23[i]);
    goto LABEL_25;
  }
  v21 = 0;
  AudMigLibSetupLog(L"Matching migration endpoint located\r\n");
  v10 = ((__int64 (__fastcall *)(struct IMMDevice *, int *))v9->lpVtbl->GetState)(v9, &v21);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x774,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
      (const char *)(unsigned int)v10,
      ppv);
LABEL_39:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
    v3 = v11;
    goto LABEL_43;
  }
  if ( v21 != 1 )
  {
    AudMigLibSetupLog(L"Migration data located, not active state=%d\r\n");
    AEBTelemetry::LogDefaultDeviceIssue(L"DefaultNotActive", v23[i]);
LABEL_25:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
    goto LABEL_32;
  }
  v22 = 0;
  pv = 0;
  v12 = CoCreateInstance(
          &GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9,
          0,
          0x17u,
          &GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46,
          &v22);
  v11 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x77A,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
      (const char *)(unsigned int)v12,
      ppv);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    goto LABEL_39;
  }
  GetId = v9->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v14 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(v9, &pv);
  v3 = v14;
  if ( v14 >= 0 )
  {
    AudMigLibSetupLog(L"Repairing default to %s\r\n", pv);
    v15 = (*(__int64 (__fastcall **)(LPVOID, LPVOID, _QWORD))(*(_QWORD *)v22 + 104LL))(v22, pv, (unsigned int)i);
    v16 = v15;
    if ( v15 >= 0 )
    {
      AudMigLibSetupLog(L"Repair complete\r\n");
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x785,
        (int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
        (const char *)(unsigned int)v15);
      AudMigLibSetupLog(L"Repair failed (0x%08x)\r\n", v16);
    }
    AEBTelemetry::LogDefaultDeviceIssue(L"DefaultChangedProblemWithOtherEndpoint", v24[i]);
    if ( pv )
      CoTaskMemFree(pv);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x77E,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audmig.cpp",
    (const char *)(unsigned int)v14,
    ppv);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v20);
LABEL_43:
  `eh vector destructor iterator'(
    v23,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector destructor iterator'(
    v25,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector destructor iterator'(
    v24,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  `eh vector destructor iterator'(
    v26,
    8u,
    3u,
    (void (*)(void *))wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
  return v3;
}

```

## disassembly

```asm
0x18003a6c8  mov     [rsp-8+arg_8], rbx
0x18003a6cd  mov     [rsp-8+arg_10], rsi
0x18003a6d2  push    rbp
0x18003a6d3  push    rdi
0x18003a6d4  push    r12
0x18003a6d6  push    r14
0x18003a6d8  push    r15
0x18003a6da  lea     rbp, [rsp-37h]
0x18003a6df  sub     rsp, 0C0h
0x18003a6e6  mov     rax, cs:__security_cookie
0x18003a6ed  xor     rax, rsp
0x18003a6f0  mov     [rbp+57h+var_30], rax
0x18003a6f4  movsxd  r12, ecx
0x18003a6f7  lea     r14, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003a6fe  mov     qword ptr [rsp+0E0h+ppv], r14; void (*)(void *)
0x18003a703  lea     rbx, ??0?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003a70a  mov     r9, rbx; void (*)(void *)
0x18003a70d  mov     edi, 3
0x18003a712  mov     r8d, edi; unsigned __int64
0x18003a715  lea     esi, [rdi+5]
0x18003a718  mov     edx, esi; unsigned __int64
0x18003a71a  lea     rcx, [rbp+57h+var_48]; void *
0x18003a71e  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003a723  nop
0x18003a724  mov     qword ptr [rsp+0E0h+ppv], r14; void (*)(void *)
0x18003a729  mov     r9, rbx; void (*)(void *)
0x18003a72c  mov     r8d, edi; unsigned __int64
0x18003a72f  mov     edx, esi; unsigned __int64
0x18003a731  lea     rcx, [rbp+57h+var_78]; void *
0x18003a735  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003a73a  nop
0x18003a73b  mov     qword ptr [rsp+0E0h+ppv], r14; void (*)(void *)
0x18003a740  mov     r9, rbx; void (*)(void *)
0x18003a743  mov     r8d, edi; unsigned __int64
0x18003a746  mov     edx, esi; unsigned __int64
0x18003a748  lea     rcx, [rbp+57h+var_60]; void *
0x18003a74c  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003a751  nop
0x18003a752  mov     qword ptr [rsp+0E0h+ppv], r14; int
0x18003a757  mov     r9, rbx; void (*)(void *)
0x18003a75a  mov     r8d, edi; unsigned __int64
0x18003a75d  mov     edx, esi; unsigned __int64
0x18003a75f  lea     rcx, [rbp+57h+var_90]; void *
0x18003a763  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x18003a768  nop
0x18003a769  lea     rax, __ImageBase
0x18003a770  mov     rdx, ds:rva off_18006AD60[rax+r12*8]; "Render" ...
0x18003a778  lea     rcx, aValidatingDefa; "Validating default selection for %s\r\n"
0x18003a77f  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a784  lea     r8, [rbp+57h+var_78]
0x18003a788  lea     rdx, [rbp+57h+var_48]
0x18003a78c  mov     ecx, r12d
0x18003a78f  call    ?GetDefaultIds@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@1@Z; GetDefaultIds(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const)
0x18003a794  mov     ebx, eax
0x18003a796  test    eax, eax
0x18003a798  jns     short loc_18003A7A1
0x18003a79a  mov     edx, 758h
0x18003a79f  jmp     short loc_18003A7BC
0x18003a7a1  lea     r8, [rbp+57h+var_90]
0x18003a7a5  lea     rdx, [rbp+57h+var_60]
0x18003a7a9  mov     ecx, r12d
0x18003a7ac  call    ?GetPreviousIds@@YAJW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@1@Z; GetPreviousIds(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> * const)
0x18003a7b1  mov     ebx, eax
0x18003a7b3  test    eax, eax
0x18003a7b5  jns     short loc_18003A7D4
0x18003a7b7  mov     edx, 759h; void *
0x18003a7bc  lea     r8, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x18003a7c3  mov     r9d, eax; char *
0x18003a7c6  mov     rcx, [rbp+5Fh]; this
0x18003a7ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003a7cf  jmp     loc_18003AB2C
0x18003a7d4  xor     r15d, r15d
0x18003a7d7  lea     r14, aAvcoreAudiocor_10; "avcore\\audiocore\\server\\audioendpoin"...
0x18003a7de  cmp     r15d, edi
0x18003a7e1  jnb     loc_18003AB25
0x18003a7e7  movsxd  rsi, r15d
0x18003a7ea  lea     rax, __ImageBase
0x18003a7f1  mov     rdx, ds:rva off_18006AD40[rax+rsi*8]; "Console" ...
0x18003a7f9  lea     rcx, aCheckingDefaul; "Checking default for %s\r\n"
0x18003a800  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a805  mov     r9, [rbp+rsi*8+57h+var_78]; unsigned __int16 *
0x18003a80a  mov     r8, [rbp+rsi*8+57h+var_90]; unsigned __int16 *
0x18003a80f  mov     edx, r15d; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0002
0x18003a812  mov     ecx, r12d; enum __MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001
0x18003a815  call    ?LogPostUpgradeDefaultInformation@AEBTelemetry@@SAXW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@W4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0002@@PEBG2@Z; AEBTelemetry::LogPostUpgradeDefaultInformation(__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0002,ushort const *,ushort const *)
0x18003a81a  mov     rcx, [rbp+rsi*8+57h+var_78]
0x18003a81f  test    rcx, rcx
0x18003a822  jz      loc_18003AA20
0x18003a828  mov     rdx, [rbp+rsi*8+57h+var_90]
0x18003a82d  test    rdx, rdx
0x18003a830  jz      loc_18003AA20
0x18003a836  call    cs:__imp__o__wcsicmp
0x18003a83c  test    eax, eax
0x18003a83e  jz      loc_18003AA20
0x18003a844  mov     r8, [rbp+rsi*8+57h+var_90]
0x18003a849  mov     rdx, [rbp+rsi*8+57h+var_78]
0x18003a84e  lea     rcx, aIncorrectDefau; "Incorrect defaults, actual %s, expected"...
0x18003a855  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a85a  mov     r8, [rbp+rsi*8+57h+var_60]
0x18003a85f  mov     rdx, [rbp+rsi*8+57h+var_48]
0x18003a864  lea     rcx, aIncorrectDefau; "Incorrect defaults, actual %s, expected"...
0x18003a86b  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a870  nop
0x18003a871  mov     [rbp+57h+var_A8], 0
0x18003a879  lea     r8, [rbp+57h+var_A8]; struct IMMDevice **
0x18003a87d  mov     rdx, [rbp+rsi*8+57h+var_90]; unsigned __int16 *
0x18003a882  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; struct IMMDeviceEnumerator *
0x18003a889  call    ?FindMatchingEndpoint@@YAJPEAUIMMDeviceEnumerator@@PEAGPEAPEAUIMMDevice@@@Z; FindMatchingEndpoint(IMMDeviceEnumerator *,ushort *,IMMDevice * *)
0x18003a88e  mov     ebx, eax
0x18003a890  test    eax, eax
0x18003a892  js      loc_18003AB05
0x18003a898  mov     rbx, [rbp+57h+var_A8]
0x18003a89c  test    rbx, rbx
0x18003a89f  jz      loc_18003A9F7
0x18003a8a5  mov     [rbp+57h+var_A0], 0
0x18003a8ac  lea     rcx, aMatchingMigrat; "Matching migration endpoint located\r\n"
0x18003a8b3  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a8b8  mov     rax, [rbx]
0x18003a8bb  lea     rdx, [rbp+57h+var_A0]
0x18003a8bf  mov     rcx, rbx
0x18003a8c2  mov     rax, [rax+30h]
0x18003a8c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a8cb  mov     edi, eax
0x18003a8cd  test    eax, eax
0x18003a8cf  js      loc_18003AAEF
0x18003a8d5  mov     edx, [rbp+57h+var_A0]
0x18003a8d8  cmp     edx, 1
0x18003a8db  jnz     loc_18003A9D3
0x18003a8e1  mov     [rbp+57h+var_98], 0
0x18003a8e9  mov     [rbp+57h+pv], 0
0x18003a8f1  lea     rax, [rbp+57h+var_98]
0x18003a8f5  mov     qword ptr [rsp+0E0h+ppv], rax; int
0x18003a8fa  lea     r9, _GUID_e8478600_a74b_4b3a_a96b_1fc3e796fc46; riid
0x18003a901  xor     edx, edx; pUnkOuter
0x18003a903  lea     r8d, [rdx+17h]; dwClsContext
0x18003a907  lea     rcx, _GUID_870af99c_171d_4f9e_af0d_e63df40c2bc9; rclsid
0x18003a90e  call    cs:__imp_CoCreateInstance
0x18003a914  mov     edi, eax
0x18003a916  test    eax, eax
0x18003a918  js      loc_18003AAB3
0x18003a91e  mov     rax, [rbx]
0x18003a921  mov     rdi, [rax+28h]
0x18003a925  xor     edx, edx
0x18003a927  lea     rcx, [rbp+57h+pv]
0x18003a92b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003a930  lea     rdx, [rbp+57h+pv]
0x18003a934  mov     rcx, rbx
0x18003a937  mov     rax, rdi
0x18003a93a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a93f  mov     ebx, eax
0x18003a941  test    eax, eax
0x18003a943  js      loc_18003AA74
0x18003a949  mov     rdx, [rbp+57h+pv]
0x18003a94d  lea     rcx, aRepairingDefau; "Repairing default to %s\r\n"
0x18003a954  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a959  mov     rcx, [rbp+57h+var_98]
0x18003a95d  mov     rax, [rcx]
0x18003a960  mov     r8d, r15d
0x18003a963  mov     rdx, [rbp+57h+pv]
0x18003a967  mov     rax, [rax+68h]
0x18003a96b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a970  mov     ebx, eax
0x18003a972  mov     rcx, [rbp+5Fh]; this
0x18003a976  test    eax, eax
0x18003a978  jns     short loc_18003A99A
0x18003a97a  mov     r9d, eax; char *
0x18003a97d  mov     r8, r14; unsigned int
0x18003a980  mov     edx, 785h; void *
0x18003a985  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003a98a  mov     edx, ebx
0x18003a98c  lea     rcx, aRepairFailed0x; "Repair failed (0x%08x)\r\n"
0x18003a993  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a998  jmp     short loc_18003A9A6
0x18003a99a  lea     rcx, aRepairComplete; "Repair complete\r\n"
0x18003a9a1  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a9a6  mov     rdx, [rbp+rsi*8+57h+var_78]; unsigned __int16 *
0x18003a9ab  lea     rcx, aDefaultchanged; "DefaultChangedProblemWithOtherEndpoint"
0x18003a9b2  call    ?LogDefaultDeviceIssue@AEBTelemetry@@SAXPEBG0@Z; AEBTelemetry::LogDefaultDeviceIssue(ushort const *,ushort const *)
0x18003a9b7  nop
0x18003a9b8  mov     rcx, [rbp+57h+pv]; pv
0x18003a9bc  test    rcx, rcx
0x18003a9bf  jz      short loc_18003A9C8
0x18003a9c1  call    cs:__imp_CoTaskMemFree
0x18003a9c7  nop
0x18003a9c8  lea     rcx, [rbp+57h+var_98]
0x18003a9cc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003a9d1  jmp     short loc_18003A9F0
0x18003a9d3  lea     rcx, aMigrationDataL; "Migration data located, not active stat"...
0x18003a9da  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003a9df  mov     rdx, [rbp+rsi*8+57h+var_90]; unsigned __int16 *
0x18003a9e4  lea     rcx, aDefaultnotacti; "DefaultNotActive"
0x18003a9eb  call    ?LogDefaultDeviceIssue@AEBTelemetry@@SAXPEBG0@Z; AEBTelemetry::LogDefaultDeviceIssue(ushort const *,ushort const *)
0x18003a9f0  mov     edi, 3
0x18003a9f5  jmp     short loc_18003AA15
0x18003a9f7  lea     rcx, aUnableToLocate; "Unable to locate an endpoint matching t"...
0x18003a9fe  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003aa03  mov     rdx, [rbp+rsi*8+57h+var_90]; unsigned __int16 *
0x18003aa08  lea     rcx, aDefaultidentif; "DefaultIdentificationProblem"
0x18003aa0f  call    ?LogDefaultDeviceIssue@AEBTelemetry@@SAXPEBG0@Z; AEBTelemetry::LogDefaultDeviceIssue(ushort const *,ushort const *)
0x18003aa14  nop
0x18003aa15  lea     rcx, [rbp+57h+var_A8]
0x18003aa19  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003aa1e  jmp     short loc_18003AA6C
0x18003aa20  cmp     [rbp+rsi*8+57h+var_78], 0
0x18003aa26  jz      short loc_18003AA39
0x18003aa28  cmp     [rbp+rsi*8+57h+var_90], 0
0x18003aa2e  jnz     short loc_18003AA60
0x18003aa30  lea     rcx, aPriorOsLacking; "Prior OS lacking a default, or migratio"...
0x18003aa37  jmp     short loc_18003AA67
0x18003aa39  cmp     [rbp+rsi*8+57h+var_90], 0
0x18003aa3f  jz      short loc_18003AA60
0x18003aa41  lea     rcx, aThereIsNoDefau; "There is no default available in the sy"...
0x18003aa48  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003aa4d  mov     rdx, [rbp+rsi*8+57h+var_90]; unsigned __int16 *
0x18003aa52  lea     rcx, aNodefault; "NoDefault"
0x18003aa59  call    ?LogDefaultDeviceIssue@AEBTelemetry@@SAXPEBG0@Z; AEBTelemetry::LogDefaultDeviceIssue(ushort const *,ushort const *)
0x18003aa5e  jmp     short loc_18003AA6C
0x18003aa60  lea     rcx, aDefaultIsAsExp; "default is as expected\r\n"
0x18003aa67  call    ?AudMigLibSetupLog@@YAXPEBGZZ; AudMigLibSetupLog(ushort const *,...)
0x18003aa6c  inc     r15d
0x18003aa6f  jmp     loc_18003A7DE
0x18003aa74  mov     rcx, [rbp+5Fh]; this
0x18003aa78  mov     r9d, eax; char *
0x18003aa7b  mov     r8, r14; unsigned int
0x18003aa7e  mov     edx, 77Eh; void *
0x18003aa83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aa88  nop
0x18003aa89  mov     rcx, [rbp+57h+pv]; pv
0x18003aa8d  test    rcx, rcx
0x18003aa90  jz      short loc_18003AA99
0x18003aa92  call    cs:__imp_CoTaskMemFree
0x18003aa98  nop
0x18003aa99  lea     rcx, [rbp+57h+var_98]
0x18003aa9d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003aaa2  nop
0x18003aaa3  lea     rcx, [rbp+57h+var_A8]
0x18003aaa7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003aaac  mov     edi, 3
0x18003aab1  jmp     short loc_18003AB27
0x18003aab3  mov     rcx, [rbp+5Fh]; this
0x18003aab7  mov     r9d, edi; char *
0x18003aaba  mov     r8, r14; unsigned int
0x18003aabd  mov     edx, 77Ah; void *
0x18003aac2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003aac7  nop
0x18003aac8  mov     rcx, [rbp+57h+pv]; pv
0x18003aacc  test    rcx, rcx
0x18003aacf  jz      short loc_18003AAD8
0x18003aad1  call    cs:__imp_CoTaskMemFree
0x18003aad7  nop
0x18003aad8  lea     rcx, [rbp+57h+var_98]
0x18003aadc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003aae1  nop
0x18003aae2  lea     rcx, [rbp+57h+var_A8]
0x18003aae6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003aaeb  mov     ebx, edi
0x18003aaed  jmp     short loc_18003AAAC
0x18003aaef  mov     rcx, [rbp+5Fh]; this
0x18003aaf3  mov     r9d, edi; char *
0x18003aaf6  mov     r8, r14; unsigned int
0x18003aaf9  mov     edx, 774h; void *
0x18003aafe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab03  jmp     short loc_18003AAE2
0x18003ab05  mov     rcx, [rbp+5Fh]; this
0x18003ab09  mov     r9d, eax; char *
0x18003ab0c  mov     r8, r14; unsigned int
0x18003ab0f  mov     edx, 76Eh; void *
0x18003ab14  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ab19  nop
0x18003ab1a  lea     rcx, [rbp+57h+var_A8]
0x18003ab1e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18003ab23  jmp     short loc_18003AB27
0x18003ab25  xor     ebx, ebx
0x18003ab27  mov     esi, 8
0x18003ab2c  lea     r14, ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18003ab33  mov     r9, r14; void (*)(void *)
0x18003ab36  mov     r8, rdi; unsigned __int64
0x18003ab39  mov     rdx, rsi; unsigned __int64
0x18003ab3c  lea     rcx, [rbp+57h+var_90]; void *
0x18003ab40  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003ab45  nop
0x18003ab46  mov     r9, r14; void (*)(void *)
0x18003ab49  mov     r8, rdi; unsigned __int64
0x18003ab4c  mov     rdx, rsi; unsigned __int64
0x18003ab4f  lea     rcx, [rbp+57h+var_60]; void *
0x18003ab53  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003ab58  nop
0x18003ab59  mov     r9, r14; void (*)(void *)
0x18003ab5c  mov     r8, rdi; unsigned __int64
0x18003ab5f  mov     rdx, rsi; unsigned __int64
0x18003ab62  lea     rcx, [rbp+57h+var_78]; void *
0x18003ab66  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003ab6b  nop
0x18003ab6c  mov     r9, r14; void (*)(void *)
0x18003ab6f  mov     r8, rdi; unsigned __int64
0x18003ab72  mov     rdx, rsi; unsigned __int64
0x18003ab75  lea     rcx, [rbp+57h+var_48]; void *
0x18003ab79  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003ab7e  mov     eax, ebx
0x18003ab80  mov     rcx, [rbp+57h+var_30]
  ... truncated ...
```
