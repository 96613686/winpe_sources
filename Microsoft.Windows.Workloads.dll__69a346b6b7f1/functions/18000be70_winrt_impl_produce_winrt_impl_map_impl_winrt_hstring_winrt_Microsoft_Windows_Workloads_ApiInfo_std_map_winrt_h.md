# winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::Lookup(void *,void * *)

- ea: `0x18000be70`
- end: `0x18000bf59`
- name: `?Lookup@?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAXPEAPEAX@Z`
- size: `233`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18000be70`
- `0x18000c890`
- `0x18000e420`
- `0x180010200`
- `0x180034ef0`
- `0x180036f4c`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::Lookup(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // r15
  __int64 v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rbx
  __int64 result; // rax
  unsigned int v11; // [rsp+20h] [rbp-78h] BYREF
  _BYTE v12[16]; // [rsp+28h] [rbp-70h] BYREF
  __int64 v13; // [rsp+38h] [rbp-60h]
  _BYTE pExceptionObject[24]; // [rsp+40h] [rbp-58h] BYREF
  __int64 v15; // [rsp+58h] [rbp-40h] BYREF

  v15 = a2;
  v4 = 0;
  *a3 = 0;
  v5 = a1 - 24;
  if ( !a1 )
    v5 = 0;
  v6 = 0;
  if ( v5 != -40 )
    v6 = v5;
  std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
    v6 + 48,
    v12,
    &v15);
  v8 = v13;
  if ( *(_BYTE *)(v13 + 25) || (unsigned __int8)std::less<winrt::hstring>::operator()(v7, &v15, (__int64 *)(v13 + 32)) )
    v8 = *(_QWORD *)(v6 + 48);
  if ( v5 != -40 )
    v4 = v5;
  if ( v8 == *(_QWORD *)(v4 + 48) )
  {
    winrt::hresult_out_of_bounds::hresult_out_of_bounds((winrt::hresult_out_of_bounds *)pExceptionObject);
    throw (winrt::hresult_out_of_bounds *)pExceptionObject;
  }
  v9 = *(_QWORD *)(v8 + 40);
  if ( v9 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 8LL))(*(_QWORD *)(v8 + 40));
  *a3 = v9;
  result = 0;
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      v11 = *(_DWORD *)winrt::to_hresult(&v11);
      result = v11;
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18000be70  mov     [rsp+arg_18], rbx
0x18000be75  push    rsi
0x18000be76  push    rdi
0x18000be77  push    r12
0x18000be79  push    r14
0x18000be7b  push    r15
0x18000be7d  sub     rsp, 70h
0x18000be81  mov     rax, cs:__security_cookie
0x18000be88  xor     rax, rsp
0x18000be8b  mov     [rsp+98h+var_38], rax
0x18000be90  mov     r14, r8
0x18000be93  mov     [rsp+98h+var_40], rdx
0x18000be98  xor     ebx, ebx
0x18000be9a  mov     [r8], rbx
0x18000be9d  lea     rsi, [rcx-18h]
0x18000bea1  test    rcx, rcx
0x18000bea4  cmovz   rsi, rbx
0x18000bea8  lea     r12, [rsi+28h]
0x18000beac  mov     r15d, ebx
0x18000beaf  test    r12, r12
0x18000beb2  cmovnz  r15, rsi
0x18000beb6  lea     r8, [rsp+98h+var_40]
0x18000bebb  lea     rdx, [rsp+98h+var_70]
0x18000bec0  lea     rcx, [r15+30h]
0x18000bec4  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x18000bec9  mov     rdi, [rsp+98h+var_60]
0x18000bece  cmp     [rdi+19h], bl
0x18000bed1  jnz     short loc_18000BEE5
0x18000bed3  lea     r8, [rdi+20h]
0x18000bed7  lea     rdx, [rsp+98h+var_40]
0x18000bedc  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000bee1  test    al, al
0x18000bee3  jz      short loc_18000BEE9
0x18000bee5  mov     rdi, [r15+30h]
0x18000bee9  test    r12, r12
0x18000beec  cmovnz  rbx, rsi
0x18000bef0  cmp     rdi, [rbx+30h]
0x18000bef4  jz      short loc_18000BF3C
0x18000bef6  mov     rbx, [rdi+28h]
0x18000befa  test    rbx, rbx
0x18000befd  jz      short loc_18000BF0F
0x18000beff  mov     rax, [rbx]
0x18000bf02  mov     rcx, rbx
0x18000bf05  mov     rax, [rax+8]
0x18000bf09  call    cs:__guard_dispatch_icall_fptr
0x18000bf0f  mov     [r14], rbx
0x18000bf12  xor     eax, eax
0x18000bf14  jmp     short loc_18000BF1A
0x18000bf16  mov     eax, [rsp+98h+var_78]
0x18000bf1a  mov     rcx, [rsp+98h+var_38]
0x18000bf1f  xor     rcx, rsp; StackCookie
0x18000bf22  call    __security_check_cookie
0x18000bf27  mov     rbx, [rsp+98h+arg_18]
0x18000bf2f  add     rsp, 70h
0x18000bf33  pop     r15
0x18000bf35  pop     r14
0x18000bf37  pop     r12
0x18000bf39  pop     rdi
0x18000bf3a  pop     rsi
0x18000bf3b  retn
0x18000bf3c  lea     rcx, [rsp+98h+pExceptionObject]; this
0x18000bf41  call    ??0hresult_out_of_bounds@winrt@@QEAA@XZ; winrt::hresult_out_of_bounds::hresult_out_of_bounds(void)
0x18000bf46  lea     rdx, _TI2?AUhresult_out_of_bounds@winrt@@; pThrowInfo
0x18000bf4d  lea     rcx, [rsp+98h+pExceptionObject]; pExceptionObject
0x18000bf52  call    _CxxThrowException
```
