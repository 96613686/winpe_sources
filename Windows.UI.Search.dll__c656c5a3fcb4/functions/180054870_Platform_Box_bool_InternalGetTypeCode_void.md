# Platform::Box<bool>::InternalGetTypeCode(void)

- ea: `0x180054870`
- end: `0x18005490b`
- name: `?InternalGetTypeCode@?$Box@_N@Platform@@CA?AW4TypeCode@2@XZ`
- size: `155`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18004f9e8`

## callees

- `0x18000334e`
- `0x18000b908`
- `0x180051348`
- `0x180054870`

## import_xrefs

- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x1800548c7`
- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x1800548c7`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800548b6`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x1800548b6`

## pseudocode

```c
__int64 Platform::Box<bool>::InternalGetTypeCode()
{
  RTL_SRWLOCK *v0; // rdi
  RTL_SRWLOCK *v1; // rax
  __int128 v3; // [rsp+20h] [rbp-18h] BYREF
  __int64 type_id; // [rsp+40h] [rbp+8h]

  v3 = 0;
  if ( byte_1800AAAB0
    || (v0 = &`Platform::Box<bool>::InternalGetTypeCode'::`2'::once,
        _Platform_AcquireSRWLockExclusive(&`Platform::Box<bool>::InternalGetTypeCode'::`2'::once),
        *(_QWORD *)&v3 = &`Platform::Box<bool>::InternalGetTypeCode'::`2'::once,
        byte_1800AAAB0) )
  {
    v1 = 0;
    v0 = (RTL_SRWLOCK *)*((_QWORD *)&v3 + 1);
  }
  else
  {
    *((_QWORD *)&v3 + 1) = &`Platform::Box<bool>::InternalGetTypeCode'::`2'::once;
    type_id = __abi_make_type_id(&_abi_typedesc_Boolean);
    `Platform::Box<bool>::InternalGetTypeCode'::`2'::result = Platform::Type::GetTypeCode(type_id);
    __abi_winrt_ptr_dtor(type_id);
    v1 = &`Platform::Box<bool>::InternalGetTypeCode'::`2'::once;
  }
  if ( v1 )
    LOBYTE(v0[1].Ptr) = 1;
  __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t((__vccorlib_srwlock_holder_t *)&v3);
  return (unsigned int)`Platform::Box<bool>::InternalGetTypeCode'::`2'::result;
}

```

## disassembly

```asm
0x180054870  mov     [rsp+arg_8], rbx
0x180054875  push    rdi
0x180054876  sub     rsp, 30h
0x18005487a  xorps   xmm0, xmm0
0x18005487d  movdqu  [rsp+38h+var_18], xmm0
0x180054883  mov     al, cs:byte_1800AAAB0
0x180054889  test    al, al
0x18005488b  jnz     short loc_1800548E0
0x18005488d  lea     rdi, ?once@?1??InternalGetTypeCode@?$Box@_N@Platform@@CA?AW4TypeCode@3@XZ@4U__vccorlib_once_t@@A; __vccorlib_once_t `Platform::Box<bool>::InternalGetTypeCode(void)'::`2'::once
0x180054894  mov     rcx, rdi; SRWLock
0x180054897  call    __Platform_AcquireSRWLockExclusive
0x18005489c  mov     qword ptr [rsp+38h+var_18], rdi
0x1800548a1  cmp     cs:byte_1800AAAB0, 0
0x1800548a8  jnz     short loc_1800548E0
0x1800548aa  mov     qword ptr [rsp+38h+var_18+8], rdi
0x1800548af  lea     rcx, __abi_typedesc_Boolean
0x1800548b6  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x1800548bc  mov     rbx, rax
0x1800548bf  mov     [rsp+38h+arg_0], rax
0x1800548c4  mov     rcx, rax
0x1800548c7  call    cs:__imp_?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z; Platform::Type::GetTypeCode(Platform::Type *)
0x1800548cd  mov     cs:?result@?1??InternalGetTypeCode@?$Box@_N@Platform@@CA?AW4TypeCode@3@XZ@4W443@A, eax; Platform::TypeCode `Platform::Box<bool>::InternalGetTypeCode(void)'::`2'::result
0x1800548d3  mov     rcx, rbx
0x1800548d6  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x1800548db  mov     rax, rdi
0x1800548de  jmp     short loc_1800548E7
0x1800548e0  xor     eax, eax
0x1800548e2  mov     rdi, qword ptr [rsp+38h+var_18+8]
0x1800548e7  test    rax, rax
0x1800548ea  jz      short loc_1800548F0
0x1800548ec  mov     byte ptr [rdi+8], 1
0x1800548f0  lea     rcx, [rsp+38h+var_18]; this
0x1800548f5  call    ??1__vccorlib_srwlock_holder_t@@QEAA@XZ; __vccorlib_srwlock_holder_t::~__vccorlib_srwlock_holder_t(void)
0x1800548fa  mov     eax, cs:?result@?1??InternalGetTypeCode@?$Box@_N@Platform@@CA?AW4TypeCode@3@XZ@4W443@A; Platform::TypeCode `Platform::Box<bool>::InternalGetTypeCode(void)'::`2'::result
0x180054900  mov     rbx, [rsp+38h+arg_8]
0x180054905  add     rsp, 30h
0x180054909  pop     rdi
0x18005490a  retn
```
