# Broker::TimeBroker::BrokerLock::~BrokerLock(void)

- ea: `0x180005b90`
- end: `0x180005c3b`
- name: `??1BrokerLock@TimeBroker@Broker@@QEAA@XZ`
- size: `171`
- prototype: `void __fastcall(Broker::TimeBroker::BrokerLock *__hidden this)`
- caller_count: `32`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ba4`
- `0x180001f78`
- `0x18000215c`
- `0x180003868`
- `0x180004e5c`
- `0x180005400`
- `0x180005760`
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
- `0x180019dd0`
- `0x180019e6c`
- `0x180019e90`
- `0x18001a006`
- `0x18001a564`
- `0x18001a670`
- `0x18001ac24`
- `0x18001ae71`
- `0x18001b23c`
- `0x18001b519`
- `0x18001b9f0`
- `0x18001bdbb`

## callees

- `0x180005b90`
- `0x18001c010`

## import_xrefs

- `BrokerLib!BrUnlockBroker` at `0x180005bde`
- `BrokerLib!BrUnlockBroker` at `0x180005bde`

## pseudocode

```c
void __fastcall Broker::TimeBroker::BrokerLock::~BrokerLock(Broker::TimeBroker::BrokerLock *this)
{
  volatile signed __int32 *v1; // rbx
  Broker::TimeBroker *v3; // rcx

  v1 = (volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1);
  if ( *(&Broker::TimeBroker::Instance + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1) + 2);
    v1 = (volatile signed __int32 *)*(&Broker::TimeBroker::Instance + 1);
  }
  v3 = Broker::TimeBroker::Instance;
  if ( !*(_DWORD *)this )
  {
    *((_QWORD *)Broker::TimeBroker::Instance + 26) = *((_QWORD *)Broker::TimeBroker::Instance + 25);
    *((_QWORD *)v3 + 25) = 0;
  }
  if ( (unsigned int)BrUnlockBroker(*((_QWORD *)v3 + 24), *(unsigned int *)this) )
    __int2c();
  if ( v1 && _InterlockedExchangeAdd(v1 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v1)(v1);
    if ( _InterlockedExchangeAdd(v1 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v1 + 8LL))(v1);
  }
}

```

## disassembly

```asm
0x180005b90  push    rbx
0x180005b92  sub     rsp, 20h
0x180005b96  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180005b9d  mov     rdx, rcx
0x180005ba0  test    rbx, rbx
0x180005ba3  jz      short loc_180005BB0
0x180005ba5  lock inc dword ptr [rbx+8]
0x180005ba9  mov     rbx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A+8; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180005bb0  cmp     dword ptr [rdx], 0
0x180005bb3  mov     rcx, qword ptr cs:?Instance@TimeBroker@Broker@@0V?$shared_ptr@VTimeBroker@Broker@@@std@@A; std::shared_ptr<Broker::TimeBroker> Broker::TimeBroker::Instance
0x180005bba  jnz     short loc_180005BD5
0x180005bbc  mov     rax, [rcx+0C8h]
0x180005bc3  mov     [rcx+0D0h], rax
0x180005bca  mov     qword ptr [rcx+0C8h], 0
0x180005bd5  mov     edx, [rdx]
0x180005bd7  mov     rcx, [rcx+0C0h]
0x180005bde  call    cs:__imp_BrUnlockBroker
0x180005be4  test    eax, eax
0x180005be6  jnz     short loc_180005C37
0x180005be8  test    rbx, rbx
0x180005beb  jz      short loc_180005C08
0x180005bed  mov     [rsp+28h+arg_0], rdi
0x180005bf2  mov     edi, 0FFFFFFFFh
0x180005bf7  mov     eax, edi
0x180005bf9  lock xadd [rbx+8], eax
0x180005bfe  cmp     eax, 1
0x180005c01  jz      short loc_180005C0E
0x180005c03  mov     rdi, [rsp+28h+arg_0]
0x180005c08  add     rsp, 20h
0x180005c0c  pop     rbx
0x180005c0d  retn
0x180005c0e  mov     rax, [rbx]
0x180005c11  mov     rcx, rbx
0x180005c14  mov     rax, [rax]
0x180005c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1c  lock xadd [rbx+0Ch], edi
0x180005c21  cmp     edi, 1
0x180005c24  jnz     short loc_180005C03
0x180005c26  mov     rax, [rbx]
0x180005c29  mov     rcx, rbx
0x180005c2c  mov     rax, [rax+8]
0x180005c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c35  jmp     short loc_180005C03
0x180005c37  int     2Ch; Windows NT - assertion failure
0x180005c39  jmp     short loc_180005BE8
```
