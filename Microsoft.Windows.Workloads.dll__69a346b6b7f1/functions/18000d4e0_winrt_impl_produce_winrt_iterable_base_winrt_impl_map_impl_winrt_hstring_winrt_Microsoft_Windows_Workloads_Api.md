# winrt::impl::produce<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::get_Current(void * *)

- ea: `0x18000d4e0`
- end: `0x18000d635`
- name: `?get_Current@?$produce@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAPEAX@Z`
- size: `341`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x18000d4e0`
- `0x1800101a0`
- `0x180010200`
- `0x1800157c0`
- `0x180035060`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::get_Current(
        __int64 a1,
        _QWORD *a2)
{
  __int64 v3; // r8
  __int64 v4; // rax
  __int64 v5; // rax
  __int64 v6; // rdi
  __int64 v7; // rax
  struct winrt::impl::hstring_header *v8; // rdx
  _QWORD *v9; // rbx
  __int64 v10; // rcx
  struct winrt::impl::hstring_header *v11; // rax
  __int64 v12; // rcx
  _QWORD *v13; // rdi
  __int64 result; // rax
  _QWORD v15[4]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-48h] BYREF
  _BYTE v17[48]; // [rsp+58h] [rbp-30h] BYREF

  *a2 = 0;
  v3 = a1 + 8;
  if ( !a1 )
    v3 = 24;
  v4 = a1 + 16;
  if ( !a1 )
    v4 = 32;
  try
  {
    if ( *(_DWORD *)(*(_QWORD *)v4 + 40LL) != *(_DWORD *)v3 )
    {
      winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    v5 = a1 + 24;
    if ( !a1 )
      v5 = 40;
    v6 = *(_QWORD *)v5;
    v7 = a1 + 32;
    if ( !a1 )
      v7 = 48;
    if ( v6 == *(_QWORD *)v7 )
    {
      winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)v17);
      throw (winrt::hresult_out_of_bounds *)v17;
    }
    v9 = operator new(0x28u);
    v15[2] = v9;
    v15[3] = v15;
    v10 = *(_QWORD *)(v6 + 40);
    v15[0] = v10;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
    v11 = winrt::impl::duplicate_hstring(*(winrt::impl **)(v6 + 32), v8);
    v12 = v15[0];
    v15[0] = 0;
    v13 = v9 + 2;
    v9[2] = &winrt::impl::produce<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v9[1] = 1;
    v9[3] = v11;
    v9[4] = v12;
    *v9 = &winrt::impl::heap_implements<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable';
    if ( v15[0] )
      winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v15);
    if ( !v9 )
      v13 = 0;
    *a2 = v13;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(v15);
  }
  return result;
}

```

## disassembly

```asm
0x18000d4e0  mov     [rsp+arg_10], rbx
0x18000d4e5  push    rsi
0x18000d4e6  push    rdi
0x18000d4e7  push    r14
0x18000d4e9  sub     rsp, 70h
0x18000d4ed  mov     rsi, rdx
0x18000d4f0  mov     r9, rcx
0x18000d4f3  xor     r14d, r14d
0x18000d4f6  mov     [rdx], r14
0x18000d4f9  lea     r8, [rcx+8]
0x18000d4fd  mov     eax, 18h
0x18000d502  test    rcx, rcx
0x18000d505  cmovz   r8, rax
0x18000d509  lea     rax, [rcx+10h]
0x18000d50d  mov     ecx, 20h ; ' '
0x18000d512  cmovz   rax, rcx
0x18000d516  mov     rax, [rax]
0x18000d519  mov     ecx, [rax+28h]
0x18000d51c  cmp     ecx, [r8]
0x18000d51f  jnz     loc_18000D5FD
0x18000d525  lea     rax, [r9+18h]
0x18000d529  mov     edx, 28h ; '('
0x18000d52e  test    r9, r9
0x18000d531  cmovz   rax, rdx
0x18000d535  mov     rdi, [rax]
0x18000d538  lea     rax, [r9+20h]
0x18000d53c  mov     ecx, 30h ; '0'
0x18000d541  cmovz   rax, rcx
0x18000d545  cmp     rdi, [rax]
0x18000d548  jz      loc_18000D618
0x18000d54e  mov     rcx, rdx; Size
0x18000d551  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d556  mov     rbx, rax
0x18000d559  mov     [rsp+88h+var_58], rax
0x18000d55e  lea     rax, [rsp+88h+var_68]
0x18000d563  mov     [rsp+88h+var_50], rax
0x18000d568  mov     rcx, [rdi+28h]
0x18000d56c  mov     [rsp+88h+var_68], rcx
0x18000d571  test    rcx, rcx
0x18000d574  jz      short loc_18000D584
0x18000d576  mov     rax, [rcx]
0x18000d579  mov     rax, [rax+8]
0x18000d57d  call    cs:__guard_dispatch_icall_fptr
0x18000d583  nop
0x18000d584  mov     rcx, [rdi+20h]; this
0x18000d588  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000d58d  nop
0x18000d58e  mov     rcx, [rsp+88h+var_68]
0x18000d593  mov     [rsp+88h+var_68], r14
0x18000d598  lea     rdi, [rbx+10h]
0x18000d59c  lea     rdx, ??_7?$produce@U?$key_value_pair@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable'
0x18000d5a3  mov     [rdi], rdx
0x18000d5a6  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d5ad  mov     qword ptr [rbx+8], 1
0x18000d5b5  mov     [rbx+18h], rax
0x18000d5b9  mov     [rbx+20h], rcx
0x18000d5bd  lea     rax, ??_7?$heap_implements@U?$key_value_pair@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable'
0x18000d5c4  mov     [rbx], rax
0x18000d5c7  cmp     [rsp+88h+var_68], 0
0x18000d5cd  jz      short loc_18000D5DA
0x18000d5cf  lea     rcx, [rsp+88h+var_68]
0x18000d5d4  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d5d9  nop
0x18000d5da  test    rbx, rbx
0x18000d5dd  cmovz   rdi, r14
0x18000d5e1  mov     [rsi], rdi
0x18000d5e4  xor     eax, eax
0x18000d5e6  jmp     short loc_18000D5EC
0x18000d5e8  mov     eax, dword ptr [rsp+88h+var_68]
0x18000d5ec  mov     rbx, [rsp+88h+arg_10]
0x18000d5f4  add     rsp, 70h
0x18000d5f8  pop     r14
0x18000d5fa  pop     rdi
0x18000d5fb  pop     rsi
0x18000d5fc  retn
0x18000d5fd  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000d602  call    ??0hresult_changed_state@winrt@@QEAA@XZ; winrt::hresult_changed_state::hresult_changed_state(void)
0x18000d607  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18000d60e  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000d613  call    _CxxThrowException
0x18000d618  lea     rcx, [rsp+88h+var_30]; this
0x18000d61d  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x18000d622  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000d629  lea     rcx, [rsp+88h+var_30]; pExceptionObject
0x18000d62e  call    _CxxThrowException
```
