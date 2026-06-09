# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<BingFilterDS,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002d90`
- end: `0x180002e64`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VBingFilterDS@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002598`
- `0x180002d90`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<BingFilterDS,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<BingFilterDS,0>::`vftable';
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
0x180002d90  push    rbx
0x180002d92  push    rbp
0x180002d93  push    rsi
0x180002d94  push    rdi
0x180002d95  sub     rsp, 28h
0x180002d99  mov     rdi, r9
0x180002d9c  mov     rbp, r8
0x180002d9f  mov     rsi, rcx
0x180002da2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002da9  mov     ecx, 18h; unsigned __int64
0x180002dae  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002db3  mov     rbx, rax
0x180002db6  test    rax, rax
0x180002db9  jz      loc_180002E56
0x180002dbf  mov     dword ptr [rax+0Ch], 1
0x180002dc6  mov     dword ptr [rax+14h], 4
0x180002dcd  lea     rax, ??_7?$SimpleClassFactory@VBingFilterDS@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<BingFilterDS,0>::`vftable'
0x180002dd4  mov     [rbx], rax
0x180002dd7  mov     rcx, rbx
0x180002dda  mov     rax, cs:off_18000FB00
0x180002de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de6  nop
0x180002de7  mov     rax, [rbx]
0x180002dea  mov     rcx, rbx
0x180002ded  mov     rax, [rax+10h]
0x180002df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df6  nop
0x180002df7  mov     eax, [rsi]
0x180002df9  mov     [rbx+14h], eax
0x180002dfc  mov     rax, [rbx]
0x180002dff  mov     r8, rdi
0x180002e02  mov     rdx, rbp
0x180002e05  mov     rcx, rbx
0x180002e08  mov     rax, [rax]
0x180002e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e10  mov     edi, eax
0x180002e12  test    byte ptr [rsi], 1
0x180002e15  jz      short loc_180002E3D
0x180002e17  test    eax, eax
0x180002e19  js      short loc_180002E39
0x180002e1b  test    byte ptr [rsi], 4
0x180002e1e  jz      short loc_180002E35
0x180002e20  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002e27  mov     rax, [rcx]
0x180002e2a  mov     rax, [rax+8]
0x180002e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e33  jmp     short loc_180002E3D
0x180002e35  xor     ebx, ebx
0x180002e37  jmp     short loc_180002E3D
0x180002e39  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180002e3d  test    rbx, rbx
0x180002e40  jz      short loc_180002E52
0x180002e42  mov     rax, [rbx]
0x180002e45  mov     rcx, rbx
0x180002e48  mov     rax, [rax+10h]
0x180002e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e51  nop
0x180002e52  mov     eax, edi
0x180002e54  jmp     short loc_180002E5B
0x180002e56  mov     eax, 8007000Eh
0x180002e5b  add     rsp, 28h
0x180002e5f  pop     rdi
0x180002e60  pop     rsi
0x180002e61  pop     rbp
0x180002e62  pop     rbx
0x180002e63  retn
```
