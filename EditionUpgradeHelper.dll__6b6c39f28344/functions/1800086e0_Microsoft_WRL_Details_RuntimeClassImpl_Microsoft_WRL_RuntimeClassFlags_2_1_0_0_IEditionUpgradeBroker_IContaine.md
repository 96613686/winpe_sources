# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::AddRef(void)

- ea: `0x1800086e0`
- end: `0x180008709`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `41`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008710`
- `0x180008720`
- `0x180008730`

## callees

- `0x1800086e0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::AddRef(
        __int64 a1)
{
  unsigned int v1; // r9d
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 36);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 36), v2 + 1, v2) )
      return (unsigned int)(v2 + 1);
  }
  return v1;
}

```

## disassembly

```asm
0x1800086e0  mov     r9d, 7FFFFFFFh
0x1800086e6  jmp     short loc_1800086F6
0x1800086e8  lea     edx, [r8+1]
0x1800086ec  mov     eax, r8d
0x1800086ef  lock cmpxchg [rcx+24h], edx
0x1800086f4  jz      short loc_180008701
0x1800086f6  mov     r8d, [rcx+24h]
0x1800086fa  cmp     r8d, r9d
0x1800086fd  jnz     short loc_1800086E8
0x1800086ff  jmp     short loc_180008705
0x180008701  lea     r9d, [r8+1]
0x180008705  mov     eax, r9d
0x180008708  retn
```
