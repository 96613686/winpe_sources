# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputPenInfo,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000fcd0`
- end: `0x18000fd93`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputPenInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fda0`
- `0x18000fdb0`
- `0x18000fdc0`

## callees

- `0x180006510`
- `0x18000fcd0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputPenInfo,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == 1799400707
      && a2[1] == *(_DWORD *)&GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data2
      && a2[2] == *(_DWORD *)GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data4
      && a2[3] == *(_DWORD *)&GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data4[4] )
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
0x18000fcd0  push    rbx
0x18000fcd2  sub     rsp, 20h
0x18000fcd6  mov     qword ptr [r8], 0
0x18000fcdd  cmp     dword ptr [rdx], 0
0x18000fce0  jnz     short loc_18000FD00
0x18000fce2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000fce8  cmp     [rdx+4], eax
0x18000fceb  jnz     short loc_18000FD6C
0x18000fced  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000fcf3  cmp     [rdx+8], eax
0x18000fcf6  jnz     short loc_18000FD6C
0x18000fcf8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000fcfe  jmp     short loc_18000FD24
0x18000fd00  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000fd06  jnz     short loc_18000FD3C
0x18000fd08  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000fd0e  cmp     [rdx+4], eax
0x18000fd11  jnz     short loc_18000FD6C
0x18000fd13  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000fd19  cmp     [rdx+8], eax
0x18000fd1c  jnz     short loc_18000FD6C
0x18000fd1e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000fd24  cmp     [rdx+0Ch], eax
0x18000fd27  jnz     short loc_18000FD6C
0x18000fd29  mov     [r8], rcx
0x18000fd2c  mov     rax, [rcx]
0x18000fd2f  mov     rax, [rax+8]
0x18000fd33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd38  xor     ebx, ebx
0x18000fd3a  jmp     short loc_18000FD8B
0x18000fd3c  cmp     dword ptr [rdx], 6B40AD03h
0x18000fd42  jnz     short loc_18000FD6C
0x18000fd44  mov     eax, dword ptr cs:_GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data2
0x18000fd4a  cmp     [rdx+4], eax
0x18000fd4d  jnz     short loc_18000FD6C
0x18000fd4f  mov     eax, dword ptr cs:_GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data4
0x18000fd55  cmp     [rdx+8], eax
0x18000fd58  jnz     short loc_18000FD6C
0x18000fd5a  mov     eax, dword ptr cs:_GUID_6b40ad03_ca1e_5527_7e02_2828540bb1d4.Data4+4
0x18000fd60  cmp     [rdx+0Ch], eax
0x18000fd63  jnz     short loc_18000FD6C
0x18000fd65  mov     [r8], rcx
0x18000fd68  xor     ebx, ebx
0x18000fd6a  jmp     short loc_18000FD7B
0x18000fd6c  add     rcx, 8
0x18000fd70  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x18000fd75  mov     ebx, eax
0x18000fd77  test    eax, eax
0x18000fd79  js      short loc_18000FD8B
0x18000fd7b  mov     rcx, [r8]
0x18000fd7e  mov     rdx, [rcx]
0x18000fd81  mov     rax, [rdx+8]
0x18000fd85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd8a  nop
0x18000fd8b  mov     eax, ebx
0x18000fd8d  add     rsp, 20h
0x18000fd91  pop     rbx
0x18000fd92  retn
```
