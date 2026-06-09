# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(TrustLevel *)

- ea: `0x180003d30`
- end: `0x180003d5c`
- name: `?GetTrustLevel@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAW4TrustLevel@@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003d70`

## callees

- `0x180003d30`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(
        __int64 a1,
        int *a2)
{
  __int64 v2; // rax
  int v4; // eax

  v2 = *(_QWORD *)(a1 + 56);
  if ( v2 )
    v4 = (*(__int64 (**)(void))(v2 + 16))();
  else
    v4 = 2;
  *a2 = v4;
  return 0;
}

```

## disassembly

```asm
0x180003d30  push    rbx
0x180003d32  sub     rsp, 20h
0x180003d36  mov     rax, [rcx+38h]
0x180003d3a  mov     rbx, rdx
0x180003d3d  test    rax, rax
0x180003d40  jz      short loc_180003D4D
0x180003d42  mov     rax, [rax+10h]
0x180003d46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4b  jmp     short loc_180003D52
0x180003d4d  mov     eax, 2
0x180003d52  mov     [rbx], eax
0x180003d54  xor     eax, eax
0x180003d56  add     rsp, 20h
0x180003d5a  pop     rbx
0x180003d5b  retn
```
