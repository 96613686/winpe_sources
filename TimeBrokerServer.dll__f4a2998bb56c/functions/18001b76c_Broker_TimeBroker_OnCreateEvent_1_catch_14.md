# _Broker::TimeBroker::OnCreateEvent_::_1_::catch$14

- ea: `0x18001b76c`
- end: `0x18001b7cf`
- name: `_Broker::TimeBroker::OnCreateEvent_::_1_::catch$14`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180016958`
- `0x18001b76c`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnCreateEvent_::_1_::catch_14(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r8

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 208) + 8LL))(*(_QWORD *)(a2 + 208));
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 101, v4, v3);
  }
  *(_DWORD *)(a2 + 100) = 1359;
  return 0;
}

```

## disassembly

```asm
0x18001b76c  mov     [rsp+arg_8], rdx
0x18001b771  push    rbp
0x18001b772  sub     rsp, 60h
0x18001b776  mov     rbp, rdx
0x18001b779  mov     rax, cs:WPP_GLOBAL_Control
0x18001b780  test    byte ptr [rax+1Ch], 1
0x18001b784  jz      short loc_18001B7B7
0x18001b786  cmp     byte ptr [rax+19h], 2
0x18001b78a  jb      short loc_18001B7B7
0x18001b78c  mov     rcx, [rbp+0D0h]
0x18001b793  mov     rax, [rcx]
0x18001b796  mov     rax, [rax+8]
0x18001b79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b79f  mov     edx, 65h ; 'e'
0x18001b7a4  mov     r9, rax
0x18001b7a7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b7ae  mov     rcx, [rcx+10h]
0x18001b7b2  call    WPP_SF_s
0x18001b7b7  mov     dword ptr [rbp+64h], 54Fh
0x18001b7be  mov     rax, 0
0x18001b7c8  add     rsp, 60h
0x18001b7cc  pop     rbp
0x18001b7cd  retn
```
