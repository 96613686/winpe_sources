# Microsoft::WRL::Details::MakeAndInitialize<CCPLUserMgrBroker,IUnknown,>(IUnknown * *)

- ea: `0x140001e98`
- end: `0x140001fa6`
- name: `??$MakeAndInitialize@VCCPLUserMgrBroker@@UIUnknown@@$$V@Details@WRL@Microsoft@@YAJPEAPEAUIUnknown@@@Z`
- size: `270`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140002a90`

## callees

- `0x140001558`
- `0x140001e98`
- `0x140002514`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::MakeAndInitialize<CCPLUserMgrBroker,IUnknown,>(_QWORD *a1)
{
  _DWORD *v2; // rax
  _DWORD *v3; // rdi
  Microsoft::WRL::Details *v5; // rcx
  unsigned int v6; // ebx

  *a1 = 0;
  v2 = operator new(0xA0u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = v2;
  if ( !v2 )
    return 2147942414LL;
  v5 = Microsoft::WRL::Details::ModuleBase::module_;
  v2[5] = 1;
  *(_QWORD *)v2 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUserManagementWizards,IUserManagementWizardsWithCancel>::`vftable'{for `IUserManagementWizards'};
  *((_QWORD *)v2 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUserManagementWizards,IUserManagementWizardsWithCancel>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUserManagementWizardsWithCancel>'};
  if ( v5 )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)v5 + 8LL))(v5);
  *((_QWORD *)v3 + 6) = 0;
  *(_QWORD *)v3 = &CCPLUserMgrBroker::`vftable'{for `IUserManagementWizards'};
  *((_QWORD *)v3 + 3) = 0;
  *((_QWORD *)v3 + 1) = &CCPLUserMgrBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUserManagementWizardsWithCancel>'};
  *((_QWORD *)v3 + 4) = 0;
  *((_QWORD *)v3 + 5) = 0;
  *((_QWORD *)v3 + 7) = 0;
  *((_QWORD *)v3 + 8) = 0;
  *((_QWORD *)v3 + 9) = 0;
  *((_QWORD *)v3 + 10) = 0;
  *((_QWORD *)v3 + 11) = 0;
  *((_QWORD *)v3 + 12) = 8;
  v3[26] = 0;
  Windows::Internal::GitPtr::GitPtr((Windows::Internal::GitPtr *)(v3 + 28));
  Windows::Internal::GitPtr::GitPtr((Windows::Internal::GitPtr *)(v3 + 32));
  Windows::Internal::GitPtr::GitPtr((Windows::Internal::GitPtr *)(v3 + 36));
  v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, _QWORD *))v3)(v3, &GUID_00000000_0000_0000_c000_000000000046, a1);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v3 + 16LL))(v3);
  return v6;
}

```

## disassembly

```asm
0x140001e98  mov     [rsp+arg_0], rbx
0x140001e9d  mov     [rsp+arg_8], rsi
0x140001ea2  push    rdi
0x140001ea3  sub     rsp, 20h
0x140001ea7  mov     rbx, rcx
0x140001eaa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140001eb1  xor     esi, esi
0x140001eb3  mov     [rcx], rsi
0x140001eb6  mov     ecx, 0A0h; unsigned __int64
0x140001ebb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140001ec0  mov     rdi, rax
0x140001ec3  test    rax, rax
0x140001ec6  jnz     short loc_140001ED2
0x140001ec8  mov     eax, 8007000Eh
0x140001ecd  jmp     loc_140001F96
0x140001ed2  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140001ed9  mov     dword ptr [rax+14h], 1
0x140001ee0  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUserManagementWizards@@UIUserManagementWizardsWithCancel@@@WRL@Microsoft@@6BIUserManagementWizards@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUserManagementWizards,IUserManagementWizardsWithCancel>::`vftable'{for `IUserManagementWizards'}
0x140001ee7  mov     [rdi], rax
0x140001eea  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUserManagementWizards@@UIUserManagementWizardsWithCancel@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUserManagementWizardsWithCancel@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUserManagementWizards,IUserManagementWizardsWithCancel>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUserManagementWizardsWithCancel>'}
0x140001ef1  mov     [rdi+8], rax
0x140001ef5  test    rcx, rcx
0x140001ef8  jz      short loc_140001F06
0x140001efa  mov     rax, [rcx]
0x140001efd  mov     rax, [rax+8]
0x140001f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f06  lea     rax, ??_7CCPLUserMgrBroker@@6BIUserManagementWizards@@@; const CCPLUserMgrBroker::`vftable'{for `IUserManagementWizards'}
0x140001f0d  mov     [rdi+30h], rsi
0x140001f11  mov     [rdi], rax
0x140001f14  lea     rcx, [rdi+70h]; this
0x140001f18  lea     rax, ??_7CCPLUserMgrBroker@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIUserManagementWizardsWithCancel@@@Details@WRL@Microsoft@@@; const CCPLUserMgrBroker::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IUserManagementWizardsWithCancel>'}
0x140001f1f  mov     [rdi+18h], rsi
0x140001f23  mov     [rdi+8], rax
0x140001f27  mov     [rdi+20h], rsi
0x140001f2b  mov     [rdi+28h], rsi
0x140001f2f  mov     [rdi+38h], rsi
0x140001f33  mov     [rdi+40h], rsi
0x140001f37  mov     [rdi+48h], rsi
0x140001f3b  mov     [rdi+50h], rsi
0x140001f3f  mov     [rdi+58h], rsi
0x140001f43  mov     qword ptr [rdi+60h], 8
0x140001f4b  mov     [rdi+68h], esi
0x140001f4e  call    ??0GitPtr@Internal@Windows@@QEAA@XZ; Windows::Internal::GitPtr::GitPtr(void)
0x140001f53  lea     rcx, [rdi+80h]; this
0x140001f5a  call    ??0GitPtr@Internal@Windows@@QEAA@XZ; Windows::Internal::GitPtr::GitPtr(void)
0x140001f5f  lea     rcx, [rdi+90h]; this
0x140001f66  call    ??0GitPtr@Internal@Windows@@QEAA@XZ; Windows::Internal::GitPtr::GitPtr(void)
0x140001f6b  mov     rax, [rdi]
0x140001f6e  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x140001f75  mov     r8, rbx
0x140001f78  mov     rcx, rdi
0x140001f7b  mov     rax, [rax]
0x140001f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f83  mov     rcx, [rdi]
0x140001f86  mov     ebx, eax
0x140001f88  mov     rax, [rcx+10h]
0x140001f8c  mov     rcx, rdi
0x140001f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f94  mov     eax, ebx
0x140001f96  mov     rbx, [rsp+28h+arg_0]
0x140001f9b  mov     rsi, [rsp+28h+arg_8]
0x140001fa0  add     rsp, 20h
0x140001fa4  pop     rdi
0x140001fa5  retn
```
