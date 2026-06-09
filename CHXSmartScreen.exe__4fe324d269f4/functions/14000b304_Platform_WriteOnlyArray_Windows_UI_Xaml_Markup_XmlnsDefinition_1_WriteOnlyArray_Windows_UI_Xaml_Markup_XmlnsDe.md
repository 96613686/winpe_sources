# Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(Windows::UI::Xaml::Markup::XmlnsDefinition *,uint)

- ea: `0x14000b304`
- end: `0x14000b3a7`
- name: `??0?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@IE$AAA@PEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@I@Z`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b24c`

## callees

- `0x14000b304`
- `0x14000bf34`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x14000b31e`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x14000b31e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
        __int64 a1,
        __int64 a2,
        unsigned int a3)
{
  Platform::Object::Object(a1 + 16);
  *(_QWORD *)a1 = ___7__WriteOnlyArray_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__6B__I__WriteOnlyArray_VXmlnsDefinition_Markup_Xaml_UI_Windows___00PublicNonVirtuals_1__;
  *(_QWORD *)(a1 + 8) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable'};
  *(_QWORD *)(a1 + 16) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object'};
  *(_QWORD *)(a1 + 24) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown'};
  *(_QWORD *)(a1 + 32) = &Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  *(_QWORD *)(a1 + 64) = -1;
  if ( __abi_module )
    (**(void (__fastcall ***)(struct __abi_Module *))__abi_module)(__abi_module);
  *(_DWORD *)(a1 + 40) = 0;
  *(_BYTE *)(a1 + 44) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  if ( a3 )
  {
    *(_QWORD *)(a1 + 48) = Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::AllocateAndCopyElements(
                             a2,
                             a3);
    *(_DWORD *)(a1 + 40) = a3;
  }
  return a1;
}

```

## disassembly

```asm
0x14000b304  mov     [rsp+arg_0], rcx
0x14000b309  push    rbx
0x14000b30a  push    rbp
0x14000b30b  push    rsi
0x14000b30c  push    rdi
0x14000b30d  sub     rsp, 28h
0x14000b311  mov     esi, r8d
0x14000b314  mov     rbp, rdx
0x14000b317  mov     rdi, rcx
0x14000b31a  add     rcx, 10h
0x14000b31e  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x14000b324  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__I?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00PublicNonVirtuals@1@@
0x14000b32b  mov     [rdi], rax
0x14000b32e  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BIDisposable@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable'}
0x14000b335  mov     [rdi+8], rax
0x14000b339  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object'}
0x14000b340  mov     [rdi+10h], rax
0x14000b344  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__abi_IUnknown@@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown'}
0x14000b34b  mov     [rdi+18h], rax
0x14000b34f  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x14000b356  mov     [rdi+20h], rax
0x14000b35a  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x14000b362  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x14000b369  xor     ebx, ebx
0x14000b36b  test    rcx, rcx
0x14000b36e  jz      short loc_14000B37C
0x14000b370  mov     rax, [rcx]
0x14000b373  mov     rax, [rax]
0x14000b376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b37b  nop
0x14000b37c  mov     [rdi+28h], ebx
0x14000b37f  mov     [rdi+2Ch], bl
0x14000b382  mov     [rdi+30h], rbx
0x14000b386  test    esi, esi
0x14000b388  jz      short loc_14000B39B
0x14000b38a  mov     edx, esi
0x14000b38c  mov     rcx, rbp
0x14000b38f  call    ?AllocateAndCopyElements@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@KAPEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@PEBV34567@I@Z; Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::AllocateAndCopyElements(Windows::UI::Xaml::Markup::XmlnsDefinition const *,uint)
0x14000b394  mov     [rdi+30h], rax
0x14000b398  mov     [rdi+28h], esi
0x14000b39b  mov     rax, rdi
0x14000b39e  add     rsp, 28h
0x14000b3a2  pop     rdi
0x14000b3a3  pop     rsi
0x14000b3a4  pop     rbp
0x14000b3a5  pop     rbx
0x14000b3a6  retn
```
