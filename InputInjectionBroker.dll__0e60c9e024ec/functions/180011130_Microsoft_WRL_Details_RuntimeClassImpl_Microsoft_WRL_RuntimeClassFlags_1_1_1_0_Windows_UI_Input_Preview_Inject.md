# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfo,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180011130`
- end: `0x1800111f3`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputGamepadInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011200`
- `0x180011210`
- `0x180011220`

## callees

- `0x180006510`
- `0x180011130`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputGamepadInfo,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == 548313663
      && a2[1] == *(_DWORD *)&GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data2
      && a2[2] == *(_DWORD *)GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data4
      && a2[3] == *(_DWORD *)&GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data4[4] )
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
0x180011130  push    rbx
0x180011132  sub     rsp, 20h
0x180011136  mov     qword ptr [r8], 0
0x18001113d  cmp     dword ptr [rdx], 0
0x180011140  jnz     short loc_180011160
0x180011142  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180011148  cmp     [rdx+4], eax
0x18001114b  jnz     short loc_1800111CC
0x18001114d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180011153  cmp     [rdx+8], eax
0x180011156  jnz     short loc_1800111CC
0x180011158  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001115e  jmp     short loc_180011184
0x180011160  cmp     dword ptr [rdx], 0AF86E2E0h
0x180011166  jnz     short loc_18001119C
0x180011168  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18001116e  cmp     [rdx+4], eax
0x180011171  jnz     short loc_1800111CC
0x180011173  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180011179  cmp     [rdx+8], eax
0x18001117c  jnz     short loc_1800111CC
0x18001117e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180011184  cmp     [rdx+0Ch], eax
0x180011187  jnz     short loc_1800111CC
0x180011189  mov     [r8], rcx
0x18001118c  mov     rax, [rcx]
0x18001118f  mov     rax, [rax+8]
0x180011193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011198  xor     ebx, ebx
0x18001119a  jmp     short loc_1800111EB
0x18001119c  cmp     dword ptr [rdx], 20AE9A3Fh
0x1800111a2  jnz     short loc_1800111CC
0x1800111a4  mov     eax, dword ptr cs:_GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data2
0x1800111aa  cmp     [rdx+4], eax
0x1800111ad  jnz     short loc_1800111CC
0x1800111af  mov     eax, dword ptr cs:_GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data4
0x1800111b5  cmp     [rdx+8], eax
0x1800111b8  jnz     short loc_1800111CC
0x1800111ba  mov     eax, dword ptr cs:_GUID_20ae9a3f_df11_4572_a9ab_d75b8a5e48ad.Data4+4
0x1800111c0  cmp     [rdx+0Ch], eax
0x1800111c3  jnz     short loc_1800111CC
0x1800111c5  mov     [r8], rcx
0x1800111c8  xor     ebx, ebx
0x1800111ca  jmp     short loc_1800111DB
0x1800111cc  add     rcx, 8
0x1800111d0  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x1800111d5  mov     ebx, eax
0x1800111d7  test    eax, eax
0x1800111d9  js      short loc_1800111EB
0x1800111db  mov     rcx, [r8]
0x1800111de  mov     rdx, [rcx]
0x1800111e1  mov     rax, [rdx+8]
0x1800111e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111ea  nop
0x1800111eb  mov     eax, ebx
0x1800111ed  add     rsp, 20h
0x1800111f1  pop     rbx
0x1800111f2  retn
```
