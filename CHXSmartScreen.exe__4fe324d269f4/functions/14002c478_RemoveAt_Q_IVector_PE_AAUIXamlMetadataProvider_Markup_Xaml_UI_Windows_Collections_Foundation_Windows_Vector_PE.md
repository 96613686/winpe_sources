# ?RemoveAt@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXI@Z

- ea: `0x14002c478`
- end: `0x14002c59e`
- name: `?RemoveAt@?Q?$IVector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@2Platform@@UE$AAAXI@Z`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: ``

## callers

- `0x14002c5b0`
- `0x14002c5c0`
- `0x140030860`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14002b96c`
- `0x14002c280`
- `0x14002c478`
- `0x140035010`

## import_xrefs

- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002c573`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002c573`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c565`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c565`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall _RemoveAt__Q__IVector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____Vector_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows__U__equal_to_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___std___2Platform__UE_AAAXI_Z(
        __int64 a1,
        unsigned int a2)
{
  unsigned __int64 v2; // r13
  _QWORD *v4; // rdi
  _QWORD *v5; // r12
  _QWORD *v6; // rbx
  _QWORD *i; // r14
  __int64 v8; // rsi
  _QWORD *v9; // rsi
  _QWORD *j; // rbx
  __int64 result; // rax
  void *Exception; // rcx
  __int64 v13; // rcx
  void *v14; // [rsp+20h] [rbp-48h]
  __int64 v15; // [rsp+20h] [rbp-48h]
  void *v16; // [rsp+20h] [rbp-48h]
  __int64 v17; // [rsp+20h] [rbp-48h]
  __int64 pExceptionObject; // [rsp+28h] [rbp-40h] BYREF
  __int64 v19; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-30h] BYREF

  try
  {
    v2 = a2;
    Platform::Collections::Details::IncrementCounter(a1 + 80);
    v4 = *(_QWORD **)(a1 + 96);
    v5 = (_QWORD *)v4[1];
    if ( v2 >= ((__int64)v5 - *v4) >> 3 )
    {
      Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
      v13 = Platform::OutOfBoundsException::OutOfBoundsException(Exception);
      pExceptionObject = __abi_winrt_ptr_ctor(v13);
      throw (Platform::OutOfBoundsException **)&pExceptionObject;
    }
    v6 = (_QWORD *)(*v4 + 8 * v2);
    for ( i = v6 + 1; i != v5; ++i )
    {
      v8 = *i;
      if ( *i != *v6 )
      {
        if ( v8 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v8 + 8LL))(*i);
        if ( *v6 )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v6 + 16LL))(*v6);
        *v6 = v8;
      }
      ++v6;
    }
    v9 = (_QWORD *)v4[1];
    for ( j = v9 - 1; j != v9; ++j )
    {
      if ( *j )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*j + 16LL))(*j);
    }
    v4[1] -= 8LL;
    result = Platform::Collections::Vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *,std::equal_to<Windows::UI::Xaml::Markup::IXamlMetadataProvider __gc *>>::Notify(
               a1,
               2,
               (unsigned int)v2);
  }
  catch ( std::bad_alloc )
  {
    v14 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v15 = Platform::OutOfMemoryException::OutOfMemoryException(v14);
    v19 = __abi_winrt_ptr_ctor(v15);
    throw (Platform::OutOfMemoryException **)&v19;
  }
  catch ( exception )
  {
    v16 = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    v17 = Platform::FailureException::FailureException(v16);
    v20 = __abi_winrt_ptr_ctor(v17);
    throw (Platform::FailureException **)&v20;
  }
  return result;
}

```

## disassembly

```asm
0x14002c478  mov     [rsp+arg_10], rbx
0x14002c47d  mov     [rsp+arg_18], rsi
0x14002c482  push    rdi
0x14002c483  push    r12
0x14002c485  push    r13
0x14002c487  push    r14
0x14002c489  push    r15
0x14002c48b  sub     rsp, 40h
0x14002c48f  mov     r13d, edx
0x14002c492  mov     r15, rcx
0x14002c495  add     rcx, 50h ; 'P'
0x14002c499  call    ?IncrementCounter@Details@Collections@Platform@@YAXAEAV?$shared_ptr@I@std@@@Z; Platform::Collections::Details::IncrementCounter(std::shared_ptr<uint> &)
0x14002c49e  mov     rdi, [r15+60h]
0x14002c4a2  mov     rcx, [rdi]
0x14002c4a5  mov     r12, [rdi+8]
0x14002c4a9  mov     rax, r12
0x14002c4ac  sub     rax, rcx
0x14002c4af  sar     rax, 3
0x14002c4b3  cmp     r13, rax
0x14002c4b6  jnb     loc_14002C55D
0x14002c4bc  lea     rbx, [rcx+r13*8]
0x14002c4c0  lea     r14, [rbx+8]
0x14002c4c4  cmp     r14, r12
0x14002c4c7  jz      short loc_14002C506
0x14002c4c9  mov     rsi, [r14]
0x14002c4cc  cmp     rsi, [rbx]
0x14002c4cf  jz      short loc_14002C4FC
0x14002c4d1  test    rsi, rsi
0x14002c4d4  jz      short loc_14002C4E5
0x14002c4d6  mov     rax, [rsi]
0x14002c4d9  mov     rcx, rsi
0x14002c4dc  mov     rax, [rax+8]
0x14002c4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c4e5  mov     rcx, [rbx]
0x14002c4e8  test    rcx, rcx
0x14002c4eb  jz      short loc_14002C4F9
0x14002c4ed  mov     rax, [rcx]
0x14002c4f0  mov     rax, [rax+10h]
0x14002c4f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c4f9  mov     [rbx], rsi
0x14002c4fc  add     rbx, 8
0x14002c500  add     r14, 8
0x14002c504  jmp     short loc_14002C4C4
0x14002c506  mov     rsi, [rdi+8]
0x14002c50a  lea     rbx, [rsi-8]
0x14002c50e  cmp     rbx, rsi
0x14002c511  jz      short loc_14002C52D
0x14002c513  mov     rcx, [rbx]
0x14002c516  test    rcx, rcx
0x14002c519  jz      short loc_14002C527
0x14002c51b  mov     rax, [rcx]
0x14002c51e  mov     rax, [rax+10h]
0x14002c522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002c527  add     rbx, 8
0x14002c52b  jmp     short loc_14002C50E
0x14002c52d  add     qword ptr [rdi+8], 0FFFFFFFFFFFFFFF8h
0x14002c532  mov     r8d, r13d
0x14002c535  mov     edx, 2
0x14002c53a  mov     rcx, r15
0x14002c53d  call    ?Notify@?$Vector@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@U?$equal_to@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@std@@@Collections@Platform@@AE$AAAXW4CollectionChange@2Foundation@Windows@@I@Z; Platform::Collections::Vector<Windows::UI::Xaml::Markup::IXamlMetadataProvider *,std::equal_to<Windows::UI::Xaml::Markup::IXamlMetadataProvider *>>::Notify(Windows::Foundation::Collections::CollectionChange,uint)
0x14002c542  nop
0x14002c543  lea     r11, [rsp+68h+var_28]
0x14002c548  mov     rbx, [r11+40h]
0x14002c54c  mov     rsi, [r11+48h]
0x14002c550  mov     rsp, r11
0x14002c553  pop     r15
0x14002c555  pop     r14
0x14002c557  pop     r13
0x14002c559  pop     r12
0x14002c55b  pop     rdi
0x14002c55c  retn
0x14002c55d  mov     edx, 90h
0x14002c562  lea     ecx, [rdx-28h]
0x14002c565  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002c56b  mov     [rsp+68h+var_48], rax
0x14002c570  mov     rcx, rax
0x14002c573  call    cs:__imp_??0OutOfBoundsException@Platform@@QE$AAA@XZ; Platform::OutOfBoundsException::OutOfBoundsException(void)
0x14002c579  mov     [rsp+68h+var_48], rax
0x14002c57e  mov     rcx, rax
0x14002c581  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002c586  mov     [rsp+68h+pExceptionObject], rax
0x14002c58b  lea     rdx, _TI11PE$AAVOutOfBoundsException@Platform@@; pThrowInfo
0x14002c592  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x14002c597  call    _CxxThrowException_0
```
