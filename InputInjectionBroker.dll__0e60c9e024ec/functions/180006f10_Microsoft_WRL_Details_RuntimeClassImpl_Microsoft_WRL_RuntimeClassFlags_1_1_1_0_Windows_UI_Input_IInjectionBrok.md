# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180006f10`
- end: `0x180006fd3`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectionBroker@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006fe0`
- `0x180006ff0`
- `0x180007080`

## callees

- `0x180006510`
- `0x180006f10`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::IInjectionBroker,Microsoft::WRL::FtmBase>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        _QWORD *a3)
{
  int v3; // eax
  int CanCastTo; // ebx

  *a3 = 0;
  if ( !*a2 )
  {
    if ( a2[1] == *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      && a2[2] == *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
      goto LABEL_9;
    }
LABEL_16:
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(
                  a1 + 8,
                  a2,
                  a3);
    if ( CanCastTo < 0 )
      return (unsigned int)CanCastTo;
LABEL_17:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    return (unsigned int)CanCastTo;
  }
  if ( *a2 != -1350114592 )
  {
    if ( *a2 == -192633670
      && a2[1] == *(_DWORD *)&GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data2
      && a2[2] == *(_DWORD *)GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data4
      && a2[3] == *(_DWORD *)&GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data4[4] )
    {
      *a3 = a1;
      CanCastTo = 0;
      goto LABEL_17;
    }
    goto LABEL_16;
  }
  if ( a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
    || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
  {
    goto LABEL_16;
  }
  v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
LABEL_9:
  if ( a2[3] != v3 )
    goto LABEL_16;
  *a3 = a1;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x180006f10  push    rbx
0x180006f12  sub     rsp, 20h
0x180006f16  mov     qword ptr [r8], 0
0x180006f1d  cmp     dword ptr [rdx], 0
0x180006f20  jnz     short loc_180006F40
0x180006f22  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180006f28  cmp     [rdx+4], eax
0x180006f2b  jnz     short loc_180006FAC
0x180006f2d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180006f33  cmp     [rdx+8], eax
0x180006f36  jnz     short loc_180006FAC
0x180006f38  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x180006f3e  jmp     short loc_180006F64
0x180006f40  cmp     dword ptr [rdx], 0AF86E2E0h
0x180006f46  jnz     short loc_180006F7C
0x180006f48  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x180006f4e  cmp     [rdx+4], eax
0x180006f51  jnz     short loc_180006FAC
0x180006f53  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180006f59  cmp     [rdx+8], eax
0x180006f5c  jnz     short loc_180006FAC
0x180006f5e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180006f64  cmp     [rdx+0Ch], eax
0x180006f67  jnz     short loc_180006FAC
0x180006f69  mov     [r8], rcx
0x180006f6c  mov     rax, [rcx]
0x180006f6f  mov     rax, [rax+8]
0x180006f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f78  xor     ebx, ebx
0x180006f7a  jmp     short loc_180006FCB
0x180006f7c  cmp     dword ptr [rdx], 0F484A4BAh
0x180006f82  jnz     short loc_180006FAC
0x180006f84  mov     eax, dword ptr cs:_GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data2
0x180006f8a  cmp     [rdx+4], eax
0x180006f8d  jnz     short loc_180006FAC
0x180006f8f  mov     eax, dword ptr cs:_GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data4
0x180006f95  cmp     [rdx+8], eax
0x180006f98  jnz     short loc_180006FAC
0x180006f9a  mov     eax, dword ptr cs:_GUID_f484a4ba_f4b8_4202_bfac_a6e3af2b6e90.Data4+4
0x180006fa0  cmp     [rdx+0Ch], eax
0x180006fa3  jnz     short loc_180006FAC
0x180006fa5  mov     [r8], rcx
0x180006fa8  xor     ebx, ebx
0x180006faa  jmp     short loc_180006FBB
0x180006fac  add     rcx, 8
0x180006fb0  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180006fb5  mov     ebx, eax
0x180006fb7  test    eax, eax
0x180006fb9  js      short loc_180006FCB
0x180006fbb  mov     rcx, [r8]
0x180006fbe  mov     rdx, [rcx]
0x180006fc1  mov     rax, [rdx+8]
0x180006fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fca  nop
0x180006fcb  mov     eax, ebx
0x180006fcd  add     rsp, 20h
0x180006fd1  pop     rbx
0x180006fd2  retn
```
