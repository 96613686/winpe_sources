# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputMouseInfo,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800101f0`
- end: `0x1800102b3`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputMouseInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800102c0`
- `0x1800102d0`
- `0x1800102e0`

## callees

- `0x180006510`
- `0x1800101f0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputMouseInfo,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == -1762300309
      && a2[1] == *(_DWORD *)&GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data2
      && a2[2] == *(_DWORD *)GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data4
      && a2[3] == *(_DWORD *)&GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data4[4] )
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
0x1800101f0  push    rbx
0x1800101f2  sub     rsp, 20h
0x1800101f6  mov     qword ptr [r8], 0
0x1800101fd  cmp     dword ptr [rdx], 0
0x180010200  jnz     short loc_180010220
0x180010202  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180010208  cmp     [rdx+4], eax
0x18001020b  jnz     short loc_18001028C
0x18001020d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180010213  cmp     [rdx+8], eax
0x180010216  jnz     short loc_18001028C
0x180010218  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001021e  jmp     short loc_180010244
0x180010220  cmp     dword ptr [rdx], 0AF86E2E0h
0x180010226  jnz     short loc_18001025C
0x180010228  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18001022e  cmp     [rdx+4], eax
0x180010231  jnz     short loc_18001028C
0x180010233  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180010239  cmp     [rdx+8], eax
0x18001023c  jnz     short loc_18001028C
0x18001023e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180010244  cmp     [rdx+0Ch], eax
0x180010247  jnz     short loc_18001028C
0x180010249  mov     [r8], rcx
0x18001024c  mov     rax, [rcx]
0x18001024f  mov     rax, [rax+8]
0x180010253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010258  xor     ebx, ebx
0x18001025a  jmp     short loc_1800102AB
0x18001025c  cmp     dword ptr [rdx], 96F56E6Bh
0x180010262  jnz     short loc_18001028C
0x180010264  mov     eax, dword ptr cs:_GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data2
0x18001026a  cmp     [rdx+4], eax
0x18001026d  jnz     short loc_18001028C
0x18001026f  mov     eax, dword ptr cs:_GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data4
0x180010275  cmp     [rdx+8], eax
0x180010278  jnz     short loc_18001028C
0x18001027a  mov     eax, dword ptr cs:_GUID_96f56e6b_e47a_5cf4_418d_8a5fb9670c7d.Data4+4
0x180010280  cmp     [rdx+0Ch], eax
0x180010283  jnz     short loc_18001028C
0x180010285  mov     [r8], rcx
0x180010288  xor     ebx, ebx
0x18001028a  jmp     short loc_18001029B
0x18001028c  add     rcx, 8
0x180010290  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180010295  mov     ebx, eax
0x180010297  test    eax, eax
0x180010299  js      short loc_1800102AB
0x18001029b  mov     rcx, [r8]
0x18001029e  mov     rdx, [rcx]
0x1800102a1  mov     rax, [rdx+8]
0x1800102a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102aa  nop
0x1800102ab  mov     eax, ebx
0x1800102ad  add     rsp, 20h
0x1800102b1  pop     rbx
0x1800102b2  retn
```
