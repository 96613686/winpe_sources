# ?GetXmlnsDefinitions@?QIXamlMetadataProvider@Markup@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAP$01E$AAV?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@XZ

- ea: `0x14002b8d0`
- end: `0x14002b965`
- name: `?GetXmlnsDefinitions@?QIXamlMetadataProvider@Markup@Xaml@UI@Windows@@App@CHXSmartScreen@@UE$AAAP$01E$AAV?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@XZ`
- size: `149`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000c590`
- `0x1400114b4`

## callees

- `0x14000b24c`
- `0x140028ba4`
- `0x14002b8d0`
- `0x140035010`

## import_xrefs

- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b8e2`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b913`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b8e2`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b913`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 _GetXmlnsDefinitions__QIXamlMetadataProvider_Markup_Xaml_UI_Windows__App_CHXSmartScreen__UE_AAAP_01E_AAV__Array_VXmlnsDefinition_Markup_Xaml_UI_Windows___00_Platform__XZ()
{
  void *v0; // rax
  _BYTE *v1; // rax
  _BYTE *v2; // rbx
  __int64 v3; // rdi
  void *v5; // [rsp+40h] [rbp+18h]

  v0 = Platform::Details::Heap::Allocate(0x58u, 0x88u);
  v1 = (_BYTE *)Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(v0);
  v2 = v1;
  v3 = (__int64)v1;
  if ( v1 )
  {
    if ( v1[76] )
    {
      v5 = Platform::Details::Heap::Allocate(0x58u, 0x88u);
      v3 = Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(
             v5,
             *((_QWORD *)v2 + 10),
             *((unsigned int *)v2 + 18));
    }
    else
    {
      (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v1 + 8LL))(v1);
    }
  }
  if ( v2 )
    (*(void (__fastcall **)(_BYTE *))(*(_QWORD *)v2 + 16LL))(v2);
  return v3;
}

```

## disassembly

```asm
0x14002b8d0  mov     [rsp+arg_0], rbx
0x14002b8d5  push    rdi
0x14002b8d6  sub     rsp, 20h
0x14002b8da  mov     edx, 88h
0x14002b8df  lea     ecx, [rdx-30h]
0x14002b8e2  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14002b8e8  mov     [rsp+28h+arg_8], rax
0x14002b8ed  mov     rcx, rax
0x14002b8f0  call    ??0?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@QE$AAA@I@Z; Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(uint)
0x14002b8f5  mov     rbx, rax
0x14002b8f8  mov     [rsp+28h+arg_8], rax
0x14002b8fd  mov     rdi, rax
0x14002b900  test    rax, rax
0x14002b903  jz      short loc_14002B943
0x14002b905  cmp     byte ptr [rax+4Ch], 0
0x14002b909  jz      short loc_14002B933
0x14002b90b  mov     edx, 88h
0x14002b910  lea     ecx, [rdx-30h]
0x14002b913  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x14002b919  mov     [rsp+28h+arg_10], rax
0x14002b91e  mov     r8d, [rbx+48h]
0x14002b922  mov     rdx, [rbx+50h]
0x14002b926  mov     rcx, rax
0x14002b929  call    ??0?$Array@VXmlnsDefinition@Markup@Xaml@UI@Windows@@$00@Platform@@QE$AAA@PEAVXmlnsDefinition@Markup@Xaml@UI@Windows@@I@Z; Platform::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>::Array<Windows::UI::Xaml::Markup::XmlnsDefinition,1>(Windows::UI::Xaml::Markup::XmlnsDefinition *,uint)
0x14002b92e  mov     rdi, rax
0x14002b931  jmp     short loc_14002B943
0x14002b933  mov     rax, [rax]
0x14002b936  mov     rcx, rbx
0x14002b939  mov     rax, [rax+8]
0x14002b93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b942  nop
0x14002b943  test    rbx, rbx
0x14002b946  jz      short loc_14002B957
0x14002b948  mov     rcx, [rbx]
0x14002b94b  mov     rax, [rcx+10h]
0x14002b94f  mov     rcx, rbx
0x14002b952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002b957  mov     rax, rdi
0x14002b95a  mov     rbx, [rsp+28h+arg_0]
0x14002b95f  add     rsp, 20h
0x14002b963  pop     rdi
0x14002b964  retn
```
