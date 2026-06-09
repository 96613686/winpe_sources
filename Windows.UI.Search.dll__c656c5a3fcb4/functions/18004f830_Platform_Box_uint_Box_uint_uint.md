# Platform::Box<uint>::Box<uint>(uint)

- ea: `0x18004f830`
- end: `0x18004f905`
- name: `??0?$Box@I@Platform@@QE$AAA@I@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18004dac0`

## callees

- `0x18000b818`
- `0x18000b888`
- `0x18000b8dc`
- `0x18000b908`
- `0x18004f830`
- `0x18004fb5c`
- `0x180054728`

## import_xrefs

- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004f84c`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004f84c`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004f87e`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004f87e`

## pseudocode

```c
__int64 __fastcall Platform::Box<unsigned int>::Box<unsigned int>(__int64 a1, unsigned int a2)
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
  TypeCode = Platform::Box<unsigned int>::InternalGetTypeCode();
  v3 = Platform::Details::CreateValue(TypeCode, &v11);
  v10 = v3;
  v4 = __abi_winrt_ptr_ctor(v3);
  v10 = v4;
  __abi_winrt_ptr_dtor(v3);
  if ( v4 )
  {
    LOBYTE(v5) = 1;
    v8 = __abi_winrt_cast_to(v5, v4, _uuidof__AV__Box_I_Platform__);
    v12 = (void *)v8;
    v7 = __abi_winrt_ptr_ctor(v8);
    __abi_winrt_ptr_dtor(v8);
  }
  else
  {
    v12 = Platform::Details::Heap::Allocate(0x38u, 0x48u);
    v6 = Platform::Details::CustomBox<unsigned int>::CustomBox<unsigned int>(v12, v11);
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
0x18004f830  mov     [rsp+arg_8], edx
0x18004f834  mov     [rsp+arg_0], rcx
0x18004f839  push    rbx
0x18004f83a  push    rsi
0x18004f83b  push    rdi
0x18004f83c  sub     rsp, 20h
0x18004f840  call    ?InternalGetTypeCode@?$Box@I@Platform@@CA?AW4TypeCode@2@XZ; Platform::Box<uint>::InternalGetTypeCode(void)
0x18004f845  mov     ecx, eax
0x18004f847  lea     rdx, [rsp+38h+arg_8]
0x18004f84c  call    cs:__imp_?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z; Platform::Details::CreateValue(Platform::TypeCode,void const *)
0x18004f852  mov     rbx, rax
0x18004f855  mov     [rsp+38h+arg_0], rax
0x18004f85a  mov     rcx, rax
0x18004f85d  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f862  mov     rsi, rax
0x18004f865  mov     [rsp+38h+arg_0], rax
0x18004f86a  mov     rcx, rbx
0x18004f86d  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f872  nop
0x18004f873  test    rsi, rsi
0x18004f876  jnz     short loc_18004F8C5
0x18004f878  lea     edx, [rsi+48h]
0x18004f87b  lea     ecx, [rsi+38h]
0x18004f87e  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x18004f884  mov     [rsp+38h+arg_10], rax
0x18004f889  mov     edx, [rsp+38h+arg_8]
0x18004f88d  mov     rcx, rax
0x18004f890  call    ??0?$CustomBox@I@Details@Platform@@QE$AAA@I@Z; Platform::Details::CustomBox<uint>::CustomBox<uint>(uint)
0x18004f895  mov     rbx, rax
0x18004f898  mov     [rsp+38h+arg_10], rax
0x18004f89d  mov     rdx, rax
0x18004f8a0  lea     rcx, [rsp+38h+arg_0]
0x18004f8a5  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18004f8aa  nop
0x18004f8ab  mov     rcx, rbx
0x18004f8ae  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f8b3  mov     rsi, [rsp+38h+arg_0]
0x18004f8b8  mov     rcx, rsi
0x18004f8bb  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f8c0  mov     rbx, rax
0x18004f8c3  jmp     short loc_18004F8F2
0x18004f8c5  lea     r8, __uuidof_?AV?$Box@I@Platform@@
0x18004f8cc  mov     rdx, rsi
0x18004f8cf  mov     cl, 1
0x18004f8d1  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18004f8d6  mov     rdi, rax
0x18004f8d9  mov     [rsp+38h+arg_10], rax
0x18004f8de  mov     rcx, rax
0x18004f8e1  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004f8e6  mov     rbx, rax
0x18004f8e9  mov     rcx, rdi
0x18004f8ec  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f8f1  nop
0x18004f8f2  mov     rcx, rsi
0x18004f8f5  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004f8fa  mov     rax, rbx
0x18004f8fd  add     rsp, 20h
0x18004f901  pop     rdi
0x18004f902  pop     rsi
0x18004f903  pop     rbx
0x18004f904  retn
```
