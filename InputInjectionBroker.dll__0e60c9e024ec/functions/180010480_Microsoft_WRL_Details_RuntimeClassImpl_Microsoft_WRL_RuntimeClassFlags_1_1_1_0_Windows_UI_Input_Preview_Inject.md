# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputKeyboardInfo,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x180010480`
- end: `0x180010543`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInjectedInputKeyboardInfo@Injection@Preview@Input@UI@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010550`
- `0x180010560`
- `0x180010570`

## callees

- `0x180006510`
- `0x180010480`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInjectedInputKeyboardInfo,Microsoft::WRL::FtmBase>::QueryInterface(
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
    if ( *a2 == 1262932288
      && a2[1] == *(_DWORD *)&GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data2
      && a2[2] == *(_DWORD *)GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data4
      && a2[3] == *(_DWORD *)&GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data4[4] )
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
0x180010480  push    rbx
0x180010482  sub     rsp, 20h
0x180010486  mov     qword ptr [r8], 0
0x18001048d  cmp     dword ptr [rdx], 0
0x180010490  jnz     short loc_1800104B0
0x180010492  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180010498  cmp     [rdx+4], eax
0x18001049b  jnz     short loc_18001051C
0x18001049d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800104a3  cmp     [rdx+8], eax
0x1800104a6  jnz     short loc_18001051C
0x1800104a8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800104ae  jmp     short loc_1800104D4
0x1800104b0  cmp     dword ptr [rdx], 0AF86E2E0h
0x1800104b6  jnz     short loc_1800104EC
0x1800104b8  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x1800104be  cmp     [rdx+4], eax
0x1800104c1  jnz     short loc_18001051C
0x1800104c3  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x1800104c9  cmp     [rdx+8], eax
0x1800104cc  jnz     short loc_18001051C
0x1800104ce  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x1800104d4  cmp     [rdx+0Ch], eax
0x1800104d7  jnz     short loc_18001051C
0x1800104d9  mov     [r8], rcx
0x1800104dc  mov     rax, [rcx]
0x1800104df  mov     rax, [rax+8]
0x1800104e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104e8  xor     ebx, ebx
0x1800104ea  jmp     short loc_18001053B
0x1800104ec  cmp     dword ptr [rdx], 4B46D140h
0x1800104f2  jnz     short loc_18001051C
0x1800104f4  mov     eax, dword ptr cs:_GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data2
0x1800104fa  cmp     [rdx+4], eax
0x1800104fd  jnz     short loc_18001051C
0x1800104ff  mov     eax, dword ptr cs:_GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data4
0x180010505  cmp     [rdx+8], eax
0x180010508  jnz     short loc_18001051C
0x18001050a  mov     eax, dword ptr cs:_GUID_4b46d140_2b6a_5ffa_7eae_bd077b052acd.Data4+4
0x180010510  cmp     [rdx+0Ch], eax
0x180010513  jnz     short loc_18001051C
0x180010515  mov     [r8], rcx
0x180010518  xor     ebx, ebx
0x18001051a  jmp     short loc_18001052B
0x18001051c  add     rcx, 8
0x180010520  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180010525  mov     ebx, eax
0x180010527  test    eax, eax
0x180010529  js      short loc_18001053B
0x18001052b  mov     rcx, [r8]
0x18001052e  mov     rdx, [rcx]
0x180010531  mov     rax, [rdx+8]
0x180010535  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001053a  nop
0x18001053b  mov     eax, ebx
0x18001053d  add     rsp, 20h
0x180010541  pop     rbx
0x180010542  retn
```
