# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<ServerFolder,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180009b50`
- end: `0x180009c24`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VServerFolder@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800020d0`
- `0x180009b50`
- `0x180019010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<ServerFolder,0>>(
        _DWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v7; // rax
  _DWORD *v8; // rbx
  int v9; // eax
  unsigned int v10; // edi

  v7 = operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v8 = v7;
  if ( !v7 )
    return 2147942414LL;
  v7[3] = 1;
  v7[5] = 4;
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<ServerFolder,0>::`vftable';
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
0x180009b50  push    rbx
0x180009b52  push    rbp
0x180009b53  push    rsi
0x180009b54  push    rdi
0x180009b55  sub     rsp, 28h
0x180009b59  mov     rdi, r9
0x180009b5c  mov     rbp, r8
0x180009b5f  mov     rsi, rcx
0x180009b62  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b69  mov     ecx, 18h; unsigned __int64
0x180009b6e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b73  mov     rbx, rax
0x180009b76  test    rax, rax
0x180009b79  jz      loc_180009C16
0x180009b7f  mov     dword ptr [rax+0Ch], 1
0x180009b86  mov     dword ptr [rax+14h], 4
0x180009b8d  lea     rax, ??_7?$SimpleClassFactory@VServerFolder@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<ServerFolder,0>::`vftable'
0x180009b94  mov     [rbx], rax
0x180009b97  mov     rcx, rbx
0x180009b9a  mov     rax, cs:off_18001A5E0
0x180009ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba6  nop
0x180009ba7  mov     rax, [rbx]
0x180009baa  mov     rcx, rbx
0x180009bad  mov     rax, [rax+10h]
0x180009bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bb6  nop
0x180009bb7  mov     eax, [rsi]
0x180009bb9  mov     [rbx+14h], eax
0x180009bbc  mov     rax, [rbx]
0x180009bbf  mov     r8, rdi
0x180009bc2  mov     rdx, rbp
0x180009bc5  mov     rcx, rbx
0x180009bc8  mov     rax, [rax]
0x180009bcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bd0  mov     edi, eax
0x180009bd2  test    byte ptr [rsi], 1
0x180009bd5  jz      short loc_180009BFD
0x180009bd7  test    eax, eax
0x180009bd9  js      short loc_180009BF9
0x180009bdb  test    byte ptr [rsi], 4
0x180009bde  jz      short loc_180009BF5
0x180009be0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009be7  mov     rax, [rcx]
0x180009bea  mov     rax, [rax+8]
0x180009bee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009bf3  jmp     short loc_180009BFD
0x180009bf5  xor     ebx, ebx
0x180009bf7  jmp     short loc_180009BFD
0x180009bf9  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180009bfd  test    rbx, rbx
0x180009c00  jz      short loc_180009C12
0x180009c02  mov     rax, [rbx]
0x180009c05  mov     rcx, rbx
0x180009c08  mov     rax, [rax+10h]
0x180009c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c11  nop
0x180009c12  mov     eax, edi
0x180009c14  jmp     short loc_180009C1B
0x180009c16  mov     eax, 8007000Eh
0x180009c1b  add     rsp, 28h
0x180009c1f  pop     rdi
0x180009c20  pop     rsi
0x180009c21  pop     rbp
0x180009c22  pop     rbx
0x180009c23  retn
```
