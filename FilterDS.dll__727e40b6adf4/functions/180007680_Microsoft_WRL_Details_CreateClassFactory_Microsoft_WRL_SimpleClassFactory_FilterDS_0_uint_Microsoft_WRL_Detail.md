# Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<FilterDS,0>>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180007680`
- end: `0x180007754`
- name: `??$CreateClassFactory@V?$SimpleClassFactory@VFilterDS@@$0A@@WRL@Microsoft@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `212`
- prototype: `__int64 __fastcall(_DWORD *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002a70`
- `0x180007680`
- `0x180024010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateClassFactory<Microsoft::WRL::SimpleClassFactory<FilterDS,0>>(
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
  *(_QWORD *)v7 = &Microsoft::WRL::SimpleClassFactory<FilterDS,0>::`vftable';
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
0x180007680  push    rbx
0x180007682  push    rbp
0x180007683  push    rsi
0x180007684  push    rdi
0x180007685  sub     rsp, 28h
0x180007689  mov     rdi, r9
0x18000768c  mov     rbp, r8
0x18000768f  mov     rsi, rcx
0x180007692  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007699  mov     ecx, 18h; unsigned __int64
0x18000769e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800076a3  mov     rbx, rax
0x1800076a6  test    rax, rax
0x1800076a9  jz      loc_180007746
0x1800076af  mov     dword ptr [rax+0Ch], 1
0x1800076b6  mov     dword ptr [rax+14h], 4
0x1800076bd  lea     rax, ??_7?$SimpleClassFactory@VFilterDS@@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::SimpleClassFactory<FilterDS,0>::`vftable'
0x1800076c4  mov     [rbx], rax
0x1800076c7  mov     rcx, rbx
0x1800076ca  mov     rax, cs:off_180025B90
0x1800076d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076d6  nop
0x1800076d7  mov     rax, [rbx]
0x1800076da  mov     rcx, rbx
0x1800076dd  mov     rax, [rax+10h]
0x1800076e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076e6  nop
0x1800076e7  mov     eax, [rsi]
0x1800076e9  mov     [rbx+14h], eax
0x1800076ec  mov     rax, [rbx]
0x1800076ef  mov     r8, rdi
0x1800076f2  mov     rdx, rbp
0x1800076f5  mov     rcx, rbx
0x1800076f8  mov     rax, [rax]
0x1800076fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007700  mov     edi, eax
0x180007702  test    byte ptr [rsi], 1
0x180007705  jz      short loc_18000772D
0x180007707  test    eax, eax
0x180007709  js      short loc_180007729
0x18000770b  test    byte ptr [rsi], 4
0x18000770e  jz      short loc_180007725
0x180007710  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007717  mov     rax, [rcx]
0x18000771a  mov     rax, [rax+8]
0x18000771e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007723  jmp     short loc_18000772D
0x180007725  xor     ebx, ebx
0x180007727  jmp     short loc_18000772D
0x180007729  and     dword ptr [rbx+14h], 0FFFFFFFAh
0x18000772d  test    rbx, rbx
0x180007730  jz      short loc_180007742
0x180007732  mov     rax, [rbx]
0x180007735  mov     rcx, rbx
0x180007738  mov     rax, [rax+10h]
0x18000773c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007741  nop
0x180007742  mov     eax, edi
0x180007744  jmp     short loc_18000774B
0x180007746  mov     eax, 8007000Eh
0x18000774b  add     rsp, 28h
0x18000774f  pop     rdi
0x180007750  pop     rsi
0x180007751  pop     rbp
0x180007752  pop     rbx
0x180007753  retn
```
