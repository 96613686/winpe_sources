# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x140006f10`
- end: `0x140006fe4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCloudExperienceHostExecuteCommand@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1400025d8`
- `0x140006f10`
- `0x14000f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[3] = 1;
  v7[5] = 4;
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>::`vftable';
  ((void (__fastcall *)(_DWORD *))Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v7);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  v8[5] = *a1;
  v9 = (**(__int64 (__fastcall ***)(_DWORD *, __int64, __int64))v8)(v8, a3, a4);
  v10 = v9;
  if ( (*(_BYTE *)a1 & 1) != 0 )
  {
    if ( v9 < 0 )
    {
      v8[5] &= 0xFFFFFFFA;
    }
    else if ( (*(_BYTE *)a1 & 4) != 0 )
    {
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    }
    else
    {
      v8 = 0;
    }
  }
  if ( v8 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
  return v10;
}

```

## disassembly

```asm
0x140006f10  push    rbx
0x140006f12  push    rbp
0x140006f13  push    rsi
0x140006f14  push    rdi
0x140006f15  sub     rsp, 28h
0x140006f19  mov     rdi, r9
0x140006f1c  mov     rbp, r8
0x140006f1f  mov     rsi, rcx
0x140006f22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140006f29  mov     ecx, 18h; unsigned __int64
0x140006f2e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140006f33  mov     rbx, rax
0x140006f36  test    rax, rax
0x140006f39  jz      loc_140006FD6
0x140006f3f  mov     dword ptr [rax+0Ch], 1
0x140006f46  mov     dword ptr [rax+14h], 4
0x140006f4d  lea     rax, ??_7?$SimpleClassFactory@VCloudExperienceHostExecuteCommand@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CloudExperienceHostExecuteCommand,0>::`vftable'
0x140006f54  mov     [rbx], rax
0x140006f57  mov     rcx, rbx
0x140006f5a  mov     rax, cs:off_140011C98
0x140006f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f66  nop
0x140006f67  mov     rax, [rbx]
0x140006f6a  mov     rcx, rbx
0x140006f6d  mov     rax, [rax+10h]
0x140006f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f76  nop
0x140006f77  mov     eax, [rsi]
0x140006f79  mov     [rbx+14h], eax
0x140006f7c  mov     rax, [rbx]
0x140006f7f  mov     r8, rdi
0x140006f82  mov     rdx, rbp
0x140006f85  mov     rcx, rbx
0x140006f88  mov     rax, [rax]
0x140006f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f90  mov     edi, eax
0x140006f92  test    byte ptr [rsi], 1
0x140006f95  jz      short loc_140006FBD
0x140006f97  test    eax, eax
0x140006f99  js      short loc_140006FB9
0x140006f9b  test    byte ptr [rsi], 4
0x140006f9e  jz      short loc_140006FB5
0x140006fa0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140006fa7  mov     rax, [rcx]
0x140006faa  mov     rax, [rax+8]
0x140006fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fb3  jmp     short loc_140006FBD
0x140006fb5  xor     ebx, ebx
0x140006fb7  jmp     short loc_140006FBD
0x140006fb9  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x140006fbd  test    rbx, rbx
0x140006fc0  jz      short loc_140006FD2
0x140006fc2  mov     rax, [rbx]
0x140006fc5  mov     rcx, rbx
0x140006fc8  mov     rax, [rax+10h]
0x140006fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fd1  nop
0x140006fd2  mov     eax, edi
0x140006fd4  jmp     short loc_140006FDB
0x140006fd6  mov     eax, 8007000Eh
0x140006fdb  add     rsp, 28h
0x140006fdf  pop     rdi
0x140006fe0  pop     rsi
0x140006fe1  pop     rbp
0x140006fe2  pop     rbx
0x140006fe3  retn
```
