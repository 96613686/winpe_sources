# Utility::GetDirectoriesToIgnoreForPartialPathMatching(void)

- ea: `0x1800261d8`
- end: `0x180026364`
- name: `?GetDirectoriesToIgnoreForPartialPathMatching@Utility@@SAAEBV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@XZ`
- size: `396`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800260f4`

## callees

- `0x18000e458`
- `0x180018300`
- `0x180018a60`
- `0x1800261d8`
- `0x1800404c4`
- `0x18004869c`
- `0x1800493b8`
- `0x18004f380`
- `0x180053020`
- `0x180059920`
- `0x180059cd0`
- `0x180059f2c`
- `0x180059f94`
- `0x1800679f8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x180026337`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180026337`
- `SHELL32!SHGetKnownFolderPath` at `0x18002627b`
- `SHELL32!SHGetKnownFolderPath` at `0x18002627b`

## string_xrefs

- `0x180026352`: `onecore\internal\base\inc\appcompat\inventory\utility.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 *Utility::GetDirectoriesToIgnoreForPartialPathMatching()
{
  HRESULT v1; // eax
  __int64 v2; // rdx
  PWSTR ppszPath; // [rsp+20h] [rbp-60h] BYREF
  _QWORD v4[2]; // [rsp+28h] [rbp-58h] BYREF
  __int64 v5[4]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v6[32]; // [rsp+58h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]

  v4[1] = -2;
  if ( dword_1801841A0 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_1801841A0);
    if ( dword_1801841A0 == -1 )
    {
      std::vector<enum tagMSIINSTALLCONTEXT>::vector<enum tagMSIINSTALLCONTEXT>(qword_1801841A8);
      atexit(Utility::GetDirectoriesToIgnoreForPartialPathMatching_::_2_::_dynamic_atexit_destructor_for__folderList__);
      Init_thread_footer(&dword_1801841A0);
    }
  }
  if ( byte_1801817E8 )
  {
    AcquireSRWLockExclusive(&stru_180183E68);
    v4[0] = &stru_180183E68;
    if ( byte_1801817E8 )
    {
      ppszPath = 0;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &ppszPath,
        0);
      v1 = SHGetKnownFolderPath(&FOLDERID_Windows, 0, 0, &ppszPath);
      if ( v1 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x465,
          (unsigned int)"onecore\\internal\\base\\inc\\appcompat\\inventory\\utility.cpp",
          (const char *)(unsigned int)v1,
          (int)ppszPath);
      std::wstring::wstring(v5, ppszPath);
      v2 = Utility::ToLower((__int64)v6, v5);
      std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(qword_1801841A8, v2);
      std::wstring::~wstring(v6);
      std::wstring::~wstring(v5);
      byte_1801817E8 = 0;
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppszPath);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v4);
  }
  return qword_1801841A8;
}

```

## disassembly

```asm
0x1800261d8  mov     rax, rsp
0x1800261db  push    rbp
0x1800261dc  mov     rbp, rsp
0x1800261df  sub     rsp, 80h
0x1800261e6  mov     [rbp+var_50], 0FFFFFFFFFFFFFFFEh
0x1800261ee  mov     [rax+8], rbx
0x1800261f2  mov     rax, cs:__security_cookie
0x1800261f9  xor     rax, rsp
0x1800261fc  mov     [rbp+var_8], rax
0x180026200  mov     ecx, cs:_tls_index
0x180026206  mov     rax, gs:58h
0x18002620f  mov     edx, 4
0x180026214  mov     rax, [rax+rcx*8]
0x180026218  mov     eax, [rdx+rax]
0x18002621b  cmp     cs:dword_1801841A0, eax
0x180026221  jg      loc_1800262EB
0x180026227  cmp     cs:byte_1801817E8, 0
0x18002622e  jnz     loc_18002632D
0x180026234  lea     rax, qword_1801841A8
0x18002623b  mov     rcx, [rbp+var_8]
0x18002623f  xor     rcx, rsp; StackCookie
0x180026242  call    __security_check_cookie
0x180026247  mov     rbx, [rsp+80h+arg_0]
0x18002624f  add     rsp, 80h
0x180026256  pop     rbp
0x180026257  retn
0x180026258  mov     [rbp+ppszPath], 0
0x180026260  xor     edx, edx
0x180026262  lea     rcx, [rbp+ppszPath]
0x180026266  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002626b  lea     r9, [rbp+ppszPath]; ppszPath
0x18002626f  xor     r8d, r8d; hToken
0x180026272  xor     edx, edx; dwFlags
0x180026274  lea     rcx, FOLDERID_Windows; rfid
0x18002627b  call    cs:__imp_SHGetKnownFolderPath
0x180026281  mov     rcx, [rbp+8]; this
0x180026285  test    eax, eax
0x180026287  js      loc_18002634F
0x18002628d  mov     rdx, [rbp+ppszPath]
0x180026291  lea     rcx, [rbp+var_48]
0x180026295  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002629a  nop
0x18002629b  lea     rdx, [rbp+var_48]
0x18002629f  lea     rcx, [rbp+var_28]
0x1800262a3  call    ?ToLower@Utility@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV23@@Z; Utility::ToLower(std::wstring const &)
0x1800262a8  nop
0x1800262a9  mov     rdx, rax
0x1800262ac  lea     rcx, qword_1801841A8
0x1800262b3  call    ??$_Emplace_one_at_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_one_at_back<std::wstring>(std::wstring &&)
0x1800262b8  nop
0x1800262b9  lea     rcx, [rbp+var_28]
0x1800262bd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800262c2  nop
0x1800262c3  lea     rcx, [rbp+var_48]
0x1800262c7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800262cc  mov     cs:byte_1801817E8, 0
0x1800262d3  lea     rcx, [rbp+ppszPath]
0x1800262d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800262dc  nop
0x1800262dd  lea     rcx, [rbp+var_58]
0x1800262e1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800262e6  jmp     loc_180026234
0x1800262eb  lea     rcx, dword_1801841A0
0x1800262f2  call    _Init_thread_header
0x1800262f7  cmp     cs:dword_1801841A0, 0FFFFFFFFh
0x1800262fe  jnz     loc_180026227
0x180026304  lea     rcx, qword_1801841A8
0x18002630b  call    ??0?$vector@W4tagMSIINSTALLCONTEXT@@V?$allocator@W4tagMSIINSTALLCONTEXT@@@std@@@std@@QEAA@XZ; std::vector<tagMSIINSTALLCONTEXT>::vector<tagMSIINSTALLCONTEXT>(void)
0x180026310  lea     rcx, _Utility__GetDirectoriesToIgnoreForPartialPathMatching____2____dynamic_atexit_destructor_for__folderList__; void (__cdecl *)()
0x180026317  call    atexit
0x18002631c  lea     rcx, dword_1801841A0
0x180026323  call    _Init_thread_footer
0x180026328  jmp     loc_180026227
0x18002632d  lea     rbx, stru_180183E68
0x180026334  mov     rcx, rbx; SRWLock
0x180026337  call    cs:__imp_AcquireSRWLockExclusive
0x18002633d  mov     [rbp+var_58], rbx
0x180026341  cmp     cs:byte_1801817E8, 0
0x180026348  jz      short loc_1800262DD
0x18002634a  jmp     loc_180026258
0x18002634f  mov     r9d, eax; char *
0x180026352  lea     r8, aOnecoreInterna_2; "onecore\\internal\\base\\inc\\appcompat"...
0x180026359  mov     edx, 465h; void *
0x18002635e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
