# ?GetMany@?Q?$IVectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$VectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAIIP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z

- ea: `0x14002b320`
- end: `0x14002b3d2`
- name: `?GetMany@?Q?$IVectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$VectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAIIP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140030a70`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x1400284b0`
- `0x14002b320`

## import_xrefs

- `wincorlib!??0ChangedStateException@Platform@@QE$AAA@XZ` at `0x14002b3a8`
- `wincorlib!??0ChangedStateException@Platform@@QE$AAA@XZ` at `0x14002b3a8`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002b368`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002b368`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b35a`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b39a`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b35a`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002b39a`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall _GetMany__Q__IVectorView_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____VectorView_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAIIP_01E_AAV__WriteOnlyArray_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_6__Z(
        __int64 a1,
        unsigned int a2,
        __int64 a3)
{
  _QWORD *v3; // r9
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  void *Exception; // [rsp+48h] [rbp+20h]

  if ( **(_DWORD **)(a1 + 64) != *(_DWORD *)(a1 + 96) )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    Exception = (void *)Platform::ChangedStateException::ChangedStateException(Exception);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::ChangedStateException **)&pExceptionObject;
  }
  v3 = *(_QWORD **)(a1 + 80);
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
0x14002b320  sub     rsp, 28h
0x14002b324  mov     r9, [rcx+40h]
0x14002b328  mov     eax, [rcx+60h]
0x14002b32b  cmp     [r9], eax
0x14002b32e  jnz     short loc_14002B392
0x14002b330  mov     r9, [rcx+50h]
0x14002b334  mov     rcx, [r9+8]
0x14002b338  sub     rcx, [r9]
0x14002b33b  sar     rcx, 3
0x14002b33f  mov     eax, edx
0x14002b341  cmp     rax, rcx
0x14002b344  ja      short loc_14002B352
0x14002b346  mov     rcx, r9
0x14002b349  add     rsp, 28h
0x14002b34d  jmp     ??$VectorGetMany@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@Collections@Platform@@YAIAEBV?$vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@V?$allocator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@IP$01E$AAV?$WriteOnlyArray@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@2@@Z
0x14002b352  mov     edx, 90h
0x14002b357  lea     ecx, [rdx-28h]
0x14002b35a  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002b360  mov     [rsp+28h+arg_18], rax
0x14002b365  mov     rcx, rax
0x14002b368  call    cs:__imp_??0OutOfBoundsException@Platform@@QE$AAA@XZ; Platform::OutOfBoundsException::OutOfBoundsException(void)
0x14002b36e  mov     [rsp+28h+arg_18], rax
0x14002b373  mov     rcx, rax
0x14002b376  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002b37b  mov     [rsp+28h+pExceptionObject], rax
0x14002b380  lea     rdx, _TI11PE$AAVOutOfBoundsException@Platform@@; pThrowInfo
0x14002b387  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002b38c  call    _CxxThrowException_0
0x14002b392  mov     edx, 90h
0x14002b397  lea     ecx, [rdx-28h]
0x14002b39a  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002b3a0  mov     [rsp+28h+arg_18], rax
0x14002b3a5  mov     rcx, rax
0x14002b3a8  call    cs:__imp_??0ChangedStateException@Platform@@QE$AAA@XZ; Platform::ChangedStateException::ChangedStateException(void)
0x14002b3ae  mov     [rsp+28h+arg_18], rax
0x14002b3b3  mov     rcx, rax
0x14002b3b6  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002b3bb  mov     [rsp+28h+pExceptionObject], rax
0x14002b3c0  lea     rdx, _TI11PE$AAVChangedStateException@Platform@@; pThrowInfo
0x14002b3c7  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002b3cc  call    _CxxThrowException_0
```
