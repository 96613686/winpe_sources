# winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::Workloads::Workload>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Windows::Workloads::Workload>>::NonDelegatingGetRuntimeClassName(void * *)

- ea: `0x18000df20`
- end: `0x18000df8d`
- name: `?NonDelegatingGetRuntimeClassName@?$root_implements@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@U?$IVectorView@UWorkload@Workloads@Windows@Microsoft@winrt@@@5673@U?$IIterable@UWorkload@Workloads@Windows@Microsoft@winrt@@@5673@@impl@winrt@@IEAAHPEAPEAX@Z`
- size: `109`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a400`
- `0x18000a6a0`
- `0x18000a850`
- `0x18000aa80`
- `0x180025af0`
- `0x180025f40`

## callees

- `0x18000df20`
- `0x180030ae5`
- `0x180030aeb`
- `0x18003bed0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000df85`
- `api-ms-win-crt-runtime-l1-1-0!abort` at `0x18000df85`

## pseudocode

```c
__int64 __fastcall winrt::impl::root_implements<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::Workloads::Workload>,winrt::Windows::Foundation::Collections::IIterable<winrt::Microsoft::Windows::Workloads::Workload>>::NonDelegatingGetRuntimeClassName(
        __int64 a1,
        _QWORD *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx
  int v5; // eax
  HANDLE ProcessHeap; // rax
  __int64 result; // rax
  LPVOID lpMem[3]; // [rsp+20h] [rbp-18h] BYREF

  try
  {
    v3 = (__int64 *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 40LL))(a1);
    v4 = *v3;
    *v3 = 0;
    *a2 = v4;
    if ( lpMem[0] )
    {
      v5 = _InterlockedDecrement((volatile signed __int32 *)lpMem[0] + 6);
      if ( v5 )
      {
        if ( v5 < 0 )
          abort();
      }
      else
      {
        ProcessHeap = WINRT_IMPL_GetProcessHeap();
        WINRT_IMPL_HeapFree(ProcessHeap, 0, lpMem[0]);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(lpMem);
  }
  return result;
}

```

## disassembly

```asm
0x18000df20  push    rbx
0x18000df22  sub     rsp, 30h
0x18000df26  mov     rbx, rdx
0x18000df29  mov     rax, [rcx]
0x18000df2c  lea     rdx, [rsp+38h+lpMem]
0x18000df31  mov     rax, [rax+28h]
0x18000df35  call    cs:__guard_dispatch_icall_fptr
0x18000df3b  mov     rcx, [rax]
0x18000df3e  mov     qword ptr [rax], 0
0x18000df45  mov     [rbx], rcx
0x18000df48  mov     rbx, [rsp+38h+lpMem]
0x18000df4d  test    rbx, rbx
0x18000df50  jz      short loc_18000DF73
0x18000df52  mov     eax, 0FFFFFFFFh
0x18000df57  lock xadd [rbx+18h], eax
0x18000df5c  sub     eax, 1
0x18000df5f  jnz     short loc_18000DF81
0x18000df61  call    WINRT_IMPL_GetProcessHeap
0x18000df66  mov     rcx, rax; hHeap
0x18000df69  mov     r8, rbx; lpMem
0x18000df6c  xor     edx, edx; dwFlags
0x18000df6e  call    WINRT_IMPL_HeapFree
0x18000df73  xor     eax, eax
0x18000df75  jmp     short loc_18000DF7B
0x18000df77  mov     eax, dword ptr [rsp+38h+lpMem]
0x18000df7b  add     rsp, 30h
0x18000df7f  pop     rbx
0x18000df80  retn
0x18000df81  test    eax, eax
0x18000df83  jns     short loc_18000DF73
0x18000df85  call    cs:__imp_abort
```
