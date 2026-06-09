# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::hstring>>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x1800166a0`
- end: `0x18001670b`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@U?$IIterator@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `107`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180015970`
- `0x180015990`
- `0x1800159b0`

## callees

- `0x180004718`
- `0x180004784`
- `0x1800166a0`
- `0x180021010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180016703`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180016703`

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
0x1800166a0  push    rbx
0x1800166a2  sub     rsp, 20h
0x1800166a6  mov     rbx, rdx
0x1800166a9  mov     rax, [rcx]
0x1800166ac  lea     rdx, [rsp+28h+lpMem]
0x1800166b1  mov     rax, [rax+28h]
0x1800166b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ba  mov     rcx, [rax]
0x1800166bd  mov     qword ptr [rax], 0
0x1800166c4  mov     [rbx], rcx
0x1800166c7  mov     rbx, [rsp+28h+lpMem]
0x1800166cc  test    rbx, rbx
0x1800166cf  jz      short loc_1800166F1
0x1800166d1  or      eax, 0FFFFFFFFh
0x1800166d4  lock xadd [rbx+18h], eax
0x1800166d9  sub     eax, 1
0x1800166dc  jnz     short loc_1800166FF
0x1800166de  nop
0x1800166df  call    WINRT_IMPL_GetProcessHeap
0x1800166e4  mov     rcx, rax; hHeap
0x1800166e7  mov     r8, rbx; lpMem
0x1800166ea  xor     edx, edx; dwFlags
0x1800166ec  call    WINRT_IMPL_HeapFree
0x1800166f1  xor     eax, eax
0x1800166f3  jmp     short loc_1800166F9
0x1800166f5  mov     eax, dword ptr [rsp+28h+lpMem]
0x1800166f9  add     rsp, 20h
0x1800166fd  pop     rbx
0x1800166fe  retn
0x1800166ff  test    eax, eax
0x180016701  jns     short loc_1800166F1
0x180016703  call    cs:__imp_abort
```
