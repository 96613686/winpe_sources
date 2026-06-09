# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180010a60`
- end: `0x180010ae4`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180005000`
- `0x1800050a8`
- `0x180010a60`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  v5 = (a1 - 24) & -(__int64)(a1 != 0);
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
0x180010a60  mov     [rsp+arg_0], rbx
0x180010a65  push    rdi
0x180010a66  sub     rsp, 30h
0x180010a6a  lea     rax, [rcx-18h]
0x180010a6e  mov     rdi, rdx
0x180010a71  neg     rcx
0x180010a74  lea     rdx, [rsp+38h+var_18]
0x180010a79  mov     rbx, r8
0x180010a7c  sbb     rcx, rcx
0x180010a7f  and     rcx, rax
0x180010a82  mov     rax, [rcx]
0x180010a85  mov     rax, [rax+20h]
0x180010a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a8e  mov     eax, [rsp+38h+var_18]
0x180010a92  test    eax, eax
0x180010a94  jz      short loc_180010ACA
0x180010a96  mov     ecx, eax
0x180010a98  mov     [rdi], eax
0x180010a9a  shl     rcx, 4; cb
0x180010a9e  call    WINRT_IMPL_CoTaskMemAlloc
0x180010aa3  mov     [rbx], rax
0x180010aa6  test    rax, rax
0x180010aa9  jnz     short loc_180010AB2
0x180010aab  mov     eax, 8007000Eh
0x180010ab0  jmp     short loc_180010AD9
0x180010ab2  mov     r8d, [rsp+38h+var_18]
0x180010ab7  mov     rcx, rax; void *
0x180010aba  mov     rdx, [rsp+38h+Src]; Src
0x180010abf  shl     r8, 4; Size
0x180010ac3  call    memmove_0
0x180010ac8  jmp     short loc_180010AD7
0x180010aca  mov     dword ptr [rdi], 0
0x180010ad0  mov     qword ptr [rbx], 0
0x180010ad7  xor     eax, eax
0x180010ad9  mov     rbx, [rsp+38h+arg_0]
0x180010ade  add     rsp, 30h
0x180010ae2  pop     rdi
0x180010ae3  retn
```
