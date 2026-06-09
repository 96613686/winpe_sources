# ?add@?QVectorChanged@?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@1?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@3Platform@@UE$AAA?AVEventRegistrationToken@45@PE$AAV?$VectorChangedEventHandler@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@345@@Z

- ea: `0x140031370`
- end: `0x14003139a`
- name: `?add@?QVectorChanged@?$IObservableVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@1?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@3Platform@@UE$AAA?AVEventRegistrationToken@45@PE$AAV?$VectorChangedEventHandler@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@345@@Z`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x140031388`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x140031388`

## pseudocode

```c
_QWORD *__fastcall _add__QVectorChanged___IObservableVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows__1__Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___3Platform__UE_AAA_AVEventRegistrationToken_45_PE_AAV__VectorChangedEventHandler_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___345__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  *(_BYTE *)(a1 + 112) = 1;
  *a2 = Platform::Details::EventSourceAdd(a1 + 120, a1 + 152, a3);
  return a2;
}

```

## disassembly

```asm
0x140031370  push    rbx
0x140031372  sub     rsp, 20h
0x140031376  mov     rbx, rdx
0x140031379  mov     byte ptr [rcx+70h], 1
0x14003137d  lea     rdx, [rcx+98h]
0x140031384  add     rcx, 78h ; 'x'
0x140031388  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x14003138e  mov     [rbx], rax
0x140031391  mov     rax, rbx
0x140031394  add     rsp, 20h
0x140031398  pop     rbx
0x140031399  retn
```
