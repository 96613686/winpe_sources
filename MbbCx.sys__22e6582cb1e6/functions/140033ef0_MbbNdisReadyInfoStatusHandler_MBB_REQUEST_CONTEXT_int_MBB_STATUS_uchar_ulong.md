# MbbNdisReadyInfoStatusHandler(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)

- ea: `0x140033ef0`
- end: `0x140033f41`
- name: `?MbbNdisReadyInfoStatusHandler@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting`

## callees

- `0x1400287b0`
- `0x140028cb8`
- `0x1400291c0`
- `0x140033ef0`

## pseudocode

```c
__int64 __fastcall MbbNdisReadyInfoStatusHandler(__int64 a1, int a2, __int64 a3, __int64 a4, unsigned int a5)
{
  unsigned __int16 v5; // ax

  v5 = *(_WORD *)(**(_QWORD **)(a1 + 48) + 82LL);
  if ( v5 >= 0x400u )
    return MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX4>(
             (struct _MBB_REQUEST_CONTEXT *)a1,
             a2,
             a3,
             a4,
             a5);
  if ( v5 == 768 )
    return MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX3>(
             (struct _MBB_REQUEST_CONTEXT *)a1,
             a2,
             a3,
             a4,
             a5);
  return MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO>(
           (struct _MBB_REQUEST_CONTEXT *)a1,
           a2,
           a3,
           a4,
           a5);
}

```

## disassembly

```asm
0x140033ef0  sub     rsp, 38h
0x140033ef4  mov     rax, [rcx+30h]
0x140033ef8  mov     r10, [rax]
0x140033efb  movzx   eax, word ptr [r10+52h]
0x140033f00  mov     r10d, 400h
0x140033f06  cmp     ax, r10w
0x140033f0a  jb      short loc_140033F1B
0x140033f0c  mov     eax, [rsp+38h+arg_20]
0x140033f10  mov     [rsp+38h+var_18], eax; unsigned int
0x140033f14  call    ??$MbbNdisReadyInfoStatusHandlerHelper@U_MBB_SUBSCRIBER_READY_INFO_EX4@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX4>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140033f19  jmp     short loc_140033F3B
0x140033f1b  mov     r10d, 300h
0x140033f21  cmp     ax, r10w
0x140033f25  mov     eax, [rsp+38h+arg_20]
0x140033f29  mov     [rsp+38h+var_18], eax; unsigned int
0x140033f2d  jnz     short loc_140033F36
0x140033f2f  call    ??$MbbNdisReadyInfoStatusHandlerHelper@U_MBB_SUBSCRIBER_READY_INFO_EX3@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO_EX3>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140033f34  jmp     short loc_140033F3B
0x140033f36  call    ??$MbbNdisReadyInfoStatusHandlerHelper@U_MBB_SUBSCRIBER_READY_INFO@@@@YAHPEAU_MBB_REQUEST_CONTEXT@@HW4_MBB_STATUS@@PEAEK@Z; MbbNdisReadyInfoStatusHandlerHelper<_MBB_SUBSCRIBER_READY_INFO>(_MBB_REQUEST_CONTEXT *,int,_MBB_STATUS,uchar *,ulong)
0x140033f3b  add     rsp, 38h
0x140033f3f  retn
```
