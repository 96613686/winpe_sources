# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::Workloads::Workload>>::GetMany(uint,uint,void * *,uint *)

- ea: `0x1800277c0`
- end: `0x1800278db`
- name: `?GetMany@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVectorView@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIIPEAPEAXPEAI@Z`
- size: `283`
- prototype: `__int64 __fastcall(__int64, unsigned int, unsigned int, __int64 *, unsigned int *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x1800277c0`
- `0x18003bed0`
- `0x18003c6e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::Workloads::Workload>>::GetMany(
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
  v10 = a1 - 24;
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
0x1800277c0  push    rbx
0x1800277c2  push    rdi
0x1800277c3  push    r12
0x1800277c5  push    r14
0x1800277c7  push    r15
0x1800277c9  sub     rsp, 20h
0x1800277cd  mov     r12, [rsp+48h+arg_20]
0x1800277d2  mov     rdi, rcx
0x1800277d5  mov     r15d, r8d
0x1800277d8  mov     rcx, r9; void *
0x1800277db  mov     r8d, r8d
0x1800277de  mov     rbx, r9
0x1800277e1  mov     r14d, edx
0x1800277e4  xor     edx, edx; Val
0x1800277e6  shl     r8, 3; Size
0x1800277ea  call    memset
0x1800277ef  xor     ecx, ecx
0x1800277f1  lea     rdx, [rdi-18h]
0x1800277f5  test    rdi, rdi
0x1800277f8  cmovz   rdx, rcx
0x1800277fc  lea     r9, [rdx+28h]
0x180027800  test    r9, r9
0x180027803  jz      short loc_18002780E
0x180027805  mov     rax, [rdx+38h]
0x180027809  mov     r8, rdx
0x18002780c  jmp     short loc_180027819
0x18002780e  mov     rax, ds:38h
0x180027816  mov     r8, rcx
0x180027819  sub     rax, [r8+30h]
0x18002781d  sar     rax, 3
0x180027821  cmp     r14d, eax
0x180027824  jnb     loc_1800278C8
0x18002782a  mov     [rsp+48h+arg_0], rbp
0x18002782f  mov     [rsp+48h+arg_8], rsi
0x180027834  test    r9, r9
0x180027837  jz      short loc_180027853
0x180027839  mov     rsi, [rdx+38h]
0x18002783d  sub     rsi, [rdx+30h]
0x180027841  sar     rsi, 3
0x180027845  sub     esi, r14d
0x180027848  cmp     r15d, esi
0x18002784b  cmovb   esi, r15d
0x18002784f  mov     ebp, esi
0x180027851  jmp     short loc_180027876
0x180027853  mov     rbp, ds:38h
0x18002785b  mov     rdx, rcx
0x18002785e  sub     rbp, ds:30h
0x180027866  sar     rbp, 3
0x18002786a  sub     ebp, r14d
0x18002786d  cmp     r15d, ebp
0x180027870  cmovb   ebp, r15d
0x180027874  mov     esi, ebp
0x180027876  mov     rax, [rdx+30h]
0x18002787a  lea     rdi, [rax+r14*8]
0x18002787e  test    esi, esi
0x180027880  jz      short loc_1800278BC
0x180027882  cmp     rbx, rdi
0x180027885  jz      short loc_1800278AD
0x180027887  cmp     qword ptr [rbx], 0
0x18002788b  jz      short loc_180027895
0x18002788d  mov     rcx, rbx
0x180027890  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180027895  mov     rcx, [rdi]
0x180027898  mov     [rbx], rcx
0x18002789b  test    rcx, rcx
0x18002789e  jz      short loc_1800278AD
0x1800278a0  mov     rax, [rcx]
0x1800278a3  mov     rax, [rax+8]
0x1800278a7  call    cs:__guard_dispatch_icall_fptr
0x1800278ad  add     rbx, 8
0x1800278b1  add     esi, 0FFFFFFFFh
0x1800278b4  jz      short loc_1800278BC
0x1800278b6  add     rdi, 8
0x1800278ba  jmp     short loc_180027882
0x1800278bc  mov     rsi, [rsp+48h+arg_8]
0x1800278c1  mov     ecx, ebp
0x1800278c3  mov     rbp, [rsp+48h+arg_0]
0x1800278c8  mov     [r12], ecx
0x1800278cc  xor     eax, eax
0x1800278ce  add     rsp, 20h
0x1800278d2  pop     r15
0x1800278d4  pop     r14
0x1800278d6  pop     r12
0x1800278d8  pop     rdi
0x1800278d9  pop     rbx
0x1800278da  retn
```
