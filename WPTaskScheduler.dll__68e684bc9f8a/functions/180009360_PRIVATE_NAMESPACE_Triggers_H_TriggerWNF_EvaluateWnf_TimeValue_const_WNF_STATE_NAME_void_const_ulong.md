# PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::EvaluateWnf(TimeValue const &,_WNF_STATE_NAME *,void * const,ulong)

- ea: `0x180009360`
- end: `0x18000972b`
- name: `?EvaluateWnf@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@EEAAHAEBVTimeValue@@PEAU_WNF_STATE_NAME@@QEAXK@Z`
- size: `971`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *this, const struct TimeValue *, struct _WNF_STATE_NAME *, _DWORD *, unsigned int Size)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180009360`
- `0x180017370`
- `0x180019544`
- `0x180019a9c`
- `0x18001bbd4`
- `0x18001cb04`
- `0x1800205f4`
- `0x180020bf6`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009618`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000968b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009618`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000968b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000962a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000962a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009385`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009385`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800093bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009484`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800093bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180009484`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::EvaluateWnf(
        PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *this,
        const struct TimeValue *a2,
        struct _WNF_STATE_NAME *a3,
        _DWORD *a4,
        unsigned int Size)
{
  unsigned int v5; // edi
  __int64 v9; // rcx
  __int64 v10; // rax
  int v11; // ecx
  PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *v13; // rdx
  const void *v14; // rcx
  DWORD dwLowDateTime; // eax
  const void *v16; // rcx
  int v17; // r9d
  unsigned __int8 *v18; // r8
  signed __int64 v19; // rax
  signed __int64 v20; // rtt
  CScheduleMgr *v21; // rcx
  __int64 v22; // rax
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp-28h] BYREF

  v5 = *((_DWORD *)this + 46);
  EnterCriticalSection((LPCRITICAL_SECTION)this + 3);
  v10 = *((_QWORD *)this + 22);
  if ( v10 && *(_DWORD *)(v10 + 40) != 4 && (*((_BYTE *)this + 236) & 1) == 0 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
    return v5;
  }
  if ( a3 && *a3 == *((_QWORD *)this + 26) )
  {
    v13 = (PRIVATE_NAMESPACE_Triggers_H::TriggerWNF *)*((unsigned int *)this + 54);
    if ( (_DWORD)v13 == 1 )
    {
      if ( (*((_BYTE *)this + 236) & 4) != 0 )
      {
        if ( Size >= 8 && a4 )
        {
          dwLowDateTime = (*a4 >> 1) & 1;
          goto LABEL_32;
        }
        goto LABEL_21;
      }
      if ( Size != *((_DWORD *)this + 55) )
      {
LABEL_21:
        dwLowDateTime = 0;
LABEL_32:
        v13 = this;
        *((_DWORD *)this + 48) = dwLowDateTime;
        goto LABEL_33;
      }
      v16 = (const void *)*((_QWORD *)this + 28);
      if ( v16 && memcmp_0(v16, a4, Size) )
      {
        dwLowDateTime = 0;
        goto LABEL_32;
      }
    }
    else
    {
      if ( (_DWORD)v13 != 2 )
      {
        if ( (unsigned int)((_DWORD)v13 - 3) <= 3 )
        {
          v17 = *((_DWORD *)this + 55);
          v18 = (unsigned __int8 *)*((_QWORD *)this + 28);
          pftDueTime.dwLowDateTime = 0;
          PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::CompareValue(
            v9,
            (int)v13,
            v18,
            v17,
            (unsigned __int8 *)a4,
            Size,
            (BOOL *)&pftDueTime);
          dwLowDateTime = pftDueTime.dwLowDateTime;
          *((_DWORD *)this + 48) = pftDueTime.dwLowDateTime;
        }
        else
        {
          *((_DWORD *)this + 48) = 1;
          dwLowDateTime = 1;
        }
LABEL_33:
        if ( !*((_DWORD *)this + 58) )
        {
          v5 |= dwLowDateTime;
          goto LABEL_35;
        }
        if ( dwLowDateTime )
        {
          _m_prefetchw((char *)this + 264);
          v19 = *((_QWORD *)this + 33);
          do
          {
            v20 = v19;
            v19 = _InterlockedCompareExchange64((volatile signed __int64 *)this + 33, v19 & 1, v19);
          }
          while ( v20 != v19 );
          if ( !v19 )
          {
            if ( (unsigned int)PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::IsInDelayedState(this) )
            {
              if ( !*((_DWORD *)this + 46) )
              {
                CScheduleMgr::ResetLastChangeStamp(v21, *((struct CSchedule **)this + 22), *a3);
                goto LABEL_35;
              }
            }
            else if ( !*((_DWORD *)this + 46) )
            {
              CScheduleMgr::ResetLastChangeStamp(v21, *((struct CSchedule **)this + 22), *a3);
              v22 = -600000000LL * *((unsigned int *)this + 58);
              pftDueTime.dwLowDateTime = -600000000 * *((_DWORD *)this + 58);
              pftDueTime.dwHighDateTime = HIDWORD(v22);
              SetThreadpoolTimer(*((PTP_TIMER *)this + 32), &pftDueTime, 0, 0);
              goto LABEL_35;
            }
            if ( (byte_180030D09 & 0x40) != 0 )
              McTemplateU0j_EventWriteTransfer(v21, NotResettingTimestamp, *((_QWORD *)this + 22) + 16LL);
            goto LABEL_35;
          }
          SetThreadpoolTimer(*((PTP_TIMER *)this + 32), 0, 0, 0);
          WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 32), 1);
          v5 = 1;
        }
        else if ( (unsigned int)PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::IsInDelayedState(this) )
        {
          goto LABEL_35;
        }
        _InterlockedExchange64((volatile __int64 *)this + 33, 0);
LABEL_35:
        *((_DWORD *)this + 46) = v5;
        if ( *((_QWORD *)this + 34) )
        {
          LOBYTE(v13) = *((_DWORD *)this + 48) != 0;
          PubSebLevelEvent(*((_QWORD *)this + 34), v13);
        }
        goto LABEL_6;
      }
      if ( (*((_BYTE *)this + 236) & 4) != 0 )
      {
        if ( Size >= 8 && a4 )
        {
          dwLowDateTime = (*a4 & 2) == 0;
          goto LABEL_32;
        }
      }
      else if ( Size == *((_DWORD *)this + 55) )
      {
        v14 = (const void *)*((_QWORD *)this + 28);
        if ( v14 )
        {
          if ( a4 && !memcmp_0(v14, a4, Size) )
            goto LABEL_21;
        }
        else if ( !a4 )
        {
          goto LABEL_21;
        }
      }
    }
    dwLowDateTime = 1;
    goto LABEL_32;
  }
  v5 = *((_DWORD *)this + 46);
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)this + 3);
  if ( (*((_BYTE *)this + 236) & 1) != 0 )
    v5 = *((_DWORD *)this + 48);
  if ( a3 && *a3 == *((_QWORD *)this + 26) )
  {
    if ( (byte_180030D05 & 2) != 0 )
      McTemplateU0jqqq_EventWriteTransfer(
        v11,
        (unsigned int)WnfTriggerEvaluateWithState,
        *((_QWORD *)this + 22) + 16,
        a3->Data[0],
        a3->Data[1],
        v5);
  }
  else if ( (byte_180030D05 & 2) != 0 )
  {
    McTemplateU0jqqq_EventWriteTransfer(
      *((_DWORD *)this + 53),
      (unsigned int)WnfTriggerEvaluate,
      *((_QWORD *)this + 22) + 16,
      *((_DWORD *)this + 52),
      *((_DWORD *)this + 53),
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180009360  mov     [rsp+arg_8], rbx
0x180009365  mov     [rsp+arg_18], rbp
0x18000936a  push    rsi
0x18000936b  push    rdi
0x18000936c  push    r14
0x18000936e  sub     rsp, 50h
0x180009372  mov     edi, [rcx+0B8h]
0x180009378  mov     rbx, rcx
0x18000937b  add     rcx, 78h ; 'x'; lpCriticalSection
0x18000937f  mov     r14, r9
0x180009382  mov     rsi, r8
0x180009385  call    cs:__imp_EnterCriticalSection
0x18000938b  mov     rax, [rbx+0B0h]
0x180009392  test    rax, rax
0x180009395  jz      short loc_1800093A1
0x180009397  cmp     dword ptr [rax+28h], 4
0x18000939b  jnz     loc_180009473
0x1800093a1  test    rsi, rsi
0x1800093a4  jz      short loc_1800093B2
0x1800093a6  mov     rax, [rsi]
0x1800093a9  cmp     rax, [rbx+0D0h]
0x1800093b0  jz      short loc_18000942A
0x1800093b2  mov     edi, [rbx+0B8h]
0x1800093b8  lea     rcx, [rbx+78h]; lpCriticalSection
0x1800093bc  call    cs:__imp_LeaveCriticalSection
0x1800093c2  test    byte ptr [rbx+0ECh], 1
0x1800093c9  jz      short loc_1800093D1
0x1800093cb  mov     edi, [rbx+0C0h]
0x1800093d1  test    rsi, rsi
0x1800093d4  jz      short loc_1800093E2
0x1800093d6  mov     rax, [rsi]
0x1800093d9  cmp     rax, [rbx+0D0h]
0x1800093e0  jz      short loc_180009407
0x1800093e2  test    cs:byte_180030D05, 2
0x1800093e9  jnz     loc_1800096FA
0x1800093ef  mov     rbx, [rsp+68h+arg_8]
0x1800093f4  mov     eax, edi
0x1800093f6  mov     rbp, [rsp+68h+arg_18]
0x1800093fe  add     rsp, 50h
0x180009402  pop     r14
0x180009404  pop     rdi
0x180009405  pop     rsi
0x180009406  retn
0x180009407  test    cs:byte_180030D05, 2
0x18000940e  jz      short loc_1800093EF
0x180009410  mov     eax, [rsi+4]
0x180009413  lea     rdx, WnfTriggerEvaluateWithState
0x18000941a  mov     r9d, [rsi]
0x18000941d  mov     [rsp+68h+var_40], edi
0x180009421  mov     dword ptr [rsp+68h+var_48], eax
0x180009425  jmp     loc_180009716
0x18000942a  mov     edx, [rbx+0D8h]
0x180009430  cmp     edx, 1
0x180009433  jz      short loc_18000948F
0x180009435  cmp     edx, 2
0x180009438  jnz     loc_18000957D
0x18000943e  test    byte ptr [rbx+0ECh], 4
0x180009445  jnz     loc_1800094D1
0x18000944b  mov     eax, dword ptr [rsp+68h+Size]
0x180009452  cmp     eax, [rbx+0DCh]
0x180009458  jnz     short loc_1800094CA
0x18000945a  mov     rcx, [rbx+0E0h]; Buf1
0x180009461  test    rcx, rcx
0x180009464  jnz     loc_18000955C
0x18000946a  test    r14, r14
0x18000946d  jnz     short loc_1800094CA
0x18000946f  xor     eax, eax
0x180009471  jmp     short loc_1800094EA
0x180009473  test    byte ptr [rbx+0ECh], 1
0x18000947a  jnz     loc_1800093A1
0x180009480  lea     rcx, [rbx+78h]; lpCriticalSection
0x180009484  call    cs:__imp_LeaveCriticalSection
0x18000948a  jmp     loc_1800093EF
0x18000948f  test    byte ptr [rbx+0ECh], 4
0x180009496  jnz     loc_180009537
0x18000949c  mov     eax, dword ptr [rsp+68h+Size]
0x1800094a3  cmp     eax, [rbx+0DCh]
0x1800094a9  jnz     short loc_18000946F
0x1800094ab  mov     rcx, [rbx+0E0h]; Buf1
0x1800094b2  test    rcx, rcx
0x1800094b5  jz      short loc_1800094CA
0x1800094b7  mov     r8d, eax; Size
0x1800094ba  mov     rdx, r14; Buf2
0x1800094bd  call    memcmp_0
0x1800094c2  test    eax, eax
0x1800094c4  jnz     loc_180009558
0x1800094ca  mov     eax, 1
0x1800094cf  jmp     short loc_1800094EA
0x1800094d1  cmp     dword ptr [rsp+68h+Size], 8
0x1800094d9  jb      short loc_1800094CA
0x1800094db  test    r14, r14
0x1800094de  jz      short loc_1800094CA
0x1800094e0  mov     eax, [r14]
0x1800094e3  shr     eax, 1
0x1800094e5  not     eax
0x1800094e7  and     eax, 1
0x1800094ea  mov     ecx, 0C0h
0x1800094ef  mov     rdx, rbx
0x1800094f2  mov     [rcx+rbx], eax
0x1800094f5  cmp     dword ptr [rbx+0E8h], 0
0x1800094fc  ja      loc_1800095DD
0x180009502  or      edi, eax
0x180009504  mov     [rbx+0B8h], edi
0x18000950a  mov     eax, [rbx+114h]
0x180009510  or      eax, [rbx+110h]
0x180009516  jz      loc_1800093B8
0x18000951c  cmp     dword ptr [rbx+0C0h], 0
0x180009523  mov     rcx, [rbx+110h]
0x18000952a  setnz   dl
0x18000952d  call    PubSebLevelEvent
0x180009532  jmp     loc_1800093B8
0x180009537  cmp     dword ptr [rsp+68h+Size], 8
0x18000953f  jb      loc_18000946F
0x180009545  test    r14, r14
0x180009548  jz      loc_18000946F
0x18000954e  mov     eax, [r14]
0x180009551  shr     eax, 1
0x180009553  and     eax, 1
0x180009556  jmp     short loc_1800094EA
0x180009558  xor     eax, eax
0x18000955a  jmp     short loc_1800094EA
0x18000955c  test    r14, r14
0x18000955f  jz      loc_1800094CA
0x180009565  mov     r8, rax; Size
0x180009568  mov     rdx, r14; Buf2
0x18000956b  call    memcmp_0
0x180009570  test    eax, eax
0x180009572  jnz     loc_1800094CA
0x180009578  jmp     loc_18000946F
0x18000957d  lea     eax, [rdx-3]
0x180009580  cmp     eax, 3
0x180009583  jbe     short loc_180009599
0x180009585  mov     dword ptr [rbx+0C0h], 1
0x18000958f  mov     eax, 1
0x180009594  jmp     loc_1800094F5
0x180009599  mov     r9d, [rbx+0DCh]
0x1800095a0  lea     rax, [rsp+68h+pftDueTime]
0x1800095a5  mov     r8, [rbx+0E0h]
0x1800095ac  mov     [rsp+68h+var_38], rax
0x1800095b1  mov     eax, dword ptr [rsp+68h+Size]
0x1800095b8  mov     [rsp+68h+var_40], eax
0x1800095bc  mov     [rsp+68h+var_48], r14
0x1800095c1  mov     [rsp+68h+pftDueTime.dwLowDateTime], 0
0x1800095c9  call    ?CompareValue@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@AEBAJW4_TASK_STATE_COMPARISON@@PEAEK1KAEAH@Z; PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::CompareValue(_TASK_STATE_COMPARISON,uchar *,ulong,uchar *,ulong,int &)
0x1800095ce  mov     eax, [rsp+68h+pftDueTime.dwLowDateTime]
0x1800095d2  mov     [rbx+0C0h], eax
0x1800095d8  jmp     loc_1800094F5
0x1800095dd  test    eax, eax
0x1800095df  jz      loc_1800096DC
0x1800095e5  prefetchw byte ptr [rbx+108h]
0x1800095ec  mov     rax, [rbx+108h]
0x1800095f3  mov     rcx, rax
0x1800095f6  and     ecx, 1
0x1800095f9  lock cmpxchg [rbx+108h], rcx
0x180009602  jnz     short loc_1800095F3
0x180009604  test    rax, rax
0x180009607  jz      short loc_18000963A
0x180009609  mov     rcx, [rbx+100h]; pti
0x180009610  xor     r9d, r9d; msWindowLength
0x180009613  xor     r8d, r8d; msPeriod
0x180009616  xor     edx, edx; pftDueTime
0x180009618  call    cs:__imp_SetThreadpoolTimer
0x18000961e  mov     rcx, [rbx+100h]; pti
0x180009625  mov     edx, 1; fCancelPendingCallbacks
0x18000962a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009630  mov     edi, 1
0x180009635  jmp     loc_1800096EC
0x18000963a  mov     rcx, rbx; this
0x18000963d  call    ?IsInDelayedState@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@AEAAHXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::IsInDelayedState(void)
0x180009642  test    eax, eax
0x180009644  jnz     short loc_180009696
0x180009646  cmp     [rbx+0B8h], eax
0x18000964c  jnz     short loc_1800096B3
0x18000964e  mov     r8, [rsi]; struct _WNF_STATE_NAME
0x180009651  mov     rdx, [rbx+0B0h]; struct CSchedule *
0x180009658  call    ?ResetLastChangeStamp@CScheduleMgr@@QEAAJPEAVCSchedule@@U_WNF_STATE_NAME@@@Z; CScheduleMgr::ResetLastChangeStamp(CSchedule *,_WNF_STATE_NAME)
0x18000965d  mov     eax, [rbx+0E8h]
0x180009663  lea     rdx, [rsp+68h+pftDueTime]; pftDueTime
0x180009668  imul    rax, 0FFFFFFFFDC3CBA00h
0x18000966f  xor     r9d, r9d; msWindowLength
0x180009672  xor     r8d, r8d; msPeriod
0x180009675  mov     rcx, rax
0x180009678  mov     [rsp+68h+pftDueTime.dwLowDateTime], eax
0x18000967c  shr     rcx, 20h
0x180009680  mov     [rsp+68h+pftDueTime.dwHighDateTime], ecx
0x180009684  mov     rcx, [rbx+100h]; pti
0x18000968b  call    cs:__imp_SetThreadpoolTimer
0x180009691  jmp     loc_180009504
0x180009696  cmp     dword ptr [rbx+0B8h], 0
0x18000969d  jnz     short loc_1800096B3
0x18000969f  mov     r8, [rsi]; struct _WNF_STATE_NAME
0x1800096a2  mov     rdx, [rbx+0B0h]; struct CSchedule *
0x1800096a9  call    ?ResetLastChangeStamp@CScheduleMgr@@QEAAJPEAVCSchedule@@U_WNF_STATE_NAME@@@Z; CScheduleMgr::ResetLastChangeStamp(CSchedule *,_WNF_STATE_NAME)
0x1800096ae  jmp     loc_180009504
0x1800096b3  test    cs:byte_180030D09, 40h
0x1800096ba  jz      loc_180009504
0x1800096c0  mov     r8, [rbx+0B0h]
0x1800096c7  lea     rdx, NotResettingTimestamp
0x1800096ce  add     r8, 10h
0x1800096d2  call    McTemplateU0j_EventWriteTransfer
0x1800096d7  jmp     loc_180009504
0x1800096dc  mov     rcx, rbx; this
0x1800096df  call    ?IsInDelayedState@TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@AEAAHXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::IsInDelayedState(void)
0x1800096e4  test    eax, eax
0x1800096e6  jnz     loc_180009504
0x1800096ec  xor     eax, eax
0x1800096ee  xchg    rax, [rbx+108h]
0x1800096f5  jmp     loc_180009504
0x1800096fa  mov     ecx, [rbx+0D4h]
0x180009700  lea     rdx, WnfTriggerEvaluate
0x180009707  mov     r9d, [rbx+0D0h]
0x18000970e  mov     [rsp+68h+var_40], edi
0x180009712  mov     dword ptr [rsp+68h+var_48], ecx
0x180009716  mov     r8, [rbx+0B0h]
0x18000971d  add     r8, 10h
0x180009721  call    McTemplateU0jqqq_EventWriteTransfer
0x180009726  jmp     loc_1800093EF
```
