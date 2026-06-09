# Platform::Box<int>::InternalGetTypeCode(void)

- ea: `0x180054684`
- end: `0x18005471f`
- name: `?InternalGetTypeCode@?$Box@H@Platform@@CA?AW4TypeCode@2@XZ`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004f754`

## callees

- `0x18000334e`
- `0x18000b908`
- `0x180051348`
- `0x180054684`

## import_xrefs

- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x1800546db`
- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x1800546db`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800546ca`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800546ca`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 Platform::Box<int>::InternalGetTypeCode()
{
  RTL_SRWLOCK *v0; // rdi
  RTL_SRWLOCK *v1; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  __int64 type_id; // [rsp+40h] [rbp+8h]

  v3 = 0;
  if ( byte_1800AAAC8
    || (v0 = &`Platform::Box<int>::InternalGetTypeCode'::`2'::once,
        _Platform_AcquireSRWLockExclusive(&`Platform::Box<int>::InternalGetTypeCode'::`2'::once),
        *(_QWORD *)&v3 = &`Platform::Box<int>::InternalGetTypeCode'::`2'::once,
        byte_1800AAAC8) )
  {
    v1 = 0;
    v0 = (RTL_SRWLOCK *)*((_QWORD *)&v3 + 1);
  }
  else
  {
    *((_QWORD *)&v3 + 1) = &`Platform::Box<int>::InternalGetTypeCode'::`2'::once;
    type_id = __abi_make_type_id(&_abi_typedesc_Int32);
    `Platform::Box<int>::InternalGetTypeCode'::`2'::result = Platform::Type::GetTypeCode(type_id);
    __abi_winrt_ptr_dtor(type_id);
    v1 = &`Platform::Box<int>::InternalGetTypeCode'::`2'::once;
  }
  if ( v1 )
    LOBYTE(v0[1].Ptr) = 1;
  __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t((__vccorlib_srwlock_holder_t *)&v3);
  return (unsigned int)`Platform::Box<int>::InternalGetTypeCode'::`2'::result;
}

```

## disassembly

```asm
0x180054684  mov     [rsp+arg_8], rbx
0x180054689  push    rdi
0x18005468a  sub     rsp, 30h
0x18005468e  xorps   xmm0, xmm0
0x180054691  movdqu  [rsp+38h+var_18], xmm0
0x180054697  mov     al, cs:byte_1800AAAC8
0x18005469d  test    al, al
0x18005469f  jnz     short loc_1800546F4
0x1800546a1  lea     rdi, ?once@?1??InternalGetTypeCode@?$Box@H@Platform@@CA?AW4TypeCode@3@XZ@4U__vccorlib_once_t@@A; __vccorlib_once_t `Platform::Box<int>::InternalGetTypeCode(void)'::`2'::once
0x1800546a8  mov     rcx, rdi; SRWLock
0x1800546ab  call    __Platform_AcquireSRWLockExclusive
0x1800546b0  mov     qword ptr [rsp+38h+var_18], rdi
0x1800546b5  cmp     cs:byte_1800AAAC8, 0
0x1800546bc  jnz     short loc_1800546F4
0x1800546be  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800546c3  lea     rcx, __abi_typedesc_Int32
0x1800546ca  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x1800546d0  mov     rbx, rax
0x1800546d3  mov     [rsp+38h+arg_0], rax
0x1800546d8  mov     rcx, rax
0x1800546db  call    cs:__imp_?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z; Platform::Type::GetTypeCode(Platform::Type *)
0x1800546e1  mov     cs:?result@?1??InternalGetTypeCode@?$Box@H@Platform@@CA?AW4TypeCode@3@XZ@4W443@A, eax; Platform::TypeCode `Platform::Box<int>::InternalGetTypeCode(void)'::`2'::result
0x1800546e7  mov     rcx, rbx
0x1800546ea  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800546ef  mov     rax, rdi
0x1800546f2  jmp     short loc_1800546FB
0x1800546f4  xor     eax, eax
0x1800546f6  mov     rdi, qword ptr [rsp+38h+var_18+8]
0x1800546fb  test    rax, rax
0x1800546fe  jz      short loc_180054704
0x180054700  mov     byte ptr [rdi+8], 1
0x180054704  lea     rcx, [rsp+38h+var_18]; this
0x180054709  call    ??1__vccorlib_srwlock_holder_t@@QEAA@XZ; __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t(void)
0x18005470e  mov     eax, cs:?result@?1??InternalGetTypeCode@?$Box@H@Platform@@CA?AW4TypeCode@3@XZ@4W443@A; Platform::TypeCode `Platform::Box<int>::InternalGetTypeCode(void)'::`2'::result
0x180054714  mov     rbx, [rsp+38h+arg_8]
0x180054719  add     rsp, 30h
0x18005471d  pop     rdi
0x18005471e  retn
```
