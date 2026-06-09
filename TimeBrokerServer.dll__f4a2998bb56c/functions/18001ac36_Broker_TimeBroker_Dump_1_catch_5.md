# _Broker::TimeBroker::Dump_::_1_::catch$5

- ea: `0x18001ac36`
- end: `0x18001acb3`
- name: `_Broker::TimeBroker::Dump_::_1_::catch$5`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001ac36`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001ac81`
- `BrokerLib!BrBufferFree` at `0x18001ac81`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::Dump_::_1_::catch_5(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      46,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(unsigned int *)(a2 + 184));
  if ( *(_QWORD *)(a2 + 264) )
    BrBufferFree();
  *(_QWORD *)(a2 + 152) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 160);
  return 0;
}

```

## disassembly

```asm
0x18001ac36  mov     [rsp+arg_8], rdx
0x18001ac3b  push    rbp
0x18001ac3c  sub     rsp, 30h
0x18001ac40  mov     rbp, rdx
0x18001ac43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ac4a  test    dword ptr [rcx+1Ch], 100h
0x18001ac51  jz      short loc_18001AC75
0x18001ac53  cmp     byte ptr [rcx+19h], 2
0x18001ac57  jb      short loc_18001AC75
0x18001ac59  mov     edx, 2Eh ; '.'
0x18001ac5e  mov     r9d, [rbp+0B8h]
0x18001ac65  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001ac6c  mov     rcx, [rcx+10h]
0x18001ac70  call    WPP_SF_d
0x18001ac75  mov     rcx, [rbp+108h]
0x18001ac7c  test    rcx, rcx
0x18001ac7f  jz      short loc_18001AC87
0x18001ac81  call    cs:__imp_BrBufferFree
0x18001ac87  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001ac8e  mov     [rbp+98h], rax
0x18001ac95  lea     rcx, [rbp+0A0h]
0x18001ac9c  call    _o___std_exception_destroy_0
0x18001aca1  nop
0x18001aca2  mov     rax, 0
0x18001acac  add     rsp, 30h
0x18001acb0  pop     rbp
0x18001acb1  retn
```
