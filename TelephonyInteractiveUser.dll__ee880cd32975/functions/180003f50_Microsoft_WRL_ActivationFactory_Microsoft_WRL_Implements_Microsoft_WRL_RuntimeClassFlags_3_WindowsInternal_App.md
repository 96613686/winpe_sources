# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180003f50`
- end: `0x180003fde`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `142`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003ff0`
- `0x180004000`
- `0x1800041a0`

## callees

- `0x1800035fc`
- `0x180003f50`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int CanCastTo; // ebx
  _QWORD *v5; // r8

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != -1350114592
      || a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_11;
    }
    v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_11;
    }
    v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] == v3 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
LABEL_11:
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo();
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180003f50  push    rbx
0x180003f52  sub     rsp, 20h
0x180003f56  mov     qword ptr [r8], 0
0x180003f5d  cmp     dword ptr [rdx], 0
0x180003f60  jnz     short loc_180003F80
0x180003f62  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180003f68  cmp     [rdx+4], eax
0x180003f6b  jnz     short loc_180003FBC
0x180003f6d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180003f73  cmp     [rdx+8], eax
0x180003f76  jnz     short loc_180003FBC
0x180003f78  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180003f7e  jmp     short loc_180003FA4
0x180003f80  cmp     dword ptr [rdx], 0AF86E2E0h
0x180003f86  jnz     short loc_180003FBC
0x180003f88  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x180003f8e  cmp     [rdx+4], eax
0x180003f91  jnz     short loc_180003FBC
0x180003f93  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180003f99  cmp     [rdx+8], eax
0x180003f9c  jnz     short loc_180003FBC
0x180003f9e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180003fa4  cmp     [rdx+0Ch], eax
0x180003fa7  jnz     short loc_180003FBC
0x180003fa9  mov     [r8], rcx
0x180003fac  mov     rax, [rcx]
0x180003faf  mov     rax, [rax+8]
0x180003fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fb8  xor     ebx, ebx
0x180003fba  jmp     short loc_180003FD6
0x180003fbc  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180003fc1  mov     ebx, eax
0x180003fc3  test    eax, eax
0x180003fc5  js      short loc_180003FD6
0x180003fc7  mov     rcx, [r8]
0x180003fca  mov     rdx, [rcx]
0x180003fcd  mov     rax, [rdx+8]
0x180003fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd6  mov     eax, ebx
0x180003fd8  add     rsp, 20h
0x180003fdc  pop     rbx
0x180003fdd  retn
```
