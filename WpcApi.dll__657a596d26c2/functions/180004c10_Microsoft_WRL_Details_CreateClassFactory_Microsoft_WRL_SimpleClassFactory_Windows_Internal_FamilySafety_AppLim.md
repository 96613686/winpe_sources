# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180004c10`
- end: `0x180004ce4`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VParentalControlsAppInventory@AppLimits@FamilySafety@Internal@Windows@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003308`
- `0x180004c10`
- `0x18002c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,0>::`vftable';
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
0x180004c10  push    rbx
0x180004c12  push    rbp
0x180004c13  push    rsi
0x180004c14  push    rdi
0x180004c15  sub     rsp, 28h
0x180004c19  mov     rdi, r9
0x180004c1c  mov     rbp, r8
0x180004c1f  mov     rsi, rcx
0x180004c22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004c29  mov     ecx, 18h; unsigned __int64
0x180004c2e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180004c33  mov     rbx, rax
0x180004c36  test    rax, rax
0x180004c39  jz      loc_180004CD6
0x180004c3f  mov     dword ptr [rax+0Ch], 1
0x180004c46  mov     dword ptr [rax+14h], 4
0x180004c4d  lea     rax, ??_7?$SimpleClassFactory@VParentalControlsAppInventory@AppLimits@FamilySafety@Internal@Windows@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<Windows::Internal::FamilySafety::AppLimits::ParentalControlsAppInventory,0>::`vftable'
0x180004c54  mov     [rbx], rax
0x180004c57  mov     rcx, rbx
0x180004c5a  mov     rax, cs:off_18002D2E0
0x180004c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c66  nop
0x180004c67  mov     rax, [rbx]
0x180004c6a  mov     rcx, rbx
0x180004c6d  mov     rax, [rax+10h]
0x180004c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c76  nop
0x180004c77  mov     eax, [rsi]
0x180004c79  mov     [rbx+14h], eax
0x180004c7c  mov     rax, [rbx]
0x180004c7f  mov     r8, rdi
0x180004c82  mov     rdx, rbp
0x180004c85  mov     rcx, rbx
0x180004c88  mov     rax, [rax]
0x180004c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c90  mov     edi, eax
0x180004c92  test    byte ptr [rsi], 1
0x180004c95  jz      short loc_180004CBD
0x180004c97  test    eax, eax
0x180004c99  js      short loc_180004CB9
0x180004c9b  test    byte ptr [rsi], 4
0x180004c9e  jz      short loc_180004CB5
0x180004ca0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004ca7  mov     rax, [rcx]
0x180004caa  mov     rax, [rax+8]
0x180004cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cb3  jmp     short loc_180004CBD
0x180004cb5  xor     ebx, ebx
0x180004cb7  jmp     short loc_180004CBD
0x180004cb9  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x180004cbd  test    rbx, rbx
0x180004cc0  jz      short loc_180004CD2
0x180004cc2  mov     rax, [rbx]
0x180004cc5  mov     rcx, rbx
0x180004cc8  mov     rax, [rax+10h]
0x180004ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cd1  nop
0x180004cd2  mov     eax, edi
0x180004cd4  jmp     short loc_180004CDB
0x180004cd6  mov     eax, 8007000Eh
0x180004cdb  add     rsp, 28h
0x180004cdf  pop     rdi
0x180004ce0  pop     rsi
0x180004ce1  pop     rbp
0x180004ce2  pop     rbx
0x180004ce3  retn
```
