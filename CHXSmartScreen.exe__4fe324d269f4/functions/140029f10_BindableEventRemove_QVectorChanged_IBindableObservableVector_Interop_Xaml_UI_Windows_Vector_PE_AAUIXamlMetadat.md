# ?BindableEventRemove@?QVectorChanged@IBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@EE$AAAXVEventRegistrationToken@Foundation@6@@Z

- ea: `0x140029f10`
- end: `0x140029f25`
- name: `?BindableEventRemove@?QVectorChanged@IBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@EE$AAAXVEventRegistrationToken@Foundation@6@@Z`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140029f30`

## import_xrefs

- `wincorlib!?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z` at `0x140029f1e`

## pseudocode

```c
void __fastcall _BindableEventRemove__QVectorChanged_IBindableObservableVector_Interop_Xaml_UI_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___Collections_Platform__EE_AAAXVEventRegistrationToken_Foundation_6__Z(
        __int64 a1,
        struct Platform::Details::EventLock *a2,
        __int64 a3,
        struct EventRegistrationToken a4)
{
  Platform::Details::EventSourceRemove((Platform::Details *)(a1 + 128), (void **)(a1 + 152), a2, a4);
}

```

## disassembly

```asm
0x140029f10  mov     r8, rdx
0x140029f13  lea     rdx, [rcx+98h]
0x140029f1a  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140029f1e  jmp     cs:__imp_?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z; Platform::Details::EventSourceRemove(void * *,Platform::Details::EventLock *,Windows::Foundation::EventRegistrationToken)
```
