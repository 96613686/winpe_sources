# ProcessWaitCallback

- ea: `0x1400046a0`
- end: `0x1400048d8`
- name: `ProcessWaitCallback`
- size: `568`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x14000116c`
- `0x14000125c`
- `0x140003b3c`
- `0x140003e54`
- `0x1400046a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400046e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400046e4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004704`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004704`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400046ba`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1400046ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400047d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400047f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400048bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400047f7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400048bf`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000472e`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14000472e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x140004711`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x140004711`

## string_xrefs

- `0x140004782`: `GameInputService instance died`
- `0x140004848`: `GameInputService watchdog runaway`

## pseudocode

```c
__int64 __fastcall ProcessWaitCallback(PVOID Parameter)
{
  unsigned int v1; // edi
  __int64 i; // rbx
  void *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rsi
  __int64 v10; // rax
  __int64 *v11; // rcx
  const char *v12; // [rsp+40h] [rbp-18h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp+38h] BYREF
  DWORD v14; // [rsp+98h] [rbp+40h] BYREF
  const char *v15; // [rsp+A0h] [rbp+48h] BYREF
  const char *v16; // [rsp+A8h] [rbp+50h] BYREF

  v1 = (unsigned int)Parameter;
  EnterCriticalSection(&CriticalSection);
  for ( i = qword_14000E6F0; (__int64 *)i != &qword_14000E6F0; i = *(_QWORD *)i )
  {
    if ( *(_DWORD *)(i + 16) == v1 )
    {
      if ( i && WaitForSingleObject(*(HANDLE *)(i + 104), 0) == 258 )
      {
        if ( v1 == WTSGetActiveConsoleSessionId() )
        {
          v4 = *(void **)(i + 120);
          ExitCode = 0;
          if ( !GetExitCodeProcess(v4, &ExitCode) )
            ExitCode = -2147418113;
          if ( (unsigned int)dword_14000E000 > 2
            && (qword_14000E010 & 0x800) != 0
            && (qword_14000E018 & 0x800) == qword_14000E018 )
          {
            v14 = ExitCode;
            v16 = "GameInputService instance died";
            LODWORD(v15) = 274;
            v12 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
              qword_14000E018,
              (int)byte_14000AE9B,
              v5,
              v6,
              (__int64 **)&v12,
              (__int64)&v15,
              (__int64 **)&v16,
              (__int64)&v14);
          }
          CloseHandle(*(HANDLE *)(i + 128));
          CloseHandle(*(HANDLE *)(i + 120));
          v9 = *(_QWORD *)(i + 136);
          *(_QWORD *)(i + 128) = 0;
          *(_QWORD *)(i + 120) = 0;
          if ( !v9 || GetTickCount64() - v9 > 0x1388 )
            *(_DWORD *)(i + 144) = 0;
          if ( *(_DWORD *)(i + 144) <= 5u )
          {
            if ( (int)InitializeSession((HINSTANCE)v1, (_QWORD *)i) >= 0 )
            {
              ++*(_DWORD *)(i + 144);
              *(_QWORD *)(i + 136) = GetTickCount64();
              break;
            }
          }
          else if ( (unsigned int)dword_14000E000 > 2
                 && (qword_14000E010 & 0x800) != 0
                 && (qword_14000E018 & 0x800) == qword_14000E018 )
          {
            v14 = 294;
            v15 = "GameInputService watchdog runaway";
            v16 = "onecore\\xbox\\gameinput\\published\\svc\\session.cpp";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              qword_14000E018,
              (int)qword_14000AE60,
              v7,
              v8,
              (__int64 **)&v16,
              (__int64)&v14,
              (__int64 **)&v15);
          }
        }
        v10 = *(_QWORD *)i;
        if ( *(_QWORD *)(*(_QWORD *)i + 8LL) != i || (v11 = *(__int64 **)(i + 8), *v11 != i) )
          __fastfail(3u);
        *v11 = v10;
        *(_QWORD *)(v10 + 8) = v11;
        DeleteSession((HANDLE *)i);
      }
      break;
    }
  }
  LeaveCriticalSection(&CriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1400046a0  push    rbp
0x1400046a2  push    rbx
0x1400046a3  push    rsi
0x1400046a4  push    rdi
0x1400046a5  push    r12
0x1400046a7  push    r15
0x1400046a9  mov     rbp, rsp
0x1400046ac  sub     rsp, 58h
0x1400046b0  mov     rdi, rcx
0x1400046b3  lea     rcx, CriticalSection; lpCriticalSection
0x1400046ba  call    cs:__imp_EnterCriticalSection
0x1400046c0  mov     rbx, cs:qword_14000E6F0
0x1400046c7  lea     rax, qword_14000E6F0
0x1400046ce  jmp     short loc_1400046D8
0x1400046d0  cmp     [rbx+10h], edi
0x1400046d3  jz      short loc_1400046F9
0x1400046d5  mov     rbx, [rbx]
0x1400046d8  cmp     rbx, rax
0x1400046db  jnz     short loc_1400046D0
0x1400046dd  lea     rcx, CriticalSection; lpCriticalSection
0x1400046e4  call    cs:__imp_LeaveCriticalSection
0x1400046ea  xor     eax, eax
0x1400046ec  add     rsp, 58h
0x1400046f0  pop     r15
0x1400046f2  pop     r12
0x1400046f4  pop     rdi
0x1400046f5  pop     rsi
0x1400046f6  pop     rbx
0x1400046f7  pop     rbp
0x1400046f8  retn
0x1400046f9  test    rbx, rbx
0x1400046fc  jz      short loc_1400046DD
0x1400046fe  mov     rcx, [rbx+68h]; hHandle
0x140004702  xor     edx, edx; dwMilliseconds
0x140004704  call    cs:__imp_WaitForSingleObject
0x14000470a  cmp     eax, 102h
0x14000470f  jnz     short loc_1400046DD
0x140004711  call    cs:__imp_WTSGetActiveConsoleSessionId
0x140004717  cmp     edi, eax
0x140004719  jnz     loc_140004885
0x14000471f  mov     rcx, [rbx+78h]; hProcess
0x140004723  lea     rdx, [rbp+ExitCode]; lpExitCode
0x140004727  mov     [rbp+ExitCode], 0
0x14000472e  call    cs:__imp_GetExitCodeProcess
0x140004734  test    eax, eax
0x140004736  jnz     short loc_14000473F
0x140004738  mov     [rbp+ExitCode], 8000FFFFh
0x14000473f  mov     eax, cs:dword_14000E000
0x140004745  lea     r12, aOnecoreXboxGam_3; "onecore\\xbox\\gameinput\\published\\sv"...
0x14000474c  mov     r15d, 800h
0x140004752  cmp     eax, 2
0x140004755  jbe     short loc_1400047C1
0x140004757  mov     rcx, cs:qword_14000E018
0x14000475e  mov     rax, cs:qword_14000E010
0x140004765  test    r15, rax
0x140004768  jz      short loc_1400047C1
0x14000476a  mov     rax, rcx
0x14000476d  and     rax, r15
0x140004770  cmp     rax, rcx
0x140004773  jnz     short loc_1400047C1
0x140004775  mov     eax, [rbp+ExitCode]
0x140004778  lea     rdx, byte_14000AE9B
0x14000477f  mov     [rbp+arg_8], eax
0x140004782  lea     rax, aGameinputservi; "GameInputService instance died"
0x140004789  mov     [rbp+arg_18], rax
0x14000478d  lea     rax, [rbp+arg_8]
0x140004791  mov     [rsp+58h+var_20], rax
0x140004796  lea     rax, [rbp+arg_18]
0x14000479a  mov     [rsp+58h+var_28], rax
0x14000479f  lea     rax, [rbp+arg_10]
0x1400047a3  mov     [rsp+58h+var_30], rax
0x1400047a8  lea     rax, [rbp+var_18]
0x1400047ac  mov     [rsp+58h+var_38], rax
0x1400047b1  mov     dword ptr [rbp+arg_10], 112h
0x1400047b8  mov     [rbp+var_18], r12
0x1400047bc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@34@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1400047c1  mov     rcx, [rbx+80h]; hObject
0x1400047c8  call    cs:__imp_CloseHandle
0x1400047ce  mov     rcx, [rbx+78h]; hObject
0x1400047d2  call    cs:__imp_CloseHandle
0x1400047d8  mov     rsi, [rbx+88h]
0x1400047df  mov     qword ptr [rbx+80h], 0
0x1400047ea  mov     qword ptr [rbx+78h], 0
0x1400047f2  test    rsi, rsi
0x1400047f5  jz      short loc_140004808
0x1400047f7  call    cs:__imp_GetTickCount64
0x1400047fd  sub     rax, rsi
0x140004800  cmp     rax, 1388h
0x140004806  jbe     short loc_140004812
0x140004808  mov     dword ptr [rbx+90h], 0
0x140004812  cmp     dword ptr [rbx+90h], 5
0x140004819  jbe     loc_1400048AB
0x14000481f  mov     eax, cs:dword_14000E000
0x140004825  cmp     eax, 2
0x140004828  jbe     short loc_140004885
0x14000482a  mov     rcx, cs:qword_14000E018
0x140004831  mov     rax, cs:qword_14000E010
0x140004838  test    r15, rax
0x14000483b  jz      short loc_140004885
0x14000483d  mov     rax, rcx
0x140004840  and     rax, r15
0x140004843  cmp     rax, rcx
0x140004846  jnz     short loc_140004885
0x140004848  lea     rax, aGameinputservi_1; "GameInputService watchdog runaway"
0x14000484f  mov     [rbp+arg_8], 126h
0x140004856  mov     [rbp+arg_10], rax
0x14000485a  lea     rdx, qword_14000AE60
0x140004861  lea     rax, [rbp+arg_10]
0x140004865  mov     [rbp+arg_18], r12
0x140004869  mov     [rsp+58h+var_28], rax
0x14000486e  lea     rax, [rbp+arg_8]
0x140004872  mov     [rsp+58h+var_30], rax
0x140004877  lea     rax, [rbp+arg_18]
0x14000487b  mov     [rsp+58h+var_38], rax
0x140004880  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_GameInputEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_GameInputEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140004885  mov     rax, [rbx]
0x140004888  cmp     [rax+8], rbx
0x14000488c  jnz     short loc_1400048D1
0x14000488e  mov     rcx, [rbx+8]
0x140004892  cmp     [rcx], rbx
0x140004895  jnz     short loc_1400048D1
0x140004897  mov     [rcx], rax
0x14000489a  mov     [rax+8], rcx
0x14000489e  mov     rcx, rbx
0x1400048a1  call    DeleteSession
0x1400048a6  jmp     loc_1400046DD
0x1400048ab  mov     rdx, rbx
0x1400048ae  mov     ecx, edi
0x1400048b0  call    InitializeSession
0x1400048b5  test    eax, eax
0x1400048b7  js      short loc_140004885
0x1400048b9  inc     dword ptr [rbx+90h]
0x1400048bf  call    cs:__imp_GetTickCount64
0x1400048c5  mov     [rbx+88h], rax
0x1400048cc  jmp     loc_1400046DD
0x1400048d1  mov     ecx, 3
0x1400048d6  int     29h; Win8: RtlFailFast(ecx)
```
