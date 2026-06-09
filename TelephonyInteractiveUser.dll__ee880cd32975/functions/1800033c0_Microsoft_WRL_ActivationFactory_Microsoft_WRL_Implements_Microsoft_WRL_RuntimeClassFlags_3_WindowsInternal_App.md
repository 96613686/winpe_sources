# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vector deleting destructor'(uint)

- ea: `0x1800033c0`
- end: `0x1800033e8`
- name: `??_E?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800021b4`
- `0x1800033c0`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vector deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[11] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x1800033c0  push    rbx
0x1800033c2  sub     rsp, 20h
0x1800033c6  mov     dword ptr [rcx+2Ch], 0C0000001h
0x1800033cd  mov     rbx, rcx
0x1800033d0  test    dl, 1
0x1800033d3  jz      short loc_1800033DF
0x1800033d5  mov     edx, 48h ; 'H'
0x1800033da  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800033df  mov     rax, rbx
0x1800033e2  add     rsp, 20h
0x1800033e6  pop     rbx
0x1800033e7  retn
```
