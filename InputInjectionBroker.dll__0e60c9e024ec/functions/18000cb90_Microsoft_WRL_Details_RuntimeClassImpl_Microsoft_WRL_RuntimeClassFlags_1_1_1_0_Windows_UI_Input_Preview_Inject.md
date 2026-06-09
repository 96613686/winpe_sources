# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000cb90`
- end: `0x18000cc53`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIInputInjector@Injection@Preview@Input@UI@Windows@@UIInputInjector2@56789@UIInputInjector3@56789@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `195`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cc60`
- `0x18000cc70`
- `0x18000cc80`
- `0x18000cc90`
- `0x18000cca0`
- `0x18000ccb0`

## callees

- `0x18000a380`
- `0x18000cb90`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::UI::Input::Preview::Injection::IInputInjector,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::QueryInterface(
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
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::CanCastTo(a1 + 8);
    if ( CanCastTo < 0 )
      return (unsigned int)CanCastTo;
LABEL_17:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a3 + 8LL))(*a3);
    return (unsigned int)CanCastTo;
  }
  if ( *a2 != -1350114592 )
  {
    if ( *a2 == -1899860092
      && a2[1] == *(_DWORD *)&GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data2
      && a2[2] == *(_DWORD *)GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data4
      && a2[3] == *(_DWORD *)&GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data4[4] )
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
0x18000cb90  push    rbx
0x18000cb92  sub     rsp, 20h
0x18000cb96  mov     qword ptr [r8], 0
0x18000cb9d  cmp     dword ptr [rdx], 0
0x18000cba0  jnz     short loc_18000CBC0
0x18000cba2  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000cba8  cmp     [rdx+4], eax
0x18000cbab  jnz     short loc_18000CC2C
0x18000cbad  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000cbb3  cmp     [rdx+8], eax
0x18000cbb6  jnz     short loc_18000CC2C
0x18000cbb8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000cbbe  jmp     short loc_18000CBE4
0x18000cbc0  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000cbc6  jnz     short loc_18000CBFC
0x18000cbc8  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000cbce  cmp     [rdx+4], eax
0x18000cbd1  jnz     short loc_18000CC2C
0x18000cbd3  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000cbd9  cmp     [rdx+8], eax
0x18000cbdc  jnz     short loc_18000CC2C
0x18000cbde  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000cbe4  cmp     [rdx+0Ch], eax
0x18000cbe7  jnz     short loc_18000CC2C
0x18000cbe9  mov     [r8], rcx
0x18000cbec  mov     rax, [rcx]
0x18000cbef  mov     rax, [rax+8]
0x18000cbf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbf8  xor     ebx, ebx
0x18000cbfa  jmp     short loc_18000CC4B
0x18000cbfc  cmp     dword ptr [rdx], 8EC26F84h
0x18000cc02  jnz     short loc_18000CC2C
0x18000cc04  mov     eax, dword ptr cs:_GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data2
0x18000cc0a  cmp     [rdx+4], eax
0x18000cc0d  jnz     short loc_18000CC2C
0x18000cc0f  mov     eax, dword ptr cs:_GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data4
0x18000cc15  cmp     [rdx+8], eax
0x18000cc18  jnz     short loc_18000CC2C
0x18000cc1a  mov     eax, dword ptr cs:_GUID_8ec26f84_0b02_4bd2_ad7a_3d4658be3e18.Data4+4
0x18000cc20  cmp     [rdx+0Ch], eax
0x18000cc23  jnz     short loc_18000CC2C
0x18000cc25  mov     [r8], rcx
0x18000cc28  xor     ebx, ebx
0x18000cc2a  jmp     short loc_18000CC3B
0x18000cc2c  add     rcx, 8
0x18000cc30  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@UIInputInjector2@Injection@Preview@Input@UI@Windows@@UIInputInjector3@6789Windows@@U?$CloakedIid@UIInputInjectorPrivate@Internal@Injection@Preview@Input@UI@Windows@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource,Windows::UI::Input::Preview::Injection::IInputInjector2,Windows::UI::Input::Preview::Injection::IInputInjector3,Microsoft::WRL::CloakedIid<Windows::UI::Input::Preview::Injection::Internal::IInputInjectorPrivate>,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x18000cc35  mov     ebx, eax
0x18000cc37  test    eax, eax
0x18000cc39  js      short loc_18000CC4B
0x18000cc3b  mov     rcx, [r8]
0x18000cc3e  mov     rdx, [rcx]
0x18000cc41  mov     rax, [rdx+8]
0x18000cc45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc4a  nop
0x18000cc4b  mov     eax, ebx
0x18000cc4d  add     rsp, 20h
0x18000cc51  pop     rbx
0x18000cc52  retn
```
