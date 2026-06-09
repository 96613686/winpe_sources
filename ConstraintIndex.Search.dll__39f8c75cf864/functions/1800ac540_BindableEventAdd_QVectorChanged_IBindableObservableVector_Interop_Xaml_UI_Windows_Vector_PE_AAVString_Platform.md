# ?BindableEventAdd@?QVectorChanged@IBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@Collections@Platform@@EE$AAA?AVEventRegistrationToken@Foundation@6@PE$AAVBindableVectorChangedEventHandler@3456@@Z

- ea: `0x1800ac540`
- end: `0x1800ac56a`
- name: `?BindableEventAdd@?QVectorChanged@IBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@Collections@Platform@@EE$AAA?AVEventRegistrationToken@Foundation@6@PE$AAVBindableVectorChangedEventHandler@3456@@Z`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800ac570`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800ac558`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800ac558`

## pseudocode

```c
_QWORD *__fastcall _BindableEventAdd__QVectorChanged_IBindableObservableVector_Interop_Xaml_UI_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_Collections_Platform__EE_AAA_AVEventRegistrationToken_Foundation_6_PE_AAVBindableVectorChangedEventHandler_3456__Z(
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
0x1800ac540  push    rbx
0x1800ac542  sub     rsp, 20h
0x1800ac546  mov     rbx, rdx
0x1800ac549  mov     byte ptr [rcx+70h], 1
0x1800ac54d  lea     rdx, [rcx+98h]
0x1800ac554  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1800ac558  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x1800ac55e  mov     [rbx], rax
0x1800ac561  mov     rax, rbx
0x1800ac564  add     rsp, 20h
0x1800ac568  pop     rbx
0x1800ac569  retn
```
