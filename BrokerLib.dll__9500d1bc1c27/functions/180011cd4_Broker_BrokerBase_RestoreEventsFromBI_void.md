# Broker::BrokerBase::RestoreEventsFromBI(void)

- ea: `0x180011cd4`
- end: `0x180011d62`
- name: `?RestoreEventsFromBI@BrokerBase@Broker@@AEAAXXZ`
- size: `142`
- prototype: `void __fastcall(Broker::BrokerBase *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000c4c0`

## callees

- `0x180004e38`
- `0x180005b50`
- `0x180011cd4`
- `0x180013ac8`
- `0x1800188c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Broker::BrokerBase::RestoreEventsFromBI(Broker::BrokerBase *this)
{
  struct _GUID *i; // rbx
  struct _GUID *v3[5]; // [rsp+20h] [rbp-28h] BYREF

  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  Broker::BILayer::EnumerateEventIds(v3, *((_QWORD *)this + 1));
  for ( i = v3[0]; i != v3[1]; ++i )
    Broker::BrokerBase::RestoreEventFromBI(this, i);
  if ( v3[0] )
    std::_Deallocate<16>(v3[0], ((char *)v3[2] - (char *)v3[0]) & 0xFFFFFFFFFFFFFFF0uLL);
}

```

## disassembly

```asm
0x180011cd4  mov     [rsp+arg_0], rbx
0x180011cd9  push    rdi
0x180011cda  sub     rsp, 40h
0x180011cde  mov     rdi, rcx
0x180011ce1  mov     rcx, cs:WPP_GLOBAL_Control
0x180011ce8  test    dword ptr [rcx+1Ch], 800h
0x180011cef  jz      short loc_180011D10
0x180011cf1  cmp     byte ptr [rcx+19h], 5
0x180011cf5  jb      short loc_180011D10
0x180011cf7  mov     edx, 2Dh ; '-'
0x180011cfc  mov     r9, [rdi+8]
0x180011d00  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180011d07  mov     rcx, [rcx+10h]
0x180011d0b  call    WPP_SF__guid_
0x180011d10  mov     rdx, [rdi+8]
0x180011d14  lea     rcx, [rsp+48h+var_28]
0x180011d19  call    ?EnumerateEventIds@BILayer@Broker@@YA?AV?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@AEBU_GUID@@@Z; Broker::BILayer::EnumerateEventIds(_GUID const &)
0x180011d1e  nop
0x180011d1f  mov     rbx, [rsp+48h+var_28]
0x180011d24  cmp     rbx, [rsp+48h+var_20]
0x180011d29  jz      short loc_180011D3C
0x180011d2b  mov     rdx, rbx; struct _GUID *
0x180011d2e  mov     rcx, rdi; this
0x180011d31  call    ?RestoreEventFromBI@BrokerBase@Broker@@AEAAXAEBU_GUID@@@Z; Broker::BrokerBase::RestoreEventFromBI(_GUID const &)
0x180011d36  add     rbx, 10h
0x180011d3a  jmp     short loc_180011D24
0x180011d3c  mov     rcx, [rsp+48h+var_28]
0x180011d41  test    rcx, rcx
0x180011d44  jz      short loc_180011D57
0x180011d46  mov     rdx, [rsp+48h+var_18]
0x180011d4b  sub     rdx, rcx
0x180011d4e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180011d52  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180011d57  mov     rbx, [rsp+48h+arg_0]
0x180011d5c  add     rsp, 40h
0x180011d60  pop     rdi
0x180011d61  retn
```
