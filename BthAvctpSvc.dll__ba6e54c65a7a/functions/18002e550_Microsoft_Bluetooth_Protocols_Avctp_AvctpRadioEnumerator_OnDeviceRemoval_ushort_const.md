# Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::OnDeviceRemoval(ushort const *)

- ea: `0x18002e550`
- end: `0x18002e72a`
- name: `?OnDeviceRemoval@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@EEAAXPEBG@Z`
- size: `474`
- prototype: `void __fastcall(Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001dd0`
- `0x180004060`
- `0x18000fcf8`
- `0x180011a20`
- `0x1800142c8`
- `0x18001446c`
- `0x1800151ac`
- `0x1800151f4`
- `0x180019c68`
- `0x180019d20`
- `0x180025a48`
- `0x18002c734`
- `0x18002c760`
- `0x18002d400`
- `0x18002e550`
- `0x18002eb08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e586`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e586`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::OnDeviceRemoval(
        Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator *this,
        const unsigned __int16 *a2)
{
  char *v4; // rbx
  char v5; // dl
  __int64 **v6; // rbx
  __int64 *v7; // rsi
  __int64 v8; // rcx
  __int64 *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // rbx
  __int64 v14; // rax
  __int64 v15; // [rsp+50h] [rbp-29h] BYREF
  char *v16; // [rsp+58h] [rbp-21h] BYREF
  _BYTE v17[16]; // [rsp+68h] [rbp-11h] BYREF
  __int64 *v18; // [rsp+78h] [rbp-1h]
  _BYTE v19[32]; // [rsp+80h] [rbp+7h] BYREF

  v4 = (char *)this + 328;
  AcquireSRWLockExclusive((PSRWLOCK)this + 41);
  v16 = v4;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
    || (v5 = 1, *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u) )
  {
    v5 = 0;
  }
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_Sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      4,
      1,
      11,
      &WPP_530b9183aa8e352d9d3e79246b5dacd2_Traceguids,
      (__int64)a2,
      (char)this);
  v6 = (__int64 **)((char *)this + 336);
  std::wstring::wstring((__int64)v19, (__int64)a2);
  std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(
    (char *)this + 336,
    v17);
  v7 = v18;
  if ( !(unsigned __int8)std::_Tree<std::_Tmap_traits<std::wstring,_GUID,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::_Lower_bound_duplicate<std::wstring>(
                           v8,
                           v18,
                           v19) )
    v7 = *v6;
  std::wstring::_Tidy_deallocate(v19);
  if ( v7 != *v6 )
  {
    v9 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>>>::_Extract(
           (__int64 **)this + 42,
           v7);
    std::_Tree_node<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>,void *>>>(
      v10,
      (char *)v9);
  }
  std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<unsigned char>,long>>::reset((char *)this + 536);
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 480);
  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v12, *((_QWORD *)this + 62), a2) )
  {
    if ( *((_BYTE *)this + 513) )
    {
      v13 = **((_QWORD **)this + 44);
      v15 = v13;
      while ( !*(_BYTE *)(v13 + 25) )
      {
        v14 = std::wstring::wstring(v19);
        std::_Func_class<void,std::wstring,bool>::operator()(v13 + 48, v14, 0);
        std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(&v15);
        v13 = v15;
      }
      *((_BYTE *)this + 513) = 0;
    }
    *((_QWORD *)this + 62) = 0;
    *(_WORD *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 480) = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
}

```

## disassembly

```asm
0x18002e550  mov     [rsp-8+arg_10], rbx
0x18002e555  push    rbp
0x18002e556  push    rsi
0x18002e557  push    rdi
0x18002e558  push    r14
0x18002e55a  push    r15
0x18002e55c  lea     rbp, [rsp-37h]
0x18002e561  sub     rsp, 0B0h
0x18002e568  mov     rax, cs:__security_cookie
0x18002e56f  xor     rax, rsp
0x18002e572  mov     [rbp+57h+var_30], rax
0x18002e576  mov     r14, rdx
0x18002e579  mov     rdi, rcx
0x18002e57c  lea     rbx, [rcx+148h]
0x18002e583  mov     rcx, rbx; SRWLock
0x18002e586  call    cs:__imp_AcquireSRWLockExclusive
0x18002e58c  mov     [rbp+57h+var_78], rbx
0x18002e590  lea     rax, WPP_GLOBAL_Control
0x18002e597  xor     r15d, r15d
0x18002e59a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5a1  cmp     rcx, rax
0x18002e5a4  jz      short loc_18002E5B4
0x18002e5a6  test    byte ptr [rcx+1Ch], 1
0x18002e5aa  jz      short loc_18002E5B4
0x18002e5ac  cmp     byte ptr [rcx+19h], 4
0x18002e5b0  mov     dl, 1
0x18002e5b2  jnb     short loc_18002E5B7
0x18002e5b4  mov     dl, r15b
0x18002e5b7  lea     rax, WPP_RECORDER_INITIALIZED
0x18002e5be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18002e5c5  setnz   r8b
0x18002e5c9  test    dl, dl
0x18002e5cb  jnz     short loc_18002E5D2
0x18002e5cd  test    r8b, r8b
0x18002e5d0  jz      short loc_18002E609
0x18002e5d2  mov     qword ptr [rsp+0D0h+var_88], rdi; char
0x18002e5d7  mov     [rsp+0D0h+var_90], r14; __int64
0x18002e5dc  lea     rax, WPP_530b9183aa8e352d9d3e79246b5dacd2_Traceguids
0x18002e5e3  mov     [rsp+0D0h+MessageGuid], rax; MessageGuid
0x18002e5e8  mov     [rsp+0D0h+var_A0], 0Bh; __int16
0x18002e5ef  mov     [rsp+0D0h+var_A8], 1; int
0x18002e5f7  mov     [rsp+0D0h+var_B0], 4; char
0x18002e5fc  mov     r9, [rcx+28h]
0x18002e600  mov     rcx, [rcx+10h]; LoggerHandle
0x18002e604  call    WPP_RECORDER_AND_TRACE_SF_Sq
0x18002e609  lea     rbx, [rdi+150h]
0x18002e610  mov     rdx, r14
0x18002e613  lea     rcx, [rbp+57h+var_50]
0x18002e617  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002e61c  lea     r8, [rbp+57h+var_50]
0x18002e620  lea     rdx, [rbp+57h+var_68]
0x18002e624  mov     rcx, rbx
0x18002e627  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tset_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tset_traits<std::wstring,std::less<std::wstring>,std::allocator<std::wstring>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18002e62c  lea     r8, [rbp+57h+var_50]
0x18002e630  mov     rsi, [rbp+57h+var_58]
0x18002e634  mov     rdx, rsi
0x18002e637  call    ??$_Lower_bound_duplicate@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@@2@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U_GUID@@@std@@PEAX@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,_GUID,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,_GUID>>,0>>::_Lower_bound_duplicate<std::wstring>(std::_Tree_node<std::pair<std::wstring const,_GUID>,void *> * const,std::wstring const &)
0x18002e63c  test    al, al
0x18002e63e  jnz     short loc_18002E643
0x18002e640  mov     rsi, [rbx]
0x18002e643  lea     rcx, [rbp+57h+var_50]
0x18002e647  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002e64c  cmp     rsi, [rbx]
0x18002e64f  jz      short loc_18002E664
0x18002e651  mov     rdx, rsi
0x18002e654  mov     rcx, rbx
0x18002e657  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>>>,std::_Iterator_base0>)
0x18002e65c  mov     rdx, rax
0x18002e65f  call    ??$_Freenode@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@PEAX@std@@@std@@@?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@PEAX@std@@SAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@URadioSdpRegistrations@AvctpRadioEnumerator@Avctp@Protocols@Bluetooth@Microsoft@@@std@@PEAX@std@@@1@PEAU01@@Z; std::_Tree_node<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>,void *>::_Freenode<std::allocator<std::_Tree_node<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>,void *>> &,std::_Tree_node<std::pair<std::wstring const,Microsoft::Bluetooth::Protocols::Avctp::AvctpRadioEnumerator::RadioSdpRegistrations>,void *> *)
0x18002e664  lea     rcx, [rdi+218h]
0x18002e66b  call    ?reset@?$shared_ptr@V?$AsyncRequestWithUniqueResultAutoCancel@V?$vector@EV?$allocator@E@std@@@std@@J@Foundation@Bluetooth@Microsoft@@@std@@QEAAXXZ; std::shared_ptr<Microsoft::Bluetooth::Foundation::AsyncRequestWithUniqueResultAutoCancel<std::vector<uchar>,long>>::reset(void)
0x18002e670  lea     rsi, [rdi+1E0h]
0x18002e677  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002e67b  inc     r9
0x18002e67e  cmp     [r14+r9*2], r15w
0x18002e683  jnz     short loc_18002E67B
0x18002e685  mov     rcx, rsi
0x18002e688  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002e68d  mov     r8, r14
0x18002e690  mov     rdx, [rsi+10h]
0x18002e694  mov     rcx, rax
0x18002e697  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18002e69c  test    al, al
0x18002e69e  jz      short loc_18002E6FE
0x18002e6a0  cmp     [rdi+201h], r15b
0x18002e6a7  jz      short loc_18002E6EE
0x18002e6a9  mov     rbx, [rdi+160h]
0x18002e6b0  mov     rbx, [rbx]
0x18002e6b3  mov     [rbp+57h+var_80], rbx
0x18002e6b7  cmp     [rbx+19h], r15b
0x18002e6bb  jnz     short loc_18002E6E7
0x18002e6bd  mov     rdx, rsi
0x18002e6c0  lea     rcx, [rbp+57h+var_50]
0x18002e6c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18002e6c9  lea     rcx, [rbx+30h]
0x18002e6cd  xor     r8d, r8d
0x18002e6d0  mov     rdx, rax
0x18002e6d3  call    ??R?$_Func_class@XV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@std@@QEBAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@_N@Z; std::_Func_class<void,std::wstring,bool>::operator()(std::wstring,bool)
0x18002e6d8  lea     rcx, [rbp+57h+var_80]
0x18002e6dc  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@UChosenTransportContext@Audio@Bluetooth@Microsoft@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,Microsoft::Bluetooth::Audio::ChosenTransportContext>>>,std::_Iterator_base0>::operator++(void)
0x18002e6e1  mov     rbx, [rbp+57h+var_80]
0x18002e6e5  jmp     short loc_18002E6B7
0x18002e6e7  mov     [rdi+201h], r15b
0x18002e6ee  mov     [rsi+10h], r15
0x18002e6f2  mov     rcx, rsi
0x18002e6f5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002e6fa  mov     [rax], r15w
0x18002e6fe  lea     rcx, [rbp+57h+var_78]
0x18002e702  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e707  mov     rcx, [rbp+57h+var_30]
0x18002e70b  xor     rcx, rsp; StackCookie
0x18002e70e  call    __security_check_cookie
0x18002e713  mov     rbx, [rsp+0D0h+arg_10]
0x18002e71b  add     rsp, 0B0h
0x18002e722  pop     r15
0x18002e724  pop     r14
0x18002e726  pop     rdi
0x18002e727  pop     rsi
0x18002e728  pop     rbp
0x18002e729  retn
```
