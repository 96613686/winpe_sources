# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x180012250`
- end: `0x1800122bb`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180010fc0`
- `0x180010fe0`
- `0x180011000`

## callees

- `0x18000509c`
- `0x180005108`
- `0x180012250`
- `0x180032010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800122b3`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800122b3`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx
  void *v5; // rbx
  int v6; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  try
  {
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v4 = *v3;
    *v3 = 0;
    *a2 = v4;
    v5 = lpMem;
    if ( lpMem )
    {
      v6 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v6 )
      {
        if ( v6 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v5);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x180012250  push    rbx
0x180012252  sub     rsp, 20h
0x180012256  mov     rbx, rdx
0x180012259  mov     rax, [rcx]
0x18001225c  lea     rdx, [rsp+28h+lpMem]
0x180012261  mov     rax, [rax+28h]
0x180012265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001226a  mov     rcx, [rax]
0x18001226d  mov     qword ptr [rax], 0
0x180012274  mov     [rbx], rcx
0x180012277  mov     rbx, [rsp+28h+lpMem]
0x18001227c  test    rbx, rbx
0x18001227f  jz      short loc_1800122A1
0x180012281  or      eax, 0FFFFFFFFh
0x180012284  lock xadd [rbx+18h], eax
0x180012289  sub     eax, 1
0x18001228c  jnz     short loc_1800122AF
0x18001228e  nop
0x18001228f  call    WINRT_IMPL_GetProcessHeap
0x180012294  mov     rcx, rax; hHeap
0x180012297  mov     r8, rbx; lpMem
0x18001229a  xor     edx, edx; dwFlags
0x18001229c  call    WINRT_IMPL_HeapFree
0x1800122a1  xor     eax, eax
0x1800122a3  jmp     short loc_1800122A9
0x1800122a5  mov     eax, dword ptr [rsp+28h+lpMem]
0x1800122a9  add     rsp, 20h
0x1800122ad  pop     rbx
0x1800122ae  retn
0x1800122af  test    eax, eax
0x1800122b1  jns     short loc_1800122A1
0x1800122b3  call    cs:__imp_abort
```
