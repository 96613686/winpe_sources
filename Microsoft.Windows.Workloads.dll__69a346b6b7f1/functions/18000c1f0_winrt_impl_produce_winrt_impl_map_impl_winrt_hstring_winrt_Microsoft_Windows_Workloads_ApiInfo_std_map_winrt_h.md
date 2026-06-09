# winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::HasKey(void *,bool *)

- ea: `0x18000c1f0`
- end: `0x18000c29a`
- name: `?HasKey@?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMap@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAXPEA_N@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000c1f0`
- `0x18000c890`
- `0x18000e420`
- `0x180034ef0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMap<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::HasKey(
        __int64 a1,
        __int64 a2,
        bool *a3)
{
  __int64 v3; // rdi
  __int64 v4; // rsi
  __int64 v6; // r14
  __int64 v7; // rcx
  __int64 v8; // rbx
  _BYTE v10[16]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v11; // [rsp+30h] [rbp-48h]
  __int64 v12; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  v12 = a2;
  v4 = a1 - 16;
  if ( !a1 )
    v4 = 0;
  v6 = 0;
  if ( v4 != -40 )
    v6 = v4;
  std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
    v6 + 48,
    v10,
    &v12);
  v8 = v11;
  if ( *(_BYTE *)(v11 + 25) || (unsigned __int8)std::less<winrt::hstring>::operator()(v7, &v12, (__int64 *)(v11 + 32)) )
    v8 = *(_QWORD *)(v6 + 48);
  if ( v4 != -40 )
    v3 = v4;
  *a3 = v8 != *(_QWORD *)(v3 + 48);
  return 0;
}

```

## disassembly

```asm
0x18000c1f0  mov     [rsp+arg_18], rbx
0x18000c1f5  push    rbp
0x18000c1f6  push    rsi
0x18000c1f7  push    rdi
0x18000c1f8  push    r14
0x18000c1fa  push    r15
0x18000c1fc  sub     rsp, 50h
0x18000c200  mov     rax, cs:__security_cookie
0x18000c207  xor     rax, rsp
0x18000c20a  mov     [rsp+78h+var_38], rax
0x18000c20f  xor     edi, edi
0x18000c211  mov     [rsp+78h+var_40], rdx
0x18000c216  test    rcx, rcx
0x18000c219  lea     rsi, [rcx-10h]
0x18000c21d  mov     r15, r8
0x18000c220  lea     rdx, [rsp+78h+var_58]
0x18000c225  cmovz   rsi, rdi
0x18000c229  lea     r8, [rsp+78h+var_40]
0x18000c22e  mov     r14d, edi
0x18000c231  lea     rbp, [rsi+28h]
0x18000c235  test    rbp, rbp
0x18000c238  cmovnz  r14, rsi
0x18000c23c  lea     rcx, [r14+30h]
0x18000c240  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x18000c245  mov     rbx, [rsp+78h+var_48]
0x18000c24a  cmp     [rbx+19h], dil
0x18000c24e  jnz     short loc_18000C262
0x18000c250  lea     r8, [rbx+20h]
0x18000c254  lea     rdx, [rsp+78h+var_40]
0x18000c259  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000c25e  test    al, al
0x18000c260  jz      short loc_18000C266
0x18000c262  mov     rbx, [r14+30h]
0x18000c266  test    rbp, rbp
0x18000c269  cmovnz  rdi, rsi
0x18000c26d  cmp     rbx, [rdi+30h]
0x18000c271  setnz   al
0x18000c274  mov     [r15], al
0x18000c277  xor     eax, eax
0x18000c279  mov     rcx, [rsp+78h+var_38]
0x18000c27e  xor     rcx, rsp; StackCookie
0x18000c281  call    __security_check_cookie
0x18000c286  mov     rbx, [rsp+78h+arg_18]
0x18000c28e  add     rsp, 50h
0x18000c292  pop     r15
0x18000c294  pop     r14
0x18000c296  pop     rdi
0x18000c297  pop     rsi
0x18000c298  pop     rbp
0x18000c299  retn
```
