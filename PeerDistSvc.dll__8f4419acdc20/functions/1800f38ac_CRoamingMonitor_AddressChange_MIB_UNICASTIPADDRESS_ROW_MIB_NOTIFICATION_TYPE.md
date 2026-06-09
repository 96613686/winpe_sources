# CRoamingMonitor::AddressChange(_MIB_UNICASTIPADDRESS_ROW *,_MIB_NOTIFICATION_TYPE)

- ea: `0x1800f38ac`
- end: `0x1800f3ac3`
- name: `?AddressChange@CRoamingMonitor@@QEAAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z`
- size: `535`
- prototype: `void __fastcall(CRoamingMonitor *__hidden this, struct _MIB_UNICASTIPADDRESS_ROW *, enum _MIB_NOTIFICATION_TYPE)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800f3e60`

## callees

- `0x180004374`
- `0x18000ceac`
- `0x180015c28`
- `0x180018170`
- `0x180018d3c`
- `0x18001f46c`
- `0x1800f38ac`
- `0x1800f3e84`
- `0x1800f43a4`
- `0x1800f564c`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f39a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f39ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f39a0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f39ae`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f3a8d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800f3a8d`

## string_xrefs

- `0x1800f3a75`: `CreateTimerQueue failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CRoamingMonitor::AddressChange(
        CRoamingMonitor *this,
        struct _MIB_UNICASTIPADDRESS_ROW *a2,
        enum _MIB_NOTIFICATION_TYPE a3)
{
  int v6; // esi
  __int64 v7; // rdx
  CRoamingMonitor *v8; // rcx
  __int64 v9; // r8
  Timer::TimerQueue *v10; // rcx
  void *v11; // rax
  _BYTE v12[72]; // [rsp+30h] [rbp-48h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+80h] [rbp+8h] BYREF

  SystemTimeAsFileTime = 0;
  v6 = 0;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x10000000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 39, WPP_bc905e231a60314e4c513b29466ae090_Traceguids);
  }
  LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v12, (RTL_SRWLOCK *)this + 5);
  if ( a2->Address.Ipv4.sin_family == 2 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x10000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 12), 40, WPP_bc905e231a60314e4c513b29466ae090_Traceguids);
    }
  }
  else if ( a2->Address.Ipv4.sin_family == 23 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x10000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF__IPV6_d(*((_QWORD *)WPP_GLOBAL_Control + 12), v7, v9, &a2->Address.si_family + 4, a3);
    }
  }
  if ( (unsigned int)CRoamingMonitor::IsInterfaceRelevant(v8, a2->InterfaceIndex, a3) )
  {
    v6 = 1;
    GetSystemTimeAsFileTime((LPFILETIME)this + 31);
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    if ( *(_QWORD *)&SystemTimeAsFileTime - *((_QWORD *)this + 30) >= 0x23C34600u )
    {
      if ( *(_QWORD *)&SystemTimeAsFileTime - *((_QWORD *)this + 29) < 0x23C34600u )
        *((_DWORD *)this + 28) = 1;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x10000000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 42, WPP_bc905e231a60314e4c513b29466ae090_Traceguids);
      }
      CRoamingMonitor::NotifyRoamingDetectionInProgress(this, 1);
    }
  }
  LockSentry<ReadersWriterLock,0>::Unlock(v12);
  if ( v6 )
  {
    LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>((__int64)v12, (RTL_SRWLOCK *)this + 6);
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x10000000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 3u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 43, WPP_bc905e231a60314e4c513b29466ae090_Traceguids);
    }
    if ( *((_QWORD *)this + 4) )
    {
      v11 = Timer::TimerQueue::Get(v10);
      if ( !v11 )
        SystemError::Throw(L"CreateTimerQueue failed");
      if ( !DeleteTimerQueueTimer(v11, *((HANDLE *)this + 4), (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
        SystemError::Throw(L"Timer::CancelEngine");
      *((_QWORD *)this + 4) = 0;
    }
    LockSentry<ReadersWriterLock,0>::Unlock(v12);
  }
}

```

## disassembly

```asm
0x1800f38ac  mov     rax, rsp
0x1800f38af  push    rbx
0x1800f38b0  push    rbp
0x1800f38b1  push    rsi
0x1800f38b2  push    rdi
0x1800f38b3  push    r12
0x1800f38b5  push    r13
0x1800f38b7  sub     rsp, 48h
0x1800f38bb  mov     ebp, r8d
0x1800f38be  mov     rdi, rdx
0x1800f38c1  mov     rbx, rcx
0x1800f38c4  mov     qword ptr [rax+8], 0
0x1800f38cc  xor     esi, esi
0x1800f38ce  lea     r13, WPP_GLOBAL_Control
0x1800f38d5  mov     r12d, 10000000h
0x1800f38db  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f38e2  cmp     rcx, r13
0x1800f38e5  jz      short loc_1800F3906
0x1800f38e7  test    [rcx+6Ch], r12d
0x1800f38eb  jz      short loc_1800F3906
0x1800f38ed  cmp     byte ptr [rcx+69h], 4
0x1800f38f1  jb      short loc_1800F3906
0x1800f38f3  lea     edx, [rsi+27h]
0x1800f38f6  lea     r8, WPP_bc905e231a60314e4c513b29466ae090_Traceguids
0x1800f38fd  mov     rcx, [rcx+60h]
0x1800f3901  call    WPP_SF_
0x1800f3906  lea     rdx, [rbx+28h]
0x1800f390a  lea     rcx, [rsp+78h+var_48]
0x1800f390f  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800f3914  nop
0x1800f3915  cmp     word ptr [rdi], 2
0x1800f3919  jz      short loc_1800F394C
0x1800f391b  cmp     word ptr [rdi], 17h
0x1800f391f  jnz     short loc_1800F3981
0x1800f3921  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3928  cmp     rcx, r13
0x1800f392b  jz      short loc_1800F3981
0x1800f392d  test    [rcx+6Ch], r12d
0x1800f3931  jz      short loc_1800F3981
0x1800f3933  cmp     byte ptr [rcx+69h], 3
0x1800f3937  jb      short loc_1800F3981
0x1800f3939  lea     r9, [rdi+8]
0x1800f393d  mov     [rsp+78h+var_58], ebp
0x1800f3941  mov     rcx, [rcx+60h]
0x1800f3945  call    WPP_SF__IPV6_d
0x1800f394a  jmp     short loc_1800F3981
0x1800f394c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3953  cmp     rcx, r13
0x1800f3956  jz      short loc_1800F3981
0x1800f3958  test    [rcx+6Ch], r12d
0x1800f395c  jz      short loc_1800F3981
0x1800f395e  cmp     byte ptr [rcx+69h], 3
0x1800f3962  jb      short loc_1800F3981
0x1800f3964  mov     edx, 28h ; '('
0x1800f3969  mov     [rsp+78h+var_58], ebp
0x1800f396d  mov     r9d, [rdi+4]
0x1800f3971  lea     r8, WPP_bc905e231a60314e4c513b29466ae090_Traceguids
0x1800f3978  mov     rcx, [rcx+60h]
0x1800f397c  call    WPP_SF_Dd
0x1800f3981  mov     r8d, ebp; enum _MIB_NOTIFICATION_TYPE
0x1800f3984  mov     edx, [rdi+28h]; unsigned int
0x1800f3987  call    ?IsInterfaceRelevant@CRoamingMonitor@@AEAAHKW4_MIB_NOTIFICATION_TYPE@@@Z; CRoamingMonitor::IsInterfaceRelevant(ulong,_MIB_NOTIFICATION_TYPE)
0x1800f398c  test    eax, eax
0x1800f398e  jz      loc_1800F3A16
0x1800f3994  mov     esi, 1
0x1800f3999  lea     rcx, [rbx+0F8h]; lpSystemTimeAsFileTime
0x1800f39a0  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f39a6  lea     rcx, [rsp+78h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f39ae  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f39b4  mov     rax, qword ptr [rsp+78h+SystemTimeAsFileTime.dwLowDateTime]
0x1800f39bc  mov     rcx, rax
0x1800f39bf  sub     rcx, [rbx+0F0h]
0x1800f39c6  mov     edx, 23C34600h
0x1800f39cb  cmp     rcx, rdx
0x1800f39ce  jnb     short loc_1800F3A07
0x1800f39d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f39d7  cmp     rcx, r13
0x1800f39da  jz      short loc_1800F39FB
0x1800f39dc  test    [rcx+6Ch], r12d
0x1800f39e0  jz      short loc_1800F39FB
0x1800f39e2  cmp     byte ptr [rcx+69h], 3
0x1800f39e6  jb      short loc_1800F39FB
0x1800f39e8  lea     edx, [rsi+29h]
0x1800f39eb  lea     r8, WPP_bc905e231a60314e4c513b29466ae090_Traceguids
0x1800f39f2  mov     rcx, [rcx+60h]
0x1800f39f6  call    WPP_SF_
0x1800f39fb  mov     edx, esi; int
0x1800f39fd  mov     rcx, rbx; this
0x1800f3a00  call    ?NotifyRoamingDetectionInProgress@CRoamingMonitor@@AEAAXH@Z; CRoamingMonitor::NotifyRoamingDetectionInProgress(int)
0x1800f3a05  jmp     short loc_1800F3A16
0x1800f3a07  sub     rax, [rbx+0E8h]
0x1800f3a0e  cmp     rax, rdx
0x1800f3a11  jnb     short loc_1800F3A16
0x1800f3a13  mov     [rbx+70h], esi
0x1800f3a16  lea     rcx, [rsp+78h+var_48]
0x1800f3a1b  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800f3a20  test    esi, esi
0x1800f3a22  jz      loc_1800F3AB6
0x1800f3a28  lea     rdx, [rbx+30h]
0x1800f3a2c  lea     rcx, [rsp+78h+var_48]
0x1800f3a31  call    ??0?$LockSentry@VReadersWriterLock@@$0A@@@QEAA@AEAVReadersWriterLock@@@Z; LockSentry<ReadersWriterLock,0>::LockSentry<ReadersWriterLock,0>(ReadersWriterLock &)
0x1800f3a36  nop
0x1800f3a37  mov     rcx, cs:WPP_GLOBAL_Control
0x1800f3a3e  cmp     rcx, r13
0x1800f3a41  jz      short loc_1800F3A64
0x1800f3a43  test    [rcx+6Ch], r12d
0x1800f3a47  jz      short loc_1800F3A64
0x1800f3a49  cmp     byte ptr [rcx+69h], 3
0x1800f3a4d  jb      short loc_1800F3A64
0x1800f3a4f  mov     edx, 2Bh ; '+'
0x1800f3a54  lea     r8, WPP_bc905e231a60314e4c513b29466ae090_Traceguids
0x1800f3a5b  mov     rcx, [rcx+60h]
0x1800f3a5f  call    WPP_SF_
0x1800f3a64  cmp     qword ptr [rbx+20h], 0
0x1800f3a69  jz      short loc_1800F3AAC
0x1800f3a6b  call    ?Get@TimerQueue@Timer@@QEAAQEAXXZ; Timer::TimerQueue::Get(void)
0x1800f3a70  test    rax, rax
0x1800f3a73  jnz     short loc_1800F3A82
0x1800f3a75  lea     rcx, aCreatetimerque_0; "CreateTimerQueue failed"
0x1800f3a7c  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x1800f3a82  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800f3a86  mov     rdx, [rbx+20h]; Timer
0x1800f3a8a  mov     rcx, rax; TimerQueue
0x1800f3a8d  call    cs:__imp_DeleteTimerQueueTimer
0x1800f3a93  test    eax, eax
0x1800f3a95  jnz     short loc_1800F3AA4
0x1800f3a97  lea     rcx, aTimerCanceleng; "Timer::CancelEngine"
0x1800f3a9e  call    ?Throw@SystemError@@SAXPEBG@Z; SystemError::Throw(ushort const *)
0x1800f3aa4  mov     qword ptr [rbx+20h], 0
0x1800f3aac  lea     rcx, [rsp+78h+var_48]
0x1800f3ab1  call    ?Unlock@?$LockSentry@VReadersWriterLock@@$0A@@@QEAAXXZ; LockSentry<ReadersWriterLock,0>::Unlock(void)
0x1800f3ab6  add     rsp, 48h
0x1800f3aba  pop     r13
0x1800f3abc  pop     r12
0x1800f3abe  pop     rdi
0x1800f3abf  pop     rsi
0x1800f3ac0  pop     rbp
0x1800f3ac1  pop     rbx
0x1800f3ac2  retn
```
