# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180010940`
- end: `0x1800109c4`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180005000`
- `0x1800050a8`
- `0x180010940`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  v5 = (a1 - 32) & -(__int64)(a1 != 0);
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v5 + 32LL))(v5, &v9);
  v6 = v9;
  if ( v9 )
  {
    *a2 = v9;
    v7 = WINRT_IMPL_CoTaskMemAlloc(16LL * v6);
    *a3 = v7;
    if ( !v7 )
      return 2147942414LL;
    memmove_0(v7, Src, 16LL * v9);
  }
  else
  {
    *a2 = 0;
    *a3 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x180010940  mov     [rsp+arg_0], rbx
0x180010945  push    rdi
0x180010946  sub     rsp, 30h
0x18001094a  lea     rax, [rcx-20h]
0x18001094e  mov     rdi, rdx
0x180010951  neg     rcx
0x180010954  lea     rdx, [rsp+38h+var_18]
0x180010959  mov     rbx, r8
0x18001095c  sbb     rcx, rcx
0x18001095f  and     rcx, rax
0x180010962  mov     rax, [rcx]
0x180010965  mov     rax, [rax+20h]
0x180010969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001096e  mov     eax, [rsp+38h+var_18]
0x180010972  test    eax, eax
0x180010974  jz      short loc_1800109AA
0x180010976  mov     ecx, eax
0x180010978  mov     [rdi], eax
0x18001097a  shl     rcx, 4; cb
0x18001097e  call    WINRT_IMPL_CoTaskMemAlloc
0x180010983  mov     [rbx], rax
0x180010986  test    rax, rax
0x180010989  jnz     short loc_180010992
0x18001098b  mov     eax, 8007000Eh
0x180010990  jmp     short loc_1800109B9
0x180010992  mov     r8d, [rsp+38h+var_18]
0x180010997  mov     rcx, rax; void *
0x18001099a  mov     rdx, [rsp+38h+Src]; Src
0x18001099f  shl     r8, 4; Size
0x1800109a3  call    memmove_0
0x1800109a8  jmp     short loc_1800109B7
0x1800109aa  mov     dword ptr [rdi], 0
0x1800109b0  mov     qword ptr [rbx], 0
0x1800109b7  xor     eax, eax
0x1800109b9  mov     rbx, [rsp+38h+arg_0]
0x1800109be  add     rsp, 30h
0x1800109c2  pop     rdi
0x1800109c3  retn
```
