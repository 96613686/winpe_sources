# ?__abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_add_VectorChanged@?QIBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@UE$AAAJPE$AAVBindableVectorChangedEventHandler@2345@PEAVEventRegistrationToken@Foundation@5@@Z

- ea: `0x140030ef0`
- end: `0x140030f7f`
- name: `?__abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_add_VectorChanged@?QIBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@UE$AAAJPE$AAVBindableVectorChangedEventHandler@2345@PEAVEventRegistrationToken@Foundation@5@@Z`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140030f90`

## callees

- `0x14000342d`
- `0x140030ef0`
- `0x140031960`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x140030f53`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x140030f53`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140030f1f`
- `wincorlib!?__abi_WinRTraiseObjectDisposedException@@YAXXZ` at `0x140030f1f`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_add_VectorChanged__QIBindableObservableVector_Interop_Xaml_UI_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___Collections_Platform__UE_AAAJPE_AAVBindableVectorChangedEventHandler_2345_PEAVEventRegistrationToken_Foundation_5__Z(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF

  if ( *(_BYTE *)(a1 + 168) )
  {
    __abi_WinRTraiseObjectDisposedException();
    __debugbreak();
  }
  memset_0(&v7, 0, sizeof(v7));
  try
  {
    *a3 = v7;
    *(_BYTE *)(a1 + 112) = 1;
    *a3 = Platform::Details::EventSourceAdd(a1 + 128, a1 + 152, a2);
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
0x140030ef0  mov     [rsp+arg_18], rbx
0x140030ef5  push    rsi
0x140030ef6  push    rdi
0x140030ef7  push    r14
0x140030ef9  sub     rsp, 30h
0x140030efd  mov     rax, cs:__security_cookie
0x140030f04  xor     rax, rsp
0x140030f07  mov     [rsp+48h+var_20], rax
0x140030f0c  mov     rsi, r8
0x140030f0f  mov     r14, rdx
0x140030f12  mov     rdi, rcx
0x140030f15  xor     ebx, ebx
0x140030f17  cmp     [rcx+0A8h], bl
0x140030f1d  jz      short loc_140030F26
0x140030f1f  call    cs:__imp_?__abi_WinRTraiseObjectDisposedException@@YAXXZ; __abi_WinRTraiseObjectDisposedException(void)
0x140030f25  int     3; Trap to Debugger
0x140030f26  xor     edx, edx; Val
0x140030f28  lea     r8d, [rdx+8]; Size
0x140030f2c  lea     rcx, [rsp+48h+var_28]; void *
0x140030f31  call    memset_0
0x140030f36  mov     rax, [rsp+48h+var_28]
0x140030f3b  mov     [rsi], rax
0x140030f3e  mov     byte ptr [rdi+70h], 1
0x140030f42  lea     rdx, [rdi+98h]
0x140030f49  lea     rcx, [rdi+80h]
0x140030f50  mov     r8, r14
0x140030f53  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x140030f59  mov     [rsi], rax
0x140030f5c  jmp     short loc_140030F62
0x140030f5e  mov     ebx, dword ptr [rsp+48h+var_28]
0x140030f62  mov     eax, ebx
0x140030f64  mov     rcx, [rsp+48h+var_20]
0x140030f69  xor     rcx, rsp; StackCookie
0x140030f6c  call    __security_check_cookie
0x140030f71  mov     rbx, [rsp+48h+arg_18]
0x140030f76  add     rsp, 30h
0x140030f7a  pop     r14
0x140030f7c  pop     rdi
0x140030f7d  pop     rsi
0x140030f7e  retn
```
