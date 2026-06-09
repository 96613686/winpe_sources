# ?ReplaceAll@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXP$01E$ABV?$Array@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z

- ea: `0x14002c6a0`
- end: `0x14002c781`
- name: `?ReplaceAll@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXP$01E$ABV?$Array@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@$00@6@@Z`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x14002c790`
- `0x140030900`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x140028614`
- `0x14002b96c`
- `0x14002c280`
- `0x14002c6a0`
- `0x140035010`

## import_xrefs

- `wincorlib!??0OutOfMemoryException@Platform@@QE$AAA@XZ` at `0x14002c756`
- `wincorlib!??0OutOfMemoryException@Platform@@QE$AAA@XZ` at `0x14002c756`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c748`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c748`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall _ReplaceAll__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAXP_01E_ABV__Array_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___00_6__Z(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // r14
  __int64 v5; // rdi
  __int64 v6; // r15
  _QWORD *v7; // r12
  _QWORD *i; // rbx
  _QWORD *v9; // rdx
  void *Exception; // rcx
  __int64 v12; // rcx
  void *v13; // [rsp+30h] [rbp-48h]
  __int64 v14; // [rsp+30h] [rbp-48h]
  void *v15; // [rsp+30h] [rbp-48h]
  __int64 v16; // [rsp+30h] [rbp-48h]
  __int64 pExceptionObject; // [rsp+38h] [rbp-40h] BYREF
  __int64 v18; // [rsp+40h] [rbp-38h] BYREF
  __int64 v19; // [rsp+48h] [rbp-30h] BYREF

  try
  {
    Platform::Collections::Details::IncrementCounter(a1 + 80);
    if ( *(_DWORD *)(a2 + 72) > 0x7FFFFFFFu )
    {
      Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
      v12 = Platform::OutOfMemoryException::OutOfMemoryException(Exception);
      pExceptionObject = __abi_winrt_ptr_ctor(v12);
      throw (Platform::OutOfMemoryException **)&pExceptionObject;
    }
    v4 = *(_QWORD *)(a1 + 96);
    v5 = *(_QWORD *)(a2 + 80);
    if ( v5 )
      v6 = v5 + 8LL * *(unsigned int *)(a2 + 72);
    else
      v6 = 0;
    v7 = *(_QWORD **)(v4 + 8);
    for ( i = *(_QWORD **)v4; i != v7; ++i )
    {
      if ( *i )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*i + 16LL))(*i);
    }
  }
  catch ( std::bad_alloc )
  {
    v13 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v14 = Platform::OutOfMemoryException::OutOfMemoryException(v13);
    v18 = __abi_winrt_ptr_ctor(v14);
    throw (Platform::OutOfMemoryException **)&v18;
  }
  catch ( exception )
  {
    v15 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v16 = Platform::FailureException::FailureException(v15);
    v19 = __abi_winrt_ptr_ctor(v16);
    throw (Platform::FailureException **)&v19;
  }
  v9 = *(_QWORD **)v4;
  *(_QWORD *)(v4 + 8) = *(_QWORD *)v4;
  std::vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>::_Insert<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc * *>(
    v4,
    v9,
    v5,
    v6);
  return Platform::Collections::Vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,std::equal_to<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>>::Notify(
           a1,
           0,
           0);
}

```

## disassembly

```asm
0x14002c6a0  mov     [rsp+arg_10], rbx
0x14002c6a5  push    rsi
0x14002c6a6  push    rdi
0x14002c6a7  push    r12
0x14002c6a9  push    r14
0x14002c6ab  push    r15
0x14002c6ad  sub     rsp, 50h
0x14002c6b1  mov     rbx, rdx
0x14002c6b4  mov     rsi, rcx
0x14002c6b7  add     rcx, 50h ; 'P'
0x14002c6bb  call    ?IncrementCounter@Details@Collections@Platform@@YAXAEAV?$shared_ptr@I@std@@@Z; Platform::Collections::Details::IncrementCounter(std::shared_ptr<uint> &)
0x14002c6c0  cmp     dword ptr [rbx+48h], 7FFFFFFFh
0x14002c6c7  ja      short loc_14002C740
0x14002c6c9  mov     r14, [rsi+60h]
0x14002c6cd  mov     rdi, [rbx+50h]
0x14002c6d1  test    rdi, rdi
0x14002c6d4  jnz     short loc_14002C6DB
0x14002c6d6  xor     r15d, r15d
0x14002c6d9  jmp     short loc_14002C6E2
0x14002c6db  mov     eax, [rbx+48h]
0x14002c6de  lea     r15, [rdi+rax*8]
0x14002c6e2  mov     r12, [r14+8]
0x14002c6e6  mov     rbx, [r14]
0x14002c6e9  jmp     short loc_14002C703
0x14002c6eb  mov     rcx, [rbx]
0x14002c6ee  test    rcx, rcx
0x14002c6f1  jz      short loc_14002C6FF
0x14002c6f3  mov     rax, [rcx]
0x14002c6f6  mov     rax, [rax+10h]
0x14002c6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c6ff  add     rbx, 8
0x14002c703  cmp     rbx, r12
0x14002c706  jnz     short loc_14002C6EB
0x14002c708  mov     rdx, [r14]
0x14002c70b  mov     [r14+8], rdx
0x14002c70f  mov     r9, r15
0x14002c712  mov     r8, rdi
0x14002c715  mov     rcx, r14
0x14002c718  call    ??$_Insert@PEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@?$vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@V?$allocator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@QEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@std@@@1@PEAPE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@1Uforward_iterator_tag@1@@Z; std::vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider *>::_Insert<Windows::UI::Xaml::Markup::IXamlMetadataProvider * *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<Windows::UI::Xaml::Markup::IXamlMetadataProvider *>>>,Windows::UI::Xaml::Markup::IXamlMetadataProvider * *,Windows::UI::Xaml::Markup::IXamlMetadataProvider * *,std::forward_iterator_tag)
0x14002c71d  xor     r8d, r8d
0x14002c720  xor     edx, edx
0x14002c722  mov     rcx, rsi
0x14002c725  call    ?Notify@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@AE$AAAXW4CollectionChange@2Foundation@Windows@@I@Z; Platform::Collections::Vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,std::equal_to<Windows::UI::Xaml::Markup::IXamlMetadataProvider *>>::Notify(Windows::Foundation::Collections::CollectionChange,uint)
0x14002c72a  nop
0x14002c72b  mov     rbx, [rsp+78h+arg_10]
0x14002c733  add     rsp, 50h
0x14002c737  pop     r15
0x14002c739  pop     r14
0x14002c73b  pop     r12
0x14002c73d  pop     rdi
0x14002c73e  pop     rsi
0x14002c73f  retn
0x14002c740  mov     edx, 90h
0x14002c745  lea     ecx, [rdx-28h]
0x14002c748  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002c74e  mov     [rsp+78h+var_48], rax
0x14002c753  mov     rcx, rax
0x14002c756  call    cs:__imp_??0OutOfMemoryException@Platform@@QE$AAA@XZ; Platform::OutOfMemoryException::OutOfMemoryException(void)
0x14002c75c  mov     [rsp+78h+var_48], rax
0x14002c761  mov     rcx, rax
0x14002c764  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002c769  mov     [rsp+78h+pExceptionObject], rax
0x14002c76e  lea     rdx, _TI11PE$AAVOutOfMemoryException@Platform@@; pThrowInfo
0x14002c775  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x14002c77a  call    _CxxThrowException_0
```
