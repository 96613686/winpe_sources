# ?remove@?QVectorChanged@?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@1?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@3Platform@@UE$AAAXVEventRegistrationToken@45@@Z

- ea: `0x140031890`
- end: `0x1400318a5`
- name: `?remove@?QVectorChanged@?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@1?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@3Platform@@UE$AAAXVEventRegistrationToken@45@@Z`
- size: `21`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `file_ops`

## import_xrefs

- `wincorlib!?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z` at `0x14003189e`

## pseudocode

```c
void __fastcall _remove__QVectorChanged___IObservableVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows__1__Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___3Platform__UE_AAAXVEventRegistrationToken_45__Z(
        __int64 a1,
        struct Platform::Details::EventLock *a2,
        __int64 a3,
        struct EventRegistrationToken a4)
{
  Platform::Details::EventSourceRemove((Platform::Details *)(a1 + 120), (void **)(a1 + 152), a2, a4);
}

```

## disassembly

```asm
0x140031890  mov     r8, rdx
0x140031893  lea     rdx, [rcx+98h]
0x14003189a  add     rcx, 78h ; 'x'
0x14003189e  jmp     cs:__imp_?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z; Platform::Details::EventSourceRemove(void * *,Platform::Details::EventLock *,Windows::Foundation::EventRegistrationToken)
```
