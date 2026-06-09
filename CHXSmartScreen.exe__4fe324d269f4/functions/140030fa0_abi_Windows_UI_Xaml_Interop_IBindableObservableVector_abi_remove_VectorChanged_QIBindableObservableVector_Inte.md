# ?__abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_remove_VectorChanged@?QIBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@UE$AAAJVEventRegistrationToken@Foundation@5@@Z

- ea: `0x140030fa0`
- end: `0x140030fda`
- name: `?__abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_remove_VectorChanged@?QIBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@UE$AAAJVEventRegistrationToken@Foundation@5@@Z`
- size: `58`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140030fe0`

## callees

- `0x140030fa0`

## import_xrefs

- `wincorlib!?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z` at `0x140030fc5`
- `wincorlib!?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z` at `0x140030fc5`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140030fb3`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140030fb3`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_remove_VectorChanged__QIBindableObservableVector_Interop_Xaml_UI_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___Collections_Platform__UE_AAAJVEventRegistrationToken_Foundation_5__Z(
        __int64 a1,
        struct Platform::Details::EventLock *a2,
        __int64 a3,
        struct EventRegistrationToken a4)
{
  struct Platform::Details::EventLock *v4; // r8

  v4 = a2;
  if ( *(_BYTE *)(a1 + 168) )
    __abi_WinRTraiseObjectDisposedException();
  try
  {
    Platform::Details::EventSourceRemove((Platform::Details *)(a1 + 128), (void **)(a1 + 152), v4, a4);
  }
  catch ( ... )
  {
    __abi_translateCurrentException(0);
  }
  return 0;
}

```

## disassembly

```asm
0x140030fa0  push    rbx
0x140030fa2  sub     rsp, 20h
0x140030fa6  mov     r8, rdx
0x140030fa9  xor     ebx, ebx
0x140030fab  cmp     [rcx+0A8h], bl
0x140030fb1  jz      short loc_140030FBA
0x140030fb3  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140030fb9  nop
0x140030fba  lea     rdx, [rcx+98h]
0x140030fc1  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140030fc5  call    cs:__imp_?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z; Platform::Details::EventSourceRemove(void * *,Platform::Details::EventLock *,Windows::Foundation::EventRegistrationToken)
0x140030fcb  nop
0x140030fcc  jmp     short loc_140030FD2
0x140030fce  mov     ebx, [rsp+28h+arg_0]
0x140030fd2  mov     eax, ebx
0x140030fd4  add     rsp, 20h
0x140030fd8  pop     rbx
0x140030fd9  retn
```
