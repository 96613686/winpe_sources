# Platform::Box<Windows::UI::Color>::Box<Windows::UI::Color>(Windows::UI::Color)

- ea: `0x140013ba8`
- end: `0x140013da0`
- name: `??0?$Box@VColor@UI@Windows@@@Platform@@QE$AAA@VColor@UI@Windows@@@Z`
- size: `504`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140013900`

## callees

- `0x1400013f0`
- `0x1400013fc`
- `0x140013ba8`
- `0x140013fa8`
- `0x140031960`
- `0x140035010`

## import_xrefs

- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x140013c11`
- `wincorlib!?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z` at `0x140013c11`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x140013c60`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x140013c60`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x140013c01`
- `wincorlib!?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z` at `0x140013c01`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140013ca5`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x140013ca5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Platform::Box<Windows::UI::Color>::Box<Windows::UI::Color>(__int64 a1, unsigned int a2)
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
  if ( byte_14004D0C0 )
  {
    v2 = 0;
    goto LABEL_7;
  }
  v2 = &`Platform::Box<Windows::UI::Color>::InternalGetTypeCode'::`2'::once;
  _Platform_AcquireSRWLockExclusive(&`Platform::Box<Windows::UI::Color>::InternalGetTypeCode'::`2'::once);
  if ( byte_14004D0C0 )
  {
LABEL_7:
    v5 = 0;
    v3 = 0;
    goto LABEL_8;
  }
  v3 = &`Platform::Box<Windows::UI::Color>::InternalGetTypeCode'::`2'::once;
  type_id = __abi_make_type_id(&_abi_typedesc_Windows_UI_Color);
  `Platform::Box<Windows::UI::Color>::InternalGetTypeCode'::`2'::result = Platform::Type::GetTypeCode(type_id);
  if ( type_id )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)type_id + 16LL))(type_id);
  v5 = &`Platform::Box<Windows::UI::Color>::InternalGetTypeCode'::`2'::once;
LABEL_8:
  if ( v5 )
    LOBYTE(v3[1].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive_0(v2);
  v6 = Platform::Details::CreateValue(
         (unsigned int)`Platform::Box<Windows::UI::Color>::InternalGetTypeCode'::`2'::result,
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
            _uuidof__AV__Box_VColor_UI_Windows___Platform__,
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
    v9 = Platform::Details::CustomBox<Windows::UI::Color>::CustomBox<Windows::UI::Color>(v8, v15);
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
0x140013ba8  push    rbp
0x140013baa  push    rbx
0x140013bab  push    rsi
0x140013bac  push    rdi
0x140013bad  mov     rbp, rsp
0x140013bb0  sub     rsp, 58h
0x140013bb4  mov     rax, cs:__security_cookie
0x140013bbb  xor     rax, rsp
0x140013bbe  mov     [rbp+var_10], rax
0x140013bc2  mov     [rbp+var_18], edx
0x140013bc5  xorps   xmm0, xmm0
0x140013bc8  movdqu  [rbp+var_30], xmm0
0x140013bcd  mov     al, cs:byte_14004D0C0
0x140013bd3  test    al, al
0x140013bd5  jnz     short loc_140013C36
0x140013bd7  lea     rbx, ?once@?1??InternalGetTypeCode@?$Box@VColor@UI@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4U__vccorlib_once_t@@A; __vccorlib_once_t `Platform::Box<Windows::UI::Color>::InternalGetTypeCode(void)'::`2'::once
0x140013bde  mov     rcx, rbx; SRWLock
0x140013be1  call    __Platform_AcquireSRWLockExclusive
0x140013be6  mov     qword ptr [rbp+var_30], rbx
0x140013bea  cmp     cs:byte_14004D0C0, 0
0x140013bf1  jnz     short loc_140013C3A
0x140013bf3  mov     rsi, rbx
0x140013bf6  mov     qword ptr [rbp+var_30+8], rbx
0x140013bfa  lea     rcx, __abi_typedesc_Windows_UI_Color
0x140013c01  call    cs:__imp_?__abi_make_type_id@@YAPE$AAVType@Platform@@AEBU__abi_type_descriptor@@@Z; __abi_make_type_id(__abi_type_descriptor const &)
0x140013c07  mov     rdi, rax
0x140013c0a  mov     [rbp+var_38], rax
0x140013c0e  mov     rcx, rax
0x140013c11  call    cs:__imp_?GetTypeCode@Type@Platform@@SA?AW4TypeCode@2@PE$AAV12@@Z; Platform::Type::GetTypeCode(Platform::Type *)
0x140013c17  mov     cs:?result@?1??InternalGetTypeCode@?$Box@VColor@UI@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4W443@A, eax; Platform::TypeCode `Platform::Box<Windows::UI::Color>::InternalGetTypeCode(void)'::`2'::result
0x140013c1d  test    rdi, rdi
0x140013c20  jz      short loc_140013C31
0x140013c22  mov     rcx, [rdi]
0x140013c25  mov     rax, [rcx+10h]
0x140013c29  mov     rcx, rdi
0x140013c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c31  mov     rax, rbx
0x140013c34  jmp     short loc_140013C40
0x140013c36  mov     rbx, qword ptr [rbp+var_30]
0x140013c3a  xor     eax, eax
0x140013c3c  mov     rsi, qword ptr [rbp+var_30+8]
0x140013c40  test    rax, rax
0x140013c43  jz      short loc_140013C49
0x140013c45  mov     byte ptr [rsi+8], 1
0x140013c49  test    rbx, rbx
0x140013c4c  jz      short loc_140013C56
0x140013c4e  mov     rcx, rbx; SRWLock
0x140013c51  call    ReleaseSRWLockExclusive_0
0x140013c56  lea     rdx, [rbp+var_18]
0x140013c5a  mov     ecx, cs:?result@?1??InternalGetTypeCode@?$Box@VColor@UI@Windows@@@Platform@@CA?AW4TypeCode@3@XZ@4W443@A; Platform::TypeCode `Platform::Box<Windows::UI::Color>::InternalGetTypeCode(void)'::`2'::result
0x140013c60  call    cs:__imp_?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z; Platform::Details::CreateValue(Platform::TypeCode,void const *)
0x140013c66  mov     rbx, rax
0x140013c69  mov     [rbp+var_38], rax
0x140013c6d  test    rax, rax
0x140013c70  jz      short loc_140013C81
0x140013c72  mov     rax, [rax]
0x140013c75  mov     rcx, rbx
0x140013c78  mov     rax, [rax+8]
0x140013c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c81  mov     [rbp+var_38], rbx
0x140013c85  test    rbx, rbx
0x140013c88  jz      short loc_140013C9A
0x140013c8a  mov     rax, [rbx]
0x140013c8d  mov     rcx, rbx
0x140013c90  mov     rax, [rax+10h]
0x140013c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c99  nop
0x140013c9a  test    rbx, rbx
0x140013c9d  jnz     short loc_140013D1E
0x140013c9f  lea     edx, [rbx+48h]
0x140013ca2  lea     ecx, [rbx+38h]
0x140013ca5  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x140013cab  mov     [rbp+var_20], rax
0x140013caf  mov     edx, [rbp+var_18]
0x140013cb2  mov     rcx, rax
0x140013cb5  call    ??0?$CustomBox@VColor@UI@Windows@@@Details@Platform@@QE$AAA@VColor@UI@Windows@@@Z; Platform::Details::CustomBox<Windows::UI::Color>::CustomBox<Windows::UI::Color>(Windows::UI::Color)
0x140013cba  mov     rdi, rax
0x140013cbd  mov     [rbp+var_20], rax
0x140013cc1  test    rax, rax
0x140013cc4  jz      short loc_140013CDC
0x140013cc6  mov     rcx, [rax]
0x140013cc9  mov     rax, [rcx+8]
0x140013ccd  mov     rcx, rdi
0x140013cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013cd5  mov     rbx, rdi
0x140013cd8  mov     [rbp+var_38], rbx
0x140013cdc  test    rdi, rdi
0x140013cdf  jz      short loc_140013CF0
0x140013ce1  mov     rax, [rdi]
0x140013ce4  mov     rcx, rdi
0x140013ce7  mov     rax, [rax+10h]
0x140013ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013cf0  test    rbx, rbx
0x140013cf3  jz      short loc_140013D05
0x140013cf5  mov     rax, [rbx]
0x140013cf8  mov     rcx, rbx
0x140013cfb  mov     rax, [rax+8]
0x140013cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d04  nop
0x140013d05  test    rbx, rbx
0x140013d08  jz      short loc_140013D19
0x140013d0a  mov     rax, [rbx]
0x140013d0d  mov     rcx, rbx
0x140013d10  mov     rax, [rax+10h]
0x140013d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d19  mov     rax, rbx
0x140013d1c  jmp     short loc_140013D8B
0x140013d1e  mov     [rbp+var_20], 0
0x140013d26  mov     rax, [rbx]
0x140013d29  lea     r8, [rbp+var_20]
0x140013d2d  lea     rdx, __uuidof_?AV?$Box@VColor@UI@Windows@@@Platform@@
0x140013d34  mov     rcx, rbx
0x140013d37  mov     rax, [rax]
0x140013d3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d3f  mov     rdi, [rbp+var_20]
0x140013d43  xor     ecx, ecx
0x140013d45  test    eax, eax
0x140013d47  cmovnz  rdi, rcx
0x140013d4b  mov     qword ptr [rbp+var_30], rdi
0x140013d4f  test    rdi, rdi
0x140013d52  jz      short loc_140013D64
0x140013d54  mov     rax, [rdi]
0x140013d57  mov     rcx, rdi
0x140013d5a  mov     rax, [rax+8]
0x140013d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d63  nop
0x140013d64  test    rdi, rdi
0x140013d67  jz      short loc_140013D79
0x140013d69  mov     rcx, [rdi]
0x140013d6c  mov     rax, [rcx+10h]
0x140013d70  mov     rcx, rdi
0x140013d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d78  nop
0x140013d79  mov     rcx, [rbx]
0x140013d7c  mov     rax, [rcx+10h]
0x140013d80  mov     rcx, rbx
0x140013d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013d88  mov     rax, rdi
0x140013d8b  mov     rcx, [rbp+var_10]
0x140013d8f  xor     rcx, rsp; StackCookie
0x140013d92  call    __security_check_cookie
0x140013d97  add     rsp, 58h
0x140013d9b  pop     rdi
0x140013d9c  pop     rsi
0x140013d9d  pop     rbx
0x140013d9e  pop     rbp
0x140013d9f  retn
```
