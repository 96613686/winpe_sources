# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::Append(void *)

- ea: `0x180027de0`
- end: `0x180027e6f`
- name: `?Append@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180027de0`
- `0x18002a740`
- `0x180034ef0`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::Append(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r8
  __int64 v3; // r9
  __int64 v4; // rbx
  _QWORD *v5; // rax
  __int64 v7; // [rsp+20h] [rbp-18h] BYREF

  v7 = a2;
  v2 = a1 - 16;
  v3 = 0;
  if ( !a1 )
    v2 = 0;
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 40));
  if ( v2 != -40 )
    v3 = v2;
  v4 = v3 + 48;
  v5 = *(_QWORD **)(v3 + 56);
  if ( v5 == *(_QWORD **)(v3 + 64) )
  {
    try
    {
      std::vector<winrt::Microsoft::Windows::Workloads::Workload>::_Emplace_reallocate<winrt::Microsoft::Windows::Workloads::Workload const &>(
        v3 + 48,
        *(_QWORD *)(v3 + 56),
        &v7);
    }
    catch ( ... )
    {
      return *(unsigned int *)winrt::to_hresult(&v7);
    }
  }
  else
  {
    *v5 = a2;
    if ( a2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    *(_QWORD *)(v4 + 8) += 8LL;
  }
  return 0;
}

```

## disassembly

```asm
0x180027de0  push    rbx
0x180027de2  sub     rsp, 30h
0x180027de6  mov     rax, cs:__security_cookie
0x180027ded  xor     rax, rsp
0x180027df0  mov     [rsp+38h+var_10], rax
0x180027df5  mov     [rsp+38h+var_18], rdx
0x180027dfa  lea     r8, [rcx-10h]
0x180027dfe  xor     r9d, r9d
0x180027e01  test    rcx, rcx
0x180027e04  cmovz   r8, r9
0x180027e08  lea     rax, [r8+28h]
0x180027e0c  lock inc dword ptr [rax]
0x180027e0f  test    rax, rax
0x180027e12  cmovnz  r9, r8
0x180027e16  lea     rbx, [r9+30h]
0x180027e1a  mov     rax, [rbx+8]
0x180027e1e  cmp     rax, [rbx+10h]
0x180027e22  jz      short loc_180027E43
0x180027e24  mov     [rax], rdx
0x180027e27  test    rdx, rdx
0x180027e2a  jz      short loc_180027E3C
0x180027e2c  mov     rax, [rdx]
0x180027e2f  mov     rcx, rdx
0x180027e32  mov     rax, [rax+8]
0x180027e36  call    cs:__guard_dispatch_icall_fptr
0x180027e3c  add     qword ptr [rbx+8], 8
0x180027e41  jmp     short loc_180027E53
0x180027e43  lea     r8, [rsp+38h+var_18]
0x180027e48  mov     rdx, rax
0x180027e4b  mov     rcx, rbx
0x180027e4e  call    ??$_Emplace_reallocate@AEBUWorkload@Workloads@Windows@Microsoft@winrt@@@?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@AEAAPEAUWorkload@Workloads@Windows@Microsoft@winrt@@QEAU23456@AEBU23456@@Z; std::vector<winrt::Microsoft::Windows::Workloads::Workload>::_Emplace_reallocate<winrt::Microsoft::Windows::Workloads::Workload const &>(winrt::Microsoft::Windows::Workloads::Workload * const,winrt::Microsoft::Windows::Workloads::Workload const &)
0x180027e53  xor     eax, eax
0x180027e55  jmp     short loc_180027E5B
0x180027e57  mov     eax, dword ptr [rsp+38h+var_18]
0x180027e5b  mov     rcx, [rsp+38h+var_10]
0x180027e60  xor     rcx, rsp; StackCookie
0x180027e63  call    __security_check_cookie
0x180027e68  add     rsp, 30h
0x180027e6c  pop     rbx
0x180027e6d  retn
```
