# Platform::WriteOnlyArray<Platform::String *,1>::WriteOnlyArray<Platform::String *,1>(Platform::String * *,uint)

- ea: `0x14002921c`
- end: `0x1400292bf`
- name: `??0?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@IE$AAA@PEAPE$AAVString@1@I@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140028aec`

## callees

- `0x14002921c`
- `0x140029ad8`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x140029236`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x140029236`

## pseudocode

```c
__int64 __fastcall Platform::WriteOnlyArray<Platform::String __gc *,1>::WriteOnlyArray<Platform::String __gc *,1>(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  Platform::Object::Object(a1 + 16);
  *(_QWORD *)a1 = ___7__WriteOnlyArray_PE_AAVString_Platform___00_Platform__6B__I__WriteOnlyArray_PE_AAVString_Platform___00PublicNonVirtuals_1__;
  *(_QWORD *)(a1 + 8) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `Platform::IDisposable'};
  *(_QWORD *)(a1 + 16) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `Platform::Object'};
  *(_QWORD *)(a1 + 24) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `__abi_IUnknown'};
  *(_QWORD *)(a1 + 32) = &Platform::WriteOnlyArray<Platform::String __gc *,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  *(_QWORD *)(a1 + 64) = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  *(_DWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 44) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 48) = Platform::WriteOnlyArray<Platform::String __gc *,1>::AllocateAndCopyElements(a2, a3);
    *(_DWORD *)(a1 + 40) = a3;
  }
  return a1;
}

```

## disassembly

```asm
0x14002921c  mov     [rsp+arg_0], rcx
0x140029221  push    rbx
0x140029222  push    rbp
0x140029223  push    rsi
0x140029224  push    rdi
0x140029225  sub     rsp, 28h
0x140029229  mov     esi, r8d
0x14002922c  mov     rbp, rdx
0x14002922f  mov     rdi, rcx
0x140029232  add     rcx, 10h
0x140029236  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x14002923c  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6B__I?$WriteOnlyArray@PE$AAVString@Platform@@$00PublicNonVirtuals@1@@
0x140029243  mov     [rdi], rax
0x140029246  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6BIDisposable@1@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `Platform::IDisposable'}
0x14002924d  mov     [rdi+8], rax
0x140029251  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6BObject@1@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `Platform::Object'}
0x140029258  mov     [rdi+10h], rax
0x14002925c  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6B__abi_IUnknown@@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `__abi_IUnknown'}
0x140029263  mov     [rdi+18h], rax
0x140029267  lea     rax, ??_7?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@@; const Platform::WriteOnlyArray<Platform::String *,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x14002926e  mov     [rdi+20h], rax
0x140029272  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x14002927a  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x140029281  xor     ebx, ebx
0x140029283  test    rcx, rcx
0x140029286  jz      short loc_140029294
0x140029288  mov     rax, [rcx]
0x14002928b  mov     rax, [rax]
0x14002928e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029293  nop
0x140029294  mov     [rdi+28h], ebx
0x140029297  mov     [rdi+2Ch], bl
0x14002929a  mov     [rdi+30h], rbx
0x14002929e  test    esi, esi
0x1400292a0  jz      short loc_1400292B3
0x1400292a2  mov     edx, esi
0x1400292a4  mov     rcx, rbp
0x1400292a7  call    ?AllocateAndCopyElements@?$WriteOnlyArray@PE$AAVString@Platform@@$00@Platform@@KAPEAPE$AAVString@2@PEBQE$AAV32@I@Z; Platform::WriteOnlyArray<Platform::String *,1>::AllocateAndCopyElements(Platform::String * const *,uint)
0x1400292ac  mov     [rdi+30h], rax
0x1400292b0  mov     [rdi+28h], esi
0x1400292b3  mov     rax, rdi
0x1400292b6  add     rsp, 28h
0x1400292ba  pop     rdi
0x1400292bb  pop     rsi
0x1400292bc  pop     rbp
0x1400292bd  pop     rbx
0x1400292be  retn
```
