# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180005dd0`
- end: `0x180005e5f`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005e70`
- `0x180005e80`
- `0x180005f80`

## callees

- `0x180004d40`
- `0x180005dd0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
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
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
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
0x180005dd0  push    rbx
0x180005dd2  sub     rsp, 20h
0x180005dd6  mov     qword ptr [r8], 0
0x180005ddd  cmp     dword ptr [rdx], 0
0x180005de0  jnz     short loc_180005E00
0x180005de2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180005de8  cmp     [rdx+4], eax
0x180005deb  jnz     short loc_180005E3C
0x180005ded  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180005df3  cmp     [rdx+8], eax
0x180005df6  jnz     short loc_180005E3C
0x180005df8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180005dfe  jmp     short loc_180005E24
0x180005e00  cmp     dword ptr [rdx], 0AF86E2E0h
0x180005e06  jnz     short loc_180005E3C
0x180005e08  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x180005e0e  cmp     [rdx+4], eax
0x180005e11  jnz     short loc_180005E3C
0x180005e13  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180005e19  cmp     [rdx+8], eax
0x180005e1c  jnz     short loc_180005E3C
0x180005e1e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180005e24  cmp     [rdx+0Ch], eax
0x180005e27  jnz     short loc_180005E3C
0x180005e29  mov     [r8], rcx
0x180005e2c  mov     rax, [rcx]
0x180005e2f  mov     rax, [rax+8]
0x180005e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e38  xor     ebx, ebx
0x180005e3a  jmp     short loc_180005E57
0x180005e3c  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180005e41  mov     ebx, eax
0x180005e43  test    eax, eax
0x180005e45  js      short loc_180005E57
0x180005e47  mov     rcx, [r8]
0x180005e4a  mov     rdx, [rcx]
0x180005e4d  mov     rax, [rdx+8]
0x180005e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e56  nop
0x180005e57  mov     eax, ebx
0x180005e59  add     rsp, 20h
0x180005e5d  pop     rbx
0x180005e5e  retn
```
