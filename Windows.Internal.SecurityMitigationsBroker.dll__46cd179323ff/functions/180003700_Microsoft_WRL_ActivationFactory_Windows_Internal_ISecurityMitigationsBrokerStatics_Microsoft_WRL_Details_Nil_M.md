# Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`scalar deleting destructor'(uint)

- ea: `0x180003700`
- end: `0x180003723`
- name: `??_G?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `35`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001390`
- `0x180003700`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[5] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180003700  push    rbx
0x180003702  sub     rsp, 20h
0x180003706  mov     dword ptr [rcx+14h], 0C0000001h
0x18000370d  mov     rbx, rcx
0x180003710  test    dl, 1
0x180003713  jz      short loc_18000371A
0x180003715  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000371a  mov     rax, rbx
0x18000371d  add     rsp, 20h
0x180003721  pop     rbx
0x180003722  retn
```
