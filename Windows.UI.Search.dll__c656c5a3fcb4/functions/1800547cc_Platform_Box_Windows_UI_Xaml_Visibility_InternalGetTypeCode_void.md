# Platform::Box<Windows::UI::Xaml::Visibility>::InternalGetTypeCode(void)

- ea: `0x1800547cc`
- end: `0x180054867`
- name: `?InternalGetTypeCode@?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@CA?AW4TypeCode@2@XZ`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004f90c`

## callees

- `0x18000334e`
- `0x18000b908`
- `0x180051348`
- `0x1800547cc`

## import_xrefs

- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x180054823`
- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x180054823`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180054812`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x180054812`

## pseudocode

```c
__int64 Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode()
{
  RTL_SRWLOCK *v0; // rdi
  RTL_SRWLOCK *v1; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  __int64 type_id; // [rsp+40h] [rbp+8h]

  v3 = 0;
  if ( byte_1800AAA98
    || (v0 = &`Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::once,
        _Platform_AcquireSRWLockExclusive(&`Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::once),
        *(_QWORD *)&v3 = &`Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::once,
        byte_1800AAA98) )
  {
    v1 = 0;
    v0 = (RTL_SRWLOCK *)*((_QWORD *)&v3 + 1);
  }
  else
  {
    *((_QWORD *)&v3 + 1) = &`Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::once;
    type_id = __abi_make_type_id(&_abi_typedesc_Windows_UI_Xaml_Visibility);
    `Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::result = Platform::Type::GetTypeCode(type_id);
    __abi_winrt_ptr_dtor(type_id);
    v1 = &`Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::once;
  }
  if ( v1 )
    LOBYTE(v0[1].Ptr) = 1;
  __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t((__vccorlib_srwlock_holder_t *)&v3);
  return (unsigned int)`Platform::Box<enum Windows::UI::Xaml::Visibility>::InternalGetTypeCode'::`2'::result;
}

```

## disassembly

```asm
0x1800547cc  mov     [rsp+arg_8], rbx
0x1800547d1  push    rdi
0x1800547d2  sub     rsp, 30h
0x1800547d6  xorps   xmm0, xmm0
0x1800547d9  movdqu  [rsp+38h+var_18], xmm0
0x1800547df  mov     al, cs:byte_1800AAA98
0x1800547e5  test    al, al
0x1800547e7  jnz     short loc_18005483C
0x1800547e9  lea     rdi, ?once@?1??InternalGetTypeCode@?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4U__vccorlib_once_t@@A; __vccorlib_once_t `Platform::Box<Windows::UI::Xaml::Visibility>::InternalGetTypeCode(void)'::`2'::once
0x1800547f0  mov     rcx, rdi; SRWLock
0x1800547f3  call    __Platform_AcquireSRWLockExclusive
0x1800547f8  mov     qword ptr [rsp+38h+var_18], rdi
0x1800547fd  cmp     cs:byte_1800AAA98, 0
0x180054804  jnz     short loc_18005483C
0x180054806  mov     qword ptr [rsp+38h+var_18+8], rdi
0x18005480b  lea     rcx, __abi_typedesc_Windows_UI_Xaml_Visibility
0x180054812  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180054818  mov     rbx, rax
0x18005481b  mov     [rsp+38h+arg_0], rax
0x180054820  mov     rcx, rax
0x180054823  call    cs:__imp_?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z; Platform::Type::GetTypeCode(Platform::Type *)
0x180054829  mov     cs:?result@?1??InternalGetTypeCode@?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4W443@A, eax; Platform::TypeCode `Platform::Box<Windows::UI::Xaml::Visibility>::InternalGetTypeCode(void)'::`2'::result
0x18005482f  mov     rcx, rbx
0x180054832  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180054837  mov     rax, rdi
0x18005483a  jmp     short loc_180054843
0x18005483c  xor     eax, eax
0x18005483e  mov     rdi, qword ptr [rsp+38h+var_18+8]
0x180054843  test    rax, rax
0x180054846  jz      short loc_18005484C
0x180054848  mov     byte ptr [rdi+8], 1
0x18005484c  lea     rcx, [rsp+38h+var_18]; this
0x180054851  call    ??1__vccorlib_srwlock_holder_t@@QEAA@XZ; __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t(void)
0x180054856  mov     eax, cs:?result@?1??InternalGetTypeCode@?$Box@W4Visibility@Xaml@UI@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4W443@A; Platform::TypeCode `Platform::Box<Windows::UI::Xaml::Visibility>::InternalGetTypeCode(void)'::`2'::result
0x18005485c  mov     rbx, [rsp+38h+arg_8]
0x180054861  add     rsp, 30h
0x180054865  pop     rdi
0x180054866  retn
```
