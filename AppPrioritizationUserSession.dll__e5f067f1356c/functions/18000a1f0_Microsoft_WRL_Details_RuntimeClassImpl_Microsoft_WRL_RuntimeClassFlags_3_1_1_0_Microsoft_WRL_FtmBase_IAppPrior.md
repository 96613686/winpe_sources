# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(_GUID const &,void * *)

- ea: `0x18000a1f0`
- end: `0x18000a27f`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@VFtmBase@23@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008ea0`
- `0x180009110`
- `0x18000a290`
- `0x18000a2a0`
- `0x18000a2b0`
- `0x18000a2c0`
- `0x18000a2d0`

## callees

- `0x180008ff0`
- `0x18000a1f0`
- `0x18000d010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Microsoft::WRL::FtmBase,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::QueryInterface(
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
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,IInspectable,Microsoft::WRL::FtmBase,IWeakReferenceSource,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::CanCastTo();
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x18000a1f0  push    rbx
0x18000a1f2  sub     rsp, 20h
0x18000a1f6  mov     qword ptr [r8], 0
0x18000a1fd  cmp     dword ptr [rdx], 0
0x18000a200  jnz     short loc_18000A220
0x18000a202  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x18000a208  cmp     [rdx+4], eax
0x18000a20b  jnz     short loc_18000A25C
0x18000a20d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x18000a213  cmp     [rdx+8], eax
0x18000a216  jnz     short loc_18000A25C
0x18000a218  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18000a21e  jmp     short loc_18000A244
0x18000a220  cmp     dword ptr [rdx], 0AF86E2E0h
0x18000a226  jnz     short loc_18000A25C
0x18000a228  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18000a22e  cmp     [rdx+4], eax
0x18000a231  jnz     short loc_18000A25C
0x18000a233  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x18000a239  cmp     [rdx+8], eax
0x18000a23c  jnz     short loc_18000A25C
0x18000a23e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x18000a244  cmp     [rdx+0Ch], eax
0x18000a247  jnz     short loc_18000A25C
0x18000a249  mov     [r8], rcx
0x18000a24c  mov     rax, [rcx]
0x18000a24f  mov     rax, [rax+8]
0x18000a253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a258  xor     ebx, ebx
0x18000a25a  jmp     short loc_18000A277
0x18000a25c  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIInspectable@@VFtmBase@23@UIWeakReferenceSource@@UIAppPrioritizationUserSessionInternal@@UIAppPrioritizationUserSession@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,IInspectable,Microsoft::WRL::FtmBase,IWeakReferenceSource,IAppPrioritizationUserSessionInternal,IAppPrioritizationUserSession>::CanCastTo(_GUID const &,void * *,bool *)
0x18000a261  mov     ebx, eax
0x18000a263  test    eax, eax
0x18000a265  js      short loc_18000A277
0x18000a267  mov     rcx, [r8]
0x18000a26a  mov     rdx, [rcx]
0x18000a26d  mov     rax, [rdx+8]
0x18000a271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a276  nop
0x18000a277  mov     eax, ebx
0x18000a279  add     rsp, 20h
0x18000a27d  pop     rbx
0x18000a27e  retn
```
