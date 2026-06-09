# _Broker::TimeBroker::OnEnableEvent_::_1_::catch$9

- ea: `0x18001bc30`
- end: `0x18001bc93`
- name: `_Broker::TimeBroker::OnEnableEvent_::_1_::catch$9`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180016958`
- `0x18001bc30`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnEnableEvent_::_1_::catch_9(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r8

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 200) + 8LL))(*(_QWORD *)(a2 + 200));
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, v4, v3);
  }
  *(_DWORD *)(a2 + 80) = 1359;
  return 0;
}

```

## disassembly

```asm
0x18001bc30  mov     [rsp+arg_8], rdx
0x18001bc35  push    rbp
0x18001bc36  sub     rsp, 50h
0x18001bc3a  mov     rbp, rdx
0x18001bc3d  mov     rax, cs:WPP_GLOBAL_Control
0x18001bc44  test    byte ptr [rax+1Ch], 1
0x18001bc48  jz      short loc_18001BC7B
0x18001bc4a  cmp     byte ptr [rax+19h], 2
0x18001bc4e  jb      short loc_18001BC7B
0x18001bc50  mov     rcx, [rbp+0C8h]
0x18001bc57  mov     rax, [rcx]
0x18001bc5a  mov     rax, [rax+8]
0x18001bc5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc63  mov     edx, 71h ; 'q'
0x18001bc68  mov     r9, rax
0x18001bc6b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc72  mov     rcx, [rcx+10h]
0x18001bc76  call    WPP_SF_s
0x18001bc7b  mov     dword ptr [rbp+50h], 54Fh
0x18001bc82  mov     rax, 0
0x18001bc8c  add     rsp, 50h
0x18001bc90  pop     rbp
0x18001bc91  retn
```
