# Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(uint)

- ea: `0x1400292c8`
- end: `0x14002934f`
- name: `??0?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@IE$AAA@I@Z`
- size: `135`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140028ba4`

## callees

- `0x1400292c8`
- `0x140035010`

## import_xrefs

- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1400292d9`
- `wincorlib!??0Object@Platform@@QE$AAA@XZ` at `0x1400292d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
        __int64 a1)
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
  return a1;
}

```

## disassembly

```asm
0x1400292c8  mov     [rsp+arg_8], rbx
0x1400292cd  push    rdi
0x1400292ce  sub     rsp, 20h
0x1400292d2  mov     rdi, rcx
0x1400292d5  add     rcx, 10h
0x1400292d9  call    cs:__imp_??0Object@Platform@@QE$AAA@XZ; Platform::Object::Object(void)
0x1400292df  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__I?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00PublicNonVirtuals@1@@
0x1400292e6  mov     [rdi], rax
0x1400292e9  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BIDisposable@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable'}
0x1400292f0  mov     [rdi+8], rax
0x1400292f4  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object'}
0x1400292fb  mov     [rdi+10h], rax
0x1400292ff  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__abi_IUnknown@@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown'}
0x140029306  mov     [rdi+18h], rax
0x14002930a  lea     rax, ??_7?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@@; const Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x140029311  mov     [rdi+20h], rax
0x140029315  mov     qword ptr [rdi+40h], 0FFFFFFFFFFFFFFFFh
0x14002931d  mov     rcx, cs:?__abi_module@@3PEAU__abi_Module@@EA; __abi_Module * __abi_module
0x140029324  xor     ebx, ebx
0x140029326  test    rcx, rcx
0x140029329  jz      short loc_140029337
0x14002932b  mov     rax, [rcx]
0x14002932e  mov     rax, [rax]
0x140029331  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140029336  nop
0x140029337  mov     [rdi+28h], ebx
0x14002933a  mov     [rdi+2Ch], bl
0x14002933d  mov     [rdi+30h], rbx
0x140029341  mov     rax, rdi
0x140029344  mov     rbx, [rsp+28h+arg_8]
0x140029349  add     rsp, 20h
0x14002934d  pop     rdi
0x14002934e  retn
```
