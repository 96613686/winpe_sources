# ServiceWatchdog::Start(ServiceWatchdog::StartReason,_FILETIME)

- ea: `0x18001edb0`
- end: `0x18001eebb`
- name: `?Start@ServiceWatchdog@@QEAAJW4StartReason@1@U_FILETIME@@@Z`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180016d3c`
- `0x18001cc50`
- `0x18001d224`

## callees

- `0x18001edb0`
- `0x1800226dc`
- `0x180022754`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edc7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001edc7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eea3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001eea3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ee16`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001ee0c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001ee0c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001ee6c`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001ee6c`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001ee43`
- `ZTrace_Maps!ZTraceReportOrigination` at `0x18001ee43`

## string_xrefs

- `0x18001ee3a`: `ServiceWatchdog::Start`
- `0x18001ee63`: `ServiceWatchdog::Start`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServiceWatchdog::Start(__int64 a1, int a2, __int64 a3)
{
  signed int LastError; // eax
  unsigned int v7; // eax
  unsigned int v8; // ebx
  int v9; // eax
  int v10; // r8d

  EnterCriticalSection((LPCRITICAL_SECTION)a1);
  if ( *(_DWORD *)(a1 + 140) )
    __int2c();
  *(_DWORD *)(a1 + 152) = 600000;
  *(_DWORD *)(a1 + 140) = a2;
  *(_DWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 160) = a3;
  *(_BYTE *)(a1 + 156) = 0;
  if ( QueryUnbiasedInterruptTime((PULONGLONG)(a1 + 144)) )
  {
    v9 = TimerQueue::Initialize((TimerQueue *)(a1 + 40));
    if ( v9 >= 0 )
    {
      v9 = TimerQueue::QueueTimer(
             (HANDLE *)(a1 + 40),
             lambda_45e146e8638d082e1a494d639387f109_::_lambda_invoker_cdecl_,
             (void *)a1,
             0xEA60u,
             0xEA60u);
      if ( v9 >= 0 )
      {
        v8 = 0;
        goto LABEL_16;
      }
      v10 = 65;
    }
    else
    {
      v10 = 59;
    }
    v7 = ZTraceReportPropagation(v9, "ServiceWatchdog::Start", v10, (const void *)a1);
  }
  else
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    v7 = ZTraceReportOrigination(LastError, "ServiceWatchdog::Start", 57, (const void *)a1);
  }
  v8 = v7;
LABEL_16:
  LeaveCriticalSection((LPCRITICAL_SECTION)a1);
  return v8;
}

```

## disassembly

```asm
0x18001edb0  mov     [rsp+arg_8], rbx
0x18001edb5  mov     [rsp+arg_10], rsi
0x18001edba  push    rdi
0x18001edbb  sub     rsp, 30h
0x18001edbf  mov     rbx, r8
0x18001edc2  mov     esi, edx
0x18001edc4  mov     rdi, rcx
0x18001edc7  call    cs:__imp_EnterCriticalSection
0x18001edcd  mov     [rsp+38h+arg_0], rdi
0x18001edd2  cmp     dword ptr [rdi+8Ch], 0
0x18001edd9  jz      short loc_18001EDDD
0x18001eddb  int     2Ch; Windows NT - assertion failure
0x18001eddd  mov     dword ptr [rdi+98h], 927C0h
0x18001ede7  mov     [rdi+8Ch], esi
0x18001eded  mov     dword ptr [rdi+88h], 0
0x18001edf7  mov     [rdi+0A0h], rbx
0x18001edfe  mov     byte ptr [rdi+9Ch], 0
0x18001ee05  lea     rcx, [rdi+90h]; UnbiasedTime
0x18001ee0c  call    cs:__imp_QueryUnbiasedInterruptTime
0x18001ee12  test    eax, eax
0x18001ee14  jnz     short loc_18001EE4D
0x18001ee16  call    cs:__imp_GetLastError
0x18001ee1c  test    eax, eax
0x18001ee1e  jz      short loc_18001EE2C
0x18001ee20  jle     short loc_18001EE31
0x18001ee22  movzx   eax, ax
0x18001ee25  or      eax, 80070000h
0x18001ee2a  jmp     short loc_18001EE31
0x18001ee2c  mov     eax, 80390004h
0x18001ee31  mov     r9, rdi
0x18001ee34  mov     r8d, 39h ; '9'
0x18001ee3a  lea     rdx, aServicewatchdo_1; "ServiceWatchdog::Start"
0x18001ee41  mov     ecx, eax
0x18001ee43  call    cs:__imp_?ZTraceReportOrigination@@YAJHPEBDHPEBX@Z; ZTraceReportOrigination(int,char const *,int,void const *)
0x18001ee49  mov     ebx, eax
0x18001ee4b  jmp     short loc_18001EEA0
0x18001ee4d  lea     rcx, [rdi+28h]; this
0x18001ee51  call    ?Initialize@TimerQueue@@QEAAJXZ; TimerQueue::Initialize(void)
0x18001ee56  test    eax, eax
0x18001ee58  jns     short loc_18001EE74
0x18001ee5a  mov     r8d, 3Bh ; ';'
0x18001ee60  mov     r9, rdi
0x18001ee63  lea     rdx, aServicewatchdo_1; "ServiceWatchdog::Start"
0x18001ee6a  mov     ecx, eax
0x18001ee6c  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001ee72  jmp     short loc_18001EE49
0x18001ee74  mov     r9d, 0EA60h; unsigned int
0x18001ee7a  mov     [rsp+38h+var_18], r9d; unsigned int
0x18001ee7f  mov     r8, rdi; void *
0x18001ee82  lea     rdx, _lambda_45e146e8638d082e1a494d639387f109____lambda_invoker_cdecl_; void (*)(void *)
0x18001ee89  lea     rcx, [rdi+28h]; this
0x18001ee8d  call    ?QueueTimer@TimerQueue@@QEAAJP6AXPEAX@Z0KK@Z; TimerQueue::QueueTimer(void (*)(void *),void *,ulong,ulong)
0x18001ee92  test    eax, eax
0x18001ee94  jns     short loc_18001EE9E
0x18001ee96  mov     r8d, 41h ; 'A'
0x18001ee9c  jmp     short loc_18001EE60
0x18001ee9e  xor     ebx, ebx
0x18001eea0  mov     rcx, rdi; lpCriticalSection
0x18001eea3  call    cs:__imp_LeaveCriticalSection
0x18001eea9  mov     eax, ebx
0x18001eeab  mov     rbx, [rsp+38h+arg_8]
0x18001eeb0  mov     rsi, [rsp+38h+arg_10]
0x18001eeb5  add     rsp, 30h
0x18001eeb9  pop     rdi
0x18001eeba  retn
```
