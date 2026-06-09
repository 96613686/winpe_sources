# Broker::TimeBroker::BrokerLock::BrokerLock(int)

- ea: `0x180002400`
- end: `0x1800024f3`
- name: `??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z`
- size: `243`
- prototype: `Broker::TimeBroker::BrokerLock *__fastcall(Broker::TimeBroker::BrokerLock *this, int)`
- caller_count: `17`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001ba4`
- `0x180001f78`
- `0x18000215c`
- `0x180003868`
- `0x18000f6f0`
- `0x180010f0c`
- `0x180011d00`
- `0x180014568`
- `0x180014970`
- `0x180015178`
- `0x1800152fc`
- `0x180015620`
- `0x180015b10`
- `0x180015cb0`
- `0x180015f3c`
- `0x1800165b0`
- `0x180016650`

## callees

- `0x180002400`
- `0x180013978`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002461`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002461`
- `BrokerLib!BrLockBroker` at `0x18000243f`
- `BrokerLib!BrLockBroker` at `0x18000243f`

## pseudocode

```c
Broker::TimeBroker::BrokerLock *__fastcall Broker::TimeBroker::BrokerLock::BrokerLock(
        Broker::TimeBroker::BrokerLock *this,
        int a2)
{
  volatile signed __int32 *v4; // rbx
  struct _FILETIME *v5; // rbp
  int v6; // eax
  void **pExceptionObject; // [rsp+30h] [rbp-58h] BYREF
  __int128 v9; // [rsp+38h] [rbp-50h]
  int v10; // [rsp+48h] [rbp-40h]
  int v11; // [rsp+50h] [rbp-38h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+90h] [rbp+8h] BYREF

  *(_DWORD *)this = a2;
  v4 = (volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v4 = (volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1);
  }
  v5 = (struct _FILETIME *)Broker::TimeBroker::Instance;
  v6 = BrLockBroker(*((_QWORD *)Broker::TimeBroker::Instance + 24));
  if ( v6 )
  {
    v9 = 0;
    v10 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v11 = v6;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  if ( !a2 )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v5[25] = SystemTimeAsFileTime;
  }
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  return this;
}

```

## disassembly

```asm
0x180002400  push    rbx
0x180002402  push    rbp
0x180002403  push    rsi
0x180002404  push    rdi
0x180002405  sub     rsp, 68h
0x180002409  mov     edi, edx
0x18000240b  mov     rsi, rcx
0x18000240e  mov     [rcx], edx
0x180002410  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180002417  test    rbx, rbx
0x18000241a  jz      short loc_180002427
0x18000241c  lock inc dword ptr [rbx+8]
0x180002420  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180002427  mov     rbp, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x18000242e  mov     [rsp+88h+var_68], rbp
0x180002433  mov     [rsp+88h+var_60], rbx
0x180002438  mov     rcx, [rbp+0C0h]
0x18000243f  call    cs:__imp_BrLockBroker
0x180002445  test    eax, eax
0x180002447  jnz     short loc_1800024C1
0x180002449  test    edi, edi
0x18000244b  jnz     short loc_180002476
0x18000244d  mov     qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002459  lea     rcx, [rsp+88h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002461  call    cs:__imp_GetSystemTimeAsFileTime
0x180002467  mov     rax, qword ptr [rsp+88h+SystemTimeAsFileTime.dwLowDateTime]
0x18000246f  mov     [rbp+0C8h], rax
0x180002476  test    rbx, rbx
0x180002479  jz      short loc_18000248C
0x18000247b  mov     edi, 0FFFFFFFFh
0x180002480  mov     eax, edi
0x180002482  lock xadd [rbx+8], eax
0x180002487  cmp     eax, 1
0x18000248a  jz      short loc_180002498
0x18000248c  mov     rax, rsi
0x18000248f  add     rsp, 68h
0x180002493  pop     rdi
0x180002494  pop     rsi
0x180002495  pop     rbp
0x180002496  pop     rbx
0x180002497  retn
0x180002498  mov     rax, [rbx]
0x18000249b  mov     rcx, rbx
0x18000249e  mov     rax, [rax]
0x1800024a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024a6  lock xadd [rbx+0Ch], edi
0x1800024ab  cmp     edi, 1
0x1800024ae  jnz     short loc_18000248C
0x1800024b0  mov     rax, [rbx]
0x1800024b3  mov     rcx, rbx
0x1800024b6  mov     rax, [rax+8]
0x1800024ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024bf  jmp     short loc_18000248C
0x1800024c1  xorps   xmm0, xmm0
0x1800024c4  movups  [rsp+88h+var_50], xmm0
0x1800024c9  mov     [rsp+88h+var_40], 1
0x1800024d1  lea     rcx, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x1800024d8  mov     [rsp+88h+pExceptionObject], rcx
0x1800024dd  mov     [rsp+88h+var_38], eax
0x1800024e1  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x1800024e8  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x1800024ed  call    _CxxThrowException_0
```
