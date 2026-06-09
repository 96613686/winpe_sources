# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IIterable<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x1800152f0`
- end: `0x180015374`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IIterable@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180004694`
- `0x180004724`
- `0x1800152f0`
- `0x180021010`

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
0x1800152f0  mov     [rsp+arg_0], rbx
0x1800152f5  push    rdi
0x1800152f6  sub     rsp, 30h
0x1800152fa  lea     rax, [rcx-20h]
0x1800152fe  mov     rdi, rdx
0x180015301  neg     rcx
0x180015304  lea     rdx, [rsp+38h+var_18]
0x180015309  mov     rbx, r8
0x18001530c  sbb     rcx, rcx
0x18001530f  and     rcx, rax
0x180015312  mov     rax, [rcx]
0x180015315  mov     rax, [rax+20h]
0x180015319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001531e  mov     eax, [rsp+38h+var_18]
0x180015322  test    eax, eax
0x180015324  jz      short loc_18001535A
0x180015326  mov     ecx, eax
0x180015328  mov     [rdi], eax
0x18001532a  shl     rcx, 4; cb
0x18001532e  call    WINRT_IMPL_CoTaskMemAlloc
0x180015333  mov     [rbx], rax
0x180015336  test    rax, rax
0x180015339  jnz     short loc_180015342
0x18001533b  mov     eax, 8007000Eh
0x180015340  jmp     short loc_180015369
0x180015342  mov     r8d, [rsp+38h+var_18]
0x180015347  mov     rcx, rax; void *
0x18001534a  mov     rdx, [rsp+38h+Src]; Src
0x18001534f  shl     r8, 4; Size
0x180015353  call    memmove_0
0x180015358  jmp     short loc_180015367
0x18001535a  mov     dword ptr [rdi], 0
0x180015360  mov     qword ptr [rbx], 0
0x180015367  xor     eax, eax
0x180015369  mov     rbx, [rsp+38h+arg_0]
0x18001536e  add     rsp, 30h
0x180015372  pop     rdi
0x180015373  retn
```
