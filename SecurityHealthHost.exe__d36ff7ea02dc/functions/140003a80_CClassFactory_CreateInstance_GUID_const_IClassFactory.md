# CClassFactory_CreateInstance(_GUID const &,IClassFactory * *)

- ea: `0x140003a80`
- end: `0x140003b7a`
- name: `?CClassFactory_CreateInstance@@YAJAEBU_GUID@@PEAPEAUIClassFactory@@@Z`
- size: `250`
- prototype: `__int64 __fastcall(const struct _GUID *, struct IClassFactory **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1400043d0`

## callees

- `0x14000190c`
- `0x140003a80`
- `0x140011010`

## pseudocode

```c
__int64 __fastcall CClassFactory_CreateInstance(const struct _GUID *a1, struct IClassFactory **a2)
{
  _DWORD *v4; // rax
  _DWORD *v5; // rbx
  int v6; // edi

  v4 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( !v4 )
    return 2147942414LL;
  v4[5] = 1;
  *(_QWORD *)v4 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,IMarshal>::`vftable'{for `IClassFactory'};
  *((_QWORD *)v4 + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,IMarshal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMarshal>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v5 = &CClassFactory::`vftable'{for `IClassFactory'};
  *((_QWORD *)v5 + 1) = &CClassFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMarshal>'};
  *(GUID *)(v5 + 6) = GUID_NULL;
  *(struct _GUID *)(v5 + 6) = *a1;
  ((void (__fastcall *)(_DWORD *))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IClassFactory,IMarshal>::AddRef)(v5);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = (**(__int64 (__fastcall ***)(_DWORD *, GUID *, struct IClassFactory **))v5)(
         v5,
         &GUID_00000001_0000_0000_c000_000000000046,
         a2);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v5 + 16LL))(v5);
  if ( v6 >= 0 )
    return 0;
  else
    return (unsigned int)v6;
}

```

## disassembly

```asm
0x140003a80  mov     [rsp+arg_0], rbx
0x140003a85  mov     [rsp+arg_8], rsi
0x140003a8a  push    rdi
0x140003a8b  sub     rsp, 20h
0x140003a8f  mov     rdi, rdx
0x140003a92  mov     rsi, rcx
0x140003a95  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140003a9c  mov     ecx, 28h ; '('; unsigned __int64
0x140003aa1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140003aa6  mov     rbx, rax
0x140003aa9  test    rax, rax
0x140003aac  jz      loc_140003B65
0x140003ab2  mov     dword ptr [rax+14h], 1
0x140003ab9  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClassFactory@@UIMarshal@@@WRL@Microsoft@@6BIClassFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,IMarshal>::`vftable'{for `IClassFactory'}
0x140003ac0  mov     [rbx], rax
0x140003ac3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIClassFactory@@UIMarshal@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMarshal@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IClassFactory,IMarshal>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMarshal>'}
0x140003aca  mov     [rbx+8], rax
0x140003ace  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140003ad5  test    rcx, rcx
0x140003ad8  jz      short loc_140003AE7
0x140003ada  mov     rax, [rcx]
0x140003add  mov     rax, [rax+8]
0x140003ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ae6  nop
0x140003ae7  lea     rax, ??_7CClassFactory@@6BIClassFactory@@@; const CClassFactory::`vftable'{for `IClassFactory'}
0x140003aee  mov     [rbx], rax
0x140003af1  lea     rax, ??_7CClassFactory@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIMarshal@@@Details@WRL@Microsoft@@@; const CClassFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IMarshal>'}
0x140003af8  mov     [rbx+8], rax
0x140003afc  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140003b03  movdqu  xmmword ptr [rbx+18h], xmm0
0x140003b08  movups  xmm0, xmmword ptr [rsi]
0x140003b0b  movdqu  xmmword ptr [rbx+18h], xmm0
0x140003b10  mov     rcx, rbx
0x140003b13  mov     rax, cs:off_140012150
0x140003b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b1f  nop
0x140003b20  mov     rax, [rbx]
0x140003b23  mov     rcx, rbx
0x140003b26  mov     rax, [rax+10h]
0x140003b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b2f  nop
0x140003b30  mov     rax, [rbx]
0x140003b33  mov     r8, rdi
0x140003b36  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x140003b3d  mov     rcx, rbx
0x140003b40  mov     rax, [rax]
0x140003b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b48  mov     edi, eax
0x140003b4a  mov     rax, [rbx]
0x140003b4d  mov     rcx, rbx
0x140003b50  mov     rax, [rax+10h]
0x140003b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b59  test    edi, edi
0x140003b5b  jns     short loc_140003B61
0x140003b5d  mov     eax, edi
0x140003b5f  jmp     short loc_140003B6A
0x140003b61  xor     eax, eax
0x140003b63  jmp     short loc_140003B6A
0x140003b65  mov     eax, 8007000Eh
0x140003b6a  mov     rbx, [rsp+28h+arg_0]
0x140003b6f  mov     rsi, [rsp+28h+arg_8]
0x140003b74  add     rsp, 20h
0x140003b78  pop     rdi
0x140003b79  retn
```
