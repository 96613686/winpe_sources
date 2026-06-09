# winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::Workloads::Workload>>::GetAt(uint,void * *)

- ea: `0x1800279e0`
- end: `0x180027a80`
- name: `?GetAt@?$produce@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@U?$IVectorView@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAX@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, unsigned int, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180010200`
- `0x1800279e0`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IVectorView<winrt::Microsoft::Windows::Workloads::Workload>>::GetAt(
        __int64 a1,
        unsigned int a2,
        _QWORD *a3)
{
  __int64 v4; // r9
  __int64 v5; // r10
  __int64 v6; // r8
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rbx
  _DWORD *v12; // rdx
  _DWORD v13[10]; // [rsp+0h] [rbp-48h] BYREF
  _BYTE pExceptionObject[32]; // [rsp+28h] [rbp-20h] BYREF

  v4 = 0;
  *a3 = 0;
  v5 = a1 - 24;
  if ( !a1 )
    v5 = 0;
  v6 = v5 + 40;
  if ( v5 == -40 )
  {
    v7 = MEMORY[0x38];
    v8 = 0;
  }
  else
  {
    v7 = *(_QWORD *)(v5 + 56);
    v8 = v5;
  }
  if ( a2 >= (unsigned int)((v7 - *(_QWORD *)(v8 + 48)) >> 3) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    try
    {
      throw (winrt::hresult_out_of_bounds *)pExceptionObject;
    }
    catch ( ... )
    {
      v12 = v13;
      v12[8] = *(_DWORD *)winrt::to_hresult(v12 + 8);
      return v13[8];
    }
  }
  if ( v6 )
    v4 = v5;
  v9 = *(_QWORD *)(v4 + 48);
  v10 = *(_QWORD *)(v9 + 8LL * a2);
  if ( v10 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v10 + 8LL))(*(_QWORD *)(v9 + 8LL * a2));
  *a3 = v10;
  return 0;
}

```

## disassembly

```asm
0x1800279e0  mov     [rsp+arg_0], rbx
0x1800279e5  push    rdi
0x1800279e6  sub     rsp, 40h
0x1800279ea  mov     rdi, r8
0x1800279ed  xor     r9d, r9d
0x1800279f0  mov     [r8], r9
0x1800279f3  lea     r10, [rcx-18h]
0x1800279f7  test    rcx, rcx
0x1800279fa  cmovz   r10, r9
0x1800279fe  lea     r8, [r10+28h]
0x180027a02  test    r8, r8
0x180027a05  jz      short loc_180027A10
0x180027a07  mov     rax, [r10+38h]
0x180027a0b  mov     rcx, r10
0x180027a0e  jmp     short loc_180027A1B
0x180027a10  mov     rax, ds:38h
0x180027a18  mov     rcx, r9
0x180027a1b  sub     rax, [rcx+30h]
0x180027a1f  sar     rax, 3
0x180027a23  cmp     edx, eax
0x180027a25  jnb     short loc_180027A63
0x180027a27  test    r8, r8
0x180027a2a  cmovnz  r9, r10
0x180027a2e  mov     ecx, edx
0x180027a30  mov     rax, [r9+30h]
0x180027a34  mov     rbx, [rax+rcx*8]
0x180027a38  test    rbx, rbx
0x180027a3b  jz      short loc_180027A4D
0x180027a3d  mov     rax, [rbx]
0x180027a40  mov     rcx, rbx
0x180027a43  mov     rax, [rax+8]
0x180027a47  call    cs:__guard_dispatch_icall_fptr
0x180027a4d  mov     [rdi], rbx
0x180027a50  xor     eax, eax
0x180027a52  jmp     short loc_180027A58
0x180027a54  mov     eax, [rsp+48h+var_28]
0x180027a58  mov     rbx, [rsp+48h+arg_0]
0x180027a5d  add     rsp, 40h
0x180027a61  pop     rdi
0x180027a62  retn
0x180027a63  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180027a68  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x180027a6d  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x180027a74  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180027a79  call    _CxxThrowException
```
