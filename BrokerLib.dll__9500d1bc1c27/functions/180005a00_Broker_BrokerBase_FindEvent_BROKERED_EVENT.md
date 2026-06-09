# Broker::BrokerBase::FindEvent(_BROKERED_EVENT *)

- ea: `0x180005a00`
- end: `0x180005a70`
- name: `?FindEvent@BrokerBase@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@PEAU_BROKERED_EVENT@@@Z`
- size: `112`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180009460`
- `0x18000eb80`
- `0x18000fd10`
- `0x180016fb0`

## callees

- `0x180005a00`
- `0x180005a80`
- `0x180005b50`

## pseudocode

```c
_QWORD *__fastcall Broker::BrokerBase::FindEvent(__int64 a1, _QWORD *a2, unsigned __int64 a3)
{
  __int64 v5; // r9
  unsigned __int64 v7; // [rsp+50h] [rbp+18h] BYREF

  v7 = a3;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v5 = 0;
    if ( *(_QWORD *)(a1 + 8) )
      v5 = *(_QWORD *)(a1 + 8);
    WPP_SF__guid_(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids, v5);
  }
  Broker::BrokeredEventTable::Find((__int64 **)(a1 + 208), a2, &v7);
  return a2;
}

```

## disassembly

```asm
0x180005a00  mov     [rsp+arg_0], rbx
0x180005a05  mov     [rsp+arg_10], r8
0x180005a0a  push    rdi
0x180005a0b  sub     rsp, 30h
0x180005a0f  mov     rbx, rdx
0x180005a12  mov     rdi, rcx
0x180005a15  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a1c  test    dword ptr [rcx+1Ch], 800h
0x180005a23  jz      short loc_180005A4E
0x180005a25  cmp     byte ptr [rcx+19h], 5
0x180005a29  jb      short loc_180005A4E
0x180005a2b  mov     rax, [rdi+8]
0x180005a2f  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180005a36  mov     rcx, [rcx+10h]
0x180005a3a  xor     r9d, r9d
0x180005a3d  test    rax, rax
0x180005a40  mov     edx, 24h ; '$'
0x180005a45  cmovnz  r9, rax
0x180005a49  call    WPP_SF__guid_
0x180005a4e  lea     rcx, [rdi+0D0h]
0x180005a55  mov     rdx, rbx
0x180005a58  lea     r8, [rsp+38h+arg_10]
0x180005a5d  call    ?Find@BrokeredEventTable@Broker@@QEAA?AV?$shared_ptr@VBrokerEvent@Broker@@@std@@AEBQEAU_BROKERED_EVENT@@@Z; Broker::BrokeredEventTable::Find(_BROKERED_EVENT * const &)
0x180005a62  mov     rax, rbx
0x180005a65  mov     rbx, [rsp+38h+arg_0]
0x180005a6a  add     rsp, 30h
0x180005a6e  pop     rdi
0x180005a6f  retn
```
