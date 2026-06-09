# winrt::implements<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>>::Release(void)

- ea: `0x180013ca8`
- end: `0x180013d39`
- name: `?Release@?$implements@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@Uhstring@winrt@@@5673@U?$IIterable@Uhstring@winrt@@@5673@@winrt@@QEAAIXZ`
- size: `145`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180013dc0`
- `0x180013de0`
- `0x180013e00`
- `0x180015678`

## callees

- `0x180004434`
- `0x180013ca8`
- `0x180041010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013d32`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180013d32`

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
0x180013ca8  mov     [rsp+arg_0], rbx
0x180013cad  push    rdi
0x180013cae  sub     rsp, 20h
0x180013cb2  mov     rax, [rcx+8]
0x180013cb6  mov     rdi, rcx
0x180013cb9  test    rax, rax
0x180013cbc  js      short loc_180013CCC
0x180013cbe  lea     rbx, [rax-1]
0x180013cc2  lock cmpxchg [rcx+8], rbx
0x180013cc8  jnz     short loc_180013CB9
0x180013cca  jmp     short loc_180013D07
0x180013ccc  or      edx, 0FFFFFFFFh
0x180013ccf  lea     rcx, [rax+rax]; Block
0x180013cd3  mov     ebx, edx
0x180013cd5  lock xadd [rcx+18h], ebx
0x180013cda  sub     ebx, 1
0x180013cdd  jnz     short loc_180013D07
0x180013cdf  mov     eax, edx
0x180013ce1  lock xadd [rcx+1Ch], eax
0x180013ce6  cmp     eax, 1
0x180013ce9  jnz     short loc_180013D07
0x180013ceb  test    rcx, rcx
0x180013cee  jz      short loc_180013D07
0x180013cf0  lock xadd cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A, edx; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x180013cf8  sub     edx, eax
0x180013cfa  jnz     short loc_180013D2E
0x180013cfc  nop
0x180013cfd  mov     edx, 20h ; ' '
0x180013d02  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180013d07  test    ebx, ebx
0x180013d09  jnz     short loc_180013D21
0x180013d0b  lea     edx, [rbx+1]
0x180013d0e  mov     [rdi+8], rdx
0x180013d12  mov     rcx, [rdi]
0x180013d15  mov     rax, [rcx+8]
0x180013d19  mov     rcx, rdi
0x180013d1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d21  mov     eax, ebx
0x180013d23  mov     rbx, [rsp+28h+arg_0]
0x180013d28  add     rsp, 20h
0x180013d2c  pop     rdi
0x180013d2d  retn
0x180013d2e  test    edx, edx
0x180013d30  jns     short loc_180013CFD
0x180013d32  call    cs:__imp_abort
```
