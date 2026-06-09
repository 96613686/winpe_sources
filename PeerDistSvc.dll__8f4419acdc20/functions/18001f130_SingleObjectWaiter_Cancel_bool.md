# SingleObjectWaiter::Cancel(bool)

- ea: `0x18001f130`
- end: `0x18001f2a5`
- name: `?Cancel@SingleObjectWaiter@@QEAAX_N@Z`
- size: `373`
- prototype: `void __fastcall(SingleObjectWaiter *__hidden this, bool)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x18001f510`
- `0x18001f748`
- `0x18009cc8c`
- `0x1800a0d58`
- `0x1800e3c74`
- `0x1800e517c`
- `0x1801026b8`
- `0x18010271c`
- `0x1801027b8`
- `0x18011d648`
- `0x180120ba4`

## callees

- `0x180004510`
- `0x180004874`
- `0x1800082d0`
- `0x18001f130`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f1ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001f1ad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001f1eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001f1eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001f224`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001f224`

## pseudocode

```c
void __fastcall SingleObjectWaiter::Cancel(PTP_WAIT *this)
{
  CHostedCacheMsgEncoding *v2; // rcx
  __int64 v3; // rdx
  _BYTE v4[40]; // [rsp+20h] [rbp-28h] BYREF
  struct _FILETIME pftTimeout; // [rsp+50h] [rbp+8h] BYREF

  InCritSec::InCritSec((InCritSec *)v4, (struct CritSec *)(this + 11), 1);
  if ( this[6] )
  {
    pftTimeout = 0;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 16, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids);
    }
    SetThreadpoolWait(this[6], 0, &pftTimeout);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 17, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids);
    }
    WaitForThreadpoolWaitCallbacks(this[6], 1);
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids);
    }
    CloseThreadpoolWait(this[6]);
    this[6] = 0;
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      v3 = 19;
LABEL_22:
      WPP_SF_q(*((_QWORD *)v2 + 12), v3, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids);
    }
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x800000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
    {
      v3 = 20;
      goto LABEL_22;
    }
  }
  InCritSec::~InCritSec((InCritSec *)v4);
}

```

## disassembly

```asm
0x18001f130  mov     [rsp+arg_8], rbx
0x18001f135  mov     [rsp+arg_10], rbp
0x18001f13a  push    rsi
0x18001f13b  sub     rsp, 40h
0x18001f13f  mov     rbx, rcx
0x18001f142  lea     rdx, [rcx+58h]; struct CritSec *
0x18001f146  lea     rcx, [rsp+48h+var_28]; this
0x18001f14b  mov     r8b, 1; bool
0x18001f14e  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18001f153  cmp     qword ptr [rbx+30h], 0
0x18001f158  jz      loc_18001F250
0x18001f15e  mov     qword ptr [rsp+48h+pftTimeout.dwLowDateTime], 0
0x18001f167  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f16e  lea     rbp, WPP_GLOBAL_Control
0x18001f175  mov     esi, 800000h
0x18001f17a  cmp     rcx, rbp
0x18001f17d  jz      short loc_18001F1A2
0x18001f17f  test    [rcx+6Ch], esi
0x18001f182  jz      short loc_18001F1A2
0x18001f184  cmp     byte ptr [rcx+69h], 4
0x18001f188  jb      short loc_18001F1A2
0x18001f18a  mov     rcx, [rcx+60h]
0x18001f18e  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f195  mov     edx, 10h
0x18001f19a  mov     r9, rbx
0x18001f19d  call    WPP_SF_q
0x18001f1a2  mov     rcx, [rbx+30h]; pwa
0x18001f1a6  lea     r8, [rsp+48h+pftTimeout]; pftTimeout
0x18001f1ab  xor     edx, edx; h
0x18001f1ad  call    cs:__imp_SetThreadpoolWait
0x18001f1b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1ba  cmp     rcx, rbp
0x18001f1bd  jz      short loc_18001F1E2
0x18001f1bf  test    [rcx+6Ch], esi
0x18001f1c2  jz      short loc_18001F1E2
0x18001f1c4  cmp     byte ptr [rcx+69h], 4
0x18001f1c8  jb      short loc_18001F1E2
0x18001f1ca  mov     rcx, [rcx+60h]
0x18001f1ce  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f1d5  mov     edx, 11h
0x18001f1da  mov     r9, rbx
0x18001f1dd  call    WPP_SF_q
0x18001f1e2  mov     rcx, [rbx+30h]; pwa
0x18001f1e6  mov     edx, 1; fCancelPendingCallbacks
0x18001f1eb  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001f1f1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1f8  cmp     rcx, rbp
0x18001f1fb  jz      short loc_18001F220
0x18001f1fd  test    [rcx+6Ch], esi
0x18001f200  jz      short loc_18001F220
0x18001f202  cmp     byte ptr [rcx+69h], 4
0x18001f206  jb      short loc_18001F220
0x18001f208  mov     rcx, [rcx+60h]
0x18001f20c  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f213  mov     edx, 12h
0x18001f218  mov     r9, rbx
0x18001f21b  call    WPP_SF_q
0x18001f220  mov     rcx, [rbx+30h]; pwa
0x18001f224  call    cs:__imp_CloseThreadpoolWait
0x18001f22a  mov     qword ptr [rbx+30h], 0
0x18001f232  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f239  cmp     rcx, rbp
0x18001f23c  jz      short loc_18001F28B
0x18001f23e  test    [rcx+6Ch], esi
0x18001f241  jz      short loc_18001F28B
0x18001f243  cmp     byte ptr [rcx+69h], 4
0x18001f247  jb      short loc_18001F28B
0x18001f249  mov     edx, 13h
0x18001f24e  jmp     short loc_18001F278
0x18001f250  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f257  lea     rbp, WPP_GLOBAL_Control
0x18001f25e  cmp     rcx, rbp
0x18001f261  jz      short loc_18001F28B
0x18001f263  mov     esi, 800000h
0x18001f268  test    [rcx+6Ch], esi
0x18001f26b  jz      short loc_18001F28B
0x18001f26d  cmp     byte ptr [rcx+69h], 4
0x18001f271  jb      short loc_18001F28B
0x18001f273  mov     edx, 14h
0x18001f278  mov     rcx, [rcx+60h]
0x18001f27c  lea     r8, WPP_7e3fc60a412935a0e7501bc6f541d1b0_Traceguids
0x18001f283  mov     r9, rbx
0x18001f286  call    WPP_SF_q
0x18001f28b  lea     rcx, [rsp+48h+var_28]; this
0x18001f290  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18001f295  mov     rbx, [rsp+48h+arg_8]
0x18001f29a  mov     rbp, [rsp+48h+arg_10]
0x18001f29f  add     rsp, 40h
0x18001f2a3  pop     rsi
0x18001f2a4  retn
```
