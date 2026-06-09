# NgcCtnrCommon::KeyHandleCache::DeleteKey(unsigned __int64,ulong)

- ea: `0x18006f314`
- end: `0x18006f3c4`
- name: `?DeleteKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KK@Z`
- size: `176`
- prototype: `int(NgcCtnrCommon::KeyHandleCache *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019120`
- `0x180022bd0`
- `0x18004c148`

## callees

- `0x18000a168`
- `0x18000d62c`
- `0x18003ba28`
- `0x18006f314`
- `0x18006f93c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f327`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f327`
- `ncrypt!NCryptDeleteKey` at `0x18006f367`
- `ncrypt!NCryptDeleteKey` at `0x18006f367`

## string_xrefs

- `0x18006f378`: `onecore\ds\security\ngc\ctnrsvc\common\keyhandlecache.cpp`

## pseudocode

```c
__int64 __fastcall NgcCtnrCommon::KeyHandleCache::DeleteKey(RTL_SRWLOCK *this, NCRYPT_KEY_HANDLE a2)
{
  RTL_SRWLOCK *v4; // r14
  __int64 v5; // rax
  __int64 v6; // rdi
  SECURITY_STATUS v7; // eax
  unsigned int v8; // ebx
  int v10; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  __int64 i; // [rsp+40h] [rbp+8h] BYREF
  RTL_SRWLOCK *v13; // [rsp+58h] [rbp+20h] BYREF

  AcquireSRWLockExclusive(this);
  v4 = this + 1;
  v13 = this;
  v5 = *(_QWORD *)this[1].Ptr;
  for ( i = v5; ; v5 = i )
  {
    if ( *(_BYTE *)(v5 + 25) )
    {
      v8 = -2146893807;
      goto LABEL_9;
    }
    v6 = v5 + 32;
    if ( *(_QWORD *)(v5 + 72) == a2 )
      break;
    std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>>,std::_Iterator_base0>::operator++(&i);
  }
  v7 = NCryptDeleteKey(a2, 0);
  v8 = v7;
  if ( v7 >= 0 )
  {
    *(_QWORD *)(v6 + 40) = 0;
    std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::erase(
      v4,
      v6);
    v8 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8E,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\keyhandlecache.cpp",
      (const char *)(unsigned int)v7,
      v10);
  }
LABEL_9:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  return v8;
}

```

## disassembly

```asm
0x18006f314  mov     [rsp+arg_8], rbx
0x18006f319  push    rsi
0x18006f31a  push    rdi
0x18006f31b  push    r14; int
0x18006f31d  sub     rsp, 20h
0x18006f321  mov     rsi, rdx
0x18006f324  mov     rbx, rcx
0x18006f327  call    cs:__imp_AcquireSRWLockExclusive
0x18006f32d  lea     r14, [rbx+8]
0x18006f331  mov     [rsp+38h+arg_18], rbx
0x18006f336  mov     rax, [r14]
0x18006f339  mov     rax, [rax]
0x18006f33c  mov     [rsp+38h+arg_0], rax
0x18006f341  cmp     byte ptr [rax+19h], 0
0x18006f345  jnz     short loc_18006F3A5
0x18006f347  lea     rdi, [rax+20h]
0x18006f34b  cmp     [rdi+28h], rsi
0x18006f34f  jz      short loc_18006F362
0x18006f351  lea     rcx, [rsp+38h+arg_0]
0x18006f356  call    ??E?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>>,std::_Iterator_base0>::operator++(void)
0x18006f35b  mov     rax, [rsp+38h+arg_0]
0x18006f360  jmp     short loc_18006F341
0x18006f362  xor     edx, edx; dwFlags
0x18006f364  mov     rcx, rsi; hKey
0x18006f367  call    cs:__imp_NCryptDeleteKey
0x18006f36d  mov     ebx, eax
0x18006f36f  test    eax, eax
0x18006f371  jns     short loc_18006F38E
0x18006f373  mov     rcx, [rsp+38h]; this
0x18006f378  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006f37f  mov     r9d, eax; char *
0x18006f382  mov     edx, 8Eh; void *
0x18006f387  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f38c  jmp     short loc_18006F3AA
0x18006f38e  mov     rdx, rdi
0x18006f391  mov     qword ptr [rdi+28h], 0
0x18006f399  mov     rcx, r14
0x18006f39c  call    ?erase@?$_Tree@V?$_Tmap_traits@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@Z; std::_Tree<std::_Tmap_traits<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>,std::less<std::pair<unsigned __int64,std::wstring>>,std::allocator<std::pair<std::pair<unsigned __int64,std::wstring> const,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>>,0>>::erase(std::pair<unsigned __int64,std::wstring> const &)
0x18006f3a1  xor     ebx, ebx
0x18006f3a3  jmp     short loc_18006F3AA
0x18006f3a5  mov     ebx, 80090011h
0x18006f3aa  lea     rcx, [rsp+38h+arg_18]
0x18006f3af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f3b4  mov     eax, ebx
0x18006f3b6  mov     rbx, [rsp+38h+arg_8]
0x18006f3bb  add     rsp, 20h
0x18006f3bf  pop     r14
0x18006f3c1  pop     rdi
0x18006f3c2  pop     rsi
0x18006f3c3  retn
```
