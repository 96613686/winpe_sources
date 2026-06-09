# Platform::Box<bool>::Box<bool>(bool)

- ea: `0x18004f9e8`
- end: `0x18004fabd`
- name: `??0?$Box@_N@Platform@@QE$AAA@_N@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, char)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x18004d920`
- `0x18004da30`

## callees

- `0x18000b818`
- `0x18000b888`
- `0x18000b8dc`
- `0x18000b908`
- `0x18004f9e8`
- `0x18004fc8c`
- `0x180054870`

## import_xrefs

- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004fa04`
- `wincorlib!?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z` at `0x18004fa04`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004fa36`
- `wincorlib!?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x18004fa36`

## pseudocode

```c
__int64 __fastcall Platform::Box<bool>::Box<bool>(__int64 a1, char a2)
{
  unsigned int TypeCode; // eax
  __int64 v3; // rbx
  __int64 v4; // rsi
  __int64 v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 v9; // rdi
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF
  char v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+50h] [rbp+18h]

  v12 = a2;
  v11 = a1;
  TypeCode = Platform::Box<bool>::InternalGetTypeCode();
  v3 = Platform::Details::CreateValue(TypeCode, &v12);
  v11 = v3;
  v4 = __abi_winrt_ptr_ctor(v3);
  v11 = v4;
  __abi_winrt_ptr_dtor(v3);
  if ( v4 )
  {
    LOBYTE(v5) = 1;
    v9 = __abi_winrt_cast_to(v5, v4, _uuidof__AV__Box__N_Platform__);
    v13 = (void *)v9;
    v8 = __abi_winrt_ptr_ctor(v9);
    __abi_winrt_ptr_dtor(v9);
  }
  else
  {
    v13 = Platform::Details::Heap::Allocate(0x38u, 0x48u);
    LOBYTE(v6) = v12;
    v7 = Platform::Details::CustomBox<bool>::CustomBox<bool>(v13, v6);
    v13 = (void *)v7;
    __abi_winrt_ptr_assign(&v11, v7);
    __abi_winrt_ptr_dtor(v7);
    v4 = v11;
    v8 = __abi_winrt_ptr_ctor(v11);
  }
  __abi_winrt_ptr_dtor(v4);
  return v8;
}

```

## disassembly

```asm
0x18004f9e8  mov     [rsp+arg_8], dl
0x18004f9ec  mov     [rsp+arg_0], rcx
0x18004f9f1  push    rbx
0x18004f9f2  push    rsi
0x18004f9f3  push    rdi
0x18004f9f4  sub     rsp, 20h
0x18004f9f8  call    ?InternalGetTypeCode@?$Box@_N@Platform@@CA?AW4TypeCode@2@XZ; Platform::Box<bool>::InternalGetTypeCode(void)
0x18004f9fd  mov     ecx, eax
0x18004f9ff  lea     rdx, [rsp+38h+arg_8]
0x18004fa04  call    cs:__imp_?CreateValue@Details@Platform@@YAPE$AAVObject@2@W4TypeCode@2@PEBX@Z; Platform::Details::CreateValue(Platform::TypeCode,void const *)
0x18004fa0a  mov     rbx, rax
0x18004fa0d  mov     [rsp+38h+arg_0], rax
0x18004fa12  mov     rcx, rax
0x18004fa15  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004fa1a  mov     rsi, rax
0x18004fa1d  mov     [rsp+38h+arg_0], rax
0x18004fa22  mov     rcx, rbx
0x18004fa25  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004fa2a  nop
0x18004fa2b  test    rsi, rsi
0x18004fa2e  jnz     short loc_18004FA7D
0x18004fa30  lea     edx, [rsi+48h]
0x18004fa33  lea     ecx, [rsi+38h]
0x18004fa36  call    cs:__imp_?Allocate@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::Allocate(unsigned __int64,unsigned __int64)
0x18004fa3c  mov     [rsp+38h+arg_10], rax
0x18004fa41  mov     dl, [rsp+38h+arg_8]
0x18004fa45  mov     rcx, rax
0x18004fa48  call    ??0?$CustomBox@_N@Details@Platform@@QE$AAA@_N@Z; Platform::Details::CustomBox<bool>::CustomBox<bool>(bool)
0x18004fa4d  mov     rbx, rax
0x18004fa50  mov     [rsp+38h+arg_10], rax
0x18004fa55  mov     rdx, rax
0x18004fa58  lea     rcx, [rsp+38h+arg_0]
0x18004fa5d  call    ?__abi_winrt_ptr_assign@@YAPEAXPEAPEAXPE$ADVObject@Platform@@@Z; __abi_winrt_ptr_assign(void * *,Platform::Object const volatile *)
0x18004fa62  nop
0x18004fa63  mov     rcx, rbx
0x18004fa66  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004fa6b  mov     rsi, [rsp+38h+arg_0]
0x18004fa70  mov     rcx, rsi
0x18004fa73  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004fa78  mov     rbx, rax
0x18004fa7b  jmp     short loc_18004FAAA
0x18004fa7d  lea     r8, __uuidof_?AV?$Box@_N@Platform@@
0x18004fa84  mov     rdx, rsi
0x18004fa87  mov     cl, 1
0x18004fa89  call    ?__abi_winrt_cast_to@@YAPE$AAVObject@Platform@@_NPE$AAV12@AEBU_GUID@@@Z; __abi_winrt_cast_to(bool,Platform::Object *,_GUID const &)
0x18004fa8e  mov     rdi, rax
0x18004fa91  mov     [rsp+38h+arg_10], rax
0x18004fa96  mov     rcx, rax
0x18004fa99  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x18004fa9e  mov     rbx, rax
0x18004faa1  mov     rcx, rdi
0x18004faa4  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004faa9  nop
0x18004faaa  mov     rcx, rsi
0x18004faad  call    ?__abi_winrt_ptr_dtor@@YAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_dtor(Platform::Object const volatile * const)
0x18004fab2  mov     rax, rbx
0x18004fab5  add     rsp, 20h
0x18004fab9  pop     rdi
0x18004faba  pop     rsi
0x18004fabb  pop     rbx
0x18004fabc  retn
```
