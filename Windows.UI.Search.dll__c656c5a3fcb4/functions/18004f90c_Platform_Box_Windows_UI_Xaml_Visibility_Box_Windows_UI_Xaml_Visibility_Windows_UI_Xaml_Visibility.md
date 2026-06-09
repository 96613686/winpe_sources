# Platform::Box<Windows::UI::Xaml::Visibility>::Box<Windows::UI::Xaml::Visibility>(Windows::UI::Xaml::Visibility)

- ea: `0x18004f90c`
- end: `0x18004f9e1`
- name: `??0?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@QE$AAA@W4Visibility@Xaml@UI@Windows@@@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004d9b0`

## callees

- `0x18000b818`
- `0x18000b888`
- `0x18000b8dc`
- `0x18000b908`
- `0x18004f90c`
- `0x18004fbf4`
- `0x1800547cc`

## import_xrefs

- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004f928`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004f928`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004f95a`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004f95a`

## pseudocode

```c
__int64 __fastcall Platform::Box<enum Windows::UI::Xaml::Visibility>::Box<enum Windows::UI::Xaml::Visibility>(
        __int64 a1,
        unsigned int a2)
{
  unsigned int TypeCode; // eax
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v10; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v11; // [rsp+48h] [rbp+10h] BYREF
  void *v12; // [rsp+50h] [rbp+18h]

  v11 = a2;
  v10 = a1;
  TypeCode = Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode();
  v3 = Platform::Details::CreateValue(TypeCode, &v11);
  v10 = v3;
  v4 = __abi_winrt_ptr_ctor(v3);
  v10 = v4;
  __abi_winrt_ptr_dtor(v3);
  if ( v4 )
  {
    LOBYTE(v5) = 1;
    v8 = __abi_winrt_cast_to(v5, v4, _uuidof__AV__Box_W4Visibility_Xaml_UI_Windows___Platform__);
    v12 = (void *)v8;
    v7 = __abi_winrt_ptr_ctor(v8);
    __abi_winrt_ptr_dtor(v8);
  }
  else
  {
    v12 = Platform::Details::Heap::Allocate(0x38u, 0x48u);
    v6 = Platform::Details::CustomBox<enum Windows::UI::Xaml::Visibility>::CustomBox<enum Windows::UI::Xaml::Visibility>(
           v12,
           v11);
    v12 = (void *)v6;
    __abi_winrt_ptr_assign(&v10, v6);
    __abi_winrt_ptr_dtor(v6);
    v4 = v10;
    v7 = __abi_winrt_ptr_ctor(v10);
  }
  __abi_winrt_ptr_dtor(v4);
  return v7;
}

```

## disassembly

```asm
0x18004f90c  mov     [rsp+arg_8], edx
0x18004f910  mov     [rsp+arg_0], rcx
0x18004f915  push    rbx
0x18004f916  push    rsi
0x18004f917  push    rdi
0x18004f918  sub     rsp, 20h
0x18004f91c  call    ?InternalGetTypeCode@?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@CA?AW4TypeCode@2@XZ; Platform::Box<Windows::UI::Xaml::Visibility>::InternalGetTypeCode(void)
0x18004f921  mov     ecx, eax
0x18004f923  lea     rdx, [rsp+38h+arg_8]
0x18004f928  call    cs:__imp_?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z; Platform::Details::CreateValue(Platform::TypeCode,void const *)
0x18004f92e  mov     rbx, rax
0x18004f931  mov     [rsp+38h+arg_0], rax
0x18004f936  mov     rcx, rax
0x18004f939  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f93e  mov     rsi, rax
0x18004f941  mov     [rsp+38h+arg_0], rax
0x18004f946  mov     rcx, rbx
0x18004f949  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f94e  nop
0x18004f94f  test    rsi, rsi
0x18004f952  jnz     short loc_18004F9A1
0x18004f954  lea     edx, [rsi+48h]
0x18004f957  lea     ecx, [rsi+38h]
0x18004f95a  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x18004f960  mov     [rsp+38h+arg_10], rax
0x18004f965  mov     edx, [rsp+38h+arg_8]
0x18004f969  mov     rcx, rax
0x18004f96c  call    ??0?$CustomBox@W4Visibility@Xaml@UI@Windows@@@Details@Platform@@QE$AAA@W4Visibility@Xaml@UI@Windows@@@Z; Platform::Details::CustomBox<Windows::UI::Xaml::Visibility>::CustomBox<Windows::UI::Xaml::Visibility>(Windows::UI::Xaml::Visibility)
0x18004f971  mov     rbx, rax
0x18004f974  mov     [rsp+38h+arg_10], rax
0x18004f979  mov     rdx, rax
0x18004f97c  lea     rcx, [rsp+38h+arg_0]
0x18004f981  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18004f986  nop
0x18004f987  mov     rcx, rbx
0x18004f98a  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f98f  mov     rsi, [rsp+38h+arg_0]
0x18004f994  mov     rcx, rsi
0x18004f997  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f99c  mov     rbx, rax
0x18004f99f  jmp     short loc_18004F9CE
0x18004f9a1  lea     r8, __uuidof_?AV?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@
0x18004f9a8  mov     rdx, rsi
0x18004f9ab  mov     cl, 1
0x18004f9ad  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18004f9b2  mov     rdi, rax
0x18004f9b5  mov     [rsp+38h+arg_10], rax
0x18004f9ba  mov     rcx, rax
0x18004f9bd  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f9c2  mov     rbx, rax
0x18004f9c5  mov     rcx, rdi
0x18004f9c8  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f9cd  nop
0x18004f9ce  mov     rcx, rsi
0x18004f9d1  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f9d6  mov     rax, rbx
0x18004f9d9  add     rsp, 20h
0x18004f9dd  pop     rdi
0x18004f9de  pop     rsi
0x18004f9df  pop     rbx
0x18004f9e0  retn
```
