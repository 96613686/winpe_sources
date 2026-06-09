# WaaS2::ComTimeout::~ComTimeout(void)

- ea: `0x180047228`
- end: `0x18004728f`
- name: `??1ComTimeout@WaaS2@@QEAA@XZ`
- size: `103`
- prototype: `void(WaaS2::ComTimeout *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18004e470`
- `0x18006dbd7`
- `0x18006dbe9`
- `0x18006dbfb`

## callees

- `0x18002cbc4`
- `0x180047228`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180047266`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180047266`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180047258`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180047258`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180047241`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180047241`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004724f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004724f`

## pseudocode

```c
void __fastcall WaaS2::ComTimeout::~ComTimeout(PTP_TIMER *this)
{
  struct _TP_TIMER *v2; // rcx
  HRESULT v3; // eax
  int v4; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *this;
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*this, 1);
    CloseThreadpoolTimer(*this);
  }
  if ( *((_BYTE *)this + 12) )
  {
    v3 = CoDisableCallCancellation(0);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\internal\\enduser\\inc\\WaaSDeviceFeatureEvaluator2.h",
        (const char *)(unsigned int)v3,
        v4);
  }
}

```

## disassembly

```asm
0x180047228  push    rbx; int
0x18004722a  sub     rsp, 20h
0x18004722e  mov     rbx, rcx
0x180047231  mov     rcx, [rcx]; pti
0x180047234  test    rcx, rcx
0x180047237  jz      short loc_18004725E
0x180047239  xor     r9d, r9d; msWindowLength
0x18004723c  xor     r8d, r8d; msPeriod
0x18004723f  xor     edx, edx; pftDueTime
0x180047241  call    cs:__imp_SetThreadpoolTimer
0x180047247  mov     rcx, [rbx]; pti
0x18004724a  mov     edx, 1; fCancelPendingCallbacks
0x18004724f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180047255  mov     rcx, [rbx]; pti
0x180047258  call    cs:__imp_CloseThreadpoolTimer
0x18004725e  cmp     byte ptr [rbx+0Ch], 0
0x180047262  jz      short loc_180047289
0x180047264  xor     ecx, ecx; pReserved
0x180047266  call    cs:__imp_CoDisableCallCancellation
0x18004726c  test    eax, eax
0x18004726e  jns     short loc_180047289
0x180047270  mov     rcx, [rsp+28h]; this
0x180047275  lea     r8, aOnecoreInterna_3; "onecore\\internal\\enduser\\inc\\WaaSDe"...
0x18004727c  mov     r9d, eax; char *
0x18004727f  mov     edx, 40h ; '@'; void *
0x180047284  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180047289  add     rsp, 20h
0x18004728d  pop     rbx
0x18004728e  retn
```
