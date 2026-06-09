# BfeEventControllerCreate

- ea: `0x18001d25c`
- end: `0x18001d607`
- name: `BfeEventControllerCreate`
- size: `939`
- prototype: `__int64 __fastcall(unsigned int, int, ULONG64 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e9f0`

## callees

- `0x1800039e4`
- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x18001d25c`
- `0x18001d91c`
- `0x18001da08`
- `0x180022730`
- `0x180044e80`
- `0x180058b30`
- `0x180077698`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d405`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d46d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d405`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d46d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d396`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001d396`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001d593`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001d593`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001d5bb`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x18001d5bb`

## string_xrefs

- `0x18001d2c3`: `%ProgramData%\Microsoft\Windows\wfp\wfpdiag.etl`
- `0x18001d323`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x18001d3a6`: `RegOpenKeyExW`
- `0x18001d3be`: `BfeRegOpenKey`
- `0x18001d524`: `BfeEventControllerCreate`

## pseudocode

```c
__int64 __fastcall BfeEventControllerCreate(unsigned int a1, int a2, ULONG64 **a3)
{
  HKEY v3; // rdi
  ULONG64 **v4; // r14
  __int64 v5; // rbx
  ULONG64 *v6; // rsi
  ULONG64 v7; // rax
  ULONG64 v8; // rax
  int v9; // r15d
  int v10; // r13d
  ULONG64 v11; // rax
  _DWORD *v12; // r12
  unsigned int v13; // eax
  __int64 v14; // rcx
  __int64 v15; // rax
  DWORD v16; // eax
  unsigned int v17; // eax
  __int64 v18; // rcx
  LPBYTE v19; // r14
  unsigned int v20; // eax
  __int64 v21; // rcx
  ULONG started; // eax
  __int64 v24; // rcx
  const char *v25; // rdx
  LPBYTE lpData; // [rsp+38h] [rbp-31h] BYREF
  int v28; // [rsp+40h] [rbp-29h]
  unsigned int v29; // [rsp+44h] [rbp-25h]
  ULONG64 *v30; // [rsp+48h] [rbp-21h] BYREF
  void *v31; // [rsp+50h] [rbp-19h] BYREF
  LPBYTE v32; // [rsp+58h] [rbp-11h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-9h] BYREF
  DWORD lpcbData; // [rsp+68h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+7h] BYREF
  DWORD Type; // [rsp+78h] [rbp+Fh] BYREF

  v3 = 0;
  v4 = a3;
  v28 = a2;
  v29 = a1;
  *a3 = 0;
  v30 = 0;
  v31 = 0;
  v5 = WfpMemAlloc(0x10u, 8u);
  if ( v5 )
    goto LABEL_29;
  v5 = BfeExpandEnvironmentStrings(L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpdiag.etl", (LPWSTR *)&v31);
  if ( v5 )
    goto LABEL_29;
  v6 = v30;
  v5 = BfeEventTracePropertiesAlloc(L"WFP-IPsec Diagnostics", v31, v30);
  if ( v5 )
    goto LABEL_29;
  v7 = *v30;
  cbData = 4;
  Type = 0;
  *(_OWORD *)(v7 + 24) = FWP_EVENT_LOGGER_GUID;
  v8 = *v6;
  v9 = 0;
  lpcbData = 0;
  lpData = 0;
  v10 = 0;
  v32 = 0;
  *(_DWORD *)(v8 + 40) = 2;
  v11 = *v6;
  hKey = 0;
  *(_DWORD *)(v11 + 44) = 0x20000;
  *(_DWORD *)(*v6 + 60) = 1024;
  *(_DWORD *)(*v6 + 64) = 8194;
  *(_DWORD *)(*v6 + 52) = 1;
  *(_DWORD *)(*v6 + 56) = 8;
  v12 = 0;
  *(_DWORD *)(*v6 + 48) = 32;
  *(_DWORD *)(*v6 + 64) |= 0x10000000u;
  v13 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"System\\CurrentControlSet\\Services\\BFE\\Parameters\\Policy\\Options",
          0,
          1u,
          &hKey);
  if ( (v13 & 0xFFFFFFFD) != 0 )
  {
    v15 = WfpReportSysErrorAsWinError(v14, "RegOpenKeyExW", v13);
    v5 = v15;
    if ( v15 )
      WfpReportError(v15, "BfeRegOpenKey");
    goto LABEL_23;
  }
  if ( v13 == 2 )
    goto LABEL_22;
  v16 = cbData;
  v3 = hKey;
  if ( !cbData )
  {
    v17 = RegQueryValueExW(hKey, L"WfpDiagMaxFileSizeKB", 0, &Type, 0, &cbData);
    if ( v17 != 2 )
    {
      if ( v17 )
      {
        v5 = WfpReportSysErrorAsWinError(v18, "RegQueryValueExW", v17);
        goto LABEL_23;
      }
      v16 = cbData;
      goto LABEL_13;
    }
LABEL_22:
    v5 = 0;
    goto LABEL_23;
  }
LABEL_13:
  lpcbData = v16;
  v5 = WfpMemAlloc(v16, 0);
  if ( !v5 )
  {
    v19 = lpData;
    v20 = RegQueryValueExW(v3, L"WfpDiagMaxFileSizeKB", 0, &Type, lpData, &lpcbData);
    if ( v20 != 2 && v20 != 234 )
    {
      if ( v20 )
      {
        v5 = WfpReportSysErrorAsWinError(v21, "RegQueryValueExW", v20);
      }
      else if ( Type == 4 && lpcbData == cbData )
      {
        lpData = 0;
        v12 = v19;
        v10 = 1;
        v32 = v19;
      }
    }
    v4 = a3;
  }
LABEL_23:
  WfpMemFree(&lpData);
  BfeRegCloseKey(v3);
  if ( v5 )
  {
    WfpReportError(v5, "BfeRegQueryValue");
  }
  else if ( v10 )
  {
    v9 = *v12;
  }
  WfpMemFree(&v32);
  if ( v5 )
  {
    WfpReportError(v5, "BfeRegQueryDWord");
LABEL_29:
    BfeEventControllerDestroy(&v30);
    goto LABEL_30;
  }
  if ( v10 && (unsigned int)(v9 - 1) <= 0xFFFFE )
    *(_DWORD *)(*v6 + 60) = v9;
  if ( v28 )
    *(_DWORD *)(*v6 + 64) |= 0x100u;
  started = ControlTraceW(0, L"WFP-IPsec Diagnostics", (PEVENT_TRACE_PROPERTIES)*v6, 1u);
  if ( started == 4201 || !started )
  {
    started = StartTraceW(v6 + 1, L"WFP-IPsec Diagnostics", (PEVENT_TRACE_PROPERTIES)*v6);
    if ( !started )
    {
      v5 = BfeEventControllerEnableAllProviders(v6, v29, 0);
      if ( v5 )
        goto LABEL_29;
      *v4 = v6;
      goto LABEL_30;
    }
    v25 = "StartTraceW";
  }
  else
  {
    v25 = "ControlTraceW";
  }
  v5 = WfpReportSysErrorAsWinError(v24, v25, started);
  if ( v5 )
    goto LABEL_29;
LABEL_30:
  WfpMemFree(&v31);
  if ( v5 )
    WfpReportError(v5, "BfeEventControllerCreate");
  return v5;
}

```

## disassembly

```asm
0x18001d25c  mov     [rsp-8+arg_8], rbx
0x18001d261  push    rbp
0x18001d262  push    rsi
0x18001d263  push    rdi
0x18001d264  push    r12
0x18001d266  push    r13
0x18001d268  push    r14
0x18001d26a  push    r15
0x18001d26c  lea     rbp, [rsp-27h]
0x18001d271  sub     rsp, 90h
0x18001d278  mov     rax, cs:__security_cookie
0x18001d27f  xor     rax, rsp
0x18001d282  mov     [rbp+57h+var_40], rax
0x18001d286  xor     edi, edi
0x18001d288  mov     [rbp+57h+var_90], r8
0x18001d28c  mov     r14, r8
0x18001d28f  mov     [rbp+57h+var_80], edx
0x18001d292  mov     [rbp+57h+var_7C], ecx
0x18001d295  mov     [r8], rdi
0x18001d298  lea     r8, [rbp+57h+var_78]
0x18001d29c  lea     r12d, [rdi+8]
0x18001d2a0  mov     [rbp+57h+var_78], rdi
0x18001d2a4  mov     edx, r12d; dwFlags
0x18001d2a7  mov     [rbp+57h+var_70], rdi
0x18001d2ab  lea     ecx, [rdi+10h]; dwBytes
0x18001d2ae  call    WfpMemAlloc
0x18001d2b3  mov     rbx, rax
0x18001d2b6  test    rax, rax
0x18001d2b9  jnz     loc_18001D50D
0x18001d2bf  lea     rdx, [rbp+57h+var_70]
0x18001d2c3  lea     rcx, FWP_EVENT_LOGFILE_NAME; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x18001d2ca  call    BfeExpandEnvironmentStrings
0x18001d2cf  mov     rbx, rax
0x18001d2d2  test    rax, rax
0x18001d2d5  jnz     loc_18001D50D
0x18001d2db  mov     rsi, [rbp+57h+var_78]
0x18001d2df  lea     rcx, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x18001d2e6  mov     rdx, [rbp+57h+var_70]; void *
0x18001d2ea  mov     r8, rsi
0x18001d2ed  call    BfeEventTracePropertiesAlloc
0x18001d2f2  mov     rbx, rax
0x18001d2f5  test    rax, rax
0x18001d2f8  jnz     loc_18001D50D
0x18001d2fe  mov     rax, [rsi]
0x18001d301  lea     ecx, [rdi+1]
0x18001d304  movups  xmm0, cs:FWP_EVENT_LOGGER_GUID
0x18001d30b  mov     r9d, ecx; samDesired
0x18001d30e  mov     [rbp+57h+cbData], 4
0x18001d315  xor     r8d, r8d; ulOptions
0x18001d318  mov     [rbp+57h+Type], edi
0x18001d31b  movdqu  xmmword ptr [rax+18h], xmm0
0x18001d320  mov     rax, [rsi]
0x18001d323  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\BF"...
0x18001d32a  mov     r15d, edi
0x18001d32d  mov     [rbp+57h+var_58], edi
0x18001d330  mov     [rbp+57h+lpData], rdi
0x18001d334  mov     r13d, edi
0x18001d337  mov     [rbp+57h+var_68], rdi
0x18001d33b  mov     dword ptr [rax+28h], 2
0x18001d342  mov     rax, [rsi]
0x18001d345  mov     [rbp+57h+hKey], rdi
0x18001d349  mov     dword ptr [rax+2Ch], 20000h
0x18001d350  mov     rax, [rsi]
0x18001d353  mov     dword ptr [rax+3Ch], 400h
0x18001d35a  mov     rax, [rsi]
0x18001d35d  mov     dword ptr [rax+40h], 2002h
0x18001d364  mov     rax, [rsi]
0x18001d367  mov     [rax+34h], ecx
0x18001d36a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001d371  mov     rax, [rsi]
0x18001d374  mov     [rax+38h], r12d
0x18001d378  mov     r12d, edi
0x18001d37b  mov     rax, [rsi]
0x18001d37e  mov     dword ptr [rax+30h], 20h ; ' '
0x18001d385  mov     rax, [rsi]
0x18001d388  bts     dword ptr [rax+40h], 1Ch
0x18001d38d  lea     rax, [rbp+57h+hKey]
0x18001d391  mov     [rsp+0C0h+phkResult], rax; phkResult
0x18001d396  call    cs:__imp_RegOpenKeyExW
0x18001d39c  test    eax, 0FFFFFFFDh
0x18001d3a1  jz      short loc_18001D3D2
0x18001d3a3  mov     r8d, eax
0x18001d3a6  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001d3ad  call    WfpReportSysErrorAsWinError
0x18001d3b2  mov     rbx, rax
0x18001d3b5  test    rax, rax
0x18001d3b8  jz      loc_18001D4BE
0x18001d3be  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x18001d3c5  mov     rcx, rax
0x18001d3c8  call    WfpReportError
0x18001d3cd  jmp     loc_18001D4BE
0x18001d3d2  cmp     eax, 2
0x18001d3d5  jz      loc_18001D4BC
0x18001d3db  mov     eax, [rbp+57h+cbData]
0x18001d3de  mov     rdi, [rbp+57h+hKey]
0x18001d3e2  test    eax, eax
0x18001d3e4  jnz     short loc_18001D432
0x18001d3e6  lea     rax, [rbp+57h+cbData]
0x18001d3ea  xor     r8d, r8d; lpReserved
0x18001d3ed  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18001d3f2  lea     r9, [rbp+57h+Type]; lpType
0x18001d3f6  lea     rdx, ValueName; "WfpDiagMaxFileSizeKB"
0x18001d3fd  mov     [rsp+0C0h+phkResult], r12; lpData
0x18001d402  mov     rcx, rdi; hKey
0x18001d405  call    cs:__imp_RegQueryValueExW
0x18001d40b  cmp     eax, 2
0x18001d40e  jz      loc_18001D4BC
0x18001d414  test    eax, eax
0x18001d416  jz      short loc_18001D42F
0x18001d418  mov     r8d, eax
0x18001d41b  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18001d422  call    WfpReportSysErrorAsWinError
0x18001d427  mov     rbx, rax
0x18001d42a  jmp     loc_18001D4BE
0x18001d42f  mov     eax, [rbp+57h+cbData]
0x18001d432  mov     ecx, eax; dwBytes
0x18001d434  lea     r8, [rbp+57h+lpData]
0x18001d438  xor     edx, edx; dwFlags
0x18001d43a  mov     [rbp+57h+var_58], eax
0x18001d43d  call    WfpMemAlloc
0x18001d442  mov     rbx, rax
0x18001d445  test    rax, rax
0x18001d448  jnz     short loc_18001D4BE
0x18001d44a  mov     r14, [rbp+57h+lpData]
0x18001d44e  lea     rax, [rbp+57h+var_58]
0x18001d452  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18001d457  lea     r9, [rbp+57h+Type]; lpType
0x18001d45b  xor     r8d, r8d; lpReserved
0x18001d45e  mov     [rsp+0C0h+phkResult], r14; lpData
0x18001d463  lea     rdx, ValueName; "WfpDiagMaxFileSizeKB"
0x18001d46a  mov     rcx, rdi; hKey
0x18001d46d  call    cs:__imp_RegQueryValueExW
0x18001d473  cmp     eax, 2
0x18001d476  jz      short loc_18001D495
0x18001d478  cmp     eax, 0EAh
0x18001d47d  jz      short loc_18001D495
0x18001d47f  test    eax, eax
0x18001d481  jz      short loc_18001D49B
0x18001d483  mov     r8d, eax
0x18001d486  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x18001d48d  call    WfpReportSysErrorAsWinError
0x18001d492  mov     rbx, rax
0x18001d495  mov     r14, [rbp+57h+var_90]
0x18001d499  jmp     short loc_18001D4BE
0x18001d49b  cmp     [rbp+57h+Type], 4
0x18001d49f  jnz     short loc_18001D495
0x18001d4a1  mov     eax, [rbp+57h+cbData]
0x18001d4a4  cmp     [rbp+57h+var_58], eax
0x18001d4a7  jnz     short loc_18001D495
0x18001d4a9  mov     [rbp+57h+lpData], r13
0x18001d4ad  mov     r12, r14
0x18001d4b0  mov     r13d, 1
0x18001d4b6  mov     [rbp+57h+var_68], r14
0x18001d4ba  jmp     short loc_18001D495
0x18001d4bc  xor     ebx, ebx
0x18001d4be  lea     rcx, [rbp+57h+lpData]
0x18001d4c2  call    WfpMemFree
0x18001d4c7  mov     rcx, rdi
0x18001d4ca  call    BfeRegCloseKey
0x18001d4cf  xor     edi, edi
0x18001d4d1  test    rbx, rbx
0x18001d4d4  jz      short loc_18001D4E7
0x18001d4d6  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x18001d4dd  mov     rcx, rbx
0x18001d4e0  call    WfpReportError
0x18001d4e5  jmp     short loc_18001D4F0
0x18001d4e7  test    r13d, r13d
0x18001d4ea  jz      short loc_18001D4F0
0x18001d4ec  mov     r15d, [r12]
0x18001d4f0  lea     rcx, [rbp+57h+var_68]
0x18001d4f4  call    WfpMemFree
0x18001d4f9  test    rbx, rbx
0x18001d4fc  jz      short loc_18001D55D
0x18001d4fe  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18001d505  mov     rcx, rbx
0x18001d508  call    WfpReportError
0x18001d50d  lea     rcx, [rbp+57h+var_78]
0x18001d511  call    BfeEventControllerDestroy
0x18001d516  lea     rcx, [rbp+57h+var_70]
0x18001d51a  call    WfpMemFree
0x18001d51f  test    rbx, rbx
0x18001d522  jz      short loc_18001D533
0x18001d524  lea     rdx, aBfeeventcontro; "BfeEventControllerCreate"
0x18001d52b  mov     rcx, rbx
0x18001d52e  call    WfpReportError
0x18001d533  mov     rax, rbx
0x18001d536  mov     rcx, [rbp+57h+var_40]
0x18001d53a  xor     rcx, rsp; StackCookie
0x18001d53d  call    __security_check_cookie
0x18001d542  mov     rbx, [rsp+0C0h+arg_8]
0x18001d54a  add     rsp, 90h
0x18001d551  pop     r15
0x18001d553  pop     r14
0x18001d555  pop     r13
0x18001d557  pop     r12
0x18001d559  pop     rdi
0x18001d55a  pop     rsi
0x18001d55b  pop     rbp
0x18001d55c  retn
0x18001d55d  test    r13d, r13d
0x18001d560  jz      short loc_18001D574
0x18001d562  lea     eax, [r15-1]
0x18001d566  cmp     eax, 0FFFFEh
0x18001d56b  ja      short loc_18001D574
0x18001d56d  mov     rax, [rsi]
0x18001d570  mov     [rax+3Ch], r15d
0x18001d574  cmp     [rbp+57h+var_80], edi
0x18001d577  jz      short loc_18001D581
0x18001d579  mov     rax, [rsi]
0x18001d57c  bts     dword ptr [rax+40h], 8
0x18001d581  mov     r8, [rsi]; Properties
0x18001d584  lea     rdx, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x18001d58b  mov     r9d, 1; ControlCode
0x18001d591  xor     ecx, ecx; TraceHandle
0x18001d593  call    cs:__imp_ControlTraceW
0x18001d599  cmp     eax, 1069h
0x18001d59e  jz      short loc_18001D5AD
0x18001d5a0  test    eax, eax
0x18001d5a2  jz      short loc_18001D5AD
0x18001d5a4  lea     rdx, aControltracew; "ControlTraceW"
0x18001d5ab  jmp     short loc_18001D5CC
0x18001d5ad  mov     r8, [rsi]; Properties
0x18001d5b0  lea     rcx, [rsi+8]; TraceHandle
0x18001d5b4  lea     rdx, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x18001d5bb  call    cs:__imp_StartTraceW
0x18001d5c1  test    eax, eax
0x18001d5c3  jz      short loc_18001D5E5
0x18001d5c5  lea     rdx, aStarttracew; "StartTraceW"
0x18001d5cc  mov     r8d, eax
0x18001d5cf  call    WfpReportSysErrorAsWinError
0x18001d5d4  mov     rbx, rax
0x18001d5d7  test    rax, rax
0x18001d5da  jnz     loc_18001D50D
0x18001d5e0  jmp     loc_18001D516
0x18001d5e5  mov     edx, [rbp+57h+var_7C]
0x18001d5e8  xor     r8d, r8d
0x18001d5eb  mov     rcx, rsi
0x18001d5ee  call    BfeEventControllerEnableAllProviders
0x18001d5f3  mov     rbx, rax
0x18001d5f6  test    rax, rax
0x18001d5f9  jnz     loc_18001D50D
0x18001d5ff  mov     [r14], rsi
0x18001d602  jmp     loc_18001D516
```
