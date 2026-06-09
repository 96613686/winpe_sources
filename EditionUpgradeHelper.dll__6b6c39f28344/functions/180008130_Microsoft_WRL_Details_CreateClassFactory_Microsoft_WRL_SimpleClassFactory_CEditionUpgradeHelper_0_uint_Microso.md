# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CEditionUpgradeHelper,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180008130`
- end: `0x180008201`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCEditionUpgradeHelper@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `209`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001d0c`
- `0x180008130`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CEditionUpgradeHelper,0>>(
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
    *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CEditionUpgradeHelper,0>::`vftable';
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
0x180008130  push    rbx
0x180008132  push    rbp
0x180008133  push    rsi
0x180008134  push    rdi
0x180008135  sub     rsp, 28h
0x180008139  mov     rsi, rcx
0x18000813c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180008143  mov     ecx, 18h; unsigned __int64
0x180008148  mov     rdi, r9
0x18000814b  mov     rbp, r8
0x18000814e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180008153  mov     rbx, rax
0x180008156  test    rax, rax
0x180008159  jz      loc_1800081F3
0x18000815f  mov     dword ptr [rax+0Ch], 1
0x180008166  mov     rcx, rbx
0x180008169  mov     dword ptr [rax+14h], 4
0x180008170  lea     rax, ??_7?$SimpleClassFactory@VCEditionUpgradeHelper@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CEditionUpgradeHelper,0>::`vftable'
0x180008177  mov     [rbx], rax
0x18000817a  mov     rax, cs:off_180028398
0x180008181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008186  mov     rax, [rbx]
0x180008189  mov     rcx, rbx
0x18000818c  mov     rax, [rax+10h]
0x180008190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008195  mov     eax, [rsi]
0x180008197  mov     r8, rdi
0x18000819a  mov     [rbx+14h], eax
0x18000819d  mov     rdx, rbp
0x1800081a0  mov     rax, [rbx]
0x1800081a3  mov     rcx, rbx
0x1800081a6  mov     rax, [rax]
0x1800081a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ae  test    byte ptr [rsi], 1
0x1800081b1  mov     edi, eax
0x1800081b3  jz      short loc_1800081E0
0x1800081b5  test    eax, eax
0x1800081b7  js      short loc_1800081DC
0x1800081b9  test    byte ptr [rsi], 4
0x1800081bc  jz      short loc_1800081D3
0x1800081be  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800081c5  mov     rdx, [rcx]
0x1800081c8  mov     rax, [rdx+8]
0x1800081cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081d1  jmp     short loc_1800081D5
0x1800081d3  xor     ebx, ebx
0x1800081d5  test    rbx, rbx
0x1800081d8  jz      short loc_1800081EF
0x1800081da  jmp     short loc_1800081E0
0x1800081dc  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x1800081e0  mov     rax, [rbx]
0x1800081e3  mov     rcx, rbx
0x1800081e6  mov     rax, [rax+10h]
0x1800081ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ef  mov     eax, edi
0x1800081f1  jmp     short loc_1800081F8
0x1800081f3  mov     eax, 8007000Eh
0x1800081f8  add     rsp, 28h
0x1800081fc  pop     rdi
0x1800081fd  pop     rsi
0x1800081fe  pop     rbp
0x1800081ff  pop     rbx
0x180008200  retn
```
