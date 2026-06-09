# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::GetAt(uint,void * *)

- ea: `0x180028250`
- end: `0x1800282f0`
- name: `?GetAt@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVector@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180010200`
- `0x180028250`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVector<winrt::Microsoft::Windows::Workloads::Workload>>::GetAt(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v4; // r9
  __int64 v5; // r10
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rbx
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  v4 = 0;
  *a3 = 0;
  v5 = a1 - 16;
  if ( !a1 )
    v5 = 0;
  if ( v5 == -40 )
  {
    v6 = MEMORY[0x38];
    v7 = 0;
  }
  else
  {
    v6 = *(_QWORD *)(v5 + 56);
    v7 = v5;
  }
  if ( a2 >= (unsigned int)((v6 - *(_QWORD *)(v7 + 48)) >> 3) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  if ( v5 != -40 )
    v4 = v5;
  v8 = *(_QWORD *)(v4 + 48);
  v9 = *(_QWORD *)(v8 + 8LL * a2);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)(v8 + 8LL * a2));
  *a3 = v9;
  return 0;
}

```

## disassembly

```asm
0x180028250  mov     [rsp+arg_0], rbx
0x180028255  push    rdi
0x180028256  sub     rsp, 40h
0x18002825a  mov     rdi, r8
0x18002825d  xor     r9d, r9d
0x180028260  mov     [r8], r9
0x180028263  lea     r10, [rcx-10h]
0x180028267  test    rcx, rcx
0x18002826a  cmovz   r10, r9
0x18002826e  lea     r8, [r10+28h]
0x180028272  test    r8, r8
0x180028275  jz      short loc_180028280
0x180028277  mov     rax, [r10+38h]
0x18002827b  mov     rcx, r10
0x18002827e  jmp     short loc_18002828B
0x180028280  mov     rax, ds:38h
0x180028288  mov     rcx, r9
0x18002828b  sub     rax, [rcx+30h]
0x18002828f  sar     rax, 3
0x180028293  cmp     edx, eax
0x180028295  jnb     short loc_1800282D3
0x180028297  test    r8, r8
0x18002829a  cmovnz  r9, r10
0x18002829e  mov     ecx, edx
0x1800282a0  mov     rax, [r9+30h]
0x1800282a4  mov     rbx, [rax+rcx*8]
0x1800282a8  test    rbx, rbx
0x1800282ab  jz      short loc_1800282BD
0x1800282ad  mov     rax, [rbx]
0x1800282b0  mov     rcx, rbx
0x1800282b3  mov     rax, [rax+8]
0x1800282b7  call    cs:__guard_dispatch_icall_fptr
0x1800282bd  mov     [rdi], rbx
0x1800282c0  xor     eax, eax
0x1800282c2  jmp     short loc_1800282C8
0x1800282c4  mov     eax, [rsp+48h+var_28]
0x1800282c8  mov     rbx, [rsp+48h+arg_0]
0x1800282cd  add     rsp, 40h
0x1800282d1  pop     rdi
0x1800282d2  retn
0x1800282d3  lea     rcx, [rsp+48h+pExceptionObject]; this
0x1800282d8  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x1800282dd  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800282e4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x1800282e9  call    _CxxThrowException
```
