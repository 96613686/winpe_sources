# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180008050`
- end: `0x180008121`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCEditionUpgradeBroker@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001d0c`
- `0x180008050`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>>(
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
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>::`vftable';
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
          (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
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
0x180008050  push    rbx
0x180008052  push    rbp
0x180008053  push    rsi
0x180008054  push    rdi
0x180008055  sub     rsp, 28h
0x180008059  mov     rsi, rcx
0x18000805c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008063  mov     ecx, 18h; unsigned __int64
0x180008068  mov     rdi, r9
0x18000806b  mov     rbp, r8
0x18000806e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008073  mov     rbx, rax
0x180008076  test    rax, rax
0x180008079  jz      loc_180008113
0x18000807f  mov     dword ptr [rax+0Ch], 1
0x180008086  mov     rcx, rbx
0x180008089  mov     dword ptr [rax+14h], 4
0x180008090  lea     rax, ??_7?$SimpleClassFactory@VCEditionUpgradeBroker@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CEditionUpgradeBroker,0>::`vftable'
0x180008097  mov     [rbx], rax
0x18000809a  mov     rax, cs:off_180028368
0x1800080a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080a6  mov     rax, [rbx]
0x1800080a9  mov     rcx, rbx
0x1800080ac  mov     rax, [rax+10h]
0x1800080b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080b5  mov     eax, [rsi]
0x1800080b7  mov     r8, rdi
0x1800080ba  mov     [rbx+14h], eax
0x1800080bd  mov     rdx, rbp
0x1800080c0  mov     rax, [rbx]
0x1800080c3  mov     rcx, rbx
0x1800080c6  mov     rax, [rax]
0x1800080c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080ce  test    byte ptr [rsi], 1
0x1800080d1  mov     edi, eax
0x1800080d3  jz      short loc_180008100
0x1800080d5  test    eax, eax
0x1800080d7  js      short loc_1800080FC
0x1800080d9  test    byte ptr [rsi], 4
0x1800080dc  jz      short loc_1800080F3
0x1800080de  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800080e5  mov     rdx, [rcx]
0x1800080e8  mov     rax, [rdx+8]
0x1800080ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080f1  jmp     short loc_1800080F5
0x1800080f3  xor     ebx, ebx
0x1800080f5  test    rbx, rbx
0x1800080f8  jz      short loc_18000810F
0x1800080fa  jmp     short loc_180008100
0x1800080fc  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180008100  mov     rax, [rbx]
0x180008103  mov     rcx, rbx
0x180008106  mov     rax, [rax+10h]
0x18000810a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000810f  mov     eax, edi
0x180008111  jmp     short loc_180008118
0x180008113  mov     eax, 8007000Eh
0x180008118  add     rsp, 28h
0x18000811c  pop     rdi
0x18000811d  pop     rsi
0x18000811e  pop     rbp
0x18000811f  pop     rbx
0x180008120  retn
```
