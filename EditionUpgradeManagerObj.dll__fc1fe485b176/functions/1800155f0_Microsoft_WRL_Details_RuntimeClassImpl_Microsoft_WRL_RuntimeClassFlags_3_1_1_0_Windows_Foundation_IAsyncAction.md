# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::QueryInterface(_GUID const &,void * *)

- ea: `0x1800155f0`
- end: `0x18001567e`
- name: `?QueryInterface@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIInspectable@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `142`
- prototype: `__int64 __fastcall(__int64, _DWORD *, _QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180015690`
- `0x1800156a0`
- `0x1800156b0`
- `0x1800156c0`

## callees

- `0x1800123dc`
- `0x1800155f0`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Foundation::IAsyncActionProgressHandler<double>,IInspectable,Microsoft::WRL::FtmBase>::QueryInterface(
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
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,IInspectable,Windows::Foundation::IAsyncActionProgressHandler<double>,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::CanCastTo();
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x1800155f0  push    rbx
0x1800155f2  sub     rsp, 20h
0x1800155f6  mov     qword ptr [r8], 0
0x1800155fd  cmp     dword ptr [rdx], 0
0x180015600  jnz     short loc_180015620
0x180015602  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180015608  cmp     [rdx+4], eax
0x18001560b  jnz     short loc_18001565C
0x18001560d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x180015613  cmp     [rdx+8], eax
0x180015616  jnz     short loc_18001565C
0x180015618  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x18001561e  jmp     short loc_180015644
0x180015620  cmp     dword ptr [rdx], 0AF86E2E0h
0x180015626  jnz     short loc_18001565C
0x180015628  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x18001562e  cmp     [rdx+4], eax
0x180015631  jnz     short loc_18001565C
0x180015633  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x180015639  cmp     [rdx+8], eax
0x18001563c  jnz     short loc_18001565C
0x18001563e  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x180015644  cmp     [rdx+0Ch], eax
0x180015647  jnz     short loc_18001565C
0x180015649  mov     [r8], rcx
0x18001564c  mov     rax, [rcx]
0x18001564f  mov     rax, [rax+8]
0x180015653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015658  xor     ebx, ebx
0x18001565a  jmp     short loc_180015676
0x18001565c  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$0A@UIInspectable@@U?$IAsyncActionProgressHandler@N@Foundation@Windows@@UIWeakReferenceSource@@U4@VFtmBase@23@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,0,IInspectable,Windows::Foundation::IAsyncActionProgressHandler<double>,IWeakReferenceSource,IInspectable,Microsoft::WRL::FtmBase>::CanCastTo(_GUID const &,void * *,bool *)
0x180015661  mov     ebx, eax
0x180015663  test    eax, eax
0x180015665  js      short loc_180015676
0x180015667  mov     rcx, [r8]
0x18001566a  mov     rdx, [rcx]
0x18001566d  mov     rax, [rdx+8]
0x180015671  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015676  mov     eax, ebx
0x180015678  add     rsp, 20h
0x18001567c  pop     rbx
0x18001567d  retn
```
