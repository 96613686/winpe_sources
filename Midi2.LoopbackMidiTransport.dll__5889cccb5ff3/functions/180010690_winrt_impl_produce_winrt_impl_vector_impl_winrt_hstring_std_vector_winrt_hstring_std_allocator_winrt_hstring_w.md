# winrt::impl::produce<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>>::GetAt(uint,void * *)

- ea: `0x180010690`
- end: `0x180010712`
- name: `?GetAt@?$produce@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `130`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000509c`
- `0x180005108`
- `0x180010690`
- `0x1800107a8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001070a`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18001070a`

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
0x180010690  push    rbx
0x180010692  sub     rsp, 20h
0x180010696  mov     rbx, r8
0x180010699  mov     rax, rcx
0x18001069c  mov     qword ptr [r8], 0
0x1800106a3  add     rcx, 18h
0x1800106a7  mov     r8d, 28h ; '('
0x1800106ad  test    rax, rax
0x1800106b0  cmovz   rcx, r8
0x1800106b4  mov     r8d, edx
0x1800106b7  lea     rdx, [rsp+28h+lpMem]
0x1800106bc  call    ?GetAt@?$vector_view_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@Ucollection_version@23@@winrt@@QEBA?AUhstring@2@I@Z; winrt::vector_view_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::impl::collection_version>::GetAt(uint)
0x1800106c1  mov     rcx, [rax]
0x1800106c4  mov     qword ptr [rax], 0
0x1800106cb  mov     [rbx], rcx
0x1800106ce  mov     rbx, [rsp+28h+lpMem]
0x1800106d3  test    rbx, rbx
0x1800106d6  jz      short loc_1800106F8
0x1800106d8  or      eax, 0FFFFFFFFh
0x1800106db  lock xadd [rbx+18h], eax
0x1800106e0  sub     eax, 1
0x1800106e3  jnz     short loc_180010706
0x1800106e5  nop
0x1800106e6  call    WINRT_IMPL_GetProcessHeap
0x1800106eb  mov     rcx, rax; hHeap
0x1800106ee  mov     r8, rbx; lpMem
0x1800106f1  xor     edx, edx; dwFlags
0x1800106f3  call    WINRT_IMPL_HeapFree
0x1800106f8  xor     eax, eax
0x1800106fa  jmp     short loc_180010700
0x1800106fc  mov     eax, dword ptr [rsp+28h+lpMem]
0x180010700  add     rsp, 20h
0x180010704  pop     rbx
0x180010705  retn
0x180010706  test    eax, eax
0x180010708  jns     short loc_1800106F8
0x18001070a  call    cs:__imp_abort
```
