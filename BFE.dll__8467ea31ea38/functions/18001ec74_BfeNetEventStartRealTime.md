# BfeNetEventStartRealTime

- ea: `0x18001ec74`
- end: `0x18001edd4`
- name: `BfeNetEventStartRealTime`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001e9f0`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x18001d610`
- `0x18001ec74`
- `0x180022730`
- `0x180058b30`
- `0x1800595ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001edc5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ed4f`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001ed4f`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001ed29`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x18001ed29`

## string_xrefs

- `0x18001edbc`: `OpenTraceW`
- `0x18001edcb`: `CreateThread`

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
0x18001ec74  mov     [rsp+arg_0], rbx
0x18001ec79  mov     [rsp+arg_8], rsi
0x18001ec7e  push    rdi
0x18001ec7f  sub     rsp, 210h
0x18001ec86  mov     rax, cs:__security_cookie
0x18001ec8d  xor     rax, rsp
0x18001ec90  mov     [rsp+218h+var_18], rax
0x18001ec98  mov     rsi, r8
0x18001ec9b  mov     [rsp+218h+lpParameter], 0
0x18001eca4  mov     r8d, 1B8h; Size
0x18001ecaa  mov     [rsp+218h+Logfile.LogFileName], 0
0x18001ecb3  xor     edx, edx; Val
0x18001ecb5  lea     rcx, [rsp+218h+Logfile.LoggerName]; void *
0x18001ecba  call    memset_0
0x18001ecbf  xor     edx, edx; dwFlags
0x18001ecc1  lea     r8, [rsp+218h+lpParameter]
0x18001ecc6  lea     ecx, [rdx+20h]; dwBytes
0x18001ecc9  call    WfpMemAlloc
0x18001ecce  mov     rbx, rax
0x18001ecd1  test    rax, rax
0x18001ecd4  jnz     loc_18001ED9B
0x18001ecda  mov     rdi, [rsp+218h+lpParameter]
0x18001ecdf  lea     rcx, [rsp+218h+Logfile]; Logfile
0x18001ece4  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18001eceb  mov     [rdi+8], rax
0x18001ecef  lea     rax, BfeNetEventCallback
0x18001ecf6  mov     [rdi+10h], rax
0x18001ecfa  lea     rax, FWP_EVENT_LOGGER_NAME; "WFP-IPsec Diagnostics"
0x18001ed01  mov     [rdi+18h], rbx
0x18001ed05  mov     [rsp+218h+Logfile.LoggerName], rax
0x18001ed0a  lea     rax, BfeNetEventRealTimeCallback
0x18001ed11  mov     qword ptr [rsp+218h+Logfile.1A8h], rax
0x18001ed19  mov     dword ptr [rsp+218h+Logfile.1Ch], 10000100h
0x18001ed21  mov     [rsp+218h+Logfile.Context], rdi
0x18001ed29  call    cs:__imp_OpenTraceW
0x18001ed2f  mov     [rdi], rax
0x18001ed32  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001ed36  jz      short loc_18001EDB6
0x18001ed38  mov     [rsp+218h+lpThreadId], rbx; lpThreadId
0x18001ed3d  lea     r8, BfeNetEventRealTimeWorker; lpStartAddress
0x18001ed44  mov     r9, rdi; lpParameter
0x18001ed47  mov     [rsp+218h+dwCreationFlags], ebx; dwCreationFlags
0x18001ed4b  xor     edx, edx; dwStackSize
0x18001ed4d  xor     ecx, ecx; lpThreadAttributes
0x18001ed4f  call    cs:__imp_CreateThread
0x18001ed55  mov     [rdi+8], rax
0x18001ed59  test    rax, rax
0x18001ed5c  jz      short loc_18001EDC5
0x18001ed5e  mov     [rsi], rdi
0x18001ed61  jmp     short loc_18001ED73
0x18001ed63  mov     r8d, eax
0x18001ed66  call    WfpReportSysErrorAsWinError
0x18001ed6b  mov     rbx, rax
0x18001ed6e  test    rax, rax
0x18001ed71  jnz     short loc_18001ED9B
0x18001ed73  mov     rax, rbx
0x18001ed76  mov     rcx, [rsp+218h+var_18]
0x18001ed7e  xor     rcx, rsp; StackCookie
0x18001ed81  call    __security_check_cookie
0x18001ed86  lea     r11, [rsp+218h+var_8]
0x18001ed8e  mov     rbx, [r11+10h]
0x18001ed92  mov     rsi, [r11+18h]
0x18001ed96  mov     rsp, r11
0x18001ed99  pop     rdi
0x18001ed9a  retn
0x18001ed9b  lea     rcx, [rsp+218h+lpParameter]
0x18001eda0  call    BfeNetEventStopRealTime
0x18001eda5  lea     rdx, aBfeneteventsta; "BfeNetEventStartRealTime"
0x18001edac  mov     rcx, rbx
0x18001edaf  call    WfpReportError
0x18001edb4  jmp     short loc_18001ED73
0x18001edb6  call    cs:__imp_GetLastError
0x18001edbc  lea     rdx, aOpentracew; "OpenTraceW"
0x18001edc3  jmp     short loc_18001ED63
0x18001edc5  call    cs:__imp_GetLastError
0x18001edcb  lea     rdx, aCreatethread; "CreateThread"
0x18001edd2  jmp     short loc_18001ED63
```
