# Platform::Box<Windows::Web::WebErrorStatus>::Box<Windows::Web::WebErrorStatus>(Windows::Web::WebErrorStatus)

- ea: `0x140013da8`
- end: `0x140013fa0`
- name: `??0?$Box@W4WebErrorStatus@Web@Windows@@@Platform@@QE$AAA@W4WebErrorStatus@Web@Windows@@@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400232c0`

## callees

- `0x1400013f0`
- `0x1400013fc`
- `0x140013da8`
- `0x140014058`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x140013e11`
- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x140013e11`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x140013e60`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x140013e60`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x140013e01`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x140013e01`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140013ea5`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140013ea5`

## pseudocode

```c
__int64 __fastcall Platform::Box<enum Windows::Web::WebErrorStatus>::Box<enum Windows::Web::WebErrorStatus>(
        __int64 a1,
        unsigned int a2)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rsi
  __int64 type_id; // rdi
  RTL_SRWLOCK *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rbx
  void *v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  int v12; // eax
  __int64 v13; // rdi
  __int64 v14; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+40h] [rbp-18h] BYREF

  v15 = a2;
  if ( byte_14004D0D8 )
  {
    v2 = 0;
    goto LABEL_7;
  }
  v2 = &`Platform::Box<enum Windows::Web::WebErrorStatus>::InternalGetTypeCode'::`2'::once;
  _Platform_AcquireSRWLockExclusive(&`Platform::Box<enum Windows::Web::WebErrorStatus>::InternalGetTypeCode'::`2'::once);
  if ( byte_14004D0D8 )
  {
LABEL_7:
    v5 = 0;
    v3 = 0;
    goto LABEL_8;
  }
  v3 = &`Platform::Box<enum Windows::Web::WebErrorStatus>::InternalGetTypeCode'::`2'::once;
  type_id = __abi_make_type_id(&_abi_typedesc_Windows_Web_WebErrorStatus);
  `Platform::Box<enum Windows::Web::WebErrorStatus>::InternalGetTypeCode'::`2'::result = Platform::Type::GetTypeCode(type_id);
  if ( type_id )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)type_id + 16LL))(type_id);
  v5 = &`Platform::Box<enum Windows::Web::WebErrorStatus>::InternalGetTypeCode'::`2'::once;
LABEL_8:
  if ( v5 )
    LOBYTE(v3[1].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive_0(v2);
  v6 = Platform::Details::CreateValue(
         (unsigned int)`Platform::Box<enum Windows::Web::WebErrorStatus>::InternalGetTypeCode'::`2'::result,
         &v15);
  v7 = v6;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 8LL))(v6);
  if ( v7 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    v14 = 0;
    v12 = (**(__int64 (__fastcall ***)(__int64, __int64 *, __int64 *))v7)(
            v7,
            _uuidof__AV__Box_W4WebErrorStatus_Web_Windows___Platform__,
            &v14);
    v13 = v14;
    if ( v12 )
      v13 = 0;
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    return v13;
  }
  else
  {
    v8 = Platform::Details::Heap::Allocate(0x38u, 0x48u);
    v9 = Platform::Details::CustomBox<enum Windows::Web::WebErrorStatus>::CustomBox<enum Windows::Web::WebErrorStatus>(
           v8,
           v15);
    v10 = v9;
    v14 = v9;
    if ( v9 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
      v7 = v10;
    }
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    if ( v7 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 8LL))(v7);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v7;
  }
}

```

## disassembly

```asm
0x140013da8  push    rbp
0x140013daa  push    rbx
0x140013dab  push    rsi
0x140013dac  push    rdi
0x140013dad  mov     rbp, rsp
0x140013db0  sub     rsp, 58h
0x140013db4  mov     rax, cs:__security_cookie
0x140013dbb  xor     rax, rsp
0x140013dbe  mov     [rbp+var_10], rax
0x140013dc2  mov     [rbp+var_18], edx
0x140013dc5  xorps   xmm0, xmm0
0x140013dc8  movdqu  [rbp+var_30], xmm0
0x140013dcd  mov     al, cs:byte_14004D0D8
0x140013dd3  test    al, al
0x140013dd5  jnz     short loc_140013E36
0x140013dd7  lea     rbx, ?once@?1??InternalGetTypeCode@?$Box@W4WebErrorStatus@Web@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4U__vccorlib_once_t@@A; __vccorlib_once_t `Platform::Box<Windows::Web::WebErrorStatus>::InternalGetTypeCode(void)'::`2'::once
0x140013dde  mov     rcx, rbx; SRWLock
0x140013de1  call    __Platform_AcquireSRWLockExclusive
0x140013de6  mov     qword ptr [rbp+var_30], rbx
0x140013dea  cmp     cs:byte_14004D0D8, 0
0x140013df1  jnz     short loc_140013E3A
0x140013df3  mov     rsi, rbx
0x140013df6  mov     qword ptr [rbp+var_30+8], rbx
0x140013dfa  lea     rcx, __abi_typedesc_Windows_Web_WebErrorStatus
0x140013e01  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x140013e07  mov     rdi, rax
0x140013e0a  mov     [rbp+var_38], rax
0x140013e0e  mov     rcx, rax
0x140013e11  call    cs:__imp_?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z; Platform::Type::GetTypeCode(Platform::Type *)
0x140013e17  mov     cs:?result@?1??InternalGetTypeCode@?$Box@W4WebErrorStatus@Web@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4W443@A, eax; Platform::TypeCode `Platform::Box<Windows::Web::WebErrorStatus>::InternalGetTypeCode(void)'::`2'::result
0x140013e1d  test    rdi, rdi
0x140013e20  jz      short loc_140013E31
0x140013e22  mov     rcx, [rdi]
0x140013e25  mov     rax, [rcx+10h]
0x140013e29  mov     rcx, rdi
0x140013e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e31  mov     rax, rbx
0x140013e34  jmp     short loc_140013E40
0x140013e36  mov     rbx, qword ptr [rbp+var_30]
0x140013e3a  xor     eax, eax
0x140013e3c  mov     rsi, qword ptr [rbp+var_30+8]
0x140013e40  test    rax, rax
0x140013e43  jz      short loc_140013E49
0x140013e45  mov     byte ptr [rsi+8], 1
0x140013e49  test    rbx, rbx
0x140013e4c  jz      short loc_140013E56
0x140013e4e  mov     rcx, rbx; SRWLock
0x140013e51  call    ReleaseSRWLockExclusive_0
0x140013e56  lea     rdx, [rbp+var_18]
0x140013e5a  mov     ecx, cs:?result@?1??InternalGetTypeCode@?$Box@W4WebErrorStatus@Web@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4W443@A; Platform::TypeCode `Platform::Box<Windows::Web::WebErrorStatus>::InternalGetTypeCode(void)'::`2'::result
0x140013e60  call    cs:__imp_?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z; Platform::Details::CreateValue(Platform::TypeCode,void const *)
0x140013e66  mov     rbx, rax
0x140013e69  mov     [rbp+var_38], rax
0x140013e6d  test    rax, rax
0x140013e70  jz      short loc_140013E81
0x140013e72  mov     rax, [rax]
0x140013e75  mov     rcx, rbx
0x140013e78  mov     rax, [rax+8]
0x140013e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e81  mov     [rbp+var_38], rbx
0x140013e85  test    rbx, rbx
0x140013e88  jz      short loc_140013E9A
0x140013e8a  mov     rax, [rbx]
0x140013e8d  mov     rcx, rbx
0x140013e90  mov     rax, [rax+10h]
0x140013e94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013e99  nop
0x140013e9a  test    rbx, rbx
0x140013e9d  jnz     short loc_140013F1E
0x140013e9f  lea     edx, [rbx+48h]
0x140013ea2  lea     ecx, [rbx+38h]
0x140013ea5  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x140013eab  mov     [rbp+var_20], rax
0x140013eaf  mov     edx, [rbp+var_18]
0x140013eb2  mov     rcx, rax
0x140013eb5  call    ??0?$CustomBox@W4WebErrorStatus@Web@Windows@@@Details@Platform@@QE$AAA@W4WebErrorStatus@Web@Windows@@@Z; Platform::Details::CustomBox<Windows::Web::WebErrorStatus>::CustomBox<Windows::Web::WebErrorStatus>(Windows::Web::WebErrorStatus)
0x140013eba  mov     rdi, rax
0x140013ebd  mov     [rbp+var_20], rax
0x140013ec1  test    rax, rax
0x140013ec4  jz      short loc_140013EDC
0x140013ec6  mov     rcx, [rax]
0x140013ec9  mov     rax, [rcx+8]
0x140013ecd  mov     rcx, rdi
0x140013ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ed5  mov     rbx, rdi
0x140013ed8  mov     [rbp+var_38], rbx
0x140013edc  test    rdi, rdi
0x140013edf  jz      short loc_140013EF0
0x140013ee1  mov     rax, [rdi]
0x140013ee4  mov     rcx, rdi
0x140013ee7  mov     rax, [rax+10h]
0x140013eeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013ef0  test    rbx, rbx
0x140013ef3  jz      short loc_140013F05
0x140013ef5  mov     rax, [rbx]
0x140013ef8  mov     rcx, rbx
0x140013efb  mov     rax, [rax+8]
0x140013eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f04  nop
0x140013f05  test    rbx, rbx
0x140013f08  jz      short loc_140013F19
0x140013f0a  mov     rax, [rbx]
0x140013f0d  mov     rcx, rbx
0x140013f10  mov     rax, [rax+10h]
0x140013f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f19  mov     rax, rbx
0x140013f1c  jmp     short loc_140013F8B
0x140013f1e  mov     [rbp+var_20], 0
0x140013f26  mov     rax, [rbx]
0x140013f29  lea     r8, [rbp+var_20]
0x140013f2d  lea     rdx, __uuidof_?AV?$Box@W4WebErrorStatus@Web@Windows@@@Platform@@
0x140013f34  mov     rcx, rbx
0x140013f37  mov     rax, [rax]
0x140013f3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f3f  mov     rdi, [rbp+var_20]
0x140013f43  xor     ecx, ecx
0x140013f45  test    eax, eax
0x140013f47  cmovnz  rdi, rcx
0x140013f4b  mov     qword ptr [rbp+var_30], rdi
0x140013f4f  test    rdi, rdi
0x140013f52  jz      short loc_140013F64
0x140013f54  mov     rax, [rdi]
0x140013f57  mov     rcx, rdi
0x140013f5a  mov     rax, [rax+8]
0x140013f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f63  nop
0x140013f64  test    rdi, rdi
0x140013f67  jz      short loc_140013F79
0x140013f69  mov     rcx, [rdi]
0x140013f6c  mov     rax, [rcx+10h]
0x140013f70  mov     rcx, rdi
0x140013f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f78  nop
0x140013f79  mov     rcx, [rbx]
0x140013f7c  mov     rax, [rcx+10h]
0x140013f80  mov     rcx, rbx
0x140013f83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013f88  mov     rax, rdi
0x140013f8b  mov     rcx, [rbp+var_10]
0x140013f8f  xor     rcx, rsp; StackCookie
0x140013f92  call    __security_check_cookie
0x140013f97  add     rsp, 58h
0x140013f9b  pop     rdi
0x140013f9c  pop     rsi
0x140013f9d  pop     rbx
0x140013f9e  pop     rbp
0x140013f9f  retn
```
