# _Broker::TimeBroker::OnSystemTimeChange_::_1_::catch$6

- ea: `0x18001a740`
- end: `0x18001a7bd`
- name: `_Broker::TimeBroker::OnSystemTimeChange_::_1_::catch$6`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001a740`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001a78b`
- `BrokerLib!BrBufferFree` at `0x18001a78b`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnSystemTimeChange_::_1_::catch_6(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
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
0x18001a740  mov     [rsp+arg_8], rdx
0x18001a745  push    rbp
0x18001a746  sub     rsp, 30h
0x18001a74a  mov     rbp, rdx
0x18001a74d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a754  test    dword ptr [rcx+1Ch], 100h
0x18001a75b  jz      short loc_18001A77F
0x18001a75d  cmp     byte ptr [rcx+19h], 2
0x18001a761  jb      short loc_18001A77F
0x18001a763  mov     edx, 21h ; '!'
0x18001a768  mov     r9d, [rbp+0E8h]
0x18001a76f  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001a776  mov     rcx, [rcx+10h]
0x18001a77a  call    WPP_SF_d
0x18001a77f  mov     rcx, [rbp+138h]
0x18001a786  test    rcx, rcx
0x18001a789  jz      short loc_18001A791
0x18001a78b  call    cs:__imp_BrBufferFree
0x18001a791  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001a798  mov     [rbp+0C8h], rax
0x18001a79f  lea     rcx, [rbp+0D0h]
0x18001a7a6  call    _o___std_exception_destroy_0
0x18001a7ab  nop
0x18001a7ac  mov     rax, 0
0x18001a7b6  add     rsp, 30h
0x18001a7ba  pop     rbp
0x18001a7bb  retn
```
