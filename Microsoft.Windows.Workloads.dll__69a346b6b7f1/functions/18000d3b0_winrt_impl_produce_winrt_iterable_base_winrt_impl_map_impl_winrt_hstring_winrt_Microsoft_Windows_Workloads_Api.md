# winrt::impl::produce<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::MoveNext(bool *)

- ea: `0x18000d3b0`
- end: `0x18000d447`
- name: `?MoveNext@?$produce@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEA_N@Z`
- size: `151`
- prototype: `__int64 __fastcall(__int64, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000d3b0`
- `0x18000f0f0`
- `0x1800101a0`
- `0x180036f4c`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::MoveNext(
        __int64 a1,
        bool *a2)
{
  __int64 v4; // r8
  __int64 v5; // rax
  __int64 v6; // r10
  __int64 v7; // r11
  __int64 *v9; // rdx
  __int64 v10; // [rsp+0h] [rbp-48h] BYREF
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF
  unsigned int v12; // [rsp+50h] [rbp+8h]

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
      v9 = &v10;
      *((_DWORD *)v9 + 20) = *(_DWORD *)winrt::to_hresult(v9 + 10);
      return v12;
    }
  }
  v6 = a1 + 24;
  if ( !a1 )
    v6 = 40;
  v7 = a1 + 32;
  if ( !a1 )
    v7 = 48;
  if ( *(_QWORD *)v6 != *(_QWORD *)v7 )
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,std::_Iterator_base0>::operator++(v6);
  *a2 = *(_QWORD *)v6 != *(_QWORD *)v7;
  return 0;
}

```

## disassembly

```asm
0x18000d3b0  push    rbx
0x18000d3b2  sub     rsp, 40h
0x18000d3b6  mov     rbx, rdx
0x18000d3b9  mov     r9, rcx
0x18000d3bc  lea     r8, [rcx+8]
0x18000d3c0  mov     eax, 18h
0x18000d3c5  test    rcx, rcx
0x18000d3c8  cmovz   r8, rax
0x18000d3cc  lea     rax, [rcx+10h]
0x18000d3d0  mov     ecx, 20h ; ' '
0x18000d3d5  cmovz   rax, rcx
0x18000d3d9  mov     rax, [rax]
0x18000d3dc  mov     ecx, [rax+28h]
0x18000d3df  cmp     ecx, [r8]
0x18000d3e2  jnz     short loc_18000D42A
0x18000d3e4  lea     r10, [r9+18h]
0x18000d3e8  mov     eax, 28h ; '('
0x18000d3ed  test    r9, r9
0x18000d3f0  cmovz   r10, rax
0x18000d3f4  lea     r11, [r9+20h]
0x18000d3f8  mov     eax, 30h ; '0'
0x18000d3fd  cmovz   r11, rax
0x18000d401  mov     rax, [r11]
0x18000d404  cmp     [r10], rax
0x18000d407  jz      short loc_18000D411
0x18000d409  mov     rcx, r10
0x18000d40c  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,std::_Iterator_base0>::operator++(void)
0x18000d411  mov     rax, [r11]
0x18000d414  cmp     [r10], rax
0x18000d417  setnz   al
0x18000d41a  mov     [rbx], al
0x18000d41c  xor     eax, eax
0x18000d41e  jmp     short loc_18000D424
0x18000d420  mov     eax, [rsp+48h+arg_0]
0x18000d424  add     rsp, 40h
0x18000d428  pop     rbx
0x18000d429  retn
0x18000d42a  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18000d42f  call    ??0hresult_changed_state@winrt@@QEAA@XZ; winrt::hresult_changed_state::hresult_changed_state(void)
0x18000d434  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18000d43b  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18000d440  call    _CxxThrowException
```
