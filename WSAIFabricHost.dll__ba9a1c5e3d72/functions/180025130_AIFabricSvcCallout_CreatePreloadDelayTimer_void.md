# AIFabricSvcCallout::CreatePreloadDelayTimer(void)

- ea: `0x180025130`
- end: `0x18002523e`
- name: `?CreatePreloadDelayTimer@AIFabricSvcCallout@@AEAAXXZ`
- size: `270`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180024c50`

## callees

- `0x18001899c`
- `0x180025130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002518c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002518c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800251be`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800251be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800251ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025207`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800251ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025207`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800251b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025210`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800251b6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025210`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025153`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180025153`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002519f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800251e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800251f9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002519f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800251e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800251f9`

## string_xrefs

- `0x18002522b`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\aifabricsvccallout.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall AIFabricSvcCallout::CreatePreloadDelayTimer(PTP_TIMER *pv)
{
  const char *v2; // r9
  struct _TP_TIMER *ThreadpoolTimer; // r14
  PTP_TIMER *v4; // rdi
  struct _TP_TIMER *v5; // rsi
  DWORD LastError; // ebx
  const char *v7; // r9
  __int64 *v8; // rdx
  __int64 v9; // [rsp+0h] [rbp-48h] BYREF
  struct _TP_TIMER *v10; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+10h] BYREF

  ThreadpoolTimer = CreateThreadpoolTimer(AIFabricSvcCallout::OnPreloadDelayTimeout, pv, 0);
  v10 = ThreadpoolTimer;
  if ( !ThreadpoolTimer )
  {
    try
    {
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xDA,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricsvccallout.cpp",
        v2);
    }
    catch ( ... )
    {
      v8 = &v9;
      wil::details::in1diag3::Log_CaughtException(
        (wil::details::in1diag3 *)v8[9],
        (void *)0xE0,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\aifabricsvccallout.cpp",
        v7);
      return;
    }
  }
  v4 = pv + 5;
  v5 = pv[5];
  pv[5] = 0;
  if ( pv + 5 == &v10 )
  {
    LastError = GetLastError();
    SetThreadpoolTimer(ThreadpoolTimer, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(ThreadpoolTimer, 1);
    CloseThreadpoolTimer(ThreadpoolTimer);
    SetLastError(LastError);
  }
  else
  {
    *v4 = ThreadpoolTimer;
  }
  pftDueTime = (struct _FILETIME)(-10000000LL * *((unsigned int *)pv + 6));
  SetThreadpoolTimer(*v4, &pftDueTime, 0, 0);
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
  }
}

```

## disassembly

```asm
0x180025130  mov     [rsp+arg_0], rbx
0x180025135  mov     [rsp+arg_10], rsi
0x18002513a  push    rdi
0x18002513b  push    r14
0x18002513d  push    r15
0x18002513f  sub     rsp, 30h
0x180025143  mov     r15, rcx
0x180025146  xor     r8d, r8d; pcbe
0x180025149  mov     rdx, rcx; pv
0x18002514c  lea     rcx, ?OnPreloadDelayTimeout@AIFabricSvcCallout@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180025153  call    cs:__imp_CreateThreadpoolTimer
0x180025159  mov     r14, rax
0x18002515c  mov     [rsp+48h+var_28], rax
0x180025161  mov     rcx, [rsp+48h]; this
0x180025166  test    rax, rax
0x180025169  jz      loc_18002522B
0x18002516f  lea     rdi, [r15+28h]
0x180025173  mov     rsi, [rdi]
0x180025176  mov     qword ptr [rdi], 0
0x18002517d  lea     rax, [rsp+48h+var_28]
0x180025182  cmp     rdi, rax
0x180025185  jz      short loc_18002518C
0x180025187  mov     [rdi], r14
0x18002518a  jmp     short loc_1800251C4
0x18002518c  call    cs:__imp_GetLastError
0x180025192  mov     ebx, eax
0x180025194  xor     r9d, r9d; msWindowLength
0x180025197  xor     r8d, r8d; msPeriod
0x18002519a  xor     edx, edx; pftDueTime
0x18002519c  mov     rcx, r14; pti
0x18002519f  call    cs:__imp_SetThreadpoolTimer
0x1800251a5  mov     edx, 1; fCancelPendingCallbacks
0x1800251aa  mov     rcx, r14; pti
0x1800251ad  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800251b3  mov     rcx, r14; pti
0x1800251b6  call    cs:__imp_CloseThreadpoolTimer
0x1800251bc  mov     ecx, ebx; dwErrCode
0x1800251be  call    cs:__imp_SetLastError
0x1800251c4  mov     eax, [r15+18h]
0x1800251c8  imul    rdx, rax, 0FFFFFFFFFF676980h
0x1800251cf  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rdx
0x1800251d4  xor     r9d, r9d; msWindowLength
0x1800251d7  xor     r8d, r8d; msPeriod
0x1800251da  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800251df  mov     rcx, [rdi]; pti
0x1800251e2  call    cs:__imp_SetThreadpoolTimer
0x1800251e8  nop
0x1800251e9  test    rsi, rsi
0x1800251ec  jz      short loc_180025217
0x1800251ee  xor     r9d, r9d; msWindowLength
0x1800251f1  xor     r8d, r8d; msPeriod
0x1800251f4  xor     edx, edx; pftDueTime
0x1800251f6  mov     rcx, rsi; pti
0x1800251f9  call    cs:__imp_SetThreadpoolTimer
0x1800251ff  mov     edx, 1; fCancelPendingCallbacks
0x180025204  mov     rcx, rsi; pti
0x180025207  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002520d  mov     rcx, rsi; pti
0x180025210  call    cs:__imp_CloseThreadpoolTimer
0x180025216  nop
0x180025217  mov     rbx, [rsp+48h+arg_0]
0x18002521c  mov     rsi, [rsp+48h+arg_10]
0x180025221  add     rsp, 30h
0x180025225  pop     r15
0x180025227  pop     r14
0x180025229  pop     rdi
0x18002522a  retn
0x18002522b  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\search\\com"...
0x180025232  mov     edx, 0DAh; void *
0x180025237  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
