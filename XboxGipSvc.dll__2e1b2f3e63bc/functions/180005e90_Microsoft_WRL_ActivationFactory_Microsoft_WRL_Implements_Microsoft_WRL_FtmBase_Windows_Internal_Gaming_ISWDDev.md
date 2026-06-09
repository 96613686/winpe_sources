# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005e90`
- end: `0x180005f1f`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005f30`
- `0x180005f40`
- `0x180005f50`

## callees

- `0x180004e10`
- `0x180005e90`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
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
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                a1,
                a2,
                a3);
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180005e90  push    rbx
0x180005e92  sub     rsp, 20h
0x180005e96  mov     qword ptr [r8], 0
0x180005e9d  cmp     dword ptr [rdx], 0
0x180005ea0  jnz     short loc_180005EC0
0x180005ea2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180005ea8  cmp     [rdx+4], eax
0x180005eab  jnz     short loc_180005EFC
0x180005ead  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180005eb3  cmp     [rdx+8], eax
0x180005eb6  jnz     short loc_180005EFC
0x180005eb8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180005ebe  jmp     short loc_180005EE4
0x180005ec0  cmp     dword ptr [rdx], 0AF86E2E0h
0x180005ec6  jnz     short loc_180005EFC
0x180005ec8  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x180005ece  cmp     [rdx+4], eax
0x180005ed1  jnz     short loc_180005EFC
0x180005ed3  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180005ed9  cmp     [rdx+8], eax
0x180005edc  jnz     short loc_180005EFC
0x180005ede  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180005ee4  cmp     [rdx+0Ch], eax
0x180005ee7  jnz     short loc_180005EFC
0x180005ee9  mov     [r8], rcx
0x180005eec  mov     rax, [rcx]
0x180005eef  mov     rax, [rax+8]
0x180005ef3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef8  xor     ebx, ebx
0x180005efa  jmp     short loc_180005F17
0x180005efc  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180005f01  mov     ebx, eax
0x180005f03  test    eax, eax
0x180005f05  js      short loc_180005F17
0x180005f07  mov     rcx, [r8]
0x180005f0a  mov     rdx, [rcx]
0x180005f0d  mov     rax, [rdx+8]
0x180005f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f16  nop
0x180005f17  mov     eax, ebx
0x180005f19  add     rsp, 20h
0x180005f1d  pop     rbx
0x180005f1e  retn
```
