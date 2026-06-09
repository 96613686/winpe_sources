# XamlTypeInfo::InfoProvider::XamlTypeInfoProvider::~XamlTypeInfoProvider(void)

- ea: `0x180051268`
- end: `0x18005129d`
- name: `??1XamlTypeInfoProvider@InfoProvider@XamlTypeInfo@@AE$AAA@XZ`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18005c0c0`

## callees

- `0x180050dc4`
- `0x180050e2c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051287`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051287`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180051296`

## pseudocode

```c
void __fastcall XamlTypeInfo::InfoProvider::XamlTypeInfoProvider::~XamlTypeInfoProvider(__int64 a1)
{
  std::_Tree<std::_Tmap_traits<Platform::String __gc *,Windows::UI::Xaml::Markup::IXamlMember __gc *,std::less<Platform::String __gc *>,std::allocator<std::pair<Platform::String __gc * const,Windows::UI::Xaml::Markup::IXamlMember __gc *>>,0>>::~_Tree<std::_Tmap_traits<Platform::String __gc *,Windows::UI::Xaml::Markup::IXamlMember __gc *,std::less<Platform::String __gc *>,std::allocator<std::pair<Platform::String __gc * const,Windows::UI::Xaml::Markup::IXamlMember __gc *>>,0>>(a1 + 128);
  std::_Tree<std::_Tmap_traits<Platform::String __gc *,Platform::WeakReference,std::less<Platform::String __gc *>,std::allocator<std::pair<Platform::String __gc * const,Platform::WeakReference>>,0>>::~_Tree<std::_Tmap_traits<Platform::String __gc *,Platform::WeakReference,std::less<Platform::String __gc *>,std::allocator<std::pair<Platform::String __gc * const,Platform::WeakReference>>,0>>(a1 + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 72));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 32));
}

```

## disassembly

```asm
0x180051268  push    rbx
0x18005126a  sub     rsp, 20h
0x18005126e  mov     rbx, rcx
0x180051271  sub     rcx, 0FFFFFFFFFFFFFF80h
0x180051275  call    ??1?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@PE$AAUIXamlMember@Markup@Xaml@UI@Windows@@U?$less@PE$AAVString@Platform@@@std@@V?$allocator@U?$pair@QE$AAVString@Platform@@PE$AAUIXamlMember@Markup@Xaml@UI@Windows@@@std@@@9@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Platform::String *,Windows::UI::Xaml::Markup::IXamlMember *,std::less<Platform::String *>,std::allocator<std::pair<Platform::String * const,Windows::UI::Xaml::Markup::IXamlMember *>>,0>>::~_Tree<std::_Tmap_traits<Platform::String *,Windows::UI::Xaml::Markup::IXamlMember *,std::less<Platform::String *>,std::allocator<std::pair<Platform::String * const,Windows::UI::Xaml::Markup::IXamlMember *>>,0>>(void)
0x18005127a  lea     rcx, [rbx+70h]
0x18005127e  call    ??1?$_Tree@V?$_Tmap_traits@PE$AAVString@Platform@@VWeakReference@2@U?$less@PE$AAVString@Platform@@@std@@V?$allocator@U?$pair@QE$AAVString@Platform@@VWeakReference@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Platform::String *,Platform::WeakReference,std::less<Platform::String *>,std::allocator<std::pair<Platform::String * const,Platform::WeakReference>>,0>>::~_Tree<std::_Tmap_traits<Platform::String *,Platform::WeakReference,std::less<Platform::String *>,std::allocator<std::pair<Platform::String * const,Platform::WeakReference>>,0>>(void)
0x180051283  lea     rcx, [rbx+48h]; lpCriticalSection
0x180051287  call    cs:__imp_DeleteCriticalSection
0x18005128d  lea     rcx, [rbx+20h]
0x180051291  add     rsp, 20h
0x180051295  pop     rbx
0x180051296  jmp     cs:__imp_DeleteCriticalSection
```
