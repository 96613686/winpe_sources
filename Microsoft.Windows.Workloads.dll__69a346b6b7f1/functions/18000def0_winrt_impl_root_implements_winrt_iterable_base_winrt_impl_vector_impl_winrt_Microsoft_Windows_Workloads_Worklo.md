# winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Microsoft::Windows::Workloads::Workload>>::NonDelegatingGetTrustLevel(winrt::Windows::Foundation::TrustLevel *)

- ea: `0x18000def0`
- end: `0x18000df17`
- name: `?NonDelegatingGetTrustLevel@?$root_implements@Uiterator@?$iterable_base@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWorkload@Workloads@Windows@Microsoft@3@Ucollection_version@23@@winrt@@U?$IIterator@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@IEAAHPEAW4TrustLevel@Foundation@Windows@3@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000a3e0`
- `0x18000a680`
- `0x18000a830`
- `0x18000aa60`
- `0x180025ad0`
- `0x180025f20`

## callees

- `0x18000def0`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Microsoft::Windows::Workloads::Workload>>::NonDelegatingGetTrustLevel(
        __int64 a1,
        _DWORD *a2)
{
  *a2 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
  return 0;
}

```

## disassembly

```asm
0x18000def0  push    rbx
0x18000def2  sub     rsp, 20h
0x18000def6  mov     rbx, rdx
0x18000def9  mov     rax, [rcx]
0x18000defc  mov     rax, [rax+10h]
0x18000df00  call    cs:__guard_dispatch_icall_fptr
0x18000df06  mov     [rbx], eax
0x18000df08  xor     eax, eax
0x18000df0a  jmp     short loc_18000DF10
0x18000df0c  mov     eax, [rsp+28h+arg_0]
0x18000df10  add     rsp, 20h
0x18000df14  pop     rbx
0x18000df15  retn
```
