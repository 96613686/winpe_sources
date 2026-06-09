# winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::Remove(void *)

- ea: `0x18000c010`
- end: `0x18000c111`
- name: `?Remove@?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAX@Z`
- size: `257`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000c010`
- `0x18000c890`
- `0x18000e420`
- `0x18000e4a0`
- `0x18000e5a0`
- `0x180010200`
- `0x180034ef0`
- `0x18003509c`
- `0x180036f4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::Remove(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rdx
  volatile signed __int32 *v3; // rsi
  __int64 v4; // rdi
  __int64 v5; // rcx
  __int64 v6; // rbx
  __int64 v7; // rax
  char *v8; // rbx
  _BYTE v10[16]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v11; // [rsp+40h] [rbp-48h]
  _BYTE pExceptionObject[24]; // [rsp+48h] [rbp-40h] BYREF
  __int64 v13; // [rsp+60h] [rbp-28h] BYREF

  v13 = a2;
  v2 = a1 - 16;
  if ( !a1 )
    v2 = 0;
  v3 = (volatile signed __int32 *)(v2 + 40);
  v4 = 0;
  if ( v2 != -40 )
    v4 = v2;
  std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
    v4 + 48,
    v10,
    &v13);
  v6 = v11;
  if ( *(_BYTE *)(v11 + 25) || (unsigned __int8)std::less<winrt::hstring>::operator()(v5, &v13, (__int64 *)(v11 + 32)) )
    v6 = *(_QWORD *)(v4 + 48);
  if ( v6 == *(_QWORD *)(v4 + 48) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  _InterlockedIncrement(v3);
  v7 = std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::_Extract(
         v4 + 48,
         v6);
  v8 = 0;
  if ( v7 )
    v8 = (char *)v7;
  if ( v8 )
  {
    std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>::`scalar deleting destructor'(v8 + 32);
    operator delete(v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18000c010  mov     [rsp+arg_10], rbx
0x18000c015  push    rsi
0x18000c016  push    rdi
0x18000c017  push    r14
0x18000c019  sub     rsp, 70h
0x18000c01d  mov     rax, cs:__security_cookie
0x18000c024  xor     rax, rsp
0x18000c027  mov     [rsp+88h+var_20], rax
0x18000c02c  mov     [rsp+88h+var_28], rdx
0x18000c031  lea     rdx, [rcx-10h]
0x18000c035  xor     r14d, r14d
0x18000c038  test    rcx, rcx
0x18000c03b  cmovz   rdx, r14
0x18000c03f  lea     rsi, [rdx+28h]
0x18000c043  xorps   xmm0, xmm0
0x18000c046  movups  [rsp+88h+var_68], xmm0
0x18000c04b  mov     qword ptr [rsp+88h+var_68], r14
0x18000c050  xor     eax, eax
0x18000c052  mov     byte ptr [rsp+88h+var_68+8], al
0x18000c056  mov     edi, r14d
0x18000c059  test    rsi, rsi
0x18000c05c  cmovnz  rdi, rdx
0x18000c060  lea     r8, [rsp+88h+var_28]
0x18000c065  lea     rdx, [rsp+88h+var_58]
0x18000c06a  lea     rcx, [rdi+30h]
0x18000c06e  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x18000c073  mov     rbx, [rsp+88h+var_48]
0x18000c078  cmp     [rbx+19h], r14b
0x18000c07c  jnz     short loc_18000C090
0x18000c07e  lea     r8, [rbx+20h]
0x18000c082  lea     rdx, [rsp+88h+var_28]
0x18000c087  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000c08c  test    al, al
0x18000c08e  jz      short loc_18000C094
0x18000c090  mov     rbx, [rdi+30h]
0x18000c094  cmp     rbx, [rdi+30h]
0x18000c098  jz      short loc_18000C0F4
0x18000c09a  lock inc dword ptr [rsi]
0x18000c09d  mov     rdx, rbx
0x18000c0a0  lea     rcx, [rdi+30h]
0x18000c0a4  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,std::_Iterator_base0>)
0x18000c0a9  mov     rbx, r14
0x18000c0ac  test    rax, rax
0x18000c0af  cmovnz  rbx, rax
0x18000c0b3  test    rbx, rbx
0x18000c0b6  jz      short loc_18000C0CE
0x18000c0b8  lea     rcx, [rbx+20h]
0x18000c0bc  call    ??_G?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@QEAAPEAXI@Z; std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>::`scalar deleting destructor'(uint)
0x18000c0c1  mov     edx, 30h ; '0'; unsigned __int64
0x18000c0c6  mov     rcx, rbx; void *
0x18000c0c9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000c0ce  xor     eax, eax
0x18000c0d0  jmp     short loc_18000C0D6
0x18000c0d2  mov     eax, dword ptr [rsp+88h+var_28]
0x18000c0d6  mov     rcx, [rsp+88h+var_20]
0x18000c0db  xor     rcx, rsp; StackCookie
0x18000c0de  call    __security_check_cookie
0x18000c0e3  mov     rbx, [rsp+88h+arg_10]
0x18000c0eb  add     rsp, 70h
0x18000c0ef  pop     r14
0x18000c0f1  pop     rdi
0x18000c0f2  pop     rsi
0x18000c0f3  retn
0x18000c0f4  lea     rcx, [rsp+88h+pExceptionObject]; this
0x18000c0f9  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x18000c0fe  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000c105  lea     rcx, [rsp+88h+pExceptionObject]; pExceptionObject
0x18000c10a  call    _CxxThrowException
```
