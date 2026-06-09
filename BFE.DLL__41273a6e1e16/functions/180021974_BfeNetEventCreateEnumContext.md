# BfeNetEventCreateEnumContext

- ea: `0x180021974`
- end: `0x180021c73`
- name: `BfeNetEventCreateEnumContext`
- size: `767`
- prototype: `__int64 __fastcall(LPFILETIME StartTime)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180046c24`

## callees

- `0x18000e7e0`
- `0x180012d8c`
- `0x1800197d0`
- `0x180021974`
- `0x180021ca8`
- `0x180024e40`
- `0x18002d020`
- `0x180044444`
- `0x180044588`
- `0x18005aa60`
- `0x18005b4fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021c10`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180021b10`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180021b10`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180021b34`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x180021b34`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180021c4e`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x180021c4e`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180021acd`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180021acd`

## string_xrefs

- `0x180021b61`: `BfeEnumContextCreate`
- `0x1800219fd`: `%ProgramData%\Microsoft\Windows\wfp\wfpdiag.etl`
- `0x180021a0c`: `%ProgramData%\Microsoft\Windows\wfp\ikediag.etl`
- `0x180021b70`: `BfeNetEventCreateEmptyEnumContext`
- `0x180021c1c`: `OpenTraceW`
- `0x180021c5f`: `BfeNetEventCreateEnumContext`

## pseudocode

```c
__int64 __fastcall BfeNetEventCreateEnumContext(LPFILETIME StartTime, int a2, _QWORD *a3)
{
  const WCHAR *v6; // r15
  WCHAR *v7; // r14
  __int64 v8; // rax
  __int64 v9; // rbx
  _QWORD *v10; // rax
  struct _FILETIME *v11; // rsi
  DWORD LastError; // eax
  __int64 v13; // rcx
  const char *v15; // rdx
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+20h] [rbp-E0h] BYREF
  void *v17; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v18; // [rsp+30h] [rbp-D0h]
  _QWORD *v19; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v20[66]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+150h] [rbp+50h]
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+160h] [rbp+60h] BYREF
  ULONG64 HandleArray; // [rsp+320h] [rbp+220h] BYREF

  memset_0(v20, 0, 0x110u);
  v17 = 0;
  Logfile.LogFileName = 0;
  memset_0(&Logfile.LoggerName, 0, 0x1B8u);
  HandleArray = -1;
  Properties = 0;
  v20[0] = 3;
  v6 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\ikediag.etl";
  *a3 = 0;
  if ( !a2 )
    v6 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpdiag.etl";
  v18 = 0;
  v19 = 0;
  v7 = (WCHAR *)L"WFP-IKE Diagnostics";
  if ( !a2 )
    v7 = (WCHAR *)L"WFP-IPsec Diagnostics";
  v8 = WfpMemAlloc(0x28u, 8u);
  v9 = v8;
  if ( v8 )
  {
    WfpReportError(v8, "BfeEnumContextCreate");
    WfpReportError(v9, "BfeNetEventCreateEmptyEnumContext");
    goto LABEL_14;
  }
  v10 = v18;
  *v18 = BfeFwpNetEventInternalCopy;
  v10[1] = BfeFwpNetEventInternalDestroy;
  v19 = v10;
  if ( StartTime )
  {
    v9 = BfeNetEventEnumTemplateConvert(StartTime, v20);
    if ( v9 )
      goto LABEL_14;
    v11 = StartTime + 1;
  }
  else
  {
    v11 = 0;
  }
  v9 = BfeExpandEnvironmentStrings(v6);
  if ( v9 )
    goto LABEL_14;
  Logfile.EventCallback = (PEVENT_CALLBACK)BfeNetEventEnumCallback;
  Logfile.LogFileName = (LPWSTR)v17;
  Logfile.Context = &v19;
  Logfile.LogFileMode = 0x10000000;
  HandleArray = OpenTraceW(&Logfile);
  if ( HandleArray == -1 )
  {
    LastError = GetLastError();
    v15 = "OpenTraceW";
    goto LABEL_16;
  }
  v9 = BfeEventTracePropertiesAlloc(v7, v17);
  if ( v9 )
  {
LABEL_14:
    BfeEnumContextDestroy(&v19);
    goto LABEL_17;
  }
  LastError = ControlTraceW(0, v7, Properties, 3u);
  if ( LastError )
  {
    v15 = "ControlTraceW";
    goto LABEL_16;
  }
  LastError = ProcessTrace(&HandleArray, 1u, StartTime, v11);
  if ( LastError )
  {
    v15 = "ProcessTrace";
LABEL_16:
    v9 = WfpReportSysErrorAsWinError(v13, v15, LastError);
    if ( v9 )
      goto LABEL_14;
    goto LABEL_17;
  }
  v9 = v21;
  if ( v21 )
    goto LABEL_14;
  *a3 = v19;
LABEL_17:
  WfpMemFree(&Properties);
  if ( HandleArray != -1 )
    CloseTrace(HandleArray);
  WfpMemFree(&v17);
  if ( v9 )
    WfpReportError(v9, "BfeNetEventCreateEnumContext");
  return v9;
}

```

## disassembly

```asm
0x180021974  mov     [rsp-8+arg_8], rbx
0x180021979  mov     [rsp-8+arg_18], rsi
0x18002197e  push    rbp
0x18002197f  push    rdi
0x180021980  push    r12
0x180021982  push    r14
0x180021984  push    r15
0x180021986  lea     rbp, [rsp-230h]
0x18002198e  sub     rsp, 330h
0x180021995  mov     rax, cs:__security_cookie
0x18002199c  xor     rax, rsp
0x18002199f  mov     [rbp+250h+var_28], rax
0x1800219a6  mov     r12, r8
0x1800219a9  mov     ebx, edx
0x1800219ab  mov     rdi, rcx
0x1800219ae  xor     edx, edx; Val
0x1800219b0  mov     r8d, 110h; Size
0x1800219b6  lea     rcx, [rsp+350h+var_308]; void *
0x1800219bb  call    memset_0
0x1800219c0  xor     edx, edx; Val
0x1800219c2  mov     [rsp+350h+var_328], 0
0x1800219cb  mov     r8d, 1B8h; Size
0x1800219d1  mov     [rbp+250h+Logfile.LogFileName], 0
0x1800219d9  lea     rcx, [rbp+250h+Logfile.LoggerName]; void *
0x1800219dd  call    memset_0
0x1800219e2  test    ebx, ebx
0x1800219e4  mov     [rbp+250h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x1800219ef  mov     edx, 8; dwFlags
0x1800219f4  mov     [rsp+350h+Properties], 0
0x1800219fd  lea     rax, FWP_EVENT_LOGFILE_NAME; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x180021a04  mov     [rsp+350h+var_308], 3
0x180021a0c  lea     r15, FWP_IKEEVENT_LOGFILE_NAME; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x180021a13  mov     qword ptr [r12], 0
0x180021a1b  cmovz   r15, rax
0x180021a1f  mov     [rsp+350h+var_320], 0
0x180021a28  lea     rax, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x180021a2f  mov     [rsp+350h+var_310], 0
0x180021a38  lea     r14, FWP_IKEEVENT_LOGGER_NAME; "WFP-IKE Diagnostics"
0x180021a3f  lea     ecx, [rdx+20h]; dwBytes
0x180021a42  cmovz   r14, rax
0x180021a46  lea     r8, [rsp+350h+var_320]
0x180021a4b  call    WfpMemAlloc
0x180021a50  mov     rbx, rax
0x180021a53  test    rax, rax
0x180021a56  jnz     loc_180021B61
0x180021a5c  mov     rax, [rsp+350h+var_320]
0x180021a61  lea     rcx, BfeFwpNetEventInternalCopy
0x180021a68  mov     [rax], rcx
0x180021a6b  lea     rcx, BfeFwpNetEventInternalDestroy
0x180021a72  mov     [rax+8], rcx
0x180021a76  mov     [rsp+350h+var_310], rax
0x180021a7b  test    rdi, rdi
0x180021a7e  jnz     loc_180021BEE
0x180021a84  xor     esi, esi
0x180021a86  lea     rdx, [rsp+350h+var_328]
0x180021a8b  mov     rcx, r15; lpSrc
0x180021a8e  call    BfeExpandEnvironmentStrings
0x180021a93  mov     rbx, rax
0x180021a96  test    rax, rax
0x180021a99  jnz     loc_180021B55
0x180021a9f  mov     rbx, [rsp+350h+var_328]
0x180021aa4  lea     rax, BfeNetEventEnumCallback
0x180021aab  mov     qword ptr [rbp+250h+Logfile.1A8h], rax
0x180021ab2  lea     rcx, [rbp+250h+Logfile]; Logfile
0x180021ab6  lea     rax, [rsp+350h+var_310]
0x180021abb  mov     [rbp+250h+Logfile.LogFileName], rbx
0x180021abf  mov     [rbp+250h+Logfile.Context], rax
0x180021ac6  mov     dword ptr [rbp+250h+Logfile.1Ch], 10000000h
0x180021acd  call    cs:__imp_OpenTraceW
0x180021ad4  nop     dword ptr [rax+rax+00h]
0x180021ad9  mov     [rbp+250h+HandleArray], rax
0x180021ae0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021ae4  jz      loc_180021C10
0x180021aea  lea     r8, [rsp+350h+Properties]
0x180021aef  mov     rdx, rbx; void *
0x180021af2  mov     rcx, r14; Src
0x180021af5  call    BfeEventTracePropertiesAlloc
0x180021afa  mov     rbx, rax
0x180021afd  test    rax, rax
0x180021b00  jnz     short loc_180021B55
0x180021b02  mov     r8, [rsp+350h+Properties]; Properties
0x180021b07  lea     r9d, [rax+3]; ControlCode
0x180021b0b  mov     rdx, r14; InstanceName
0x180021b0e  xor     ecx, ecx; TraceHandle
0x180021b10  call    cs:__imp_ControlTraceW
0x180021b17  nop     dword ptr [rax+rax+00h]
0x180021b1c  test    eax, eax
0x180021b1e  jnz     loc_180021C28
0x180021b24  mov     r9, rsi; EndTime
0x180021b27  lea     edx, [rbx+1]; HandleCount
0x180021b2a  mov     r8, rdi; StartTime
0x180021b2d  lea     rcx, [rbp+250h+HandleArray]; HandleArray
0x180021b34  call    cs:__imp_ProcessTrace
0x180021b3b  nop     dword ptr [rax+rax+00h]
0x180021b40  test    eax, eax
0x180021b42  jnz     loc_180021C34
0x180021b48  mov     rbx, [rbp+250h+var_200]
0x180021b4c  test    rbx, rbx
0x180021b4f  jz      loc_180021C40
0x180021b55  lea     rcx, [rsp+350h+var_310]
0x180021b5a  call    BfeEnumContextDestroy
0x180021b5f  jmp     short loc_180021B91
0x180021b61  lea     rdx, aBfeenumcontext; "BfeEnumContextCreate"
0x180021b68  mov     rcx, rbx
0x180021b6b  call    WfpReportError
0x180021b70  lea     rdx, aBfeneteventcre; "BfeNetEventCreateEmptyEnumContext"
0x180021b77  mov     rcx, rbx
0x180021b7a  call    WfpReportError
0x180021b7f  jmp     short loc_180021B55
0x180021b81  mov     r8d, eax
0x180021b84  call    WfpReportSysErrorAsWinError
0x180021b89  mov     rbx, rax
0x180021b8c  test    rax, rax
0x180021b8f  jnz     short loc_180021B55
0x180021b91  lea     rcx, [rsp+350h+Properties]
0x180021b96  call    WfpMemFree
0x180021b9b  mov     rcx, [rbp+250h+HandleArray]; TraceHandle
0x180021ba2  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180021ba6  jnz     loc_180021C4E
0x180021bac  lea     rcx, [rsp+350h+var_328]
0x180021bb1  call    WfpMemFree
0x180021bb6  test    rbx, rbx
0x180021bb9  jnz     loc_180021C5F
0x180021bbf  mov     rax, rbx
0x180021bc2  mov     rcx, [rbp+250h+var_28]
0x180021bc9  xor     rcx, rsp; StackCookie
0x180021bcc  call    __security_check_cookie
0x180021bd1  lea     r11, [rsp+350h+var_20]
0x180021bd9  mov     rbx, [r11+38h]
0x180021bdd  mov     rsi, [r11+48h]
0x180021be1  mov     rsp, r11
0x180021be4  pop     r15
0x180021be6  pop     r14
0x180021be8  pop     r12
0x180021bea  pop     rdi
0x180021beb  pop     rbp
0x180021bec  retn
0x180021bee  lea     rdx, [rsp+350h+var_308]
0x180021bf3  mov     rcx, rdi
0x180021bf6  call    BfeNetEventEnumTemplateConvert
0x180021bfb  mov     rbx, rax
0x180021bfe  test    rax, rax
0x180021c01  jnz     loc_180021B55
0x180021c07  lea     rsi, [rdi+8]
0x180021c0b  jmp     loc_180021A86
0x180021c10  call    cs:__imp_GetLastError
0x180021c17  nop     dword ptr [rax+rax+00h]
0x180021c1c  lea     rdx, aOpentracew; "OpenTraceW"
0x180021c23  jmp     loc_180021B81
0x180021c28  lea     rdx, aControltracew; "ControlTraceW"
0x180021c2f  jmp     loc_180021B81
0x180021c34  lea     rdx, aProcesstrace; "ProcessTrace"
0x180021c3b  jmp     loc_180021B81
0x180021c40  mov     rax, [rsp+350h+var_310]
0x180021c45  mov     [r12], rax
0x180021c49  jmp     loc_180021B91
0x180021c4e  call    cs:__imp_CloseTrace
0x180021c55  nop     dword ptr [rax+rax+00h]
0x180021c5a  jmp     loc_180021BAC
0x180021c5f  lea     rdx, aBfeneteventcre_1; "BfeNetEventCreateEnumContext"
0x180021c66  mov     rcx, rbx
0x180021c69  call    WfpReportError
0x180021c6e  jmp     loc_180021BBF
```
