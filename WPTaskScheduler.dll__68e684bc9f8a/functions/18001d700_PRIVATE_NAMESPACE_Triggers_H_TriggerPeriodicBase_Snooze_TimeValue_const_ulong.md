# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Snooze(TimeValue const &,ulong)

- ea: `0x18001d700`
- end: `0x18001d8f5`
- name: `?Snooze@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@EEAAJAEBVTimeValue@@K@Z`
- size: `501`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this, SYSTEMTIME *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001260`
- `0x18000ea40`
- `0x18001d700`
- `0x18001fbac`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d86b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d86b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d747`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d8c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d747`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d8c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d757`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d757`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d764`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001d764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d87d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d87d`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::Snooze(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        SYSTEMTIME *a2,
        unsigned int a3)
{
  __int64 v4; // rbx
  struct _TP_TIMER *v5; // rcx
  unsigned int v6; // edi
  SYSTEMTIME v8; // xmm0
  unsigned int v9; // eax
  __int64 v10; // rbx
  SYSTEMTIME v11; // xmm0
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  __int64 v16; // r8
  struct _TP_TIMER *ThreadpoolTimer; // rax
  signed int LastError; // eax
  __int64 v20; // rbx
  SYSTEMTIME v21; // xmm1
  __int128 v22; // xmm0
  SYSTEMTIME SystemTime; // [rsp+30h] [rbp-39h] BYREF
  SYSTEMTIME v24; // [rsp+40h] [rbp-29h]
  __int128 v25; // [rsp+50h] [rbp-19h]
  SYSTEMTIME v26; // [rsp+60h] [rbp-9h] BYREF
  __int64 v27; // [rsp+70h] [rbp+7h]
  __int64 v28; // [rsp+78h] [rbp+Fh]
  int v29; // [rsp+80h] [rbp+17h]
  int v30; // [rsp+84h] [rbp+1Bh]
  int v31; // [rsp+88h] [rbp+1Fh]
  struct _FILETIME pftDueTime; // [rsp+90h] [rbp+27h] BYREF

  v4 = a3;
  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 55);
  v6 = 0;
  if ( v5 )
  {
    SetThreadpoolTimer(v5, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 55), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 55));
    *((_QWORD *)this + 55) = 0;
    *((_DWORD *)this + 28) = 0;
  }
  if ( !(_DWORD)v4 )
    return v6;
  v8 = *a2;
  v24 = a2[1];
  LODWORD(v25) = *(_DWORD *)&a2[2].wYear;
  v9 = *(_DWORD *)&a2[2].wDayOfWeek;
  v10 = 600000000 * v4;
  SystemTime = v8;
  *(_QWORD *)((char *)&v25 + 4) = v9 | 0x100000000LL;
  TimeValue::AdvanceNs100(&SystemTime, v10, 0);
  if ( !*((_DWORD *)this + 122) )
    goto LABEL_9;
  v11 = (SYSTEMTIME)*((_OWORD *)this + 28);
  v12 = *((_QWORD *)this + 24);
  v27 = *((_QWORD *)this + 58);
  v28 = *((_QWORD *)this + 59);
  v29 = *((_DWORD *)this + 120);
  v30 = *((_DWORD *)this + 121);
  v26 = v11;
  v31 = 1;
  TimeValue::AdvanceNs100(&v26, v12, 0);
  if ( !(unsigned int)operator>=((__int64)&SystemTime, (__int64)&v26, v13, v14) )
  {
LABEL_9:
    ThreadpoolTimer = CreateThreadpoolTimer(
                        CScheduleMgr::BaseSnoozeCallback,
                        *((PVOID *)this + 22),
                        &ThreadpoolCallBackEnvironment);
    *((_QWORD *)this + 55) = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v20 = -v10;
      v21 = v24;
      *(SYSTEMTIME *)((char *)this + 72) = SystemTime;
      v22 = v25;
      pftDueTime.dwHighDateTime = HIDWORD(v20);
      *(SYSTEMTIME *)((char *)this + 88) = v21;
      pftDueTime.dwLowDateTime = v20;
      *(_OWORD *)((char *)this + 104) = v22;
      SetThreadpoolTimer(ThreadpoolTimer, &pftDueTime, 0, 0);
    }
    else
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
    return v6;
  }
  if ( (byte_180030D01 & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(v15, TriggerSnoozePastIntervalError, v16, 1, &pftDueTime);
  return 2194604299LL;
}

```

## disassembly

```asm
0x18001d700  mov     [rsp-8+arg_8], rbx
0x18001d705  mov     [rsp-8+arg_18], rsi
0x18001d70a  push    rbp
0x18001d70b  push    rdi
0x18001d70c  push    r14
0x18001d70e  lea     rbp, [rsp-47h]
0x18001d713  sub     rsp, 0B0h
0x18001d71a  mov     rax, cs:__security_cookie
0x18001d721  xor     rax, rsp
0x18001d724  mov     [rbp+57h+var_20], rax
0x18001d728  mov     rsi, rcx
0x18001d72b  mov     ebx, r8d
0x18001d72e  mov     rcx, [rcx+1B8h]; pti
0x18001d735  xor     edi, edi
0x18001d737  mov     r14, rdx
0x18001d73a  test    rcx, rcx
0x18001d73d  jz      short loc_18001D774
0x18001d73f  xor     r9d, r9d; msWindowLength
0x18001d742  xor     r8d, r8d; msPeriod
0x18001d745  xor     edx, edx; pftDueTime
0x18001d747  call    cs:__imp_SetThreadpoolTimer
0x18001d74d  mov     rcx, [rsi+1B8h]; pti
0x18001d754  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18001d757  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001d75d  mov     rcx, [rsi+1B8h]; pti
0x18001d764  call    cs:__imp_CloseThreadpoolTimer
0x18001d76a  mov     [rsi+1B8h], rdi
0x18001d771  mov     [rsi+70h], edi
0x18001d774  test    ebx, ebx
0x18001d776  jz      loc_18001D8CF
0x18001d77c  mov     rax, [r14+10h]
0x18001d780  lea     rcx, [rbp+57h+SystemTime]; lpSystemTime
0x18001d784  movups  xmm0, xmmword ptr [r14]
0x18001d788  mov     qword ptr [rbp+57h+var_80], rax
0x18001d78c  xor     r8d, r8d; int
0x18001d78f  mov     rax, [r14+18h]
0x18001d793  mov     qword ptr [rbp+57h+var_80+8], rax
0x18001d797  mov     eax, [r14+20h]
0x18001d79b  mov     dword ptr [rbp+57h+var_70], eax
0x18001d79e  mov     eax, [r14+24h]
0x18001d7a2  imul    rbx, 23C34600h
0x18001d7a9  movdqu  xmmword ptr [rbp+57h+SystemTime.wYear], xmm0
0x18001d7ae  mov     dword ptr [rbp+57h+var_70+4], eax
0x18001d7b1  mov     rdx, rbx; __int64
0x18001d7b4  mov     dword ptr [rbp+57h+var_70+8], 1
0x18001d7bb  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18001d7c0  cmp     [rsi+1E8h], edi
0x18001d7c6  jz      loc_18001D856
0x18001d7cc  mov     rax, [rsi+1D0h]
0x18001d7d3  lea     rcx, [rbp+57h+var_60]; lpSystemTime
0x18001d7d7  movups  xmm0, xmmword ptr [rsi+1C0h]
0x18001d7de  mov     rdx, [rsi+0C0h]; __int64
0x18001d7e5  xor     r8d, r8d; int
0x18001d7e8  mov     [rbp+57h+var_50], rax
0x18001d7ec  mov     rax, [rsi+1D8h]
0x18001d7f3  mov     [rbp+57h+var_48], rax
0x18001d7f7  mov     eax, [rsi+1E0h]
0x18001d7fd  mov     [rbp+57h+var_40], eax
0x18001d800  mov     eax, [rsi+1E4h]
0x18001d806  mov     [rbp+57h+var_3C], eax
0x18001d809  movdqu  xmmword ptr [rbp+57h+var_60.wYear], xmm0
0x18001d80e  mov     [rbp+57h+var_38], 1
0x18001d815  call    ?AdvanceNs100@TimeValue@@QEAAX_JH@Z; TimeValue::AdvanceNs100(__int64,int)
0x18001d81a  lea     rdx, [rbp+57h+var_60]
0x18001d81e  lea     rcx, [rbp+57h+SystemTime]
0x18001d822  call    ??P@YAHAEBVTimeValue@@0@Z; operator>=(TimeValue const &,TimeValue const &)
0x18001d827  test    eax, eax
0x18001d829  jz      short loc_18001D856
0x18001d82b  test    cs:byte_180030D01, 10h
0x18001d832  jz      short loc_18001D84F
0x18001d834  lea     rax, [rbp+57h+pftDueTime]
0x18001d838  mov     r9d, 1
0x18001d83e  lea     rdx, TriggerSnoozePastIntervalError
0x18001d845  mov     [rsp+0C0h+var_A0], rax
0x18001d84a  call    McGenEventWrite_EventWriteTransfer
0x18001d84f  mov     eax, 82CF010Bh
0x18001d854  jmp     short loc_18001D8D1
0x18001d856  mov     rdx, [rsi+0B0h]; pv
0x18001d85d  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001d864  lea     rcx, ?BaseSnoozeCallback@CScheduleMgr@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d86b  call    cs:__imp_CreateThreadpoolTimer
0x18001d871  mov     [rsi+1B8h], rax
0x18001d878  test    rax, rax
0x18001d87b  jnz     short loc_18001D894
0x18001d87d  call    cs:__imp_GetLastError
0x18001d883  mov     edi, eax
0x18001d885  test    eax, eax
0x18001d887  jle     short loc_18001D8CF
0x18001d889  movzx   edi, ax
0x18001d88c  or      edi, 80070000h
0x18001d892  jmp     short loc_18001D8CF
0x18001d894  movups  xmm0, xmmword ptr [rbp+57h+SystemTime.wYear]
0x18001d898  neg     rbx
0x18001d89b  xor     r9d, r9d; msWindowLength
0x18001d89e  movups  xmm1, [rbp+57h+var_80]
0x18001d8a2  mov     rcx, rbx
0x18001d8a5  xor     r8d, r8d; msPeriod
0x18001d8a8  movups  xmmword ptr [rsi+48h], xmm0
0x18001d8ac  shr     rcx, 20h
0x18001d8b0  lea     rdx, [rbp+57h+pftDueTime]; pftDueTime
0x18001d8b4  movups  xmm0, [rbp+57h+var_70]
0x18001d8b8  mov     [rbp+57h+pftDueTime.dwHighDateTime], ecx
0x18001d8bb  mov     rcx, rax; pti
0x18001d8be  movups  xmmword ptr [rsi+58h], xmm1
0x18001d8c2  mov     [rbp+57h+pftDueTime.dwLowDateTime], ebx
0x18001d8c5  movups  xmmword ptr [rsi+68h], xmm0
0x18001d8c9  call    cs:__imp_SetThreadpoolTimer
0x18001d8cf  mov     eax, edi
0x18001d8d1  mov     rcx, [rbp+57h+var_20]
0x18001d8d5  xor     rcx, rsp; StackCookie
0x18001d8d8  call    __security_check_cookie
0x18001d8dd  lea     r11, [rsp+0C0h+var_10]
0x18001d8e5  mov     rbx, [r11+28h]
0x18001d8e9  mov     rsi, [r11+38h]
0x18001d8ed  mov     rsp, r11
0x18001d8f0  pop     r14
0x18001d8f2  pop     rdi
0x18001d8f3  pop     rbp
0x18001d8f4  retn
```
