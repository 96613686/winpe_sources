# winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::HasKey(void *,bool *)

- ea: `0x18000bd90`
- end: `0x18000be3a`
- name: `?HasKey@?$produce@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IMapView@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHPEAXPEA_N@Z`
- size: `170`
- prototype: `__int64 __fastcall(__int64, __int64, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000bd90`
- `0x18000c890`
- `0x18000e420`
- `0x180034ef0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IMapView<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::HasKey(
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
  v4 = a1 - 24;
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
0x18000bd90  mov     [rsp+arg_18], rbx
0x18000bd95  push    rbp
0x18000bd96  push    rsi
0x18000bd97  push    rdi
0x18000bd98  push    r14
0x18000bd9a  push    r15
0x18000bd9c  sub     rsp, 50h
0x18000bda0  mov     rax, cs:__security_cookie
0x18000bda7  xor     rax, rsp
0x18000bdaa  mov     [rsp+78h+var_38], rax
0x18000bdaf  xor     edi, edi
0x18000bdb1  mov     [rsp+78h+var_40], rdx
0x18000bdb6  test    rcx, rcx
0x18000bdb9  lea     rsi, [rcx-18h]
0x18000bdbd  mov     r15, r8
0x18000bdc0  lea     rdx, [rsp+78h+var_58]
0x18000bdc5  cmovz   rsi, rdi
0x18000bdc9  lea     r8, [rsp+78h+var_40]
0x18000bdce  mov     r14d, edi
0x18000bdd1  lea     rbp, [rsi+28h]
0x18000bdd5  test    rbp, rbp
0x18000bdd8  cmovnz  r14, rsi
0x18000bddc  lea     rcx, [r14+30h]
0x18000bde0  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x18000bde5  mov     rbx, [rsp+78h+var_48]
0x18000bdea  cmp     [rbx+19h], dil
0x18000bdee  jnz     short loc_18000BE02
0x18000bdf0  lea     r8, [rbx+20h]
0x18000bdf4  lea     rdx, [rsp+78h+var_40]
0x18000bdf9  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000bdfe  test    al, al
0x18000be00  jz      short loc_18000BE06
0x18000be02  mov     rbx, [r14+30h]
0x18000be06  test    rbp, rbp
0x18000be09  cmovnz  rdi, rsi
0x18000be0d  cmp     rbx, [rdi+30h]
0x18000be11  setnz   al
0x18000be14  mov     [r15], al
0x18000be17  xor     eax, eax
0x18000be19  mov     rcx, [rsp+78h+var_38]
0x18000be1e  xor     rcx, rsp; StackCookie
0x18000be21  call    __security_check_cookie
0x18000be26  mov     rbx, [rsp+78h+arg_18]
0x18000be2e  add     rsp, 50h
0x18000be32  pop     r15
0x18000be34  pop     r14
0x18000be36  pop     rdi
0x18000be37  pop     rsi
0x18000be38  pop     rbp
0x18000be39  retn
```
