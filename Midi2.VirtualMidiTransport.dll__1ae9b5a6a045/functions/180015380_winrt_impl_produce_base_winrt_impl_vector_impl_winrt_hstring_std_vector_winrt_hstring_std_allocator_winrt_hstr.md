# winrt::impl::produce_base<winrt::impl::vector_impl<winrt::hstring,std::vector<winrt::hstring,std::allocator<winrt::hstring>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::hstring>,void>::GetIids(uint *,winrt::guid * *)

- ea: `0x180015380`
- end: `0x180015404`
- name: `?GetIids@?$produce_base@U?$vector_impl@Uhstring@winrt@@V?$vector@Uhstring@winrt@@V?$allocator@Uhstring@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IVector@Uhstring@winrt@@@Collections@Foundation@Windows@3@X@impl@winrt@@UEAAHPEAIPEAPEAUguid@3@@Z`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180004694`
- `0x180004724`
- `0x180015380`
- `0x180021010`

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
0x180015380  mov     [rsp+arg_0], rbx
0x180015385  push    rdi
0x180015386  sub     rsp, 30h
0x18001538a  lea     rax, [rcx-10h]
0x18001538e  mov     rdi, rdx
0x180015391  neg     rcx
0x180015394  lea     rdx, [rsp+38h+var_18]
0x180015399  mov     rbx, r8
0x18001539c  sbb     rcx, rcx
0x18001539f  and     rcx, rax
0x1800153a2  mov     rax, [rcx]
0x1800153a5  mov     rax, [rax+20h]
0x1800153a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ae  mov     eax, [rsp+38h+var_18]
0x1800153b2  test    eax, eax
0x1800153b4  jz      short loc_1800153EA
0x1800153b6  mov     ecx, eax
0x1800153b8  mov     [rdi], eax
0x1800153ba  shl     rcx, 4; cb
0x1800153be  call    WINRT_IMPL_CoTaskMemAlloc
0x1800153c3  mov     [rbx], rax
0x1800153c6  test    rax, rax
0x1800153c9  jnz     short loc_1800153D2
0x1800153cb  mov     eax, 8007000Eh
0x1800153d0  jmp     short loc_1800153F9
0x1800153d2  mov     r8d, [rsp+38h+var_18]
0x1800153d7  mov     rcx, rax; void *
0x1800153da  mov     rdx, [rsp+38h+Src]; Src
0x1800153df  shl     r8, 4; Size
0x1800153e3  call    memmove_0
0x1800153e8  jmp     short loc_1800153F7
0x1800153ea  mov     dword ptr [rdi], 0
0x1800153f0  mov     qword ptr [rbx], 0
0x1800153f7  xor     eax, eax
0x1800153f9  mov     rbx, [rsp+38h+arg_0]
0x1800153fe  add     rsp, 30h
0x180015402  pop     rdi
0x180015403  retn
```
