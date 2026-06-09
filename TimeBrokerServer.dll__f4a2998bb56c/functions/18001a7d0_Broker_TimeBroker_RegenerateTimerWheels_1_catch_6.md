# _Broker::TimeBroker::RegenerateTimerWheels_::_1_::catch$6

- ea: `0x18001a7d0`
- end: `0x18001a84d`
- name: `_Broker::TimeBroker::RegenerateTimerWheels_::_1_::catch$6`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001a7d0`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001a81b`
- `BrokerLib!BrBufferFree` at `0x18001a81b`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::RegenerateTimerWheels_::_1_::catch_6(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(unsigned int *)(a2 + 208));
  if ( *(_QWORD *)(a2 + 280) )
    BrBufferFree();
  *(_QWORD *)(a2 + 176) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 184);
  return 0;
}

```

## disassembly

```asm
0x18001a7d0  mov     [rsp+arg_8], rdx
0x18001a7d5  push    rbp
0x18001a7d6  sub     rsp, 30h
0x18001a7da  mov     rbp, rdx
0x18001a7dd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a7e4  test    dword ptr [rcx+1Ch], 100h
0x18001a7eb  jz      short loc_18001A80F
0x18001a7ed  cmp     byte ptr [rcx+19h], 2
0x18001a7f1  jb      short loc_18001A80F
0x18001a7f3  mov     edx, 34h ; '4'
0x18001a7f8  mov     r9d, [rbp+0D0h]
0x18001a7ff  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001a806  mov     rcx, [rcx+10h]
0x18001a80a  call    WPP_SF_d
0x18001a80f  mov     rcx, [rbp+118h]
0x18001a816  test    rcx, rcx
0x18001a819  jz      short loc_18001A821
0x18001a81b  call    cs:__imp_BrBufferFree
0x18001a821  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001a828  mov     [rbp+0B0h], rax
0x18001a82f  lea     rcx, [rbp+0B8h]
0x18001a836  call    _o___std_exception_destroy_0
0x18001a83b  nop
0x18001a83c  mov     rax, 0
0x18001a846  add     rsp, 30h
0x18001a84a  pop     rbp
0x18001a84b  retn
```
