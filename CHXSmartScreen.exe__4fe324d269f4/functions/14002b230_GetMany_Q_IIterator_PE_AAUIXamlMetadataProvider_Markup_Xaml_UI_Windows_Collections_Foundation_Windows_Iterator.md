# ?GetMany@?Q?$IIterator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$IteratorForVectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@2Platform@@UE$AAAIP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@7@@Z

- ea: `0x14002b230`
- end: `0x14002b29d`
- name: `?GetMany@?Q?$IIterator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$IteratorForVectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@2Platform@@UE$AAAIP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@7@@Z`
- size: `109`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140030310`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x1400284b0`
- `0x14002b230`

## import_xrefs

- `wincorlib!??0ChangedStateException@Platform@@QE$AAA@XZ` at `0x14002b273`
- `wincorlib!??0ChangedStateException@Platform@@QE$AAA@XZ` at `0x14002b273`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b265`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b265`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _GetMany__Q__IIterator_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____IteratorForVectorView_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Details_2Platform__UE_AAAIP_01E_AAV__WriteOnlyArray_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_7__Z(
        __int64 a1,
        __int64 a2)
{
  __int64 result; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  void *Exception; // [rsp+40h] [rbp+18h]

  if ( **(_DWORD **)(a1 + 48) != *(_DWORD *)(a1 + 80) )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    Exception = (void *)Platform::ChangedStateException::ChangedStateException(Exception);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::ChangedStateException **)&pExceptionObject;
  }
  result = Platform::Collections::Details::VectorGetMany<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>(
             *(_QWORD **)(a1 + 64),
             *(_DWORD *)(a1 + 84),
             a2);
  *(_DWORD *)(a1 + 84) += result;
  return result;
}

```

## disassembly

```asm
0x14002b230  push    rbx
0x14002b232  sub     rsp, 20h
0x14002b236  mov     rbx, rcx
0x14002b239  mov     r8, [rcx+30h]
0x14002b23d  mov     eax, [rcx+50h]
0x14002b240  cmp     [r8], eax
0x14002b243  jnz     short loc_14002B25D
0x14002b245  mov     r8, rdx
0x14002b248  mov     edx, [rcx+54h]
0x14002b24b  mov     rcx, [rcx+40h]
0x14002b24f  call    ??$VectorGetMany@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@Collections@Platform@@YAIAEBV?$vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@V?$allocator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@IP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@@Z
0x14002b254  add     [rbx+54h], eax
0x14002b257  add     rsp, 20h
0x14002b25b  pop     rbx
0x14002b25c  retn
0x14002b25d  mov     edx, 90h
0x14002b262  lea     ecx, [rdx-28h]
0x14002b265  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002b26b  mov     [rsp+28h+arg_10], rax
0x14002b270  mov     rcx, rax
0x14002b273  call    cs:__imp_??0ChangedStateException@Platform@@QE$AAA@XZ; Platform::ChangedStateException::ChangedStateException(void)
0x14002b279  mov     [rsp+28h+arg_10], rax
0x14002b27e  mov     rcx, rax
0x14002b281  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002b286  mov     [rsp+28h+pExceptionObject], rax
0x14002b28b  lea     rdx, _TI11PE$AAVChangedStateException@Platform@@; pThrowInfo
0x14002b292  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002b297  call    _CxxThrowException_0
```
