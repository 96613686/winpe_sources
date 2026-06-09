# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::GetAt(uint,void * *)

- ea: `0x1800151c0`
- end: `0x180015242`
- name: `?GetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180004718`
- `0x180004784`
- `0x1800151c0`
- `0x180015248`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001523a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001523a`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::GetAt(
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
  LPVOID lpMem; // [rsp+30h] [rbp+8h] BYREF

  *a3 = 0;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 40;
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
  return 0;
}

```

## disassembly

```asm
0x1800151c0  push    rbx
0x1800151c2  sub     rsp, 20h
0x1800151c6  mov     rbx, r8
0x1800151c9  mov     rax, rcx
0x1800151cc  mov     qword ptr [r8], 0
0x1800151d3  add     rcx, 10h
0x1800151d7  mov     r8d, 28h ; '('
0x1800151dd  test    rax, rax
0x1800151e0  cmovz   rcx, r8
0x1800151e4  mov     r8d, edx
0x1800151e7  lea     rdx, [rsp+28h+lpMem]
0x1800151ec  call    ?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)
0x1800151f1  mov     rcx, [rax]
0x1800151f4  mov     qword ptr [rax], 0
0x1800151fb  mov     [rbx], rcx
0x1800151fe  mov     rbx, [rsp+28h+lpMem]
0x180015203  test    rbx, rbx
0x180015206  jz      short loc_180015228
0x180015208  or      eax, 0FFFFFFFFh
0x18001520b  lock xadd [rbx+18h], eax
0x180015210  sub     eax, 1
0x180015213  jnz     short loc_180015236
0x180015215  nop
0x180015216  call    WINRT_IMPL_GetProcessHeap
0x18001521b  mov     rcx, rax; hHeap
0x18001521e  mov     r8, rbx; lpMem
0x180015221  xor     edx, edx; dwFlags
0x180015223  call    WINRT_IMPL_HeapFree
0x180015228  xor     eax, eax
0x18001522a  jmp     short loc_180015230
0x18001522c  mov     eax, dword ptr [rsp+28h+lpMem]
0x180015230  add     rsp, 20h
0x180015234  pop     rbx
0x180015235  retn
0x180015236  test    eax, eax
0x180015238  jns     short loc_180015228
0x18001523a  call    cs:__imp_abort
```
