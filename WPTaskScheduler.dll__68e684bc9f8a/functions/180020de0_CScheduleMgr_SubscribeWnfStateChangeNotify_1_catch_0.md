# _CScheduleMgr::SubscribeWnfStateChangeNotify_::_1_::catch$0

- ea: `0x180020de0`
- end: `0x180020e1b`
- name: `_CScheduleMgr::SubscribeWnfStateChangeNotify_::_1_::catch$0`
- size: `59`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020df5`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x180020df5`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::SubscribeWnfStateChangeNotify_::_1_::catch_0(__int64 a1, __int64 a2)
{
  _QWORD *v3; // rbx

  v3 = *(_QWORD **)(a2 + 120);
  RtlUnsubscribeWnfNotificationWaitForCompletion(*v3);
  *v3 = 0;
  *(_DWORD *)(a2 + 64) = -1073741823;
  return 0;
}

```

## disassembly

```asm
0x180020de0  mov     [rsp+arg_8], rdx
0x180020de5  push    rbx
0x180020de6  push    rbp
0x180020de7  sub     rsp, 48h
0x180020deb  mov     rbp, rdx
0x180020dee  mov     rbx, [rbp+78h]
0x180020df2  mov     rcx, [rbx]
0x180020df5  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180020dfb  mov     qword ptr [rbx], 0
0x180020e02  mov     dword ptr [rbp+40h], 0C0000001h
0x180020e09  mov     rax, 0
0x180020e13  add     rsp, 48h
0x180020e17  pop     rbp
0x180020e18  pop     rbx
0x180020e19  retn
```
