# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::GetAt(uint,void * *)

- ea: `0x180015130`
- end: `0x1800151b2`
- name: `?GetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004718`
- `0x180004784`
- `0x180015130`
- `0x180015248`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800151aa`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800151aa`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::GetAt(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  __int64 *v6; // rax
  __int64 v7; // rcx
  void *v8; // rbx
  int v9; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v5 = a1 + 24;
  if ( !a1 )
    v5 = 40;
  try
  {
    v6 = winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(
           v5,
           &lpMem,
           a2);
    v7 = *v6;
    *v6 = 0;
    *a3 = v7;
    v8 = lpMem;
    if ( lpMem )
    {
      v9 = _InterlockedDecrement((volatile signed __int32 *)lpMem + 6);
      if ( v9 )
      {
        if ( v9 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, v8);
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
0x180015130  push    rbx
0x180015132  sub     rsp, 20h
0x180015136  mov     rbx, r8
0x180015139  mov     rax, rcx
0x18001513c  mov     qword ptr [r8], 0
0x180015143  add     rcx, 18h
0x180015147  mov     r8d, 28h ; '('
0x18001514d  test    rax, rax
0x180015150  cmovz   rcx, r8
0x180015154  mov     r8d, edx
0x180015157  lea     rdx, [rsp+28h+lpMem]
0x18001515c  call    ?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)
0x180015161  mov     rcx, [rax]
0x180015164  mov     qword ptr [rax], 0
0x18001516b  mov     [rbx], rcx
0x18001516e  mov     rbx, [rsp+28h+lpMem]
0x180015173  test    rbx, rbx
0x180015176  jz      short loc_180015198
0x180015178  or      eax, 0FFFFFFFFh
0x18001517b  lock xadd [rbx+18h], eax
0x180015180  sub     eax, 1
0x180015183  jnz     short loc_1800151A6
0x180015185  nop
0x180015186  call    WINRT_IMPL_GetProcessHeap
0x18001518b  mov     rcx, rax; hHeap
0x18001518e  mov     r8, rbx; lpMem
0x180015191  xor     edx, edx; dwFlags
0x180015193  call    WINRT_IMPL_HeapFree
0x180015198  xor     eax, eax
0x18001519a  jmp     short loc_1800151A0
0x18001519c  mov     eax, dword ptr [rsp+28h+lpMem]
0x1800151a0  add     rsp, 20h
0x1800151a4  pop     rbx
0x1800151a5  retn
0x1800151a6  test    eax, eax
0x1800151a8  jns     short loc_180015198
0x1800151aa  call    cs:__imp_abort
```
