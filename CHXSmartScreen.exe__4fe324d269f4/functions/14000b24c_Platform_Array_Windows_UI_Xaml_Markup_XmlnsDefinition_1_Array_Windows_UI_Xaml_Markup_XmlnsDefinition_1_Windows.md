# Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(Windows::UI::Xaml::Markup::XmlnsDefinition *,uint)

- ea: `0x14000b24c`
- end: `0x14000b2fb`
- name: `??0?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@QE$AAA@PEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@I@Z`
- size: `175`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140011920`
- `0x14002b8d0`

## callees

- `0x14000b304`

## import_xrefs

- `wincorlib!?GetIBoxArrayVtable@Details@Platform@@YAPEAXPEAX@Z` at `0x14000b2e3`
- `wincorlib!?GetIBoxArrayVtable@Details@Platform@@YAPEAXPEAX@Z` at `0x14000b2e3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Platform::Details *__fastcall Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
        Platform::Details *a1,
        __int64 a2,
        unsigned int a3)
{
  void *v4; // rdx

  Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
    (__int64)a1 + 32,
    a2,
    a3);
  *(_QWORD *)a1 = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::IBoxArray<Windows::UI::Xaml::Markup::XmlnsDefinition>'};
  *((_QWORD *)a1 + 1) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IValueType'};
  *((_QWORD *)a1 + 2) = ___7__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__6B__I__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00PublicNonVirtuals_1__;
  *((_QWORD *)a1 + 3) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable'};
  *((_QWORD *)a1 + 4) = ___7__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__6B__I__WriteOnlyArray_VXmlnsDefinition_Markup_Xaml_UI_Windows___00PublicNonVirtuals_1__;
  *((_QWORD *)a1 + 5) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'};
  *((_QWORD *)a1 + 6) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'};
  *((_QWORD *)a1 + 7) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'};
  *((_QWORD *)a1 + 8) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'};
  *((_QWORD *)a1 + 14) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown's `Platform::Details::IWeakReferenceSource'};
  *((_QWORD *)a1 + 15) = &Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'};
  *((_QWORD *)a1 + 1) = Platform::Details::GetIBoxArrayVtable(a1, v4);
  return a1;
}

```

## disassembly

```asm
0x14000b24c  mov     [rsp+arg_8], rbx
0x14000b251  mov     [rsp+arg_0], rcx
0x14000b256  push    rdi
0x14000b257  sub     rsp, 30h
0x14000b25b  mov     rdi, rcx
0x14000b25e  add     rcx, 20h ; ' '
0x14000b262  call    ??0?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@IE$AAA@PEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@I@Z; Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(Windows::UI::Xaml::Markup::XmlnsDefinition *,uint)
0x14000b267  nop
0x14000b268  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@?$IBoxArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::IBoxArray<Windows::UI::Xaml::Markup::XmlnsDefinition>'}
0x14000b26f  mov     [rdi], rax
0x14000b272  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BIValueType@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IValueType'}
0x14000b279  mov     [rdi+8], rax
0x14000b27d  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__I?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00PublicNonVirtuals@1@@
0x14000b284  mov     [rdi+10h], rax
0x14000b288  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BIDisposable@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable'}
0x14000b28f  mov     [rdi+18h], rax
0x14000b293  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__I?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00PublicNonVirtuals@1@@
0x14000b29a  mov     [rdi+20h], rax
0x14000b29e  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BIDisposable@1@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::IDisposable's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'}
0x14000b2a5  mov     [rdi+28h], rax
0x14000b2a9  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'}
0x14000b2b0  mov     [rdi+30h], rax
0x14000b2b4  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__abi_IUnknown@@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'}
0x14000b2bb  mov     [rdi+38h], rax
0x14000b2bf  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@?$WriteOnlyArray@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource's `Platform::WriteOnlyArray<Windows::UI::Xaml::Markup::XmlnsDefinition,1>'}
0x14000b2c6  mov     [rdi+40h], rax
0x14000b2ca  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6B__abi_IUnknown@@IWeakReferenceSource@Details@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `__abi_IUnknown's `Platform::Details::IWeakReferenceSource'}
0x14000b2d1  mov     [rdi+70h], rax
0x14000b2d5  lea     rax, ??_7?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@6BObject@1@IWeakReferenceSource@Details@1@@; const Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::`vftable'{for `Platform::Object's `Platform::Details::IWeakReferenceSource'}
0x14000b2dc  mov     [rdi+78h], rax
0x14000b2e0  mov     rcx, rdi
0x14000b2e3  call    cs:__imp_?GetIBoxArrayVtable@Details@Platform@@YAPEAXPEAX@Z; Platform::Details::GetIBoxArrayVtable(void *)
0x14000b2e9  mov     [rdi+8], rax
0x14000b2ed  mov     rax, rdi
0x14000b2f0  mov     rbx, [rsp+38h+arg_8]
0x14000b2f5  add     rsp, 30h
0x14000b2f9  pop     rdi
0x14000b2fa  retn
```
