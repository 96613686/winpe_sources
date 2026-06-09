# Platform::Box<int>::Box<int>(int)

- ea: `0x18004f754`
- end: `0x18004f829`
- name: `??0?$Box@H@Platform@@QE$AAA@H@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004db40`
- `0x18004dbc0`

## callees

- `0x18000b818`
- `0x18000b888`
- `0x18000b8dc`
- `0x18000b908`
- `0x18004f754`
- `0x18004fac4`
- `0x180054684`

## import_xrefs

- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004f770`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004f770`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004f7a2`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004f7a2`

## pseudocode

```c
__int64 __fastcall Platform::Box<int>::Box<int>(__int64 a1, unsigned int a2)
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
  TypeCode = Platform::Box<int>::InternalGetTypeCode();
  v3 = Platform::Details::CreateValue(TypeCode, &v11);
  v10 = v3;
  v4 = __abi_winrt_ptr_ctor(v3);
  v10 = v4;
  __abi_winrt_ptr_dtor(v3);
  if ( v4 )
  {
    LOBYTE(v5) = 1;
    v8 = __abi_winrt_cast_to(v5, v4, _uuidof__AV__Box_H_Platform__);
    v12 = (void *)v8;
    v7 = __abi_winrt_ptr_ctor(v8);
    __abi_winrt_ptr_dtor(v8);
  }
  else
  {
    v12 = Platform::Details::Heap::Allocate(0x38u, 0x48u);
    v6 = Platform::Details::CustomBox<int>::CustomBox<int>(v12, v11);
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
0x18004f754  mov     [rsp+arg_8], edx
0x18004f758  mov     [rsp+arg_0], rcx
0x18004f75d  push    rbx
0x18004f75e  push    rsi
0x18004f75f  push    rdi
0x18004f760  sub     rsp, 20h
0x18004f764  call    ?InternalGetTypeCode@?$Box@H@Platform@@CA?AW4TypeCode@2@XZ; Platform::Box<int>::InternalGetTypeCode(void)
0x18004f769  mov     ecx, eax
0x18004f76b  lea     rdx, [rsp+38h+arg_8]
0x18004f770  call    cs:__imp_?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z; Platform::Details::CreateValue(Platform::TypeCode,void const *)
0x18004f776  mov     rbx, rax
0x18004f779  mov     [rsp+38h+arg_0], rax
0x18004f77e  mov     rcx, rax
0x18004f781  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f786  mov     rsi, rax
0x18004f789  mov     [rsp+38h+arg_0], rax
0x18004f78e  mov     rcx, rbx
0x18004f791  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f796  nop
0x18004f797  test    rsi, rsi
0x18004f79a  jnz     short loc_18004F7E9
0x18004f79c  lea     edx, [rsi+48h]
0x18004f79f  lea     ecx, [rsi+38h]
0x18004f7a2  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x18004f7a8  mov     [rsp+38h+arg_10], rax
0x18004f7ad  mov     edx, [rsp+38h+arg_8]
0x18004f7b1  mov     rcx, rax
0x18004f7b4  call    ??0?$CustomBox@H@Details@Platform@@QE$AAA@H@Z; Platform::Details::CustomBox<int>::CustomBox<int>(int)
0x18004f7b9  mov     rbx, rax
0x18004f7bc  mov     [rsp+38h+arg_10], rax
0x18004f7c1  mov     rdx, rax
0x18004f7c4  lea     rcx, [rsp+38h+arg_0]
0x18004f7c9  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18004f7ce  nop
0x18004f7cf  mov     rcx, rbx
0x18004f7d2  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f7d7  mov     rsi, [rsp+38h+arg_0]
0x18004f7dc  mov     rcx, rsi
0x18004f7df  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f7e4  mov     rbx, rax
0x18004f7e7  jmp     short loc_18004F816
0x18004f7e9  lea     r8, __uuidof_?AV?$Box@H@Platform@@
0x18004f7f0  mov     rdx, rsi
0x18004f7f3  mov     cl, 1
0x18004f7f5  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18004f7fa  mov     rdi, rax
0x18004f7fd  mov     [rsp+38h+arg_10], rax
0x18004f802  mov     rcx, rax
0x18004f805  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f80a  mov     rbx, rax
0x18004f80d  mov     rcx, rdi
0x18004f810  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f815  nop
0x18004f816  mov     rcx, rsi
0x18004f819  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f81e  mov     rax, rbx
0x18004f821  add     rsp, 20h
0x18004f825  pop     rdi
0x18004f826  pop     rsi
0x18004f827  pop     rbx
0x18004f828  retn
```
