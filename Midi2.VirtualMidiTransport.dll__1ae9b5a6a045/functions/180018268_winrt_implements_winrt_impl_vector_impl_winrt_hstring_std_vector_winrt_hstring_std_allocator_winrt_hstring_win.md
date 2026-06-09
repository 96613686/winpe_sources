# winrt::implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::Release(void)

- ea: `0x180018268`
- end: `0x1800182f9`
- name: `?Release@?$implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@Uhstring@winrt@@@5673@U?$IIterable@Uhstring@winrt@@@5673@@winrt@@QEAAIXZ`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018380`
- `0x1800183a0`
- `0x1800183c0`
- `0x18001a72c`

## callees

- `0x180003914`
- `0x180018268`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800182f2`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800182f2`

## pseudocode

```c
__int64 __fastcall winrt::implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rax
  unsigned __int32 v3; // ebx
  signed __int64 v4; // rtt
  volatile signed __int32 *v5; // rcx

  v1 = *((_QWORD *)a1 + 1);
  while ( v1 >= 0 )
  {
    v3 = v1 - 1;
    v4 = v1;
    v1 = _InterlockedCompareExchange64(a1 + 1, v1 - 1, v1);
    if ( v4 == v1 )
      goto LABEL_10;
  }
  v5 = (volatile signed __int32 *)(2 * v1);
  v3 = _InterlockedDecrement((volatile signed __int32 *)(2 * v1 + 24));
  if ( !v3 && _InterlockedExchangeAdd(v5 + 7, 0xFFFFFFFF) == 1 && v5 )
  {
    if ( _InterlockedDecrement(&`winrt::get_module_lock'::`2'::s_lock) < 0 )
      abort();
    operator delete((void *)v5);
  }
LABEL_10:
  if ( !v3 )
  {
    *((_QWORD *)a1 + 1) = 1;
    (*(void (__fastcall **)(volatile signed __int64 *))(*a1 + 8))(a1);
  }
  return v3;
}

```

## disassembly

```asm
0x180018268  mov     [rsp+arg_0], rbx
0x18001826d  push    rdi
0x18001826e  sub     rsp, 20h
0x180018272  mov     rax, [rcx+8]
0x180018276  mov     rdi, rcx
0x180018279  test    rax, rax
0x18001827c  js      short loc_18001828C
0x18001827e  lea     rbx, [rax-1]
0x180018282  lock cmpxchg [rcx+8], rbx
0x180018288  jnz     short loc_180018279
0x18001828a  jmp     short loc_1800182C7
0x18001828c  or      edx, 0FFFFFFFFh
0x18001828f  lea     rcx, [rax+rax]; Block
0x180018293  mov     ebx, edx
0x180018295  lock xadd [rcx+18h], ebx
0x18001829a  sub     ebx, 1
0x18001829d  jnz     short loc_1800182C7
0x18001829f  mov     eax, edx
0x1800182a1  lock xadd [rcx+1Ch], eax
0x1800182a6  cmp     eax, 1
0x1800182a9  jnz     short loc_1800182C7
0x1800182ab  test    rcx, rcx
0x1800182ae  jz      short loc_1800182C7
0x1800182b0  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x1800182b8  sub     edx, eax
0x1800182ba  jnz     short loc_1800182EE
0x1800182bc  nop
0x1800182bd  mov     edx, 20h ; ' '
0x1800182c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800182c7  test    ebx, ebx
0x1800182c9  jnz     short loc_1800182E1
0x1800182cb  lea     edx, [rbx+1]
0x1800182ce  mov     [rdi+8], rdx
0x1800182d2  mov     rcx, [rdi]
0x1800182d5  mov     rax, [rcx+8]
0x1800182d9  mov     rcx, rdi
0x1800182dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800182e1  mov     eax, ebx
0x1800182e3  mov     rbx, [rsp+28h+arg_0]
0x1800182e8  add     rsp, 20h
0x1800182ec  pop     rdi
0x1800182ed  retn
0x1800182ee  test    edx, edx
0x1800182f0  jns     short loc_1800182BD
0x1800182f2  call    cs:__imp_abort
```
