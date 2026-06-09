# Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>(Windows::UI::Xaml::Markup::IXamlMetadataProvider * *,uint)

- ea: `0x140029170`
- end: `0x140029213`
- name: `??0?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@IE$AAA@PEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@I@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140028a34`

## callees

- `0x140029170`
- `0x140029a28`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x14002918a`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x14002918a`

## pseudocode

```c
__int64 __fastcall Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  Platform::Object::Object(a1 + 16);
  *(_QWORD *)a1 = ___7__WriteOnlyArray_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_Platform__6B__I__WriteOnlyArray_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00PublicNonVirtuals_1__;
  *(_QWORD *)(a1 + 8) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::`vftable'{for `Platform::IDisposable'};
  *(_QWORD *)(a1 + 16) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::`vftable'{for `Platform::Object'};
  *(_QWORD *)(a1 + 24) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::`vftable'{for `__abi_IUnknown'};
  *(_QWORD *)(a1 + 32) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  *(_QWORD *)(a1 + 64) = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  *(_DWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 44) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 48) = Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,1>::AllocateAndCopyElements(
                             a2,
                             a3);
    *(_DWORD *)(a1 + 40) = a3;
  }
  return a1;
}

```

## disassembly

```asm
0x140029170  mov     [rsp+arg_0], rcx
0x140029175  push    rbx
0x140029176  push    rbp
0x140029177  push    rsi
0x140029178  push    rdi
0x140029179  sub     rsp, 28h
0x14002917d  mov     esi, r8d
0x140029180  mov     rbp, rdx
0x140029183  mov     rdi, rcx
0x140029186  add     rcx, 10h
0x14002918a  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x140029190  lea     rax, ??_7?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@6B__I?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00PublicNonVirtuals@1@@
0x140029197  mov     [rdi], rax
0x14002919a  lea     rax, ??_7?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@6BIDisposable@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::`vftable'{for `Platform::IDisposable'}
0x1400291a1  mov     [rdi+8], rax
0x1400291a5  lea     rax, ??_7?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::`vftable'{for `Platform::Object'}
0x1400291ac  mov     [rdi+10h], rax
0x1400291b0  lea     rax, ??_7?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@6B__abi_IUnknown@@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::`vftable'{for `__abi_IUnknown'}
0x1400291b7  mov     [rdi+18h], rax
0x1400291bb  lea     rax, ??_7?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x1400291c2  mov     [rdi+20h], rax
0x1400291c6  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x1400291ce  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x1400291d5  xor     ebx, ebx
0x1400291d7  test    rcx, rcx
0x1400291da  jz      short loc_1400291E8
0x1400291dc  mov     rax, [rcx]
0x1400291df  mov     rax, [rax]
0x1400291e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400291e7  nop
0x1400291e8  mov     [rdi+28h], ebx
0x1400291eb  mov     [rdi+2Ch], bl
0x1400291ee  mov     [rdi+30h], rbx
0x1400291f2  test    esi, esi
0x1400291f4  jz      short loc_140029207
0x1400291f6  mov     edx, esi
0x1400291f8  mov     rcx, rbp
0x1400291fb  call    ?AllocateAndCopyElements@?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@Platform@@KAPEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@PEBQE$AAU34567@I@Z; Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,1>::AllocateAndCopyElements(Windows::UI::Xaml::Markup::IXamlMetadataProvider * const *,uint)
0x140029200  mov     [rdi+30h], rax
0x140029204  mov     [rdi+28h], esi
0x140029207  mov     rax, rdi
0x14002920a  add     rsp, 28h
0x14002920e  pop     rdi
0x14002920f  pop     rsi
0x140029210  pop     rbp
0x140029211  pop     rbx
0x140029212  retn
```
