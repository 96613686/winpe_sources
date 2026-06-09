# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<UserOOBECreateUserObjectHandlerServer,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x1400070d0`
- end: `0x1400071a4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VUserOOBECreateUserObjectHandlerServer@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1400025d8`
- `0x1400070d0`
- `0x14000f010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<UserOOBECreateUserObjectHandlerServer,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<UserOOBECreateUserObjectHandlerServer,0>::`vftable';
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
0x1400070d0  push    rbx
0x1400070d2  push    rbp
0x1400070d3  push    rsi
0x1400070d4  push    rdi
0x1400070d5  sub     rsp, 28h
0x1400070d9  mov     rdi, r9
0x1400070dc  mov     rbp, r8
0x1400070df  mov     rsi, rcx
0x1400070e2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400070e9  mov     ecx, 18h; unsigned __int64
0x1400070ee  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400070f3  mov     rbx, rax
0x1400070f6  test    rax, rax
0x1400070f9  jz      loc_140007196
0x1400070ff  mov     dword ptr [rax+0Ch], 1
0x140007106  mov     dword ptr [rax+14h], 4
0x14000710d  lea     rax, ??_7?$SimpleClassFactory@VUserOOBECreateUserObjectHandlerServer@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<UserOOBECreateUserObjectHandlerServer,0>::`vftable'
0x140007114  mov     [rbx], rax
0x140007117  mov     rcx, rbx
0x14000711a  mov     rax, cs:off_140011CC8
0x140007121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007126  nop
0x140007127  mov     rax, [rbx]
0x14000712a  mov     rcx, rbx
0x14000712d  mov     rax, [rax+10h]
0x140007131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007136  nop
0x140007137  mov     eax, [rsi]
0x140007139  mov     [rbx+14h], eax
0x14000713c  mov     rax, [rbx]
0x14000713f  mov     r8, rdi
0x140007142  mov     rdx, rbp
0x140007145  mov     rcx, rbx
0x140007148  mov     rax, [rax]
0x14000714b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007150  mov     edi, eax
0x140007152  test    byte ptr [rsi], 1
0x140007155  jz      short loc_14000717D
0x140007157  test    eax, eax
0x140007159  js      short loc_140007179
0x14000715b  test    byte ptr [rsi], 4
0x14000715e  jz      short loc_140007175
0x140007160  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140007167  mov     rax, [rcx]
0x14000716a  mov     rax, [rax+8]
0x14000716e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007173  jmp     short loc_14000717D
0x140007175  xor     ebx, ebx
0x140007177  jmp     short loc_14000717D
0x140007179  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x14000717d  test    rbx, rbx
0x140007180  jz      short loc_140007192
0x140007182  mov     rax, [rbx]
0x140007185  mov     rcx, rbx
0x140007188  mov     rax, [rax+10h]
0x14000718c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007191  nop
0x140007192  mov     eax, edi
0x140007194  jmp     short loc_14000719B
0x140007196  mov     eax, 8007000Eh
0x14000719b  add     rsp, 28h
0x14000719f  pop     rdi
0x1400071a0  pop     rsi
0x1400071a1  pop     rbp
0x1400071a2  pop     rbx
0x1400071a3  retn
```
