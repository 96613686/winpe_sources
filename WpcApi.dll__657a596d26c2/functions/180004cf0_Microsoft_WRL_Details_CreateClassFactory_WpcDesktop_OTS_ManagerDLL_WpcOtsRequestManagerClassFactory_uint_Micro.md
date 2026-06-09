# Microsoft::WRL::Details::CreateClassFactory<WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180004cf0`
- end: `0x180004dc4`
- name: `??$CreateClassFactory@VWpcOtsRequestManagerClassFactory@ManagerDLL@OTS@WpcDesktop@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180003308`
- `0x180004cf0`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory>(
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
  *(_QWORD *)v7 = &WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory::`vftable';
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
0x180004cf0  push    rbx
0x180004cf2  push    rbp
0x180004cf3  push    rsi
0x180004cf4  push    rdi
0x180004cf5  sub     rsp, 28h
0x180004cf9  mov     rdi, r9
0x180004cfc  mov     rbp, r8
0x180004cff  mov     rsi, rcx
0x180004d02  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004d09  mov     ecx, 18h; unsigned __int64
0x180004d0e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004d13  mov     rbx, rax
0x180004d16  test    rax, rax
0x180004d19  jz      loc_180004DB6
0x180004d1f  mov     dword ptr [rax+0Ch], 1
0x180004d26  mov     dword ptr [rax+14h], 4
0x180004d2d  lea     rax, ??_7WpcOtsRequestManagerClassFactory@ManagerDLL@OTS@WpcDesktop@@6B@; const WpcDesktop::OTS::ManagerDLL::WpcOtsRequestManagerClassFactory::`vftable'
0x180004d34  mov     [rbx], rax
0x180004d37  mov     rcx, rbx
0x180004d3a  mov     rax, cs:off_18002D318
0x180004d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d46  nop
0x180004d47  mov     rax, [rbx]
0x180004d4a  mov     rcx, rbx
0x180004d4d  mov     rax, [rax+10h]
0x180004d51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d56  nop
0x180004d57  mov     eax, [rsi]
0x180004d59  mov     [rbx+14h], eax
0x180004d5c  mov     rax, [rbx]
0x180004d5f  mov     r8, rdi
0x180004d62  mov     rdx, rbp
0x180004d65  mov     rcx, rbx
0x180004d68  mov     rax, [rax]
0x180004d6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d70  mov     edi, eax
0x180004d72  test    byte ptr [rsi], 1
0x180004d75  jz      short loc_180004D9D
0x180004d77  test    eax, eax
0x180004d79  js      short loc_180004D99
0x180004d7b  test    byte ptr [rsi], 4
0x180004d7e  jz      short loc_180004D95
0x180004d80  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004d87  mov     rax, [rcx]
0x180004d8a  mov     rax, [rax+8]
0x180004d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d93  jmp     short loc_180004D9D
0x180004d95  xor     ebx, ebx
0x180004d97  jmp     short loc_180004D9D
0x180004d99  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180004d9d  test    rbx, rbx
0x180004da0  jz      short loc_180004DB2
0x180004da2  mov     rax, [rbx]
0x180004da5  mov     rcx, rbx
0x180004da8  mov     rax, [rax+10h]
0x180004dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004db1  nop
0x180004db2  mov     eax, edi
0x180004db4  jmp     short loc_180004DBB
0x180004db6  mov     eax, 8007000Eh
0x180004dbb  add     rsp, 28h
0x180004dbf  pop     rdi
0x180004dc0  pop     rsi
0x180004dc1  pop     rbp
0x180004dc2  pop     rbx
0x180004dc3  retn
```
