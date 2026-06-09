# PcaFileTracerStart(unsigned __int64)

- ea: `0x180035760`
- end: `0x1800359cb`
- name: `?PcaFileTracerStart@@YAK_K@Z`
- size: `619`
- prototype: `__int64 __fastcall(struct _PCA_FILE_TRACER *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003af4`

## callees

- `0x180012920`
- `0x180035760`
- `0x18004e3bc`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003591e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003591e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800357a0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800357a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800359b6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180035908`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180035908`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180035840`
- `api-ms-win-eventing-controller-l1-1-0!ControlTraceW` at `0x180035840`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800358dc`
- `api-ms-win-eventing-controller-l1-1-0!EnableTraceEx2` at `0x1800358dc`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180035851`
- `api-ms-win-eventing-controller-l1-1-0!StartTraceW` at `0x180035851`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180035899`
- `api-ms-win-eventing-consumer-l1-1-0!OpenTraceW` at `0x180035899`

## string_xrefs

- `0x1800359ad`: `OpenTrace failed [%d]`
- `0x1800359c2`: `Failed to create trace thread [%d]`

## pseudocode

```c
__int64 __fastcall PcaFileTracerStart(struct _PCA_FILE_TRACER *a1)
{
  ULONG started; // eax
  ULONG Timeout; // ebx
  TRACEHANDLE v4; // rax
  HANDLE Thread; // rax
  const char *v7; // r9
  int v8; // r8d
  DWORD LastError; // eax
  int v10; // r8d
  const char *v11; // r9
  ULONGLONG MatchAnyKeyword; // [rsp+20h] [rbp-208h]
  _EVENT_TRACE_LOGFILEW Logfile; // [rsp+40h] [rbp-1E8h] BYREF

  memset_0(&Logfile, 0, sizeof(Logfile));
  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  PcapFileTracerReset(a1);
  memset_0(*((void **)a1 + 6), 0, 0x78u);
  **((_DWORD **)a1 + 6) = *((_DWORD *)a1 + 14);
  *(_OWORD *)(*((_QWORD *)a1 + 6) + 24LL) = xmmword_180103B10;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 40LL) = 1;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 44LL) = 0x20000;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 116LL) = 120;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 48LL) = 32;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 52LL) = 8;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 56LL) = 128;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 68LL) = 2;
  *(_DWORD *)(*((_QWORD *)a1 + 6) + 64LL) = 256;
  ControlTraceW(0, L"PCA file tracing session", *((PEVENT_TRACE_PROPERTIES *)a1 + 6), 1u);
  started = StartTraceW((PTRACEHANDLE)a1 + 8, L"PCA file tracing session", *((PEVENT_TRACE_PROPERTIES *)a1 + 6));
  Timeout = started;
  if ( started )
  {
    v7 = "Failed to start trace [%d]";
    v8 = 708;
LABEL_10:
    LODWORD(MatchAnyKeyword) = started;
    AslLogCallPrintf(1, (unsigned int)"PcaFileTracerStart", v8, (_DWORD)v7, MatchAnyKeyword);
    goto LABEL_7;
  }
  Logfile.LogFileMode = 268435712;
  Logfile.BufferCallback = (PEVENT_TRACE_BUFFER_CALLBACKW)PcapFileTracerProcessBufferCallback;
  Logfile.LoggerName = (LPWSTR)L"PCA file tracing session";
  Logfile.EventCallback = (PEVENT_CALLBACK)PcapFileTracerProcessEventRecordCallback;
  Logfile.Context = a1;
  v4 = OpenTraceW(&Logfile);
  *((_QWORD *)a1 + 9) = v4;
  if ( !v4 )
  {
    LastError = GetLastError();
    v10 = 725;
    v11 = "OpenTrace failed [%d]";
    goto LABEL_6;
  }
  started = EnableTraceEx2(*((_QWORD *)a1 + 8), &ProviderId, 1u, 4u, 0x10u, 0, Timeout, 0);
  Timeout = started;
  if ( started )
  {
    v7 = "Failed to enable file trace [%d]";
    v8 = 743;
    goto LABEL_10;
  }
  Thread = CreateThread(0, 0, PcapFileTracerThreadProc, *((LPVOID *)a1 + 9), 0, 0);
  *((_QWORD *)a1 + 5) = Thread;
  if ( !Thread )
  {
    LastError = GetLastError();
    v10 = 759;
    v11 = "Failed to create trace thread [%d]";
LABEL_6:
    Timeout = LastError;
    LODWORD(MatchAnyKeyword) = LastError;
    AslLogCallPrintf(1, (unsigned int)"PcaFileTracerStart", v10, (_DWORD)v11, MatchAnyKeyword);
    if ( !Timeout )
      goto LABEL_5;
LABEL_7:
    PcapFileTracerReset(a1);
  }
LABEL_5:
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  return Timeout;
}

```

## disassembly

```asm
0x180035760  mov     [rsp+arg_8], rbx
0x180035765  mov     [rsp+arg_10], rsi
0x18003576a  push    rdi
0x18003576b  push    r14
0x18003576d  push    r15
0x18003576f  sub     rsp, 210h
0x180035776  mov     rax, cs:__security_cookie
0x18003577d  xor     rax, rsp
0x180035780  mov     [rsp+228h+var_28], rax
0x180035788  mov     rdi, rcx
0x18003578b  xor     edx, edx; Val
0x18003578d  lea     rcx, [rsp+228h+Logfile]; void *
0x180035792  mov     r8d, 1C0h; Size
0x180035798  call    memset_0
0x18003579d  mov     rcx, rdi; lpCriticalSection
0x1800357a0  call    cs:__imp_EnterCriticalSection
0x1800357a6  mov     rcx, rdi; struct _PCA_FILE_TRACER *
0x1800357a9  call    ?PcapFileTracerReset@@YAXPEAU_PCA_FILE_TRACER@@@Z; PcapFileTracerReset(_PCA_FILE_TRACER *)
0x1800357ae  mov     rcx, [rdi+30h]; void *
0x1800357b2  mov     ebx, 78h ; 'x'
0x1800357b7  mov     r8d, ebx; Size
0x1800357ba  xor     edx, edx; Val
0x1800357bc  call    memset_0
0x1800357c1  mov     rcx, [rdi+30h]
0x1800357c5  lea     esi, [rbx-77h]
0x1800357c8  mov     eax, [rdi+38h]
0x1800357cb  lea     r15, InstanceName; "PCA file tracing session"
0x1800357d2  movups  xmm0, cs:xmmword_180103B10
0x1800357d9  mov     r9d, esi; ControlCode
0x1800357dc  mov     rdx, r15; InstanceName
0x1800357df  mov     [rcx], eax
0x1800357e1  xor     ecx, ecx; TraceHandle
0x1800357e3  mov     rax, [rdi+30h]
0x1800357e7  movdqu  xmmword ptr [rax+18h], xmm0
0x1800357ec  mov     rax, [rdi+30h]
0x1800357f0  mov     [rax+28h], esi
0x1800357f3  mov     rax, [rdi+30h]
0x1800357f7  mov     dword ptr [rax+2Ch], 20000h
0x1800357fe  mov     rax, [rdi+30h]
0x180035802  mov     [rax+74h], ebx
0x180035805  mov     rax, [rdi+30h]
0x180035809  mov     dword ptr [rax+30h], 20h ; ' '
0x180035810  mov     rax, [rdi+30h]
0x180035814  mov     dword ptr [rax+34h], 8
0x18003581b  mov     rax, [rdi+30h]
0x18003581f  mov     dword ptr [rax+38h], 80h
0x180035826  mov     rax, [rdi+30h]
0x18003582a  mov     dword ptr [rax+44h], 2
0x180035831  mov     rax, [rdi+30h]
0x180035835  mov     dword ptr [rax+40h], 100h
0x18003583c  mov     r8, [rdi+30h]; Properties
0x180035840  call    cs:__imp_ControlTraceW
0x180035846  mov     r8, [rdi+30h]; Properties
0x18003584a  lea     rcx, [rdi+40h]; TraceHandle
0x18003584e  mov     rdx, r15; InstanceName
0x180035851  call    cs:__imp_StartTraceW
0x180035857  mov     ebx, eax
0x180035859  test    eax, eax
0x18003585b  jnz     loc_180035971
0x180035861  lea     rax, ?PcapFileTracerProcessBufferCallback@@YAKPEAU_EVENT_TRACE_LOGFILEW@@@Z; PcapFileTracerProcessBufferCallback(_EVENT_TRACE_LOGFILEW *)
0x180035868  mov     dword ptr [rsp+228h+Logfile.1Ch], 10000100h
0x180035870  mov     [rsp+228h+Logfile.BufferCallback], rax
0x180035878  lea     rcx, [rsp+228h+Logfile]; Logfile
0x18003587d  lea     rax, ?PcapFileTracerProcessEventRecordCallback@@YAXPEAU_EVENT_RECORD@@@Z; PcapFileTracerProcessEventRecordCallback(_EVENT_RECORD *)
0x180035884  mov     [rsp+228h+Logfile.LoggerName], r15
0x180035889  mov     qword ptr [rsp+228h+Logfile.1A8h], rax
0x180035891  mov     [rsp+228h+Logfile.Context], rdi
0x180035899  call    cs:__imp_OpenTraceW
0x18003589f  mov     [rdi+48h], rax
0x1800358a3  test    rax, rax
0x1800358a6  jz      loc_1800359A1
0x1800358ac  mov     rcx, [rdi+40h]; TraceHandle
0x1800358b0  lea     rdx, ProviderId; ProviderId
0x1800358b7  mov     [rsp+228h+EnableParameters], 0; EnableParameters
0x1800358c0  mov     r9b, 4; Level
0x1800358c3  mov     [rsp+228h+Timeout], ebx; Timeout
0x1800358c7  mov     r8d, esi; ControlCode
0x1800358ca  mov     [rsp+228h+MatchAllKeyword], 0; MatchAllKeyword
0x1800358d3  mov     [rsp+228h+MatchAnyKeyword], 10h; MatchAnyKeyword
0x1800358dc  call    cs:__imp_EnableTraceEx2
0x1800358e2  mov     ebx, eax
0x1800358e4  test    eax, eax
0x1800358e6  jnz     loc_180035980
0x1800358ec  mov     r9, [rdi+48h]; lpParameter
0x1800358f0  lea     r8, ?PcapFileTracerThreadProc@@YAKPEAX@Z; lpStartAddress
0x1800358f7  mov     [rsp+228h+MatchAllKeyword], 0; lpThreadId
0x180035900  xor     edx, edx; dwStackSize
0x180035902  xor     ecx, ecx; lpThreadAttributes
0x180035904  mov     dword ptr [rsp+228h+MatchAnyKeyword], eax; dwCreationFlags
0x180035908  call    cs:__imp_CreateThread
0x18003590e  mov     [rdi+28h], rax
0x180035912  test    rax, rax
0x180035915  jz      loc_1800359B6
0x18003591b  mov     rcx, rdi; lpCriticalSection
0x18003591e  call    cs:__imp_LeaveCriticalSection
0x180035924  mov     eax, ebx
0x180035926  mov     rcx, [rsp+228h+var_28]
0x18003592e  xor     rcx, rsp; StackCookie
0x180035931  call    __security_check_cookie
0x180035936  lea     r11, [rsp+228h+var_18]
0x18003593e  mov     rbx, [r11+28h]
0x180035942  mov     rsi, [r11+30h]
0x180035946  mov     rsp, r11
0x180035949  pop     r15
0x18003594b  pop     r14
0x18003594d  pop     rdi
0x18003594e  retn
0x18003594f  lea     rdx, aPcafiletracers; "PcaFileTracerStart"
0x180035956  mov     ebx, eax
0x180035958  mov     ecx, esi
0x18003595a  mov     dword ptr [rsp+228h+MatchAnyKeyword], eax
0x18003595e  call    AslLogCallPrintf
0x180035963  test    ebx, ebx
0x180035965  jz      short loc_18003591B
0x180035967  mov     rcx, rdi; struct _PCA_FILE_TRACER *
0x18003596a  call    ?PcapFileTracerReset@@YAXPEAU_PCA_FILE_TRACER@@@Z; PcapFileTracerReset(_PCA_FILE_TRACER *)
0x18003596f  jmp     short loc_18003591B
0x180035971  lea     r9, aFailedToStartT_1; "Failed to start trace [%d]"
0x180035978  mov     r8d, 2C4h
0x18003597e  jmp     short loc_18003598D
0x180035980  lea     r9, aFailedToEnable; "Failed to enable file trace [%d]"
0x180035987  mov     r8d, 2E7h
0x18003598d  lea     rdx, aPcafiletracers; "PcaFileTracerStart"
0x180035994  mov     dword ptr [rsp+228h+MatchAnyKeyword], eax
0x180035998  mov     ecx, esi
0x18003599a  call    AslLogCallPrintf
0x18003599f  jmp     short loc_180035967
0x1800359a1  call    cs:__imp_GetLastError
0x1800359a7  mov     r8d, 2D5h
0x1800359ad  lea     r9, aOpentraceFaile; "OpenTrace failed [%d]"
0x1800359b4  jmp     short loc_18003594F
0x1800359b6  call    cs:__imp_GetLastError
0x1800359bc  mov     r8d, 2F7h
0x1800359c2  lea     r9, aFailedToCreate_13; "Failed to create trace thread [%d]"
0x1800359c9  jmp     short loc_18003594F
```
