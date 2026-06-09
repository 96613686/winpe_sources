# BfeNetEventCreateEnumContext

- ea: `0x18001f028`
- end: `0x18001f308`
- name: `BfeNetEventCreateEnumContext`
- size: `736`
- prototype: `__int64 __fastcall(LPFILETIME StartTime, int, _QWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180044dc8`

## callees

- `0x18000e000`
- `0x18001236c`
- `0x180018b74`
- `0x18001d91c`
- `0x18001da08`
- `0x18001f028`
- `0x18001f338`
- `0x180022730`
- `0x18002b67c`
- `0x180058b30`
- `0x1800595ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2b1`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001f1be`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x18001f1be`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18001f1dc`
- `api-ms-win-eventing-consumer-l1-1-0!ProcessTrace` at `0x18001f1dc`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18001f2e9`
- `api-ms-win-eventing-consumer-l1-1-0!CloseTrace` at `0x18001f2e9`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001f181`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001f181`

## string_xrefs

- `0x18001f203`: `BfeEnumContextCreate`
- `0x18001f0b1`: `%ProgramData%\Microsoft\Windows\wfp\wfpdiag.etl`
- `0x18001f0c0`: `%ProgramData%\Microsoft\Windows\wfp\ikediag.etl`
- `0x18001f212`: `BfeNetEventCreateEmptyEnumContext`
- `0x18001f2b7`: `OpenTraceW`
- `0x18001f2f4`: `BfeNetEventCreateEnumContext`

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
  _WORD *v12; // rbx
  DWORD LastError; // eax
  __int64 v14; // rcx
  const char *v16; // rdx
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+20h] [rbp-E0h] BYREF
  void *v18; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD *v19; // [rsp+30h] [rbp-D0h]
  _QWORD *v20; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v21[66]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+150h] [rbp+50h]
  struct _EVENT_TRACE_LOGFILEW Logfile; // [rsp+160h] [rbp+60h] BYREF
  ULONG64 HandleArray; // [rsp+320h] [rbp+220h] BYREF

  memset_0(v21, 0, 0x110u);
  v18 = 0;
  Logfile.LogFileName = 0;
  memset_0(&Logfile.LoggerName, 0, 0x1B8u);
  HandleArray = -1;
  Properties = 0;
  v21[0] = 3;
  v6 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\ikediag.etl";
  *a3 = 0;
  if ( !a2 )
    v6 = L"%ProgramData%\\Microsoft\\Windows\\wfp\\wfpdiag.etl";
  v19 = 0;
  v20 = 0;
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
  v10 = v19;
  *v19 = BfeFwpNetEventInternalCopy;
  v10[1] = BfeFwpNetEventInternalDestroy;
  v20 = v10;
  if ( StartTime )
  {
    v9 = BfeNetEventEnumTemplateConvert(StartTime, v21);
    if ( v9 )
      goto LABEL_14;
    v11 = StartTime + 1;
  }
  else
  {
    v11 = 0;
  }
  v9 = BfeExpandEnvironmentStrings(v6, (LPWSTR *)&v18);
  if ( v9 )
    goto LABEL_14;
  v12 = v18;
  Logfile.EventCallback = (PEVENT_CALLBACK)BfeNetEventEnumCallback;
  Logfile.LogFileName = (LPWSTR)v18;
  Logfile.Context = &v20;
  Logfile.LogFileMode = 0x10000000;
  HandleArray = OpenTraceW(&Logfile);
  if ( HandleArray == -1 )
  {
    LastError = GetLastError();
    v16 = "OpenTraceW";
    goto LABEL_16;
  }
  v9 = BfeEventTracePropertiesAlloc(v7, v12, &Properties);
  if ( v9 )
  {
LABEL_14:
    BfeEnumContextDestroy(&v20);
    goto LABEL_17;
  }
  LastError = ControlTraceW(0, v7, Properties, 3u);
  if ( LastError )
  {
    v16 = "ControlTraceW";
    goto LABEL_16;
  }
  LastError = ProcessTrace(&HandleArray, 1u, StartTime, v11);
  if ( LastError )
  {
    v16 = "ProcessTrace";
LABEL_16:
    v9 = WfpReportSysErrorAsWinError(v14, v16, LastError);
    if ( v9 )
      goto LABEL_14;
    goto LABEL_17;
  }
  v9 = v22;
  if ( v22 )
    goto LABEL_14;
  *a3 = v20;
LABEL_17:
  WfpMemFree(&Properties);
  if ( HandleArray != -1 )
    CloseTrace(HandleArray);
  WfpMemFree(&v18);
  if ( v9 )
    WfpReportError(v9, "BfeNetEventCreateEnumContext");
  return v9;
}

```

## disassembly

```asm
0x18001f028  mov     [rsp-8+arg_8], rbx
0x18001f02d  mov     [rsp-8+arg_18], rsi
0x18001f032  push    rbp
0x18001f033  push    rdi
0x18001f034  push    r12
0x18001f036  push    r14
0x18001f038  push    r15
0x18001f03a  lea     rbp, [rsp-230h]
0x18001f042  sub     rsp, 330h
0x18001f049  mov     rax, cs:__security_cookie
0x18001f050  xor     rax, rsp
0x18001f053  mov     [rbp+250h+var_28], rax
0x18001f05a  mov     r12, r8
0x18001f05d  mov     ebx, edx
0x18001f05f  mov     rdi, rcx
0x18001f062  xor     edx, edx; Val
0x18001f064  mov     r8d, 110h; Size
0x18001f06a  lea     rcx, [rsp+350h+var_308]; void *
0x18001f06f  call    memset_0
0x18001f074  xor     edx, edx; Val
0x18001f076  mov     [rsp+350h+var_328], 0
0x18001f07f  mov     r8d, 1B8h; Size
0x18001f085  mov     [rbp+250h+Logfile.LogFileName], 0
0x18001f08d  lea     rcx, [rbp+250h+Logfile.LoggerName]; void *
0x18001f091  call    memset_0
0x18001f096  test    ebx, ebx
0x18001f098  mov     [rbp+250h+HandleArray], 0FFFFFFFFFFFFFFFFh
0x18001f0a3  mov     edx, 8; dwFlags
0x18001f0a8  mov     [rsp+350h+Properties], 0
0x18001f0b1  lea     rax, FWP_EVENT_LOGFILE_NAME; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x18001f0b8  mov     [rsp+350h+var_308], 3
0x18001f0c0  lea     r15, FWP_IKEEVENT_LOGFILE_NAME; "%ProgramData%\\Microsoft\\Windows\\wfp"...
0x18001f0c7  mov     qword ptr [r12], 0
0x18001f0cf  cmovz   r15, rax
0x18001f0d3  mov     [rsp+350h+var_320], 0
0x18001f0dc  lea     rax, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x18001f0e3  mov     [rsp+350h+var_310], 0
0x18001f0ec  lea     r14, FWP_IKEEVENT_LOGGER_NAME; "WFP-IKE Diagnostics"
0x18001f0f3  lea     ecx, [rdx+20h]; dwBytes
0x18001f0f6  cmovz   r14, rax
0x18001f0fa  lea     r8, [rsp+350h+var_320]
0x18001f0ff  call    WfpMemAlloc
0x18001f104  mov     rbx, rax
0x18001f107  test    rax, rax
0x18001f10a  jnz     loc_18001F203
0x18001f110  mov     rax, [rsp+350h+var_320]
0x18001f115  lea     rcx, BfeFwpNetEventInternalCopy
0x18001f11c  mov     [rax], rcx
0x18001f11f  lea     rcx, BfeFwpNetEventInternalDestroy
0x18001f126  mov     [rax+8], rcx
0x18001f12a  mov     [rsp+350h+var_310], rax
0x18001f12f  test    rdi, rdi
0x18001f132  jnz     loc_18001F28F
0x18001f138  xor     esi, esi
0x18001f13a  lea     rdx, [rsp+350h+var_328]
0x18001f13f  mov     rcx, r15; lpSrc
0x18001f142  call    BfeExpandEnvironmentStrings
0x18001f147  mov     rbx, rax
0x18001f14a  test    rax, rax
0x18001f14d  jnz     loc_18001F1F7
0x18001f153  mov     rbx, [rsp+350h+var_328]
0x18001f158  lea     rax, BfeNetEventEnumCallback
0x18001f15f  mov     qword ptr [rbp+250h+Logfile.1A8h], rax
0x18001f166  lea     rcx, [rbp+250h+Logfile]; Logfile
0x18001f16a  lea     rax, [rsp+350h+var_310]
0x18001f16f  mov     [rbp+250h+Logfile.LogFileName], rbx
0x18001f173  mov     [rbp+250h+Logfile.Context], rax
0x18001f17a  mov     dword ptr [rbp+250h+Logfile.1Ch], 10000000h
0x18001f181  call    cs:__imp_OpenTraceW
0x18001f187  mov     [rbp+250h+HandleArray], rax
0x18001f18e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f192  jz      loc_18001F2B1
0x18001f198  lea     r8, [rsp+350h+Properties]
0x18001f19d  mov     rdx, rbx; void *
0x18001f1a0  mov     rcx, r14; Src
0x18001f1a3  call    BfeEventTracePropertiesAlloc
0x18001f1a8  mov     rbx, rax
0x18001f1ab  test    rax, rax
0x18001f1ae  jnz     short loc_18001F1F7
0x18001f1b0  mov     r8, [rsp+350h+Properties]; Properties
0x18001f1b5  lea     r9d, [rax+3]; ControlCode
0x18001f1b9  mov     rdx, r14; InstanceName
0x18001f1bc  xor     ecx, ecx; TraceHandle
0x18001f1be  call    cs:__imp_ControlTraceW
0x18001f1c4  test    eax, eax
0x18001f1c6  jnz     loc_18001F2C3
0x18001f1cc  mov     r9, rsi; EndTime
0x18001f1cf  lea     edx, [rbx+1]; HandleCount
0x18001f1d2  mov     r8, rdi; StartTime
0x18001f1d5  lea     rcx, [rbp+250h+HandleArray]; HandleArray
0x18001f1dc  call    cs:__imp_ProcessTrace
0x18001f1e2  test    eax, eax
0x18001f1e4  jnz     loc_18001F2CF
0x18001f1ea  mov     rbx, [rbp+250h+var_200]
0x18001f1ee  test    rbx, rbx
0x18001f1f1  jz      loc_18001F2DB
0x18001f1f7  lea     rcx, [rsp+350h+var_310]
0x18001f1fc  call    BfeEnumContextDestroy
0x18001f201  jmp     short loc_18001F233
0x18001f203  lea     rdx, aBfeenumcontext; "BfeEnumContextCreate"
0x18001f20a  mov     rcx, rbx
0x18001f20d  call    WfpReportError
0x18001f212  lea     rdx, aBfeneteventcre; "BfeNetEventCreateEmptyEnumContext"
0x18001f219  mov     rcx, rbx
0x18001f21c  call    WfpReportError
0x18001f221  jmp     short loc_18001F1F7
0x18001f223  mov     r8d, eax
0x18001f226  call    WfpReportSysErrorAsWinError
0x18001f22b  mov     rbx, rax
0x18001f22e  test    rax, rax
0x18001f231  jnz     short loc_18001F1F7
0x18001f233  lea     rcx, [rsp+350h+Properties]
0x18001f238  call    WfpMemFree
0x18001f23d  mov     rcx, [rbp+250h+HandleArray]; TraceHandle
0x18001f244  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001f248  jnz     loc_18001F2E9
0x18001f24e  lea     rcx, [rsp+350h+var_328]
0x18001f253  call    WfpMemFree
0x18001f258  test    rbx, rbx
0x18001f25b  jnz     loc_18001F2F4
0x18001f261  mov     rax, rbx
0x18001f264  mov     rcx, [rbp+250h+var_28]
0x18001f26b  xor     rcx, rsp; StackCookie
0x18001f26e  call    __security_check_cookie
0x18001f273  lea     r11, [rsp+350h+var_20]
0x18001f27b  mov     rbx, [r11+38h]
0x18001f27f  mov     rsi, [r11+48h]
0x18001f283  mov     rsp, r11
0x18001f286  pop     r15
0x18001f288  pop     r14
0x18001f28a  pop     r12
0x18001f28c  pop     rdi
0x18001f28d  pop     rbp
0x18001f28e  retn
0x18001f28f  lea     rdx, [rsp+350h+var_308]
0x18001f294  mov     rcx, rdi
0x18001f297  call    BfeNetEventEnumTemplateConvert
0x18001f29c  mov     rbx, rax
0x18001f29f  test    rax, rax
0x18001f2a2  jnz     loc_18001F1F7
0x18001f2a8  lea     rsi, [rdi+8]
0x18001f2ac  jmp     loc_18001F13A
0x18001f2b1  call    cs:__imp_GetLastError
0x18001f2b7  lea     rdx, aOpentracew; "OpenTraceW"
0x18001f2be  jmp     loc_18001F223
0x18001f2c3  lea     rdx, aControltracew; "ControlTraceW"
0x18001f2ca  jmp     loc_18001F223
0x18001f2cf  lea     rdx, aProcesstrace; "ProcessTrace"
0x18001f2d6  jmp     loc_18001F223
0x18001f2db  mov     rax, [rsp+350h+var_310]
0x18001f2e0  mov     [r12], rax
0x18001f2e4  jmp     loc_18001F233
0x18001f2e9  call    cs:__imp_CloseTrace
0x18001f2ef  jmp     loc_18001F24E
0x18001f2f4  lea     rdx, aBfeneteventcre_1; "BfeNetEventCreateEnumContext"
0x18001f2fb  mov     rcx, rbx
0x18001f2fe  call    WfpReportError
0x18001f303  jmp     loc_18001F261
```
