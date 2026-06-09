# CLoggingMgrImpl::ShutdownInternal(void)

- ea: `0x18012b700`
- end: `0x18012b877`
- name: `?ShutdownInternal@CLoggingMgrImpl@@QEAAJXZ`
- size: `375`
- prototype: `__int64 __fastcall(CLoggingMgrImpl *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18012b5f0`

## callees

- `0x180004374`
- `0x180004510`
- `0x180004874`
- `0x180008290`
- `0x18012b700`
- `0x180159010`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x18012b7d6`
- `ntdll!EtwEventUnregister` at `0x18012b7d6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012b7a8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18012b7a8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012b78f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18012b78f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012b773`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18012b773`

## pseudocode

```c
__int64 __fastcall CLoggingMgrImpl::ShutdownInternal(CLoggingMgrImpl *this)
{
  char *v2; // rsi
  unsigned int v3; // edi
  struct _TP_TIMER *v4; // rcx
  __int64 v5; // rcx
  unsigned int v6; // eax
  int v7; // esi
  _BYTE v9[72]; // [rsp+20h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 18, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids);
  }
  v2 = (char *)this + 40;
  v3 = 0;
  InCritSec::InCritSec((InCritSec *)v9, (CLoggingMgrImpl *)((char *)this + 40), 1);
  v4 = (struct _TP_TIMER *)*((_QWORD *)this + 3);
  *((_BYTE *)this + 33) = 0;
  *((_BYTE *)this + 16) = 0;
  if ( v4 )
  {
    SetThreadpoolTimer(v4, 0, 0, 0);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 16LL))((char *)this + 40);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 3), 1);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v2 + 8LL))((char *)this + 40);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 3));
    *((_BYTE *)this + 32) = 0;
    *((_QWORD *)this + 3) = 0;
  }
  v5 = *((_QWORD *)this + 1);
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 65) = 0;
  *((_BYTE *)this + 256) = 0;
  *((_BYTE *)this + 292) = 0;
  if ( v5 )
  {
    v6 = EtwEventUnregister();
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 19, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids, v6);
      }
      if ( v7 > 0 )
        v3 = (unsigned __int16)v7 | 0x80070000;
      else
        v3 = v7;
    }
    *((_QWORD *)this + 1) = 0;
  }
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x2000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 20, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids, v3);
  }
  InCritSec::~InCritSec((InCritSec *)v9);
  return v3;
}

```

## disassembly

```asm
0x18012b700  push    rbx
0x18012b702  push    rsi
0x18012b703  push    rdi
0x18012b704  push    r15
0x18012b706  sub     rsp, 48h
0x18012b70a  mov     rbx, rcx
0x18012b70d  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b714  lea     r15, WPP_GLOBAL_Control
0x18012b71b  cmp     rcx, r15
0x18012b71e  jz      short loc_18012B744
0x18012b720  test    dword ptr [rcx+6Ch], 2000h
0x18012b727  jz      short loc_18012B744
0x18012b729  cmp     byte ptr [rcx+69h], 4
0x18012b72d  jb      short loc_18012B744
0x18012b72f  mov     rcx, [rcx+60h]
0x18012b733  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012b73a  mov     edx, 12h
0x18012b73f  call    WPP_SF_
0x18012b744  lea     rsi, [rbx+28h]
0x18012b748  mov     r8b, 1; bool
0x18012b74b  mov     rdx, rsi; struct CritSec *
0x18012b74e  lea     rcx, [rsp+68h+var_48]; this
0x18012b753  xor     edi, edi
0x18012b755  call    ??0InCritSec@@QEAA@AEAVCritSec@@_N@Z; InCritSec::InCritSec(CritSec &,bool)
0x18012b75a  mov     rcx, [rbx+18h]; pti
0x18012b75e  mov     [rbx+21h], dil
0x18012b762  mov     [rbx+10h], dil
0x18012b766  test    rcx, rcx
0x18012b769  jz      short loc_18012B7B6
0x18012b76b  xor     r9d, r9d; msWindowLength
0x18012b76e  xor     r8d, r8d; msPeriod
0x18012b771  xor     edx, edx; pftDueTime
0x18012b773  call    cs:__imp_SetThreadpoolTimer
0x18012b779  mov     rax, [rsi]
0x18012b77c  mov     rcx, rsi
0x18012b77f  mov     rax, [rax+10h]
0x18012b783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b788  mov     rcx, [rbx+18h]; pti
0x18012b78c  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x18012b78f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18012b795  mov     rax, [rsi]
0x18012b798  mov     rcx, rsi
0x18012b79b  mov     rax, [rax+8]
0x18012b79f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18012b7a4  mov     rcx, [rbx+18h]; pti
0x18012b7a8  call    cs:__imp_CloseThreadpoolTimer
0x18012b7ae  mov     [rbx+20h], dil
0x18012b7b2  mov     [rbx+18h], rdi
0x18012b7b6  mov     rcx, [rbx+8]
0x18012b7ba  mov     [rbx+58h], edi
0x18012b7bd  mov     [rbx+104h], edi
0x18012b7c3  mov     [rbx+100h], dil
0x18012b7ca  mov     [rbx+124h], dil
0x18012b7d1  test    rcx, rcx
0x18012b7d4  jz      short loc_18012B82E
0x18012b7d6  call    cs:__imp_EtwEventUnregister
0x18012b7dc  mov     esi, eax
0x18012b7de  test    eax, eax
0x18012b7e0  jz      short loc_18012B826
0x18012b7e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b7e9  cmp     rcx, r15
0x18012b7ec  jz      short loc_18012B815
0x18012b7ee  test    dword ptr [rcx+6Ch], 2000h
0x18012b7f5  jz      short loc_18012B815
0x18012b7f7  cmp     byte ptr [rcx+69h], 1
0x18012b7fb  jb      short loc_18012B815
0x18012b7fd  mov     rcx, [rcx+60h]
0x18012b801  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012b808  mov     edx, 13h
0x18012b80d  mov     r9d, eax
0x18012b810  call    WPP_SF_d
0x18012b815  test    esi, esi
0x18012b817  jg      short loc_18012B81D
0x18012b819  mov     edi, esi
0x18012b81b  jmp     short loc_18012B826
0x18012b81d  movzx   edi, si
0x18012b820  or      edi, 80070000h
0x18012b826  mov     qword ptr [rbx+8], 0
0x18012b82e  mov     rcx, cs:WPP_GLOBAL_Control
0x18012b835  cmp     rcx, r15
0x18012b838  jz      short loc_18012B861
0x18012b83a  test    dword ptr [rcx+6Ch], 2000h
0x18012b841  jz      short loc_18012B861
0x18012b843  cmp     byte ptr [rcx+69h], 4
0x18012b847  jb      short loc_18012B861
0x18012b849  mov     rcx, [rcx+60h]
0x18012b84d  lea     r8, WPP_67a4de9b54913b2f748cc295e4a5c623_Traceguids
0x18012b854  mov     edx, 14h
0x18012b859  mov     r9d, edi
0x18012b85c  call    WPP_SF_d
0x18012b861  lea     rcx, [rsp+68h+var_48]; this
0x18012b866  call    ??1InCritSec@@QEAA@XZ; InCritSec::~InCritSec(void)
0x18012b86b  mov     eax, edi
0x18012b86d  add     rsp, 48h
0x18012b871  pop     r15
0x18012b873  pop     rdi
0x18012b874  pop     rsi
0x18012b875  pop     rbx
0x18012b876  retn
```
