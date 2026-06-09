# winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(ushort const *)

- ea: `0x18002d6d8`
- end: `0x18002d834`
- name: `?GetOneCoreRegistryKey@implementation@Core@ViewManagement@UI@Windows@winrt@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z`
- size: `348`
- prototype: ``
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800290dc`
- `0x180029b04`
- `0x180029d24`
- `0x180029de4`
- `0x180029ef4`

## callees

- `0x180003980`
- `0x180004344`
- `0x180004e4c`
- `0x180004eb4`
- `0x180006c10`
- `0x18000cf94`
- `0x180028fc0`
- `0x18002cef0`
- `0x18002cfe4`
- `0x18002d2b0`
- `0x18002d4d0`
- `0x18002d6d8`
- `0x18002da88`

## string_xrefs

- `0x18002d7b7`: `onecoreuap\windows\accessibletech\experience\src\winrt\lib\util.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
PHKEY __fastcall winrt::Windows::UI::ViewManagement::Core::implementation::GetOneCoreRegistryKey(
        PHKEY phkResult,
        int a2)
{
  LPWSTR *DefaultAccountSidAsString; // rax
  __int64 v5; // rdx
  int v6; // eax
  PHKEY RegistryKeyWithAcl; // rax
  HKEY phkResulta[3]; // [rsp+38h] [rbp-230h] BYREF
  WCHAR SubKey[256]; // [rsp+50h] [rbp-218h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  phkResulta[1] = (HKEY)phkResult;
  if ( dword_180046F30 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_180046F30);
    if ( dword_180046F30 == -1 )
    {
      DefaultAccountSidAsString = anonymous_namespace_::GetDefaultAccountSidAsString((LPWSTR *)phkResulta);
      v5 = (__int64)*DefaultAccountSidAsString;
      *DefaultAccountSidAsString = 0;
      qword_180046F38 = v5;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(phkResulta);
      Init_thread_footer(&dword_180046F30);
    }
  }
  memset_0(SubKey, 0, sizeof(SubKey));
  v6 = StringCchPrintfW(SubKey, 0x100u, L"%ws\\%ws", qword_180046F38);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x115,
      (unsigned int)"onecoreuap\\windows\\accessibletech\\experience\\src\\winrt\\lib\\util.cpp",
      (const char *)(unsigned int)v6,
      a2);
  anonymous_namespace_::OpenOneCoreRegistryKey(phkResult, SubKey);
  if ( !*phkResult )
  {
    RegistryKeyWithAcl = anonymous_namespace_::CreateRegistryKeyWithAcl(phkResulta, HKEY_USERS, SubKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(
      phkResult,
      RegistryKeyWithAcl);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(phkResulta);
  }
  return phkResult;
}

```

## disassembly

```asm
0x18002d6d8  mov     [rsp+arg_10], rbx
0x18002d6dd  push    rdi
0x18002d6de  sub     rsp, 260h
0x18002d6e5  mov     rax, cs:__security_cookie
0x18002d6ec  xor     rax, rsp
0x18002d6ef  mov     [rsp+268h+var_18], rax
0x18002d6f7  mov     rdi, rdx
0x18002d6fa  mov     rbx, rcx
0x18002d6fd  mov     [rsp+268h+var_228], rcx
0x18002d702  mov     [rsp+268h+var_238], 0
0x18002d70a  mov     ecx, cs:_tls_index
0x18002d710  mov     rax, gs:58h
0x18002d719  mov     edx, 4
0x18002d71e  mov     rax, [rax+rcx*8]
0x18002d722  mov     ecx, [rdx+rax]
0x18002d725  cmp     cs:dword_180046F30, ecx
0x18002d72b  jle     short loc_18002D774
0x18002d72d  lea     rcx, dword_180046F30
0x18002d734  call    _Init_thread_header
0x18002d739  cmp     cs:dword_180046F30, 0FFFFFFFFh
0x18002d740  jnz     short loc_18002D774
0x18002d742  lea     rcx, [rsp+268h+phkResult]; StringSid
0x18002d747  call    _anonymous_namespace___GetDefaultAccountSidAsString
0x18002d74c  mov     rdx, [rax]
0x18002d74f  mov     qword ptr [rax], 0
0x18002d756  mov     cs:qword_180046F38, rdx
0x18002d75d  lea     rcx, [rsp+268h+phkResult]
0x18002d762  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18002d767  nop
0x18002d768  lea     rcx, dword_180046F30
0x18002d76f  call    _Init_thread_footer
0x18002d774  xor     edx, edx; Val
0x18002d776  mov     r8d, 200h; Size
0x18002d77c  lea     rcx, [rsp+268h+SubKey]; void *
0x18002d781  call    memset_0
0x18002d786  mov     qword ptr [rsp+268h+var_248], rdi; int
0x18002d78b  mov     r9, cs:qword_180046F38
0x18002d792  lea     r8, aWsWs; "%ws\\%ws"
0x18002d799  mov     edx, 100h; unsigned __int64
0x18002d79e  lea     rcx, [rsp+268h+SubKey]; unsigned __int16 *
0x18002d7a3  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002d7a8  mov     rcx, [rsp+268h]; this
0x18002d7b0  test    eax, eax
0x18002d7b2  jns     short loc_18002D7C9
0x18002d7b4  mov     r9d, eax; char *
0x18002d7b7  lea     r8, aOnecoreuapWind_0; "onecoreuap\\windows\\accessibletech\\ex"...
0x18002d7be  mov     edx, 115h; void *
0x18002d7c3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002d7c9  lea     rdx, [rsp+268h+SubKey]; lpSubKey
0x18002d7ce  mov     rcx, rbx; phkResult
0x18002d7d1  call    _anonymous_namespace___OpenOneCoreRegistryKey
0x18002d7d6  mov     [rsp+268h+var_238], 1
0x18002d7de  cmp     qword ptr [rbx], 0
0x18002d7e2  jnz     short loc_18002D80F
0x18002d7e4  lea     r8, [rsp+268h+SubKey]; lpSubKey
0x18002d7e9  mov     rdx, 0FFFFFFFF80000003h; hKey
0x18002d7f0  lea     rcx, [rsp+268h+phkResult]; phkResult
0x18002d7f5  call    _anonymous_namespace___CreateRegistryKeyWithAcl
0x18002d7fa  mov     rdx, rax
0x18002d7fd  mov     rcx, rbx
0x18002d800  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &&)
0x18002d805  lea     rcx, [rsp+268h+phkResult]
0x18002d80a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002d80f  mov     rax, rbx
0x18002d812  mov     rcx, [rsp+268h+var_18]
0x18002d81a  xor     rcx, rsp; StackCookie
0x18002d81d  call    __security_check_cookie
0x18002d822  mov     rbx, [rsp+268h+arg_10]
0x18002d82a  add     rsp, 260h
0x18002d831  pop     rdi
0x18002d832  retn
```
