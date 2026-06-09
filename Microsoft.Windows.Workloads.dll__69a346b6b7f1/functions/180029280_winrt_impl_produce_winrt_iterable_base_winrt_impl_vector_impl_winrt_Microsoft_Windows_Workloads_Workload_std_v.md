# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Microsoft::Windows::Workloads::Workload>>::GetMany(uint,void * *,uint *)

- ea: `0x180029280`
- end: `0x18002938e`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWorkload@Workloads@Windows@Microsoft@3@Ucollection_version@23@@winrt@@U?$IIterator@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `270`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64 *, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x1800101a0`
- `0x180029280`
- `0x180036f4c`
- `0x18003bed0`
- `0x18003c6e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Microsoft::Windows::Workloads::Workload>>::GetMany(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        _DWORD *a4)
{
  __int64 *v5; // rbx
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // r15
  __int64 *v11; // rdi
  __int64 v12; // rax
  __int64 v13; // r14
  int v14; // esi
  __int64 v15; // rcx
  _DWORD *v17; // rdx
  _DWORD v18[10]; // [rsp+0h] [rbp-78h] BYREF
  _BYTE pExceptionObject[80]; // [rsp+28h] [rbp-50h] BYREF

  v5 = a3;
  memset(a3, 0, 8LL * a2);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
  {
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v17 = v18;
      v17[8] = *(_DWORD *)winrt::to_hresult(v17 + 8);
      return v18[8];
    }
  }
  v10 = a1 + 24;
  if ( !a1 )
    v10 = 40;
  v11 = *(__int64 **)v10;
  v12 = a1 + 32;
  if ( !a1 )
    v12 = 48;
  v13 = (__int64)(*(_QWORD *)v12 - (_QWORD)v11) >> 3;
  if ( a2 < (unsigned int)v13 )
    LODWORD(v13) = a2;
  v14 = v13;
  if ( (_DWORD)v13 )
  {
    while ( 1 )
    {
      if ( v5 != v11 )
      {
        if ( *v5 )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v5);
        v15 = *v11;
        *v5 = *v11;
        if ( v15 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
      }
      ++v5;
      if ( !--v14 )
        break;
      ++v11;
    }
  }
  *(_QWORD *)v10 += 8LL * (unsigned int)v13;
  *a4 = v13;
  return 0;
}

```

## disassembly

```asm
0x180029280  push    rbx
0x180029282  push    rsi
0x180029283  push    rdi
0x180029284  push    r12
0x180029286  push    r13
0x180029288  push    r14
0x18002928a  push    r15
0x18002928c  sub     rsp, 40h
0x180029290  mov     r13, r9
0x180029293  mov     rbx, r8
0x180029296  mov     r12d, edx
0x180029299  mov     rsi, rcx
0x18002929c  mov     r8d, r12d
0x18002929f  shl     r8, 3; Size
0x1800292a3  xor     edx, edx; Val
0x1800292a5  mov     rcx, rbx; void *
0x1800292a8  call    memset
0x1800292ad  lea     rdx, [rsi+8]
0x1800292b1  mov     eax, 18h
0x1800292b6  test    rsi, rsi
0x1800292b9  cmovz   rdx, rax
0x1800292bd  lea     rax, [rsi+10h]
0x1800292c1  mov     ecx, 20h ; ' '
0x1800292c6  cmovz   rax, rcx
0x1800292ca  mov     rax, [rax]
0x1800292cd  mov     ecx, [rax+28h]
0x1800292d0  cmp     ecx, [rdx]
0x1800292d2  jnz     loc_180029371
0x1800292d8  lea     r15, [rsi+18h]
0x1800292dc  mov     eax, 28h ; '('
0x1800292e1  test    rsi, rsi
0x1800292e4  cmovz   r15, rax
0x1800292e8  mov     rdi, [r15]
0x1800292eb  lea     rax, [rsi+20h]
0x1800292ef  mov     ecx, 30h ; '0'
0x1800292f4  cmovz   rax, rcx
0x1800292f8  mov     r14, [rax]
0x1800292fb  sub     r14, rdi
0x1800292fe  sar     r14, 3
0x180029302  cmp     r12d, r14d
0x180029305  cmovb   r14d, r12d
0x180029309  mov     esi, r14d
0x18002930c  test    r14d, r14d
0x18002930f  jz      short loc_18002934B
0x180029311  cmp     rbx, rdi
0x180029314  jz      short loc_18002933C
0x180029316  cmp     qword ptr [rbx], 0
0x18002931a  jz      short loc_180029324
0x18002931c  mov     rcx, rbx
0x18002931f  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180029324  mov     rcx, [rdi]
0x180029327  mov     [rbx], rcx
0x18002932a  test    rcx, rcx
0x18002932d  jz      short loc_18002933C
0x18002932f  mov     rax, [rcx]
0x180029332  mov     rax, [rax+8]
0x180029336  call    cs:__guard_dispatch_icall_fptr
0x18002933c  add     rbx, 8
0x180029340  add     esi, 0FFFFFFFFh
0x180029343  jz      short loc_18002934B
0x180029345  add     rdi, 8
0x180029349  jmp     short loc_180029311
0x18002934b  mov     eax, r14d
0x18002934e  shl     rax, 3
0x180029352  add     [r15], rax
0x180029355  mov     [r13+0], r14d
0x180029359  xor     eax, eax
0x18002935b  jmp     short loc_180029361
0x18002935d  mov     eax, [rsp+78h+var_58]
0x180029361  add     rsp, 40h
0x180029365  pop     r15
0x180029367  pop     r14
0x180029369  pop     r13
0x18002936b  pop     r12
0x18002936d  pop     rdi
0x18002936e  pop     rsi
0x18002936f  pop     rbx
0x180029370  retn
0x180029371  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180029376  call    ??0hresult_changed_state@winrt@@QEAA@XZ; winrt::hresult_changed_state::hresult_changed_state(void)
0x18002937b  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x180029382  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180029387  call    _CxxThrowException
```
