# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CMVMasterDatastore,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002590`
- end: `0x180002664`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCMVMasterDatastore@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001e08`
- `0x180002590`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CMVMasterDatastore,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CMVMasterDatastore,0>::`vftable';
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
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
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
0x180002590  push    rbx
0x180002592  push    rbp
0x180002593  push    rsi
0x180002594  push    rdi
0x180002595  sub     rsp, 28h
0x180002599  mov     rdi, r9
0x18000259c  mov     rbp, r8
0x18000259f  mov     rsi, rcx
0x1800025a2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800025a9  mov     ecx, 18h; unsigned __int64
0x1800025ae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800025b3  mov     rbx, rax
0x1800025b6  test    rax, rax
0x1800025b9  jz      loc_180002656
0x1800025bf  mov     dword ptr [rax+0Ch], 1
0x1800025c6  mov     dword ptr [rax+14h], 4
0x1800025cd  lea     rax, ??_7?$SimpleClassFactory@VCMVMasterDatastore@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CMVMasterDatastore,0>::`vftable'
0x1800025d4  mov     [rbx], rax
0x1800025d7  mov     rcx, rbx
0x1800025da  mov     rax, cs:off_180013138
0x1800025e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e6  nop
0x1800025e7  mov     rax, [rbx]
0x1800025ea  mov     rcx, rbx
0x1800025ed  mov     rax, [rax+10h]
0x1800025f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025f6  nop
0x1800025f7  mov     eax, [rsi]
0x1800025f9  mov     [rbx+14h], eax
0x1800025fc  mov     rax, [rbx]
0x1800025ff  mov     r8, rdi
0x180002602  mov     rdx, rbp
0x180002605  mov     rcx, rbx
0x180002608  mov     rax, [rax]
0x18000260b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002610  mov     edi, eax
0x180002612  test    byte ptr [rsi], 1
0x180002615  jz      short loc_18000263D
0x180002617  test    eax, eax
0x180002619  js      short loc_180002639
0x18000261b  test    byte ptr [rsi], 4
0x18000261e  jz      short loc_180002635
0x180002620  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002627  mov     rax, [rcx]
0x18000262a  mov     rax, [rax+8]
0x18000262e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002633  jmp     short loc_18000263D
0x180002635  xor     ebx, ebx
0x180002637  jmp     short loc_18000263D
0x180002639  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000263d  test    rbx, rbx
0x180002640  jz      short loc_180002652
0x180002642  mov     rax, [rbx]
0x180002645  mov     rcx, rbx
0x180002648  mov     rax, [rax+10h]
0x18000264c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002651  nop
0x180002652  mov     eax, edi
0x180002654  jmp     short loc_18000265B
0x180002656  mov     eax, 8007000Eh
0x18000265b  add     rsp, 28h
0x18000265f  pop     rdi
0x180002660  pop     rsi
0x180002661  pop     rbp
0x180002662  pop     rbx
0x180002663  retn
```
