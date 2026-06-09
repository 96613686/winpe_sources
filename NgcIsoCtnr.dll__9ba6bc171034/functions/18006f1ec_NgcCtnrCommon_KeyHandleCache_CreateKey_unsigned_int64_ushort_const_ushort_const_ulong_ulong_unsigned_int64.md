# NgcCtnrCommon::KeyHandleCache::CreateKey(unsigned __int64,ushort const *,ushort const *,ulong,ulong,unsigned __int64 *)

- ea: `0x18006f1ec`
- end: `0x18006f30c`
- name: `?CreateKey@KeyHandleCache@NgcCtnrCommon@@QEAAJ_KPEBG1KKPEA_K@Z`
- size: `288`
- prototype: `__int64 __fastcall(PSRWLOCK SRWLock, NCRYPT_PROV_HANDLE hProvider, LPCWSTR pszAlgId, LPCWSTR pszKeyName, unsigned int, unsigned int, unsigned __int64 *)`
- caller_count: `3`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ea1c`
- `0x180024820`
- `0x180048c48`

## callees

- `0x180007670`
- `0x18000a168`
- `0x18000d62c`
- `0x1800108e4`
- `0x180011c9c`
- `0x180017d70`
- `0x18001dc68`
- `0x18002bfec`
- `0x18006f02c`
- `0x18006f1b4`
- `0x18006f1ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f2a2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18006f2a2`
- `ncrypt!NCryptCreatePersistedKey` at `0x18006f24f`
- `ncrypt!NCryptCreatePersistedKey` at `0x18006f24f`

## string_xrefs

- `0x18006f262`: `onecore\ds\security\ngc\ctnrsvc\common\keyhandlecache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NgcCtnrCommon::KeyHandleCache::CreateKey(
        PSRWLOCK SRWLock,
        NCRYPT_PROV_HANDLE hProvider,
        LPCWSTR pszAlgId,
        LPCWSTR pszKeyName,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 *a7)
{
  SECURITY_STATUS v11; // eax
  unsigned int v12; // ebx
  NCRYPT_KEY_HANDLE v13; // rbx
  __int64 v14; // rax
  _QWORD *v15; // rax
  DWORD dwLegacyKeySpec; // [rsp+20h] [rbp-61h]
  PSRWLOCK v18; // [rsp+30h] [rbp-51h] BYREF
  _BYTE v19[32]; // [rsp+38h] [rbp-49h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+58h] [rbp-29h] BYREF
  NCRYPT_PROV_HANDLE v21; // [rsp+60h] [rbp-21h] BYREF
  _BYTE v22[32]; // [rsp+68h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  phKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(
    &phKey,
    0);
  v11 = NCryptCreatePersistedKey(hProvider, &phKey, pszAlgId, pszKeyName, 0, 0);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v13 = phKey;
    v14 = std::wstring::wstring(v19, pszKeyName);
    v21 = hProvider;
    std::wstring::wstring(v22, v14);
    std::wstring::_Tidy_deallocate(v19);
    AcquireSRWLockExclusive(SRWLock);
    v18 = SRWLock;
    v15 = (_QWORD *)std::map<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::_Try_emplace<std::pair<unsigned __int64,std::wstring> const &,>(
                      &SRWLock[1],
                      v19,
                      &v21);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::operator=(
      *v15 + 72LL,
      &phKey);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v18);
    *a7 = v13;
    std::wstring::_Tidy_deallocate(v22);
    v12 = 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\common\\keyhandlecache.cpp",
      (const char *)(unsigned int)v11,
      dwLegacyKeySpec);
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
  return v12;
}

```

## disassembly

```asm
0x18006f1ec  push    rbp
0x18006f1ee  push    rbx
0x18006f1ef  push    rsi
0x18006f1f0  push    rdi
0x18006f1f1  push    r14
0x18006f1f3  push    r15
0x18006f1f5  lea     rbp, [rsp-17h]
0x18006f1fa  sub     rsp, 98h
0x18006f201  mov     rax, cs:__security_cookie
0x18006f208  xor     rax, rsp
0x18006f20b  mov     [rbp+3Fh+var_38], rax
0x18006f20f  mov     r14, r9
0x18006f212  mov     rbx, r8
0x18006f215  mov     rsi, rdx
0x18006f218  mov     rdi, rcx
0x18006f21b  mov     r15, [rbp+3Fh+arg_30]
0x18006f21f  mov     [rbp+3Fh+phKey], 0
0x18006f227  xor     edx, edx
0x18006f229  lea     rcx, [rbp+3Fh+phKey]
0x18006f22d  call    ?reset@?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAAX_K@Z; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::reset(unsigned __int64)
0x18006f232  mov     [rsp+0C0h+dwFlags], 0; dwFlags
0x18006f23a  mov     [rsp+0C0h+dwLegacyKeySpec], 0; int
0x18006f242  mov     r9, r14; pszKeyName
0x18006f245  mov     r8, rbx; pszAlgId
0x18006f248  lea     rdx, [rbp+3Fh+phKey]; phKey
0x18006f24c  mov     rcx, rsi; hProvider
0x18006f24f  call    cs:__imp_NCryptCreatePersistedKey
0x18006f255  mov     ebx, eax
0x18006f257  test    eax, eax
0x18006f259  jns     short loc_18006F275
0x18006f25b  mov     rcx, [rbp+47h]; this
0x18006f25f  mov     r9d, eax; char *
0x18006f262  lea     r8, aOnecoreDsSecur_13; "onecore\\ds\\security\\ngc\\ctnrsvc\\co"...
0x18006f269  mov     edx, 1Eh; void *
0x18006f26e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f273  jmp     short loc_18006F2E5
0x18006f275  mov     rbx, [rbp+3Fh+phKey]
0x18006f279  mov     rdx, r14
0x18006f27c  lea     rcx, [rbp+3Fh+var_88]
0x18006f280  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006f285  mov     [rbp+3Fh+var_60], rsi
0x18006f289  mov     rdx, rax
0x18006f28c  lea     rcx, [rbp+3Fh+var_58]
0x18006f290  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18006f295  nop
0x18006f296  lea     rcx, [rbp+3Fh+var_88]
0x18006f29a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f29f  mov     rcx, rdi; SRWLock
0x18006f2a2  call    cs:__imp_AcquireSRWLockExclusive
0x18006f2a8  mov     [rbp+3Fh+var_90], rdi
0x18006f2ac  lea     rcx, [rdi+8]
0x18006f2b0  lea     r8, [rbp+3Fh+var_60]
0x18006f2b4  lea     rdx, [rbp+3Fh+var_88]
0x18006f2b8  call    ??$_Try_emplace@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@$$V@?$map@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@U?$less@U?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@2@V?$allocator@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@@2@@std@@AEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAX@std@@_N@1@AEBU?$pair@_KV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@@Z; std::map<std::pair<unsigned __int64,std::wstring>,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::_Try_emplace<std::pair<unsigned __int64,std::wstring> const &,>(std::pair<unsigned __int64,std::wstring> const &)
0x18006f2bd  mov     rcx, [rax]
0x18006f2c0  add     rcx, 48h ; 'H'
0x18006f2c4  lea     rdx, [rbp+3Fh+phKey]
0x18006f2c8  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>> &&)
0x18006f2cd  nop
0x18006f2ce  lea     rcx, [rbp+3Fh+var_90]
0x18006f2d2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18006f2d7  mov     [r15], rbx
0x18006f2da  lea     rcx, [rbp+3Fh+var_58]
0x18006f2de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006f2e3  xor     ebx, ebx
0x18006f2e5  lea     rcx, [rbp+3Fh+phKey]
0x18006f2e9  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18006f2ee  mov     eax, ebx
0x18006f2f0  mov     rcx, [rbp+3Fh+var_38]
0x18006f2f4  xor     rcx, rsp; StackCookie
0x18006f2f7  call    __security_check_cookie
0x18006f2fc  add     rsp, 98h
0x18006f303  pop     r15
0x18006f305  pop     r14
0x18006f307  pop     rdi
0x18006f308  pop     rsi
0x18006f309  pop     rbx
0x18006f30a  pop     rbp
0x18006f30b  retn
```
