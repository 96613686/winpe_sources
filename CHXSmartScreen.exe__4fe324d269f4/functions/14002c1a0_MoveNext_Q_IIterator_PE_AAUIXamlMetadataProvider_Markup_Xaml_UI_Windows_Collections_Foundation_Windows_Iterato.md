# ?MoveNext@?Q?$IIterator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$IteratorForVectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@2Platform@@UE$AAA_NXZ

- ea: `0x14002c1a0`
- end: `0x14002c264`
- name: `?MoveNext@?Q?$IIterator@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Collections@Foundation@Windows@@?$IteratorForVectorView@PE$AAUIXamlMetadataProvider@Markup@Xaml@UI@Windows@@@Details@2Platform@@UE$AAA_NXZ`
- size: `196`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14002c270`
- `0x1400303a0`

## callees

- `0x140003330`
- `0x1400088b4`
- `0x14002c1a0`

## import_xrefs

- `wincorlib!??0ChangedStateException@Platform@@QE$AAA@XZ` at `0x14002c23a`
- `wincorlib!??0ChangedStateException@Platform@@QE$AAA@XZ` at `0x14002c23a`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002c1fa`
- `wincorlib!??0OutOfBoundsException@Platform@@QE$AAA@XZ` at `0x14002c1fa`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c1ec`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c22c`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c1ec`
- `wincorlib!?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z` at `0x14002c22c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
bool __fastcall _MoveNext__Q__IIterator_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Collections_Foundation_Windows____IteratorForVectorView_PE_AAUIXamlMetadataProvider_Markup_Xaml_UI_Windows___Details_2Platform__UE_AAA_NXZ(
        __int64 a1)
{
  _QWORD *v1; // rdx
  unsigned __int64 v2; // r8
  unsigned __int64 v3; // rax
  __int64 pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  void *Exception; // [rsp+38h] [rbp+10h]

  if ( **(_DWORD **)(a1 + 48) != *(_DWORD *)(a1 + 80) )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    Exception = (void *)Platform::ChangedStateException::ChangedStateException(Exception);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::ChangedStateException **)&pExceptionObject;
  }
  v1 = *(_QWORD **)(a1 + 64);
  v2 = *(unsigned int *)(a1 + 84);
  if ( v2 >= (__int64)(v1[1] - *v1) >> 3 )
  {
    Exception = Platform::Details::Heap::AllocateException(0x68u, 0x90u);
    Exception = (void *)Platform::OutOfBoundsException::OutOfBoundsException(Exception);
    pExceptionObject = __abi_winrt_ptr_ctor(Exception);
    throw (Platform::OutOfBoundsException **)&pExceptionObject;
  }
  v3 = (unsigned int)(v2 + 1);
  *(_DWORD *)(a1 + 84) = v3;
  return v3 < (__int64)(v1[1] - *v1) >> 3;
}

```

## disassembly

```asm
0x14002c1a0  sub     rsp, 28h
0x14002c1a4  mov     rdx, [rcx+30h]
0x14002c1a8  mov     eax, [rcx+50h]
0x14002c1ab  cmp     [rdx], eax
0x14002c1ad  jnz     short loc_14002C224
0x14002c1af  mov     rdx, [rcx+40h]
0x14002c1b3  mov     r8d, [rcx+54h]
0x14002c1b7  mov     rax, [rdx+8]
0x14002c1bb  sub     rax, [rdx]
0x14002c1be  sar     rax, 3
0x14002c1c2  cmp     r8, rax
0x14002c1c5  jnb     short loc_14002C1E4
0x14002c1c7  lea     eax, [r8+1]
0x14002c1cb  mov     [rcx+54h], eax
0x14002c1ce  mov     rcx, [rdx+8]
0x14002c1d2  sub     rcx, [rdx]
0x14002c1d5  sar     rcx, 3
0x14002c1d9  cmp     rax, rcx
0x14002c1dc  setb    al
0x14002c1df  add     rsp, 28h
0x14002c1e3  retn
0x14002c1e4  mov     edx, 90h
0x14002c1e9  lea     ecx, [rdx-28h]
0x14002c1ec  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002c1f2  mov     [rsp+28h+arg_8], rax
0x14002c1f7  mov     rcx, rax
0x14002c1fa  call    cs:__imp_??0OutOfBoundsException@Platform@@QE$AAA@XZ; Platform::OutOfBoundsException::OutOfBoundsException(void)
0x14002c200  mov     [rsp+28h+arg_8], rax
0x14002c205  mov     rcx, rax
0x14002c208  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002c20d  mov     [rsp+28h+pExceptionObject], rax
0x14002c212  lea     rdx, _TI11PE$AAVOutOfBoundsException@Platform@@; pThrowInfo
0x14002c219  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002c21e  call    _CxxThrowException_0
0x14002c224  mov     edx, 90h
0x14002c229  lea     ecx, [rdx-28h]
0x14002c22c  call    cs:__imp_?AllocateException@Heap@Details@Platform@@SAPEAX_K0@Z; Platform::Details::Heap::AllocateException(unsigned __int64,unsigned __int64)
0x14002c232  mov     [rsp+28h+arg_8], rax
0x14002c237  mov     rcx, rax
0x14002c23a  call    cs:__imp_??0ChangedStateException@Platform@@QE$AAA@XZ; Platform::ChangedStateException::ChangedStateException(void)
0x14002c240  mov     [rsp+28h+arg_8], rax
0x14002c245  mov     rcx, rax
0x14002c248  call    ?__abi_winrt_ptr_ctor@@YAPEAXQE$ADVObject@Platform@@@Z; __abi_winrt_ptr_ctor(Platform::Object const volatile * const)
0x14002c24d  mov     [rsp+28h+pExceptionObject], rax
0x14002c252  lea     rdx, _TI11PE$AAVChangedStateException@Platform@@; pThrowInfo
0x14002c259  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x14002c25e  call    _CxxThrowException_0
```
