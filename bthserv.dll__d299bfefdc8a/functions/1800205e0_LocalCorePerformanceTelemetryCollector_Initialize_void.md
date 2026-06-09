# LocalCorePerformanceTelemetryCollector::Initialize(void)

- ea: `0x1800205e0`
- end: `0x18002078a`
- name: `?Initialize@LocalCorePerformanceTelemetryCollector@@AEAAXXZ`
- size: `426`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c9d8`

## callees

- `0x1800110fc`
- `0x18001140c`
- `0x1800205e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020678`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020678`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800206a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800206a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002068b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002068b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020666`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180020666`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002069f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002069f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020696`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180020696`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180020728`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x180020728`

## pseudocode

```c
void __fastcall LocalCorePerformanceTelemetryCollector::Initialize(struct _TP_TIMER **pv)
{
  char v2; // di
  bool v3; // dl
  PTP_TIMER ThreadpoolTimer; // rax
  int v5; // r8d
  struct _TP_TIMER *v6; // r14
  struct _TP_TIMER *v7; // rbp
  DWORD LastError; // ebx
  struct _FILETIME pftDueTime; // [rsp+A0h] [rbp+8h] BYREF

  v2 = 1;
  v3 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_si(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v3,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  ThreadpoolTimer = CreateThreadpoolTimer(
                      LocalCorePerformanceTelemetryCollector::CollectPerformanceTelemetryCallback,
                      pv,
                      0);
  v6 = pv[1];
  v7 = ThreadpoolTimer;
  if ( v6 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(v6, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v6, 1);
    CloseThreadpoolTimer(v6);
    SetLastError(LastError);
  }
  pv[1] = v7;
  if ( v7 )
  {
    pftDueTime = (struct _FILETIME)-36000000000LL;
    SetThreadpoolTimerEx(v7, &pftDueTime, 0x36EE80u, 0);
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_si(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v2,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        *((_QWORD *)WPP_GLOBAL_Control + 5));
  }
  else
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
      v2 = 0;
    if ( v2 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v2, v5, *((_QWORD *)WPP_GLOBAL_Control + 5));
    }
  }
}

```

## disassembly

```asm
0x1800205e0  push    rbx
0x1800205e2  push    rbp
0x1800205e3  push    rsi
0x1800205e4  push    rdi
0x1800205e5  push    r12
0x1800205e7  push    r13
0x1800205e9  push    r14
0x1800205eb  push    r15
0x1800205ed  sub     rsp, 58h
0x1800205f1  mov     rsi, rcx
0x1800205f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800205fb  lea     r15, WPP_GLOBAL_Control
0x180020602  mov     edi, 1
0x180020607  cmp     rcx, r15
0x18002060a  jz      short loc_180020617
0x18002060c  cmp     byte ptr [rcx+19h], 5
0x180020610  jb      short loc_180020617
0x180020612  mov     dl, dil
0x180020615  jmp     short loc_180020619
0x180020617  xor     dl, dl
0x180020619  lea     r12, WPP_RECORDER_INITIALIZED
0x180020620  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x180020627  lea     r13, WPP_5e83cdb759c63b5e0899db4d3690f4b2_Traceguids
0x18002062e  setnz   r8b
0x180020632  test    dl, dl
0x180020634  jnz     short loc_18002063B
0x180020636  test    r8b, r8b
0x180020639  jz      short loc_180020659
0x18002063b  mov     r9, [rcx+28h]
0x18002063f  mov     rcx, [rcx+10h]
0x180020643  mov     [rsp+98h+var_50], rsi
0x180020648  mov     [rsp+98h+var_60], r13
0x18002064d  mov     [rsp+98h+var_68], 0Ah
0x180020654  call    WPP_RECORDER_AND_TRACE_SF_si
0x180020659  xor     r8d, r8d; pcbe
0x18002065c  lea     rcx, ?CollectPerformanceTelemetryCallback@LocalCorePerformanceTelemetryCollector@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180020663  mov     rdx, rsi; pv
0x180020666  call    cs:__imp_CreateThreadpoolTimer
0x18002066c  mov     r14, [rsi+8]
0x180020670  mov     rbp, rax
0x180020673  test    r14, r14
0x180020676  jz      short loc_1800206AD
0x180020678  call    cs:__imp_GetLastError
0x18002067e  xor     r9d, r9d; msWindowLength
0x180020681  xor     r8d, r8d; msPeriod
0x180020684  xor     edx, edx; pftDueTime
0x180020686  mov     rcx, r14; pti
0x180020689  mov     ebx, eax
0x18002068b  call    cs:__imp_SetThreadpoolTimer
0x180020691  mov     edx, edi; fCancelPendingCallbacks
0x180020693  mov     rcx, r14; pti
0x180020696  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002069c  mov     rcx, r14; pti
0x18002069f  call    cs:__imp_CloseThreadpoolTimer
0x1800206a5  mov     ecx, ebx; dwErrCode
0x1800206a7  call    cs:__imp_SetLastError
0x1800206ad  mov     [rsi+8], rbp
0x1800206b1  test    rbp, rbp
0x1800206b4  jnz     short loc_180020702
0x1800206b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800206bd  cmp     rcx, r15
0x1800206c0  jz      short loc_1800206C8
0x1800206c2  cmp     byte ptr [rcx+19h], 3
0x1800206c6  jnb     short loc_1800206CB
0x1800206c8  xor     dil, dil
0x1800206cb  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1800206d2  setnz   r8b
0x1800206d6  test    dil, dil
0x1800206d9  jnz     short loc_1800206E4
0x1800206db  test    r8b, r8b
0x1800206de  jz      loc_180020779
0x1800206e4  mov     r9, [rcx+28h]
0x1800206e8  mov     dl, dil
0x1800206eb  mov     rcx, [rcx+10h]
0x1800206ef  mov     [rsp+98h+var_60], r13
0x1800206f4  mov     [rsp+98h+var_68], 0Bh
0x1800206fb  call    WPP_RECORDER_AND_TRACE_SF_s
0x180020700  jmp     short loc_180020779
0x180020702  mov     rax, 0FFFFFFF79E3B9800h
0x18002070c  lea     rdx, [rsp+98h+pftDueTime]; pftDueTime
0x180020714  xor     r9d, r9d; msWindowLength
0x180020717  mov     qword ptr [rsp+98h+pftDueTime.dwLowDateTime], rax
0x18002071f  mov     r8d, 36EE80h; msPeriod
0x180020725  mov     rcx, rbp; pti
0x180020728  call    cs:__imp_SetThreadpoolTimerEx
0x18002072e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020735  cmp     rcx, r15
0x180020738  jz      short loc_180020740
0x18002073a  cmp     byte ptr [rcx+19h], 5
0x18002073e  jnb     short loc_180020743
0x180020740  xor     dil, dil
0x180020743  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18002074a  setnz   r8b
0x18002074e  test    dil, dil
0x180020751  jnz     short loc_180020758
0x180020753  test    r8b, r8b
0x180020756  jz      short loc_180020779
0x180020758  mov     r9, [rcx+28h]
0x18002075c  mov     dl, dil
0x18002075f  mov     rcx, [rcx+10h]
0x180020763  mov     [rsp+98h+var_50], rsi
0x180020768  mov     [rsp+98h+var_60], r13
0x18002076d  mov     [rsp+98h+var_68], 0Ch
0x180020774  call    WPP_RECORDER_AND_TRACE_SF_si
0x180020779  add     rsp, 58h
0x18002077d  pop     r15
0x18002077f  pop     r14
0x180020781  pop     r13
0x180020783  pop     r12
0x180020785  pop     rdi
0x180020786  pop     rsi
0x180020787  pop     rbp
0x180020788  pop     rbx
0x180020789  retn
```
