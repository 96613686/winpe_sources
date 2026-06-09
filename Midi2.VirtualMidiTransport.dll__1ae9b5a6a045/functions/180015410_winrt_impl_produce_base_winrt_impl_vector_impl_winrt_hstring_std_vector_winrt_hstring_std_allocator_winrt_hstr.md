# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180015410`
- end: `0x180015494`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVectorView@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180004694`
- `0x180004724`
- `0x180015410`
- `0x180021010`

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
0x180015410  mov     [rsp+arg_0], rbx
0x180015415  push    rdi
0x180015416  sub     rsp, 30h
0x18001541a  lea     rax, [rcx-18h]
0x18001541e  mov     rdi, rdx
0x180015421  neg     rcx
0x180015424  lea     rdx, [rsp+38h+var_18]
0x180015429  mov     rbx, r8
0x18001542c  sbb     rcx, rcx
0x18001542f  and     rcx, rax
0x180015432  mov     rax, [rcx]
0x180015435  mov     rax, [rax+20h]
0x180015439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001543e  mov     eax, [rsp+38h+var_18]
0x180015442  test    eax, eax
0x180015444  jz      short loc_18001547A
0x180015446  mov     ecx, eax
0x180015448  mov     [rdi], eax
0x18001544a  shl     rcx, 4; cb
0x18001544e  call    WINRT_IMPL_CoTaskMemAlloc
0x180015453  mov     [rbx], rax
0x180015456  test    rax, rax
0x180015459  jnz     short loc_180015462
0x18001545b  mov     eax, 8007000Eh
0x180015460  jmp     short loc_180015489
0x180015462  mov     r8d, [rsp+38h+var_18]
0x180015467  mov     rcx, rax; void *
0x18001546a  mov     rdx, [rsp+38h+Src]; Src
0x18001546f  shl     r8, 4; Size
0x180015473  call    memmove_0
0x180015478  jmp     short loc_180015487
0x18001547a  mov     dword ptr [rdi], 0
0x180015480  mov     qword ptr [rbx], 0
0x180015487  xor     eax, eax
0x180015489  mov     rbx, [rsp+38h+arg_0]
0x18001548e  add     rsp, 30h
0x180015492  pop     rdi
0x180015493  retn
```
