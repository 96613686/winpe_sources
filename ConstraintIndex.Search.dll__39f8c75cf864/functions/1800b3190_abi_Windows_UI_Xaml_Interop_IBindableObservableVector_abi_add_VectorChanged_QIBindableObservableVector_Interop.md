# ?__abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_add_VectorChanged@?QIBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@Collections@Platform@@UE$AAAJPE$AAVBindableVectorChangedEventHandler@2345@PEAVEventRegistrationToken@Foundation@5@@Z

- ea: `0x1800b3190`
- end: `0x1800b321b`
- name: `?__abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_add_VectorChanged@?QIBindableObservableVector@Interop@Xaml@UI@Windows@@?$Vector@PE$AAVString@Platform@@U?$equal_to@PE$AAVString@Platform@@@std@@$00@Collections@Platform@@UE$AAAJPE$AAVBindableVectorChangedEventHandler@2345@PEAVEventRegistrationToken@Foundation@5@@Z`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800b3230`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18003fff0`
- `0x1800b3190`

## import_xrefs

- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800b31ef`
- `wincorlib!?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z` at `0x1800b31ef`

## pseudocode

```c
__int64 __fastcall ___abi_Windows_UI_Xaml_Interop_IBindableObservableVector____abi_add_VectorChanged__QIBindableObservableVector_Interop_Xaml_UI_Windows____Vector_PE_AAVString_Platform__U__equal_to_PE_AAVString_Platform___std___00_Collections_Platform__UE_AAAJPE_AAVBindableVectorChangedEventHandler_2345_PEAVEventRegistrationToken_Foundation_5__Z(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v7; // [rsp+20h] [rbp-28h] BYREF

  __abi_winrt_throw_on_disposed(*(_BYTE *)(a1 + 168));
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
0x1800b3190  mov     [rsp+arg_18], rbx
0x1800b3195  push    rsi
0x1800b3196  push    rdi
0x1800b3197  push    r14
0x1800b3199  sub     rsp, 30h
0x1800b319d  mov     rax, cs:__security_cookie
0x1800b31a4  xor     rax, rsp
0x1800b31a7  mov     [rsp+48h+var_20], rax
0x1800b31ac  mov     rsi, r8
0x1800b31af  mov     r14, rdx
0x1800b31b2  mov     rdi, rcx
0x1800b31b5  mov     cl, [rcx+0A8h]; bool
0x1800b31bb  call    ?__abi_winrt_throw_on_disposed@@YAX_N@Z; __abi_winrt_throw_on_disposed(bool)
0x1800b31c0  xor     ebx, ebx
0x1800b31c2  xor     edx, edx; Val
0x1800b31c4  lea     r8d, [rbx+8]; Size
0x1800b31c8  lea     rcx, [rsp+48h+var_28]; void *
0x1800b31cd  call    memset_0
0x1800b31d2  mov     rax, [rsp+48h+var_28]
0x1800b31d7  mov     [rsi], rax
0x1800b31da  mov     byte ptr [rdi+70h], 1
0x1800b31de  lea     rdx, [rdi+98h]
0x1800b31e5  lea     rcx, [rdi+80h]
0x1800b31ec  mov     r8, r14
0x1800b31ef  call    cs:__imp_?EventSourceAdd@Details@Platform@@YA?AVEventRegistrationToken@Foundation@Windows@@PEAPEAXPEAUEventLock@12@PE$AAVDelegate@2@@Z; Platform::Details::EventSourceAdd(void * *,Platform::Details::EventLock *,Platform::Delegate *)
0x1800b31f5  mov     [rsi], rax
0x1800b31f8  jmp     short loc_1800B31FE
0x1800b31fa  mov     ebx, dword ptr [rsp+48h+var_28]
0x1800b31fe  mov     eax, ebx
0x1800b3200  mov     rcx, [rsp+48h+var_20]
0x1800b3205  xor     rcx, rsp; StackCookie
0x1800b3208  call    __security_check_cookie
0x1800b320d  mov     rbx, [rsp+48h+arg_18]
0x1800b3212  add     rsp, 30h
0x1800b3216  pop     r14
0x1800b3218  pop     rdi
0x1800b3219  pop     rsi
0x1800b321a  retn
```
