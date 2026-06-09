# Platform::Box<uint>::InternalGetTypeCode(void)

- ea: `0x180054728`
- end: `0x1800547c3`
- name: `?InternalGetTypeCode@?$Box@I@Platform@@CA?AW4TypeCode@2@XZ`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004f830`

## callees

- `0x18000334e`
- `0x18000b908`
- `0x180051348`
- `0x180054728`

## import_xrefs

- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x18005477f`
- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x18005477f`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x18005476e`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x18005476e`

## pseudocode

```c
__int64 Platform::Box<unsigned int>::InternalGetTypeCode()
{
  RTL_SRWLOCK *v0; // rdi
  RTL_SRWLOCK *v1; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  __int64 type_id; // [rsp+40h] [rbp+8h]

  v3 = 0;
  if ( byte_1800AAA80
    || (v0 = &`Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::once,
        _Platform_AcquireSRWLockExclusive(&`Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::once),
        *(_QWORD *)&v3 = &`Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::once,
        byte_1800AAA80) )
  {
    v1 = 0;
    v0 = (RTL_SRWLOCK *)*((_QWORD *)&v3 + 1);
  }
  else
  {
    *((_QWORD *)&v3 + 1) = &`Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::once;
    type_id = __abi_make_type_id(&_abi_typedesc_UInt32);
    `Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::result = Platform::Type::GetTypeCode(type_id);
    __abi_winrt_ptr_dtor(type_id);
    v1 = &`Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::once;
  }
  if ( v1 )
    LOBYTE(v0[1].Ptr) = 1;
  __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t((__vccorlib_srwlock_holder_t *)&v3);
  return (unsigned int)`Platform::Box<unsigned int>::InternalGetTypeCode'::`2'::result;
}

```

## disassembly

```asm
0x180054728  mov     [rsp+arg_8], rbx
0x18005472d  push    rdi
0x18005472e  sub     rsp, 30h
0x180054732  xorps   xmm0, xmm0
0x180054735  movdqu  [rsp+38h+var_18], xmm0
0x18005473b  mov     al, cs:byte_1800AAA80
0x180054741  test    al, al
0x180054743  jnz     short loc_180054798
0x180054745  lea     rdi, ?once@?1??InternalGetTypeCode@?$Box@I@Platform@@CA?AW4TypeCode@3@XZ@4U__vccorlib_once_t@@A; __vccorlib_once_t `Platform::Box<uint>::InternalGetTypeCode(void)'::`2'::once
0x18005474c  mov     rcx, rdi; SRWLock
0x18005474f  call    __Platform_AcquireSRWLockExclusive
0x180054754  mov     qword ptr [rsp+38h+var_18], rdi
0x180054759  cmp     cs:byte_1800AAA80, 0
0x180054760  jnz     short loc_180054798
0x180054762  mov     qword ptr [rsp+38h+var_18+8], rdi
0x180054767  lea     rcx, __abi_typedesc_UInt32
0x18005476e  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x180054774  mov     rbx, rax
0x180054777  mov     [rsp+38h+arg_0], rax
0x18005477c  mov     rcx, rax
0x18005477f  call    cs:__imp_?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z; Platform::Type::GetTypeCode(Platform::Type *)
0x180054785  mov     cs:?result@?1??InternalGetTypeCode@?$Box@I@Platform@@CA?AW4TypeCode@3@XZ@4W443@A, eax; Platform::TypeCode `Platform::Box<uint>::InternalGetTypeCode(void)'::`2'::result
0x18005478b  mov     rcx, rbx
0x18005478e  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x180054793  mov     rax, rdi
0x180054796  jmp     short loc_18005479F
0x180054798  xor     eax, eax
0x18005479a  mov     rdi, qword ptr [rsp+38h+var_18+8]
0x18005479f  test    rax, rax
0x1800547a2  jz      short loc_1800547A8
0x1800547a4  mov     byte ptr [rdi+8], 1
0x1800547a8  lea     rcx, [rsp+38h+var_18]; this
0x1800547ad  call    ??1__vccorlib_srwlock_holder_t@@QEAA@XZ; __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t(void)
0x1800547b2  mov     eax, cs:?result@?1??InternalGetTypeCode@?$Box@I@Platform@@CA?AW4TypeCode@3@XZ@4W443@A; Platform::TypeCode `Platform::Box<uint>::InternalGetTypeCode(void)'::`2'::result
0x1800547b8  mov     rbx, [rsp+38h+arg_8]
0x1800547bd  add     rsp, 30h
0x1800547c1  pop     rdi
0x1800547c2  retn
```
