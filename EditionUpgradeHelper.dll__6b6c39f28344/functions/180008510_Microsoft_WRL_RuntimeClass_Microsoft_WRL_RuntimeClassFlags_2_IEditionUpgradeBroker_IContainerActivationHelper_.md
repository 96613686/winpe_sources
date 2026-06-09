# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`scalar deleting destructor'(uint)

- ea: `0x180008510`
- end: `0x180008538`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001cb0`
- `0x180008510`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[9] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180008510  push    rbx
0x180008512  sub     rsp, 20h
0x180008516  mov     dword ptr [rcx+24h], 0C0000001h
0x18000851d  mov     rbx, rcx
0x180008520  test    dl, 1
0x180008523  jz      short loc_18000852F
0x180008525  mov     edx, 28h ; '('; unsigned __int64
0x18000852a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000852f  mov     rax, rbx
0x180008532  add     rsp, 20h
0x180008536  pop     rbx
0x180008537  retn
```
