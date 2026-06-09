# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>>::GetAt(uint,void * *)

- ea: `0x180010720`
- end: `0x1800107a2`
- name: `?GetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000509c`
- `0x180005108`
- `0x180010720`
- `0x1800107a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001079a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001079a`

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
0x180010720  push    rbx
0x180010722  sub     rsp, 20h
0x180010726  mov     rbx, r8
0x180010729  mov     rax, rcx
0x18001072c  mov     qword ptr [r8], 0
0x180010733  add     rcx, 10h
0x180010737  mov     r8d, 28h ; '('
0x18001073d  test    rax, rax
0x180010740  cmovz   rcx, r8
0x180010744  mov     r8d, edx
0x180010747  lea     rdx, [rsp+28h+lpMem]
0x18001074c  call    ?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)
0x180010751  mov     rcx, [rax]
0x180010754  mov     qword ptr [rax], 0
0x18001075b  mov     [rbx], rcx
0x18001075e  mov     rbx, [rsp+28h+lpMem]
0x180010763  test    rbx, rbx
0x180010766  jz      short loc_180010788
0x180010768  or      eax, 0FFFFFFFFh
0x18001076b  lock xadd [rbx+18h], eax
0x180010770  sub     eax, 1
0x180010773  jnz     short loc_180010796
0x180010775  nop
0x180010776  call    WINRT_IMPL_GetProcessHeap
0x18001077b  mov     rcx, rax; hHeap
0x18001077e  mov     r8, rbx; lpMem
0x180010781  xor     edx, edx; dwFlags
0x180010783  call    WINRT_IMPL_HeapFree
0x180010788  xor     eax, eax
0x18001078a  jmp     short loc_180010790
0x18001078c  mov     eax, dword ptr [rsp+28h+lpMem]
0x180010790  add     rsp, 20h
0x180010794  pop     rbx
0x180010795  retn
0x180010796  test    eax, eax
0x180010798  jns     short loc_180010788
0x18001079a  call    cs:__imp_abort
```
