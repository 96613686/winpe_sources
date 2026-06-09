# _Broker::TimeBroker::OnDeleteEvent_::_1_::catch$2

- ea: `0x18001b87b`
- end: `0x18001b8db`
- name: `_Broker::TimeBroker::OnDeleteEvent_::_1_::catch$2`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180016958`
- `0x18001b87b`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnDeleteEvent_::_1_::catch_2(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r8

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 8LL))(*(_QWORD *)(a2 + 32));
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, v4, v3);
  }
  *(_DWORD *)(a2 + 104) = 1359;
  return 0;
}

```

## disassembly

```asm
0x18001b87b  mov     [rsp+arg_8], rdx
0x18001b880  push    rbp
0x18001b881  sub     rsp, 20h
0x18001b885  mov     rbp, rdx
0x18001b888  mov     rax, cs:WPP_GLOBAL_Control
0x18001b88f  test    byte ptr [rax+1Ch], 1
0x18001b893  jz      short loc_18001B8C3
0x18001b895  cmp     byte ptr [rax+19h], 2
0x18001b899  jb      short loc_18001B8C3
0x18001b89b  mov     rcx, [rbp+20h]
0x18001b89f  mov     rax, [rcx]
0x18001b8a2  mov     rax, [rax+8]
0x18001b8a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8ab  mov     edx, 69h ; 'i'
0x18001b8b0  mov     r9, rax
0x18001b8b3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b8ba  mov     rcx, [rcx+10h]
0x18001b8be  call    WPP_SF_s
0x18001b8c3  mov     dword ptr [rbp+68h], 54Fh
0x18001b8ca  mov     rax, 0
0x18001b8d4  add     rsp, 20h
0x18001b8d8  pop     rbp
0x18001b8d9  retn
```
