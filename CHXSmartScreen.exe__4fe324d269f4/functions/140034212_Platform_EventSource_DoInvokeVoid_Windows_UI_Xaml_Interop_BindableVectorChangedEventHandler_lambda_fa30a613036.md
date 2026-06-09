# _Platform::EventSource::DoInvokeVoid_Windows::UI::Xaml::Interop::BindableVectorChangedEventHandler__lambda_fa30a613036bcec23797998bf71b5136____::_1_::catch$4

- ea: `0x140034212`
- end: `0x140034280`
- name: `_Platform::EventSource::DoInvokeVoid_Windows::UI::Xaml::Interop::BindableVectorChangedEventHandler__lambda_fa30a613036bcec23797998bf71b5136____::_1_::catch$4`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x140034212`

## import_xrefs

- `wincorlib!?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z` at `0x140034268`
- `wincorlib!?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z` at `0x140034268`

## pseudocode

```c
__int64 __fastcall Platform::EventSource::DoInvokeVoid_Windows::UI::Xaml::Interop::BindableVectorChangedEventHandler__lambda_fa30a613036bcec23797998bf71b5136____::_1_::catch_4(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        struct EventRegistrationToken a4)
{
  __int64 v5; // rcx
  int v6; // eax

  v5 = *(_QWORD *)(a2 + 88);
  v6 = *(_DWORD *)(v5 + 64);
  if ( v6 != -2147023174 && v6 != -2147417848 && v6 != -2146823277 && v6 != -1996357631 )
  {
    *(_QWORD *)(a2 + 56) = __abi_winrt_ptr_ctor(v5);
    throw (Platform::Exception **)(a2 + 56);
  }
  Platform::Details::EventSourceRemove(
    *(Platform::Details **)(a2 + 72),
    *(void ***)(a2 + 64),
    *(struct Platform::Details::EventLock **)(a2 + 112),
    a4);
  return 0;
}

```

## disassembly

```asm
0x140034212  mov     [rsp+arg_8], rdx
0x140034217  push    rbp
0x140034218  sub     rsp, 20h
0x14003421c  mov     rbp, rdx
0x14003421f  mov     rcx, [rbp+58h]
0x140034223  mov     eax, [rcx+40h]
0x140034226  cmp     eax, 800706BAh
0x14003422b  jz      short loc_14003425C
0x14003422d  cmp     eax, 80010108h
0x140034232  jz      short loc_14003425C
0x140034234  cmp     eax, 800A1393h
0x140034239  jz      short loc_14003425C
0x14003423b  cmp     eax, 89020001h
0x140034240  jz      short loc_14003425C
0x140034242  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x140034247  mov     [rbp+38h], rax
0x14003424b  lea     rdx, _TI9PE$AAVException@Platform@@; pThrowInfo
0x140034252  lea     rcx, [rbp+38h]; pExceptionObject
0x140034256  call    _CxxThrowException_0
0x14003425c  mov     r8, [rbp+70h]
0x140034260  mov     rdx, [rbp+40h]
0x140034264  mov     rcx, [rbp+48h]
0x140034268  call    cs:__imp_?EventSourceRemove@Details@Platform@@YAXPEAPEAXPEAUEventLock@12@VEventRegistrationToken@Foundation@Windows@@@Z; Platform::Details::EventSourceRemove(void * *,Platform::Details::EventLock *,Windows::Foundation::EventRegistrationToken)
0x14003426e  nop
0x14003426f  mov     rax, 0
0x140034279  add     rsp, 20h
0x14003427d  pop     rbp
0x14003427e  retn
```
