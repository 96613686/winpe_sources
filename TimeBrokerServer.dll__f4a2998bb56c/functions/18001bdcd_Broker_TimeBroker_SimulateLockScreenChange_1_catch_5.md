# _Broker::TimeBroker::SimulateLockScreenChange_::_1_::catch$5

- ea: `0x18001bdcd`
- end: `0x18001be47`
- name: `_Broker::TimeBroker::SimulateLockScreenChange_::_1_::catch$5`
- size: `122`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003800`
- `0x180013882`
- `0x18001bdcd`

## import_xrefs

- `BrokerLib!BrBufferFree` at `0x18001be15`
- `BrokerLib!BrBufferFree` at `0x18001be15`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::SimulateLockScreenChange_::_1_::catch_5(__int64 a1, __int64 a2)
{
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      119,
      &WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids,
      *(unsigned int *)(a2 + 184));
  if ( *(_QWORD *)(a2 + 48) )
    BrBufferFree();
  *(_QWORD *)(a2 + 152) = &std::exception::`vftable';
  o___std_exception_destroy_0(a2 + 160);
  return 0;
}

```

## disassembly

```asm
0x18001bdcd  mov     [rsp+arg_8], rdx
0x18001bdd2  push    rbp
0x18001bdd3  sub     rsp, 30h
0x18001bdd7  mov     rbp, rdx
0x18001bdda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bde1  test    dword ptr [rcx+1Ch], 100h
0x18001bde8  jz      short loc_18001BE0C
0x18001bdea  cmp     byte ptr [rcx+19h], 2
0x18001bdee  jb      short loc_18001BE0C
0x18001bdf0  mov     edx, 77h ; 'w'
0x18001bdf5  mov     r9d, [rbp+0B8h]
0x18001bdfc  lea     r8, WPP_8cfee079bb8a3683490f419e7fb9c12a_Traceguids
0x18001be03  mov     rcx, [rcx+10h]
0x18001be07  call    WPP_SF_d
0x18001be0c  mov     rcx, [rbp+30h]
0x18001be10  test    rcx, rcx
0x18001be13  jz      short loc_18001BE1B
0x18001be15  call    cs:__imp_BrBufferFree
0x18001be1b  lea     rax, ??_7exception@std@@6B@; const std::exception::`vftable'
0x18001be22  mov     [rbp+98h], rax
0x18001be29  lea     rcx, [rbp+0A0h]
0x18001be30  call    _o___std_exception_destroy_0
0x18001be35  nop
0x18001be36  mov     rax, 0
0x18001be40  add     rsp, 30h
0x18001be44  pop     rbp
0x18001be45  retn
```
