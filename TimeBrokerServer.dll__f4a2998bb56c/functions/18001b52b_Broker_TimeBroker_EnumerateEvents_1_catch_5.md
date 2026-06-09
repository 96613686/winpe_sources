# _Broker::TimeBroker::EnumerateEvents_::_1_::catch$5

- ea: `0x18001b52b`
- end: `0x18001b59f`
- name: `_Broker::TimeBroker::EnumerateEvents_::_1_::catch$5`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001b52b`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001b573`
- `BrokerLib!BrBufferFree` at `0x18001b573`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::EnumerateEvents_::_1_::catch_5(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(unsigned int *)(a2 + 136));
  if ( *(_QWORD *)(a2 + 56) )
    BrBufferFree();
  *(_QWORD *)(a2 + 104) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 112);
  return 0;
}

```

## disassembly

```asm
0x18001b52b  mov     [rsp+arg_8], rdx
0x18001b530  push    rbp
0x18001b531  sub     rsp, 30h
0x18001b535  mov     rbp, rdx
0x18001b538  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b53f  test    dword ptr [rcx+1Ch], 100h
0x18001b546  jz      short loc_18001B56A
0x18001b548  cmp     byte ptr [rcx+19h], 2
0x18001b54c  jb      short loc_18001B56A
0x18001b54e  mov     edx, 18h
0x18001b553  mov     r9d, [rbp+88h]
0x18001b55a  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001b561  mov     rcx, [rcx+10h]
0x18001b565  call    WPP_SF_d
0x18001b56a  mov     rcx, [rbp+38h]
0x18001b56e  test    rcx, rcx
0x18001b571  jz      short loc_18001B579
0x18001b573  call    cs:__imp_BrBufferFree
0x18001b579  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001b580  mov     [rbp+68h], rax
0x18001b584  lea     rcx, [rbp+70h]
0x18001b588  call    _o___std_exception_destroy_0
0x18001b58d  nop
0x18001b58e  mov     rax, 0
0x18001b598  add     rsp, 30h
0x18001b59c  pop     rbp
0x18001b59d  retn
```
