# winrt::impl::produce<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::less<winrt::hstring>,std::allocator<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::GetMany(uint,void * *,uint *)

- ea: `0x18000d1f0`
- end: `0x18000d3aa`
- name: `?GetMany@?$produce@Uiterator@?$iterable_base@U?$map_impl@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@V?$map@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@U?$less@Uhstring@winrt@@@std@@V?$allocator@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@8@@std@@Usingle_threaded_collection_base@impl@2@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@Ucollection_version@23@@winrt@@U?$IIterator@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@Collections@Foundation@Windows@3@@impl@winrt@@UEAAHIPEAPEAXPEAI@Z`
- size: `442`
- prototype: `__int64 __fastcall(__int64, unsigned int, char *, _DWORD *)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x1800040a0`
- `0x18000d1f0`
- `0x18000f0f0`
- `0x1800101a0`
- `0x1800157c0`
- `0x180035060`
- `0x180036f4c`
- `0x18003bed0`
- `0x18003c6e0`

## pseudocode

```c
__int64 __fastcall winrt::impl::produce<winrt::iterable_base<winrt::impl::map_impl<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo,std::map<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::single_threaded_collection_base>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>,winrt::impl::collection_version>::iterator,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::GetMany(
        __int64 a1,
        unsigned int a2,
        char *a3,
        _DWORD *a4)
{
  int v6; // r12d
  size_t v7; // rdi
  __int64 v8; // rdx
  __int64 v9; // rax
  char *i; // rbx
  __int64 v11; // r14
  __int64 v12; // rdi
  __int64 v13; // rax
  struct winrt::impl::hstring_header *v14; // rdx
  _QWORD *v15; // rsi
  __int64 v16; // rcx
  struct winrt::impl::hstring_header *v17; // rax
  __int64 v18; // rcx
  __int64 result; // rax
  __int64 v20; // [rsp+20h] [rbp-88h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-80h] BYREF
  size_t v22; // [rsp+30h] [rbp-78h]
  _DWORD *v23; // [rsp+38h] [rbp-70h]
  _QWORD *v24; // [rsp+48h] [rbp-60h]
  __int64 *v25; // [rsp+50h] [rbp-58h]
  _BYTE pExceptionObject[80]; // [rsp+58h] [rbp-50h] BYREF

  v23 = a4;
  v6 = 0;
  LODWORD(v20) = 0;
  v7 = 8LL * a2;
  v22 = v7;
  memset(a3, 0, v7);
  v8 = a1 + 8;
  if ( !a1 )
    v8 = 24;
  v9 = a1 + 16;
  if ( !a1 )
    v9 = 32;
  try
  {
    if ( *(_DWORD *)(*(_QWORD *)v9 + 40LL) != *(_DWORD *)v8 )
    {
      winrt::hresult_changed_state::hresult_changed_state((winrt::hresult_changed_state *)pExceptionObject);
      throw (winrt::hresult_changed_state *)pExceptionObject;
    }
    for ( i = a3; i < &a3[v7]; i += 8 )
    {
      v11 = a1 + 24;
      if ( !a1 )
        v11 = 40;
      v12 = *(_QWORD *)v11;
      v13 = a1 + 32;
      if ( !a1 )
        v13 = 48;
      if ( v12 == *(_QWORD *)v13 )
        break;
      v15 = operator new(0x28u);
      v24 = v15;
      v25 = &v20;
      v16 = *(_QWORD *)(v12 + 40);
      v20 = v16;
      if ( v16 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 8LL))(v16);
      v17 = winrt::impl::duplicate_hstring(*(winrt::impl **)(v12 + 32), v14);
      v18 = v20;
      v20 = 0;
      v15[2] = &winrt::impl::produce<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable';
      _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
      v15[1] = 1;
      v15[3] = v17;
      v15[4] = v18;
      *v15 = &winrt::impl::heap_implements<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable';
      if ( v20 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v20);
      v21 = v15 + 2;
      v6 |= 3u;
      if ( i == (char *)&v21 )
      {
        if ( v15 != (_QWORD *)-16LL )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(&v21);
      }
      else
      {
        if ( *(_QWORD *)i )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(i);
        *(_QWORD *)i = v15 + 2;
      }
      std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,std::_Iterator_base0>::operator++(v11);
      v7 = v22;
    }
    *v23 = (i - a3) >> 3;
    result = 0;
  }
  catch ( ... )
  {
    return *(unsigned int *)winrt::to_hresult(&v20);
  }
  return result;
}

```

## disassembly

```asm
0x18000d1f0  push    rbx
0x18000d1f2  push    rsi
0x18000d1f3  push    rdi
0x18000d1f4  push    r12
0x18000d1f6  push    r13
0x18000d1f8  push    r14
0x18000d1fa  push    r15
0x18000d1fc  sub     rsp, 70h
0x18000d200  mov     [rsp+0A8h+var_70], r9
0x18000d205  mov     r13, r8
0x18000d208  mov     r15, rcx
0x18000d20b  xor     r12d, r12d
0x18000d20e  mov     dword ptr [rsp+0A8h+var_88], r12d
0x18000d213  mov     edi, edx
0x18000d215  shl     rdi, 3
0x18000d219  mov     [rsp+0A8h+var_78], rdi
0x18000d21e  mov     r8, rdi; Size
0x18000d221  xor     edx, edx; Val
0x18000d223  mov     rcx, r13; void *
0x18000d226  call    memset
0x18000d22b  lea     rdx, [r15+8]
0x18000d22f  mov     eax, 18h
0x18000d234  test    r15, r15
0x18000d237  cmovz   rdx, rax
0x18000d23b  lea     rax, [r15+10h]
0x18000d23f  mov     ecx, 20h ; ' '
0x18000d244  cmovz   rax, rcx
0x18000d248  mov     rax, [rax]
0x18000d24b  mov     ecx, [rax+28h]
0x18000d24e  cmp     ecx, [rdx]
0x18000d250  jnz     loc_18000D38D
0x18000d256  mov     rbx, r13
0x18000d259  mov     edx, 30h ; '0'
0x18000d25e  mov     ecx, 28h ; '('; Size
0x18000d263  lea     rax, [rdi+r13]
0x18000d267  cmp     rbx, rax
0x18000d26a  jnb     loc_18000D367
0x18000d270  lea     r14, [r15+18h]
0x18000d274  test    r15, r15
0x18000d277  cmovz   r14, rcx
0x18000d27b  mov     rdi, [r14]
0x18000d27e  lea     rax, [r15+20h]
0x18000d282  cmovz   rax, rdx
0x18000d286  cmp     rdi, [rax]
0x18000d289  jz      loc_18000D367
0x18000d28f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d294  mov     rsi, rax
0x18000d297  mov     [rsp+0A8h+var_60], rax
0x18000d29c  lea     rax, [rsp+0A8h+var_88]
0x18000d2a1  mov     [rsp+0A8h+var_58], rax
0x18000d2a6  mov     rcx, [rdi+28h]
0x18000d2aa  mov     [rsp+0A8h+var_88], rcx
0x18000d2af  test    rcx, rcx
0x18000d2b2  jz      short loc_18000D2C2
0x18000d2b4  mov     rax, [rcx]
0x18000d2b7  mov     rax, [rax+8]
0x18000d2bb  call    cs:__guard_dispatch_icall_fptr
0x18000d2c1  nop
0x18000d2c2  mov     rcx, [rdi+20h]; this
0x18000d2c6  call    ?duplicate_hstring@impl@winrt@@YAPEAUhstring_header@12@PEAU312@@Z; winrt::impl::duplicate_hstring(winrt::impl::hstring_header *)
0x18000d2cb  nop
0x18000d2cc  mov     rcx, [rsp+0A8h+var_88]
0x18000d2d1  mov     [rsp+0A8h+var_88], 0
0x18000d2da  lea     rdi, [rsi+10h]
0x18000d2de  lea     rdx, ??_7?$produce@U?$key_value_pair@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@3@@impl@winrt@@6B@; const winrt::impl::produce<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>,winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>::`vftable'
0x18000d2e5  mov     [rdi], rdx
0x18000d2e8  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000d2ef  mov     qword ptr [rsi+8], 1
0x18000d2f7  mov     [rsi+18h], rax
0x18000d2fb  mov     [rsi+20h], rcx
0x18000d2ff  lea     rax, ??_7?$heap_implements@U?$key_value_pair@U?$IKeyValuePair@Uhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@Collections@Foundation@Windows@winrt@@@impl@winrt@@@impl@winrt@@6B@; const winrt::impl::heap_implements<winrt::impl::key_value_pair<winrt::Windows::Foundation::Collections::IKeyValuePair<winrt::hstring,winrt::Microsoft::Windows::Workloads::ApiInfo>>>::`vftable'
0x18000d306  mov     [rsi], rax
0x18000d309  cmp     [rsp+0A8h+var_88], 0
0x18000d30f  jz      short loc_18000D31C
0x18000d311  lea     rcx, [rsp+0A8h+var_88]
0x18000d316  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d31b  nop
0x18000d31c  mov     [rsp+0A8h+var_80], rdi
0x18000d321  or      r12d, 3
0x18000d325  lea     rax, [rsp+0A8h+var_80]
0x18000d32a  cmp     rbx, rax
0x18000d32d  jz      short loc_18000D342
0x18000d32f  cmp     qword ptr [rbx], 0
0x18000d333  jz      short loc_18000D33D
0x18000d335  mov     rcx, rbx
0x18000d338  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d33d  mov     [rbx], rdi
0x18000d340  jmp     short loc_18000D351
0x18000d342  test    rdi, rdi
0x18000d345  jz      short loc_18000D351
0x18000d347  lea     rcx, [rsp+0A8h+var_80]
0x18000d34c  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18000d351  add     rbx, 8
0x18000d355  mov     rcx, r14
0x18000d358  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBUhstring@winrt@@UApiInfo@Workloads@Windows@Microsoft@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<winrt::hstring const,winrt::Microsoft::Windows::Workloads::ApiInfo>>>,std::_Iterator_base0>::operator++(void)
0x18000d35d  mov     rdi, [rsp+0A8h+var_78]
0x18000d362  jmp     loc_18000D259
0x18000d367  sub     rbx, r13
0x18000d36a  sar     rbx, 3
0x18000d36e  mov     rax, [rsp+0A8h+var_70]
0x18000d373  mov     [rax], ebx
0x18000d375  xor     eax, eax
0x18000d377  jmp     short loc_18000D37D
0x18000d379  mov     eax, dword ptr [rsp+0A8h+var_88]
0x18000d37d  add     rsp, 70h
0x18000d381  pop     r15
0x18000d383  pop     r14
0x18000d385  pop     r13
0x18000d387  pop     r12
0x18000d389  pop     rdi
0x18000d38a  pop     rsi
0x18000d38b  pop     rbx
0x18000d38c  retn
0x18000d38d  lea     rcx, [rsp+0A8h+pExceptionObject]; this
0x18000d392  call    ??0hresult_changed_state@winrt@@QEAA@XZ; winrt::hresult_changed_state::hresult_changed_state(void)
0x18000d397  lea     rdx, _TI2?AUhresult_changed_state@winrt@@; pThrowInfo
0x18000d39e  lea     rcx, [rsp+0A8h+pExceptionObject]; pExceptionObject
0x18000d3a3  call    _CxxThrowException
```
