# winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload,std::allocator<winrt::Microsoft::Windows::Workloads::Workload>>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Microsoft::Windows::Workloads::Workload>>::get_Current(void * *)

- ea: `0x180029430`
- end: `0x1800294f8`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$vector_impl@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$vector@UWorkload@Workloads@Windows@Microsoft@winrt@@V?$allocator@UWorkload@Workloads@Windows@Microsoft@winrt@@@std@@@std@@Usingle_threaded_collection_base@impl@5@@impl@winrt@@UWorkload@Workloads@Windows@Microsoft@3@Ucollection_version@23@@winrt@@U?$IIterator@UWorkload@Workloads@Windows@Microsoft@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `200`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800101a0`
- `0x180010200`
- `0x180029430`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::vector_impl<winrt::Microsoft::Windows::Workloads::Workload,std::vector<winrt::Microsoft::Windows::Workloads::Workload>,winrt::impl::single_threaded_collection_base>,winrt::Microsoft::Windows::Workloads::Workload,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Microsoft::Windows::Workloads::Workload>>::get_Current(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 *v11; // rdx
  __int64 v12; // [rsp+0h] [rbp-58h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v14[32]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v15; // [rsp+60h] [rbp+8h]

  *a2 = 0;
  v4 = a1 + 8;
  if ( !a1 )
    v4 = 24;
  v5 = a1 + 16;
  if ( !a1 )
    v5 = 32;
  if ( *(_DWORD *)(*(_QWORD *)v5 + 40LL) != *(_DWORD *)v4 )
  {
    winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject);
    try
    {
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    catch ( ... )
    {
      v11 = &v12;
      *((_DWORD *)v11 + 24) = *(_DWORD *)winrt::to_hresult(v11 + 12);
      return v15;
    }
  }
  v6 = a1 + 24;
  if ( !a1 )
    v6 = 40;
  v7 = *(__int64 **)v6;
  v8 = a1 + 32;
  if ( !a1 )
    v8 = 48;
  if ( v7 == *(__int64 **)v8 )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)v14);
    throw (winrt::hresult_out_of_bounds *)v14;
  }
  v9 = *v7;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 8LL))(v9);
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x180029430  mov     [rsp+arg_8], rbx
0x180029435  push    rdi
0x180029436  sub     rsp, 50h
0x18002943a  mov     rdi, rdx
0x18002943d  mov     r9, rcx
0x180029440  xor     eax, eax
0x180029442  mov     [rdx], rax
0x180029445  lea     r8, [rcx+8]
0x180029449  mov     eax, 18h
0x18002944e  test    rcx, rcx
0x180029451  cmovz   r8, rax
0x180029455  lea     rax, [rcx+10h]
0x180029459  mov     ecx, 20h ; ' '
0x18002945e  cmovz   rax, rcx
0x180029462  mov     rax, [rax]
0x180029465  mov     ecx, [rax+28h]
0x180029468  cmp     ecx, [r8]
0x18002946b  jnz     short loc_1800294C0
0x18002946d  lea     rax, [r9+18h]
0x180029471  mov     ecx, 28h ; '('
0x180029476  test    r9, r9
0x180029479  cmovz   rax, rcx
0x18002947d  mov     rbx, [rax]
0x180029480  lea     rax, [r9+20h]
0x180029484  mov     ecx, 30h ; '0'
0x180029489  cmovz   rax, rcx
0x18002948d  cmp     rbx, [rax]
0x180029490  jz      short loc_1800294DB
0x180029492  mov     rbx, [rbx]
0x180029495  test    rbx, rbx
0x180029498  jz      short loc_1800294AA
0x18002949a  mov     rax, [rbx]
0x18002949d  mov     rcx, rbx
0x1800294a0  mov     rax, [rax+8]
0x1800294a4  call    cs:__guard_dispatch_icall_fptr
0x1800294aa  mov     [rdi], rbx
0x1800294ad  xor     eax, eax
0x1800294af  jmp     short loc_1800294B5
0x1800294b1  mov     eax, [rsp+58h+arg_0]
0x1800294b5  mov     rbx, [rsp+58h+arg_8]
0x1800294ba  add     rsp, 50h
0x1800294be  pop     rdi
0x1800294bf  retn
0x1800294c0  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1800294c5  call    ??0hresult_changed_state@winrt@@QEAA@XZ; winrt::hresult_changed_state::hresult_changed_state(void)
0x1800294ca  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x1800294d1  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800294d6  call    _CxxThrowException
0x1800294db  lea     rcx, [rsp+58h+var_20]; this
0x1800294e0  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x1800294e5  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x1800294ec  lea     rcx, [rsp+58h+var_20]; pExceptionObject
0x1800294f1  call    _CxxThrowException
```
