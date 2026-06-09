# _Broker::TimeBroker::OnEnableEvent_::_1_::catch$8

- ea: `0x18001bbc0`
- end: `0x18001bc23`
- name: `_Broker::TimeBroker::OnEnableEvent_::_1_::catch$8`
- size: `99`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180016958`
- `0x18001bbc0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Broker::TimeBroker::OnEnableEvent_::_1_::catch_8(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // r8

  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 192) + 8LL))(*(_QWORD *)(a2 + 192));
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 112, v4, v3);
  }
  *(_DWORD *)(a2 + 80) = 1359;
  return 0;
}

```

## disassembly

```asm
0x18001bbc0  mov     [rsp+arg_8], rdx
0x18001bbc5  push    rbp
0x18001bbc6  sub     rsp, 50h
0x18001bbca  mov     rbp, rdx
0x18001bbcd  mov     rax, cs:WPP_GLOBAL_Control
0x18001bbd4  test    byte ptr [rax+1Ch], 1
0x18001bbd8  jz      short loc_18001BC0B
0x18001bbda  cmp     byte ptr [rax+19h], 2
0x18001bbde  jb      short loc_18001BC0B
0x18001bbe0  mov     rcx, [rbp+0C0h]
0x18001bbe7  mov     rax, [rcx]
0x18001bbea  mov     rax, [rax+8]
0x18001bbee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbf3  mov     edx, 70h ; 'p'
0x18001bbf8  mov     r9, rax
0x18001bbfb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bc02  mov     rcx, [rcx+10h]
0x18001bc06  call    WPP_SF_s
0x18001bc0b  mov     dword ptr [rbp+50h], 54Fh
0x18001bc12  mov     rax, 0
0x18001bc1c  add     rsp, 50h
0x18001bc20  pop     rbp
0x18001bc21  retn
```
