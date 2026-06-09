# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x140001dc0`
- end: `0x140001e91`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCCPLUserMgrBroker@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140001558`
- `0x140001dc0`
- `0x140007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>>(
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
  if ( v7 )
  {
    v7[3] = 1;
    v7[5] = 4;
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>::`vftable';
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
      else
      {
        if ( (*(_BYTE *)a1 & 4) != 0 )
          (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                            + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
        else
          v8 = 0;
        if ( !v8 )
          return v10;
      }
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v8 + 16LL))(v8);
    return v10;
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x140001dc0  push    rbx
0x140001dc2  push    rbp
0x140001dc3  push    rsi
0x140001dc4  push    rdi
0x140001dc5  sub     rsp, 28h
0x140001dc9  mov     rsi, rcx
0x140001dcc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140001dd3  mov     ecx, 18h; unsigned __int64
0x140001dd8  mov     rdi, r9
0x140001ddb  mov     rbp, r8
0x140001dde  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140001de3  mov     rbx, rax
0x140001de6  test    rax, rax
0x140001de9  jz      loc_140001E83
0x140001def  mov     dword ptr [rax+0Ch], 1
0x140001df6  mov     rcx, rbx
0x140001df9  mov     dword ptr [rax+14h], 4
0x140001e00  lea     rax, ??_7?$SimpleClassFactory@VCCPLUserMgrBroker@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CCPLUserMgrBroker,0>::`vftable'
0x140001e07  mov     [rbx], rax
0x140001e0a  mov     rax, cs:off_1400090F0
0x140001e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e16  mov     rax, [rbx]
0x140001e19  mov     rcx, rbx
0x140001e1c  mov     rax, [rax+10h]
0x140001e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e25  mov     eax, [rsi]
0x140001e27  mov     r8, rdi
0x140001e2a  mov     [rbx+14h], eax
0x140001e2d  mov     rdx, rbp
0x140001e30  mov     rax, [rbx]
0x140001e33  mov     rcx, rbx
0x140001e36  mov     rax, [rax]
0x140001e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e3e  test    byte ptr [rsi], 1
0x140001e41  mov     edi, eax
0x140001e43  jz      short loc_140001E70
0x140001e45  test    eax, eax
0x140001e47  js      short loc_140001E6C
0x140001e49  test    byte ptr [rsi], 4
0x140001e4c  jz      short loc_140001E63
0x140001e4e  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140001e55  mov     rdx, [rcx]
0x140001e58  mov     rax, [rdx+8]
0x140001e5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e61  jmp     short loc_140001E65
0x140001e63  xor     ebx, ebx
0x140001e65  test    rbx, rbx
0x140001e68  jz      short loc_140001E7F
0x140001e6a  jmp     short loc_140001E70
0x140001e6c  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x140001e70  mov     rax, [rbx]
0x140001e73  mov     rcx, rbx
0x140001e76  mov     rax, [rax+10h]
0x140001e7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e7f  mov     eax, edi
0x140001e81  jmp     short loc_140001E88
0x140001e83  mov     eax, 8007000Eh
0x140001e88  add     rsp, 28h
0x140001e8c  pop     rdi
0x140001e8d  pop     rsi
0x140001e8e  pop     rbp
0x140001e8f  pop     rbx
0x140001e90  retn
```
