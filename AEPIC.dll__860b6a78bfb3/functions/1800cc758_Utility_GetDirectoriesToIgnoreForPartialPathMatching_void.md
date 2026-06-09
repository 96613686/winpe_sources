# Utility::GetDirectoriesToIgnoreForPartialPathMatching(void)

- ea: `0x1800cc758`
- end: `0x1800cc8c4`
- name: `?GetDirectoriesToIgnoreForPartialPathMatching@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800ce818`

## callees

- `0x180005890`
- `0x180005d10`
- `0x180005ec0`
- `0x180005f28`
- `0x180008570`
- `0x18000faf0`
- `0x18001c5f0`
- `0x1800c97f0`
- `0x1800c993c`
- `0x1800ca4f8`
- `0x1800cc758`
- `0x1800cea08`
- `0x1800d006c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cc7b4`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800cc7b4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800cc7ee`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800cc7ee`

## string_xrefs

- `0x1800cc87c`: `onecore\base\appcompat\inventory\software\inv\lib\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *Utility::GetDirectoriesToIgnoreForPartialPathMatching()
{
  HRESULT v0; // eax
  __int64 v1; // rax
  PWSTR ppszPath; // [rsp+20h] [rbp-60h] BYREF
  RTL_SRWLOCK *v4; // [rsp+28h] [rbp-58h] BYREF
  _BYTE v5[32]; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v6[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  if ( dword_180122E40 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180122E40);
    if ( dword_180122E40 == -1 )
    {
      atexit(Utility::GetDirectoriesToIgnoreForPartialPathMatching_::_2_::_dynamic_atexit_destructor_for__folderList__);
      Init_thread_footer(&dword_180122E40);
    }
  }
  if ( byte_180120D9B )
  {
    AcquireSRWLockExclusive(&stru_180122B68);
    v4 = &stru_180122B68;
    if ( byte_180120D9B )
    {
      ppszPath = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPath,
        0);
      v0 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
      if ( v0 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x465,
          (unsigned int)"onecore\\base\\appcompat\\inventory\\software\\inv\\lib\\utility.cpp",
          (const char *)(unsigned int)v0,
          (int)ppszPath);
      std::wstring::wstring(v5, ppszPath);
      v1 = Utility::ToLower(v6, v5);
      std::vector<std::wstring>::push_back(qword_180122E48, v1);
      std::wstring::_Tidy_deallocate(v6);
      std::wstring::_Tidy_deallocate(v5);
      byte_180120D9B = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v4);
  }
  return qword_180122E48;
}

```

## disassembly

```asm
0x1800cc758  mov     [rsp-8+arg_0], rbx
0x1800cc75d  push    rbp
0x1800cc75e  mov     rbp, rsp
0x1800cc761  sub     rsp, 80h
0x1800cc768  mov     rax, cs:__security_cookie
0x1800cc76f  xor     rax, rsp
0x1800cc772  mov     [rbp+var_10], rax
0x1800cc776  mov     ecx, cs:_tls_index
0x1800cc77c  mov     rax, gs:58h
0x1800cc785  mov     edx, 4
0x1800cc78a  mov     rax, [rax+rcx*8]
0x1800cc78e  mov     eax, [rdx+rax]
0x1800cc791  cmp     cs:dword_180122E40, eax
0x1800cc797  jg      loc_1800CC88E
0x1800cc79d  cmp     cs:byte_180120D9B, 0
0x1800cc7a4  jz      loc_1800CC855
0x1800cc7aa  lea     rbx, stru_180122B68
0x1800cc7b1  mov     rcx, rbx; SRWLock
0x1800cc7b4  call    cs:__imp_AcquireSRWLockExclusive
0x1800cc7ba  mov     [rbp+var_58], rbx
0x1800cc7be  cmp     cs:byte_180120D9B, 0
0x1800cc7c5  jz      loc_1800CC84C
0x1800cc7cb  mov     [rbp+ppszPath], 0
0x1800cc7d3  xor     edx, edx
0x1800cc7d5  lea     rcx, [rbp+ppszPath]
0x1800cc7d9  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800cc7de  lea     r9, [rbp+ppszPath]; ppszPath
0x1800cc7e2  xor     r8d, r8d; hToken
0x1800cc7e5  xor     edx, edx; dwFlags
0x1800cc7e7  lea     rcx, FOLDERID_Windows; rfid
0x1800cc7ee  call    cs:__imp_SHGetKnownFolderPath
0x1800cc7f4  mov     rcx, [rbp+8]; this
0x1800cc7f8  test    eax, eax
0x1800cc7fa  js      short loc_1800CC879
0x1800cc7fc  mov     rdx, [rbp+ppszPath]
0x1800cc800  lea     rcx, [rbp+var_50]
0x1800cc804  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800cc809  nop
0x1800cc80a  lea     rdx, [rbp+var_50]
0x1800cc80e  lea     rcx, [rbp+var_30]
0x1800cc812  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800cc817  nop
0x1800cc818  mov     rdx, rax
0x1800cc81b  lea     rcx, qword_180122E48
0x1800cc822  call    ?push_back@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAX$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::vector<std::wstring>::push_back(std::wstring &&)
0x1800cc827  nop
0x1800cc828  lea     rcx, [rbp+var_30]
0x1800cc82c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc831  nop
0x1800cc832  lea     rcx, [rbp+var_50]
0x1800cc836  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800cc83b  mov     cs:byte_180120D9B, 0
0x1800cc842  lea     rcx, [rbp+ppszPath]
0x1800cc846  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800cc84b  nop
0x1800cc84c  lea     rcx, [rbp+var_58]
0x1800cc850  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800cc855  lea     rax, qword_180122E48
0x1800cc85c  mov     rcx, [rbp+var_10]
0x1800cc860  xor     rcx, rsp; StackCookie
0x1800cc863  call    __security_check_cookie
0x1800cc868  mov     rbx, [rsp+80h+arg_0]
0x1800cc870  add     rsp, 80h
0x1800cc877  pop     rbp
0x1800cc878  retn
0x1800cc879  mov     r9d, eax; char *
0x1800cc87c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appcompat\\inventory\\so"...
0x1800cc883  mov     edx, 465h; void *
0x1800cc888  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800cc88e  lea     rcx, dword_180122E40
0x1800cc895  call    _Init_thread_header
0x1800cc89a  cmp     cs:dword_180122E40, 0FFFFFFFFh
0x1800cc8a1  jnz     loc_1800CC79D
0x1800cc8a7  lea     rcx, _Utility__GetDirectoriesToIgnoreForPartialPathMatching____2____dynamic_atexit_destructor_for__folderList__; void (__cdecl *)()
0x1800cc8ae  call    atexit
0x1800cc8b3  lea     rcx, dword_180122E40
0x1800cc8ba  call    _Init_thread_footer
0x1800cc8bf  jmp     loc_1800CC79D
```
