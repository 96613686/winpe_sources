# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(TrustLevel *)

- ea: `0x180003ce0`
- end: `0x180003d0c`
- name: `?GetTrustLevel@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIServiceUiToastStatics@Calls@ApplicationModel@WindowsInternal@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJPEAW4TrustLevel@@@Z`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003d20`

## callees

- `0x180003ce0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IServiceUiToastStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::GetTrustLevel(
        __int64 a1,
        int *a2)
{
  __int64 v2; // rax
  int v4; // eax

  v2 = *(_QWORD *)(a1 + 48);
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
0x180003ce0  push    rbx
0x180003ce2  sub     rsp, 20h
0x180003ce6  mov     rax, [rcx+30h]
0x180003cea  mov     rbx, rdx
0x180003ced  test    rax, rax
0x180003cf0  jz      short loc_180003CFD
0x180003cf2  mov     rax, [rax+10h]
0x180003cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003cfb  jmp     short loc_180003D02
0x180003cfd  mov     eax, 2
0x180003d02  mov     [rbx], eax
0x180003d04  xor     eax, eax
0x180003d06  add     rsp, 20h
0x180003d0a  pop     rbx
0x180003d0b  retn
```
