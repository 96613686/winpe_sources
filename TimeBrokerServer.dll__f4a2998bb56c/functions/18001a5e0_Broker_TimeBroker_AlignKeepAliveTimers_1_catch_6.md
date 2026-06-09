# _Broker::TimeBroker::AlignKeepAliveTimers_::_1_::catch$6

- ea: `0x18001a5e0`
- end: `0x18001a65d`
- name: `_Broker::TimeBroker::AlignKeepAliveTimers_::_1_::catch$6`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001a5e0`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001a62b`
- `BrokerLib!BrBufferFree` at `0x18001a62b`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::AlignKeepAliveTimers_::_1_::catch_6(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      98,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(unsigned int *)(a2 + 200));
  if ( *(_QWORD *)(a2 + 280) )
    BrBufferFree();
  *(_QWORD *)(a2 + 168) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 176);
  return 0;
}

```

## disassembly

```asm
0x18001a5e0  mov     [rsp+arg_8], rdx
0x18001a5e5  push    rbp
0x18001a5e6  sub     rsp, 30h
0x18001a5ea  mov     rbp, rdx
0x18001a5ed  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5f4  test    dword ptr [rcx+1Ch], 100h
0x18001a5fb  jz      short loc_18001A61F
0x18001a5fd  cmp     byte ptr [rcx+19h], 2
0x18001a601  jb      short loc_18001A61F
0x18001a603  mov     edx, 62h ; 'b'
0x18001a608  mov     r9d, [rbp+0C8h]
0x18001a60f  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001a616  mov     rcx, [rcx+10h]
0x18001a61a  call    WPP_SF_d
0x18001a61f  mov     rcx, [rbp+118h]
0x18001a626  test    rcx, rcx
0x18001a629  jz      short loc_18001A631
0x18001a62b  call    cs:__imp_BrBufferFree
0x18001a631  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001a638  mov     [rbp+0A8h], rax
0x18001a63f  lea     rcx, [rbp+0B0h]
0x18001a646  call    _o___std_exception_destroy_0
0x18001a64b  nop
0x18001a64c  mov     rax, 0
0x18001a656  add     rsp, 30h
0x18001a65a  pop     rbp
0x18001a65b  retn
```
