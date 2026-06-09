# ?GetMany@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAIIP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z

- ea: `0x14002b2a4`
- end: `0x14002b30a`
- name: `?GetMany@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAIIP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002b310`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x1400284b0`
- `0x14002b2a4`

## import_xrefs

- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002b2e0`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002b2e0`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b2d2`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b2d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _GetMany__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAIIP_01E_AAV__WriteOnlyArray_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_6__Z(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  _QWORD *v3; // r9
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  void *Exception; // [rsp+48h] [rbp+20h]

  v3 = *(_QWORD **)(a1 + 96);
  if ( a2 > (unsigned __int64)((__int64)(v3[1] - *v3) >> 3) )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    Exception = (void *)Platform::OutOfBoundsException::OutOfBoundsException(Exception);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::OutOfBoundsException **)&pExceptionObject;
  }
  return Platform::Collections::Details::VectorGetMany<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>(
           v3,
           a2,
           a3);
}

```

## disassembly

```asm
0x14002b2a4  sub     rsp, 28h
0x14002b2a8  mov     r9, [rcx+60h]
0x14002b2ac  mov     rcx, [r9+8]
0x14002b2b0  sub     rcx, [r9]
0x14002b2b3  sar     rcx, 3
0x14002b2b7  mov     eax, edx
0x14002b2b9  cmp     rax, rcx
0x14002b2bc  ja      short loc_14002B2CA
0x14002b2be  mov     rcx, r9
0x14002b2c1  add     rsp, 28h
0x14002b2c5  jmp     ??$VectorGetMany@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@Collections@Platform@@YAIAEBV?$vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@V?$allocator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@IP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@@Z
0x14002b2ca  mov     edx, 90h
0x14002b2cf  lea     ecx, [rdx-28h]
0x14002b2d2  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002b2d8  mov     [rsp+28h+arg_18], rax
0x14002b2dd  mov     rcx, rax
0x14002b2e0  call    cs:__imp_??0OutOfBoundsException@Platform@@QE$AAA@XZ; Platform::OutOfBoundsException::OutOfBoundsException(void)
0x14002b2e6  mov     [rsp+28h+arg_18], rax
0x14002b2eb  mov     rcx, rax
0x14002b2ee  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002b2f3  mov     [rsp+28h+pExceptionObject], rax
0x14002b2f8  lea     rdx, _TI11PE$AAVOutOfBoundsException@Platform@@; pThrowInfo
0x14002b2ff  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002b304  call    _CxxThrowException_0
```
