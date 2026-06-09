# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::DeleteConsent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004941c`
- end: `0x180049578`
- name: `?DeleteConsent@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z`
- size: `348`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x180049580`
- `0x180049704`
- `0x180049808`
- `0x18004a788`
- `0x18004ac88`

## callees

- `0x1800094c0`
- `0x180016d54`
- `0x18001c3b4`
- `0x1800257a4`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x1800473fc`
- `0x18004941c`
- `0x18004e9ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800494fd`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800494fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180049517`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180049517`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::DeleteConsent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdx
  __int64 v12; // rax
  const WCHAR *v13; // rax
  unsigned int v14; // eax
  HKEY hKey; // [rsp+20h] [rbp-40h] BYREF
  RTL_SRWLOCK *v17; // [rsp+28h] [rbp-38h] BYREF
  _BYTE Src[16]; // [rsp+30h] [rbp-30h] BYREF
  unsigned __int64 v19; // [rsp+40h] [rbp-20h]
  unsigned __int64 v20; // [rsp+48h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&hKey, a2, 983103);
  std::wstring::wstring(Src, a3);
  if ( *(_QWORD *)(a4 + 16) )
  {
    if ( v19 >= v20 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v19;
      v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v7 + 2 * v8) = 92;
    }
    v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    std::wstring::_Append<unsigned short>(Src, v9);
  }
  if ( *(_QWORD *)(a5 + 16) )
  {
    if ( v19 >= v20 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v19;
      v10 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v10 + 2 * v11) = 92;
    }
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    std::wstring::_Append<unsigned short>(Src, v12);
  }
  AcquireSRWLockExclusive(&stru_180168B88);
  v17 = &stru_180168B88;
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  v14 = RegDeleteTreeW(hKey, v13);
  if ( v14 != 2 && v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x8A7,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)v14,
      (unsigned int)hKey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v17);
  std::wstring::_Tidy_deallocate(Src);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18004941c  mov     [rsp-18h+arg_0], rbx
0x180049421  push    rbp
0x180049422  push    rsi
0x180049423  push    rdi
0x180049424  mov     rbp, rsp
0x180049427  sub     rsp, 60h
0x18004942b  mov     rax, cs:__security_cookie
0x180049432  xor     rax, rsp
0x180049435  mov     [rbp+var_10], rax
0x180049439  mov     rsi, r9
0x18004943c  mov     rbx, r8
0x18004943f  mov     rdi, [rbp+arg_20]
0x180049443  mov     r8d, 0F003Fh
0x180049449  lea     rcx, [rbp+hKey]
0x18004944d  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x180049452  nop
0x180049453  mov     rdx, rbx
0x180049456  lea     rcx, [rbp+Src]
0x18004945a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004945f  nop
0x180049460  mov     ebx, 5Ch ; '\'
0x180049465  cmp     qword ptr [rsi+10h], 0
0x18004946a  jz      short loc_1800494AC
0x18004946c  mov     rdx, [rbp+var_20]
0x180049470  lea     rcx, [rbp+Src]; Src
0x180049474  cmp     rdx, [rbp+var_18]
0x180049478  jnb     short loc_18004948C
0x18004947a  lea     rax, [rdx+1]
0x18004947e  mov     [rbp+var_20], rax
0x180049482  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049487  mov     [rax+rdx*2], ebx
0x18004948a  jmp     short loc_180049494
0x18004948c  mov     r9d, ebx
0x18004948f  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180049494  mov     rcx, rsi
0x180049497  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004949c  mov     r8, [rsi+10h]
0x1800494a0  mov     rdx, rax
0x1800494a3  lea     rcx, [rbp+Src]
0x1800494a7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800494ac  cmp     qword ptr [rdi+10h], 0
0x1800494b1  jz      short loc_1800494F3
0x1800494b3  mov     rdx, [rbp+var_20]
0x1800494b7  lea     rcx, [rbp+Src]; Src
0x1800494bb  cmp     rdx, [rbp+var_18]
0x1800494bf  jnb     short loc_1800494D3
0x1800494c1  lea     rax, [rdx+1]
0x1800494c5  mov     [rbp+var_20], rax
0x1800494c9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800494ce  mov     [rax+rdx*2], ebx
0x1800494d1  jmp     short loc_1800494DB
0x1800494d3  mov     r9d, ebx
0x1800494d6  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x1800494db  mov     rcx, rdi
0x1800494de  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800494e3  mov     r8, [rdi+10h]
0x1800494e7  mov     rdx, rax
0x1800494ea  lea     rcx, [rbp+Src]
0x1800494ee  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800494f3  lea     rbx, stru_180168B88
0x1800494fa  mov     rcx, rbx; SRWLock
0x1800494fd  call    cs:__imp_AcquireSRWLockExclusive
0x180049503  mov     [rbp+var_38], rbx
0x180049507  lea     rcx, [rbp+Src]
0x18004950b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180049510  mov     rdx, rax; lpSubKey
0x180049513  mov     rcx, [rbp+hKey]; hKey
0x180049517  call    cs:__imp_RegDeleteTreeW
0x18004951d  cmp     eax, 2
0x180049520  jz      short loc_18004953F
0x180049522  mov     rcx, [rbp+18h]; this
0x180049526  test    eax, eax
0x180049528  jz      short loc_18004953F
0x18004952a  mov     r9d, eax; char *
0x18004952d  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180049534  mov     edx, 8A7h; void *
0x180049539  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004953f  lea     rcx, [rbp+var_38]
0x180049543  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180049548  nop
0x180049549  lea     rcx, [rbp+Src]
0x18004954d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180049552  nop
0x180049553  lea     rcx, [rbp+hKey]
0x180049557  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004955c  mov     rcx, [rbp+var_10]
0x180049560  xor     rcx, rsp; StackCookie
0x180049563  call    __security_check_cookie
0x180049568  mov     rbx, [rsp+60h+arg_0]
0x180049570  add     rsp, 60h
0x180049574  pop     rdi
0x180049575  pop     rsi
0x180049576  pop     rbp
0x180049577  retn
```
