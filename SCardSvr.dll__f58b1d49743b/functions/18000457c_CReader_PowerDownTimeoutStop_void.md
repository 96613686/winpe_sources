# CReader::PowerDownTimeoutStop(void)

- ea: `0x18000457c`
- end: `0x180004683`
- name: `?PowerDownTimeoutStop@CReader@@IEAAXXZ`
- size: `263`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180001950`
- `0x1800039e0`
- `0x18002d62c`

## callees

- `0x1800044e0`
- `0x18000457c`
- `0x1800075d0`
- `0x18000d7a0`
- `0x180028b78`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000460c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000460c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000462d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000462d`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800045b2`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800045b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CReader::PowerDownTimeoutStop(CReader *this)
{
  char v2; // di
  struct _TP_TIMER *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = 0;
  CLockWrite::CLockWrite((CLockWrite *)&v6, (CReader *)((char *)this + 56));
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 88);
  if ( v3 && IsThreadpoolTimerSet(v3) )
  {
    WppTraceIndent(v4, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    }
    v2 = 1;
    SetThreadpoolTimer(*((PTP_TIMER *)this + 88), 0, 0, 0);
  }
  CLockWrite::~CLockWrite((CLockWrite *)&v6);
  if ( v2 )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 88), 1);
  }
  else
  {
    WppTraceIndent(v5, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    }
  }
}

```

## disassembly

```asm
0x18000457c  mov     [rsp+arg_8], rbx
0x180004581  mov     [rsp+arg_10], rbp
0x180004586  push    rdi
0x180004587  sub     rsp, 20h
0x18000458b  mov     rbx, rcx
0x18000458e  lea     rdx, [rcx+38h]; struct CAccessLock *
0x180004592  lea     rcx, [rsp+28h+arg_0]; this
0x180004597  xor     dil, dil
0x18000459a  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18000459f  mov     rcx, [rbx+2C0h]; pti
0x1800045a6  lea     rbp, WPP_GLOBAL_Control
0x1800045ad  test    rcx, rcx
0x1800045b0  jz      short loc_180004612
0x1800045b2  call    cs:__imp_IsThreadpoolTimerSet
0x1800045b8  test    eax, eax
0x1800045ba  jz      short loc_180004612
0x1800045bc  mov     edx, 2
0x1800045c1  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x1800045c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800045cd  cmp     rcx, rbp
0x1800045d0  jz      short loc_1800045FA
0x1800045d2  test    byte ptr [rcx+1Ch], 10h
0x1800045d6  jz      short loc_1800045FA
0x1800045d8  cmp     byte ptr [rcx+19h], 4
0x1800045dc  jb      short loc_1800045FA
0x1800045de  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x1800045e5  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x1800045ec  mov     rcx, [rcx+10h]
0x1800045f0  mov     edx, 0Bh
0x1800045f5  call    WPP_SF_s
0x1800045fa  mov     rcx, [rbx+2C0h]; pti
0x180004601  xor     r9d, r9d; msWindowLength
0x180004604  xor     r8d, r8d; msPeriod
0x180004607  xor     edx, edx; pftDueTime
0x180004609  mov     dil, 1
0x18000460c  call    cs:__imp_SetThreadpoolTimer
0x180004612  lea     rcx, [rsp+28h+arg_0]; this
0x180004617  call    ??1CLockWrite@@QEAA@XZ; CLockWrite::~CLockWrite(void)
0x18000461c  test    dil, dil
0x18000461f  jz      short loc_180004635
0x180004621  mov     rcx, [rbx+2C0h]; pti
0x180004628  mov     edx, 1; fCancelPendingCallbacks
0x18000462d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004633  jmp     short loc_180004673
0x180004635  mov     edx, 2
0x18000463a  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000463f  mov     rcx, cs:WPP_GLOBAL_Control
0x180004646  cmp     rcx, rbp
0x180004649  jz      short loc_180004673
0x18000464b  test    byte ptr [rcx+1Ch], 10h
0x18000464f  jz      short loc_180004673
0x180004651  cmp     byte ptr [rcx+19h], 4
0x180004655  jb      short loc_180004673
0x180004657  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000465e  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x180004665  mov     rcx, [rcx+10h]
0x180004669  mov     edx, 0Ch
0x18000466e  call    WPP_SF_s
0x180004673  mov     rbx, [rsp+28h+arg_8]
0x180004678  mov     rbp, [rsp+28h+arg_10]
0x18000467d  add     rsp, 20h
0x180004681  pop     rdi
0x180004682  retn
```
