# winrt::map_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>::Insert(winrt::hstring const &,winrt::Microsoft::Windows::Workloads::ApiInfo const &)

- ea: `0x18000d7a0`
- end: `0x18000d961`
- name: `?Insert@?$map_base@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@Uhstring@3@UApiInfo@Workloads@Windows@Microsoft@3@@winrt@@QEAA_NAEBUhstring@2@AEBUApiInfo@Workloads@Windows@Microsoft@2@@Z`
- size: `449`
- prototype: `__int64 __fastcall(volatile signed __int32 *, winrt::impl **, __int64 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18000c120`

## callees

- `0x1800040a0`
- `0x18000c890`
- `0x18000d7a0`
- `0x18000db50`
- `0x18000e420`
- `0x1800101e0`
- `0x1800157c0`
- `0x180034ef0`
- `0x180035060`
- `0x18003bed0`

## pseudocode

```c
__int64 __fastcall winrt::map_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>::Insert(
        volatile signed __int32 *a1,
        winrt::impl **a2,
        __int64 *a3)
{
  __int64 v5; // rdi
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 *v8; // rbx
  __int64 v9; // rax
  unsigned __int8 v10; // di
  __int64 v11; // rcx
  __int64 v12; // rsi
  _QWORD *v13; // rbx
  struct winrt::impl::hstring_header *v14; // rdx
  __int64 v15; // rcx
  __int128 v17; // [rsp+20h] [rbp-88h] BYREF
  __int64 v18; // [rsp+30h] [rbp-78h]
  _QWORD *v19; // [rsp+38h] [rbp-70h]
  __int64 v20; // [rsp+40h] [rbp-68h]
  _BYTE v21[24]; // [rsp+48h] [rbp-60h] BYREF
  __int64 v22; // [rsp+60h] [rbp-48h] BYREF
  char v23; // [rsp+68h] [rbp-40h]

  v23 = 0;
  _InterlockedIncrement(a1);
  v5 = (__int64)(a1 + 2);
  if ( !a1 )
    v5 = 48;
  v6 = std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(
         v5,
         v21,
         a2);
  v17 = *(_OWORD *)v6;
  v20 = *(_QWORD *)(v6 + 16);
  if ( *(_BYTE *)(v20 + 25)
    || (unsigned __int8)std::less<winrt::hstring>::operator()(v7, (__int64 *)a2, (__int64 *)(v20 + 32)) )
  {
    if ( *(_QWORD *)(v5 + 8) == 0x555555555555555LL )
      std::_Throw_tree_length_error();
    v12 = *(_QWORD *)v5;
    v18 = v5;
    v13 = operator new(0x30u);
    v19 = v13;
    v13[4] = winrt::impl::duplicate_hstring(*a2, v14);
    v15 = *a3;
    v13[5] = *a3;
    if ( v15 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 8LL))(v15);
    *v13 = v12;
    v13[1] = v12;
    v13[2] = v12;
    *((_WORD *)v13 + 12) = 0;
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(
      (_QWORD *)v5,
      (__int64)&v17,
      (__int64)v13);
    v10 = 0;
  }
  else
  {
    if ( v23 )
    {
      if ( v22 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
      v23 = 0;
    }
    v8 = (__int64 *)(v20 + 40);
    v9 = *(_QWORD *)(v20 + 40);
    *(_QWORD *)(v20 + 40) = 0;
    v22 = v9;
    v23 = 1;
    v10 = 1;
    if ( v8 != a3 )
    {
      if ( *v8 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v8);
      v11 = *a3;
      *v8 = *a3;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( v23 && v22 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v22);
  return v10;
}

```

## disassembly

```asm
0x18000d7a0  mov     [rsp+arg_10], rbx
0x18000d7a5  push    rbp
0x18000d7a6  push    rsi
0x18000d7a7  push    rdi
0x18000d7a8  push    r14
0x18000d7aa  push    r15
0x18000d7ac  sub     rsp, 80h
0x18000d7b3  mov     rax, cs:__security_cookie
0x18000d7ba  xor     rax, rsp
0x18000d7bd  mov     [rsp+0A8h+var_38], rax
0x18000d7c2  mov     r14, r8
0x18000d7c5  mov     r15, rdx
0x18000d7c8  mov     [rsp+0A8h+var_40], 0
0x18000d7cd  lock inc dword ptr [rcx]
0x18000d7d0  lea     rdi, [rcx+8]
0x18000d7d4  mov     ebp, 30h ; '0'
0x18000d7d9  test    rcx, rcx
0x18000d7dc  cmovz   rdi, rbp
0x18000d7e0  mov     r8, rdx
0x18000d7e3  lea     rdx, [rsp+0A8h+var_60]
0x18000d7e8  mov     rcx, rdi
0x18000d7eb  call    ??$_Find_lower_bound@Uhstring@winrt@@@?$_Tree@V?$_Tmap_traits@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@PEAX@std@@@1@AEBUhstring@winrt@@@Z; std::_Tree<std::_Tmap_traits<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>,0>>::_Find_lower_bound<winrt::hstring>(winrt::hstring const &)
0x18000d7f0  movups  xmm0, xmmword ptr [rax]
0x18000d7f3  movups  [rsp+0A8h+var_88], xmm0
0x18000d7f8  movsd   xmm0, qword ptr [rax+10h]
0x18000d7fd  movsd   [rsp+0A8h+var_68], xmm0
0x18000d803  mov     rbx, [rsp+0A8h+var_68]
0x18000d808  cmp     byte ptr [rbx+19h], 0
0x18000d80c  jnz     loc_18000D892
0x18000d812  lea     r8, [rbx+20h]
0x18000d816  mov     rdx, r15
0x18000d819  call    ??R?$less@Uhstring@winrt@@@std@@QEBA_NAEBUhstring@winrt@@0@Z; std::less<winrt::hstring>::operator()(winrt::hstring const &,winrt::hstring const &)
0x18000d81e  test    al, al
0x18000d820  jnz     short loc_18000D892
0x18000d822  cmp     [rsp+0A8h+var_40], al
0x18000d826  jz      short loc_18000D83F
0x18000d828  cmp     [rsp+0A8h+var_48], 0
0x18000d82e  jz      short loc_18000D83A
0x18000d830  lea     rcx, [rsp+0A8h+var_48]
0x18000d835  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d83a  mov     [rsp+0A8h+var_40], 0
0x18000d83f  add     rbx, 28h ; '('
0x18000d843  mov     rax, [rbx]
0x18000d846  mov     qword ptr [rbx], 0
0x18000d84d  mov     [rsp+0A8h+var_48], rax
0x18000d852  mov     [rsp+0A8h+var_40], 1
0x18000d857  mov     dil, 1
0x18000d85a  cmp     rbx, r14
0x18000d85d  jz      loc_18000D91A
0x18000d863  cmp     qword ptr [rbx], 0
0x18000d867  jz      short loc_18000D871
0x18000d869  mov     rcx, rbx
0x18000d86c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d871  mov     rcx, [r14]
0x18000d874  mov     [rbx], rcx
0x18000d877  test    rcx, rcx
0x18000d87a  jz      loc_18000D91A
0x18000d880  mov     rax, [rcx]
0x18000d883  mov     rax, [rax+8]
0x18000d887  call    cs:__guard_dispatch_icall_fptr
0x18000d88d  jmp     loc_18000D91A
0x18000d892  mov     rax, 555555555555555h
0x18000d89c  cmp     [rdi+8], rax
0x18000d8a0  jz      loc_18000D95B
0x18000d8a6  mov     rsi, [rdi]
0x18000d8a9  mov     [rsp+0A8h+var_78], rdi
0x18000d8ae  mov     [rsp+0A8h+var_70], 0
0x18000d8b7  mov     rcx, rbp; Size
0x18000d8ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d8bf  mov     rbx, rax
0x18000d8c2  mov     [rsp+0A8h+var_70], rax
0x18000d8c7  mov     rcx, [r15]; this
0x18000d8ca  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000d8cf  mov     [rbx+20h], rax
0x18000d8d3  mov     rcx, [r14]
0x18000d8d6  mov     [rbx+28h], rcx
0x18000d8da  test    rcx, rcx
0x18000d8dd  jz      short loc_18000D8EC
0x18000d8df  mov     rax, [rcx]
0x18000d8e2  mov     rax, [rax+8]
0x18000d8e6  call    cs:__guard_dispatch_icall_fptr
0x18000d8ec  mov     [rbx], rsi
0x18000d8ef  mov     [rbx+8], rsi
0x18000d8f3  mov     [rbx+10h], rsi
0x18000d8f7  mov     word ptr [rbx+18h], 0
0x18000d8fd  movups  xmm0, [rsp+0A8h+var_88]
0x18000d902  movaps  [rsp+0A8h+var_88], xmm0
0x18000d907  mov     r8, rbx
0x18000d90a  lea     rdx, [rsp+0A8h+var_88]
0x18000d90f  mov     rcx, rdi
0x18000d912  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CB_KUWorkloadManager@Workloads@Windows@Microsoft@winrt@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>,void *> *>,std::_Tree_node<std::pair<unsigned __int64 const,winrt::Microsoft::Windows::Workloads::WorkloadManager>,void *> * const)
0x18000d917  xor     dil, dil
0x18000d91a  cmp     [rsp+0A8h+var_40], 0
0x18000d91f  jz      short loc_18000D933
0x18000d921  cmp     [rsp+0A8h+var_48], 0
0x18000d927  jz      short loc_18000D933
0x18000d929  lea     rcx, [rsp+0A8h+var_48]
0x18000d92e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d933  movzx   eax, dil
0x18000d937  mov     rcx, [rsp+0A8h+var_38]
0x18000d93c  xor     rcx, rsp; StackCookie
0x18000d93f  call    __security_check_cookie
0x18000d944  mov     rbx, [rsp+0A8h+arg_10]
0x18000d94c  add     rsp, 80h
0x18000d953  pop     r15
0x18000d955  pop     r14
0x18000d957  pop     rdi
0x18000d958  pop     rsi
0x18000d959  pop     rbp
0x18000d95a  retn
0x18000d95b  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
