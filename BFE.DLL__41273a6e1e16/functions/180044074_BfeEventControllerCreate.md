# BfeEventControllerCreate

- ea: `0x180044074`
- end: `0x18004443e`
- name: `BfeEventControllerCreate`
- size: `970`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021300`

## callees

- `0x180004070`
- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x180044074`
- `0x180044444`
- `0x180044588`
- `0x180046e9c`
- `0x18005aa60`
- `0x18007a168`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044223`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044291`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044223`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180044291`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800441ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800441ae`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800443be`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x1800443be`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800443ec`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x1800443ec`

## string_xrefs

- `0x1800440db`: `%ProgramData%\Microsoft\Windows\wfp\wfpdiag.etl`
- `0x18004413b`: `System\CurrentControlSet\Services\BFE\Parameters\Policy\Options`
- `0x1800441c4`: `RegOpenKeyExW`
- `0x1800441dc`: `BfeRegOpenKey`
- `0x18004434e`: `BfeEventControllerCreate`

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
  v5 = BfeExpandEnvironmentStrings(L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpdiag.etl");
  if ( v5 )
    goto LABEL_29;
  v6 = v30;
  v5 = BfeEventTracePropertiesAlloc((void *)L"WFP-IPsec Diagnostics", v31);
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
0x180044074  mov     [rsp-8+arg_8], rbx
0x180044079  push    rbp
0x18004407a  push    rsi
0x18004407b  push    rdi
0x18004407c  push    r12
0x18004407e  push    r13
0x180044080  push    r14
0x180044082  push    r15
0x180044084  lea     rbp, [rsp-27h]
0x180044089  sub     rsp, 90h
0x180044090  mov     rax, cs:__security_cookie
0x180044097  xor     rax, rsp
0x18004409a  mov     [rbp+57h+var_40], rax
0x18004409e  xor     edi, edi
0x1800440a0  mov     [rbp+57h+var_90], r8
0x1800440a4  mov     r14, r8
0x1800440a7  mov     [rbp+57h+var_80], edx
0x1800440aa  mov     [rbp+57h+var_7C], ecx
0x1800440ad  mov     [r8], rdi
0x1800440b0  lea     r8, [rbp+57h+var_78]
0x1800440b4  lea     r12d, [rdi+8]
0x1800440b8  mov     [rbp+57h+var_78], rdi
0x1800440bc  mov     edx, r12d; dwFlags
0x1800440bf  mov     [rbp+57h+var_70], rdi
0x1800440c3  lea     ecx, [rdi+10h]; dwBytes
0x1800440c6  call    WfpMemAlloc
0x1800440cb  mov     rbx, rax
0x1800440ce  test    rax, rax
0x1800440d1  jnz     loc_180044337
0x1800440d7  lea     rdx, [rbp+57h+var_70]
0x1800440db  lea     rcx, FWP_EVENT_LOGFILE_NAME; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x1800440e2  call    BfeExpandEnvironmentStrings
0x1800440e7  mov     rbx, rax
0x1800440ea  test    rax, rax
0x1800440ed  jnz     loc_180044337
0x1800440f3  mov     rsi, [rbp+57h+var_78]
0x1800440f7  lea     rcx, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x1800440fe  mov     rdx, [rbp+57h+var_70]; void *
0x180044102  mov     r8, rsi
0x180044105  call    BfeEventTracePropertiesAlloc
0x18004410a  mov     rbx, rax
0x18004410d  test    rax, rax
0x180044110  jnz     loc_180044337
0x180044116  mov     rax, [rsi]
0x180044119  lea     ecx, [rdi+1]
0x18004411c  movups  xmm0, cs:FWP_EVENT_LOGGER_GUID
0x180044123  mov     r9d, ecx; samDesired
0x180044126  mov     [rbp+57h+cbData], 4
0x18004412d  xor     r8d, r8d; ulOptions
0x180044130  mov     [rbp+57h+Type], edi
0x180044133  movdqu  xmmword ptr [rax+18h], xmm0
0x180044138  mov     rax, [rsi]
0x18004413b  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\BF"...
0x180044142  mov     r15d, edi
0x180044145  mov     [rbp+57h+var_58], edi
0x180044148  mov     [rbp+57h+lpData], rdi
0x18004414c  mov     r13d, edi
0x18004414f  mov     [rbp+57h+var_68], rdi
0x180044153  mov     dword ptr [rax+28h], 2
0x18004415a  mov     rax, [rsi]
0x18004415d  mov     [rbp+57h+hKey], rdi
0x180044161  mov     dword ptr [rax+2Ch], 20000h
0x180044168  mov     rax, [rsi]
0x18004416b  mov     dword ptr [rax+3Ch], 400h
0x180044172  mov     rax, [rsi]
0x180044175  mov     dword ptr [rax+40h], 2002h
0x18004417c  mov     rax, [rsi]
0x18004417f  mov     [rax+34h], ecx
0x180044182  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180044189  mov     rax, [rsi]
0x18004418c  mov     [rax+38h], r12d
0x180044190  mov     r12d, edi
0x180044193  mov     rax, [rsi]
0x180044196  mov     dword ptr [rax+30h], 20h ; ' '
0x18004419d  mov     rax, [rsi]
0x1800441a0  bts     dword ptr [rax+40h], 1Ch
0x1800441a5  lea     rax, [rbp+57h+hKey]
0x1800441a9  mov     [rsp+0C0h+phkResult], rax; phkResult
0x1800441ae  call    cs:__imp_RegOpenKeyExW
0x1800441b5  nop     dword ptr [rax+rax+00h]
0x1800441ba  test    eax, 0FFFFFFFDh
0x1800441bf  jz      short loc_1800441F0
0x1800441c1  mov     r8d, eax
0x1800441c4  lea     rdx, aRegopenkeyexw; "RegOpenKeyExW"
0x1800441cb  call    WfpReportSysErrorAsWinError
0x1800441d0  mov     rbx, rax
0x1800441d3  test    rax, rax
0x1800441d6  jz      loc_1800442E8
0x1800441dc  lea     rdx, aBferegopenkey; "BfeRegOpenKey"
0x1800441e3  mov     rcx, rax
0x1800441e6  call    WfpReportError
0x1800441eb  jmp     loc_1800442E8
0x1800441f0  cmp     eax, 2
0x1800441f3  jz      loc_1800442E6
0x1800441f9  mov     eax, [rbp+57h+cbData]
0x1800441fc  mov     rdi, [rbp+57h+hKey]
0x180044200  test    eax, eax
0x180044202  jnz     short loc_180044256
0x180044204  lea     rax, [rbp+57h+cbData]
0x180044208  xor     r8d, r8d; lpReserved
0x18004420b  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x180044210  lea     r9, [rbp+57h+Type]; lpType
0x180044214  lea     rdx, aWfpdiagmaxfile; "WfpDiagMaxFileSizeKB"
0x18004421b  mov     [rsp+0C0h+phkResult], r12; lpData
0x180044220  mov     rcx, rdi; hKey
0x180044223  call    cs:__imp_RegQueryValueExW
0x18004422a  nop     dword ptr [rax+rax+00h]
0x18004422f  cmp     eax, 2
0x180044232  jz      loc_1800442E6
0x180044238  test    eax, eax
0x18004423a  jz      short loc_180044253
0x18004423c  mov     r8d, eax
0x18004423f  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x180044246  call    WfpReportSysErrorAsWinError
0x18004424b  mov     rbx, rax
0x18004424e  jmp     loc_1800442E8
0x180044253  mov     eax, [rbp+57h+cbData]
0x180044256  mov     ecx, eax; dwBytes
0x180044258  lea     r8, [rbp+57h+lpData]
0x18004425c  xor     edx, edx; dwFlags
0x18004425e  mov     [rbp+57h+var_58], eax
0x180044261  call    WfpMemAlloc
0x180044266  mov     rbx, rax
0x180044269  test    rax, rax
0x18004426c  jnz     short loc_1800442E8
0x18004426e  mov     r14, [rbp+57h+lpData]
0x180044272  lea     rax, [rbp+57h+var_58]
0x180044276  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18004427b  lea     r9, [rbp+57h+Type]; lpType
0x18004427f  xor     r8d, r8d; lpReserved
0x180044282  mov     [rsp+0C0h+phkResult], r14; lpData
0x180044287  lea     rdx, aWfpdiagmaxfile; "WfpDiagMaxFileSizeKB"
0x18004428e  mov     rcx, rdi; hKey
0x180044291  call    cs:__imp_RegQueryValueExW
0x180044298  nop     dword ptr [rax+rax+00h]
0x18004429d  cmp     eax, 2
0x1800442a0  jz      short loc_1800442BF
0x1800442a2  cmp     eax, 0EAh
0x1800442a7  jz      short loc_1800442BF
0x1800442a9  test    eax, eax
0x1800442ab  jz      short loc_1800442C5
0x1800442ad  mov     r8d, eax
0x1800442b0  lea     rdx, aRegqueryvaluee; "RegQueryValueExW"
0x1800442b7  call    WfpReportSysErrorAsWinError
0x1800442bc  mov     rbx, rax
0x1800442bf  mov     r14, [rbp+57h+var_90]
0x1800442c3  jmp     short loc_1800442E8
0x1800442c5  cmp     [rbp+57h+Type], 4
0x1800442c9  jnz     short loc_1800442BF
0x1800442cb  mov     eax, [rbp+57h+cbData]
0x1800442ce  cmp     [rbp+57h+var_58], eax
0x1800442d1  jnz     short loc_1800442BF
0x1800442d3  mov     [rbp+57h+lpData], r13
0x1800442d7  mov     r12, r14
0x1800442da  mov     r13d, 1
0x1800442e0  mov     [rbp+57h+var_68], r14
0x1800442e4  jmp     short loc_1800442BF
0x1800442e6  xor     ebx, ebx
0x1800442e8  lea     rcx, [rbp+57h+lpData]
0x1800442ec  call    WfpMemFree
0x1800442f1  mov     rcx, rdi
0x1800442f4  call    BfeRegCloseKey
0x1800442f9  xor     edi, edi
0x1800442fb  test    rbx, rbx
0x1800442fe  jz      short loc_180044311
0x180044300  lea     rdx, aBferegqueryval; "BfeRegQueryValue"
0x180044307  mov     rcx, rbx
0x18004430a  call    WfpReportError
0x18004430f  jmp     short loc_18004431A
0x180044311  test    r13d, r13d
0x180044314  jz      short loc_18004431A
0x180044316  mov     r15d, [r12]
0x18004431a  lea     rcx, [rbp+57h+var_68]
0x18004431e  call    WfpMemFree
0x180044323  test    rbx, rbx
0x180044326  jz      short loc_180044388
0x180044328  lea     rdx, aBferegquerydwo; "BfeRegQueryDWord"
0x18004432f  mov     rcx, rbx
0x180044332  call    WfpReportError
0x180044337  lea     rcx, [rbp+57h+var_78]
0x18004433b  call    BfeEventControllerDestroy
0x180044340  lea     rcx, [rbp+57h+var_70]
0x180044344  call    WfpMemFree
0x180044349  test    rbx, rbx
0x18004434c  jz      short loc_18004435D
0x18004434e  lea     rdx, aBfeeventcontro; "BfeEventControllerCreate"
0x180044355  mov     rcx, rbx
0x180044358  call    WfpReportError
0x18004435d  mov     rax, rbx
0x180044360  mov     rcx, [rbp+57h+var_40]
0x180044364  xor     rcx, rsp; StackCookie
0x180044367  call    __security_check_cookie
0x18004436c  mov     rbx, [rsp+0C0h+arg_8]
0x180044374  add     rsp, 90h
0x18004437b  pop     r15
0x18004437d  pop     r14
0x18004437f  pop     r13
0x180044381  pop     r12
0x180044383  pop     rdi
0x180044384  pop     rsi
0x180044385  pop     rbp
0x180044386  retn
0x180044388  test    r13d, r13d
0x18004438b  jz      short loc_18004439F
0x18004438d  lea     eax, [r15-1]
0x180044391  cmp     eax, 0FFFFEh
0x180044396  ja      short loc_18004439F
0x180044398  mov     rax, [rsi]
0x18004439b  mov     [rax+3Ch], r15d
0x18004439f  cmp     [rbp+57h+var_80], edi
0x1800443a2  jz      short loc_1800443AC
0x1800443a4  mov     rax, [rsi]
0x1800443a7  bts     dword ptr [rax+40h], 8
0x1800443ac  mov     r8, [rsi]; Properties
0x1800443af  lea     rdx, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x1800443b6  mov     r9d, 1; ControlCode
0x1800443bc  xor     ecx, ecx; TraceHandle
0x1800443be  call    cs:__imp_ControlTraceW
0x1800443c5  nop     dword ptr [rax+rax+00h]
0x1800443ca  cmp     eax, 1069h
0x1800443cf  jz      short loc_1800443DE
0x1800443d1  test    eax, eax
0x1800443d3  jz      short loc_1800443DE
0x1800443d5  lea     rdx, aControltracew; "ControlTraceW"
0x1800443dc  jmp     short loc_180044403
0x1800443de  mov     r8, [rsi]; Properties
0x1800443e1  lea     rcx, [rsi+8]; TraceHandle
0x1800443e5  lea     rdx, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x1800443ec  call    cs:__imp_StartTraceW
0x1800443f3  nop     dword ptr [rax+rax+00h]
0x1800443f8  test    eax, eax
0x1800443fa  jz      short loc_18004441C
0x1800443fc  lea     rdx, aStarttracew; "StartTraceW"
0x180044403  mov     r8d, eax
0x180044406  call    WfpReportSysErrorAsWinError
0x18004440b  mov     rbx, rax
0x18004440e  test    rax, rax
0x180044411  jnz     loc_180044337
0x180044417  jmp     loc_180044340
0x18004441c  mov     edx, [rbp+57h+var_7C]
0x18004441f  xor     r8d, r8d
0x180044422  mov     rcx, rsi
0x180044425  call    BfeEventControllerEnableAllProviders
0x18004442a  mov     rbx, rax
0x18004442d  test    rax, rax
0x180044430  jnz     loc_180044337
0x180044436  mov     [r14], rsi
0x180044439  jmp     loc_180044340
```
