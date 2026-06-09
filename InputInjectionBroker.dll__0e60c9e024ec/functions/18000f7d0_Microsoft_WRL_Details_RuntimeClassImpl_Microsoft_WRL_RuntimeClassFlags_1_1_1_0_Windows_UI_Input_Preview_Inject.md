# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputTouchInfo,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f7d0`
- end: `0x18000f893`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputTouchInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000f8a0`
- `0x18000f8b0`
- `0x18000f8c0`

## callees

- `0x180006510`
- `0x18000f7d0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputTouchInfo,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == 575656415
      && a2[1] == *(_DWORD *)&GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data2
      && a2[2] == *(_DWORD *)GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data4
      && a2[3] == *(_DWORD *)&GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data4[4] )
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
0x18000f7d0  push    rbx
0x18000f7d2  sub     rsp, 20h
0x18000f7d6  mov     qword ptr [r8], 0
0x18000f7dd  cmp     dword ptr [rdx], 0
0x18000f7e0  jnz     short loc_18000F800
0x18000f7e2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000f7e8  cmp     [rdx+4], eax
0x18000f7eb  jnz     short loc_18000F86C
0x18000f7ed  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000f7f3  cmp     [rdx+8], eax
0x18000f7f6  jnz     short loc_18000F86C
0x18000f7f8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000f7fe  jmp     short loc_18000F824
0x18000f800  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000f806  jnz     short loc_18000F83C
0x18000f808  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000f80e  cmp     [rdx+4], eax
0x18000f811  jnz     short loc_18000F86C
0x18000f813  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000f819  cmp     [rdx+8], eax
0x18000f81c  jnz     short loc_18000F86C
0x18000f81e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000f824  cmp     [rdx+0Ch], eax
0x18000f827  jnz     short loc_18000F86C
0x18000f829  mov     [r8], rcx
0x18000f82c  mov     rax, [rcx]
0x18000f82f  mov     rax, [rax+8]
0x18000f833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f838  xor     ebx, ebx
0x18000f83a  jmp     short loc_18000F88B
0x18000f83c  cmp     dword ptr [rdx], 224FD1DFh
0x18000f842  jnz     short loc_18000F86C
0x18000f844  mov     eax, dword ptr cs:_GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data2
0x18000f84a  cmp     [rdx+4], eax
0x18000f84d  jnz     short loc_18000F86C
0x18000f84f  mov     eax, dword ptr cs:_GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data4
0x18000f855  cmp     [rdx+8], eax
0x18000f858  jnz     short loc_18000F86C
0x18000f85a  mov     eax, dword ptr cs:_GUID_224fd1df_43e8_5ef5_510a_69ca8c9b4c28.Data4+4
0x18000f860  cmp     [rdx+0Ch], eax
0x18000f863  jnz     short loc_18000F86C
0x18000f865  mov     [r8], rcx
0x18000f868  xor     ebx, ebx
0x18000f86a  jmp     short loc_18000F87B
0x18000f86c  add     rcx, 8
0x18000f870  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x18000f875  mov     ebx, eax
0x18000f877  test    eax, eax
0x18000f879  js      short loc_18000F88B
0x18000f87b  mov     rcx, [r8]
0x18000f87e  mov     rdx, [rcx]
0x18000f881  mov     rax, [rdx+8]
0x18000f885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f88a  nop
0x18000f88b  mov     eax, ebx
0x18000f88d  add     rsp, 20h
0x18000f891  pop     rbx
0x18000f892  retn
```
