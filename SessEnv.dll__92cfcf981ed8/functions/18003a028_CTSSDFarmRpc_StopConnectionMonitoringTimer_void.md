# CTSSDFarmRpc::StopConnectionMonitoringTimer(void)

- ea: `0x18003a028`
- end: `0x18003a0b4`
- name: `?StopConnectionMonitoringTimer@CTSSDFarmRpc@@AEAAJXZ`
- size: `140`
- prototype: `__int64 __fastcall(CTSSDFarmRpc *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180039bb0`
- `0x180039f90`
- `0x18003a460`

## callees

- `0x180003f30`
- `0x18003a028`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a075`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003a075`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a040`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003a040`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a057`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003a057`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a06b`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a06b`

## string_xrefs

- `0x18003a098`: `DeleteTimerQueueTimer failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CTSSDFarmRpc::StopConnectionMonitoringTimer(CTSSDFarmRpc *this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rbx
  signed int v3; // esi
  void *v4; // rbp
  signed int LastError; // eax

  v1 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 1608);
  v3 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1608));
  v4 = (void *)*((_QWORD *)this + 200);
  *((_QWORD *)this + 200) = 0;
  LeaveCriticalSection(v1);
  if ( v4 && !DeleteTimerQueueTimer(0, v4, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 < 0 )
      _DbgPrintMessage(8, "DeleteTimerQueueTimer failed: 0x%x in %s", v3, "CTSSDFarmRpc::StopConnectionMonitoringTimer");
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18003a028  push    rbx
0x18003a02a  push    rbp
0x18003a02b  push    rsi
0x18003a02c  push    rdi
0x18003a02d  sub     rsp, 28h
0x18003a031  lea     rbx, [rcx+648h]
0x18003a038  mov     rdi, rcx
0x18003a03b  mov     rcx, rbx; lpCriticalSection
0x18003a03e  xor     esi, esi
0x18003a040  call    cs:__imp_EnterCriticalSection
0x18003a046  mov     rbp, [rdi+640h]
0x18003a04d  mov     rcx, rbx; lpCriticalSection
0x18003a050  mov     [rdi+640h], rsi
0x18003a057  call    cs:__imp_LeaveCriticalSection
0x18003a05d  test    rbp, rbp
0x18003a060  jz      short loc_18003A0A9
0x18003a062  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003a066  mov     rdx, rbp; Timer
0x18003a069  xor     ecx, ecx; TimerQueue
0x18003a06b  call    cs:__imp_DeleteTimerQueueTimer
0x18003a071  test    eax, eax
0x18003a073  jnz     short loc_18003A0A9
0x18003a075  call    cs:__imp_GetLastError
0x18003a07b  mov     esi, eax
0x18003a07d  test    eax, eax
0x18003a07f  jle     short loc_18003A08A
0x18003a081  movzx   esi, ax
0x18003a084  or      esi, 80070000h
0x18003a08a  test    esi, esi
0x18003a08c  jns     short loc_18003A0A9
0x18003a08e  lea     r9, aCtssdfarmrpcSt; "CTSSDFarmRpc::StopConnectionMonitoringT"...
0x18003a095  mov     r8d, esi
0x18003a098  lea     rdx, aDeletetimerque_2; "DeleteTimerQueueTimer failed: 0x%x in %"...
0x18003a09f  mov     ecx, 8; int
0x18003a0a4  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18003a0a9  mov     eax, esi
0x18003a0ab  add     rsp, 28h
0x18003a0af  pop     rdi
0x18003a0b0  pop     rsi
0x18003a0b1  pop     rbp
0x18003a0b2  pop     rbx
0x18003a0b3  retn
```
