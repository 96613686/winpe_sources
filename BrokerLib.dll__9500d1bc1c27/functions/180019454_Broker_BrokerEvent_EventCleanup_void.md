# Broker::BrokerEvent::EventCleanup(void)

- ea: `0x180019454`
- end: `0x1800194bd`
- name: `?EventCleanup@BrokerEvent@Broker@@QEAAXXZ`
- size: `105`
- prototype: `void __fastcall(Broker::BrokerEvent *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800183bc`

## callees

- `0x18000e9f4`
- `0x180015af0`
- `0x180019454`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180019493`
- `ntdll!NtDeleteWnfStateName` at `0x180019493`

## pseudocode

```c
void __fastcall Broker::BrokerEvent::EventCleanup(Broker::BrokerEvent *this)
{
  __int64 v1; // rax
  __int64 v3; // [rsp+20h] [rbp-18h] BYREF

  v1 = *((_QWORD *)this + 2);
  v3 = 0;
  v3 = *(_QWORD *)(v1 + 16);
  if ( v3 )
    NtDeleteWnfStateName(&v3);
  BciHeapFree(*((void **)this + 2));
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180019454  push    rbx
0x180019456  sub     rsp, 30h
0x18001945a  mov     rax, cs:__security_cookie
0x180019461  xor     rax, rsp
0x180019464  mov     [rsp+38h+var_10], rax
0x180019469  mov     rax, [rcx+10h]
0x18001946d  mov     rbx, rcx
0x180019470  mov     [rsp+38h+var_18], 0
0x180019479  mov     rax, [rax+10h]
0x18001947d  mov     [rsp+38h+var_18], rax
0x180019482  test    eax, eax
0x180019484  jnz     short loc_18001948E
0x180019486  shr     rax, 20h
0x18001948a  test    eax, eax
0x18001948c  jz      short loc_180019499
0x18001948e  lea     rcx, [rsp+38h+var_18]
0x180019493  call    cs:__imp_NtDeleteWnfStateName
0x180019499  mov     rcx, [rbx+10h]; void *
0x18001949d  call    ?BciHeapFree@@YAHPEAX@Z; BciHeapFree(void *)
0x1800194a2  mov     qword ptr [rbx+10h], 0
0x1800194aa  mov     rcx, [rsp+38h+var_10]
0x1800194af  xor     rcx, rsp; StackCookie
0x1800194b2  call    __security_check_cookie
0x1800194b7  add     rsp, 30h
0x1800194bb  pop     rbx
0x1800194bc  retn
```
