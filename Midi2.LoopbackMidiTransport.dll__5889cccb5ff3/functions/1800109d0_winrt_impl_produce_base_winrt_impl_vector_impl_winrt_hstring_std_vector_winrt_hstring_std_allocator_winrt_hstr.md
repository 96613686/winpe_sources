# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x1800109d0`
- end: `0x180010a54`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180005000`
- `0x1800050a8`
- `0x1800109d0`
- `0x180032010`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,void>::GetIids(
        __int64 a1,
        unsigned int *a2,
        _QWORD *a3)
{
  __int64 v5; // rcx
  unsigned int v6; // eax
  void *v7; // rax
  unsigned int v9; // [rsp+20h] [rbp-18h] BYREF
  void *Src; // [rsp+28h] [rbp-10h]

  v5 = (a1 - 16) & -(__int64)(a1 != 0);
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
0x1800109d0  mov     [rsp+arg_0], rbx
0x1800109d5  push    rdi
0x1800109d6  sub     rsp, 30h
0x1800109da  lea     rax, [rcx-10h]
0x1800109de  mov     rdi, rdx
0x1800109e1  neg     rcx
0x1800109e4  lea     rdx, [rsp+38h+var_18]
0x1800109e9  mov     rbx, r8
0x1800109ec  sbb     rcx, rcx
0x1800109ef  and     rcx, rax
0x1800109f2  mov     rax, [rcx]
0x1800109f5  mov     rax, [rax+20h]
0x1800109f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109fe  mov     eax, [rsp+38h+var_18]
0x180010a02  test    eax, eax
0x180010a04  jz      short loc_180010A3A
0x180010a06  mov     ecx, eax
0x180010a08  mov     [rdi], eax
0x180010a0a  shl     rcx, 4; cb
0x180010a0e  call    WINRT_IMPL_CoTaskMemAlloc
0x180010a13  mov     [rbx], rax
0x180010a16  test    rax, rax
0x180010a19  jnz     short loc_180010A22
0x180010a1b  mov     eax, 8007000Eh
0x180010a20  jmp     short loc_180010A49
0x180010a22  mov     r8d, [rsp+38h+var_18]
0x180010a27  mov     rcx, rax; void *
0x180010a2a  mov     rdx, [rsp+38h+Src]; Src
0x180010a2f  shl     r8, 4; Size
0x180010a33  call    memmove_0
0x180010a38  jmp     short loc_180010A47
0x180010a3a  mov     dword ptr [rdi], 0
0x180010a40  mov     qword ptr [rbx], 0
0x180010a47  xor     eax, eax
0x180010a49  mov     rbx, [rsp+38h+arg_0]
0x180010a4e  add     rsp, 30h
0x180010a52  pop     rdi
0x180010a53  retn
```
