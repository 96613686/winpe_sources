# DynamicVirtualChannelTransport::AttemptReconnect(void)

- ea: `0x180015ce8`
- end: `0x180015e6a`
- name: `?AttemptReconnect@DynamicVirtualChannelTransport@@IEAAJXZ`
- size: `386`
- prototype: `__int64 __fastcall(DynamicVirtualChannelTransport *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180015fe8`
- `0x180016bb0`
- `0x180016fb0`

## callees

- `0x180015550`
- `0x180015ce8`
- `0x180015e70`
- `0x180015f38`
- `0x180016830`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015d0d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180015d0d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015e25`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180015e25`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015d88`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015d88`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015dd6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180015dd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015cf8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015cf8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180015e56`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180015e56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DynamicVirtualChannelTransport::AttemptReconnect(DynamicVirtualChannelTransport *this)
{
  DWORD CurrentThreadId; // ebp
  int v3; // r14d
  __int64 v5; // rdx
  volatile signed __int32 *v6; // rdi
  HANDLE Handles[2]; // [rsp+20h] [rbp-68h] BYREF
  __int128 v8; // [rsp+30h] [rbp-58h] BYREF
  int v9; // [rsp+40h] [rbp-48h]
  int v10; // [rsp+48h] [rbp-40h]

  CurrentThreadId = GetCurrentThreadId();
  v3 = *((_DWORD *)this + 18);
  while ( WaitForSingleObject(*((HANDLE *)this + 15), 0) )
  {
    if ( CurrentThreadId == v3 )
    {
      if ( *((_QWORD *)this + 6) && *((_QWORD *)this + 5) )
        return 0;
      if ( *((_BYTE *)this + 17) )
        DynamicVirtualChannelTransport::OnTransportConnectionStatusChanged(this, 0);
      DynamicVirtualChannelTransport::CleanupConnections(this);
      DynamicVirtualChannelTransport::DoConnectToHost(this);
      if ( *((_QWORD *)this + 6) && *((_QWORD *)this + 5) )
      {
        if ( *((_BYTE *)this + 17) )
          DynamicVirtualChannelTransport::OnTransportConnectionStatusChanged(this, 2);
        return 0;
      }
    }
    else
    {
      AcquireSRWLockExclusive((PSRWLOCK)this + 20);
      v8 = 0;
      v9 = 0;
      v10 = 0;
      v5 = *((_QWORD *)this + 13);
      if ( v5 == *((_QWORD *)this + 14) )
      {
        std::vector<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>>>::_Emplace_reallocate<std::tuple<enum DynamicVirtualChannelTransport::MarshalledCallType,unsigned int,std::shared_ptr<std::vector<char>>> const &>(
          (char *)this + 96,
          v5,
          &v8);
      }
      else
      {
        *(_QWORD *)v5 = 0;
        *(_QWORD *)(v5 + 8) = 0;
        *(_DWORD *)(v5 + 16) = 0;
        *(_DWORD *)(v5 + 24) = 0;
        *((_QWORD *)this + 13) += 32LL;
      }
      SetEvent(*((HANDLE *)this + 16));
      v6 = (volatile signed __int32 *)*((_QWORD *)&v8 + 1);
      if ( *((_QWORD *)&v8 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v8 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      if ( this != (DynamicVirtualChannelTransport *)-160LL )
        ReleaseSRWLockExclusive((PSRWLOCK)this + 20);
    }
    Handles[0] = *((HANDLE *)this + 18);
    Handles[1] = *((HANDLE *)this + 15);
    if ( WaitForMultipleObjects(2u, Handles, 1, 0x3E8u) == 1 )
      return 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180015ce8  push    rbx
0x180015cea  push    rbp
0x180015ceb  push    rsi
0x180015cec  push    rdi
0x180015ced  push    r14
0x180015cef  push    r15
0x180015cf1  sub     rsp, 58h
0x180015cf5  mov     rbx, rcx
0x180015cf8  call    cs:__imp_GetCurrentThreadId
0x180015cfe  mov     ebp, eax
0x180015d00  mov     r14d, [rbx+48h]
0x180015d04  xor     r15d, r15d
0x180015d07  xor     edx, edx; dwMilliseconds
0x180015d09  mov     rcx, [rbx+78h]; hHandle
0x180015d0d  call    cs:__imp_WaitForSingleObject
0x180015d13  test    eax, eax
0x180015d15  jz      short loc_180015D6F
0x180015d17  cmp     ebp, r14d
0x180015d1a  jnz     short loc_180015D7E
0x180015d1c  cmp     [rbx+30h], r15
0x180015d20  jz      short loc_180015D28
0x180015d22  cmp     [rbx+28h], r15
0x180015d26  jnz     short loc_180015D6F
0x180015d28  cmp     [rbx+11h], r15b
0x180015d2c  jz      short loc_180015D38
0x180015d2e  xor     edx, edx
0x180015d30  mov     rcx, rbx
0x180015d33  call    ?OnTransportConnectionStatusChanged@DynamicVirtualChannelTransport@@AEAAXW4TransportConnectionStatus@@@Z; DynamicVirtualChannelTransport::OnTransportConnectionStatusChanged(TransportConnectionStatus)
0x180015d38  mov     rcx, rbx; this
0x180015d3b  call    ?CleanupConnections@DynamicVirtualChannelTransport@@AEAAXXZ; DynamicVirtualChannelTransport::CleanupConnections(void)
0x180015d40  mov     rcx, rbx; this
0x180015d43  call    ?DoConnectToHost@DynamicVirtualChannelTransport@@IEAAJXZ; DynamicVirtualChannelTransport::DoConnectToHost(void)
0x180015d48  cmp     [rbx+30h], r15
0x180015d4c  jz      loc_180015E2C
0x180015d52  cmp     [rbx+28h], r15
0x180015d56  jz      loc_180015E2C
0x180015d5c  cmp     [rbx+11h], r15b
0x180015d60  jz      short loc_180015D6F
0x180015d62  mov     edx, 2
0x180015d67  mov     rcx, rbx
0x180015d6a  call    ?OnTransportConnectionStatusChanged@DynamicVirtualChannelTransport@@AEAAXW4TransportConnectionStatus@@@Z; DynamicVirtualChannelTransport::OnTransportConnectionStatusChanged(TransportConnectionStatus)
0x180015d6f  xor     eax, eax
0x180015d71  add     rsp, 58h
0x180015d75  pop     r15
0x180015d77  pop     r14
0x180015d79  pop     rdi
0x180015d7a  pop     rsi
0x180015d7b  pop     rbp
0x180015d7c  pop     rbx
0x180015d7d  retn
0x180015d7e  lea     rsi, [rbx+0A0h]
0x180015d85  mov     rcx, rsi; SRWLock
0x180015d88  call    cs:__imp_AcquireSRWLockExclusive
0x180015d8e  xorps   xmm0, xmm0
0x180015d91  movdqu  [rsp+88h+var_58], xmm0
0x180015d97  mov     [rsp+88h+var_48], r15d
0x180015d9c  mov     [rsp+88h+var_40], r15d
0x180015da1  lea     rcx, [rbx+60h]
0x180015da5  mov     rdx, [rcx+8]
0x180015da9  cmp     rdx, [rcx+10h]
0x180015dad  jz      short loc_180015DC5
0x180015daf  mov     [rdx], r15
0x180015db2  mov     [rdx+8], r15
0x180015db6  mov     [rdx+10h], r15d
0x180015dba  mov     [rdx+18h], r15d
0x180015dbe  add     qword ptr [rcx+8], 20h ; ' '
0x180015dc3  jmp     short loc_180015DCF
0x180015dc5  lea     r8, [rsp+88h+var_58]
0x180015dca  call    ??$_Emplace_reallocate@AEBV?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@?$vector@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@V?$allocator@V?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@std@@@2@@std@@AEAAPEAV?$tuple@W4MarshalledCallType@DynamicVirtualChannelTransport@@IV?$shared_ptr@V?$vector@DV?$allocator@D@std@@@std@@@std@@@1@QEAV21@AEBV21@@Z; std::vector<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>>>::_Emplace_reallocate<std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> const &>(std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> * const,std::tuple<DynamicVirtualChannelTransport::MarshalledCallType,uint,std::shared_ptr<std::vector<char>>> const &)
0x180015dcf  mov     rcx, [rbx+80h]; hEvent
0x180015dd6  call    cs:__imp_SetEvent
0x180015ddc  mov     rdi, qword ptr [rsp+88h+var_58+8]
0x180015de1  test    rdi, rdi
0x180015de4  jz      short loc_180015E1D
0x180015de6  or      eax, 0FFFFFFFFh
0x180015de9  lock xadd [rdi+8], eax
0x180015dee  cmp     eax, 1
0x180015df1  jnz     short loc_180015E1D
0x180015df3  mov     rax, [rdi]
0x180015df6  mov     rcx, rdi
0x180015df9  mov     rax, [rax]
0x180015dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e01  or      eax, 0FFFFFFFFh
0x180015e04  lock xadd [rdi+0Ch], eax
0x180015e09  cmp     eax, 1
0x180015e0c  jnz     short loc_180015E1D
0x180015e0e  mov     rax, [rdi]
0x180015e11  mov     rcx, rdi
0x180015e14  mov     rax, [rax+8]
0x180015e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e1d  test    rsi, rsi
0x180015e20  jz      short loc_180015E2C
0x180015e22  mov     rcx, rsi; SRWLock
0x180015e25  call    cs:__imp_ReleaseSRWLockExclusive
0x180015e2b  nop
0x180015e2c  mov     rax, [rbx+90h]
0x180015e33  mov     [rsp+88h+Handles], rax
0x180015e38  mov     rax, [rbx+78h]
0x180015e3c  mov     [rsp+88h+var_60], rax
0x180015e41  mov     r9d, 3E8h; dwMilliseconds
0x180015e47  mov     r8d, 1; bWaitAll
0x180015e4d  lea     rdx, [rsp+88h+Handles]; lpHandles
0x180015e52  lea     ecx, [r8+1]; nCount
0x180015e56  call    cs:__imp_WaitForMultipleObjects
0x180015e5c  cmp     eax, 1
0x180015e5f  jnz     loc_180015D07
0x180015e65  jmp     loc_180015D6F
```
