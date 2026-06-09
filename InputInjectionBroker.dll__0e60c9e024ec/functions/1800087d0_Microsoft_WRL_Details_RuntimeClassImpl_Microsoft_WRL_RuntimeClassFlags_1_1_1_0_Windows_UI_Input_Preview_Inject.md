# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800087d0`
- end: `0x180008893`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputButtonInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800088a0`
- `0x1800088b0`
- `0x1800088c0`

## callees

- `0x180006510`
- `0x1800087d0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputButtonInfo,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -1564059727
      && a2[1] == *(_DWORD *)&GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data2
      && a2[2] == *(_DWORD *)GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data4
      && a2[3] == *(_DWORD *)&GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data4[4] )
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
0x1800087d0  push    rbx
0x1800087d2  sub     rsp, 20h
0x1800087d6  mov     qword ptr [r8], 0
0x1800087dd  cmp     dword ptr [rdx], 0
0x1800087e0  jnz     short loc_180008800
0x1800087e2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x1800087e8  cmp     [rdx+4], eax
0x1800087eb  jnz     short loc_18000886C
0x1800087ed  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800087f3  cmp     [rdx+8], eax
0x1800087f6  jnz     short loc_18000886C
0x1800087f8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800087fe  jmp     short loc_180008824
0x180008800  cmp     dword ptr [rdx], 0AF86E2E0h
0x180008806  jnz     short loc_18000883C
0x180008808  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000880e  cmp     [rdx+4], eax
0x180008811  jnz     short loc_18000886C
0x180008813  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180008819  cmp     [rdx+8], eax
0x18000881c  jnz     short loc_18000886C
0x18000881e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180008824  cmp     [rdx+0Ch], eax
0x180008827  jnz     short loc_18000886C
0x180008829  mov     [r8], rcx
0x18000882c  mov     rax, [rcx]
0x18000882f  mov     rax, [rax+8]
0x180008833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008838  xor     ebx, ebx
0x18000883a  jmp     short loc_18000888B
0x18000883c  cmp     dword ptr [rdx], 0A2C657B1h
0x180008842  jnz     short loc_18000886C
0x180008844  mov     eax, dword ptr cs:_GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data2
0x18000884a  cmp     [rdx+4], eax
0x18000884d  jnz     short loc_18000886C
0x18000884f  mov     eax, dword ptr cs:_GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data4
0x180008855  cmp     [rdx+8], eax
0x180008858  jnz     short loc_18000886C
0x18000885a  mov     eax, dword ptr cs:_GUID_a2c657b1_3587_57eb_a052_560c1ac7d750.Data4+4
0x180008860  cmp     [rdx+0Ch], eax
0x180008863  jnz     short loc_18000886C
0x180008865  mov     [r8], rcx
0x180008868  xor     ebx, ebx
0x18000886a  jmp     short loc_18000887B
0x18000886c  add     rcx, 8
0x180008870  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180008875  mov     ebx, eax
0x180008877  test    eax, eax
0x180008879  js      short loc_18000888B
0x18000887b  mov     rcx, [r8]
0x18000887e  mov     rdx, [rcx]
0x180008881  mov     rax, [rdx+8]
0x180008885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000888a  nop
0x18000888b  mov     eax, ebx
0x18000888d  add     rsp, 20h
0x180008891  pop     rbx
0x180008892  retn
```
