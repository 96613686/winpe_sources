# InitComServer(ulong,ulong)

- ea: `0x140022b5c`
- end: `0x1400234b1`
- name: `?InitComServer@@YAJKK@Z`
- size: `2389`
- prototype: `signed int __fastcall()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002d070`

## callees

- `0x140022b5c`
- `0x1400234b8`
- `0x140029274`
- `0x140046430`
- `0x140048010`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x140022cbd`
- `ntdll!RtlCreateAcl` at `0x140022cbd`
- `ntdll!RtlNtStatusToDosError` at `0x140022fd8`
- `ntdll!RtlNtStatusToDosError` at `0x140023218`
- `ntdll!RtlNtStatusToDosError` at `0x140022fd8`
- `ntdll!RtlNtStatusToDosError` at `0x140023218`
- `ntdll!RtlAddAccessAllowedAce` at `0x140022cd9`
- `ntdll!RtlAddAccessAllowedAce` at `0x140022cd9`
- `ntdll!RtlLengthSid` at `0x140022c95`
- `ntdll!RtlLengthSid` at `0x140022c95`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022ff6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023236`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022ce7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140022ff6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140023236`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140022ca2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x140022ca2`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140022d3d`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x140022d3d`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140022bcc`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x140022bcc`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022c12`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022c71`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022c12`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x140022c71`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140022d22`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorGroup` at `0x140022d22`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x140022c25`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140022d07`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x140022d07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002309b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002317b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002319c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231e3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022e5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022e92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022eb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140022f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002309b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140023150`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002317b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002319c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400231e3`
- `wbemcomn!GetMemLogObject` at `0x140022f19`
- `wbemcomn!GetMemLogObject` at `0x1400230ba`
- `wbemcomn!GetMemLogObject` at `0x140023193`
- `wbemcomn!GetMemLogObject` at `0x1400231bb`
- `wbemcomn!GetMemLogObject` at `0x140023240`
- `wbemcomn!GetMemLogObject` at `0x1400232e6`
- `wbemcomn!GetMemLogObject` at `0x14002332d`
- `wbemcomn!GetMemLogObject` at `0x140023374`
- `wbemcomn!GetMemLogObject` at `0x1400233bb`
- `wbemcomn!GetMemLogObject` at `0x140023408`
- `wbemcomn!GetMemLogObject` at `0x140023474`
- `wbemcomn!GetMemLogObject` at `0x140022f19`
- `wbemcomn!GetMemLogObject` at `0x1400230ba`
- `wbemcomn!GetMemLogObject` at `0x140023193`
- `wbemcomn!GetMemLogObject` at `0x1400231bb`
- `wbemcomn!GetMemLogObject` at `0x140023240`
- `wbemcomn!GetMemLogObject` at `0x1400232e6`
- `wbemcomn!GetMemLogObject` at `0x14002332d`
- `wbemcomn!GetMemLogObject` at `0x140023374`
- `wbemcomn!GetMemLogObject` at `0x1400233bb`
- `wbemcomn!GetMemLogObject` at `0x140023408`
- `wbemcomn!GetMemLogObject` at `0x140023474`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140022f29`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400230c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400231b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400231d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002324b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400232f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023338`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002337f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400233c6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023413`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002347f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140022f29`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400230c5`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400231b0`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400231d8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002324b`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400232f1`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023338`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002337f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x1400233c6`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x140023413`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14002347f`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022e58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022ec8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022f13`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022f63`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022f88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022fed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002304d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400230b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140023113`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002322d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140023402`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022e58`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022ec8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022f13`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022f63`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022f88`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140022fed`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002304d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1400230b0`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140023113`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x14002322d`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x140023402`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140022b87`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x140022b87`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140022d83`
- `api-ms-win-core-com-l1-1-0!CoInitializeSecurity` at `0x140022d83`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140022ddc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140022ddc`

## pseudocode

```c
signed int __fastcall InitComServer()
{
  HRESULT v0; // ebx
  PSID v1; // r15
  PSID v2; // r12
  SIZE_T v3; // rbx
  struct _ACL *v4; // rax
  struct _ACL *v5; // rsi
  int Acl; // eax
  int v7; // eax
  signed int result; // eax
  signed int v9; // eax
  bool v10; // sf
  signed int v11; // eax
  signed int v12; // edi
  signed int v13; // eax
  CMemoryLog *v14; // rax
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  signed int LastError; // eax
  CMemoryLog *MemLogObject; // rax
  signed int v20; // eax
  bool v21; // sf
  signed int v22; // eax
  CMemoryLog *v23; // rdi
  signed int v24; // eax
  CMemoryLog *v25; // rdi
  signed int v26; // eax
  signed int v27; // eax
  signed int v28; // eax
  CMemoryLog *v29; // rax
  CMemoryLog *v30; // rax
  CMemoryLog *v31; // rax
  CMemoryLog *v32; // rax
  CMemoryLog *v33; // rax
  CMemoryLog *v34; // rax
  CMemoryLog *v35; // rax
  PSID Sid; // [rsp+60h] [rbp-A0h] BYREF
  PSID pOwner; // [rsp+68h] [rbp-98h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-90h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v40; // [rsp+98h] [rbp-68h]
  _BYTE v41[8]; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL (__stdcall *v42)(HLOCAL); // [rsp+A8h] [rbp-58h]
  struct _ACL *v43; // [rsp+B0h] [rbp-50h]
  _BYTE v44[8]; // [rsp+B8h] [rbp-48h] BYREF
  PVOID (__stdcall *v45)(PSID); // [rsp+C0h] [rbp-40h]
  PSID v46; // [rsp+C8h] [rbp-38h]
  _BYTE v47[8]; // [rsp+D0h] [rbp-30h] BYREF
  PVOID (__stdcall *v48)(PSID); // [rsp+D8h] [rbp-28h]
  PSID v49; // [rsp+E0h] [rbp-20h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+E8h] [rbp-18h] BYREF

  v0 = CoInitializeEx(0, 0);
  if ( v0 < 0 )
    goto LABEL_13;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v40 = 0;
  pOwner = 0;
  Sid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError > 0 )
      v12 = (unsigned __int16)LastError | 0x80070000;
    CoUninitialize();
    if ( v12 < 0 )
    {
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, v12);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
        (unsigned int)v12);
    }
    return v12;
  }
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0xBu, 0, 0, 0, 0, 0, 0, 0, &Sid) )
  {
    v1 = Sid;
    v47[0] = 0;
    v48 = FreeSid;
    v49 = Sid;
    if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &pOwner) )
    {
      CoUninitialize();
      v9 = GetLastError();
      v10 = v9 < 0;
      if ( v9 > 0 )
        v10 = 1;
      if ( v10 )
      {
        v25 = GetMemLogObject();
        v26 = GetLastError();
        if ( v26 > 0 )
          v26 = (unsigned __int16)v26 | 0x80070000;
        CMemoryLog::Write(v25, v26);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v27 = GetLastError();
        if ( v27 > 0 )
          v27 = (unsigned __int16)v27 | 0x80070000;
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          12,
          WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
          (unsigned int)v27);
      }
      v11 = GetLastError();
      v12 = v11;
      if ( v11 > 0 )
        v12 = (unsigned __int16)v11 | 0x80070000;
      ((void (__fastcall *)(PSID))FreeSid)(v1);
      return v12;
    }
    v2 = pOwner;
    v44[0] = 0;
    v45 = FreeSid;
    v46 = pOwner;
    v3 = RtlLengthSid(Sid) + 20;
    v4 = (struct _ACL *)LocalAlloc(0, v3);
    v5 = v4;
    if ( !v4 )
    {
      CoUninitialize();
      v14 = GetMemLogObject();
      v0 = -2147024888;
      CMemoryLog::Write(v14, -2147024888);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids, 2147942408LL);
      }
      ((void (__fastcall *)(PSID))FreeSid)(v2);
      ((void (__fastcall *)(PSID))FreeSid)(v1);
      return v0;
    }
    Acl = RtlCreateAcl(v4, v3, 2u);
    if ( Acl < 0 )
    {
      v16 = RtlNtStatusToDosError(Acl);
      v12 = v16;
      if ( v16 > 0 )
        v12 = (unsigned __int16)v16 | 0x80070000;
      CoUninitialize();
      LocalFree(v5);
      if ( v12 < 0 )
      {
        v30 = GetMemLogObject();
        CMemoryLog::Write(v30, v12);
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
          (unsigned int)v12);
      }
      ((void (__fastcall *)(PSID))FreeSid)(v2);
      ((void (__fastcall *)(PSID))FreeSid)(v1);
      return v12;
    }
    v7 = RtlAddAccessAllowedAce(v5, 2u, 1u, Sid);
    if ( v7 >= 0 )
    {
      v41[0] = 0;
      v42 = LocalFree;
      v43 = v5;
      if ( SetSecurityDescriptorOwner(pSecurityDescriptor, pOwner, 0) )
      {
        if ( SetSecurityDescriptorGroup(pSecurityDescriptor, pOwner, 0) )
        {
          if ( SetSecurityDescriptorDacl(pSecurityDescriptor, 1, v5, 0) )
          {
            v0 = CoInitializeSecurity(pSecurityDescriptor, -1, 0, 0, 2u, 3u, 0, 0x40u, 0);
            if ( v0 >= 0 )
            {
              ((void (__fastcall *)(struct _ACL *))LocalFree)(v5);
              ((void (__fastcall *)(PSID))FreeSid)(v2);
              ((void (__fastcall *)(PSID))FreeSid)(v1);
LABEL_13:
              ppv = 0;
              if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &IID_IGlobalOptions, &ppv) < 0 )
              {
                CoUninitialize();
                return 14;
              }
              (*(void (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)ppv + 24LL))(ppv, 1, 1);
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
              if ( v0 < 0 )
              {
                v35 = GetMemLogObject();
                CMemoryLog::Write(v35, v0);
              }
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
                && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  21,
                  WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
                  (unsigned int)v0);
              }
              return v0;
            }
            CoUninitialize();
            v34 = GetMemLogObject();
            CMemoryLog::Write(v34, v0);
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                20,
                WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
                (unsigned int)v0);
            }
            ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(v41);
            v12 = v0;
            goto LABEL_114;
          }
          v17 = GetLastError();
          v12 = v17;
          if ( v17 > 0 )
            v12 = (unsigned __int16)v17 | 0x80070000;
          CoUninitialize();
          if ( v12 < 0 )
          {
            v33 = GetMemLogObject();
            CMemoryLog::Write(v33, v12);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              19,
              WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
              (unsigned int)v12);
          }
        }
        else
        {
          v15 = GetLastError();
          v12 = v15;
          if ( v15 > 0 )
            v12 = (unsigned __int16)v15 | 0x80070000;
          CoUninitialize();
          if ( v12 < 0 )
          {
            v32 = GetMemLogObject();
            CMemoryLog::Write(v32, v12);
          }
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
              (unsigned int)v12);
          }
        }
      }
      else
      {
        v13 = GetLastError();
        v12 = v13;
        if ( v13 > 0 )
          v12 = (unsigned __int16)v13 | 0x80070000;
        CoUninitialize();
        if ( v12 < 0 )
        {
          v31 = GetMemLogObject();
          CMemoryLog::Write(v31, v12);
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
            (unsigned int)v12);
        }
      }
      ((void (__fastcall *)(struct _ACL *))LocalFree)(v5);
      ((void (__fastcall *)(PSID))FreeSid)(v2);
      ((void (__fastcall *)(PSID))FreeSid)(v1);
      return v12;
    }
    v28 = RtlNtStatusToDosError(v7);
    v12 = v28;
    if ( v28 > 0 )
      v12 = (unsigned __int16)v28 | 0x80070000;
    CoUninitialize();
    LocalFree(v5);
    if ( v12 < 0 )
    {
      v29 = GetMemLogObject();
      CMemoryLog::Write(v29, v12);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
        (unsigned int)v12);
    }
LABEL_114:
    ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(v44);
    ScopeGuardImpl1<void * (*)(void *),void *>::~ScopeGuardImpl1<void * (*)(void *),void *>(v47);
    return v12;
  }
  CoUninitialize();
  v20 = GetLastError();
  v21 = v20 < 0;
  if ( v20 > 0 )
    v21 = 1;
  if ( v21 )
  {
    v23 = GetMemLogObject();
    v24 = GetLastError();
    if ( v24 > 0 )
      v24 = (unsigned __int16)v24 | 0x80070000;
    CMemoryLog::Write(v23, v24);
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = GetLastError();
    if ( v22 > 0 )
      v22 = (unsigned __int16)v22 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_06f3c53ba90d3c5290ee926c0e3353ee_Traceguids,
      (unsigned int)v22);
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140022b5c  push    rbp
0x140022b5e  push    rbx
0x140022b5f  push    rsi
0x140022b60  push    rdi
0x140022b61  push    r12
0x140022b63  push    r13
0x140022b65  push    r14
0x140022b67  push    r15
0x140022b69  lea     rbp, [rsp-8]
0x140022b6e  sub     rsp, 108h
0x140022b75  mov     rax, cs:__security_cookie
0x140022b7c  xor     rax, rsp
0x140022b7f  mov     [rbp+40h+var_50], rax
0x140022b83  xor     edx, edx; dwCoInit
0x140022b85  xor     ecx, ecx; pvReserved
0x140022b87  call    cs:__imp_CoInitializeEx
0x140022b8d  mov     ebx, eax
0x140022b8f  mov     edi, 1
0x140022b94  xor     r13d, r13d
0x140022b97  test    eax, eax
0x140022b99  js      loc_140022DBA
0x140022b9f  xorps   xmm0, xmm0
0x140022ba2  xor     eax, eax
0x140022ba4  movups  [rsp+140h+pSecurityDescriptor], xmm0
0x140022ba9  movups  [rbp+40h+var_B8], xmm0
0x140022bad  mov     [rbp+40h+var_A8], rax
0x140022bb1  mov     [rsp+140h+pOwner], r13
0x140022bb6  mov     [rsp+140h+Sid], r13
0x140022bbb  mov     dword ptr [rbp+40h+pIdentifierAuthority.Value], r13d
0x140022bbf  mov     word ptr [rbp+40h+pIdentifierAuthority.Value+4], 500h
0x140022bc5  mov     edx, edi; dwRevision
0x140022bc7  lea     rcx, [rsp+140h+pSecurityDescriptor]; pSecurityDescriptor
0x140022bcc  call    cs:__imp_InitializeSecurityDescriptor
0x140022bd2  test    eax, eax
0x140022bd4  jz      loc_14002309B
0x140022bda  lea     rax, [rsp+140h+Sid]
0x140022bdf  mov     [rsp+140h+pSid], rax; pSid
0x140022be4  mov     [rsp+140h+nSubAuthority7], r13d; nSubAuthority7
0x140022be9  mov     [rsp+140h+nSubAuthority6], r13d; nSubAuthority6
0x140022bee  mov     [rsp+140h+nSubAuthority5], r13d; nSubAuthority5
0x140022bf3  mov     [rsp+140h+nSubAuthority4], r13d; nSubAuthority4
0x140022bf8  mov     [rsp+140h+nSubAuthority3], r13d; nSubAuthority3
0x140022bfd  mov     [rsp+140h+nSubAuthority2], r13d; nSubAuthority2
0x140022c02  xor     r9d, r9d; nSubAuthority1
0x140022c05  lea     esi, [rdi+0Ah]
0x140022c08  mov     r8d, esi; nSubAuthority0
0x140022c0b  mov     dl, dil; nSubAuthorityCount
0x140022c0e  lea     rcx, [rbp+40h+pIdentifierAuthority]; pIdentifierAuthority
0x140022c12  call    cs:__imp_AllocateAndInitializeSid
0x140022c18  test    eax, eax
0x140022c1a  jz      loc_140023113
0x140022c20  mov     r15, [rsp+140h+Sid]
0x140022c25  mov     r14, cs:__imp_FreeSid
0x140022c2c  mov     [rbp+40h+var_70], r13b
0x140022c30  mov     [rbp+40h+var_68], r14
0x140022c34  mov     [rbp+40h+var_60], r15
0x140022c38  lea     rax, [rsp+140h+pOwner]
0x140022c3d  mov     [rsp+140h+pSid], rax; pSid
0x140022c42  mov     [rsp+140h+nSubAuthority7], r13d; nSubAuthority7
0x140022c47  mov     [rsp+140h+nSubAuthority6], r13d; nSubAuthority6
0x140022c4c  mov     [rsp+140h+nSubAuthority5], r13d; nSubAuthority5
0x140022c51  mov     [rsp+140h+nSubAuthority4], r13d; nSubAuthority4
0x140022c56  mov     [rsp+140h+nSubAuthority3], r13d; nSubAuthority3
0x140022c5b  mov     [rsp+140h+nSubAuthority2], r13d; nSubAuthority2
0x140022c60  mov     r9d, 220h; nSubAuthority1
0x140022c66  lea     r8d, [rdi+1Fh]; nSubAuthority0
0x140022c6a  mov     dl, dil; nSubAuthorityCount
0x140022c6d  lea     rcx, [rbp+40h+pIdentifierAuthority]; pIdentifierAuthority
0x140022c71  call    cs:__imp_AllocateAndInitializeSid
0x140022c77  test    eax, eax
0x140022c79  jz      loc_140022E58
0x140022c7f  mov     r12, [rsp+140h+pOwner]
0x140022c84  mov     [rbp+40h+var_88], r13b
0x140022c88  mov     [rbp+40h+var_80], r14
0x140022c8c  mov     [rbp+40h+var_78], r12
0x140022c90  mov     rcx, [rsp+140h+Sid]; Sid
0x140022c95  call    cs:__imp_RtlLengthSid
0x140022c9b  lea     ebx, [rax+14h]
0x140022c9e  mov     edx, ebx; uBytes
0x140022ca0  xor     ecx, ecx; uFlags
0x140022ca2  call    cs:__imp_LocalAlloc
0x140022ca8  mov     rsi, rax
0x140022cab  test    rax, rax
0x140022cae  jz      loc_140022F13
0x140022cb4  lea     r8d, [rdi+1]; AclRevision
0x140022cb8  mov     edx, ebx; AclSize
0x140022cba  mov     rcx, rax; Acl
0x140022cbd  call    cs:__imp_RtlCreateAcl
0x140022cc3  test    eax, eax
0x140022cc5  js      loc_140022FD6
0x140022ccb  mov     r9, [rsp+140h+Sid]; Sid
0x140022cd0  mov     r8d, edi; AccessMask
0x140022cd3  lea     edx, [rdi+1]; Revision
0x140022cd6  mov     rcx, rsi; Acl
0x140022cd9  call    cs:__imp_RtlAddAccessAllowedAce
0x140022cdf  test    eax, eax
0x140022ce1  js      loc_140023216
0x140022ce7  mov     r13, cs:__imp_LocalFree
0x140022cee  mov     [rbp+40h+var_A0], 0
0x140022cf2  mov     [rbp+40h+var_98], r13
0x140022cf6  mov     [rbp+40h+var_90], rsi
0x140022cfa  xor     r8d, r8d; bOwnerDefaulted
0x140022cfd  mov     rdx, [rsp+140h+pOwner]; pOwner
0x140022d02  lea     rcx, [rsp+140h+pSecurityDescriptor]; pSecurityDescriptor
0x140022d07  call    cs:__imp_SetSecurityDescriptorOwner
0x140022d0d  test    eax, eax
0x140022d0f  jz      loc_140022EB3
0x140022d15  xor     r8d, r8d; bGroupDefaulted
0x140022d18  mov     rdx, [rsp+140h+pOwner]; pGroup
0x140022d1d  lea     rcx, [rsp+140h+pSecurityDescriptor]; pSecurityDescriptor
0x140022d22  call    cs:__imp_SetSecurityDescriptorGroup
0x140022d28  test    eax, eax
0x140022d2a  jz      loc_140022F73
0x140022d30  xor     r9d, r9d; bDaclDefaulted
0x140022d33  mov     r8, rsi; pDacl
0x140022d36  mov     edx, edi; bDaclPresent
0x140022d38  lea     rcx, [rsp+140h+pSecurityDescriptor]; pSecurityDescriptor
0x140022d3d  call    cs:__imp_SetSecurityDescriptorDacl
0x140022d43  test    eax, eax
0x140022d45  jz      loc_140023038
0x140022d4b  mov     qword ptr [rsp+140h+nSubAuthority6], 0; pReserved3
0x140022d54  mov     [rsp+140h+nSubAuthority5], 40h ; '@'; dwCapabilities
0x140022d5c  mov     qword ptr [rsp+140h+nSubAuthority4], 0; pAuthList
0x140022d65  mov     [rsp+140h+nSubAuthority3], 3; dwImpLevel
0x140022d6d  mov     [rsp+140h+nSubAuthority2], 2; dwAuthnLevel
0x140022d75  xor     r9d, r9d; pReserved1
0x140022d78  xor     r8d, r8d; asAuthSvc
0x140022d7b  or      edx, 0FFFFFFFFh; cAuthSvc
0x140022d7e  lea     rcx, [rsp+140h+pSecurityDescriptor]; pSecDesc
0x140022d83  call    cs:__imp_CoInitializeSecurity
0x140022d89  mov     ebx, eax
0x140022d8b  test    eax, eax
0x140022d8d  js      loc_140023402
0x140022d93  mov     rcx, rsi
0x140022d96  mov     rax, r13
0x140022d99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022d9e  nop
0x140022d9f  mov     rcx, r12
0x140022da2  mov     rax, r14
0x140022da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022daa  nop
0x140022dab  mov     rcx, r15
0x140022dae  mov     rax, r14
0x140022db1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022db6  nop
0x140022db7  xor     r13d, r13d
0x140022dba  mov     [rsp+140h+ppv], r13
0x140022dbf  lea     rax, [rsp+140h+ppv]
0x140022dc4  mov     qword ptr [rsp+140h+nSubAuthority2], rax; ppv
0x140022dc9  lea     r9, IID_IGlobalOptions; riid
0x140022dd0  mov     r8d, edi; dwClsContext
0x140022dd3  xor     edx, edx; pUnkOuter
0x140022dd5  lea     rcx, CLSID_GlobalOptions; rclsid
0x140022ddc  call    cs:__imp_CoCreateInstance
0x140022de2  test    eax, eax
0x140022de4  js      loc_140022F63
0x140022dea  mov     rcx, [rsp+140h+ppv]
0x140022def  mov     rax, [rcx]
0x140022df2  mov     r8, rdi
0x140022df5  mov     edx, edi
0x140022df7  mov     rax, [rax+18h]
0x140022dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022e00  mov     rcx, [rsp+140h+ppv]
0x140022e05  mov     rax, [rcx]
0x140022e08  mov     rax, [rax+10h]
0x140022e0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022e11  test    ebx, ebx
0x140022e13  js      loc_140023474
0x140022e19  lea     rax, WPP_GLOBAL_Control
0x140022e20  mov     rcx, cs:WPP_GLOBAL_Control
0x140022e27  cmp     rcx, rax
0x140022e2a  jz      short loc_140022E36
0x140022e2c  test    byte ptr [rcx+1Ch], 4
0x140022e30  jnz     loc_14002348A
0x140022e36  mov     eax, ebx
0x140022e38  mov     rcx, [rbp+40h+var_50]
0x140022e3c  xor     rcx, rsp; StackCookie
0x140022e3f  call    __security_check_cookie
0x140022e44  add     rsp, 108h
0x140022e4b  pop     r15
0x140022e4d  pop     r14
0x140022e4f  pop     r13
0x140022e51  pop     r12
0x140022e53  pop     rdi
0x140022e54  pop     rsi
0x140022e55  pop     rbx
0x140022e56  pop     rbp
0x140022e57  retn
0x140022e58  call    cs:__imp_CoUninitialize
0x140022e5e  nop
0x140022e5f  call    cs:__imp_GetLastError
0x140022e65  mov     ebx, 80070000h
0x140022e6a  test    eax, eax
0x140022e6c  jle     short loc_140022E75
0x140022e6e  movzx   eax, ax
0x140022e71  or      eax, ebx
0x140022e73  test    eax, eax
0x140022e75  js      loc_1400231BB
0x140022e7b  lea     rax, WPP_GLOBAL_Control
0x140022e82  mov     rcx, cs:WPP_GLOBAL_Control
0x140022e89  cmp     rcx, rax
0x140022e8c  jnz     loc_140023299
0x140022e92  call    cs:__imp_GetLastError
0x140022e98  mov     edi, eax
0x140022e9a  test    eax, eax
0x140022e9c  jle     short loc_140022EA3
0x140022e9e  movzx   edi, ax
0x140022ea1  or      edi, ebx
0x140022ea3  mov     rcx, r15
0x140022ea6  mov     rax, r14
0x140022ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022eae  nop
0x140022eaf  mov     eax, edi
0x140022eb1  jmp     short loc_140022E38
0x140022eb3  call    cs:__imp_GetLastError
0x140022eb9  mov     edi, eax
0x140022ebb  test    eax, eax
0x140022ebd  jle     short loc_140022EC8
0x140022ebf  movzx   edi, ax
0x140022ec2  or      edi, 80070000h
0x140022ec8  call    cs:__imp_CoUninitialize
0x140022ece  test    edi, edi
0x140022ed0  js      loc_14002332D
0x140022ed6  lea     rax, WPP_GLOBAL_Control
0x140022edd  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ee4  cmp     rcx, rax
0x140022ee7  jnz     loc_140023343
0x140022eed  mov     rcx, rsi
0x140022ef0  mov     rax, r13
0x140022ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022ef8  nop
0x140022ef9  mov     rcx, r12
0x140022efc  mov     rax, r14
0x140022eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022f04  nop
0x140022f05  mov     rcx, r15
0x140022f08  mov     rax, r14
0x140022f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022f10  nop
0x140022f11  jmp     short loc_140022EAF
0x140022f13  call    cs:__imp_CoUninitialize
0x140022f19  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140022f1f  mov     ebx, 80070008h
0x140022f24  mov     edx, ebx
0x140022f26  mov     rcx, rax
0x140022f29  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140022f2f  lea     rax, WPP_GLOBAL_Control
0x140022f36  mov     rcx, cs:WPP_GLOBAL_Control
0x140022f3d  cmp     rcx, rax
0x140022f40  jnz     loc_1400232B2
0x140022f46  mov     rcx, r12
0x140022f49  mov     rax, r14
0x140022f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022f51  nop
0x140022f52  mov     rcx, r15
0x140022f55  mov     rax, r14
0x140022f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022f5d  nop
0x140022f5e  jmp     loc_140022E36
0x140022f63  call    cs:__imp_CoUninitialize
0x140022f69  mov     eax, 0Eh
0x140022f6e  jmp     loc_140022E38
0x140022f73  call    cs:__imp_GetLastError
0x140022f79  mov     edi, eax
0x140022f7b  test    eax, eax
0x140022f7d  jle     short loc_140022F88
0x140022f7f  movzx   edi, ax
0x140022f82  or      edi, 80070000h
0x140022f88  call    cs:__imp_CoUninitialize
0x140022f8e  test    edi, edi
0x140022f90  js      loc_140023374
0x140022f96  lea     rax, WPP_GLOBAL_Control
0x140022f9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140022fa4  cmp     rcx, rax
0x140022fa7  jnz     loc_14002338A
0x140022fad  mov     rcx, rsi
0x140022fb0  mov     rax, r13
0x140022fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022fb8  nop
0x140022fb9  mov     rcx, r12
0x140022fbc  mov     rax, r14
0x140022fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022fc4  nop
0x140022fc5  mov     rcx, r15
0x140022fc8  mov     rax, r14
0x140022fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140022fd0  nop
0x140022fd1  jmp     loc_140022EAF
0x140022fd6  mov     ecx, eax; Status
0x140022fd8  call    cs:__imp_RtlNtStatusToDosError
0x140022fde  mov     edi, eax
0x140022fe0  test    eax, eax
0x140022fe2  jle     short loc_140022FED
0x140022fe4  movzx   edi, ax
0x140022fe7  or      edi, 80070000h
0x140022fed  call    cs:__imp_CoUninitialize
0x140022ff3  mov     rcx, rsi; hMem
0x140022ff6  call    cs:__imp_LocalFree
0x140022ffc  test    edi, edi
0x140022ffe  js      loc_1400232E6
  ... truncated ...
```
