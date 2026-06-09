# _Broker::TimeBroker::OnNetworkStateChange_::_1_::catch$6

- ea: `0x18001a6b0`
- end: `0x18001a72d`
- name: `_Broker::TimeBroker::OnNetworkStateChange_::_1_::catch$6`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001a6b0`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001a6fb`
- `BrokerLib!BrBufferFree` at `0x18001a6fb`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnNetworkStateChange_::_1_::catch_6(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(unsigned int *)(a2 + 232));
  if ( *(_QWORD *)(a2 + 312) )
    BrBufferFree();
  *(_QWORD *)(a2 + 200) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 208);
  return 0;
}

```

## disassembly

```asm
0x18001a6b0  mov     [rsp+arg_8], rdx
0x18001a6b5  push    rbp
0x18001a6b6  sub     rsp, 30h
0x18001a6ba  mov     rbp, rdx
0x18001a6bd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6c4  test    dword ptr [rcx+1Ch], 100h
0x18001a6cb  jz      short loc_18001A6EF
0x18001a6cd  cmp     byte ptr [rcx+19h], 2
0x18001a6d1  jb      short loc_18001A6EF
0x18001a6d3  mov     edx, 1Dh
0x18001a6d8  mov     r9d, [rbp+0E8h]
0x18001a6df  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001a6e6  mov     rcx, [rcx+10h]
0x18001a6ea  call    WPP_SF_d
0x18001a6ef  mov     rcx, [rbp+138h]
0x18001a6f6  test    rcx, rcx
0x18001a6f9  jz      short loc_18001A701
0x18001a6fb  call    cs:__imp_BrBufferFree
0x18001a701  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001a708  mov     [rbp+0C8h], rax
0x18001a70f  lea     rcx, [rbp+0D0h]
0x18001a716  call    _o___std_exception_destroy_0
0x18001a71b  nop
0x18001a71c  mov     rax, 0
0x18001a726  add     rsp, 30h
0x18001a72a  pop     rbp
0x18001a72b  retn
```
