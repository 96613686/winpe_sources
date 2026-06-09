# ?RemoveAtEnd@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXXZ

- ea: `0x14002c5d0`
- end: `0x14002c676`
- name: `?RemoveAtEnd@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXXZ`
- size: `166`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14002c680`
- `0x14002c690`
- `0x1400308b0`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14002b96c`
- `0x14002c280`
- `0x14002c5d0`
- `0x140035010`

## import_xrefs

- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002c64b`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002c64b`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c63d`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c63d`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall _RemoveAtEnd__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAXXZ(
        __int64 a1)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 result; // rax
  void *Exception; // rcx
  __int64 v7; // rcx
  void *v8; // rax
  void *v9; // rax
  __int64 pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+28h] [rbp-20h] BYREF
  __int64 v12; // [rsp+30h] [rbp-18h] BYREF
  __int64 v13; // [rsp+50h] [rbp+8h]
  __int64 v14; // [rsp+50h] [rbp+8h]

  try
  {
    Platform::Collections::Details::IncrementCounter(a1 + 80);
    v2 = *(_QWORD **)(a1 + 96);
    v3 = v2[1];
    if ( *v2 == v3 )
    {
      Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
      v7 = Platform::OutOfBoundsException::OutOfBoundsException(Exception);
      pExceptionObject = __abi_winrt_ptr_ctor(v7);
      throw (Platform::OutOfBoundsException **)&pExceptionObject;
    }
    v4 = *(_QWORD *)(v3 - 8);
    if ( v4 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    v2[1] -= 8LL;
    result = Platform::Collections::Vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,std::equal_to<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>>::Notify(
               a1,
               2,
               (__int64)(*(_QWORD *)(*(_QWORD *)(a1 + 96) + 8LL) - **(_QWORD **)(a1 + 96)) >> 3);
  }
  catch ( std::bad_alloc )
  {
    v8 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v13 = Platform::OutOfMemoryException::OutOfMemoryException(v8);
    v11 = __abi_winrt_ptr_ctor(v13);
    throw (Platform::OutOfMemoryException **)&v11;
  }
  catch ( exception )
  {
    v9 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v14 = Platform::FailureException::FailureException(v9);
    v12 = __abi_winrt_ptr_ctor(v14);
    throw (Platform::FailureException **)&v12;
  }
  return result;
}

```

## disassembly

```asm
0x14002c5d0  mov     [rsp+arg_8], rbx
0x14002c5d5  push    rdi
0x14002c5d6  sub     rsp, 40h
0x14002c5da  mov     rbx, rcx
0x14002c5dd  add     rcx, 50h ; 'P'
0x14002c5e1  call    ?IncrementCounter@Details@Collections@Platform@@YAXAEAV?$shared_ptr@I@std@@@Z; Platform::Collections::Details::IncrementCounter(std::shared_ptr<uint> &)
0x14002c5e6  mov     rdi, [rbx+60h]
0x14002c5ea  mov     rcx, [rdi+8]
0x14002c5ee  cmp     [rdi], rcx
0x14002c5f1  jz      short loc_14002C635
0x14002c5f3  mov     rcx, [rcx-8]
0x14002c5f7  test    rcx, rcx
0x14002c5fa  jz      short loc_14002C608
0x14002c5fc  mov     rax, [rcx]
0x14002c5ff  mov     rax, [rax+10h]
0x14002c603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c608  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFF8h
0x14002c60d  mov     rax, [rbx+60h]
0x14002c611  mov     r8, [rax+8]
0x14002c615  sub     r8, [rax]
0x14002c618  sar     r8, 3
0x14002c61c  mov     edx, 2
0x14002c621  mov     rcx, rbx
0x14002c624  call    ?Notify@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@AE$AAAXW4CollectionChange@2Foundation@Windows@@I@Z; Platform::Collections::Vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,std::equal_to<Windows::UI::Xaml::Markup::IXamlMetadataProvider *>>::Notify(Windows::Foundation::Collections::CollectionChange,uint)
0x14002c629  nop
0x14002c62a  mov     rbx, [rsp+48h+arg_8]
0x14002c62f  add     rsp, 40h
0x14002c633  pop     rdi
0x14002c634  retn
0x14002c635  mov     edx, 90h
0x14002c63a  lea     ecx, [rdx-28h]
0x14002c63d  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002c643  mov     [rsp+48h+arg_0], rax
0x14002c648  mov     rcx, rax
0x14002c64b  call    cs:__imp_??0OutOfBoundsException@Platform@@QE$AAA@XZ; Platform::OutOfBoundsException::OutOfBoundsException(void)
0x14002c651  mov     [rsp+48h+arg_0], rax
0x14002c656  mov     rcx, rax
0x14002c659  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002c65e  mov     [rsp+48h+pExceptionObject], rax
0x14002c663  lea     rdx, _TI11PE$AAVOutOfBoundsException@Platform@@; pThrowInfo
0x14002c66a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x14002c66f  call    _CxxThrowException_0
```
