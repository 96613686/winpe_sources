# ?BindableEventAdd@?QVectorChanged@IBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@EE$AAA?AVEventRegistrationToken@Foundation@6@PE$AAVBindableVectorChangedEventHandler@3456@@Z

- ea: `0x140029ed0`
- end: `0x140029efa`
- name: `?BindableEventAdd@?QVectorChanged@IBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@EE$AAA?AVEventRegistrationToken@Foundation@6@PE$AAVBindableVectorChangedEventHandler@3456@@Z`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140029f00`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x140029ee8`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x140029ee8`

## pseudocode

```c
_QWORD *__fastcall _BindableEventAdd__QVectorChanged_IBindableObservableVector_Interop_Xaml_UI_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___Collections_Platform__EE_AAA_AVEventRegistrationToken_Foundation_6_PE_AAVBindableVectorChangedEventHandler_3456__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  *(_BYTE *)(a1 + 112) = 1;
  *a2 = Platform::Details::EventSourceAdd(a1 + 128, a1 + 152, a3);
  return a2;
}

```

## disassembly

```asm
0x140029ed0  push    rbx
0x140029ed2  sub     rsp, 20h
0x140029ed6  mov     rbx, rdx
0x140029ed9  mov     byte ptr [rcx+70h], 1
0x140029edd  lea     rdx, [rcx+98h]
0x140029ee4  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140029ee8  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x140029eee  mov     [rbx], rax
0x140029ef1  mov     rax, rbx
0x140029ef4  add     rsp, 20h
0x140029ef8  pop     rbx
0x140029ef9  retn
```
