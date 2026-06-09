# AiSvcpInitializeGpCallback(void)

- ea: `0x1800037d8`
- end: `0x180003939`
- name: `?AiSvcpInitializeGpCallback@@YAKXZ`
- size: `353`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180003940`
- `0x180003c80`

## callees

- `0x1800037d8`
- `0x180004870`
- `0x1800049a8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003841`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003896`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800038e7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000382f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000382f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003921`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003921`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800038d5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800038d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800038c3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800038c3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180003884`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180003884`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 AiSvcpInitializeGpCallback(void)
{
  DWORD v0; // ebx
  DWORD LastError; // eax
  __int64 v2; // r8
  _QWORD *v3; // rcx
  __int64 v4; // rdx
  struct _TP_WAIT *ThreadpoolWait; // rax
  struct _TP_TIMER *ThreadpoolTimer; // rax
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  v0 = 0;
  pftDueTime = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      53,
      WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids,
      "AiSvcpInitializeGpCallback");
  AiSvcpGroupPolicyChangeEvent = CreateEventW(0, 0, 0, 0);
  if ( AiSvcpGroupPolicyChangeEvent )
  {
    ThreadpoolWait = CreateThreadpoolWait((PTP_WAIT_CALLBACK)AiSvcpGroupPolicyChangedCallback, 0, 0);
    AiSvcpGroupPolicyWaitObject = ThreadpoolWait;
    if ( ThreadpoolWait )
    {
      SetThreadpoolWait(ThreadpoolWait, AiSvcpGroupPolicyChangeEvent, 0);
      ThreadpoolTimer = CreateThreadpoolTimer(AiSvcpConfigureAppID, 0, 0);
      AiSvcpGpNotifyTimer = ThreadpoolTimer;
      if ( ThreadpoolTimer )
      {
        pftDueTime = (struct _FILETIME)-10000000LL;
        SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
        return v0;
      }
      LastError = GetLastError();
      v0 = LastError;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v4 = 56;
        goto LABEL_8;
      }
    }
    else
    {
      LastError = GetLastError();
      v0 = LastError;
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      {
        v4 = 55;
        goto LABEL_8;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v0 = LastError;
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    {
      v4 = 54;
LABEL_8:
      WPP_SF_d(v3[2], v4, v2, LastError);
    }
  }
  return v0;
}

```

## disassembly

```asm
0x1800037d8  mov     [rsp+arg_8], rbx
0x1800037dd  mov     [rsp+arg_10], rsi
0x1800037e2  push    rdi
0x1800037e3  sub     rsp, 20h
0x1800037e7  xor     ebx, ebx
0x1800037e9  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rbx
0x1800037ee  mov     rcx, cs:WPP_GLOBAL_Control
0x1800037f5  lea     rsi, WPP_GLOBAL_Control
0x1800037fc  mov     edi, 400h
0x180003801  cmp     rcx, rsi
0x180003804  jz      short loc_180003825
0x180003806  test    [rcx+1Ch], edi
0x180003809  jz      short loc_180003825
0x18000380b  mov     rcx, [rcx+10h]
0x18000380f  lea     edx, [rbx+35h]
0x180003812  lea     r9, aAisvcpinitiali; "AiSvcpInitializeGpCallback"
0x180003819  lea     r8, WPP_c500ddf3cb7e33b2855b0d42471a40ca_Traceguids
0x180003820  call    WPP_SF_s
0x180003825  xor     r9d, r9d; lpName
0x180003828  xor     r8d, r8d; bInitialState
0x18000382b  xor     edx, edx; bManualReset
0x18000382d  xor     ecx, ecx; lpEventAttributes
0x18000382f  call    cs:__imp_CreateEventW
0x180003835  mov     cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA, rax; void * AiSvcpGroupPolicyChangeEvent
0x18000383c  test    rax, rax
0x18000383f  jnz     short loc_180003878
0x180003841  call    cs:__imp_GetLastError
0x180003847  mov     ebx, eax
0x180003849  mov     rcx, cs:WPP_GLOBAL_Control
0x180003850  cmp     rcx, rsi
0x180003853  jz      loc_180003927
0x180003859  test    [rcx+1Ch], edi
0x18000385c  jz      loc_180003927
0x180003862  mov     edx, 36h ; '6'
0x180003867  mov     rcx, [rcx+10h]
0x18000386b  mov     r9d, eax
0x18000386e  call    WPP_SF_d
0x180003873  jmp     loc_180003927
0x180003878  xor     r8d, r8d; pcbe
0x18000387b  lea     rcx, ?AiSvcpGroupPolicyChangedCallback@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180003882  xor     edx, edx; pv
0x180003884  call    cs:__imp_CreateThreadpoolWait
0x18000388a  mov     cs:?AiSvcpGroupPolicyWaitObject@@3PEAU_TP_WAIT@@EA, rax; _TP_WAIT * AiSvcpGroupPolicyWaitObject
0x180003891  test    rax, rax
0x180003894  jnz     short loc_1800038B6
0x180003896  call    cs:__imp_GetLastError
0x18000389c  mov     ebx, eax
0x18000389e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038a5  cmp     rcx, rsi
0x1800038a8  jz      short loc_180003927
0x1800038aa  test    [rcx+1Ch], edi
0x1800038ad  jz      short loc_180003927
0x1800038af  mov     edx, 37h ; '7'
0x1800038b4  jmp     short loc_180003867
0x1800038b6  mov     rdx, cs:?AiSvcpGroupPolicyChangeEvent@@3PEAXEA; h
0x1800038bd  xor     r8d, r8d; pftTimeout
0x1800038c0  mov     rcx, rax; pwa
0x1800038c3  call    cs:__imp_SetThreadpoolWait
0x1800038c9  xor     r8d, r8d; pcbe
0x1800038cc  lea     rcx, ?AiSvcpConfigureAppID@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800038d3  xor     edx, edx; pv
0x1800038d5  call    cs:__imp_CreateThreadpoolTimer
0x1800038db  mov     cs:?AiSvcpGpNotifyTimer@@3PEAU_TP_TIMER@@EA, rax; _TP_TIMER * AiSvcpGpNotifyTimer
0x1800038e2  test    rax, rax
0x1800038e5  jnz     short loc_18000390A
0x1800038e7  call    cs:__imp_GetLastError
0x1800038ed  mov     ebx, eax
0x1800038ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800038f6  cmp     rcx, rsi
0x1800038f9  jz      short loc_180003927
0x1800038fb  test    [rcx+1Ch], edi
0x1800038fe  jz      short loc_180003927
0x180003900  mov     edx, 38h ; '8'
0x180003905  jmp     loc_180003867
0x18000390a  xor     r9d, r9d; msWindowLength
0x18000390d  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], 0FFFFFFFFFF676980h
0x180003916  xor     r8d, r8d; msPeriod
0x180003919  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18000391e  mov     rcx, rax; pti
0x180003921  call    cs:__imp_SetThreadpoolTimer
0x180003927  mov     rsi, [rsp+28h+arg_10]
0x18000392c  mov     eax, ebx
0x18000392e  mov     rbx, [rsp+28h+arg_8]
0x180003933  add     rsp, 20h
0x180003937  pop     rdi
0x180003938  retn
```
