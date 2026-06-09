# Broker::TimeBroker::OnResumeFromSleep(void)

- ea: `0x180001ba4`
- end: `0x180001c0d`
- name: `?OnResumeFromSleep@TimeBroker@Broker@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(Broker::TimeBroker *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011280`

## callees

- `0x180001ba4`
- `0x180001c14`
- `0x180002400`
- `0x180003840`
- `0x180005b90`

## pseudocode

```c
void __fastcall Broker::TimeBroker::OnResumeFromSleep(Broker::TimeBroker *this)
{
  char v2; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_QWORD *)this + 24) )
  {
    Broker::TimeBroker::BrokerLock::BrokerLock((Broker::TimeBroker::BrokerLock *)&v2, 0);
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids);
    Broker::TimeBroker::OnTimerExpired(this, 1);
    Broker::TimeBroker::BrokerLock::~BrokerLock((Broker::TimeBroker::BrokerLock *)&v2);
  }
}

```

## disassembly

```asm
0x180001ba4  push    rbx
0x180001ba6  sub     rsp, 20h
0x180001baa  mov     rbx, rcx
0x180001bad  cmp     qword ptr [rcx+0C0h], 0
0x180001bb5  jz      short loc_180001C07
0x180001bb7  xor     edx, edx; int
0x180001bb9  lea     rcx, [rsp+28h+arg_0]; this
0x180001bbe  call    ??0BrokerLock@TimeBroker@Broker@@QEAA@H@Z; Broker::TimeBroker::BrokerLock::BrokerLock(int)
0x180001bc3  nop
0x180001bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bcb  test    dword ptr [rcx+1Ch], 100h
0x180001bd2  jz      short loc_180001BEF
0x180001bd4  cmp     byte ptr [rcx+19h], 4
0x180001bd8  jb      short loc_180001BEF
0x180001bda  mov     edx, 25h ; '%'
0x180001bdf  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x180001be6  mov     rcx, [rcx+10h]
0x180001bea  call    WPP_SF_
0x180001bef  mov     edx, 1
0x180001bf4  mov     rcx, rbx
0x180001bf7  call    ?OnTimerExpired@TimeBroker@Broker@@AEAAXW4TimeSource@12@@Z; Broker::TimeBroker::OnTimerExpired(Broker::TimeBroker::TimeSource)
0x180001bfc  nop
0x180001bfd  lea     rcx, [rsp+28h+arg_0]; this
0x180001c02  call    ??1BrokerLock@TimeBroker@Broker@@QEAA@XZ; Broker::TimeBroker::BrokerLock::~BrokerLock(void)
0x180001c07  add     rsp, 20h
0x180001c0b  pop     rbx
0x180001c0c  retn
```
