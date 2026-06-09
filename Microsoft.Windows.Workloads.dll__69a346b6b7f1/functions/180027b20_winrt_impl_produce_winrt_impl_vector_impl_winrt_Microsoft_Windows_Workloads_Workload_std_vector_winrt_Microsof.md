# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::GetMany(uint,uint,void * *,uint *)

- ea: `0x180027b20`
- end: `0x180027c3b`
- name: `?GetMany@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIIPEAPEAXPEAI@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x180027b20`
- `0x18003bed0`
- `0x18003c6e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::GetMany(
        __int64 a1,
        unsigned int a2,
        unsigned int a3,
        __int64 *a4,
        unsigned int *a5)
{
  __int64 *v7; // rbx
  __int64 v8; // r14
  unsigned int v9; // ecx
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // r8
  unsigned int v13; // esi
  unsigned int v14; // ebp
  __int64 *v15; // rdi
  __int64 v16; // rcx

  v7 = a4;
  v8 = a2;
  memset(a4, 0, 8LL * a3);
  v9 = 0;
  v10 = a1 - 16;
  if ( !a1 )
    v10 = 0;
  if ( v10 == -40 )
  {
    v11 = MEMORY[0x38];
    v12 = 0;
  }
  else
  {
    v11 = *(_QWORD *)(v10 + 56);
    v12 = v10;
  }
  if ( (unsigned int)v8 < (unsigned int)((v11 - *(_QWORD *)(v12 + 48)) >> 3) )
  {
    if ( v10 == -40 )
    {
      v10 = 0;
      v14 = ((__int64)(MEMORY[0x38] - MEMORY[0x30]) >> 3) - v8;
      if ( a3 < v14 )
        v14 = a3;
      v13 = v14;
    }
    else
    {
      v13 = ((__int64)(*(_QWORD *)(v10 + 56) - *(_QWORD *)(v10 + 48)) >> 3) - v8;
      if ( a3 < v13 )
        v13 = a3;
      v14 = v13;
    }
    v15 = (__int64 *)(*(_QWORD *)(v10 + 48) + 8 * v8);
    if ( v13 )
    {
      while ( 1 )
      {
        if ( v7 != v15 )
        {
          if ( *v7 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v7);
          v16 = *v15;
          *v7 = *v15;
          if ( v16 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
        }
        ++v7;
        if ( !--v13 )
          break;
        ++v15;
      }
    }
    v9 = v14;
  }
  *a5 = v9;
  return 0;
}

```

## disassembly

```asm
0x180027b20  push    rbx
0x180027b22  push    rdi
0x180027b23  push    r12
0x180027b25  push    r14
0x180027b27  push    r15
0x180027b29  sub     rsp, 20h
0x180027b2d  mov     r12, [rsp+48h+arg_20]
0x180027b32  mov     rdi, rcx
0x180027b35  mov     r15d, r8d
0x180027b38  mov     rcx, r9; void *
0x180027b3b  mov     r8d, r8d
0x180027b3e  mov     rbx, r9
0x180027b41  mov     r14d, edx
0x180027b44  xor     edx, edx; Val
0x180027b46  shl     r8, 3; Size
0x180027b4a  call    memset
0x180027b4f  xor     ecx, ecx
0x180027b51  lea     rdx, [rdi-10h]
0x180027b55  test    rdi, rdi
0x180027b58  cmovz   rdx, rcx
0x180027b5c  lea     r9, [rdx+28h]
0x180027b60  test    r9, r9
0x180027b63  jz      short loc_180027B6E
0x180027b65  mov     rax, [rdx+38h]
0x180027b69  mov     r8, rdx
0x180027b6c  jmp     short loc_180027B79
0x180027b6e  mov     rax, ds:38h
0x180027b76  mov     r8, rcx
0x180027b79  sub     rax, [r8+30h]
0x180027b7d  sar     rax, 3
0x180027b81  cmp     r14d, eax
0x180027b84  jnb     loc_180027C28
0x180027b8a  mov     [rsp+48h+arg_0], rbp
0x180027b8f  mov     [rsp+48h+arg_8], rsi
0x180027b94  test    r9, r9
0x180027b97  jz      short loc_180027BB3
0x180027b99  mov     rsi, [rdx+38h]
0x180027b9d  sub     rsi, [rdx+30h]
0x180027ba1  sar     rsi, 3
0x180027ba5  sub     esi, r14d
0x180027ba8  cmp     r15d, esi
0x180027bab  cmovb   esi, r15d
0x180027baf  mov     ebp, esi
0x180027bb1  jmp     short loc_180027BD6
0x180027bb3  mov     rbp, ds:38h
0x180027bbb  mov     rdx, rcx
0x180027bbe  sub     rbp, ds:30h
0x180027bc6  sar     rbp, 3
0x180027bca  sub     ebp, r14d
0x180027bcd  cmp     r15d, ebp
0x180027bd0  cmovb   ebp, r15d
0x180027bd4  mov     esi, ebp
0x180027bd6  mov     rax, [rdx+30h]
0x180027bda  lea     rdi, [rax+r14*8]
0x180027bde  test    esi, esi
0x180027be0  jz      short loc_180027C1C
0x180027be2  cmp     rbx, rdi
0x180027be5  jz      short loc_180027C0D
0x180027be7  cmp     qword ptr [rbx], 0
0x180027beb  jz      short loc_180027BF5
0x180027bed  mov     rcx, rbx
0x180027bf0  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027bf5  mov     rcx, [rdi]
0x180027bf8  mov     [rbx], rcx
0x180027bfb  test    rcx, rcx
0x180027bfe  jz      short loc_180027C0D
0x180027c00  mov     rax, [rcx]
0x180027c03  mov     rax, [rax+8]
0x180027c07  call    cs:__guard_dispatch_icall_fptr
0x180027c0d  add     rbx, 8
0x180027c11  add     esi, 0FFFFFFFFh
0x180027c14  jz      short loc_180027C1C
0x180027c16  add     rdi, 8
0x180027c1a  jmp     short loc_180027BE2
0x180027c1c  mov     rsi, [rsp+48h+arg_8]
0x180027c21  mov     ecx, ebp
0x180027c23  mov     rbp, [rsp+48h+arg_0]
0x180027c28  mov     [r12], ecx
0x180027c2c  xor     eax, eax
0x180027c2e  add     rsp, 20h
0x180027c32  pop     r15
0x180027c34  pop     r14
0x180027c36  pop     r12
0x180027c38  pop     rdi
0x180027c39  pop     rbx
0x180027c3a  retn
```
