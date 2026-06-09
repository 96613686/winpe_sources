# BfeNetEventStartRealTime

- ea: `0x18002158c`
- end: `0x180021709`
- name: `BfeNetEventStartRealTime`
- size: `381`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021300`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x18002158c`
- `0x180024e40`
- `0x18004a054`
- `0x18005aa60`
- `0x18005b4fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800216f4`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180021671`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180021671`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180021641`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180021641`

## string_xrefs

- `0x1800216eb`: `OpenTraceW`
- `0x180021700`: `CreateThread`

## pseudocode

```c
__int64 __fastcall BfeNetEventStartRealTime(__int64 a1, __int64 a2, TRACEHANDLE **a3)
{
  __int64 v4; // rbx
  TRACEHANDLE *v5; // rdi
  TRACEHANDLE v6; // rax
  HANDLE Thread; // rax
  DWORD LastError; // eax
  __int64 v10; // rcx
  const char *v11; // rdx
  LPVOID lpParameter[2]; // [rsp+30h] [rbp-1E8h] BYREF
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-1D8h] BYREF

  lpParameter[0] = 0;
  Logfile.LogFileName = 0;
  memset_0(&Logfile.LoggerName, 0, 0x1B8u);
  v4 = WfpMemAlloc(0x20u, 0);
  if ( v4 )
    goto LABEL_7;
  v5 = (TRACEHANDLE *)lpParameter[0];
  *(_QWORD *)lpParameter[0] = -1;
  v5[1] = 0;
  v5[2] = (TRACEHANDLE)BfeNetEventCallback;
  v5[3] = 0;
  Logfile.LoggerName = (LPWSTR)L"WFP-IPsec Diagnostics";
  Logfile.EventCallback = (PEVENT_CALLBACK)BfeNetEventRealTimeCallback;
  Logfile.LogFileMode = 268435712;
  Logfile.Context = v5;
  v6 = OpenTraceW(&Logfile);
  *v5 = v6;
  if ( v6 == -1 )
  {
    LastError = GetLastError();
    v11 = "OpenTraceW";
    goto LABEL_5;
  }
  Thread = CreateThread(0, 0, BfeNetEventRealTimeWorker, v5, 0, 0);
  v5[1] = (TRACEHANDLE)Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v11 = "CreateThread";
LABEL_5:
    v4 = WfpReportSysErrorAsWinError(v10, v11, LastError);
    if ( !v4 )
      return v4;
LABEL_7:
    BfeNetEventStopRealTime(lpParameter);
    WfpReportError(v4, "BfeNetEventStartRealTime");
    return v4;
  }
  *a3 = v5;
  return v4;
}

```

## disassembly

```asm
0x18002158c  mov     [rsp+arg_0], rbx
0x180021591  mov     [rsp+arg_8], rsi
0x180021596  push    rdi
0x180021597  sub     rsp, 210h
0x18002159e  mov     rax, cs:__security_cookie
0x1800215a5  xor     rax, rsp
0x1800215a8  mov     [rsp+218h+var_18], rax
0x1800215b0  mov     rsi, r8
0x1800215b3  mov     [rsp+218h+lpParameter], 0
0x1800215bc  mov     r8d, 1B8h; Size
0x1800215c2  mov     [rsp+218h+Logfile.LogFileName], 0
0x1800215cb  xor     edx, edx; Val
0x1800215cd  lea     rcx, [rsp+218h+Logfile.LoggerName]; void *
0x1800215d2  call    memset_0
0x1800215d7  xor     edx, edx; dwFlags
0x1800215d9  lea     r8, [rsp+218h+lpParameter]
0x1800215de  lea     ecx, [rdx+20h]; dwBytes
0x1800215e1  call    WfpMemAlloc
0x1800215e6  mov     rbx, rax
0x1800215e9  test    rax, rax
0x1800215ec  jnz     loc_1800216C4
0x1800215f2  mov     rdi, [rsp+218h+lpParameter]
0x1800215f7  lea     rcx, [rsp+218h+Logfile]; Logfile
0x1800215fc  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x180021603  mov     [rdi+8], rax
0x180021607  lea     rax, BfeNetEventCallback
0x18002160e  mov     [rdi+10h], rax
0x180021612  lea     rax, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x180021619  mov     [rdi+18h], rbx
0x18002161d  mov     [rsp+218h+Logfile.LoggerName], rax
0x180021622  lea     rax, BfeNetEventRealTimeCallback
0x180021629  mov     qword ptr [rsp+218h+Logfile.1A8h], rax
0x180021631  mov     dword ptr [rsp+218h+Logfile.1Ch], 10000100h
0x180021639  mov     [rsp+218h+Logfile.Context], rdi
0x180021641  call    cs:__imp_OpenTraceW
0x180021648  nop     dword ptr [rax+rax+00h]
0x18002164d  mov     [rdi], rax
0x180021650  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180021654  jz      loc_1800216DF
0x18002165a  mov     [rsp+218h+lpThreadId], rbx; lpThreadId
0x18002165f  lea     r8, BfeNetEventRealTimeWorker; lpStartAddress
0x180021666  mov     r9, rdi; lpParameter
0x180021669  mov     [rsp+218h+dwCreationFlags], ebx; dwCreationFlags
0x18002166d  xor     edx, edx; dwStackSize
0x18002166f  xor     ecx, ecx; lpThreadAttributes
0x180021671  call    cs:__imp_CreateThread
0x180021678  nop     dword ptr [rax+rax+00h]
0x18002167d  mov     [rdi+8], rax
0x180021681  test    rax, rax
0x180021684  jz      short loc_1800216F4
0x180021686  mov     [rsi], rdi
0x180021689  jmp     short loc_18002169B
0x18002168b  mov     r8d, eax
0x18002168e  call    WfpReportSysErrorAsWinError
0x180021693  mov     rbx, rax
0x180021696  test    rax, rax
0x180021699  jnz     short loc_1800216C4
0x18002169b  mov     rax, rbx
0x18002169e  mov     rcx, [rsp+218h+var_18]
0x1800216a6  xor     rcx, rsp; StackCookie
0x1800216a9  call    __security_check_cookie
0x1800216ae  lea     r11, [rsp+218h+var_8]
0x1800216b6  mov     rbx, [r11+10h]
0x1800216ba  mov     rsi, [r11+18h]
0x1800216be  mov     rsp, r11
0x1800216c1  pop     rdi
0x1800216c2  retn
0x1800216c4  lea     rcx, [rsp+218h+lpParameter]
0x1800216c9  call    BfeNetEventStopRealTime
0x1800216ce  lea     rdx, aBfeneteventsta; "BfeNetEventStartRealTime"
0x1800216d5  mov     rcx, rbx
0x1800216d8  call    WfpReportError
0x1800216dd  jmp     short loc_18002169B
0x1800216df  call    cs:__imp_GetLastError
0x1800216e6  nop     dword ptr [rax+rax+00h]
0x1800216eb  lea     rdx, aOpentracew; "OpenTraceW"
0x1800216f2  jmp     short loc_18002168B
0x1800216f4  call    cs:__imp_GetLastError
0x1800216fb  nop     dword ptr [rax+rax+00h]
0x180021700  lea     rdx, aCreatethread; "CreateThread"
0x180021707  jmp     short loc_18002168B
```
