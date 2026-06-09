# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CmDebuggerApi,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180009de0`
- end: `0x180009eb4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VCmDebuggerApi@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180001574`
- `0x180009de0`
- `0x180010010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<CmDebuggerApi,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<CmDebuggerApi,0>::`vftable';
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
0x180009de0  push    rbx
0x180009de2  push    rbp
0x180009de3  push    rsi
0x180009de4  push    rdi
0x180009de5  sub     rsp, 28h
0x180009de9  mov     rdi, r9
0x180009dec  mov     rbp, r8
0x180009def  mov     rsi, rcx
0x180009df2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009df9  mov     ecx, 18h; unsigned __int64
0x180009dfe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e03  mov     rbx, rax
0x180009e06  test    rax, rax
0x180009e09  jz      loc_180009EA6
0x180009e0f  mov     dword ptr [rax+0Ch], 1
0x180009e16  mov     dword ptr [rax+14h], 4
0x180009e1d  lea     rax, ??_7?$SimpleClassFactory@VCmDebuggerApi@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<CmDebuggerApi,0>::`vftable'
0x180009e24  mov     [rbx], rax
0x180009e27  mov     rcx, rbx
0x180009e2a  mov     rax, cs:off_180011108
0x180009e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e36  nop
0x180009e37  mov     rax, [rbx]
0x180009e3a  mov     rcx, rbx
0x180009e3d  mov     rax, [rax+10h]
0x180009e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e46  nop
0x180009e47  mov     eax, [rsi]
0x180009e49  mov     [rbx+14h], eax
0x180009e4c  mov     rax, [rbx]
0x180009e4f  mov     r8, rdi
0x180009e52  mov     rdx, rbp
0x180009e55  mov     rcx, rbx
0x180009e58  mov     rax, [rax]
0x180009e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e60  mov     edi, eax
0x180009e62  test    byte ptr [rsi], 1
0x180009e65  jz      short loc_180009E8D
0x180009e67  test    eax, eax
0x180009e69  js      short loc_180009E89
0x180009e6b  test    byte ptr [rsi], 4
0x180009e6e  jz      short loc_180009E85
0x180009e70  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180009e77  mov     rax, [rcx]
0x180009e7a  mov     rax, [rax+8]
0x180009e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e83  jmp     short loc_180009E8D
0x180009e85  xor     ebx, ebx
0x180009e87  jmp     short loc_180009E8D
0x180009e89  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180009e8d  test    rbx, rbx
0x180009e90  jz      short loc_180009EA2
0x180009e92  mov     rax, [rbx]
0x180009e95  mov     rcx, rbx
0x180009e98  mov     rax, [rax+10h]
0x180009e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea1  nop
0x180009ea2  mov     eax, edi
0x180009ea4  jmp     short loc_180009EAB
0x180009ea6  mov     eax, 8007000Eh
0x180009eab  add     rsp, 28h
0x180009eaf  pop     rdi
0x180009eb0  pop     rsi
0x180009eb1  pop     rbp
0x180009eb2  pop     rbx
0x180009eb3  retn
```
